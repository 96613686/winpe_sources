# VdocumentStore::updateDocument(VdbServer const *,VrbsCollectionId,VwcharPtrStorePath const &,VwcharPtrStorePath const &,VwcharPtrStorePath const &,VfileBlobManager *,uchar const *,ulong,ulong,ulong,ulong &,char,VtriState,char,char,char,Vtime const &,Vtime &,ulong &,VdocHandle *,VvirusCheck *,VlinkVvector const *,wchar_t const * *,uchar const *,ulong,__int64,ulong,uint,char const *,char,char,Vstring,VwcharPtrStorePath,wchar_t const *,long,long,long,char,char,long,SPFileSaveParams const *,ulong &,ulong,__int64 *,uchar *,char,long,char,char)

- ea: `0x1800e0fa0`
- end: `0x1800e40e8`
- name: `?updateDocument@VdocumentStore@@QEAA?AVVHRESULT@@PEBVVdbServer@@VVrbsCollectionId@@AEBVVwcharPtrStorePath@@22PEAVVfileBlobManager@@PEBEKKKAEAKDW4VtriState@@DDDAEBVVtime@@AEAV8@5PEAVVdocHandle@@PEAVVvirusCheck@@PEBVVlinkVvector@@PEAPEB_W4K_JKIPEBDDDVVstring@@V5@PEB_WJJJDDJPEBUSPFileSaveParams@@5KPEA_JPEAEDJDD@Z`
- size: `12616`
- prototype: `struct VHRESULT __high(const struct VdbServer *, struct VrbsCollectionId, const struct VwcharPtrStorePath *, const struct VwcharPtrStorePath *, const struct VwcharPtrStorePath *, struct VfileBlobManager *, const unsigned __int8 *, unsigned int, unsigned int, unsigned int, unsigned int *, char, enum VtriState, char, char, char, const struct Vtime *, struct Vtime *, unsigned int *, struct VdocHandle *, struct VvirusCheck *, const struct VlinkVvector *, const wchar_t **, const unsigned __int8 *, unsigned int, __int64, unsigned int, unsigned int, const char *, char, char, struct Vstring, struct VwcharPtrStorePath, const wchar_t *, int, int, int, char, char, int, const struct SPFileSaveParams *, unsigned int *, unsigned int, __int64 *, unsigned __int8 *, char, int, char, char)`
- caller_count: `1`
- callee_count: `79`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800fc0d0`

## callees

- `0x1800012d0`
- `0x180007a30`
- `0x180007a80`
- `0x180007ce0`
- `0x180008460`
- `0x180008480`
- `0x18000b570`
- `0x18000df60`
- `0x18000e0a0`
- `0x18000e880`
- `0x18000fac0`
- `0x18001e0e4`
- `0x18001ea60`
- `0x1800208f0`
- `0x180028a08`
- `0x180029938`
- `0x180029c50`
- `0x18002ba50`
- `0x18004a6c0`
- `0x18004a760`
- `0x18008ea50`
- `0x1800974f0`
- `0x1800a3f10`
- `0x1800b3550`
- `0x1800b4140`
- `0x1800b48e0`
- `0x1800b54d0`
- `0x1800b5d00`
- `0x1800b5e70`
- `0x1800c407c`
- `0x1800c40f4`
- `0x1800c4188`
- `0x1800dd3d0`
- `0x1800dd67c`
- `0x1800e0fa0`
- `0x1800eee90`
- `0x1800ef850`
- `0x1800f7710`
- `0x1800f7800`
- `0x1800f7de0`
- `0x1800f8270`
- `0x1800fe480`
- `0x1800ffbf0`
- `0x180102620`
- `0x1801026d0`
- `0x18010cee0`
- `0x180173a70`
- `0x18017fbb0`
- `0x180181b60`
- `0x180181c70`

## import_xrefs

- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x1800e1217`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x1800e247f`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x1800e1217`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x1800e247f`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x1800e133c`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x1800e13d5`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x1800e2eba`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x1800e3bd4`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x1800e3ce1`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x1800e133c`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x1800e13d5`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x1800e2eba`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x1800e3bd4`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x1800e3ce1`
- `onetutil!??0VHRESULT@@QEAA@AEBV0@@Z` at `0x1800e138a`
- `onetutil!??0VHRESULT@@QEAA@AEBV0@@Z` at `0x1800e32e1`
- `onetutil!??0VHRESULT@@QEAA@AEBV0@@Z` at `0x1800e3ca1`
- `onetutil!??0VHRESULT@@QEAA@AEBV0@@Z` at `0x1800e3cc3`
- `onetutil!??0VHRESULT@@QEAA@AEBV0@@Z` at `0x1800e3d02`
- `onetutil!??0VHRESULT@@QEAA@AEBV0@@Z` at `0x1800e3fd4`
- `onetutil!??0VHRESULT@@QEAA@AEBV0@@Z` at `0x1800e3ffa`
- `onetutil!??0VHRESULT@@QEAA@AEBV0@@Z` at `0x1800e138a`
- `onetutil!??0VHRESULT@@QEAA@AEBV0@@Z` at `0x1800e32e1`
- `onetutil!??0VHRESULT@@QEAA@AEBV0@@Z` at `0x1800e3ca1`
- `onetutil!??0VHRESULT@@QEAA@AEBV0@@Z` at `0x1800e3cc3`
- `onetutil!??0VHRESULT@@QEAA@AEBV0@@Z` at `0x1800e3d02`
- `onetutil!??0VHRESULT@@QEAA@AEBV0@@Z` at `0x1800e3fd4`
- `onetutil!??0VHRESULT@@QEAA@AEBV0@@Z` at `0x1800e3ffa`
- `onetutil!??0Vwstring@@QEAA@PEB_W@Z` at `0x1800e272c`
- `onetutil!??0Vwstring@@QEAA@PEB_W@Z` at `0x1800e278c`
- `onetutil!??0Vwstring@@QEAA@PEB_W@Z` at `0x1800e272c`
- `onetutil!??0Vwstring@@QEAA@PEB_W@Z` at `0x1800e278c`
- `onetutil!??0VwstringVvector@@QEAA@XZ` at `0x1800e11de`
- `onetutil!??0VwstringVvector@@QEAA@XZ` at `0x1800e11de`
- `onetutil!??1VwstringVvector@@QEAA@XZ` at `0x1800e4072`
- `onetutil!??1VwstringVvector@@QEAA@XZ` at `0x1800e4072`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e13ae`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e1543`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e1913`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e1b6c`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e2bde`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e2cd2`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e2d4e`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e2f15`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e3299`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e3302`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e334b`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e33a5`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e3405`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e3468`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e34ff`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e3554`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e35a9`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e3676`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e36cb`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e37a1`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e3c1e`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e3d3e`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e13ae`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e1543`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e1913`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e1b6c`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e2bde`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e2cd2`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e2d4e`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e2f15`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e3299`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e3302`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e334b`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e33a5`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e3405`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e3468`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e34ff`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e3554`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e35a9`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e3676`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e36cb`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e37a1`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e3c1e`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800e3d3e`
- `onetutil!??0Vstring@@QEAA@PEB_W@Z` at `0x1800e3e4b`
- `onetutil!??0Vstring@@QEAA@PEB_W@Z` at `0x1800e3e8f`
- `onetutil!??0Vstring@@QEAA@PEB_W@Z` at `0x1800e3e4b`
- `onetutil!??0Vstring@@QEAA@PEB_W@Z` at `0x1800e3e8f`
- `onetutil!??0Vwstring@@QEAA@PEBD@Z` at `0x1800e1227`
- `onetutil!??0Vwstring@@QEAA@PEBD@Z` at `0x1800e1227`
- `onetutil!??0Vtime@@QEAA@_K@Z` at `0x1800e16ee`
- `onetutil!??0Vtime@@QEAA@_K@Z` at `0x1800e2143`
- `onetutil!??0Vtime@@QEAA@_K@Z` at `0x1800e34b0`
- `onetutil!??0Vtime@@QEAA@_K@Z` at `0x1800e16ee`
- `onetutil!??0Vtime@@QEAA@_K@Z` at `0x1800e2143`
- `onetutil!??0Vtime@@QEAA@_K@Z` at `0x1800e34b0`
- `onetutil!?secondsI64@Vtime@@QEBA_KXZ` at `0x1800e12bb`
- `onetutil!?secondsI64@Vtime@@QEBA_KXZ` at `0x1800e12bb`
- `onetutil!??0Vwstring@@QEAA@AEBVVstring@@@Z` at `0x1800e3885`
- `onetutil!??0Vwstring@@QEAA@AEBVVstring@@@Z` at `0x1800e38e0`
- `onetutil!??0Vwstring@@QEAA@AEBVVstring@@@Z` at `0x1800e39d0`
- `onetutil!??0Vwstring@@QEAA@AEBVVstring@@@Z` at `0x1800e3a6f`
- `onetutil!??0Vwstring@@QEAA@AEBVVstring@@@Z` at `0x1800e3885`
- `onetutil!??0Vwstring@@QEAA@AEBVVstring@@@Z` at `0x1800e38e0`
- `onetutil!??0Vwstring@@QEAA@AEBVVstring@@@Z` at `0x1800e39d0`
- `onetutil!??0Vwstring@@QEAA@AEBVVstring@@@Z` at `0x1800e3a6f`
- `onetutil!?Vitostr@@YA?AVVstring@@J@Z` at `0x1800e39c2`
- `onetutil!?Vitostr@@YA?AVVstring@@J@Z` at `0x1800e3a61`
- `onetutil!?Vitostr@@YA?AVVstring@@J@Z` at `0x1800e39c2`
- `onetutil!?Vitostr@@YA?AVVstring@@J@Z` at `0x1800e3a61`
- `onetutil!?setFromInt@Vstring@@QEAAXJ@Z` at `0x1800e3824`
- `onetutil!?setFromInt@Vstring@@QEAAXJ@Z` at `0x1800e3836`
- `onetutil!?setFromInt@Vstring@@QEAAXJ@Z` at `0x1800e3824`
- `onetutil!?setFromInt@Vstring@@QEAAXJ@Z` at `0x1800e3836`
- `onetutil!?getString@VmetaDict@@QEBADPEBDPEAPEBDPEAW4Access@1@@Z` at `0x1800e19fc`
- `onetutil!?getString@VmetaDict@@QEBADPEBDPEAPEBDPEAW4Access@1@@Z` at `0x1800e19fc`
- `onetutil!?getBool@VmetaDict@@QEBADPEBDPEADPEAW4Access@1@@Z` at `0x1800e159d`
- `onetutil!?getBool@VmetaDict@@QEBADPEBDPEADPEAW4Access@1@@Z` at `0x1800e159d`
- `onetutil!?setInt@VmetaDict@@QEAADPEBDJW4Access@1@W4OP@Vdict@@@Z` at `0x1800e184b`
- `onetutil!?setInt@VmetaDict@@QEAADPEBDJW4Access@1@W4OP@Vdict@@@Z` at `0x1800e185b`
- `onetutil!?setInt@VmetaDict@@QEAADPEBDJW4Access@1@W4OP@Vdict@@@Z` at `0x1800e184b`
- `onetutil!?setInt@VmetaDict@@QEAADPEBDJW4Access@1@W4OP@Vdict@@@Z` at `0x1800e185b`
- `onetutil!?setBool@VmetaDict@@QEAADPEBDDW4Access@1@W4OP@Vdict@@@Z` at `0x1800e19b6`
- `onetutil!?setBool@VmetaDict@@QEAADPEBDDW4Access@1@W4OP@Vdict@@@Z` at `0x1800e19b6`
- `onetutil!?getInt@VmetaDict@@QEBADPEBDPEAJPEAW4Access@1@@Z` at `0x1800e15ce`
- `onetutil!?getInt@VmetaDict@@QEBADPEBDPEAJPEAW4Access@1@@Z` at `0x1800e1602`
- `onetutil!?getInt@VmetaDict@@QEBADPEBDPEAJPEAW4Access@1@@Z` at `0x1800e15ce`
- `onetutil!?getInt@VmetaDict@@QEBADPEBDPEAJPEAW4Access@1@@Z` at `0x1800e1602`
- `onetutil!?safeAppend@?$VurlTemplate@VVstoreUrlSettings@@@@QEAAXVVstring@@@Z` at `0x1800e3ebc`
- `onetutil!?safeAppend@?$VurlTemplate@VVstoreUrlSettings@@@@QEAAXVVstring@@@Z` at `0x1800e3ebc`
- `onetutil!??0Vstring@@QEAA@AEBV0@@Z` at `0x1800e3e65`
- `onetutil!??0Vstring@@QEAA@AEBV0@@Z` at `0x1800e3eae`
- `onetutil!??0Vstring@@QEAA@AEBV0@@Z` at `0x1800e3e65`
- `onetutil!??0Vstring@@QEAA@AEBV0@@Z` at `0x1800e3eae`
- `onetutil!??0Vstring@@QEAA@XZ` at `0x1800e3802`
- `onetutil!??0Vstring@@QEAA@XZ` at `0x1800e380d`
- `onetutil!??0Vstring@@QEAA@XZ` at `0x1800e3ed9`
- `onetutil!??0Vstring@@QEAA@XZ` at `0x1800e3802`
- `onetutil!??0Vstring@@QEAA@XZ` at `0x1800e380d`
- `onetutil!??0Vstring@@QEAA@XZ` at `0x1800e3ed9`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800e3a05`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800e3aa4`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800e3bec`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800e3bf7`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800e3e73`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800e3ec7`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800e3f92`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800e4034`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800e40b4`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800e3a05`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800e3aa4`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800e3bec`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800e3bf7`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800e3e73`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800e3ec7`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800e3f92`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800e4034`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800e40b4`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1800e2748`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1800e27a8`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1800e38af`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1800e390a`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1800e39fa`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1800e3a99`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1800e4057`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1800e2748`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1800e27a8`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1800e38af`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1800e390a`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1800e39fa`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1800e3a99`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1800e4057`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800e1406`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800e1406`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x1800e3861`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x1800e3892`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x1800e38bc`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x1800e38ed`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x1800e3917`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x1800e3973`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x1800e399f`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x1800e39dd`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x1800e3a12`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x1800e3a3e`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x1800e3a7c`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x1800e3ab1`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x1800e3ad4`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x1800e3861`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x1800e3892`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x1800e38bc`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x1800e38ed`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x1800e3917`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x1800e3973`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x1800e399f`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x1800e39dd`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x1800e3a12`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x1800e3a3e`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x1800e3a7c`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x1800e3ab1`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x1800e3ad4`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x1800e1417`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x1800e1417`
- `onetutil!??0VHRESULT@@QEAA@J@Z` at `0x1800e1170`
- `onetutil!??0VHRESULT@@QEAA@J@Z` at `0x1800e1170`

## string_xrefs

- `0x1800e158f`: `vti_cachedhaspersonalviewmetatag`
- `0x1800e1122`: `VdocumentStore::updateDocument`
- `0x1800e1317`: `VdocumentStore::updateDocument failed because bUrlIsAttachment is true, but pList is NULL.`
- `0x1800e155f`: `VdocumentStore::updateDocument failed calling validateUrlForStore. (0x%08X)`
- `0x1800e192b`: `VdocumentStore::updateDocument failed calling PrepareUpdateQuery. (0x%08X)`
- `0x1800e1b84`: `VdocumentStore::updateDocument failed calling writeBlob. (0x%08X)`
- `0x1800e1ead`: `proc_UpdateDocument2`
- `0x1800e1eb6`: `proc_UpdateDocument`
- `0x1800e2bf9`: `VdocumentStore::updateDocument failed calling transferBlob. (0x%08X)`
- `0x1800e2d0e`: `VdocumentStore::updateDocument failed calling GetPreparedUpdateQuery. (0x%08X)`
- `0x1800e2d66`: `VdocumentStore::updateDocument failed calling AppendParsedWebParts. (0x%08X)`
- `0x1800e2ec7`: `VdocumentStore::updateDocument failed calling CITPList::get_ListID. (0x%08X)`
- `0x1800e2f2d`: `VdocumentStore::updateDocument failed calling AcquireLock. (0x%08X)`
- `0x1800e2fae`: ` done: IF @iRet = 0 BEGIN  COMMIT;`
- `0x1800e3067`: ` EXEC proc_UpdateDiskUsed @S, 1;`
- `0x1800e3083`: ` EXEC proc_GetLinkInfoSingleDoc @S,@DN,@LN, @Level;`
- `0x1800e323f`: ` END ELSE ROLLBACK;  SET ?=@Level; SET ?=@iRet;`
- `0x1800e3278`: `VdocumentStore::updateDocument`
- `0x1800e32b5`: `VdocumentStore::updateDocument failed calling ExecQuery. (0x%08X)`
- `0x1800e3363`: `VdocumentStore::updateDocument failed calling handleDocQuery(..., qpAuditMask, ...). (0x%08X)`
- `0x1800e33bd`: `VdocumentStore::updateDocument failed calling handleDocQuery(..., dwQueryParts, ...). (0x%08X)`
- `0x1800e341d`: `VdocumentStore::updateDocument failed calling handleDocQuery(..., qpLinks, ...). (0x%08X)`
- `0x1800e3480`: `VdocumentStore::updateDocument failed calling GetOutputParam(iOutparamDtm, ...). (0x%08X)`
- `0x1800e3517`: `VdocumentStore::updateDocument failed calling GetOutputParam(iOutparamUIVersion, ...). (0x%08X)`
- `0x1800e356c`: `VdocumentStore::updateDocument failed calling GetOutputParam(iOutparamDocFlags, ...). (0x%08X)`
- `0x1800e35c1`: `VdocumentStore::updateDocument failed calling GetOutputParam(iDocVersion, ...). (0x%08X)`
- `0x1800e368e`: `VdocumentStore::updateDocument failed calling handleWnsSubscriptionsQueryResult. (0x%08X)`
- `0x1800e36e3`: `VdocumentStore::updateDocument failed calling GetOutputParam(iOutparamDocLevel, ...). (0x%08X)`
- `0x1800e37b9`: `VdocumentStore::updateDocument failed calling reinitProps. (0x%08X)`
- `0x1800e3bb1`: `VdocumentStore::updateDocument failed because createInternalEntryFromDirNameLeafName returned NULL.`
- `0x1800e3c3a`: `VdocumentStore::updateDocument failed calling addAuditEntry. (0x%08X)`
- `0x1800e3c75`: `VdocumentStore::updateDocument failed calling GetBetterHrFromOutParam. (0x%08X)`

## pseudocode

```c
// Hidden C++ exception states: #wind=72
VHRESULT *__fastcall VdocumentStore::updateDocument(
        VdocumentStore *a1,
        VHRESULT *a2,
        VdbServer *a3,
        int a4,
        const wchar_t **a5,
        const wchar_t **a6,
        const wchar_t **a7,
        __int64 a8,
        unsigned __int8 *a9,
        unsigned int a10,
        unsigned int a11,
        unsigned int a12,
        _BYTE *a13,
        char a14,
        int a15,
        char a16,
        char a17,
        char a18,
        struct Vtime *a19,
        struct Vtime *a20,
        _DWORD *a21,
        VdocHandle *a22,
        struct VvirusCheck *a23,
        struct VlinkVvector *a24,
        wchar_t **a25,
        unsigned __int8 *a26,
        unsigned int a27,
        unsigned __int8 *a28,
        unsigned int a29,
        unsigned int a30,
        char *a31,
        char a32,
        char a33,
        Vstring *a34,
        wchar_t *a35,
        wchar_t *a36,
        int a37,
        int a38,
        int a39,
        char a40,
        char a41,
        int a42,
        __int64 a43,
        __int64 a44,
        unsigned int a45,
        struct VvirusCheck **a46,
        char *a47,
        char a48,
        unsigned int a49,
        char a50,
        char a51)
{
  const char *v53; // rax
  unsigned __int64 v54; // rax
  unsigned int v55; // r13d
  unsigned __int64 v56; // rax
  struct VdoclibManager *DoclibManager; // rax
  __int64 v58; // r9
  unsigned __int64 v59; // r12
  const wchar_t **v60; // rsi
  VdbSubweb *v61; // r13
  char *v62; // rcx
  unsigned int v63; // edi
  VHRESULT *v64; // rax
  __int64 v65; // rax
  void *v66; // rdi
  __int64 v67; // rax
  VdbServer *v68; // rsi
  bool v69; // al
  char *v70; // rdx
  __int64 v71; // rax
  _DWORD *v72; // rsi
  int v73; // ecx
  char v74; // al
  char v75; // al
  char v76; // al
  char v77; // al
  char *v78; // rcx
  char v79; // al
  char v80; // al
  char v81; // al
  int v82; // eax
  struct VdoclibManager *v83; // rax
  __int64 updated; // rax
  __int64 v85; // r8
  int v86; // eax
  const wchar_t *v87; // r9
  __int64 v88; // rcx
  VmetaDict *v89; // rcx
  __int64 v90; // rax
  __int64 v91; // rdx
  const struct VrequestIdentity *v92; // rdx
  char v93; // al
  const wchar_t *v94; // rdx
  unsigned __int16 v95; // r9
  unsigned int v96; // r8d
  unsigned __int8 **v97; // rdx
  VdbSubweb *v98; // rsi
  __int64 v99; // rcx
  __int64 v100; // rax
  __int64 v101; // rax
  bool v102; // cf
  const char *v103; // rax
  __int64 v104; // r13
  const wchar_t *v105; // rdx
  const wchar_t *v106; // rdx
  unsigned int v107; // r13d
  char v108; // si
  const struct _GUID *v109; // rdx
  __int64 v110; // rax
  int v111; // eax
  const wchar_t *v112; // r9
  __int64 v113; // rcx
  struct VdoclibManager *v114; // rax
  __int64 PreparedUpdateQuery; // rax
  __int64 v116; // rax
  __int64 v117; // rcx
  __int64 v118; // rax
  __int64 v119; // rax
  unsigned int v120; // eax
  __int64 v121; // rax
  __int64 v122; // rcx
  __int64 v123; // rax
  __int64 v124; // rax
  __int64 v125; // rax
  __int64 v126; // rax
  int v127; // ecx
  unsigned int v128; // r12d
  __int64 v129; // rcx
  __int64 v130; // rax
  __int64 v131; // rdx
  __int64 v132; // rcx
  __int64 v133; // rax
  __int64 v134; // rax
  __int64 v135; // rax
  __int64 v136; // rax
  unsigned int v137; // esi
  __int64 v138; // rax
  VHRESULT *v139; // rax
  __int64 v140; // rax
  __int64 v141; // rax
  __int64 v142; // rax
  __int64 v143; // rax
  __int64 OutputParam; // rax
  struct Vtime *v145; // rcx
  __int64 v146; // rax
  __int64 v147; // rax
  _DWORD *v148; // r13
  __int64 v149; // rax
  __int64 v150; // rax
  __int64 v151; // rax
  char v152; // si
  __int64 v153; // rax
  int v154; // ecx
  unsigned __int64 v155; // rax
  int v156; // esi
  _DWORD *v157; // rdi
  unsigned int v158; // eax
  const wchar_t *v159; // rdi
  unsigned int v160; // eax
  unsigned int v161; // eax
  const wchar_t *v162; // rdi
  unsigned int v163; // eax
  unsigned int v164; // eax
  unsigned int v165; // eax
  unsigned int v166; // eax
  const struct Vstring *v167; // rax
  const wchar_t *v168; // rdi
  unsigned int v169; // eax
  unsigned int v170; // eax
  unsigned int v171; // eax
  const struct Vstring *v172; // rax
  const wchar_t *v173; // rdi
  unsigned int v174; // eax
  unsigned int v175; // eax
  unsigned int v176; // eax
  int AppPrincipalId; // edx
  char v178; // r10
  __int64 v179; // rax
  __int64 v180; // rax
  __int64 v181; // rax
  VHRESULT *v182; // rax
  VHRESULT *v183; // rax
  _QWORD *v184; // rdi
  VHRESULT *v185; // rax
  __int64 v186; // rax
  __int64 v187; // r8
  int v188; // esi
  Vstring *v189; // rax
  const wchar_t *v190; // rax
  const wchar_t *v191; // rdx
  VHRESULT *v192; // rdx
  VHRESULT *v193; // rax
  wchar_t **v195; // [rsp+28h] [rbp-120h]
  wchar_t **v196; // [rsp+28h] [rbp-120h]
  wchar_t **v197; // [rsp+28h] [rbp-120h]
  wchar_t **v198; // [rsp+28h] [rbp-120h]
  int psza; // [rsp+30h] [rbp-118h]
  int psz; // [rsp+30h] [rbp-118h]
  int v201; // [rsp+38h] [rbp-110h]
  int v202; // [rsp+50h] [rbp-F8h]
  int v203; // [rsp+60h] [rbp-E8h]
  char v204[8]; // [rsp+C8h] [rbp-80h] BYREF
  char v205[8]; // [rsp+D0h] [rbp-78h] BYREF
  char v206[8]; // [rsp+D8h] [rbp-70h] BYREF
  unsigned int v207; // [rsp+E0h] [rbp-68h] BYREF
  char v208; // [rsp+E8h] [rbp-60h]
  char v209; // [rsp+E9h] [rbp-5Fh] BYREF
  char v210; // [rsp+EAh] [rbp-5Eh]
  VdbSubweb *v211; // [rsp+F0h] [rbp-58h]
  const wchar_t **v212; // [rsp+F8h] [rbp-50h]
  char v213; // [rsp+100h] [rbp-48h] BYREF
  bool v214; // [rsp+101h] [rbp-47h]
  char v215; // [rsp+102h] [rbp-46h]
  int v216; // [rsp+104h] [rbp-44h] BYREF
  unsigned __int64 v217; // [rsp+108h] [rbp-40h]
  int v218[2]; // [rsp+110h] [rbp-38h] BYREF
  int v219; // [rsp+120h] [rbp-28h] BYREF
  __int64 v220; // [rsp+128h] [rbp-20h] BYREF
  struct VlinkVvector *InternalEntryFromDirNameLeafName; // [rsp+130h] [rbp-18h] BYREF
  char v222; // [rsp+138h] [rbp-10h]
  char v223[4]; // [rsp+140h] [rbp-8h] BYREF
  unsigned int v224; // [rsp+144h] [rbp-4h]
  unsigned int v225; // [rsp+148h] [rbp+0h]
  _QWORD v226[2]; // [rsp+150h] [rbp+8h] BYREF
  __int64 v227; // [rsp+160h] [rbp+18h] BYREF
  _BYTE *v228; // [rsp+168h] [rbp+20h] BYREF
  wchar_t *v229; // [rsp+170h] [rbp+28h] BYREF
  VdocumentStore *v230; // [rsp+178h] [rbp+30h] BYREF
  __int64 v231; // [rsp+180h] [rbp+38h] BYREF
  VdbServer *v232; // [rsp+188h] [rbp+40h]
  unsigned int v233; // [rsp+190h] [rbp+48h] BYREF
  struct _GUID *v234; // [rsp+198h] [rbp+50h] BYREF
  __int64 v235; // [rsp+1A0h] [rbp+58h]
  __int64 v236; // [rsp+1A8h] [rbp+60h] BYREF
  unsigned int v237; // [rsp+1B0h] [rbp+68h] BYREF
  unsigned int v238; // [rsp+1B4h] [rbp+6Ch]
  char v239[8]; // [rsp+1B8h] [rbp+70h] BYREF
  const wchar_t **v240; // [rsp+1C0h] [rbp+78h]
  const wchar_t **v241; // [rsp+1C8h] [rbp+80h]
  _QWORD *v242; // [rsp+1D0h] [rbp+88h] BYREF
  struct VvirusCheck *v243[2]; // [rsp+1D8h] [rbp+90h] BYREF
  struct Vtime *v244; // [rsp+1E8h] [rbp+A0h]
  void *Block; // [rsp+1F0h] [rbp+A8h] BYREF
  char *v246; // [rsp+1F8h] [rbp+B0h]
  int v247; // [rsp+200h] [rbp+B8h] BYREF
  OLECHAR *v248; // [rsp+208h] [rbp+C0h] BYREF
  int v249; // [rsp+210h] [rbp+C8h] BYREF
  unsigned __int8 *v250[2]; // [rsp+218h] [rbp+D0h] BYREF
  unsigned __int64 v251; // [rsp+228h] [rbp+E0h]
  struct Vtime *v252; // [rsp+230h] [rbp+E8h]
  struct VvirusCheck **v253; // [rsp+238h] [rbp+F0h]
  char *v254; // [rsp+240h] [rbp+F8h]
  struct _GUID *v255; // [rsp+248h] [rbp+100h]
  double v256; // [rsp+250h] [rbp+108h] BYREF
  _DWORD *v257; // [rsp+258h] [rbp+110h]
  Vstring *v258; // [rsp+260h] [rbp+118h]
  void **v259; // [rsp+268h] [rbp+120h] BYREF
  VdbServer *v260; // [rsp+270h] [rbp+128h]
  bool v261; // [rsp+278h] [rbp+130h]
  _QWORD v262[4]; // [rsp+288h] [rbp+140h] BYREF
  char *v263; // [rsp+2A8h] [rbp+160h]
  const wchar_t *v264; // [rsp+2B0h] [rbp+168h]
  __int64 v265; // [rsp+2B8h] [rbp+170h]
  const wchar_t *v266; // [rsp+2C0h] [rbp+178h]
  char v267; // [rsp+2D8h] [rbp+190h]
  bool v268; // [rsp+2D9h] [rbp+191h]
  __int16 v269; // [rsp+2E0h] [rbp+198h]
  bool v270; // [rsp+2E2h] [rbp+19Ah]
  char v271; // [rsp+2E3h] [rbp+19Bh]
  _BYTE *v272; // [rsp+2E8h] [rbp+1A0h]
  const wchar_t *v273; // [rsp+2F0h] [rbp+1A8h]
  int v274; // [rsp+2F8h] [rbp+1B0h]
  int v275; // [rsp+2FCh] [rbp+1B4h]
  const wchar_t *v276; // [rsp+300h] [rbp+1B8h]
  char v277; // [rsp+308h] [rbp+1C0h]
  char *v278; // [rsp+310h] [rbp+1C8h]
  bool v279; // [rsp+318h] [rbp+1D0h]
  bool v280; // [rsp+319h] [rbp+1D1h]
  bool v281; // [rsp+31Ah] [rbp+1D2h]
  char v282; // [rsp+31Bh] [rbp+1D3h]
  char v283; // [rsp+31Ch] [rbp+1D4h]
  char v284; // [rsp+31Dh] [rbp+1D5h]
  char v285; // [rsp+31Eh] [rbp+1D6h]
  char v286; // [rsp+31Fh] [rbp+1D7h]
  char v287; // [rsp+320h] [rbp+1D8h]
  char v288; // [rsp+321h] [rbp+1D9h]
  char v289; // [rsp+322h] [rbp+1DAh]
  bool v290; // [rsp+323h] [rbp+1DBh]
  char v291; // [rsp+325h] [rbp+1DDh]
  char v292; // [rsp+326h] [rbp+1DEh]
  int v293; // [rsp+328h] [rbp+1E0h]
  wchar_t *v294; // [rsp+338h] [rbp+1F0h]
  unsigned __int8 *v295; // [rsp+340h] [rbp+1F8h]
  wchar_t **v296; // [rsp+348h] [rbp+200h]
  unsigned __int64 v297; // [rsp+350h] [rbp+208h] BYREF
  _BYTE v298[16]; // [rsp+358h] [rbp+210h] BYREF
  _BYTE v299[40]; // [rsp+368h] [rbp+220h] BYREF
  _BYTE v300[40]; // [rsp+390h] [rbp+248h] BYREF
  __int64 v301; // [rsp+3B8h] [rbp+270h]
  VHRESULT *v302; // [rsp+3C0h] [rbp+278h]
  Vstring *v303; // [rsp+3C8h] [rbp+280h]
  _BYTE v304[32]; // [rsp+3D0h] [rbp+288h] BYREF
  struct _GUID v305; // [rsp+3F0h] [rbp+2A8h] BYREF
  __int128 v306; // [rsp+400h] [rbp+2B8h] BYREF
  _BYTE v307[16]; // [rsp+418h] [rbp+2D0h] BYREF
  VsqlClient *v308; // [rsp+428h] [rbp+2E0h]
  int v309[20]; // [rsp+868h] [rbp+720h] BYREF
  char *v310; // [rsp+8B8h] [rbp+770h] BYREF
  char v311; // [rsp+8C0h] [rbp+778h] BYREF
  int v312; // [rsp+CC4h] [rbp+B7Ch]
  int v313; // [rsp+CC8h] [rbp+B80h]

  v301 = -2;
  v232 = a3;
  v230 = a1;
  v302 = a2;
  v240 = a5;
  v241 = a6;
  v212 = a7;
  v227 = a8;
  v250[0] = a9;
  v228 = a13;
  v244 = a19;
  v252 = a20;
  v257 = a21;
  v243[0] = a23;
  InternalEntryFromDirNameLeafName = a24;
  v296 = a25;
  v295 = a26;
  v217 = (unsigned __int64)a28;
  v246 = a31;
  v258 = a34;
  v303 = a34;
  v294 = a36;
  v231 = a43;
  v226[0] = a44;
  v238 = a45;
  v253 = a46;
  v254 = a47;
  v225 = 0;
  VmonitoredScope::VmonitoredScope(
    (VmonitoredScope *)v298,
    0x215798u,
    0x6FB7043u,
    0x32u,
    L"VdocumentStore::updateDocument");
  v235 = -1;
  v236 = -1;
  v211 = (VdbSubweb *)*((_QWORD *)a22 + 18);
  v206[0] = *((_BYTE *)a22 + 3260);
  VHRESULT::VHRESULT(a2, 0);
  v225 = 1;
  v214 = *((_QWORD *)v211 + 57) == 0;
  LOBYTE(v216) = 0;
  LOBYTE(v219) = 0;
  v204[0] = a27 != 0;
  v224 = 0;
  v220 = 0;
  v208 = 0;
  Voledb::Voledb((Voledb *)v307, v230, 1);
  VdoclibUpdateParams::VdoclibUpdateParams((VdoclibUpdateParams *)v262);
  v242 = 0;
  VdoclibActivitiesParams::VdoclibActivitiesParams((VdoclibActivitiesParams *)v300);
  VwstringVvector::VwstringVvector(v304);
  sub_1800F7DE0(v309, v230);
  CWebLocker::CWebLocker((CWebLocker *)v299, v211);
  v255 = 0;
  v53 = Vstring::data((VdocHandle *)((char *)a22 + 152));
  Vwstring::Vwstring((Vwstring *)&v248, v53);
  Block = 0;
  v233 = -1;
  v210 = 0;
  v259 = &VWnsSubscriptionProcessor::`vftable';
  v260 = v232;
  v261 = 0;
  v215 = 0;
  v209 = 0;
  v54 = (unsigned __int64)a28 >> 20;
  LOBYTE(v54) = ((unsigned __int64)a28 & 0x100000) != 0;
  v251 = v54;
  v55 = *((_DWORD *)a22 + 94);
  v229 = (wchar_t *)*((_QWORD *)a22 + 46);
  if ( !v229 || v227 && *(_QWORD *)(v227 + 24) && !*((_BYTE *)a22 + 380) )
  {
    v229 = 0;
    v55 = 0;
  }
  if ( a18 )
  {
    v56 = Vtime::secondsI64(v252);
    OWSOleDateFromTimeT(v56, &v256);
  }
  DoclibManager = VdbSubweb::getDoclibManager(v211);
  LOBYTE(v58) = a16;
  VdoclibManager::GetContainingList(DoclibManager, v218, (char *)a22 + 152, v58, &v220);
  VHRESULT::~VHRESULT((VHRESULT *)v218);
  if ( a32 )
  {
    if ( !v220 )
    {
      ULSSendTraceTag(
        20018583,
        117141511,
        50,
        L"VdocumentStore::updateDocument failed because bUrlIsAttachment is true, but pList is NULL.");
      VHRESULT::operator=(a2, 2147500037LL);
LABEL_11:
      v59 = v217;
LABEL_12:
      v60 = v212;
LABEL_13:
      v61 = v211;
      goto LABEL_14;
    }
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v220 + 480LL))(v220) )
    {
      v67 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v220 + 488LL))(v220);
      v208 = *(_DWORD *)VsecurableObject::assertPermissionMask(v67, v218, 2048, 50) >= 0;
      VHRESULT::~VHRESULT((VHRESULT *)v218);
    }
  }
  if ( v220 && ((unsigned __int8)VdoclibManager::IsDoclibItem((char *)a22 + 152, v220, 0, 2) || (*v228 & 2) != 0) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v220 + 568LL))(v220);
    v216 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v220 + 480LL))(v220);
    v219 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v220 + 584LL))(v220);
  }
  v68 = v232;
  v69 = (v217 & 0x40000000000LL) != 0 || VdbServer::allowPoundPercentInPath(v232);
  v70 = (char *)v68 + 200;
  v60 = v212;
  v71 = VdocumentStore::validateUrlForStore(v218, v70, v240, v241, v212, v69, 0, 3);
  VHRESULT::operator=(a2, v71);
  VHRESULT::~VHRESULT((VHRESULT *)v218);
  if ( *(int *)a2 < 0 )
  {
    LODWORD(v196) = *(_DWORD *)a2;
    ULSSendTraceTag(
      20018584,
      117141511,
      50,
      L"VdocumentStore::updateDocument failed calling validateUrlForStore. (0x%08X)",
      v196);
    v59 = v217;
    goto LABEL_13;
  }
  v213 = 0;
  VmetaDict::getBool((VdocHandle *)((char *)a22 + 168), "vti_cachedhaspersonalviewmetatag", &v213, 0);
  v72 = v228;
  if ( v213 )
    *(_DWORD *)v228 |= 0x80u;
  else
    *(_DWORD *)v228 &= ~0x80u;
  if ( VmetaDict::getInt((VdocHandle *)((char *)a22 + 168), "vti_irm_IrmEnabled", &v247, 0) )
  {
    if ( v247 )
      *v72 |= 0x400000u;
    else
      *v72 &= ~0x400000u;
  }
  if ( VmetaDict::getInt((VdocHandle *)((char *)a22 + 168), "vti_irm_dlp_IrmEnabled", &v249, 0) )
  {
    if ( v249 )
      *v72 |= 0x800000u;
    else
      *v72 &= ~0x800000u;
  }
  if ( !v220 || (v217 & 0x8000) != 0 )
  {
    v59 = v217;
    goto LABEL_94;
  }
  v262[0] = (char *)a22 + 152;
  v262[1] = *v240;
  v262[2] = *v241;
  v263 = (char *)a22 + 168;
  v264 = L"@DoclibRowId";
  v265 = 0;
  v266 = L"@iRet";
  v267 = 0;
  v268 = (*((_DWORD *)a22 + 770) & 0x40) != 0;
  v269 = 1;
  v73 = *((_DWORD *)a22 + 772);
  v279 = (v73 & 2) != 0;
  v280 = (v73 & 4) != 0;
  v281 = (v73 & 8) != 0;
  if ( a17 || (Vtime::Vtime((Vtime *)v218, 0), v74 = 0, *(_QWORD *)v244 > *(_QWORD *)v218) )
    v74 = 1;
  v292 = v74;
  v291 = a18;
  v59 = v217;
  if ( (v217 & 0x2000) != 0 )
  {
    v75 = HIBYTE(v269);
    if ( !a38 )
      v75 = 1;
    HIBYTE(v269) = v75;
  }
  v270 = (v217 & 0x800000) != 0;
  v271 = v251;
  v272 = v307;
  v274 = a37;
  v275 = a38;
  v277 = v206[0];
  v276 = L"@Level";
  v286 = 0;
  v278 = v246;
  v289 = *((_BYTE *)a22 + 3329);
  v290 = (v217 & 0x20000) != 0;
  v273 = L"@ActivitiesEditChangeVersionFlag";
  if ( v206[0] != -1 )
  {
    v79 = v283;
    if ( (v217 & 0x200000) != 0 )
      v79 = 1;
    v283 = v79;
    v80 = v285;
    if ( (v217 & 0x10000000) != 0 )
      v80 = 1;
    v285 = v80;
    goto LABEL_74;
  }
  if ( (v217 & 0x20) != 0 )
  {
    v76 = v283;
    if ( (v217 & 0x200000) != 0 )
      v76 = 1;
    v283 = v76;
    v77 = v285;
    if ( (v217 & 0x10000000) != 0 )
      v77 = 1;
    v285 = v77;
    if ( (v217 & 0x1000000) == 0 )
    {
      v287 = 1;
      if ( (v217 & 0x10000) != 0 )
      {
        v78 = (char *)a22 + 168;
        if ( (_BYTE)v216 )
        {
          VmetaDict::setInt(v78, "vti_doclibmodstat", 2, 1, 0);
          goto LABEL_74;
        }
        VmetaDict::setInt(v78, "vti_doclibmodstat", 0, 1, 0);
      }
      else if ( (_BYTE)v216 || (_BYTE)v219 )
      {
        goto LABEL_74;
      }
      v288 = 1;
    }
  }
LABEL_74:
  v81 = v283;
  if ( *((_BYTE *)a22 + 3084) )
    v81 = 1;
  v283 = v81;
  v262[3] = (char *)a22 + 168;
  if ( (*((_DWORD *)a22 + 770) & 8) == 0 || (v82 = 0, *((_DWORD *)a22 + 828)) )
    v82 = 1;
  v293 = v82;
  v83 = VdbSubweb::getDoclibManager(v211);
  updated = VdoclibManager::PrepareUpdateQuery(v83, v218, v262, v59, 0);
  VHRESULT::operator=(a2, updated);
  VHRESULT::~VHRESULT((VHRESULT *)v218);
  v86 = *(_DWORD *)a2;
  if ( *(int *)a2 < 0 )
  {
    v87 = L"VdocumentStore::updateDocument failed calling PrepareUpdateQuery. (0x%08X)";
    v88 = 20018585;
LABEL_81:
    LODWORD(v195) = v86;
    ULSSendTraceTag(v88, 117141511, 50, v87, v195);
    goto LABEL_12;
  }
  if ( (v59 & 0x200000) != 0 && v282 || v285 && v284 )
  {
    if ( (v59 & 0x1000000) != 0 )
    {
      v59 &= ~0x20uLL;
      v217 = v59;
    }
    else
    {
      v210 = 1;
    }
  }
  if ( v283 && v282 )
  {
    LOBYTE(v85) = 1;
    VmetaDict::setBool((char *)a22 + 168, "vti_ignoredreqprops", v85, 1, 0);
  }
  v242 = v262;
LABEL_94:
  v89 = (VdocHandle *)((char *)a22 + 168);
  if ( (*((_DWORD *)a22 + 770) & 0x40) != 0 )
  {
    v234 = 0;
    VmetaDict::getString(v89, "vti_contenttypeorder", (const char **)&v234, 0);
    if ( v234 && LOBYTE(v234->Data1) )
    {
      *(_DWORD *)v228 |= 0x2000u;
    }
    else
    {
      (*(void (__fastcall **)(__int64, const char *))(*((_QWORD *)a22 + 21) + 56LL))(
        (__int64)a22 + 168,
        "vti_contenttypeorder");
      *(_DWORD *)v228 &= ~0x2000u;
    }
  }
  else if ( (*(unsigned __int8 (__fastcall **)(VmetaDict *, const char *))(*(_QWORD *)v89 + 40LL))(
              v89,
              "vti_contenttypeorder") )
  {
    (*(void (__fastcall **)(__int64, const char *))(*((_QWORD *)a22 + 21) + 56LL))(
      (__int64)a22 + 168,
      "vti_contenttypeorder");
  }
  v90 = sub_180028A08(
          v309,
          v218,
          v307,
          *(_QWORD *)(*((_QWORD *)a22 + 18) + 56LL) + 184LL,
          (char *)a22 + 3144,
          (char *)a22 + 3128,
          v248,
          v59,
          v206[0],
          1,
          *((_DWORD *)a22 + 794),
          *((_QWORD *)a22 + 398),
          *((_QWORD *)a22 + 399),
          *((_BYTE *)a22 + 3200),
          v227,
          a4,
          v253,
          v254,
          &v236,
          &Block,
          &v233,
          &v209,
          v232);
  VHRESULT::operator=(a2, v90);
  VHRESULT::~VHRESULT((VHRESULT *)v218);
  v86 = *(_DWORD *)a2;
  if ( *(int *)a2 < 0 )
  {
    v87 = L"VdocumentStore::updateDocument failed calling writeBlob. (0x%08X)";
    v88 = 20018586;
    goto LABEL_81;
  }
  Voledb::AppendQuery(
    (Voledb *)v307,
    L"DECLARE @S uniqueidentifier; DECLARE @W uniqueidentifier; DECLARE @DocId uniqueidentifier; DECLARE @DoclibRowId int;"
     " DECLARE @Level tinyint; DECLARE @DocUIVersion int;DECLARE @ActivitiesChangeVersionFlag int = 0;DECLARE @Activities"
     "EditChangeVersionFlag int = 0;DECLARE @IsCurrentVersion bit; DECLARE @DN nvarchar(400); DECLARE @LN nvarchar(400); "
     "DECLARE @FU nvarchar(400); SET @DN=?");
  Voledb::BindInputParam((Voledb *)v307, *v240);
  Voledb::AppendQuery((Voledb *)v307, L";SET @iRet=0; ");
  Voledb::AppendQuery((Voledb *)v307, L";SET @LN=?");
  Voledb::BindInputParam((Voledb *)v307, *v241);
  Voledb::AppendQuery((Voledb *)v307, L";SET @FU=?");
  Voledb::BindInputParam((Voledb *)v307, *v212);
  Voledb::AppendQuery((Voledb *)v307, L";SET @S=?");
  v234 = (struct _GUID *)((char *)v232 + 184);
  Voledb::BindInputParam((Voledb *)v307, (char *)v232 + 184, 0x10u, 0x48u, 1);
  Voledb::AppendQuery((Voledb *)v307, L";SET @W=?");
  *(_QWORD *)v218 = (char *)v211 + 264;
  Voledb::BindInputParam((Voledb *)v307, (char *)v211 + 264, 0x10u, 0x48u, 1);
  Voledb::AppendQuery((Voledb *)v307, L";SET @DocUIVersion = 512;");
  v223[0] = v206[0];
  if ( v210 )
  {
    Voledb::AppendQuery(
      (Voledb *)v307,
      L" DECLARE @Now datetime;  SELECT @Now = dbo.fn_RoundDateToNearestSecond(GETUTCDATE());  EXEC @iRet = proc_CheckoutD"
       "ocumentInternal @S, @W, @DN, @LN, ?, ?, ?, ?, NULL, 0, 0, 0, 0, 0, @Now,  NULL, NULL, NULL");
    Voledb::BindInputParam((Voledb *)v307, v223, 1u, 0x11u, 0);
    v205[0] = v219;
    Voledb::BindInputParam((Voledb *)v307, v205, 1u, 0xBu, 1);
    v205[0] = v216;
    Voledb::BindInputParam((Voledb *)v307, v205, 1u, 0xBu, 1);
    v91 = *((_QWORD *)v211 + 8);
    if ( v91 )
      v92 = *(const struct VrequestIdentity **)(v91 + 88);
    else
      v92 = 0;
    Voledb::BindInputParam((Voledb *)v307, v92);
    if ( VdbServer::sprocsSchemaVersionGreaterThanOrEqualTo(*(VdbServer **)(*((_QWORD *)a22 + 18) + 56LL), 16, 0, 67, 0) )
    {
      Voledb::AppendQuery((Voledb *)v307, L", ? OUTPUT, ?");
      Voledb::BindRequestGuid((Voledb *)v307);
      v205[0] = a48;
      Voledb::BindInputParam((Voledb *)v307, v205, 1u, 0xBu, 1);
    }
    Voledb::AppendQuery((Voledb *)v307, L";");
    v206[0] = -1;
  }
  Voledb::AppendQuery((Voledb *)v307, L"IF @iRet <> 0 GOTO done; ");
  Voledb::AppendQuery((Voledb *)v307, L";SET @Level =?;");
  v205[0] = v206[0];
  Voledb::BindInputParam((Voledb *)v307, v205, 1u, 0x11u, 1);
  if ( a42 > 0 )
  {
    Voledb::AppendQuery((Voledb *)v307, L" EXEC @iRet= proc_RestoreWebPartForDoc @S,@DN,@LN, @Level , ?;");
    v207 = a42;
    Voledb::BindInputParam((Voledb *)v307, &v207, 4u, 3u, 1);
    Voledb::AppendQuery((Voledb *)v307, L" IF @iRet <> 0 GOTO done; ");
  }
  Voledb::AppendQuery((Voledb *)v307, L" EXEC @iRet = ");
  v93 = VdbServer::databaseSupports64BitDocSizes(v232);
  v94 = L"proc_UpdateDocument2";
  if ( !v93 )
    v94 = L"proc_UpdateDocument";
  Voledb::AppendQuery((Voledb *)v307, v94);
  Voledb::AppendQuery((Voledb *)v307, L" @S, @W, @DN, @LN");
  Voledb::AppendQuery((Voledb *)v307, L", ?, ?, ?, ?");
  if ( v227 )
    v205[0] = *(_QWORD *)(v227 + 24) != 0;
  else
    v205[0] = 0;
  Voledb::BindInputParam((Voledb *)v307, v205, 1u, 0xBu, 1);
  v237 = a10;
  Voledb::BindCompressedInputBytesParam((Voledb *)v307, v250[0], a10, &v237);
  if ( VdbServer::databaseSupports64BitDocSizes(v232) )
  {
    v250[0] = (unsigned __int8 *)(v236 & -(__int64)(v227 != 0));
    v95 = 20;
    v96 = 8;
    v97 = v250;
  }
  else
  {
    v207 = v227 != 0 ? v236 : 0;
    v95 = 3;
    v96 = 4;
    v97 = (unsigned __int8 **)&v207;
  }
  Voledb::BindInputParam((Voledb *)v307, v97, v96, v95, 1);
  v207 = v237;
  Voledb::BindInputParam((Voledb *)v307, &v207, 4u, 0x13u, 1);
  Voledb::AppendQuery((Voledb *)v307, L", ?, ?");
  if ( v229 && v55 )
  {
    Voledb::BindInputParam((Voledb *)v307, v229, v55, 0x80u, 0);
    v207 = v55;
    Voledb::BindInputParam((Voledb *)v307, &v207, 4u, 0x13u, 1);
    if ( v55 > 0xFB40 )
    {
      LODWORD(v197) = v55;
      ULSSendTraceTag(1681419115, 117141571, 50, L"Saving FFM with size %i for file %s.", v197, *v212);
    }
  }
  else
  {
    VsqlClient::PlaceholderBindInputNULL(v308, 0x80u, 0);
    v207 = 0;
    Voledb::BindInputParam((Voledb *)v307, &v207, 4u, 0x13u, 1);
  }
  Voledb::AppendQuery((Voledb *)v307, L", ?, ?, ?, ?");
  Voledb::BindInputParam((Voledb *)v307, v204, 1u, 0xBu, 1);
  v207 = a11;
  Voledb::BindInputParam((Voledb *)v307, &v207, 4u, 0x13u, 1);
  v207 = a12;
  Voledb::BindInputParam((Voledb *)v307, &v207, 4u, 0x13u, 1);
  v207 = *(_DWORD *)v228;
  Voledb::BindInputParam((Voledb *)v307, &v207, 4u, 0x13u, 1);
  Voledb::AppendQuery((Voledb *)v307, L", ?, ?");
  if ( a17 && (Vtime::Vtime((Vtime *)v250, 0), (unsigned __int8 *)*(_QWORD *)v244 > v250[0]) )
    Voledb::BindInputParam((Voledb *)v307, v244);
  else
    VsqlClient::PlaceholderBindInputNULL(v308, 7u, 0);
  if ( a18 )
    Voledb::BindInputParam((Voledb *)v307, v252);
  else
    VsqlClient::PlaceholderBindInputNULL(v308, 7u, 0);
  Voledb::AppendQuery((Voledb *)v307, L", ?, ?, ?, ?, ?, ?, ?, ?, ?");
  if ( a15 == 2 )
  {
    VsqlClient::PlaceholderBindInputNULL(v308, 0xBu, 0);
  }
  else
  {
    v204[0] = a15 == 0;
    Voledb::BindInputParam((Voledb *)v307, v204, 1u, 0xBu, 1);
  }
  v204[0] = v214;
  Voledb::BindInputParam((Voledb *)v307, v204, 1u, 0xBu, 1);
  v204[0] = a14;
  Voledb::BindInputParam((Voledb *)v307, v204, 1u, 0xBu, 1);
  v204[0] = v219;
  Voledb::BindInputParam((Voledb *)v307, v204, 1u, 0xBu, 1);
  v98 = v211;
  v99 = *((_QWORD *)v211 + 8);
  if ( v99 )
    v100 = *(_QWORD *)(v99 + 88);
  else
    v100 = 0;
  if ( *(_QWORD *)(*(_QWORD *)(v100 + 48) + 48LL) )
  {
    if ( v99 )
      v101 = *(_QWORD *)(v99 + 88);
    else
      v101 = 0;
    v207 = **(_DWORD **)(v101 + 48);
    Voledb::BindInputParam((Voledb *)v307, &v207, 4u, 3u, 1);
  }
  else
  {
    VsqlClient::PlaceholderBindInputNULL(v308, 3u, 0);
  }
  v102 = v208 != 0;
  v208 = -v208;
  v207 = a32 != 0 ? 3 - v102 : 0;
  Voledb::BindInputParam((Voledb *)v307, &v207, 4u, 3u, 1);
  v250[0] = (unsigned __int8 *)v59;
  Voledb::BindInputParam((Voledb *)v307, v250, 8u, 0x14u, 1);
  v207 = a29;
  Voledb::BindInputParam((Voledb *)v307, &v207, 4u, 0x13u, 1);
  v207 = a30;
  Voledb::BindInputParam((Voledb *)v307, &v207, 4u, 3u, 1);
  Voledb::AppendQuery((Voledb *)v307, L", ?, ?, ?, ?");
  if ( v246 && *v246 )
    Voledb::BindInputParam((Voledb *)v307, v246);
  else
    VsqlClient::PlaceholderBindInputNULL(v308, 0x82u, 0);
  v204[0] = 1;
  Voledb::BindInputParam((Voledb *)v307, v204, 1u, 0xBu, 1);
  v204[0] = a33;
  Voledb::BindInputParam((Voledb *)v307, v204, 1u, 0xBu, 1);
  if ( *(_DWORD *)(*(_QWORD *)v258 - 4LL) )
  {
    v103 = Vstring::data(v258);
    Voledb::BindInputParam((Voledb *)v307, v103);
  }
  else
  {
    VsqlClient::PlaceholderBindInputNULL(v308, 0x82u, 0);
  }
  Voledb::AppendQuery((Voledb *)v307, L", ?, ?, ?, ?");
  v204[0] = v216;
  Voledb::BindInputParam((Voledb *)v307, v204, 1u, 0xBu, 1);
  v204[0] = 0;
  Voledb::BindInputParam((Voledb *)v307, v204, 1u, 0xBu, 1);
  if ( a35 && *a35 )
    Voledb::BindInputParam((Voledb *)v307, a35);
  else
    VsqlClient::PlaceholderBindInputNULL(v308, 0x82u, 0);
  if ( v294 && *v294 )
    Voledb::BindInputParam((Voledb *)v307, v294);
  else
    VsqlClient::PlaceholderBindInputNULL(v308, 0x82u, 0);
  Voledb::AppendQuery((Voledb *)v307, L", ?, ?, ?, ?");
  VvirusCheck::appendQueryParameters(v243[0], (struct Voledb *)v307, 1, 1, 1);
  Voledb::AppendQuery((Voledb *)v307, L", ?, ?, ?, ?, ?, ?");
  if ( a39 >= 0 )
  {
    v207 = a39;
    Voledb::BindInputParam((Voledb *)v307, &v207, 4u, 3u, 1);
    v204[0] = a40;
    Voledb::BindInputParam((Voledb *)v307, v204, 1u, 0xBu, 1);
    v204[0] = a41;
    Voledb::BindInputParam((Voledb *)v307, v204, 1u, 0xBu, 1);
    v224 = 0x10000;
  }
  else
  {
    VsqlClient::PlaceholderBindInputNULL(v308, 3u, 0);
    v204[0] = 0;
    Voledb::BindInputParam((Voledb *)v307, v204, 1u, 0xBu, 1);
    v204[0] = 0;
    Voledb::BindInputParam((Voledb *)v307, v204, 1u, 0xBu, 1);
  }
  v104 = v231;
  if ( !v231 || *(_BYTE *)(v231 + 200) == 0xFF )
  {
    VsqlClient::PlaceholderBindInputNULL(v308, 0x10u, 0);
  }
  else
  {
    v204[0] = *(_BYTE *)(v231 + 200);
    Voledb::BindInputParam((Voledb *)v307, v204, 1u, 0x11u, 1);
  }
  if ( !v104 || *(_QWORD *)(v104 + 192) == -1 )
  {
    VsqlClient::PlaceholderBindInputNULL(v308, 0x14u, 0);
  }
  else
  {
    v243[0] = *(struct VvirusCheck **)(v104 + 192);
    Voledb::BindInputParam((Voledb *)v307, v243, 8u, 0x14u, 1);
  }
  if ( v104 && (v105 = *(const wchar_t **)(v104 + 184)) != 0 && *v105 )
  {
    Vwstring::Vwstring((Vwstring *)&v229, v105);
    Voledb::BindInputParam((Voledb *)v307, v229);
    Vwstring::~Vwstring(&v229);
  }
  else
  {
    VsqlClient::PlaceholderBindInputNULL(v308, 0x82u, 0);
  }
  Voledb::AppendQuery((Voledb *)v307, L", ?, ?, ?, ?, ?");
  if ( v104 && (v106 = *(const wchar_t **)(v104 + 176)) != 0 )
  {
    Vwstring::Vwstring((Vwstring *)&v229, v106);
    Voledb::BindInputParam((Voledb *)v307, v229);
    Vwstring::~Vwstring(&v229);
  }
  else
  {
    VsqlClient::PlaceholderBindInputNULL(v308, 0x82u, 0);
  }
  v207 = v238;
  Voledb::BindInputParam((Voledb *)v307, &v207, 4u, 0x13u, 1);
  v243[0] = *((struct VvirusCheck **)a22 + 398);
  Voledb::BindInputParam((Voledb *)v307, v243, 8u, 0x14u, 1);
  v243[0] = *v253;
  Voledb::BindInputParam((Voledb *)v307, v243, 8u, 0x14u, 1);
  v204[0] = *v254;
  Voledb::BindInputParam((Voledb *)v307, v204, 1u, 0x11u, 1);
  Voledb::AppendQuery(
    (Voledb *)v307,
    L", @DocId OUTPUT, @Level OUTPUT , @DoclibRowId OUTPUT,? OUTPUT,? OUTPUT,? OUTPUT,? OUTPUT, ? OUTPUT ");
  v107 = VsqlClient::PlaceholderBindOutput(v308, 7u, 8);
  LODWORD(v246) = VsqlClient::PlaceholderBindOutput(v308, 3u, 4);
  LODWORD(v244) = VsqlClient::PlaceholderBindOutput(v308, 3u, 4);
  LODWORD(v229) = VsqlClient::PlaceholderBindOutput(v308, 3u, 4);
  Voledb::BindRequestGuid((Voledb *)v307);
  if ( VdbServer::sprocsSchemaVersionGreaterThanOrEqualTo(*(VdbServer **)(*((_QWORD *)a22 + 18) + 56LL), 16, 0, 11, 0) )
  {
    Voledb::AppendQuery((Voledb *)v307, L", ?");
    if ( v233 == -1 )
      VsqlClient::PlaceholderBindInputNULL(v308, 0x80u, 0);
    else
      Voledb::BindInputParam((Voledb *)v307, Block, v233, 0x80u, 1);
  }
  if ( VdbServer::sprocsSchemaVersionGreaterThanOrEqualTo(*(VdbServer **)(*((_QWORD *)a22 + 18) + 56LL), 16, 0, 67, 0) )
  {
    Voledb::AppendQuery((Voledb *)v307, L", ?");
    v204[0] = a48;
    Voledb::BindInputParam((Voledb *)v307, v204, 1u, 0xBu, 1);
  }
  if ( VdbServer::databaseSupportsOriginatorId(*(VdbServer **)(*((_QWORD *)a22 + 18) + 56LL)) )
  {
    Voledb::AppendQuery((Voledb *)v307, L", ?");
    if ( v209
      || !v227
      || !*(_QWORD *)(v227 + 24)
      || (v108 = 1, v233 == -1)
      && (unsigned __int8)sub_1800DD67C()
      && (VdocHandle::isOneNote(a22) || VdocHandle::isWBX(a22)) )
    {
      v108 = 0;
    }
    if ( !v231 || v108 )
      v109 = &stru_18020E740;
    else
      v109 = (const struct _GUID *)(v231 + 256);
    Voledb::BindInputParam((Voledb *)v307, v109, 0x10u, 0x48u, 1);
    v98 = v211;
  }
  if ( VdbServer::sprocsSchemaVersionGreaterThanOrEqualTo(*(VdbServer **)(*((_QWORD *)a22 + 18) + 56LL), 16, 0, 87, 0) )
  {
    Voledb::AppendQuery((Voledb *)v307, L", ?");
    v207 = a49;
    Voledb::BindInputParam((Voledb *)v307, &v207, 4u, 3u, 1);
  }
  if ( VdbServer::sprocsSchemaVersionGreaterThanOrEqualTo(*(VdbServer **)(*((_QWORD *)a22 + 18) + 56LL), 16, 0, 93, 0) )
  {
    Voledb::AppendQuery((Voledb *)v307, L", ?");
    v204[0] = a50;
    Voledb::BindInputParam((Voledb *)v307, v204, 1u, 0xBu, 1);
  }
  if ( !VdbServer::OutputActivitiesPropertiesKillSwitchActivated()
    && VdbServer::sprocsSchemaVersionGreaterThanOrEqualTo(*(VdbServer **)(*((_QWORD *)a22 + 18) + 56LL), 16, 0, 236, 0) )
  {
    Voledb::AppendQuery((Voledb *)v307, L", @ActivitiesChangeVersionFlag=@ActivitiesChangeVersionFlag OUTPUT ");
  }
  Voledb::AppendQuery((Voledb *)v307, L"; IF @iRet <> 0 GOTO done; ");
  v110 = sub_180029938(
           (int)v309,
           (int)v243,
           (int)L"@S",
           (int)L"@DocId",
           (int)L"@Level",
           *(VdbServer **)(*((_QWORD *)a22 + 18) + 56LL));
  VHRESULT::operator=(a2, v110);
  VHRESULT::~VHRESULT((VHRESULT *)v243);
  v111 = *(_DWORD *)a2;
  if ( *(int *)a2 < 0 )
  {
    v112 = L"VdocumentStore::updateDocument failed calling transferBlob. (0x%08X)";
    v113 = 20018587;
LABEL_208:
    LODWORD(v195) = v111;
    ULSSendTraceTag(v113, 117141511, 50, v112, v195);
    goto LABEL_11;
  }
  if ( (a29 & 1) != 0 )
    VdocumentStore::appendDocUpdateParams(
      v230,
      (struct Voledb *)v307,
      *(struct VdbServer **)(*((_QWORD *)a22 + 18) + 56LL),
      InternalEntryFromDirNameLeafName,
      (const wchar_t **)v296,
      v295,
      a27);
  Voledb::AppendQuery((Voledb *)v307, L" EXEC proc_DirtyDependents @S,1,@FU;");
  if ( v214 )
    v224 |= 1u;
  v59 = v217;
  if ( v220 && (v217 & 0x8000) == 0 )
  {
    v114 = VdbSubweb::getDoclibManager(v98);
    PreparedUpdateQuery = VdoclibManager::GetPreparedUpdateQuery(
                            v114,
                            &InternalEntryFromDirNameLeafName,
                            v262,
                            v59,
                            0,
                            0);
    VHRESULT::operator=(a2, PreparedUpdateQuery);
    VHRESULT::~VHRESULT((VHRESULT *)&InternalEntryFromDirNameLeafName);
    if ( v263 )
    {
      (*(void (__fastcall **)(char *))(*((_QWORD *)v263 + 8) + 16LL))(v263 + 64);
      v263 = 0;
    }
    v86 = *(_DWORD *)a2;
    if ( *(int *)a2 < 0 )
    {
      v87 = L"VdocumentStore::updateDocument failed calling GetPreparedUpdateQuery. (0x%08X)";
      v88 = 20018588;
      goto LABEL_81;
    }
    if ( !v86 )
      v224 |= 0x40u;
  }
  sub_1800C40F4(a22, v307);
  v116 = sub_1800C4188(&InternalEntryFromDirNameLeafName, a22, v307);
  VHRESULT::operator=(a2, v116);
  VHRESULT::~VHRESULT((VHRESULT *)&InternalEntryFromDirNameLeafName);
  v86 = *(_DWORD *)a2;
  if ( *(int *)a2 < 0 )
  {
    v87 = L"VdocumentStore::updateDocument failed calling AppendParsedWebParts. (0x%08X)";
    v88 = 20018589;
    goto LABEL_81;
  }
  sub_1800C407C(a22, v307);
  if ( (v59 & 8) != 0 && (v59 & 0x20) != 0 && v206[0] == -1 )
  {
    Voledb::AppendQuery((Voledb *)v307, L" EXEC @iRet= proc_CloneDoc @S,@DN,@LN, NULL, NULL, NULL, @Level, ?, ?, ?, ?;");
    v204[0] = -1;
    Voledb::BindInputParam((Voledb *)v307, v204, 1u, 0x11u, 1);
    v204[0] = v219;
    Voledb::BindInputParam((Voledb *)v307, v204, 1u, 0xBu, 1);
    v204[0] = v216;
    Voledb::BindInputParam((Voledb *)v307, v204, 1u, 0xBu, 1);
    v117 = *((_QWORD *)v98 + 8);
    if ( v117 )
      v118 = *(_QWORD *)(v117 + 88);
    else
      v118 = 0;
    if ( *(_QWORD *)(*(_QWORD *)(v118 + 48) + 48LL) )
    {
      if ( v117 )
        v119 = *(_QWORD *)(v117 + 88);
      else
        v119 = 0;
      v207 = **(_DWORD **)(v119 + 48);
      Voledb::BindInputParam((Voledb *)v307, &v207, 4u, 3u, 1);
    }
    else
    {
      VsqlClient::PlaceholderBindInputNULL(v308, 3u, 0);
    }
  }
  if ( v220 )
  {
    v120 = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v220 + 160LL))(v220, &v305);
    VHRESULT::operator=(a2, v120);
    v86 = *(_DWORD *)a2;
    if ( *(int *)a2 < 0 )
    {
      v87 = L"VdocumentStore::updateDocument failed calling CITPList::get_ListID. (0x%08X)";
      v88 = 20018590;
      goto LABEL_81;
    }
    v255 = &v305;
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v220 + 720LL))(v220) )
    {
      v121 = CWebLocker::AcquireLock(v299, &InternalEntryFromDirNameLeafName);
      VHRESULT::operator=(a2, v121);
      VHRESULT::~VHRESULT((VHRESULT *)&InternalEntryFromDirNameLeafName);
      v86 = *(_DWORD *)a2;
      if ( *(int *)a2 < 0 )
      {
        v87 = L"VdocumentStore::updateDocument failed calling AcquireLock. (0x%08X)";
        v88 = 20018591;
        goto LABEL_81;
      }
    }
    if ( v299[0] )
    {
      Voledb::AppendQuery((Voledb *)v307, L";IF @iRet = 0 BEGIN ");
      CTranLockManager::AppendTranUnlockWebQuery(
        (struct Voledb *)v307,
        (const struct _GUID *)(*((_QWORD *)v98 + 7) + 184LL),
        (const struct _GUID *)((char *)v98 + 264));
    }
    else
    {
      Voledb::AppendQuery((Voledb *)v307, L";IF @iRet = 0 BEGIN ");
      CTranLockManager::AppendEnsureTranLockNotRequiredQuery((struct Voledb *)v307, v234, &v305, 1);
    }
    Voledb::AppendQuery((Voledb *)v307, L" END;");
  }
  Voledb::AppendQuery((Voledb *)v307, L" done: IF @iRet = 0 BEGIN  COMMIT;");
  v122 = *((_QWORD *)a22 + 18);
  v123 = *(_QWORD *)(v122 + 64);
  if ( v123 )
    v124 = *(_QWORD *)(v123 + 88);
  else
    v124 = 0;
  if ( v124 )
  {
    v125 = *(_QWORD *)(v122 + 64);
    if ( v125 )
      v126 = *(_QWORD *)(v125 + 88);
    else
      v126 = 0;
    v127 = **(_DWORD **)(v126 + 48);
  }
  else
  {
    v127 = -1;
  }
  CTranLockManager::AppendItemUpdateForListQuery((struct Voledb *)v307, v234, v255, v232, (_BYTE)v251 == 0, v127);
  if ( v220
    && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v220 + 600LL))(v220)
    && v227
    && *(_QWORD *)(v227 + 24) )
  {
    Voledb::AppendQuery((Voledb *)v307, L" EXEC proc_IncrementSiteClientTag @S;");
  }
  Voledb::AppendQuery((Voledb *)v307, L" EXEC proc_UpdateDiskUsed @S, 1;");
  v128 = v59 & 0x4000000;
  if ( !v128 )
    Voledb::AppendQuery((Voledb *)v307, L" EXEC proc_GetLinkInfoSingleDoc @S,@DN,@LN, @Level;");
  if ( a42 > 0 && VdbServer::databaseSupportsVersionEvents(*(VdbServer **)(*((_QWORD *)a22 + 18) + 56LL)) )
  {
    Voledb::AppendQuery(
      (Voledb *)v307,
      L" DECLARE @VerEventTime datetime = GETUTCDATE(); EXEC proc_AddDocVersionEvent @S, @DocId, 3, ?, @VerEventTime, NULL, ?;");
    v129 = *(_QWORD *)(*((_QWORD *)a22 + 18) + 64LL);
    if ( v129 )
      v130 = *(_QWORD *)(v129 + 88);
    else
      v130 = 0;
    v207 = **(_DWORD **)(v130 + 48);
    Voledb::BindInputParam((Voledb *)v307, &v207, 4u, 3u, 1);
    Voledb::BindRequestGuid((Voledb *)v307);
  }
  if ( VdbServer::KillActivityStoreFilter() || !(_BYTE)v251 )
  {
    if ( v231 )
      v131 = *(_QWORD *)(v231 + 272);
    else
      v131 = 0;
    v132 = *((_QWORD *)a22 + 18);
    v133 = *(_QWORD *)(v132 + 64);
    if ( v133 )
      v134 = *(_QWORD *)(v133 + 88);
    else
      v134 = 0;
    if ( v134 )
    {
      v135 = *(_QWORD *)(v132 + 64);
      if ( v135 )
        v136 = *(_QWORD *)(v135 + 88);
      else
        v136 = 0;
      v235 = **(unsigned int **)(v136 + 48);
    }
    LOBYTE(v203) = *((_BYTE *)a22 + 3260);
    VdoclibActivitiesParams::BuildActivitiesQuery(
      v300,
      &InternalEntryFromDirNameLeafName,
      v307,
      v220,
      v98,
      L"@DoclibRowId",
      L"@DocId",
      *v212,
      8,
      v235,
      v131,
      v203,
      v217);
    VHRESULT::~VHRESULT((VHRESULT *)&InternalEntryFromDirNameLeafName);
  }
  if ( a51 && v220 && VdbServer::sprocsSchemaVersionGreaterThanOrEqualTo(v260, 16, 0, 97, 0) )
  {
    VWnsSubscriptionProcessor::appendGetWnsSubscriptionsQuery(
      (VWnsSubscriptionProcessor *)&v259,
      (struct Voledb *)v307,
      &v305,
      0);
    v215 = 1;
  }
  Voledb::AppendQuery((Voledb *)v307, L" END ELSE ROLLBACK;  SET ?=@Level; SET ?=@iRet;");
  v137 = VsqlClient::PlaceholderBindOutput(v308, 0x11u, 1);
  LODWORD(v235) = VsqlClient::PlaceholderBindReturnValue(v308);
  v138 = Voledb::ExecQuery(v307, &InternalEntryFromDirNameLeafName, 0, "VdocumentStore::updateDocument");
  VHRESULT::operator=(a2, v138);
  VHRESULT::~VHRESULT((VHRESULT *)&InternalEntryFromDirNameLeafName);
  if ( *(int *)a2 < 0 )
  {
    LODWORD(v198) = *(_DWORD *)a2;
    ULSSendTraceTag(20018592, 117141511, 50, L"VdocumentStore::updateDocument failed calling ExecQuery. (0x%08X)", v198);
    *(_QWORD *)v218 = v226;
    v139 = VHRESULT::VHRESULT((VHRESULT *)v226, a2);
    v140 = VdocHandle::translateSqlError(&InternalEntryFromDirNameLeafName, v139, v307);
    VHRESULT::operator=(a2, v140);
    VHRESULT::~VHRESULT((VHRESULT *)&InternalEntryFromDirNameLeafName);
    goto LABEL_11;
  }
  v141 = VdocHandle::handleDocQuery(a22, &InternalEntryFromDirNameLeafName, v307, 0x8000, 0, 0, 0, 0);
  VHRESULT::operator=(a2, v141);
  VHRESULT::~VHRESULT((VHRESULT *)&InternalEntryFromDirNameLeafName);
  v111 = *(_DWORD *)a2;
  if ( *(int *)a2 < 0 )
  {
    v112 = L"VdocumentStore::updateDocument failed calling handleDocQuery(..., qpAuditMask, ...). (0x%08X)";
    v113 = 20018593;
    goto LABEL_208;
  }
  v142 = VdocHandle::handleDocQuery(a22, &InternalEntryFromDirNameLeafName, v307, v224, 0, 0, 0, 0);
  VHRESULT::operator=(a2, v142);
  VHRESULT::~VHRESULT((VHRESULT *)&InternalEntryFromDirNameLeafName);
  v111 = *(_DWORD *)a2;
  if ( *(int *)a2 < 0 )
  {
    v112 = L"VdocumentStore::updateDocument failed calling handleDocQuery(..., dwQueryParts, ...). (0x%08X)";
    v113 = 20018594;
    goto LABEL_208;
  }
  if ( !v128 )
  {
    v143 = VdocHandle::handleDocQuery(a22, &InternalEntryFromDirNameLeafName, v307, 2, 0, 0, 0, 0);
    VHRESULT::operator=(a2, v143);
    VHRESULT::~VHRESULT((VHRESULT *)&InternalEntryFromDirNameLeafName);
    v111 = *(_DWORD *)a2;
    if ( *(int *)a2 < 0 )
    {
      v112 = L"VdocumentStore::updateDocument failed calling handleDocQuery(..., qpLinks, ...). (0x%08X)";
      v113 = 20018595;
      goto LABEL_208;
    }
  }
  if ( !a18 )
  {
    OutputParam = Voledb::GetOutputParam(v307, &InternalEntryFromDirNameLeafName, v107, &v256, 8, 0);
    VHRESULT::operator=(a2, OutputParam);
    VHRESULT::~VHRESULT((VHRESULT *)&InternalEntryFromDirNameLeafName);
    v111 = *(_DWORD *)a2;
    if ( *(int *)a2 < 0 )
    {
      v112 = L"VdocumentStore::updateDocument failed calling GetOutputParam(iOutparamDtm, ...). (0x%08X)";
      v113 = 20018624;
      goto LABEL_208;
    }
    OWSTimeTFromOleDate(v256, &v297);
    Vtime::Vtime((Vtime *)&InternalEntryFromDirNameLeafName, v297);
    v145 = v252;
    *(_QWORD *)v252 = InternalEntryFromDirNameLeafName;
    *((_BYTE *)v145 + 8) = v222;
  }
  v146 = Voledb::GetOutputParam(v307, &InternalEntryFromDirNameLeafName, (unsigned int)v246, v257, 4, 0);
  VHRESULT::operator=(a2, v146);
  VHRESULT::~VHRESULT((VHRESULT *)&InternalEntryFromDirNameLeafName);
  v111 = *(_DWORD *)a2;
  if ( *(int *)a2 < 0 )
  {
    v112 = L"VdocumentStore::updateDocument failed calling GetOutputParam(iOutparamUIVersion, ...). (0x%08X)";
    v113 = 20018625;
    goto LABEL_208;
  }
  v147 = Voledb::GetOutputParam(v307, &InternalEntryFromDirNameLeafName, (unsigned int)v244, v228, 4, 0);
  VHRESULT::operator=(a2, v147);
  VHRESULT::~VHRESULT((VHRESULT *)&InternalEntryFromDirNameLeafName);
  v111 = *(_DWORD *)a2;
  if ( *(int *)a2 < 0 )
  {
    v112 = L"VdocumentStore::updateDocument failed calling GetOutputParam(iOutparamDocFlags, ...). (0x%08X)";
    v113 = 20018626;
    goto LABEL_208;
  }
  v148 = (_DWORD *)v226[0];
  v149 = Voledb::GetOutputParam(v307, v226, (unsigned int)v229, v226[0], 4, 0);
  VHRESULT::operator=(a2, v149);
  VHRESULT::~VHRESULT((VHRESULT *)v226);
  v111 = *(_DWORD *)a2;
  if ( *(int *)a2 < 0 )
  {
    v112 = L"VdocumentStore::updateDocument failed calling GetOutputParam(iDocVersion, ...). (0x%08X)";
    v113 = 20018627;
    goto LABEL_208;
  }
  v59 = v217;
  LOBYTE(v201) = *((_BYTE *)a22 + 3260);
  VdoclibActivitiesParams::GetOutputActivitiesProperties(
    v300,
    v226,
    v307,
    *((_QWORD *)a22 + 18),
    v220,
    v304,
    v201,
    v217);
  VHRESULT::~VHRESULT((VHRESULT *)v226);
  if ( v215 && (a11 != *v148 || !(unsigned __int8)VserverDebugFlagSet::checkFlag(25063)) )
  {
    v261 = v209 == 0;
    v150 = VWnsSubscriptionProcessor::handleWnsSubscriptionsQueryResult(&v259, v218, v307, *(_QWORD *)v218, 7);
    VHRESULT::operator=(a2, v150);
    VHRESULT::~VHRESULT((VHRESULT *)v218);
    v86 = *(_DWORD *)a2;
    if ( *(int *)a2 < 0 )
    {
      v87 = L"VdocumentStore::updateDocument failed calling handleWnsSubscriptionsQueryResult. (0x%08X)";
      v88 = 20018628;
      goto LABEL_81;
    }
  }
  v151 = Voledb::GetOutputParam(v307, v218, v137, v206, 1, 0);
  VHRESULT::operator=(a2, v151);
  VHRESULT::~VHRESULT((VHRESULT *)v218);
  v86 = *(_DWORD *)a2;
  if ( *(int *)a2 < 0 )
  {
    v87 = L"VdocumentStore::updateDocument failed calling GetOutputParam(iOutparamDocLevel, ...). (0x%08X)";
    v88 = 20018629;
    goto LABEL_81;
  }
  v152 = v206[0];
  *((_BYTE *)a22 + 3260) = v206[0];
  v153 = sub_180029C50(
           (int)v309,
           (int)v218,
           (int)v234,
           (int)a22 + 3144,
           (__int64)a22 + 3128,
           v248,
           v152,
           *((_DWORD *)a22 + 794) + v238,
           (unsigned int)*((_QWORD *)a22 + 398) + *(_DWORD *)v253,
           (__int64)*v253 + *((_QWORD *)a22 + 398),
           *v254,
           a4,
           v236,
           *(_BYTE *)(*(_QWORD *)(*((_QWORD *)a22 + 18) + 56LL) + 984LL));
  VHRESULT::operator=(a2, v153);
  VHRESULT::~VHRESULT((VHRESULT *)v218);
  v86 = *(_DWORD *)a2;
  if ( *(int *)a2 < 0 )
  {
    v87 = L"VdocumentStore::updateDocument failed calling reinitProps. (0x%08X)";
    v88 = 20018630;
    goto LABEL_81;
  }
  v154 = *((_DWORD *)a22 + 818);
  if ( (v154 & 2) == 0 || (v155 = v59 & 0x20, (v59 & 0x20) == 0) )
  {
    if ( (v154 & 0x10) == 0 )
      goto LABEL_12;
    v155 = v59 & 0x20;
    if ( (v59 & 0x20) != 0 )
      goto LABEL_12;
  }
  v156 = v155 != 0 ? 2 : 5;
  Vstring::Vstring((Vstring *)&v227);
  Vstring::Vstring((Vstring *)&v228);
  v157 = v257;
  Vstring::setFromInt((Vstring *)&v227, *v257 >> 9);
  Vstring::setFromInt((Vstring *)&v228, *v157 & 0x1FF);
  v310 = &v311;
  v312 = 0;
  v313 = 512;
  v158 = Vwcslen(L"<Version><Major>");
  sub_18001E0E4(&v310, L"<Version><Major>", v158);
  v159 = *(const wchar_t **)Vwstring::Vwstring((Vwstring *)v218, (const struct Vstring *)&v227);
  v160 = Vwcslen(v159);
  sub_18001E0E4(&v310, v159, v160);
  Vwstring::~Vwstring(v218);
  v161 = Vwcslen(L"</Major><Minor>");
  sub_18001E0E4(&v310, L"</Major><Minor>", v161);
  v162 = *(const wchar_t **)Vwstring::Vwstring((Vwstring *)v218, (const struct Vstring *)&v228);
  v163 = Vwcslen(v162);
  sub_18001E0E4(&v310, v162, v163);
  Vwstring::~Vwstring(v218);
  v164 = Vwcslen(L"</Minor>");
  sub_18001E0E4(&v310, L"</Minor>", v164);
  if ( v220 )
  {
    v219 = 0;
    v216 = 0;
    (*(void (__fastcall **)(__int64, int *, int *))(*(_QWORD *)v220 + 616LL))(v220, &v219, &v216);
    if ( v216 + v219 > 0 )
    {
      v165 = Vwcslen(L"<AutomaticVersionTrimming/>");
      sub_18001E0E4(&v310, L"<AutomaticVersionTrimming/>", v165);
      if ( v219 > 0 )
      {
        v166 = Vwcslen(L"<MajorVersionsRetained>");
        sub_18001E0E4(&v310, L"<MajorVersionsRetained>", v166);
        v167 = (const struct Vstring *)Vitostr(v226, (unsigned int)v219);
        v168 = *(const wchar_t **)Vwstring::Vwstring((Vwstring *)v218, v167);
        v169 = Vwcslen(v168);
        sub_18001E0E4(&v310, v168, v169);
        Vwstring::~Vwstring(v218);
        Vstring::~Vstring((Vstring *)v226);
        v170 = Vwcslen(L"</MajorVersionsRetained>");
        sub_18001E0E4(&v310, L"</MajorVersionsRetained>", v170);
      }
      if ( v216 > 0 )
      {
        v171 = Vwcslen(L"<DraftsForMajorVersionsRetained>");
        sub_18001E0E4(&v310, L"<DraftsForMajorVersionsRetained>", v171);
        v172 = (const struct Vstring *)Vitostr(v226, (unsigned int)v216);
        v173 = *(const wchar_t **)Vwstring::Vwstring((Vwstring *)v218, v172);
        v174 = Vwcslen(v173);
        sub_18001E0E4(&v310, v173, v174);
        Vwstring::~Vwstring(v218);
        Vstring::~Vstring((Vstring *)v226);
        v175 = Vwcslen(L"</DraftsForMajorVersionsRetained>");
        sub_18001E0E4(&v310, L"</DraftsForMajorVersionsRetained>", v175);
      }
    }
  }
  v176 = Vwcslen(L"</Version>");
  sub_18001E0E4(&v310, L"</Version>", v176);
  AppPrincipalId = VsecurityUtil::GetAppPrincipalId(*((const struct VsecurableObject **)a22 + 18));
  v61 = v211;
  v178 = *(_BYTE *)(*((_QWORD *)v211 + 7) + 513LL);
  *(_WORD *)&v310[2 * v312] = 0;
  v179 = *(_QWORD *)(*((_QWORD *)a22 + 18) + 64LL);
  if ( v179 )
    v180 = *(_QWORD *)(v179 + 88);
  else
    v180 = 0;
  LOBYTE(v202) = v178;
  InternalEntryFromDirNameLeafName = (struct VlinkVvector *)VauditEntry::createInternalEntryFromDirNameLeafName(
                                                              *((_QWORD *)v61 + 7) + 184LL,
                                                              (char *)a22 + 3128,
                                                              *v240,
                                                              *v241,
                                                              (*((_DWORD *)a22 + 770) & 0x40) != 0 ? 5 : 1,
                                                              **(_DWORD **)(v180 + 48),
                                                              AppPrincipalId,
                                                              v156,
                                                              v310,
                                                              v202);
  if ( InternalEntryFromDirNameLeafName )
  {
    v181 = VglobalAuditStore::addAuditEntry(v218, *((_QWORD *)v61 + 7), &InternalEntryFromDirNameLeafName);
    VHRESULT::operator=(a2, v181);
    VHRESULT::~VHRESULT((VHRESULT *)v218);
    if ( *(int *)a2 < 0 )
    {
      LODWORD(v195) = *(_DWORD *)a2;
      ULSSendTraceTag(
        20018632,
        117141511,
        50,
        L"VdocumentStore::updateDocument failed calling addAuditEntry. (0x%08X)",
        v195);
    }
  }
  else
  {
    ULSSendTraceTag(
      20018631,
      117141511,
      50,
      L"VdocumentStore::updateDocument failed because createInternalEntryFromDirNameLeafName returned NULL.");
    VHRESULT::operator=(a2, 2147942414LL);
  }
  sub_1800012D0(&v310);
  Vstring::~Vstring((Vstring *)&v228);
  Vstring::~Vstring((Vstring *)&v227);
  v60 = v212;
LABEL_14:
  v62 = v263;
  if ( v263 )
  {
    (*(void (__fastcall **)(char *))(*((_QWORD *)v263 + 8) + 16LL))(v263 + 64);
    v263 = 0;
  }
  v63 = v235;
  if ( (_DWORD)v235 != -1 )
  {
    *(_QWORD *)v218 = v226;
    v64 = VHRESULT::VHRESULT((VHRESULT *)v226, a2);
    v65 = sub_18002BA50(&InternalEntryFromDirNameLeafName, v307, v64, v63);
    VHRESULT::operator=(a2, v65);
    VHRESULT::~VHRESULT((VHRESULT *)&InternalEntryFromDirNameLeafName);
  }
  if ( *(_DWORD *)a2 == -2147018894 && v210 )
  {
    VHRESULT::operator=(a2, 2164392041LL);
    LODWORD(v195) = *(_DWORD *)a2;
    ULSSendTraceTag(
      6632473,
      117141571,
      50,
      L"Missing required properties/validation failure and the checkout failed due to a shared lock. Converting to HR: 0x%08x",
      v195);
  }
  v66 = Block;
  if ( (unsigned int)COWSAllocator::QueryNewMode(v62) )
    COWSAllocator::Free(v66);
  else
    free(v66);
  Block = 0;
  if ( *(int *)a2 < 0 )
  {
    LODWORD(v195) = *(_DWORD *)a2;
    ULSSendTraceTag(
      20018633,
      117141511,
      50,
      L"VdocumentStore::updateDocument failed calling GetBetterHrFromOutParam. (0x%08X)",
      v195);
    *(_QWORD *)v218 = v226;
    v182 = VHRESULT::VHRESULT((VHRESULT *)v226, a2);
    if ( (unsigned __int8)CTranLockManager::IsTranLockError(v182) )
    {
      *(_QWORD *)v218 = v226;
      v183 = VHRESULT::VHRESULT((VHRESULT *)v226, a2);
      CTranLockManager::LogTranLockErrors(v183, (char *)v61 + 264);
      VHRESULT::operator=(a2, 2147500037LL);
    }
    v184 = v242;
    if ( v242 )
    {
      *(_QWORD *)v218 = v226;
      v185 = VHRESULT::VHRESULT((VHRESULT *)v226, a2);
      v186 = VdocumentStore::setFieldDataErrors(
               v230,
               &InternalEntryFromDirNameLeafName,
               v61,
               v184[8],
               v184[9],
               v307,
               v185);
      VHRESULT::operator=(a2, v186);
      VHRESULT::~VHRESULT((VHRESULT *)&InternalEntryFromDirNameLeafName);
    }
  }
  if ( *(int *)a2 >= 0 && v299[0] )
    CWebLocker::setLockWasReleasedInSQL((CWebLocker *)v299);
  v306 = *(_OWORD *)((char *)a22 + 3128);
  if ( *(int *)a2 >= 0 && (v224 & 0x40) != 0 )
  {
    v187 = 1;
    if ( (v59 & 0x1000020) == 0x20 )
      v187 = 5;
    VdocumentStore::fireListEvent(v220, v61, v187, 0, *v60, *((_QWORD *)a22 + 381), (char *)a22 + 168);
    LOBYTE(psza) = 0;
    VdocHandle::checkAndFireItemEvent(
      a22,
      v218,
      a22,
      *((_QWORD *)a22 + 384),
      10002,
      psza,
      v59,
      0,
      *((_DWORD *)a22 + 828),
      0,
      &v306);
    v188 = 1;
    v225 = 1;
    VHRESULT::~VHRESULT((VHRESULT *)v218);
  }
  else
  {
    v188 = v225;
  }
  Vstring::Vstring((Vstring *)&v242, *v240);
  v226[0] = v239;
  Vstring::Vstring((Vstring *)v239, (const struct Vstring *)&v242);
  Vstring::~Vstring((Vstring *)&v242);
  v226[0] = &v230;
  Vstring::Vstring((Vstring *)&v230, *v241);
  v226[0] = &v230;
  InternalEntryFromDirNameLeafName = (struct VlinkVvector *)v218;
  v189 = Vstring::Vstring((Vstring *)v218, (const struct Vstring *)&v230);
  VurlTemplate<VstoreUrlSettings>::safeAppend(v239, v189);
  Vstring::~Vstring((Vstring *)&v230);
  *(_QWORD *)v218 = &v231;
  Vstring::Vstring((Vstring *)&v231);
  v190 = L"File";
  if ( (*((_DWORD *)a22 + 770) & 0x40) != 0 )
    v190 = L"Folder";
  v191 = L"FileModified";
  if ( (*((_DWORD *)a22 + 770) & 0x40) != 0 )
    v191 = L"FolderModified";
  VSimpleUsageEventLog::writeFileActivityLogInternal(v226, v191, &v306, &v305, v61, v239, v190, &v231, 1, 0, v304, v300);
  v225 = v188 & 0xFFFFFBFF;
  VHRESULT::~VHRESULT((VHRESULT *)v226);
  *(_QWORD *)v218 = &v231;
  Vstring::~Vstring((Vstring *)&v231);
  if ( v220 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v220 + 64LL))(v220);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v220 + 16LL))(v220);
  }
  *(_QWORD *)v218 = v226;
  if ( *((_QWORD *)v61 + 7) )
  {
    v192 = VHRESULT::VHRESULT((VHRESULT *)v226, a2);
    LOBYTE(psz) = *((_BYTE *)a22 + 3260);
    VmonitoredScope::Done(v298, v192, v236, *((_QWORD *)v61 + 7) + 184LL, (char *)a22 + 3128, psz);
  }
  else
  {
    v193 = VHRESULT::VHRESULT((VHRESULT *)v226, a2);
    LOBYTE(psz) = 0;
    VmonitoredScope::Done(v298, v193, v236, &stru_18020E740, &stru_18020E740, psz);
  }
  *(_QWORD *)v218 = v239;
  Vstring::~Vstring((Vstring *)v239);
  v259 = &VWnsSubscriptionProcessor::`vftable';
  v260 = 0;
  Vwstring::~Vwstring(&v248);
  CWebLocker::~CWebLocker((CWebLocker *)v299);
  VwstringVvector::~VwstringVvector(v304);
  VdoclibActivitiesParams::~VdoclibActivitiesParams((VdoclibActivitiesParams *)v300);
  VdoclibUpdateParams::~VdoclibUpdateParams((VdoclibUpdateParams *)v262);
  Voledb::~Voledb((Voledb *)v307);
  VmonitoredScope::~VmonitoredScope((VmonitoredScope *)v298);
  Vstring::~Vstring(v258);
  return a2;
}

```

## disassembly

```asm
0x1800e0fa0  mov     rax, rsp
0x1800e0fa3  push    rbp
0x1800e0fa4  push    rsi
0x1800e0fa5  push    rdi
0x1800e0fa6  push    r12
0x1800e0fa8  push    r13
0x1800e0faa  push    r14
0x1800e0fac  push    r15
0x1800e0fae  lea     rbp, [rax-0BD8h]
0x1800e0fb5  sub     rsp, 0CE0h
0x1800e0fbc  mov     [rbp+0BD0h+var_960], 0FFFFFFFFFFFFFFFEh
0x1800e0fc7  mov     [rax+20h], rbx
0x1800e0fcb  mov     rax, cs:__security_cookie
0x1800e0fd2  xor     rax, rsp
0x1800e0fd5  mov     [rbp+0BD0h+var_40], rax
0x1800e0fdc  mov     edi, r9d
0x1800e0fdf  mov     [rbp+0BD0h+var_B90], r8
0x1800e0fe3  mov     r14, rdx
0x1800e0fe6  mov     [rbp+0BD0h+var_BA0], rcx
0x1800e0fea  mov     [rbp+0BD0h+var_958], rdx
0x1800e0ff1  mov     rax, [rbp+0BD0h+arg_20]
0x1800e0ff8  mov     [rbp+0BD0h+var_B58], rax
0x1800e0ffc  mov     rax, [rbp+0BD0h+arg_28]
0x1800e1003  mov     [rbp+0BD0h+var_B50], rax
0x1800e100a  mov     rax, [rbp+0BD0h+arg_30]
0x1800e1011  mov     [rbp+0BD0h+var_C20], rax
0x1800e1015  mov     rax, [rbp+0BD0h+arg_38]
0x1800e101c  mov     [rbp+0BD0h+var_BB8], rax
0x1800e1020  mov     rax, [rbp+0BD0h+arg_40]
0x1800e1027  mov     [rbp+0BD0h+var_B00], rax
0x1800e102e  mov     rax, [rbp+0BD0h+arg_60]
0x1800e1035  mov     [rbp+0BD0h+var_BB0], rax
0x1800e1039  mov     sil, [rbp+0BD0h+arg_78]
0x1800e1040  mov     rax, [rbp+0BD0h+arg_90]
0x1800e1047  mov     [rbp+0BD0h+var_B30], rax
0x1800e104e  mov     rax, [rbp+0BD0h+arg_98]
0x1800e1055  mov     [rbp+0BD0h+var_AE8], rax
0x1800e105c  mov     rax, [rbp+0BD0h+arg_A0]
0x1800e1063  mov     [rbp+0BD0h+var_AC0], rax
0x1800e106a  mov     r15, [rbp+0BD0h+arg_A8]
0x1800e1071  mov     rax, [rbp+0BD0h+arg_B0]
0x1800e1078  mov     [rbp+0BD0h+var_B40], rax
0x1800e107f  mov     rax, [rbp+0BD0h+arg_B8]
0x1800e1086  mov     [rbp+0BD0h+var_BE8], rax
0x1800e108a  mov     rax, [rbp+0BD0h+arg_C0]
0x1800e1091  mov     [rbp+0BD0h+var_9D0], rax
0x1800e1098  mov     rax, [rbp+0BD0h+arg_C8]
0x1800e109f  mov     [rbp+0BD0h+var_9D8], rax
0x1800e10a6  mov     r13, [rbp+0BD0h+arg_D8]
0x1800e10ad  mov     [rbp+0BD0h+var_C10], r13
0x1800e10b1  mov     rax, [rbp+0BD0h+arg_F0]
0x1800e10b8  mov     [rbp+0BD0h+var_B20], rax
0x1800e10bf  mov     rax, [rbp+0BD0h+arg_108]
0x1800e10c6  mov     [rbp+0BD0h+var_AB8], rax
0x1800e10cd  mov     [rbp+0BD0h+var_950], rax
0x1800e10d4  mov     rax, [rbp+0BD0h+arg_118]
0x1800e10db  mov     [rbp+0BD0h+var_9E0], rax
0x1800e10e2  mov     rdx, [rbp+0BD0h+arg_150]
0x1800e10e9  mov     [rbp+0BD0h+var_B98], rdx
0x1800e10ed  mov     rax, [rbp+0BD0h+arg_158]
0x1800e10f4  mov     [rbp+0BD0h+var_BC8], rax
0x1800e10f8  mov     eax, [rbp+0BD0h+arg_160]
0x1800e10fe  mov     [rbp+0BD0h+var_B64], eax
0x1800e1101  mov     rax, [rbp+0BD0h+arg_168]
0x1800e1108  mov     [rbp+0BD0h+var_AE0], rax
0x1800e110f  mov     rax, [rbp+0BD0h+arg_170]
0x1800e1116  mov     [rbp+0BD0h+var_AD8], rax
0x1800e111d  xor     ebx, ebx
0x1800e111f  mov     [rbp+0BD0h+var_BD0], ebx
0x1800e1122  lea     rax, aVdocumentstore_86; "VdocumentStore::updateDocument"
0x1800e1129  mov     [rsp+0D10h+var_CF0], rax; wchar_t *
0x1800e112e  mov     edx, 215798h; unsigned int
0x1800e1133  lea     r9d, [rbx+32h]; unsigned int
0x1800e1137  mov     r8d, 6FB7043h; unsigned int
0x1800e113d  lea     rcx, [rbp+0BD0h+var_9C0]; this
0x1800e1144  call    ??0VmonitoredScope@@QEAA@KKKPEB_W@Z; VmonitoredScope::VmonitoredScope(ulong,ulong,ulong,wchar_t const *)
0x1800e1149  nop
0x1800e114a  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800e114e  mov     [rbp+0BD0h+var_B78], rax
0x1800e1152  mov     [rbp+0BD0h+var_B70], rax
0x1800e1156  mov     r12, [r15+90h]
0x1800e115d  mov     [rbp+0BD0h+var_C28], r12
0x1800e1161  mov     al, [r15+0CBCh]
0x1800e1168  mov     [rbp+0BD0h+var_C40], al
0x1800e116b  xor     edx, edx
0x1800e116d  mov     rcx, r14
0x1800e1170  call    cs:??0VHRESULT@@QEAA@J@Z; VHRESULT::VHRESULT(long)
0x1800e1176  lea     ecx, [rbx+1]
0x1800e1179  mov     [rbp+0BD0h+var_BD0], ecx
0x1800e117c  cmp     [r12+1C8h], rbx
0x1800e1184  setz    [rbp+0BD0h+var_C17]
0x1800e1188  mov     byte ptr [rbp+0BD0h+var_C14], bl
0x1800e118b  mov     byte ptr [rbp+0BD0h+var_BF8], bl
0x1800e118e  cmp     [rbp+0BD0h+arg_D0], ebx
0x1800e1194  setnz   [rbp+0BD0h+var_C50]
0x1800e1198  mov     [rbp+0BD0h+var_BD4], ebx
0x1800e119b  mov     [rbp+0BD0h+var_BF0], rbx
0x1800e119f  mov     [rbp+0BD0h+var_C30], bl
0x1800e11a2  mov     r8b, cl; char
0x1800e11a5  mov     rdx, [rbp+0BD0h+var_BA0]; struct COWSConnection *
0x1800e11a9  lea     rcx, [rbp+0BD0h+var_900]; this
0x1800e11b0  call    ??0Voledb@@QEAA@PEAVCOWSConnection@@D@Z; Voledb::Voledb(COWSConnection *,char)
0x1800e11b5  nop
0x1800e11b6  lea     rcx, [rbp+0BD0h+var_A90]; this
0x1800e11bd  call    ??0VdoclibUpdateParams@@QEAA@XZ; VdoclibUpdateParams::VdoclibUpdateParams(void)
0x1800e11c2  nop
0x1800e11c3  mov     [rbp+0BD0h+var_B48], rbx
0x1800e11ca  lea     rcx, [rbp+0BD0h+var_988]; this
0x1800e11d1  call    ??0VdoclibActivitiesParams@@QEAA@XZ; VdoclibActivitiesParams::VdoclibActivitiesParams(void)
0x1800e11d6  nop
0x1800e11d7  lea     rcx, [rbp+0BD0h+var_948]
0x1800e11de  call    cs:??0VwstringVvector@@QEAA@XZ; VwstringVvector::VwstringVvector(void)
0x1800e11e4  nop
0x1800e11e5  mov     rdx, [rbp+0BD0h+var_BA0]
0x1800e11e9  lea     rcx, [rbp+0BD0h+var_4B0]
0x1800e11f0  call    sub_1800F7DE0
0x1800e11f5  nop
0x1800e11f6  mov     rdx, r12; struct VdbSubweb *
0x1800e11f9  lea     rcx, [rbp+0BD0h+var_9B0]; this
0x1800e1200  call    ??0CWebLocker@@QEAA@PEAVVdbSubweb@@@Z; CWebLocker::CWebLocker(VdbSubweb *)
0x1800e1205  nop
0x1800e1206  mov     [rbp+0BD0h+var_AD0], rbx
0x1800e120d  lea     r12, [r15+98h]
0x1800e1214  mov     rcx, r12
0x1800e1217  call    cs:?data@Vstring@@QEBAPEBDXZ; Vstring::data(void)
0x1800e121d  mov     rdx, rax
0x1800e1220  lea     rcx, [rbp+0BD0h+var_B10]
0x1800e1227  call    cs:??0Vwstring@@QEAA@PEBD@Z; Vwstring::Vwstring(char const *)
0x1800e122d  nop
0x1800e122e  mov     [rbp+0BD0h+Block], rbx
0x1800e1235  or      [rbp+0BD0h+var_B88], 0FFFFFFFFh
0x1800e1239  mov     [rbp+0BD0h+var_C2E], bl
0x1800e123c  lea     rax, ??_7VWnsSubscriptionProcessor@@6B@; const VWnsSubscriptionProcessor::`vftable'
0x1800e1243  mov     [rbp+0BD0h+var_AB0], rax
0x1800e124a  mov     rax, [rbp+0BD0h+var_B90]
0x1800e124e  mov     [rbp+0BD0h+var_AA8], rax
0x1800e1255  mov     [rbp+0BD0h+var_AA0], bl
0x1800e125b  mov     [rbp+0BD0h+var_C16], bl
0x1800e125e  mov     [rbp+0BD0h+var_C2F], bl
0x1800e1261  mov     rax, r13
0x1800e1264  shr     rax, 14h
0x1800e1268  and     al, 1
0x1800e126a  mov     [rbp+0BD0h+var_AF0], rax
0x1800e1271  mov     r13d, [r15+178h]
0x1800e1278  mov     rcx, [r15+170h]
0x1800e127f  mov     [rbp+0BD0h+var_BA8], rcx
0x1800e1283  test    rcx, rcx
0x1800e1286  setnz   al
0x1800e1289  test    al, al
0x1800e128b  jz      short loc_1800E12A5
0x1800e128d  mov     rax, [rbp+0BD0h+var_BB8]
0x1800e1291  test    rax, rax
0x1800e1294  jz      short loc_1800E12AC
0x1800e1296  cmp     [rax+18h], rbx
0x1800e129a  jz      short loc_1800E12AC
0x1800e129c  cmp     [r15+17Ch], bl
0x1800e12a3  jnz     short loc_1800E12AC
0x1800e12a5  mov     [rbp+0BD0h+var_BA8], rbx
0x1800e12a9  mov     r13d, ebx
0x1800e12ac  cmp     [rbp+0BD0h+arg_88], bl
0x1800e12b2  jz      short loc_1800E12D0
0x1800e12b4  mov     rcx, [rbp+0BD0h+var_AE8]
0x1800e12bb  call    cs:?secondsI64@Vtime@@QEBA_KXZ; Vtime::secondsI64(void)
0x1800e12c1  mov     rcx, rax; unsigned __int64
0x1800e12c4  lea     rdx, [rbp+0BD0h+var_AC8]; double *
0x1800e12cb  call    ?OWSOleDateFromTimeT@@YAD_KPEAN@Z; OWSOleDateFromTimeT(unsigned __int64,double *)
0x1800e12d0  mov     rcx, [rbp+0BD0h+var_C28]; this
0x1800e12d4  call    ?getDoclibManager@VdbSubweb@@QEAAPEAVVdoclibManager@@XZ; VdbSubweb::getDoclibManager(void)
0x1800e12d9  mov     rcx, rax
0x1800e12dc  lea     rax, [rbp+0BD0h+var_BF0]
0x1800e12e0  mov     [rsp+0D10h+var_CF0], rax
0x1800e12e5  mov     r9b, sil
0x1800e12e8  mov     r8, r12
0x1800e12eb  lea     rdx, [rbp+0BD0h+var_C08]
0x1800e12ef  call    ?GetContainingList@VdoclibManager@@QEAA?AVVHRESULT@@AEBVVurlStorePath@@DPEAPEAUITPList@@@Z; VdoclibManager::GetContainingList(VurlStorePath const &,char,ITPList * *)
0x1800e12f4  lea     rcx, [rbp+0BD0h+var_C08]
0x1800e12f8  call    cs:??1VHRESULT@@QEAA@XZ; VHRESULT::~VHRESULT(void)
0x1800e12fe  cmp     [rbp+0BD0h+arg_F8], bl
0x1800e1304  jz      loc_1800E1475
0x1800e130a  mov     rcx, [rbp+0BD0h+var_BF0]
0x1800e130e  test    rcx, rcx
0x1800e1311  jnz     loc_1800E1422
0x1800e1317  lea     r9, aVdocumentstore_87; "VdocumentStore::updateDocument failed b"...
0x1800e131e  mov     edx, 6FB7007h
0x1800e1323  mov     ecx, 1317597h
0x1800e1328  mov     r8d, 32h ; '2'
0x1800e132e  call    cs:ULSSendTraceTag
0x1800e1334  mov     edx, 80004005h
0x1800e1339  mov     rcx, r14
0x1800e133c  call    cs:??4VHRESULT@@QEAAAEAV0@J@Z; VHRESULT::operator=(long)
0x1800e1342  mov     r12, [rbp+0BD0h+var_C10]
0x1800e1346  mov     rsi, [rbp+0BD0h+var_C20]
0x1800e134a  mov     r13, [rbp+0BD0h+var_C28]
0x1800e134e  mov     rcx, [rbp+0BD0h+var_A70]
0x1800e1355  test    rcx, rcx
0x1800e1358  jz      short loc_1800E1372
0x1800e135a  add     rcx, 40h ; '@'
0x1800e135e  mov     rax, [rcx]
0x1800e1361  mov     rax, [rax+10h]
0x1800e1365  call    cs:__guard_dispatch_icall_fptr
0x1800e136b  mov     [rbp+0BD0h+var_A70], rbx
0x1800e1372  mov     rdi, [rbp+0BD0h+var_B78]
0x1800e1376  cmp     edi, 0FFFFFFFFh
0x1800e1379  jz      short loc_1800E13BF
0x1800e137b  lea     rax, [rbp+0BD0h+var_BC8]
0x1800e137f  mov     qword ptr [rbp+0BD0h+var_C08], rax
0x1800e1383  mov     rdx, r14
0x1800e1386  lea     rcx, [rbp+0BD0h+var_BC8]
0x1800e138a  call    cs:??0VHRESULT@@QEAA@AEBV0@@Z; VHRESULT::VHRESULT(VHRESULT const &)
0x1800e1390  nop
0x1800e1391  mov     r9d, edi
0x1800e1394  mov     r8, rax
0x1800e1397  lea     rdx, [rbp+0BD0h+var_900]
0x1800e139e  lea     rcx, [rbp+0BD0h+var_BE8]
0x1800e13a2  call    sub_18002BA50
0x1800e13a7  nop
0x1800e13a8  mov     rdx, rax
0x1800e13ab  mov     rcx, r14
0x1800e13ae  call    cs:??4VHRESULT@@QEAAAEAV0@AEBV0@@Z; VHRESULT::operator=(VHRESULT const &)
0x1800e13b4  nop
0x1800e13b5  lea     rcx, [rbp+0BD0h+var_BE8]
0x1800e13b9  call    cs:??1VHRESULT@@QEAA@XZ; VHRESULT::~VHRESULT(void)
0x1800e13bf  cmp     dword ptr [r14], 80071772h
0x1800e13c6  jnz     short loc_1800E13FF
0x1800e13c8  cmp     [rbp+0BD0h+var_C2E], bl
0x1800e13cb  jz      short loc_1800E13FF
0x1800e13cd  mov     edx, 81020069h
0x1800e13d2  mov     rcx, r14
0x1800e13d5  call    cs:??4VHRESULT@@QEAAAEAV0@J@Z; VHRESULT::operator=(long)
0x1800e13db  mov     eax, [r14]
0x1800e13de  mov     dword ptr [rsp+0D10h+var_CF0], eax
0x1800e13e2  lea     r9, aMissingRequire; "Missing required properties/validation "...
0x1800e13e9  mov     edx, 6FB7043h
0x1800e13ee  mov     ecx, 653419h
0x1800e13f3  mov     r8d, 32h ; '2'
0x1800e13f9  call    cs:ULSSendTraceTag
0x1800e13ff  mov     rdi, [rbp+0BD0h+Block]
0x1800e1406  call    cs:?QueryNewMode@COWSAllocator@@SAHXZ; COWSAllocator::QueryNewMode(void)
0x1800e140c  mov     rcx, rdi; Block
0x1800e140f  test    eax, eax
0x1800e1411  jz      loc_1800E3C59
0x1800e1417  call    cs:?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800e141d  jmp     loc_1800E3C5F
0x1800e1422  mov     rax, [rcx]
0x1800e1425  mov     rax, [rax+1E0h]
0x1800e142c  call    cs:__guard_dispatch_icall_fptr
0x1800e1432  test    eax, eax
0x1800e1434  jz      short loc_1800E1475
0x1800e1436  mov     rcx, [rbp+0BD0h+var_BF0]
0x1800e143a  mov     rax, [rcx]
0x1800e143d  mov     rax, [rax+1E8h]
0x1800e1444  call    cs:__guard_dispatch_icall_fptr
0x1800e144a  mov     rcx, rax
0x1800e144d  mov     r9d, 32h ; '2'
0x1800e1453  mov     r8d, 800h
0x1800e1459  lea     rdx, [rbp+0BD0h+var_C08]
0x1800e145d  call    ?assertPermissionMask@VsecurableObject@@QEBA?AVVHRESULT@@_KW4_ulstracelevel@@@Z; VsecurableObject::assertPermissionMask(unsigned __int64,_ulstracelevel)
0x1800e1462  nop
0x1800e1463  cmp     [rax], ebx
0x1800e1465  setnl   al
0x1800e1468  mov     [rbp+0BD0h+var_C30], al
0x1800e146b  lea     rcx, [rbp+0BD0h+var_C08]
0x1800e146f  call    cs:??1VHRESULT@@QEAA@XZ; VHRESULT::~VHRESULT(void)
0x1800e1475  mov     rdx, [rbp+0BD0h+var_BF0]
0x1800e1479  test    rdx, rdx
0x1800e147c  jz      short loc_1800E14DE
0x1800e147e  mov     r9d, 2
0x1800e1484  xor     r8d, r8d
0x1800e1487  mov     rcx, r12
0x1800e148a  call    ?IsDoclibItem@VdoclibManager@@SADAEBVVurlStorePath@@PEAUITPList@@PEADW4VtriState@@@Z; VdoclibManager::IsDoclibItem(VurlStorePath const &,ITPList *,char *,VtriState)
0x1800e148f  test    al, al
0x1800e1491  jnz     short loc_1800E149C
0x1800e1493  mov     rcx, [rbp+0BD0h+var_BB0]
0x1800e1497  test    byte ptr [rcx], 2
0x1800e149a  jz      short loc_1800E14DE
0x1800e149c  mov     rcx, [rbp+0BD0h+var_BF0]
0x1800e14a0  mov     rax, [rcx]
0x1800e14a3  mov     rax, [rax+238h]
0x1800e14aa  call    cs:__guard_dispatch_icall_fptr
0x1800e14b0  mov     rcx, [rbp+0BD0h+var_BF0]
0x1800e14b4  mov     rax, [rcx]
0x1800e14b7  mov     rax, [rax+1E0h]
0x1800e14be  call    cs:__guard_dispatch_icall_fptr
0x1800e14c4  mov     [rbp+0BD0h+var_C14], eax
0x1800e14c7  mov     rcx, [rbp+0BD0h+var_BF0]
0x1800e14cb  mov     rax, [rcx]
0x1800e14ce  mov     rax, [rax+248h]
0x1800e14d5  call    cs:__guard_dispatch_icall_fptr
0x1800e14db  mov     [rbp+0BD0h+var_BF8], eax
0x1800e14de  mov     rax, 40000000000h
0x1800e14e8  mov     rsi, [rbp+0BD0h+var_B90]
0x1800e14ec  test    [rbp+0BD0h+var_C10], rax
0x1800e14f0  jnz     short loc_1800E1502
0x1800e14f2  mov     rcx, rsi; this
0x1800e14f5  call    ?allowPoundPercentInPath@VdbServer@@QEBADXZ; VdbServer::allowPoundPercentInPath(void)
0x1800e14fa  test    al, al
0x1800e14fc  jnz     short loc_1800E1502
0x1800e14fe  mov     al, bl
0x1800e1500  jmp     short loc_1800E1507
0x1800e1502  mov     eax, 1
  ... truncated ...
```
