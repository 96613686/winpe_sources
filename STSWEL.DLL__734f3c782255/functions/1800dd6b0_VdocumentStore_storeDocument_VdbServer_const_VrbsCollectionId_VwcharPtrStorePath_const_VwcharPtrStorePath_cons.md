# VdocumentStore::storeDocument(VdbServer const *,VrbsCollectionId,VwcharPtrStorePath const &,VwcharPtrStorePath const &,VwcharPtrStorePath const &,_GUID const *,_GUID const *,VfileBlobManager &,ulong &,uchar const *,ulong,ulong,char,char,VtriState,__int64,uint,char const *,char,char,Vtime const &,Vtime &,VdocHandle *,VvirusCheck *,VlinkVvector const *,wchar_t const * *,uchar const *,ulong,long,long,long,long,char,Vstring const &,_GUID const *,ulong &,ulong,char,__int64 *,uchar *,long,SPFileSaveParams const *,long,VtriState)

- ea: `0x1800dd6b0`
- end: `0x1800dffe6`
- name: `?storeDocument@VdocumentStore@@QEAA?AVVHRESULT@@PEBVVdbServer@@VVrbsCollectionId@@AEBVVwcharPtrStorePath@@22PEBU_GUID@@3AEAVVfileBlobManager@@AEAKPEBEKKDDW4VtriState@@_JIPEBDDDAEBVVtime@@AEAV9@PEAVVdocHandle@@PEAVVvirusCheck@@PEBVVlinkVvector@@PEAPEB_W6KJJJJDAEBVVstring@@35KDPEA_JPEAEJPEBUSPFileSaveParams@@JW48@@Z`
- size: `10550`
- prototype: `struct VHRESULT __high(const struct VdbServer *, struct VrbsCollectionId, const struct VwcharPtrStorePath *, const struct VwcharPtrStorePath *, const struct VwcharPtrStorePath *, const struct _GUID *, const struct _GUID *, struct VfileBlobManager *, unsigned int *, const unsigned __int8 *, unsigned int, unsigned int, char, char, enum VtriState, __int64, unsigned int, const char *, char, char, const struct Vtime *, struct Vtime *, struct VdocHandle *, struct VvirusCheck *, const struct VlinkVvector *, const wchar_t **, const unsigned __int8 *, unsigned int, int, int, int, int, char, const struct Vstring *, const struct _GUID *, unsigned int *, unsigned int, char, __int64 *, unsigned __int8 *, int, const struct SPFileSaveParams *, int, enum VtriState)`
- caller_count: `1`
- callee_count: `74`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800fc0d0`

## callees

- `0x180001258`
- `0x180007a80`
- `0x180007ce0`
- `0x180007e40`
- `0x18000b570`
- `0x180028a08`
- `0x180029938`
- `0x180029c50`
- `0x18002ba50`
- `0x18004a6c0`
- `0x18004a760`
- `0x18008ea10`
- `0x18008ea50`
- `0x1800974f0`
- `0x1800a3f10`
- `0x1800b3550`
- `0x1800b4140`
- `0x1800b48e0`
- `0x1800b5880`
- `0x1800b5d00`
- `0x1800b5e70`
- `0x1800c407c`
- `0x1800c40f4`
- `0x1800c4188`
- `0x1800dd3d0`
- `0x1800dd67c`
- `0x1800dd6b0`
- `0x1800eee90`
- `0x1800ef850`
- `0x1800f72b0`
- `0x1800f7710`
- `0x1800f7800`
- `0x1800f7de0`
- `0x1800f7e14`
- `0x1800fe480`
- `0x1800ffbf0`
- `0x180102620`
- `0x1801026d0`
- `0x180136f50`
- `0x180137380`
- `0x180173a70`
- `0x18017fbe0`
- `0x180181b60`
- `0x180181c70`
- `0x180181dc0`
- `0x180182c10`
- `0x180190350`
- `0x1801906a0`
- `0x180197ff0`
- `0x180198290`

## import_xrefs

- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x1800dd93d`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x1800decad`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x1800dd93d`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x1800decad`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x1800ddb69`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x1800ddc9a`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x1800df3c9`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x1800df52b`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x1800df8d3`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x1800ddb69`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x1800ddc9a`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x1800df3c9`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x1800df52b`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x1800df8d3`
- `onetutil!??0VHRESULT@@QEAA@AEBV0@@Z` at `0x1800df601`
- `onetutil!??0VHRESULT@@QEAA@AEBV0@@Z` at `0x1800df802`
- `onetutil!??0VHRESULT@@QEAA@AEBV0@@Z` at `0x1800df885`
- `onetutil!??0VHRESULT@@QEAA@AEBV0@@Z` at `0x1800df8b1`
- `onetutil!??0VHRESULT@@QEAA@AEBV0@@Z` at `0x1800dfde4`
- `onetutil!??0VHRESULT@@QEAA@AEBV0@@Z` at `0x1800dfe6d`
- `onetutil!??0VHRESULT@@QEAA@AEBV0@@Z` at `0x1800dfee3`
- `onetutil!??0VHRESULT@@QEAA@AEBV0@@Z` at `0x1800dff18`
- `onetutil!??0VHRESULT@@QEAA@AEBV0@@Z` at `0x1800df601`
- `onetutil!??0VHRESULT@@QEAA@AEBV0@@Z` at `0x1800df802`
- `onetutil!??0VHRESULT@@QEAA@AEBV0@@Z` at `0x1800df885`
- `onetutil!??0VHRESULT@@QEAA@AEBV0@@Z` at `0x1800df8b1`
- `onetutil!??0VHRESULT@@QEAA@AEBV0@@Z` at `0x1800dfde4`
- `onetutil!??0VHRESULT@@QEAA@AEBV0@@Z` at `0x1800dfe6d`
- `onetutil!??0VHRESULT@@QEAA@AEBV0@@Z` at `0x1800dfee3`
- `onetutil!??0VHRESULT@@QEAA@AEBV0@@Z` at `0x1800dff18`
- `onetutil!??0Vwstring@@QEAA@PEB_W@Z` at `0x1800dda03`
- `onetutil!??0Vwstring@@QEAA@PEB_W@Z` at `0x1800dda03`
- `onetutil!??1VwstringVvector@@QEAA@XZ` at `0x1800dfa90`
- `onetutil!??1VwstringVvector@@QEAA@XZ` at `0x1800dfa90`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800dda8e`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800de15b`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800de3f8`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800df152`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800df244`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800df2c8`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800df33e`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800df5b0`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800df625`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800df675`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800df6dd`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800df73a`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800df7a2`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800df82a`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800dfce5`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800dfd69`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800dfe0b`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800dfeaf`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800dda8e`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800de15b`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800de3f8`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800df152`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800df244`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800df2c8`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800df33e`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800df5b0`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800df625`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800df675`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800df6dd`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800df73a`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800df7a2`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800df82a`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800dfce5`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800dfd69`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800dfe0b`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1800dfeaf`
- `onetutil!??0Vwstring@@QEAA@PEBD@Z` at `0x1800dd94d`
- `onetutil!??0Vwstring@@QEAA@PEBD@Z` at `0x1800dd94d`
- `onetutil!??0Vtime@@QEAA@_K@Z` at `0x1800de05d`
- `onetutil!??0Vtime@@QEAA@_K@Z` at `0x1800df920`
- `onetutil!??0Vtime@@QEAA@_K@Z` at `0x1800de05d`
- `onetutil!??0Vtime@@QEAA@_K@Z` at `0x1800df920`
- `onetutil!?secondsI64@Vtime@@QEBA_KXZ` at `0x1800dda27`
- `onetutil!?secondsI64@Vtime@@QEBA_KXZ` at `0x1800de9e4`
- `onetutil!?secondsI64@Vtime@@QEBA_KXZ` at `0x1800dda27`
- `onetutil!?secondsI64@Vtime@@QEBA_KXZ` at `0x1800de9e4`
- `onetutil!??0Vwstring@@QEAA@AEBVVstring@@@Z` at `0x1800dfbbb`
- `onetutil!??0Vwstring@@QEAA@AEBVVstring@@@Z` at `0x1800dfbbb`
- `onetutil!??YVwstring@@QEAAAEAV0@PEB_W@Z` at `0x1800df97e`
- `onetutil!??YVwstring@@QEAAAEAV0@PEB_W@Z` at `0x1800df98e`
- `onetutil!??YVwstring@@QEAAAEAV0@PEB_W@Z` at `0x1800df97e`
- `onetutil!??YVwstring@@QEAAAEAV0@PEB_W@Z` at `0x1800df98e`
- `onetutil!?getBool@VmetaDict@@QEBADPEBDPEADPEAW4Access@1@@Z` at `0x1800ddec6`
- `onetutil!?getBool@VmetaDict@@QEBADPEBDPEADPEAW4Access@1@@Z` at `0x1800ddec6`
- `onetutil!?setBool@VmetaDict@@QEAADPEBDDW4Access@1@W4OP@Vdict@@@Z` at `0x1800de2a5`
- `onetutil!?setBool@VmetaDict@@QEAADPEBDDW4Access@1@W4OP@Vdict@@@Z` at `0x1800de2a5`
- `onetutil!?getInt@VmetaDict@@QEBADPEBDPEAJPEAW4Access@1@@Z` at `0x1800ddefb`
- `onetutil!?getInt@VmetaDict@@QEBADPEBDPEAJPEAW4Access@1@@Z` at `0x1800ddf31`
- `onetutil!?getInt@VmetaDict@@QEBADPEBDPEAJPEAW4Access@1@@Z` at `0x1800ddefb`
- `onetutil!?getInt@VmetaDict@@QEBADPEBDPEAJPEAW4Access@1@@Z` at `0x1800ddf31`
- `onetutil!??0Vwstring@@QEAA@XZ` at `0x1800dda11`
- `onetutil!??0Vwstring@@QEAA@XZ` at `0x1800dda11`
- `onetutil!?inspect@VstorePathSanityInspector@@SAXPEB_W@Z` at `0x1800df7e1`
- `onetutil!?inspect@VstorePathSanityInspector@@SAXPEB_W@Z` at `0x1800df96a`
- `onetutil!?inspect@VstorePathSanityInspector@@SAXPEB_W@Z` at `0x1800df7e1`
- `onetutil!?inspect@VstorePathSanityInspector@@SAXPEB_W@Z` at `0x1800df96a`
- `onetutil!??0VwstringVvector@@QEAA@I@Z` at `0x1800dfa19`
- `onetutil!??0VwstringVvector@@QEAA@I@Z` at `0x1800dfa19`
- `onetutil!??0Vstring@@QEAA@XZ` at `0x1800df9fa`
- `onetutil!??0Vstring@@QEAA@XZ` at `0x1800df9fa`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800dfabc`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800dfad2`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800dfabc`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800dfad2`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1800dfc30`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1800dff4d`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1800dff5b`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1800dff8b`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1800dfc30`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1800dff4d`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1800dff5b`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1800dff8b`
- `onetutil!??4Vwstring@@QEAAAEAV0@PEB_W@Z` at `0x1800df7d8`
- `onetutil!??4Vwstring@@QEAAAEAV0@PEB_W@Z` at `0x1800df95d`
- `onetutil!??4Vwstring@@QEAAAEAV0@PEB_W@Z` at `0x1800df7d8`
- `onetutil!??4Vwstring@@QEAAAEAV0@PEB_W@Z` at `0x1800df95d`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800de1f7`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800dfda7`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800de1f7`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800dfda7`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x1800de208`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x1800dfdb4`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x1800de208`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x1800dfdb4`
- `onetutil!??0VHRESULT@@QEAA@J@Z` at `0x1800dd8f2`
- `onetutil!??0VHRESULT@@QEAA@J@Z` at `0x1800dd8f2`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800dda9c`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800ddb3a`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800dde1c`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800dde8f`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800de169`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800de406`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800df160`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800df252`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800df2d6`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800df34c`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800df5be`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800df633`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800df683`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800df6eb`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800df748`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800df7b0`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800df838`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800dfaa6`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800dfc25`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800dfcf3`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800dfd77`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800dfe19`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800dfebd`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800dda9c`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800ddb3a`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800dde1c`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800dde8f`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800de169`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800de406`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800df160`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800df252`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800df2d6`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800df34c`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800df5be`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800df633`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800df683`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800df6eb`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800df748`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800df7b0`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800df838`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800dfaa6`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800dfc25`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800dfcf3`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800dfd77`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800dfe19`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800dfebd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800dfd9a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800dfdbc`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800dfd9a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800dfdbc`
- `onetnative!SqmIncrementOne` at `0x1800dfb0f`
- `onetnative!SqmIncrementOne` at `0x1800dfb0f`
- `onetnative!ULSSendTraceTag` at `0x1800ddaef`
- `onetnative!ULSSendTraceTag` at `0x1800de195`
- `onetnative!ULSSendTraceTag` at `0x1800de8f5`
- `onetnative!ULSSendTraceTag` at `0x1800df188`
- `onetnative!ULSSendTraceTag` at `0x1800df5e6`
- `onetnative!ULSSendTraceTag` at `0x1800df86a`
- `onetnative!ULSSendTraceTag` at `0x1800df9e5`
- `onetnative!ULSSendTraceTag` at `0x1800dfb87`
- `onetnative!ULSSendTraceTag` at `0x1800dfd1b`
- `onetnative!ULSSendTraceTag` at `0x1800dfe41`
- `onetnative!ULSSendTraceTag` at `0x1800ddaef`
- `onetnative!ULSSendTraceTag` at `0x1800de195`
- `onetnative!ULSSendTraceTag` at `0x1800de8f5`
- `onetnative!ULSSendTraceTag` at `0x1800df188`
- `onetnative!ULSSendTraceTag` at `0x1800df5e6`
- `onetnative!ULSSendTraceTag` at `0x1800df86a`
- `onetnative!ULSSendTraceTag` at `0x1800df9e5`
- `onetnative!ULSSendTraceTag` at `0x1800dfb87`

## string_xrefs

- `0x1800ddeb8`: `vti_cachedhaspersonalviewmetatag`
- `0x1800ddca3`: `VdocumentStore::storeDocument DF_SUBIMAGE not set, but VPUTDOC_UPDATETHUMBNAILDEPENDENCY sent. (0x%08X)`
- `0x1800de17a`: `VdocumentStore::storeDocument call to PrepareUpdateQuery failed. (0x%08X)`
- `0x1800de413`: `VdocumentStore::storeDocument call to writeBlob failed. (0x%08X)`
- `0x1800df28b`: `VdocumentStore::storeDocument call to GetPreparedUpdateQuery failed. (0x%08X)`
- `0x1800df431`: ` done: IF @iRet=0 BEGIN COMMIT; `
- `0x1800df4b0`: `EXEC proc_UpdateDiskUsed @S, 1;`
- `0x1800df4cd`: `EXEC proc_GetLinkInfoSingleDoc @S,@DN,@LN,@Level;`
- `0x1800df56a`: ` END  ELSE ROLLBACK;  SET ? = @iRet;`
- `0x1800df6f8`: `VdocumentStore::storeDocument handleDocQuery(..., qpLinks, ...) failed. (0x%08X)`

## pseudocode

```c
// Hidden C++ exception states: #wind=54
VHRESULT *__fastcall VdocumentStore::storeDocument(
        VdocumentStore *a1,
        VHRESULT *a2,
        VdbServer *a3,
        int a4,
        const wchar_t **a5,
        const wchar_t **a6,
        _QWORD *a7,
        __int64 a8,
        void *a9,
        __int64 a10,
        _DWORD *a11,
        unsigned __int8 *a12,
        unsigned int a13,
        int a14,
        char a15,
        char a16,
        int a17,
        unsigned __int64 a18,
        int a19,
        char *a20,
        char a21,
        char a22,
        struct Vtime *a23,
        struct Vtime *a24,
        __int64 a25,
        struct VvirusCheck *a26,
        struct VlinkVvector *a27,
        wchar_t **a28,
        unsigned __int8 *a29,
        unsigned int a30,
        unsigned int a31,
        int a32,
        int a33,
        int a34,
        char a35,
        Vstring *a36,
        void *a37,
        struct _GUID *a38,
        int a39,
        char a40,
        unsigned __int64 *a41,
        char *a42,
        int a43,
        const struct _GUID *a44,
        int a45,
        int a46)
{
  unsigned __int64 v48; // rax
  int v49; // eax
  bool v50; // r12
  wchar_t *v51; // rsi
  const struct VurlStorePath *v52; // r13
  const char *v53; // rax
  unsigned __int64 v54; // rax
  __int64 v55; // rax
  VdbServer *v56; // rdi
  char v57; // al
  int v58; // eax
  const wchar_t *v59; // r9
  __int64 v60; // rcx
  wchar_t *v61; // rdi
  struct VdbSubweb *v62; // rsi
  void *v63; // r14
  struct VdoclibManager *DoclibManager; // rax
  __int64 v65; // r9
  bool v66; // di
  unsigned int v67; // eax
  struct VdoclibManager *v68; // rax
  char v69; // di
  char ShouldPromoteToDoclib; // al
  unsigned __int64 v71; // r13
  VKillSwitch *Instance; // rax
  int v73; // ecx
  __int64 v74; // rax
  __int64 v75; // rax
  int *v76; // rax
  int v77; // ecx
  unsigned int v78; // edi
  unsigned int v79; // edi
  __int64 v80; // r12
  char v81; // al
  unsigned __int64 v82; // rdi
  char v83; // cl
  char v84; // al
  char v85; // al
  struct VdoclibManager *v86; // rax
  __int64 updated; // rax
  __int64 v88; // r8
  int v89; // eax
  const wchar_t *v90; // r9
  __int64 v91; // rcx
  unsigned int v92; // r13d
  __int64 v93; // rcx
  __int64 v94; // rcx
  __int64 v95; // rcx
  _QWORD *v96; // rax
  int v97; // eax
  bool v98; // di
  __int64 v99; // rax
  VdbServer *v100; // rdi
  char v101; // al
  const wchar_t *v102; // rdx
  struct VdbSubweb *v103; // rdi
  __int64 v104; // rcx
  __int64 v105; // rax
  __int64 v106; // rax
  unsigned __int16 v107; // r9
  unsigned int v108; // r8d
  unsigned __int8 **v109; // rdx
  unsigned int v110; // edi
  struct Vtime *v111; // rdi
  const char *v112; // rax
  unsigned int v113; // r13d
  VdocHandle *v114; // rdi
  char v115; // di
  const struct _GUID *v116; // rdx
  VdocHandle *v117; // r12
  __int64 v118; // rax
  int v119; // eax
  const wchar_t *v120; // r9
  __int64 v121; // rcx
  unsigned int v122; // edi
  struct VdoclibManager *v123; // rax
  __int64 PreparedUpdateQuery; // rax
  __int64 v125; // rax
  __int64 v126; // rax
  unsigned int v127; // eax
  __int64 v128; // rcx
  __int64 v129; // rax
  __int64 v130; // rax
  __int64 v131; // rax
  __int64 v132; // rax
  int v133; // ecx
  unsigned int v134; // eax
  __int64 v135; // rax
  VHRESULT *v136; // rax
  __int64 v137; // rax
  __int64 v138; // rax
  __int64 v139; // rax
  __int64 OutputParam; // rax
  __int64 v141; // rax
  VHRESULT *v142; // rax
  __int64 v143; // rax
  VHRESULT *v144; // rax
  VHRESULT *v145; // rax
  struct Vtime *v146; // rcx
  __int64 v147; // rdi
  const char *v148; // rax
  __int64 v149; // rsi
  unsigned int v150; // r13d
  __int64 v151; // rcx
  __int64 v152; // rdi
  int v153; // eax
  char v154; // di
  __int64 v155; // rax
  int v156; // eax
  const wchar_t *v157; // r9
  __int64 v158; // rcx
  __int64 v159; // rax
  void *v160; // rdi
  VHRESULT *v161; // rax
  __int64 v162; // rax
  _QWORD *v163; // rdi
  VHRESULT *v164; // rax
  __int64 v165; // rax
  VHRESULT *v166; // rax
  VHRESULT *v167; // rax
  wchar_t **v169; // [rsp+28h] [rbp-120h]
  wchar_t **v170; // [rsp+28h] [rbp-120h]
  wchar_t **v171; // [rsp+28h] [rbp-120h]
  wchar_t **v172; // [rsp+28h] [rbp-120h]
  wchar_t **v173; // [rsp+28h] [rbp-120h]
  int v174; // [rsp+28h] [rbp-120h]
  char pszb; // [rsp+30h] [rbp-118h]
  int psz; // [rsp+30h] [rbp-118h]
  OLECHAR *pszc; // [rsp+30h] [rbp-118h]
  OLECHAR *psza; // [rsp+30h] [rbp-118h]
  char v179[8]; // [rsp+38h] [rbp-110h]
  int v180; // [rsp+60h] [rbp-E8h]
  char v181[8]; // [rsp+C8h] [rbp-80h] BYREF
  char v182; // [rsp+D0h] [rbp-78h]
  bool v183[8]; // [rsp+D8h] [rbp-70h] BYREF
  unsigned int v184; // [rsp+E0h] [rbp-68h]
  VmetaDict *v185; // [rsp+E8h] [rbp-60h] BYREF
  char v186[8]; // [rsp+F0h] [rbp-58h] BYREF
  void *v187; // [rsp+F8h] [rbp-50h]
  char v188; // [rsp+100h] [rbp-48h] BYREF
  bool v189; // [rsp+101h] [rbp-47h]
  char v190; // [rsp+102h] [rbp-46h]
  int v191; // [rsp+104h] [rbp-44h]
  __int64 v192; // [rsp+108h] [rbp-40h] BYREF
  struct VdbSubweb *v193; // [rsp+110h] [rbp-38h]
  unsigned int v194; // [rsp+118h] [rbp-30h]
  __int64 v195; // [rsp+120h] [rbp-28h]
  unsigned __int64 v196; // [rsp+128h] [rbp-20h]
  wchar_t v197; // [rsp+130h] [rbp-18h] BYREF
  unsigned int v198; // [rsp+138h] [rbp-10h] BYREF
  int v199; // [rsp+140h] [rbp-8h] BYREF
  VdbServer *v200; // [rsp+148h] [rbp+0h]
  int v201; // [rsp+150h] [rbp+8h]
  VdocHandle *v202; // [rsp+158h] [rbp+10h]
  const wchar_t **v203; // [rsp+160h] [rbp+18h] BYREF
  char *v204; // [rsp+168h] [rbp+20h] BYREF
  struct _GUID *v205; // [rsp+170h] [rbp+28h]
  int v206; // [rsp+178h] [rbp+30h]
  unsigned int v207; // [rsp+17Ch] [rbp+34h] BYREF
  unsigned int v208; // [rsp+180h] [rbp+38h]
  __int64 v209; // [rsp+188h] [rbp+40h] BYREF
  unsigned int v210; // [rsp+190h] [rbp+48h] BYREF
  unsigned int v211; // [rsp+194h] [rbp+4Ch]
  int v212; // [rsp+198h] [rbp+50h]
  int v213; // [rsp+19Ch] [rbp+54h]
  int v214; // [rsp+1A0h] [rbp+58h] BYREF
  unsigned int v215; // [rsp+1A4h] [rbp+5Ch]
  int v216; // [rsp+1A8h] [rbp+60h]
  unsigned __int8 *v217; // [rsp+1B0h] [rbp+68h] BYREF
  __int64 v218; // [rsp+1B8h] [rbp+70h]
  struct _GUID *v219; // [rsp+1C0h] [rbp+78h]
  __int64 v220; // [rsp+1C8h] [rbp+80h] BYREF
  VdocumentStore *v221; // [rsp+1D0h] [rbp+88h]
  _QWORD *v222; // [rsp+1D8h] [rbp+90h] BYREF
  void *Block; // [rsp+1E0h] [rbp+98h] BYREF
  _QWORD v224[2]; // [rsp+1E8h] [rbp+A0h] BYREF
  struct VlinkVvector *v225; // [rsp+1F8h] [rbp+B0h] BYREF
  char v226; // [rsp+200h] [rbp+B8h]
  int v227; // [rsp+218h] [rbp+D0h] BYREF
  __int64 v228; // [rsp+220h] [rbp+D8h]
  struct Vtime *v229; // [rsp+228h] [rbp+E0h]
  _QWORD *v230; // [rsp+230h] [rbp+E8h]
  unsigned __int64 *v231; // [rsp+238h] [rbp+F0h]
  char *v232; // [rsp+240h] [rbp+F8h]
  OLECHAR *v233; // [rsp+248h] [rbp+100h] BYREF
  int v234; // [rsp+250h] [rbp+108h] BYREF
  unsigned __int64 v235; // [rsp+258h] [rbp+110h] BYREF
  _BYTE v236[16]; // [rsp+260h] [rbp+118h] BYREF
  _DWORD *v237; // [rsp+270h] [rbp+128h]
  const wchar_t **v238; // [rsp+278h] [rbp+130h]
  void *v239; // [rsp+280h] [rbp+138h]
  struct Vtime *v240; // [rsp+288h] [rbp+140h]
  char *v241; // [rsp+290h] [rbp+148h] BYREF
  double v242; // [rsp+298h] [rbp+150h] BYREF
  int v243[2]; // [rsp+2A0h] [rbp+158h]
  char v244[8]; // [rsp+2A8h] [rbp+160h] BYREF
  void **v245; // [rsp+2B0h] [rbp+168h] BYREF
  VdbServer *v246; // [rsp+2B8h] [rbp+170h]
  bool v247; // [rsp+2C0h] [rbp+178h]
  _QWORD v248[4]; // [rsp+2C8h] [rbp+180h] BYREF
  char *v249; // [rsp+2E8h] [rbp+1A0h]
  const wchar_t *v250; // [rsp+2F0h] [rbp+1A8h]
  const wchar_t *v251; // [rsp+2F8h] [rbp+1B0h]
  const wchar_t *v252; // [rsp+300h] [rbp+1B8h]
  char v253; // [rsp+318h] [rbp+1D0h]
  bool v254; // [rsp+319h] [rbp+1D1h]
  int v255; // [rsp+320h] [rbp+1D8h]
  char v256; // [rsp+324h] [rbp+1DCh]
  _BYTE *v257; // [rsp+328h] [rbp+1E0h]
  int v258; // [rsp+338h] [rbp+1F0h]
  int v259; // [rsp+33Ch] [rbp+1F4h]
  const wchar_t *v260; // [rsp+340h] [rbp+1F8h]
  char v261; // [rsp+348h] [rbp+200h]
  char *v262; // [rsp+350h] [rbp+208h]
  char v263; // [rsp+35Bh] [rbp+213h]
  char v264; // [rsp+35Ch] [rbp+214h]
  char v265; // [rsp+35Dh] [rbp+215h]
  char v266; // [rsp+35Eh] [rbp+216h]
  char v267; // [rsp+35Fh] [rbp+217h]
  char v268; // [rsp+365h] [rbp+21Dh]
  char v269; // [rsp+366h] [rbp+21Eh]
  unsigned __int8 *v270; // [rsp+378h] [rbp+230h]
  wchar_t **v271[2]; // [rsp+380h] [rbp+238h] BYREF
  Vstring *v272; // [rsp+390h] [rbp+248h]
  unsigned __int64 v273; // [rsp+398h] [rbp+250h] BYREF
  struct VvirusCheck *v274; // [rsp+3A0h] [rbp+258h]
  _BYTE v275[16]; // [rsp+3A8h] [rbp+260h] BYREF
  void *v276; // [rsp+3B8h] [rbp+270h]
  const struct _GUID *v277; // [rsp+3C0h] [rbp+278h]
  _BYTE v278[40]; // [rsp+3C8h] [rbp+280h] BYREF
  VHRESULT *v279; // [rsp+3F0h] [rbp+2A8h]
  __int64 v280; // [rsp+3F8h] [rbp+2B0h]
  struct _GUID v281; // [rsp+400h] [rbp+2B8h] BYREF
  _BYTE v282[24]; // [rsp+410h] [rbp+2C8h] BYREF
  _BYTE v283[16]; // [rsp+428h] [rbp+2E0h] BYREF
  VsqlClient *v284; // [rsp+438h] [rbp+2F0h]
  int v285[8]; // [rsp+878h] [rbp+730h] BYREF
  __int128 v286; // [rsp+898h] [rbp+750h]
  struct _GUID v287; // [rsp+8A8h] [rbp+760h]
  unsigned int v288; // [rsp+8B8h] [rbp+770h]
  char v289; // [rsp+8BCh] [rbp+774h]
  unsigned int v290; // [rsp+980h] [rbp+838h]

  v280 = -2;
  v200 = a3;
  v221 = a1;
  v279 = a2;
  v203 = a5;
  v238 = a6;
  v230 = a7;
  *(_QWORD *)v243 = a8;
  v187 = a9;
  v218 = a10;
  v237 = a11;
  v217 = a12;
  v196 = a18;
  v204 = a20;
  v240 = a23;
  v229 = a24;
  v202 = (VdocHandle *)a25;
  v274 = a26;
  v225 = a27;
  v271[0] = a28;
  v270 = a29;
  v198 = a31;
  v272 = a36;
  v276 = a37;
  v205 = a38;
  v216 = a39;
  v231 = a41;
  v232 = a42;
  v277 = a44;
  v194 = 0;
  VmonitoredScope::VmonitoredScope(
    (VmonitoredScope *)v275,
    0x215797u,
    0x6FB7043u,
    0x32u,
    L"VdocumentStore::storeDocument");
  v209 = -1;
  v193 = *(struct VdbSubweb **)(a25 + 144);
  v48 = a18 >> 34;
  LOBYTE(v48) = (a18 & 0x400000000LL) != 0;
  v235 = v48;
  Voledb::Voledb((Voledb *)v283, v221, 1);
  v189 = *((_QWORD *)v193 + 57) == 0;
  v49 = *(_DWORD *)(a25 + 3080) >> 8;
  LOBYTE(v49) = BYTE1(*(_DWORD *)(a25 + 3080)) & 1;
  v213 = v49;
  v181[0] = a30 != 0;
  CWebLocker::CWebLocker((CWebLocker *)v278, v193);
  v219 = 0;
  v192 = 0;
  v182 = 0;
  v184 = -1;
  VHRESULT::VHRESULT(a2, 0);
  v194 = 1;
  v50 = 0;
  v206 = 0;
  v195 = 0;
  v51 = 0;
  LODWORD(v228) = 0;
  LOBYTE(v199) = 0;
  v215 = 0;
  LOBYTE(v201) = 0;
  LOBYTE(v212) = 0;
  LOBYTE(v191) = 1;
  sub_1800F7DE0(v285, v221);
  v52 = (const struct VurlStorePath *)(a25 + 152);
  v53 = Vstring::data((Vstring *)(a25 + 152));
  Vwstring::Vwstring((Vwstring *)&v233, v53);
  VdoclibUpdateParams::VdoclibUpdateParams((VdoclibUpdateParams *)v248);
  v222 = 0;
  v249 = 0;
  Block = 0;
  v207 = -1;
  v245 = &VWnsSubscriptionProcessor::`vftable';
  v246 = v200;
  v247 = 0;
  v190 = 0;
  v241 = 0;
  v214 = 0;
  v186[0] = 0;
  v197 = 0;
  v185 = (VmetaDict *)(a25 + 168);
  v211 = *(_DWORD *)(a25 + 376);
  v239 = *(void **)(a25 + 368);
  if ( !v239 || *(_QWORD *)(v218 + 24) && !*((_BYTE *)v202 + 380) )
  {
    v239 = 0;
    v211 = 0;
  }
  Vwstring::Vwstring((Vwstring *)v244, *a6);
  Vwstring::Vwstring(&v220);
  if ( a22 )
  {
    v54 = Vtime::secondsI64(v229);
    OWSOleDateFromTimeT(v54, &v242);
  }
  pszb = VdbServer::allowPoundPercentInPath(v200);
  v55 = VdocumentStore::validateUrlForStore(v236, (char *)v200 + 200, v203, a6, v230, pszb, &v197, 1);
  VHRESULT::operator=(a2, v55);
  VHRESULT::~VHRESULT((VHRESULT *)v236);
  v56 = v200;
  v57 = VdbServer::allowPoundPercentInPath(v200);
  VdocumentStore::LogPoundPercentFileFolderCreation((const struct _GUID *)((char *)v56 + 532), v57, &v197, 1, v52);
  v58 = *(_DWORD *)a2;
  if ( *(int *)a2 < 0 )
  {
    v59 = L"VdocumentStore::storeDocument validateUrlForStore failed. (0x%08X)";
    v60 = 20018563;
LABEL_9:
    LODWORD(v169) = v58;
    ULSSendTraceTag(v60, 117141571, 50, v59, v169);
    v61 = 0;
LABEL_10:
    v62 = v193;
    v63 = v187;
LABEL_100:
    v92 = v184;
    goto LABEL_101;
  }
  DoclibManager = VdbSubweb::getDoclibManager(v193);
  LOBYTE(v65) = 1;
  v66 = *(_DWORD *)VdoclibManager::GetContainingList(DoclibManager, v236, v52, v65, &v192) == 0;
  VHRESULT::~VHRESULT((VHRESULT *)v236);
  if ( !v66 )
  {
    LOWORD(v71) = v196;
    goto LABEL_43;
  }
  v67 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v192 + 160LL))(v192, v282);
  if ( *(int *)VHRESULT::operator=(a2, v67) < 0 )
  {
    v58 = *(_DWORD *)a2;
    v59 = L"VdocumentStore::storeDocument get_ListID failed. (0x%08X)";
    v60 = 20018564;
    goto LABEL_9;
  }
  v219 = (struct _GUID *)v282;
  v68 = VdbSubweb::getDoclibManager(v193);
  v69 = 1;
  LOBYTE(v169) = 1;
  ShouldPromoteToDoclib = VdoclibManager::ShouldPromoteToDoclib(v68, v52, v185, v196, (_DWORD)v169, 0, 2);
  v182 = ShouldPromoteToDoclib;
  if ( ShouldPromoteToDoclib || (a14 & 2) != 0 )
  {
    v71 = v196;
    if ( v192 && (v196 & 0x80000) == 0 )
    {
      Instance = VKillSwitch::getInstance();
      if ( Instance && VKillSwitch::findKey(Instance, &stru_1802354C8) )
      {
        v69 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v192 + 568LL))(v192);
      }
      else if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v192 + 568LL))(v192)
             && (v71 & 0x10000000000LL) == 0 )
      {
        v69 = 0;
      }
      v201 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v192 + 584LL))(v192);
      v212 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v192 + 480LL))(v192);
      if ( (v71 & 0x40000000) != 0 )
      {
        if ( (a14 & 2) == 0 )
        {
          VHRESULT::operator=(a2, 2147500037LL);
          v58 = *(_DWORD *)a2;
          v59 = L"VdocumentStore::storeDocument DF_SUBIMAGE not set, but VPUTDOC_UPDATETHUMBNAILDEPENDENCY sent. (0x%08X)";
          v60 = 20018565;
          goto LABEL_9;
        }
        v69 = 1;
        if ( (v71 & 0x10000) != 0 )
        {
          LOBYTE(v191) = 1;
LABEL_44:
          ShouldPromoteToDoclib = v182;
          goto LABEL_45;
        }
        LOBYTE(v73) = (v71 & 0x20) != 0 ? 2 : -1;
LABEL_30:
        v191 = v73;
        goto LABEL_44;
      }
      if ( !v69 || (v71 & 0x2000) != 0 || (v71 & 0x20) != 0 && (a14 & 2) != 0 )
      {
        v69 = 1;
        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v192 + 480LL))(v192) != 1 && !(_BYTE)v201 )
          goto LABEL_44;
        v73 = (unsigned __int8)v191;
        if ( (v71 & 0x12000) != 0x12000 )
          v73 = 2;
        goto LABEL_30;
      }
      LOBYTE(v191) = -1;
LABEL_43:
      v69 = 1;
      goto LABEL_44;
    }
  }
  else
  {
    LOWORD(v71) = v196;
  }
LABEL_45:
  if ( (_BYTE)v213 )
  {
    if ( ShouldPromoteToDoclib )
    {
      v199 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _BYTE *, _BYTE *))(*(_QWORD *)v192 + 496LL))(
               v192,
               v236,
               v236,
               v236);
      if ( (_BYTE)v199 )
      {
        v228 = 401;
        v195 = sub_180001258(saturated_mul(0x191u, 2u));
      }
    }
  }
  if ( a16 )
  {
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v192 + 480LL))(v192) )
    {
      v74 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v192 + 488LL))(v192);
      v50 = *(_DWORD *)VsecurableObject::assertPermissionMask(v74, v224, 2048, 50) >= 0;
      VHRESULT::~VHRESULT((VHRESULT *)v224);
    }
    if ( (v71 & 0x800) != 0 )
    {
      v77 = v194;
      goto LABEL_59;
    }
    if ( (v71 & 0x2000) != 0 )
    {
      v75 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v192 + 488LL))(v192);
      v76 = (int *)VsecurableObject::assertPermissionMask(v75, v224, 2048, 50);
      v77 = 3;
      v194 = 3;
      if ( *v76 >= 0 )
      {
LABEL_59:
        if ( (v77 & 2) != 0 )
        {
          v194 = v77 & 0xFFFFFFFD;
          VHRESULT::~VHRESULT((VHRESULT *)v224);
        }
        if ( v69 )
          v206 = 1;
        else
          v206 = 3 - v50;
        goto LABEL_64;
      }
    }
    else
    {
      v77 = v194;
    }
    v69 = 0;
    goto LABEL_59;
  }
LABEL_64:
  v188 = 0;
  VmetaDict::getBool(v185, "vti_cachedhaspersonalviewmetatag", &v188, 0);
  if ( v188 )
    v78 = a14 | 0x80;
  else
    v78 = a14 & 0xFFFFFF7F;
  v290 = v78;
  if ( VmetaDict::getInt(v185, "vti_irm_IrmEnabled", &v227, 0) )
  {
    if ( v227 )
      v78 |= 0x400000u;
    else
      v78 &= ~0x400000u;
    v290 = v78;
  }
  if ( VmetaDict::getInt(v185, "vti_irm_dlp_IrmEnabled", &v234, 0) )
  {
    if ( v234 )
      v79 = v78 | 0x800000;
    else
      v79 = v78 & 0xFF7FFFFF;
    v290 = v79;
  }
  v80 = 0;
  v224[0] = 0;
  if ( v182 )
  {
    v248[0] = (char *)v202 + 152;
    v248[1] = *v203;
    v248[2] = *v238;
    v248[3] = (char *)v202 + 168;
    v249 = (char *)v202 + 168;
    v250 = L"@DoclibRowId";
    v251 = L"@DocUIVersion";
    v252 = L"@iRet";
    v253 = 1;
    v254 = (*((_DWORD *)v202 + 770) & 0x40) != 0;
    v255 = 1;
    v257 = v283;
    v258 = a32;
    v259 = a33;
    v260 = L"@Level";
    v261 = v191;
    v267 = 0;
    v262 = v204;
    if ( a21 || (Vtime::Vtime((Vtime *)&v281, 0), v81 = 0, *(_QWORD *)v240 > *(_QWORD *)&v281.Data1) )
      v81 = 1;
    v269 = v81;
    v268 = a22;
    v82 = v196 & 0x200000;
    v83 = v264;
    if ( (v196 & 0x200000) != 0 )
      v83 = 1;
    v264 = v83;
    v84 = v266;
    if ( (v196 & 0x10000000) != 0 )
      v84 = 1;
    v266 = v84;
    v85 = v83;
    if ( *((_BYTE *)v202 + 3084) )
      v85 = 1;
    v264 = v85;
    if ( (v196 & 0x2000) != 0 )
    {
      v256 = 1;
      if ( (v196 & 0x10000) != 0 )
        v80 = 0x10000;
      v80 |= 0x2000uLL;
      v224[0] = v80;
    }
    if ( (v196 & 0x80000) != 0 )
    {
      v80 |= 0x80200uLL;
      v224[0] = v80;
    }
    if ( (v196 & 0x10000) != 0 )
    {
      v80 |= 0x10000uLL;
      v224[0] = v80;
    }
    v86 = VdbSubweb::getDoclibManager(*((VdbSubweb **)v202 + 18));
    updated = VdoclibManager::PrepareUpdateQuery(v86, &v281, v248, v80, 0);
    VHRESULT::operator=(a2, updated);
    VHRESULT::~VHRESULT((VHRESULT *)&v281);
    v89 = *(_DWORD *)a2;
    if ( *(int *)a2 < 0 )
    {
      v90 = L"VdocumentStore::storeDocument call to PrepareUpdateQuery failed. (0x%08X)";
      v91 = 20018566;
LABEL_97:
      LODWORD(v171) = v89;
      ULSSendTraceTag(v91, 117141571, 50, v90, v171);
LABEL_98:
      v62 = v193;
      v63 = v187;
      goto LABEL_99;
    }
    if ( (_BYTE)v191 != 0xFF && (v82 && v263 || v266 && v265) )
    {
      LOBYTE(v191) = -1;
      v261 = -1;
      v95 = *(_QWORD *)(v218 + 24);
      if ( v95 )
      {
        (*(void (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v95 + 24LL))(v95, &v222);
        v96 = v222;
      }
      else
      {
        v96 = 0;
      }
      if ( !v96 )
        v290 |= 0x8000u;
    }
    if ( v264 && v263 )
    {
      LOBYTE(v88) = 1;
      VmetaDict::setBool(v185, "vti_ignoredreqprops", v88, 1, 0);
    }
    v222 = v248;
  }
  v97 = 0;
  v98 = v191;
  if ( (_BYTE)v191 == 0xFF )
    v97 = 0x10000;
  v208 = v97;
  if ( v182 )
  {
    v286 = *(_OWORD *)((char *)v200 + 184);
    v287 = *v219;
    v288 = v198;
    v289 = 1;
  }
  v99 = sub_180028A08(
          v285,
          &v281,
          v283,
          *(_QWORD *)(*((_QWORD *)v202 + 18) + 56LL) + 184LL,
          *(_QWORD *)v243,
          v187,
          v233,
          v196,
          (_BYTE)v191,
          0,
          0,
          100,
          -1,
          0,
          v218,
          a4,
          v231,
          v232,
          &v209,
          &Block,
          &v207,
          v186,
          v200);
  VHRESULT::operator=(a2, v99);
  VHRESULT::~VHRESULT((VHRESULT *)&v281);
  v89 = *(_DWORD *)a2;
  if ( *(int *)a2 < 0 )
  {
    v90 = L"VdocumentStore::storeDocument call to writeBlob failed. (0x%08X)";
    v91 = 20018567;
    goto LABEL_97;
  }
  Voledb::AppendQuery(
    (Voledb *)v283,
    L"DECLARE @S uniqueidentifier; DECLARE @DocId uniqueidentifier; DECLARE @Level tinyint; DECLARE @DocUIVersion int; DEC"
     "LARE @DN nvarchar(400); DECLARE @LN nvarchar(400); DECLARE @FU nvarchar(400); SET @Level=?;");
  v183[0] = v98;
  Voledb::BindInputParam((Voledb *)v283, v183, 1u, 0x11u, 1);
  if ( !v182 )
    Voledb::AppendQuery((Voledb *)v283, L"DECLARE @DoclibRowId int; ");
  Voledb::AppendQuery((Voledb *)v283, L" SET @DocUIVersion =?;");
  if ( v98 || !(_BYTE)v201 )
  {
    LODWORD(v185) = 512;
    Voledb::BindInputParam((Voledb *)v283, &v185, 4u, 3u, 1);
    *v237 = 512;
  }
  else
  {
    LODWORD(v185) = 1;
    Voledb::BindInputParam((Voledb *)v283, &v185, 4u, 3u, 1);
    *v237 = 1;
  }
  Voledb::AppendQuery((Voledb *)v283, L" SET @DocId=?;");
  Voledb::BindInputParam((Voledb *)v283, v187, 0x10u, 0x48u, 1);
  Voledb::AppendQuery((Voledb *)v283, L" SET @S=?;");
  v100 = v200;
  Voledb::BindInputParam((Voledb *)v283, (char *)v200 + 184, 0x10u, 0x48u, 1);
  Voledb::AppendQuery((Voledb *)v283, L" SET @DN=?;");
  Voledb::BindInputParam((Voledb *)v283, *v203);
  Voledb::AppendQuery((Voledb *)v283, L" SET @LN=?;");
  Voledb::BindInputParam((Voledb *)v283, *v238);
  Voledb::AppendQuery((Voledb *)v283, L" EXEC @iRet = ");
  v101 = VdbServer::databaseSupports64BitDocSizes(v100);
  v102 = L"proc_AddDocument2 ";
  if ( !v101 )
    v102 = L"proc_AddDocument ";
  Voledb::AppendQuery((Voledb *)v283, v102);
  Voledb::AppendQuery((Voledb *)v283, L"@S, ?, ?, ?, ?");
  v103 = v193;
  Voledb::BindInputParam((Voledb *)v283, (char *)v193 + 264, 0x10u, 0x48u, 1);
  v104 = *((_QWORD *)v103 + 8);
  if ( v104 )
    v105 = *(_QWORD *)(v104 + 88);
  else
    v105 = 0;
  if ( *(_QWORD *)(*(_QWORD *)(v105 + 48) + 48LL) )
  {
    if ( v104 )
      v106 = *(_QWORD *)(v104 + 88);
    else
      v106 = 0;
    LODWORD(v185) = **(_DWORD **)(v106 + 48);
    Voledb::BindInputParam((Voledb *)v283, &v185, 4u, 3u, 1);
  }
  else
  {
    VsqlClient::PlaceholderBindInputNULL(v284, 3u, 0);
  }
  VsecurityUtil::BindAppPrincipalIdInputParam((struct Voledb *)v283, v103);
  if ( v182 && a32 )
  {
    LODWORD(v185) = a32;
    Voledb::BindInputParam((Voledb *)v283, &v185, 4u, 3u, 1);
  }
  else
  {
    VsqlClient::PlaceholderBindInputNULL(v284, 3u, 0);
  }
  Voledb::AppendQuery((Voledb *)v283, L", @DN, @LN OUTPUT, @Level, ");
  if ( a45 && a45 / 512 >= 0 && a45 % 512 >= 0 )
  {
    Voledb::AppendQuery((Voledb *)v283, L"?");
    LODWORD(v185) = a45;
    Voledb::BindInputParam((Voledb *)v283, &v185, 4u, 3u, 1);
  }
  else
  {
    Voledb::AppendQuery((Voledb *)v283, L"@DocUIVersion");
  }
  Voledb::AppendQuery((Voledb *)v283, L", @DocId, ?, @DoclibRowId");
  Voledb::BindInputParam((Voledb *)v283, v219, 0x10u, 0x48u, 1);
  Voledb::AppendQuery((Voledb *)v283, L", ?, ?, ?, ?, ?, ?");
  v183[0] = *(_QWORD *)(v218 + 24) != 0;
  Voledb::BindInputParam((Voledb *)v283, v183, 1u, 0xBu, 1);
  v210 = a13;
  Voledb::BindCompressedInputBytesParam((Voledb *)v283, v217, a13, &v210);
  if ( VdbServer::databaseSupports64BitDocSizes(v200) )
  {
    v217 = (unsigned __int8 *)v209;
    v107 = 20;
    v108 = 8;
    v109 = &v217;
  }
  else
  {
    LODWORD(v185) = v209;
    v107 = 3;
    v108 = 4;
    v109 = (unsigned __int8 **)&v185;
  }
  Voledb::BindInputParam((Voledb *)v283, v109, v108, v107, 1);
  LODWORD(v185) = v210;
  Voledb::BindInputParam((Voledb *)v283, &v185, 4u, 0x13u, 1);
  if ( v239 && (v110 = v211) != 0 )
  {
    Voledb::BindInputParam((Voledb *)v283, v239, v211, 0x80u, 0);
    LODWORD(v185) = v110;
    Voledb::BindInputParam((Voledb *)v283, &v185, 4u, 0x13u, 1);
    if ( v110 > 0xFB40 )
    {
      LODWORD(v172) = v110;
      ULSSendTraceTag(1681419114, 117141571, 50, L"Saving FFM with size %i for file %s.", v172, *v230);
    }
  }
  else
  {
    VsqlClient::PlaceholderBindInputNULL(v284, 0x80u, 0);
    LODWORD(v185) = 0;
    Voledb::BindInputParam((Voledb *)v283, &v185, 4u, 0x13u, 1);
  }
  Voledb::AppendQuery((Voledb *)v283, L", ?, ?, ?, ?, ?, ?");
  v183[0] = v201;
  Voledb::BindInputParam((Voledb *)v283, v183, 1u, 0xBu, 1);
  v183[0] = v212;
  Voledb::BindInputParam((Voledb *)v283, v183, 1u, 0xBu, 1);
  Voledb::BindInputParam((Voledb *)v283, v181, 1u, 0xBu, 1);
  LODWORD(v185) = v290;
  Voledb::BindInputParam((Voledb *)v283, &v185, 4u, 0x13u, 1);
  if ( a21 && (v111 = v240, Vtime::secondsI64(v240)) )
    Voledb::BindInputParam((Voledb *)v283, v111);
  else
    VsqlClient::PlaceholderBindInputNULL(v284, 7u, 0);
  if ( a22 )
    Voledb::BindInputParam((Voledb *)v283, v229);
  else
    VsqlClient::PlaceholderBindInputNULL(v284, 7u, 0);
  Voledb::AppendQuery((Voledb *)v283, L", ?, ?, ?, ?, ?, ?, ?, ?");
  v181[0] = v189;
  Voledb::BindInputParam((Voledb *)v283, v181, 1u, 0xBu, 1);
  v217 = (unsigned __int8 *)v196;
  Voledb::BindInputParam((Voledb *)v283, &v217, 8u, 0x14u, 1);
  v181[0] = a15;
  Voledb::BindInputParam((Voledb *)v283, v181, 1u, 0xBu, 1);
  v181[0] = v213;
  Voledb::BindInputParam((Voledb *)v283, v181, 1u, 0xBu, 1);
  if ( a17 == 2 )
  {
    VsqlClient::PlaceholderBindInputNULL(v284, 0xBu, 0);
  }
  else
  {
    v181[0] = a17 == 0;
    Voledb::BindInputParam((Voledb *)v283, v181, 1u, 0xBu, 1);
  }
  LODWORD(v185) = a19;
  Voledb::BindInputParam((Voledb *)v283, &v185, 4u, 3u, 1);
  if ( v204 && *v204 )
    Voledb::BindInputParam((Voledb *)v283, v204);
  else
    VsqlClient::PlaceholderBindInputNULL(v284, 0x82u, 0);
  LODWORD(v185) = v206;
  Voledb::BindInputParam((Voledb *)v283, &v185, 4u, 3u, 1);
  Voledb::AppendQuery((Voledb *)v283, L", ?, ?, ?, ?");
  VvirusCheck::appendQueryParameters(v274, (struct Voledb *)v283, 1, 1, 1);
  Voledb::AppendQuery((Voledb *)v283, L", ?, ?");
  if ( a34 >= 0 )
  {
    LODWORD(v185) = a34;
    Voledb::BindInputParam((Voledb *)v283, &v185, 4u, 3u, 1);
    v181[0] = a35;
    Voledb::BindInputParam((Voledb *)v283, v181, 1u, 0xBu, 1);
    v208 |= 0x10000u;
  }
  else
  {
    VsqlClient::PlaceholderBindInputNULL(v284, 3u, 0);
    v181[0] = 0;
    Voledb::BindInputParam((Voledb *)v283, v181, 1u, 0xBu, 1);
  }
  Voledb::AppendQuery((Voledb *)v283, L", ?, ? OUTPUT, ?, ?, ?, ?, ?, ? OUTPUT");
  if ( *(_DWORD *)(*(_QWORD *)v272 - 4LL) )
  {
    v112 = Vstring::data(v272);
    Voledb::BindInputParam((Voledb *)v283, v112);
  }
  else
  {
    VsqlClient::PlaceholderBindInputNULL(v284, 0x82u, 0);
  }
  v113 = VsqlClient::PlaceholderBindOutput(v284, 7u, 8);
  v181[0] = v235;
  Voledb::BindInputParam((Voledb *)v283, v181, 1u, 0xBu, 1);
  LODWORD(v185) = v216;
  Voledb::BindInputParam((Voledb *)v283, &v185, 4u, 0x13u, 1);
  v235 = *v231;
  Voledb::BindInputParam((Voledb *)v283, &v235, 8u, 0x14u, 1);
  v181[0] = *v232;
  Voledb::BindInputParam((Voledb *)v283, v181, 1u, 0x11u, 1);
  if ( v276 )
    Voledb::BindInputParam((Voledb *)v283, v276, 0x10u, 0x80u, 0);
  else
    VsqlClient::PlaceholderBindInputNULL(v284, 0x80u, 0);
  Voledb::BindRequestGuid((Voledb *)v283);
  v114 = v202;
  if ( VdbServer::sprocsSchemaVersionGreaterThanOrEqualTo(*(VdbServer **)(*((_QWORD *)v202 + 18) + 56LL), 16, 0, 11, 0) )
  {
    Voledb::AppendQuery((Voledb *)v283, L", ?");
    if ( v207 == -1 )
      VsqlClient::PlaceholderBindInputNULL(v284, 0x80u, 0);
    else
      Voledb::BindInputParam((Voledb *)v283, Block, v207, 0x80u, 1);
  }
  if ( VdbServer::sprocsSchemaVersionGreaterThanOrEqualTo(*(VdbServer **)(*((_QWORD *)v114 + 18) + 56LL), 16, 0, 49, 0) )
  {
    Voledb::AppendQuery((Voledb *)v283, L", ?");
    LODWORD(v185) = a43;
    Voledb::BindInputParam((Voledb *)v283, &v185, 4u, 3u, 1);
  }
  if ( VdbServer::sprocsSchemaVersionGreaterThanOrEqualTo(*(VdbServer **)(*((_QWORD *)v114 + 18) + 56LL), 16, 0, 67, 0) )
  {
    Voledb::AppendQuery((Voledb *)v283, L", ?");
    v181[0] = a40;
    Voledb::BindInputParam((Voledb *)v283, v181, 1u, 0xBu, 1);
  }
  if ( VdbServer::databaseSupportsOriginatorId(*(VdbServer **)(*((_QWORD *)v114 + 18) + 56LL)) )
  {
    Voledb::AppendQuery((Voledb *)v283, L", ?");
    if ( v186[0]
      || !*(_QWORD *)(v218 + 24)
      || (v115 = 1, v207 == -1)
      && (unsigned __int8)sub_1800DD67C()
      && (VdocHandle::isOneNote(v202) || VdocHandle::isWBX(v202)) )
    {
      v115 = 0;
    }
    if ( !v277 || (v116 = v277 + 16, v115) )
      v116 = &stru_18020E740;
    Voledb::BindInputParam((Voledb *)v283, v116, 0x10u, 0x48u, 1);
    v114 = v202;
  }
  if ( VdbServer::databaseSchemaVersionGreaterThanOrEqualTo(
         *(VdbServer **)(*((_QWORD *)v114 + 18) + 56LL),
         16,
         0,
         93,
         0) )
  {
    if ( (*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v114 + 18) + 56LL) + 704LL) & 0x8000LL) != 0
      && v192
      && (v196 & 0x2000) == 0 )
    {
      (*(void (__fastcall **)(__int64, int *, char **))(*(_QWORD *)v192 + 776LL))(v192, &v214, &v241);
    }
    Voledb::AppendQuery((Voledb *)v283, L", ?, ?");
    if ( v241 && *v241 )
      Voledb::BindInputParam((Voledb *)v283, v241);
    else
      VsqlClient::PlaceholderBindInputNULL(v284, 0x82u, 0);
    if ( v214 )
    {
      LODWORD(v185) = v214;
      Voledb::BindInputParam((Voledb *)v283, &v185, 4u, 3u, 1);
    }
    else
    {
      VsqlClient::PlaceholderBindInputNULL(v284, 3u, 0);
    }
  }
  Voledb::AppendQuery((Voledb *)v283, L"; SET @FU = dbo.fn_GetFullUrl(@DN, @LN);");
  v61 = (wchar_t *)v195;
  if ( v195 )
  {
    Voledb::AppendQuery((Voledb *)v283, L"SET ? = @LN;");
    v215 = VsqlClient::PlaceholderBindOutput(v284, 0x82u, 2 * (int)v228);
  }
  Voledb::AppendQuery((Voledb *)v283, L" IF @iRet <> 0 GOTO done; ");
  v117 = v202;
  v118 = sub_180029938(
           (int)v285,
           (int)&v281,
           (int)L"@S",
           (int)L"@DocId",
           (int)L"@Level",
           *(VdbServer **)(*((_QWORD *)v202 + 18) + 56LL));
  VHRESULT::operator=(a2, v118);
  VHRESULT::~VHRESULT((VHRESULT *)&v281);
  v119 = *(_DWORD *)a2;
  if ( *(int *)a2 < 0 )
  {
    v120 = L"VdocumentStore::storeDocument call to transferBlob failed. (0x%08X)";
    v121 = 20018568;
LABEL_222:
    LODWORD(v171) = v119;
    ULSSendTraceTag(v121, 117141571, 50, v120, v171);
    goto LABEL_10;
  }
  VdocumentStore::appendDocUpdateParams(
    v221,
    (struct Voledb *)v283,
    *(struct VdbServer **)(*((_QWORD *)v117 + 18) + 56LL),
    v225,
    (const wchar_t **)v271[0],
    v270,
    a30);
  Voledb::AppendQuery((Voledb *)v283, L" EXEC proc_DirtyDependents @S,1,@FU;");
  v122 = v208;
  if ( v189 )
    v122 = 1;
  if ( v182 )
  {
    v123 = VdbSubweb::getDoclibManager(*((VdbSubweb **)v117 + 18));
    PreparedUpdateQuery = VdoclibManager::GetPreparedUpdateQuery(v123, &v281, v248, v224[0], 0, v187);
    VHRESULT::operator=(a2, PreparedUpdateQuery);
    VHRESULT::~VHRESULT((VHRESULT *)&v281);
    if ( !*(_DWORD *)a2 )
      v122 |= 0x40u;
    if ( v249 )
    {
      (*(void (__fastcall **)(char *))(*((_QWORD *)v249 + 8) + 16LL))(v249 + 64);
      v249 = 0;
    }
    v89 = *(_DWORD *)a2;
    if ( *(int *)a2 < 0 )
    {
      v90 = L"VdocumentStore::storeDocument call to GetPreparedUpdateQuery failed. (0x%08X)";
      v91 = 20018569;
      goto LABEL_97;
    }
  }
  sub_1800C40F4(v117, v283);
  v125 = sub_1800C4188(&v281, v117, v283);
  VHRESULT::operator=(a2, v125);
  VHRESULT::~VHRESULT((VHRESULT *)&v281);
  v89 = *(_DWORD *)a2;
  if ( *(int *)a2 < 0 )
  {
    v90 = L"VdocumentStore::storeDocument call to AppendParsedWebParts failed. (0x%08X)";
    v91 = 20018570;
    goto LABEL_97;
  }
  sub_1800C407C(v117, v283);
  if ( v192 )
  {
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v192 + 720LL))(v192) )
    {
      v126 = CWebLocker::AcquireLock(v278, &v281);
      VHRESULT::operator=(a2, v126);
      VHRESULT::~VHRESULT((VHRESULT *)&v281);
      v89 = *(_DWORD *)a2;
      if ( *(int *)a2 < 0 )
      {
        v90 = L"VdocumentStore::storeDocument call to AcquireLock failed. (0x%08X)";
        v91 = 20018571;
        goto LABEL_97;
      }
    }
    if ( v278[0] )
    {
      Voledb::AppendQuery((Voledb *)v283, L";IF @iRet = 0 BEGIN ");
      CTranLockManager::AppendTranUnlockWebQuery(
        (struct Voledb *)v283,
        (const struct _GUID *)(*((_QWORD *)v193 + 7) + 184LL),
        (const struct _GUID *)((char *)v193 + 264));
    }
    else
    {
      v127 = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v192 + 160LL))(v192, &v281);
      VHRESULT::operator=(a2, v127);
      v89 = *(_DWORD *)a2;
      if ( *(int *)a2 < 0 )
      {
        v90 = L"VdocumentStore::storeDocument get_ListID failed. (0x%08X)";
        v91 = 20018572;
        goto LABEL_97;
      }
      Voledb::AppendQuery((Voledb *)v283, L";IF @iRet = 0 BEGIN ");
      CTranLockManager::AppendEnsureTranLockNotRequiredQuery(
        (struct Voledb *)v283,
        (const struct _GUID *)((char *)v200 + 184),
        &v281,
        1);
    }
    Voledb::AppendQuery((Voledb *)v283, L" END;");
  }
  Voledb::AppendQuery((Voledb *)v283, L" done: IF @iRet=0 BEGIN COMMIT; ");
  if ( v182 )
  {
    v128 = *((_QWORD *)v117 + 18);
    v129 = *(_QWORD *)(v128 + 64);
    if ( v129 )
      v130 = *(_QWORD *)(v129 + 88);
    else
      v130 = 0;
    if ( v130 )
    {
      v131 = *(_QWORD *)(v128 + 64);
      if ( v131 )
        v132 = *(_QWORD *)(v131 + 88);
      else
        v132 = 0;
      v133 = **(_DWORD **)(v132 + 48);
    }
    else
    {
      v133 = -1;
    }
    CTranLockManager::AppendItemUpdateForListQuery(
      (struct Voledb *)v283,
      (const struct _GUID *)((char *)v200 + 184),
      v219,
      v200,
      1,
      v133);
  }
  Voledb::AppendQuery((Voledb *)v283, L"EXEC proc_UpdateDiskUsed @S, 1;");
  v196 &= 0x4000000u;
  if ( !v196 )
    Voledb::AppendQuery((Voledb *)v283, L"EXEC proc_GetLinkInfoSingleDoc @S,@DN,@LN,@Level;");
  if ( v192 && v182 && (v290 & 0x100000) == 0 && VdbServer::databaseSupportsGetListWnsSubscriptions(v246) )
  {
    v134 = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v192 + 160LL))(v192, &v281);
    VHRESULT::operator=(a2, v134);
    v89 = *(_DWORD *)a2;
    if ( *(int *)a2 < 0 )
    {
      v90 = L"VdocumentStore::storeDocument get_ListID failed. (0x%08X)";
      v91 = 20018573;
      goto LABEL_97;
    }
    VWnsSubscriptionProcessor::appendGetWnsSubscriptionsQuery(
      (VWnsSubscriptionProcessor *)&v245,
      (struct Voledb *)v283,
      &v281,
      0);
    v190 = 1;
  }
  Voledb::AppendQuery((Voledb *)v283, L" END  ELSE ROLLBACK;  SET ? = @iRet;");
  v184 = VsqlClient::PlaceholderBindReturnValue(v284);
  v135 = Voledb::ExecQuery(v283, &v281, 0, "VdocumentStore::storeDocument");
  VHRESULT::operator=(a2, v135);
  VHRESULT::~VHRESULT((VHRESULT *)&v281);
  if ( *(int *)a2 < 0 )
  {
    LODWORD(v171) = *(_DWORD *)a2;
    ULSSendTraceTag(20018574, 117141571, 50, L"VdocumentStore::storeDocument ExecQuery failed. (0x%08X)", v171);
    v205 = &v281;
    v136 = VHRESULT::VHRESULT((VHRESULT *)&v281, a2);
    v137 = VdocHandle::translateSqlError(&v225, v136, v283);
    VHRESULT::operator=(a2, v137);
    VHRESULT::~VHRESULT((VHRESULT *)&v225);
    goto LABEL_98;
  }
  v138 = VdocHandle::handleDocQuery(v117, &v281, v283, v122, 0, &v198, 0, 0);
  VHRESULT::operator=(a2, v138);
  VHRESULT::~VHRESULT((VHRESULT *)&v281);
  v89 = *(_DWORD *)a2;
  if ( *(int *)a2 < 0 )
  {
    v90 = L"VdocumentStore::storeDocument handleDocQuery(..., dwQueryParts, ...) failed. (0x%08X)";
    v91 = 20018575;
    goto LABEL_97;
  }
  if ( !v196 )
  {
    v139 = VdocHandle::handleDocQuery(v117, &v281, v283, 2, 0, 0, 0, 0);
    VHRESULT::operator=(a2, v139);
    VHRESULT::~VHRESULT((VHRESULT *)&v281);
    v89 = *(_DWORD *)a2;
    if ( *(int *)a2 < 0 )
    {
      v90 = L"VdocumentStore::storeDocument handleDocQuery(..., qpLinks, ...) failed. (0x%08X)";
      v91 = 20018576;
      goto LABEL_97;
    }
  }
  OutputParam = Voledb::GetOutputParam(v283, &v281, v113, &v242, 8, 0);
  VHRESULT::operator=(a2, OutputParam);
  VHRESULT::~VHRESULT((VHRESULT *)&v281);
  v89 = *(_DWORD *)a2;
  if ( *(int *)a2 < 0 )
  {
    v90 = L"VdocumentStore::storeDocument GetOutputParam(ordDate, ...) failed. (0x%08X)";
    v91 = 20018577;
    goto LABEL_97;
  }
  v61 = (wchar_t *)v195;
  if ( v195 )
  {
    v141 = Voledb::GetOutputParam(v283, &v281, v215, v195, 2 * (int)v228, 0);
    VHRESULT::operator=(a2, v141);
    VHRESULT::~VHRESULT((VHRESULT *)&v281);
    v119 = *(_DWORD *)a2;
    if ( *(int *)a2 < 0 )
    {
      v120 = L"VdocumentStore::storeDocument GetOutputParam(ordwzLeafName, ...) failed. (0x%08X)";
      v121 = 20018578;
      goto LABEL_222;
    }
    Vwstring::operator=(v244, v61);
    VstorePathSanityInspector::inspect(v61);
    v51 = v61;
  }
  v225 = (struct VlinkVvector *)&v281;
  v142 = VHRESULT::VHRESULT((VHRESULT *)&v281, a2);
  v143 = sub_18002BA50(v271, v283, v142, v184);
  VHRESULT::operator=(a2, v143);
  VHRESULT::~VHRESULT((VHRESULT *)v271);
  v92 = -1;
  v184 = -1;
  if ( *(int *)a2 >= 0 )
  {
    if ( v278[0] )
      CWebLocker::setLockWasReleasedInSQL((CWebLocker *)v278);
    if ( !a22 )
    {
      OWSTimeTFromOleDate(v242, &v273);
      Vtime::Vtime((Vtime *)&v225, v273);
      v146 = v229;
      *(_QWORD *)v229 = v225;
      *((_BYTE *)v146 + 8) = v226;
    }
    v147 = *v230;
    if ( (_BYTE)v199 )
    {
      Vwstring::operator=(&v220, *v203);
      VstorePathSanityInspector::inspect(L"/");
      Vwstring::operator+=(&v220, L"/");
      Vwstring::operator+=(&v220, v51);
      v147 = v220;
    }
    if ( a46 )
    {
      v148 = "Not Shared";
      if ( a46 != 1 )
        v148 = "Unknown";
    }
    else
    {
      v148 = "Shared";
    }
    ULSSendTraceTag(36763273, 117141571, 100, L"Sharing state: %S", v148);
    v225 = (struct VlinkVvector *)&v203;
    Vstring::Vstring((Vstring *)&v203);
    v149 = sub_1800F7E14(&v204, v147);
    VwstringVvector::VwstringVvector((VwstringVvector *)&v225, 0);
    pszc = (OLECHAR *)v149;
    v62 = v193;
    VSimpleUsageEventLog::writeFileActivityLogInternal(
      &v281,
      L"FileUploaded",
      v187,
      v219,
      v193,
      pszc,
      L"File",
      &v203,
      1,
      0,
      &v225,
      0);
    v194 |= 0x800u;
    v150 = v194;
    VwstringVvector::~VwstringVvector(&v225);
    v194 = v150 & 0xFFFFF7FF;
    VHRESULT::~VHRESULT((VHRESULT *)&v281);
    v225 = (struct VlinkVvector *)&v204;
    Vstring::~Vstring((Vstring *)&v204);
    v225 = (struct VlinkVvector *)&v203;
    Vstring::~Vstring((Vstring *)&v203);
    if ( v182 )
    {
      VdocumentStore::fireListEvent(v192, v62, 0, 0, v147, 0, (char *)v117 + 168);
      SqmIncrementOne(4758);
      v151 = v192;
      if ( v192 )
      {
        v152 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v192 + 504LL))(v192);
        v151 = v192;
      }
      else
      {
        v152 = 0;
      }
      v153 = -1;
      v199 = -1;
      if ( v151 )
      {
        (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v151 + 144LL))(v151, &v199);
        v153 = v199;
      }
      *(_DWORD *)v179 = v153;
      LODWORD(psza) = 10001;
      LODWORD(v173) = v198;
      ULSSendTraceTag(
        6908112,
        117141511,
        50,
        L"storeDocument checking ER, ItemId: %d, EventType: %d, ListBaseType: %d",
        v173,
        psza,
        *(_QWORD *)v179);
      if ( (unsigned __int8)VeventHost::hasEventReceiver(v152, v62, 10001, v198, 0) )
      {
        Vwstring::Vwstring((Vwstring *)&v204, (VdocHandle *)((char *)v117 + 160));
        LOBYTE(v174) = 0;
        VeventHost::fireItemEvent(
          v152,
          &v281,
          10001,
          0,
          v174,
          v62,
          v192,
          v198,
          0,
          0,
          v204,
          0,
          (char *)v117 + 168,
          0,
          v187);
        VHRESULT::~VHRESULT((VHRESULT *)&v281);
        Vwstring::~Vwstring(&v204);
      }
    }
    v154 = v191;
    *((_BYTE *)v117 + 3260) = v191;
    v205->Data1 = 1;
    v180 = a4;
    v63 = v187;
    v155 = sub_180029C50(
             (int)v285,
             (int)&v281,
             (unsigned int)*(_QWORD *)(*((_QWORD *)v117 + 18) + 56LL) + 184,
             v243[0],
             (__int64)v187,
             v233,
             v154,
             v216,
             *(_DWORD *)v231 + 100,
             *v231 + 100,
             *v232,
             v180,
             v209,
             *(_BYTE *)(*(_QWORD *)(*((_QWORD *)v117 + 18) + 56LL) + 984LL));
    VHRESULT::operator=(a2, v155);
    VHRESULT::~VHRESULT((VHRESULT *)&v281);
    v156 = *(_DWORD *)a2;
    if ( *(int *)a2 >= 0 )
    {
      if ( !v190 )
        goto LABEL_99;
      v247 = v186[0] == 0;
      v159 = VWnsSubscriptionProcessor::handleWnsSubscriptionsQueryResult(&v245, &v281, v283, (char *)v62 + 264, 5);
      VHRESULT::operator=(a2, v159);
      VHRESULT::~VHRESULT((VHRESULT *)&v281);
      v156 = *(_DWORD *)a2;
      v157 = L"VdocumentStore::storeDocument setDontIgnoreNotifications failed. (0x%08X)";
      v158 = 20018581;
    }
    else
    {
      v157 = L"VdocumentStore::storeDocument reinitProps failed. (0x%08X)";
      v158 = 20018580;
    }
    LODWORD(v170) = v156;
    ULSSendTraceTag(v158, 117141571, 50, v157, v170);
LABEL_99:
    v61 = (wchar_t *)v195;
    goto LABEL_100;
  }
  LODWORD(v171) = *(_DWORD *)a2;
  ULSSendTraceTag(
    20018579,
    117141571,
    50,
    L"VdocumentStore::storeDocument GetBetterHrFromOutParam returned failure. (0x%08X)",
    v171);
  v205 = &v281;
  v144 = VHRESULT::VHRESULT((VHRESULT *)&v281, a2);
  if ( (unsigned __int8)CTranLockManager::IsTranLockError(v144) )
  {
    v205 = &v281;
    v145 = VHRESULT::VHRESULT((VHRESULT *)&v281, a2);
    v62 = v193;
    CTranLockManager::LogTranLockErrors(v145, (char *)v193 + 264);
    VHRESULT::operator=(a2, 2147500037LL);
  }
  else
  {
    v62 = v193;
  }
  v63 = v187;
LABEL_101:
  if ( v249 )
    (*(void (__fastcall **)(char *))(*((_QWORD *)v249 + 8) + 16LL))(v249 + 64);
  v93 = v192;
  if ( v192 )
  {
    if ( !a16 )
    {
      (*(void (**)(void))(*(_QWORD *)v192 + 64LL))();
      v93 = v192;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
  }
  if ( (unsigned int)COWSAllocator::QueryNewMode(v93) )
    COWSAllocator::Free(v61);
  else
    free(v61);
  v160 = Block;
  if ( (unsigned int)COWSAllocator::QueryNewMode(v94) )
    COWSAllocator::Free(v160);
  else
    free(v160);
  Block = 0;
  if ( v92 != -1 )
  {
    v205 = &v281;
    v161 = VHRESULT::VHRESULT((VHRESULT *)&v281, a2);
    v162 = sub_18002BA50(&v225, v283, v161, v92);
    VHRESULT::operator=(a2, v162);
    VHRESULT::~VHRESULT((VHRESULT *)&v225);
    if ( *(int *)a2 < 0 )
    {
      LODWORD(v170) = *(_DWORD *)a2;
      ULSSendTraceTag(
        20018582,
        117141571,
        50,
        L"VdocumentStore::storeDocument GetBetterHrFromOutParam returned failure. (0x%08X)",
        v170);
    }
  }
  v163 = v222;
  if ( v222 && *(int *)a2 < 0 )
  {
    v205 = &v281;
    v164 = VHRESULT::VHRESULT((VHRESULT *)&v281, a2);
    v165 = VdocumentStore::setFieldDataErrors(v221, &v225, v62, v163[8], v163[9], v283, v164);
    VHRESULT::operator=(a2, v165);
    VHRESULT::~VHRESULT((VHRESULT *)&v225);
  }
  if ( *((_QWORD *)v62 + 7) && v63 )
  {
    v205 = &v281;
    v166 = VHRESULT::VHRESULT((VHRESULT *)&v281, a2);
    LOBYTE(psz) = v191;
    VmonitoredScope::Done(v275, v166, v209, *((_QWORD *)v62 + 7) + 184LL, v63, psz);
  }
  else
  {
    v205 = &v281;
    v167 = VHRESULT::VHRESULT((VHRESULT *)&v281, a2);
    LOBYTE(psz) = 0;
    VmonitoredScope::Done(v275, v167, v209, &stru_18020E740, &stru_18020E740, psz);
  }
  Vwstring::~Vwstring(&v220);
  Vwstring::~Vwstring(v244);
  v245 = &VWnsSubscriptionProcessor::`vftable';
  v246 = 0;
  VdoclibUpdateParams::~VdoclibUpdateParams((VdoclibUpdateParams *)v248);
  Vwstring::~Vwstring(&v233);
  CWebLocker::~CWebLocker((CWebLocker *)v278);
  Voledb::~Voledb((Voledb *)v283);
  VmonitoredScope::~VmonitoredScope((VmonitoredScope *)v275);
  return a2;
}

```

## disassembly

```asm
0x1800dd6b0  mov     rax, rsp
0x1800dd6b3  push    rbp
0x1800dd6b4  push    rsi
0x1800dd6b5  push    rdi
0x1800dd6b6  push    r12
0x1800dd6b8  push    r13
0x1800dd6ba  push    r14
0x1800dd6bc  push    r15
0x1800dd6be  lea     rbp, [rax-7C8h]
0x1800dd6c5  sub     rsp, 8D0h
0x1800dd6cc  mov     [rbp+7C0h+var_510], 0FFFFFFFFFFFFFFFEh
0x1800dd6d7  mov     [rax+20h], rbx
0x1800dd6db  mov     rax, cs:__security_cookie
0x1800dd6e2  xor     rax, rsp
0x1800dd6e5  mov     [rbp+7C0h+var_40], rax
0x1800dd6ec  mov     r14d, r9d
0x1800dd6ef  mov     [rbp+7C0h+var_7C0], r8
0x1800dd6f3  mov     r15, rdx
0x1800dd6f6  mov     [rbp+7C0h+var_738], rcx
0x1800dd6fd  mov     [rbp+7C0h+var_518], rdx
0x1800dd704  mov     rax, [rbp+7C0h+arg_20]
0x1800dd70b  mov     [rbp+7C0h+var_7A8], rax
0x1800dd70f  mov     rdi, [rbp+7C0h+arg_28]
0x1800dd716  mov     [rbp+7C0h+var_690], rdi
0x1800dd71d  mov     rax, [rbp+7C0h+arg_30]
0x1800dd724  mov     [rbp+7C0h+var_6D8], rax
0x1800dd72b  mov     rax, [rbp+7C0h+arg_38]
0x1800dd732  mov     qword ptr [rbp+7C0h+var_668], rax
0x1800dd739  mov     rax, [rbp+7C0h+arg_40]
0x1800dd740  mov     [rbp+7C0h+var_810], rax
0x1800dd744  mov     rax, [rbp+7C0h+arg_48]
0x1800dd74b  mov     [rbp+7C0h+var_750], rax
0x1800dd74f  mov     rax, [rbp+7C0h+arg_50]
0x1800dd756  mov     [rbp+7C0h+var_698], rax
0x1800dd75d  mov     rax, [rbp+7C0h+arg_58]
0x1800dd764  mov     [rbp+7C0h+var_758], rax
0x1800dd768  mov     rsi, [rbp+7C0h+arg_88]
0x1800dd76f  mov     [rbp+7C0h+var_7E0], rsi
0x1800dd773  mov     rax, [rbp+7C0h+arg_98]
0x1800dd77a  mov     [rbp+7C0h+var_7A0], rax
0x1800dd77e  mov     rax, [rbp+7C0h+arg_B0]
0x1800dd785  mov     [rbp+7C0h+var_680], rax
0x1800dd78c  mov     rax, [rbp+7C0h+arg_B8]
0x1800dd793  mov     [rbp+7C0h+var_6E0], rax
0x1800dd79a  mov     r13, [rbp+7C0h+arg_C0]
0x1800dd7a1  mov     [rbp+7C0h+var_7B0], r13
0x1800dd7a5  mov     rax, [rbp+7C0h+arg_C8]
0x1800dd7ac  mov     [rbp+7C0h+var_568], rax
0x1800dd7b3  mov     rax, [rbp+7C0h+arg_D0]
0x1800dd7ba  mov     [rbp+7C0h+var_710], rax
0x1800dd7c1  mov     rax, [rbp+7C0h+arg_D8]
0x1800dd7c8  mov     [rbp+7C0h+var_588], rax
0x1800dd7cf  mov     rax, [rbp+7C0h+arg_E0]
0x1800dd7d6  mov     [rbp+7C0h+var_590], rax
0x1800dd7dd  mov     eax, [rbp+7C0h+arg_F0]
0x1800dd7e3  mov     [rbp+7C0h+var_7D0], eax
0x1800dd7e6  mov     rax, [rbp+7C0h+arg_118]
0x1800dd7ed  mov     [rbp+7C0h+var_578], rax
0x1800dd7f4  mov     rcx, [rbp+7C0h+arg_120]
0x1800dd7fb  mov     [rbp+7C0h+var_550], rcx
0x1800dd802  mov     rax, [rbp+7C0h+arg_128]
0x1800dd809  mov     [rbp+7C0h+var_798], rax
0x1800dd80d  mov     eax, [rbp+7C0h+arg_130]
0x1800dd813  mov     [rbp+7C0h+var_760], eax
0x1800dd816  mov     rax, [rbp+7C0h+arg_140]
0x1800dd81d  mov     [rbp+7C0h+var_6D0], rax
0x1800dd824  mov     rax, [rbp+7C0h+arg_148]
0x1800dd82b  mov     [rbp+7C0h+var_6C8], rax
0x1800dd832  mov     rax, [rbp+7C0h+arg_158]
0x1800dd839  mov     [rbp+7C0h+var_548], rax
0x1800dd840  xor     ebx, ebx
0x1800dd842  mov     [rbp+7C0h+var_7F0], ebx
0x1800dd845  lea     rax, aVdocumentstore_66; "VdocumentStore::storeDocument"
0x1800dd84c  mov     [rsp+900h+var_8E0], rax; wchar_t *
0x1800dd851  mov     edx, 215797h; unsigned int
0x1800dd856  lea     r9d, [rbx+32h]; unsigned int
0x1800dd85a  mov     r8d, 6FB7043h; unsigned int
0x1800dd860  lea     rcx, [rbp+7C0h+var_560]; this
0x1800dd867  call    ??0VmonitoredScope@@QEAA@KKKPEB_W@Z; VmonitoredScope::VmonitoredScope(ulong,ulong,ulong,wchar_t const *)
0x1800dd86c  nop
0x1800dd86d  or      [rbp+7C0h+var_780], 0FFFFFFFFFFFFFFFFh
0x1800dd872  mov     r12, [r13+90h]
0x1800dd879  mov     [rbp+7C0h+var_7F8], r12
0x1800dd87d  mov     rax, rsi
0x1800dd880  shr     rax, 22h
0x1800dd884  lea     esi, [rbx+1]
0x1800dd887  and     al, sil
0x1800dd88a  mov     [rbp+7C0h+var_6B0], rax
0x1800dd891  mov     r8b, sil; char
0x1800dd894  mov     rdx, [rbp+7C0h+var_738]; struct COWSConnection *
0x1800dd89b  lea     rcx, [rbp+7C0h+var_4E0]; this
0x1800dd8a2  call    ??0Voledb@@QEAA@PEAVCOWSConnection@@D@Z; Voledb::Voledb(COWSConnection *,char)
0x1800dd8a7  nop
0x1800dd8a8  cmp     [r12+1C8h], rbx
0x1800dd8b0  setz    [rbp+7C0h+var_807]
0x1800dd8b4  mov     eax, [r13+0C08h]
0x1800dd8bb  shr     eax, 8
0x1800dd8be  and     al, sil
0x1800dd8c1  mov     [rbp+7C0h+var_76C], eax
0x1800dd8c4  cmp     [rbp+7C0h+arg_E8], ebx
0x1800dd8ca  setnz   [rbp+7C0h+var_840]
0x1800dd8ce  mov     rdx, r12; struct VdbSubweb *
0x1800dd8d1  lea     rcx, [rbp+7C0h+var_540]; this
0x1800dd8d8  call    ??0CWebLocker@@QEAA@PEAVVdbSubweb@@@Z; CWebLocker::CWebLocker(VdbSubweb *)
0x1800dd8dd  nop
0x1800dd8de  mov     [rbp+7C0h+var_748], rbx
0x1800dd8e2  mov     [rbp+7C0h+var_800], rbx
0x1800dd8e6  mov     [rbp+7C0h+var_838], bl
0x1800dd8e9  or      [rbp+7C0h+var_828], 0FFFFFFFFh
0x1800dd8ed  xor     edx, edx
0x1800dd8ef  mov     rcx, r15
0x1800dd8f2  call    cs:??0VHRESULT@@QEAA@J@Z; VHRESULT::VHRESULT(long)
0x1800dd8f8  mov     [rbp+7C0h+var_7F0], esi
0x1800dd8fb  mov     r12b, bl
0x1800dd8fe  mov     [rbp+7C0h+var_790], ebx
0x1800dd901  mov     [rbp+7C0h+var_7E8], rbx
0x1800dd905  mov     esi, ebx
0x1800dd907  mov     dword ptr [rbp+7C0h+var_6E8], ebx
0x1800dd90d  mov     byte ptr [rbp+7C0h+var_7C8], bl
0x1800dd910  mov     [rbp+7C0h+var_764], ebx
0x1800dd913  mov     byte ptr [rbp+7C0h+var_7B8], bl
0x1800dd916  mov     byte ptr [rbp+7C0h+var_770], bl
0x1800dd919  lea     eax, [rbx+1]
0x1800dd91c  mov     byte ptr [rbp+7C0h+var_804], al
0x1800dd91f  mov     rdx, [rbp+7C0h+var_738]
0x1800dd926  lea     rcx, [rbp+7C0h+var_90]
0x1800dd92d  call    sub_1800F7DE0
0x1800dd932  nop
0x1800dd933  add     r13, 98h
0x1800dd93a  mov     rcx, r13
0x1800dd93d  call    cs:?data@Vstring@@QEBAPEBDXZ; Vstring::data(void)
0x1800dd943  mov     rdx, rax
0x1800dd946  lea     rcx, [rbp+7C0h+var_6C0]
0x1800dd94d  call    cs:??0Vwstring@@QEAA@PEBD@Z; Vwstring::Vwstring(char const *)
0x1800dd953  nop
0x1800dd954  lea     rcx, [rbp+7C0h+var_640]; this
0x1800dd95b  call    ??0VdoclibUpdateParams@@QEAA@XZ; VdoclibUpdateParams::VdoclibUpdateParams(void)
0x1800dd960  nop
0x1800dd961  mov     [rbp+7C0h+var_730], rbx
0x1800dd968  mov     [rbp+7C0h+var_620], rbx
0x1800dd96f  mov     [rbp+7C0h+Block], rbx
0x1800dd976  or      [rbp+7C0h+var_78C], 0FFFFFFFFh
0x1800dd97a  lea     rax, ??_7VWnsSubscriptionProcessor@@6B@; const VWnsSubscriptionProcessor::`vftable'
0x1800dd981  mov     [rbp+7C0h+var_658], rax
0x1800dd988  mov     rdx, [rbp+7C0h+var_7C0]
0x1800dd98c  mov     [rbp+7C0h+var_650], rdx
0x1800dd993  mov     [rbp+7C0h+var_648], bl
0x1800dd999  mov     [rbp+7C0h+var_806], bl
0x1800dd99c  mov     [rbp+7C0h+var_678], rbx
0x1800dd9a3  mov     [rbp+7C0h+var_768], ebx
0x1800dd9a6  mov     [rbp+7C0h+var_818], bl
0x1800dd9a9  mov     [rbp+7C0h+var_7D8], bx
0x1800dd9ad  mov     rcx, [rbp+7C0h+var_7B0]
0x1800dd9b1  add     rcx, 0A8h
0x1800dd9b8  mov     [rbp+7C0h+var_820], rcx
0x1800dd9bc  mov     eax, [rcx+0D0h]
0x1800dd9c2  mov     [rbp+7C0h+var_774], eax
0x1800dd9c5  mov     rax, [rcx+0C8h]
0x1800dd9cc  mov     [rbp+7C0h+var_688], rax
0x1800dd9d3  test    rax, rax
0x1800dd9d6  setnz   al
0x1800dd9d9  test    al, al
0x1800dd9db  jz      short loc_1800DD9EF
0x1800dd9dd  mov     rax, [rbp+7C0h+var_750]
0x1800dd9e1  cmp     [rax+18h], rbx
0x1800dd9e5  jz      short loc_1800DD9F9
0x1800dd9e7  cmp     [rcx+0D4h], bl
0x1800dd9ed  jnz     short loc_1800DD9F9
0x1800dd9ef  mov     [rbp+7C0h+var_688], rbx
0x1800dd9f6  mov     [rbp+7C0h+var_774], ebx
0x1800dd9f9  mov     rdx, [rdi]
0x1800dd9fc  lea     rcx, [rbp+7C0h+var_660]
0x1800dda03  call    cs:??0Vwstring@@QEAA@PEB_W@Z; Vwstring::Vwstring(wchar_t const *)
0x1800dda09  nop
0x1800dda0a  lea     rcx, [rbp+7C0h+var_740]
0x1800dda11  call    cs:??0Vwstring@@QEAA@XZ; Vwstring::Vwstring(void)
0x1800dda17  nop
0x1800dda18  cmp     [rbp+7C0h+arg_A8], bl
0x1800dda1e  jz      short loc_1800DDA3C
0x1800dda20  mov     rcx, [rbp+7C0h+var_6E0]
0x1800dda27  call    cs:?secondsI64@Vtime@@QEBA_KXZ; Vtime::secondsI64(void)
0x1800dda2d  mov     rcx, rax; unsigned __int64
0x1800dda30  lea     rdx, [rbp+7C0h+var_670]; double *
0x1800dda37  call    ?OWSOleDateFromTimeT@@YAD_KPEAN@Z; OWSOleDateFromTimeT(unsigned __int64,double *)
0x1800dda3c  mov     rcx, [rbp+7C0h+var_7C0]; this
0x1800dda40  call    ?allowPoundPercentInPath@VdbServer@@QEBADXZ; VdbServer::allowPoundPercentInPath(void)
0x1800dda45  mov     rdx, [rbp+7C0h+var_7C0]
0x1800dda49  add     rdx, 0C8h
0x1800dda50  mov     r8d, 1
0x1800dda56  mov     [rsp+900h+var_8C8], r8d
0x1800dda5b  lea     rcx, [rbp+7C0h+var_7D8]
0x1800dda5f  mov     qword ptr [rsp+900h+var_8D0], rcx
0x1800dda64  mov     byte ptr [rsp+900h+psz], al
0x1800dda68  mov     rax, [rbp+7C0h+var_6D8]
0x1800dda6f  mov     [rsp+900h+var_8E0], rax
0x1800dda74  mov     r9, rdi
0x1800dda77  mov     r8, [rbp+7C0h+var_7A8]
0x1800dda7b  lea     rcx, [rbp+7C0h+var_6A8]
0x1800dda82  call    ?validateUrlForStore@VdocumentStore@@SA?AVVHRESULT@@AEBU_GUID@@AEBVVwcharPtrStorePath@@11DPEA_WW4VstoreOperation@@@Z; VdocumentStore::validateUrlForStore(_GUID const &,VwcharPtrStorePath const &,VwcharPtrStorePath const &,VwcharPtrStorePath const &,char,wchar_t *,VstoreOperation)
0x1800dda87  nop
0x1800dda88  mov     rdx, rax
0x1800dda8b  mov     rcx, r15
0x1800dda8e  call    cs:??4VHRESULT@@QEAAAEAV0@AEBV0@@Z; VHRESULT::operator=(VHRESULT const &)
0x1800dda94  nop
0x1800dda95  lea     rcx, [rbp+7C0h+var_6A8]
0x1800dda9c  call    cs:??1VHRESULT@@QEAA@XZ; VHRESULT::~VHRESULT(void)
0x1800ddaa2  mov     rdi, [rbp+7C0h+var_7C0]
0x1800ddaa6  mov     rcx, rdi; this
0x1800ddaa9  call    ?allowPoundPercentInPath@VdbServer@@QEBADXZ; VdbServer::allowPoundPercentInPath(void)
0x1800ddaae  mov     dl, al; char
0x1800ddab0  lea     rcx, [rdi+214h]; struct _GUID *
0x1800ddab7  mov     [rsp+900h+var_8E0], r13; struct VurlStorePath *
0x1800ddabc  mov     edi, 1
0x1800ddac1  mov     r9b, dil; char
0x1800ddac4  lea     r8, [rbp+7C0h+var_7D8]; wchar_t *
0x1800ddac8  call    ?LogPoundPercentFileFolderCreation@VdocumentStore@@SAXAEBU_GUID@@DAEB_WDAEBVVurlStorePath@@@Z; VdocumentStore::LogPoundPercentFileFolderCreation(_GUID const &,char,wchar_t const &,char,VurlStorePath const &)
0x1800ddacd  mov     eax, [r15]
0x1800ddad0  test    eax, eax
0x1800ddad2  jns     short loc_1800DDB05
0x1800ddad4  lea     r9, aVdocumentstore_67; "VdocumentStore::storeDocument validateU"...
0x1800ddadb  mov     ecx, 1317583h
0x1800ddae0  mov     dword ptr [rsp+900h+var_8E0], eax
0x1800ddae4  mov     edx, 6FB7043h
0x1800ddae9  mov     r8d, 32h ; '2'
0x1800ddaef  call    cs:ULSSendTraceTag
0x1800ddaf5  mov     rdi, rbx
0x1800ddaf8  mov     rsi, [rbp+7C0h+var_7F8]
0x1800ddafc  mov     r14, [rbp+7C0h+var_810]
0x1800ddb00  jmp     loc_1800DE1A7
0x1800ddb05  mov     rcx, [rbp+7C0h+var_7F8]; this
0x1800ddb09  call    ?getDoclibManager@VdbSubweb@@QEAAPEAVVdoclibManager@@XZ; VdbSubweb::getDoclibManager(void)
0x1800ddb0e  mov     rcx, rax
0x1800ddb11  lea     rax, [rbp+7C0h+var_800]
0x1800ddb15  mov     [rsp+900h+var_8E0], rax
0x1800ddb1a  mov     r9b, dil
0x1800ddb1d  mov     r8, r13
0x1800ddb20  lea     rdx, [rbp+7C0h+var_6A8]
0x1800ddb27  call    ?GetContainingList@VdoclibManager@@QEAA?AVVHRESULT@@AEBVVurlStorePath@@DPEAPEAUITPList@@@Z; VdoclibManager::GetContainingList(VurlStorePath const &,char,ITPList * *)
0x1800ddb2c  nop
0x1800ddb2d  cmp     [rax], ebx
0x1800ddb2f  setz    dil
0x1800ddb33  lea     rcx, [rbp+7C0h+var_6A8]
0x1800ddb3a  call    cs:??1VHRESULT@@QEAA@XZ; VHRESULT::~VHRESULT(void)
0x1800ddb40  test    dil, dil
0x1800ddb43  jz      loc_1800DDD4B
0x1800ddb49  mov     rcx, [rbp+7C0h+var_800]
0x1800ddb4d  mov     rax, [rcx]
0x1800ddb50  lea     rdx, [rbp+7C0h+var_4F8]
0x1800ddb57  mov     rax, [rax+0A0h]
0x1800ddb5e  call    cs:__guard_dispatch_icall_fptr
0x1800ddb64  mov     edx, eax
0x1800ddb66  mov     rcx, r15
0x1800ddb69  call    cs:??4VHRESULT@@QEAAAEAV0@J@Z; VHRESULT::operator=(long)
0x1800ddb6f  cmp     [rax], ebx
0x1800ddb71  jge     short loc_1800DDB87
0x1800ddb73  mov     eax, [r15]
0x1800ddb76  lea     r9, aVdocumentstore_68; "VdocumentStore::storeDocument get_ListI"...
0x1800ddb7d  mov     ecx, 1317584h
0x1800ddb82  jmp     loc_1800DDAE0
0x1800ddb87  lea     rax, [rbp+7C0h+var_4F8]
0x1800ddb8e  mov     [rbp+7C0h+var_748], rax
0x1800ddb92  mov     rcx, [rbp+7C0h+var_7F8]; this
0x1800ddb96  call    ?getDoclibManager@VdbSubweb@@QEAAPEAVVdoclibManager@@XZ; VdbSubweb::getDoclibManager(void)
0x1800ddb9b  mov     rcx, rax
0x1800ddb9e  mov     eax, 2
0x1800ddba3  mov     dword ptr [rsp+900h+var_8D0], eax
0x1800ddba7  mov     [rsp+900h+psz], rbx
0x1800ddbac  lea     edi, [rax-1]
0x1800ddbaf  mov     byte ptr [rsp+900h+var_8E0], dil
0x1800ddbb4  mov     r9, [rbp+7C0h+var_7E0]
0x1800ddbb8  mov     r8, [rbp+7C0h+var_820]
0x1800ddbbc  mov     rdx, r13
0x1800ddbbf  call    ?ShouldPromoteToDoclib@VdoclibManager@@QEAADAEBVVurlStorePath@@PEBVVmetaDict@@_JDPEAPEAUITPList@@W4VtriState@@@Z; VdoclibManager::ShouldPromoteToDoclib(VurlStorePath const &,VmetaDict const *,__int64,char,ITPList * *,VtriState)
0x1800ddbc4  mov     [rbp+7C0h+var_838], al
0x1800ddbc7  test    al, al
0x1800ddbc9  jnz     short loc_1800DDBD8
0x1800ddbcb  test    byte ptr [rbp+7C0h+arg_68], 2
0x1800ddbd2  jz      loc_1800DDD45
0x1800ddbd8  mov     r13, [rbp+7C0h+var_7E0]
0x1800ddbdc  cmp     [rbp+7C0h+var_800], rbx
0x1800ddbe0  jz      loc_1800DDD57
0x1800ddbe6  bt      r13, 13h
0x1800ddbeb  jb      loc_1800DDD57
0x1800ddbf1  call    ?getInstance@VKillSwitch@@SAPEAV1@XZ; VKillSwitch::getInstance(void)
0x1800ddbf6  test    rax, rax
0x1800ddbf9  jz      short loc_1800DDC26
0x1800ddbfb  lea     rdx, stru_1802354C8; struct _GUID *
0x1800ddc02  mov     rcx, rax; this
0x1800ddc05  call    ?findKey@VKillSwitch@@AEAADPEBU_GUID@@@Z; VKillSwitch::findKey(_GUID const *)
0x1800ddc0a  test    al, al
0x1800ddc0c  jz      short loc_1800DDC26
0x1800ddc0e  mov     rcx, [rbp+7C0h+var_800]
0x1800ddc12  mov     rax, [rcx]
0x1800ddc15  mov     rax, [rax+238h]
0x1800ddc1c  call    cs:__guard_dispatch_icall_fptr
0x1800ddc22  mov     edi, eax
0x1800ddc24  jmp     short loc_1800DDC50
0x1800ddc26  mov     rcx, [rbp+7C0h+var_800]
0x1800ddc2a  mov     rax, [rcx]
0x1800ddc2d  mov     rax, [rax+238h]
  ... truncated ...
```
