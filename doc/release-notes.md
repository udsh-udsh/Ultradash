(note: this is a temporary file, to be added-to by anybody, and moved to release-notes at release time)

Ultradash Coin version *version* is now available from:  <https://github.com/ultradash-project/ultradash/releases>

This is a new major version release, including various bug fixes and performance improvements, as well as updated translations.

Please report bugs using the issue tracker at github: <https://github.com/ultradash-project/ultradash/issues>


Mandatory Update
==============


How to Upgrade
==============

If you are running an older version, shut it down. Wait until it has completely shut down (which might take a few minutes for older versions), then run the installer (on Windows) or just copy over /Applications/Ultradash-Qt (on Mac) or ultradashd/ultradash-qt (on Linux).


Compatibility
==============

Ultradash Coin is extensively tested on multiple operating systems using the Linux kernel, macOS 10.10+, and Windows 7 and later.

Microsoft ended support for Windows XP on [April 8th, 2014](https://www.microsoft.com/en-us/WindowsForBusiness/end-of-xp-support), No attempt is made to prevent installing or running the software on Windows XP, you can still do so at your own risk but be aware that there are known instabilities and issues. Please do not report issues about Windows XP to the issue tracker.

Apple released it's last Mountain Lion update August 13, 2015, and officially ended support on [December 14, 2015](http://news.fnal.gov/2015/10/mac-os-x-mountain-lion-10-8-end-of-life-december-14/). Ultradash Coin software starting with v3.2.0 will no longer run on MacOS versions prior to Yosemite (10.10). Please do not report issues about MacOS versions prior to Yosemite to the issue tracker.

Ultradash Coin should also work on most other Unix-like systems but is not frequently tested on them.

 
Notable Changes
==============

## GUI Changes

### Options Dialog Cleanup

The options/settings UI dialog has been cleaned up to no longer show settings that are wallet related when running in "disable wallet" (`-disablewallet`) mode.

## RPC Changes

### Removal of Deprecated Commands

The `masternode` and `mnbudget` RPC commands, which were marked as deprecated in Ultradash Coin v2.3.1 (September 19, 2017), have now been completely removed from Ultradash Coin.

Several new commands were added in v2.3.1 to replace the two aforementioned commands, reference the [v2.3.1 Release Notes](https://github.com/Ultradash-Project/Ultradash/blob/master/doc/release-notes/release-notes-2.3.1.md#rpc-changes) for further details.

### New `getblockindexstats` Command

A new RPC command (`getblockindexstats`) has been introduced which serves the purpose of obtaining statistical information on a range of blocks. The information returned is as follows:
  * transaction count (not including coinbase/coinstake txes)
  * transaction count (including coinbase/coinstake txes)
  * total transaction bytes
  * total fees in block range
  * average fee per kB

Command Reference:
```$xslt
getblockindexstats height range ( fFeeOnly )
nReturns aggregated BlockIndex data for blocks
height, height+1, height+2, ..., height+range-1]

nArguments:
1. height             (numeric, required) block height where the search starts.
2. range              (numeric, required) number of blocks to include.
3. fFeeOnly           (boolean, optional, default=False) return only fee info.
```
Result:
```
{
  first_block: x,              (integer) First counted block
  last_block: x,               (integer) Last counted block
  txcount: xxxxx,              (numeric) tx count (excluding coinbase/coinstake)
  txcount_all: xxxxx,          (numeric) tx count (including coinbase/coinstake)
  feeperkb: xxxxx,             (numeric) Average fee per kb (excluding zc txes)
}
```

## Build System Changes

### New Architectures for Depends

The depends system has new added support for the `s390x` and `ppc64el` architectures. This is done in order to support the future integration with [Snapcraft](https://www.snapcraft.io), as well as to support any developers who may use systems based on such architectures.

### Basic CMake Support

While the existing Autotools based build system is our standard build system, and will continue to be so, we have added basic support for compiling with CMake on macOS and linux systems.

This is intended to be used in conjunction with IDEs like CLion (which relies heavily on CMake) in order to streamline the development process. Developers can now use, for example, CLion's internal debugger and profiling tools.

Note that it is still required to have relevant dependencies installed on the system for this to function properly.

*version* Change log
==============

Detailed release notes follow. This overview includes changes that affect behavior, not code moves, refactors and string updates. For convenience in locating the code changes and accompanying discussion, both the pull request and git merge commit are mentioned.

### Core Features

### Build System
 
### P2P Protocol and Network Code

### GUI
 
### RPC/REST

### Wallet
 
### Miscellaneous
 
 
## Credits

Thanks to everyone who directly contributed to this release:


As well as everyone that helped translating on [Transifex](https://www.transifex.com/projects/p/ultradash-project-translations/), the QA team during Testing and the Node hosts supporting our Testnet.
