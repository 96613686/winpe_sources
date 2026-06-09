# WwanPmInit

- ea: `0x18009e098`
- end: `0x18009e34d`
- name: `WwanPmInit`
- size: `693`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014fe8`

## callees

- `0x180012300`
- `0x180014b5c`
- `0x180014f1c`
- `0x180016c50`
- `0x180074758`
- `0x180074cec`
- `0x18009b900`
- `0x18009ba7c`
- `0x18009bb64`
- `0x18009c0a0`
- `0x18009c308`
- `0x18009e098`
- `0x1800a0d04`
- `0x1800a0dc8`
- `0x1800a26a4`
- `0x1800a2710`
- `0x1800a2a40`
- `0x1800a2bf8`
- `0x1800a5b68`
- `0x1800a5c88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009e0c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009e0c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e2b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e31e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e2b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e31e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18009e1f0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18009e1f0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009e22c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009e22c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18009e12c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18009e12c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18009e2a7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18009e307`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18009e2a7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18009e307`

## string_xrefs

- `0x18009e263`: `MigrationCompleted`
- `0x18009e284`: `Failed to read the migration state for the profile store. ERROR_FILE_NOT_FOUND is ok - anything else is unexpected. Run migration anyway. [0x%8x]`
- `0x18009e0d7`: `PM is already initialized, errCode (0x%8x)`
- `0x18009e175`: `_createSchemaCollection failed, errCode (0x%8x)`
- `0x18009e1e0`: `InitDMConfigKeyNodeMap failed, errCode (0x%8x)`

## pseudocode

```c
__int64 WwanPmInit()
{
  unsigned int inited; // ebx
  unsigned int v1; // eax
  unsigned int v2; // eax
  HRESULT v3; // eax
  unsigned int SchemaCollection; // eax
  unsigned int HighestProfileIndex; // eax
  unsigned int DWORD; // eax
  unsigned int v8; // [rsp+30h] [rbp+8h] BYREF

  WwanLog::Enter("WwanPmInit");
  v8 = 0;
  EnterCriticalSection(&g_pmCs);
  if ( byte_180152850 )
  {
    inited = 1247;
    WwanLog::Error("WwanPmInit", 0, L"PM is already initialized, errCode (0x%8x)", 1247);
    goto LABEL_30;
  }
  v1 = WwanFsInit();
  inited = v1;
  if ( !v1 )
  {
    v2 = WwanRegInit();
    inited = v2;
    if ( v2 )
    {
      WwanLog::Error("WwanPmInit", 0, L"WwanRegInit failed, errCode (0x%8x)", v2);
LABEL_29:
      WwanFsDeinit();
      goto LABEL_30;
    }
    v3 = CoInitializeEx(0, 0);
    inited = v3;
    if ( v3 < 0 )
    {
      if ( (v3 & 0x1FFF0000) == 0x70000 )
        inited = (unsigned __int16)v3;
      WwanLog::Error("WwanPmInit", 0, L"CoInitializeEx failed, errCode (0x%8x)", inited);
      goto LABEL_28;
    }
    SchemaCollection = createSchemaCollection(&qword_180152868);
    inited = SchemaCollection;
    if ( SchemaCollection )
    {
      WwanLog::Error("WwanPmInit", 0, L"_createSchemaCollection failed, errCode (0x%8x)", SchemaCollection);
LABEL_27:
      CoUninitialize();
LABEL_28:
      WwanRegDeinit();
      goto LABEL_29;
    }
    inited = initKeyList(&qword_180152858, qword_180152868);
    if ( inited )
    {
      deinitKeyList(&qword_180152858);
      WwanLog::Error("WwanPmInit", 0, L"_initKeyList failed, errCode (0x%8x)", inited);
      goto LABEL_26;
    }
    inited = InitDMConfigKeyNodeMap(qword_180152868);
    if ( inited )
    {
      DeinitDMConfigKeyNodeMap();
      WwanLog::Error("WwanPmInit", 0, L"InitDMConfigKeyNodeMap failed, errCode (0x%8x)", inited);
LABEL_26:
      deleteSchemaCollection(qword_180152868);
      goto LABEL_27;
    }
    InitializeCriticalSection(&g_csHighestProfileIndex);
    g_dwHighestProfileIndex = 0x20000000;
    HighestProfileIndex = WwanRegGetHighestProfileIndex(&v8);
    inited = HighestProfileIndex;
    if ( HighestProfileIndex )
    {
      WwanLog::Error("WwanPmInit", 0, L"WwanRegGetHighestProfileIndex failed, result %u.", HighestProfileIndex);
      DeleteCriticalSection(&g_csHighestProfileIndex);
      goto LABEL_26;
    }
    g_dwHighestProfileIndex = v8 & 0xFFFFFFF | 0x20000000;
    WwanRegGetPowerProfile();
    byte_180152850 = 1;
    v8 = 0;
    DWORD = StateSeparation::GetDWORD(g_pSSWwansvcInReg, L"Profiles", L"MigrationCompleted", &v8);
    if ( DWORD )
    {
      WwanLog::Info(
        "_isProfileStoreMigrationDone",
        0,
        L"Failed to read the migration state for the profile store. ERROR_FILE_NOT_FOUND is ok - anything else is unexpect"
         "ed. Run migration anyway. [0x%8x]",
        DWORD);
    }
    else if ( v8 )
    {
LABEL_25:
      CoUninitialize();
      LeaveCriticalSection(&g_pmCs);
      WwanLog::Verbose("WwanPmInit", 0, L"errCode (0x%8x)", 0);
      WwanLog::Exit("WwanPmInit");
      return 0;
    }
    migrateProfileStoreFromSubscriberIdToSimIccidHelper();
    goto LABEL_25;
  }
  WwanLog::Error("WwanPmInit", 0, L"WwanFsInit failed, errCode (0x%8x)", v1);
LABEL_30:
  LeaveCriticalSection(&g_pmCs);
  WwanLog::Verbose("WwanPmInit", 0, L"errCode (0x%8x)", inited);
  WwanLog::Exit("WwanPmInit");
  return inited;
}

```

## disassembly

```asm
0x18009e098  mov     [rsp+arg_8], rbx
0x18009e09d  push    rdi
0x18009e09e  sub     rsp, 20h
0x18009e0a2  lea     rdi, aWwanpminit; "WwanPmInit"
0x18009e0a9  mov     rcx, rdi; char *
0x18009e0ac  call    ?Enter@WwanLog@@SAXPEBD@Z; WwanLog::Enter(char const *)
0x18009e0b1  mov     [rsp+28h+arg_0], 0
0x18009e0b9  lea     rcx, g_pmCs; lpCriticalSection
0x18009e0c0  call    cs:__imp_EnterCriticalSection
0x18009e0c6  cmp     cs:byte_180152850, 0
0x18009e0cd  jz      short loc_18009E0ED
0x18009e0cf  mov     ebx, 4DFh
0x18009e0d4  mov     r9d, ebx
0x18009e0d7  lea     r8, aPmIsAlreadyIni; "PM is already initialized, errCode (0x%"...
0x18009e0de  xor     edx, edx; struct _GUID *
0x18009e0e0  mov     rcx, rdi; char *
0x18009e0e3  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18009e0e8  jmp     loc_18009E317
0x18009e0ed  call    ?WwanFsInit@@YAKXZ; WwanFsInit(void)
0x18009e0f2  mov     ebx, eax
0x18009e0f4  test    eax, eax
0x18009e0f6  jz      short loc_18009E104
0x18009e0f8  mov     r9d, eax
0x18009e0fb  lea     r8, aWwanfsinitFail; "WwanFsInit failed, errCode (0x%8x)"
0x18009e102  jmp     short loc_18009E0DE
0x18009e104  call    ?WwanRegInit@@YAKXZ; WwanRegInit(void)
0x18009e109  mov     ebx, eax
0x18009e10b  test    eax, eax
0x18009e10d  jz      short loc_18009E128
0x18009e10f  mov     r9d, eax
0x18009e112  lea     r8, aWwanreginitFai; "WwanRegInit failed, errCode (0x%8x)"
0x18009e119  xor     edx, edx; struct _GUID *
0x18009e11b  mov     rcx, rdi; char *
0x18009e11e  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18009e123  jmp     loc_18009E312
0x18009e128  xor     edx, edx; dwCoInit
0x18009e12a  xor     ecx, ecx; pvReserved
0x18009e12c  call    cs:__imp_CoInitializeEx
0x18009e132  mov     ebx, eax
0x18009e134  test    eax, eax
0x18009e136  jns     short loc_18009E160
0x18009e138  and     eax, 1FFF0000h
0x18009e13d  cmp     eax, 70000h
0x18009e142  jnz     short loc_18009E147
0x18009e144  movzx   ebx, bx
0x18009e147  mov     r9d, ebx
0x18009e14a  lea     r8, aCoinitializeex; "CoInitializeEx failed, errCode (0x%8x)"
0x18009e151  xor     edx, edx; struct _GUID *
0x18009e153  mov     rcx, rdi; char *
0x18009e156  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18009e15b  jmp     loc_18009E30D
0x18009e160  lea     rcx, qword_180152868
0x18009e167  call    _createSchemaCollection
0x18009e16c  mov     ebx, eax
0x18009e16e  test    eax, eax
0x18009e170  jz      short loc_18009E18B
0x18009e172  mov     r9d, eax
0x18009e175  lea     r8, aCreateschemaco; "_createSchemaCollection failed, errCode"...
0x18009e17c  xor     edx, edx; struct _GUID *
0x18009e17e  mov     rcx, rdi; char *
0x18009e181  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18009e186  jmp     loc_18009E307
0x18009e18b  mov     rdx, cs:qword_180152868
0x18009e192  lea     rcx, qword_180152858
0x18009e199  call    _initKeyList
0x18009e19e  mov     ebx, eax
0x18009e1a0  test    eax, eax
0x18009e1a2  jz      short loc_18009E1C9
0x18009e1a4  lea     rcx, qword_180152858
0x18009e1ab  call    _deinitKeyList
0x18009e1b0  lea     r8, aInitkeylistFai; "_initKeyList failed, errCode (0x%8x)"
0x18009e1b7  mov     r9d, ebx
0x18009e1ba  xor     edx, edx; struct _GUID *
0x18009e1bc  mov     rcx, rdi; char *
0x18009e1bf  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18009e1c4  jmp     loc_18009E2FB
0x18009e1c9  mov     rcx, cs:qword_180152868
0x18009e1d0  call    InitDMConfigKeyNodeMap
0x18009e1d5  mov     ebx, eax
0x18009e1d7  test    eax, eax
0x18009e1d9  jz      short loc_18009E1E9
0x18009e1db  call    DeinitDMConfigKeyNodeMap
0x18009e1e0  lea     r8, aInitdmconfigke_0; "InitDMConfigKeyNodeMap failed, errCode "...
0x18009e1e7  jmp     short loc_18009E1B7
0x18009e1e9  lea     rcx, ?g_csHighestProfileIndex@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18009e1f0  call    cs:__imp_InitializeCriticalSection
0x18009e1f6  nop
0x18009e1f7  mov     cs:?g_dwHighestProfileIndex@@3KA, 20000000h; ulong g_dwHighestProfileIndex
0x18009e201  lea     rcx, [rsp+28h+arg_0]; unsigned int *
0x18009e206  call    ?WwanRegGetHighestProfileIndex@@YAKPEAK@Z; WwanRegGetHighestProfileIndex(ulong *)
0x18009e20b  mov     ebx, eax
0x18009e20d  test    eax, eax
0x18009e20f  jz      short loc_18009E237
0x18009e211  mov     r9d, eax
0x18009e214  lea     r8, aWwanreggethigh_0; "WwanRegGetHighestProfileIndex failed, r"...
0x18009e21b  xor     edx, edx; struct _GUID *
0x18009e21d  mov     rcx, rdi; char *
0x18009e220  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18009e225  lea     rcx, ?g_csHighestProfileIndex@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18009e22c  call    cs:__imp_DeleteCriticalSection
0x18009e232  jmp     loc_18009E2FB
0x18009e237  mov     eax, [rsp+28h+arg_0]
0x18009e23b  and     eax, 0FFFFFFFh
0x18009e240  bts     eax, 1Dh
0x18009e244  mov     cs:?g_dwHighestProfileIndex@@3KA, eax; ulong g_dwHighestProfileIndex
0x18009e24a  call    ?WwanRegGetPowerProfile@@YAKXZ; WwanRegGetPowerProfile(void)
0x18009e24f  mov     cs:byte_180152850, 1
0x18009e256  mov     [rsp+28h+arg_0], 0
0x18009e25e  lea     r9, [rsp+28h+arg_0]; unsigned int *
0x18009e263  lea     r8, aMigrationcompl; "MigrationCompleted"
0x18009e26a  lea     rdx, aProfiles; "Profiles"
0x18009e271  mov     rcx, cs:?g_pSSWwansvcInReg@@3PEAVStateSeparation@@EA; this
0x18009e278  call    ?GetDWORD@StateSeparation@@QEAAKPEBG0PEAK@Z; StateSeparation::GetDWORD(ushort const *,ushort const *,ulong *)
0x18009e27d  test    eax, eax
0x18009e27f  jz      short loc_18009E29B
0x18009e281  mov     r9d, eax
0x18009e284  lea     r8, aFailedToReadTh; "Failed to read the migration state for "...
0x18009e28b  xor     edx, edx; struct _GUID *
0x18009e28d  lea     rcx, aIsprofilestore; "_isProfileStoreMigrationDone"
0x18009e294  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18009e299  jmp     short loc_18009E2A2
0x18009e29b  cmp     [rsp+28h+arg_0], 0
0x18009e2a0  jnz     short loc_18009E2A7
0x18009e2a2  call    _migrateProfileStoreFromSubscriberIdToSimIccidHelper
0x18009e2a7  call    cs:__imp_CoUninitialize
0x18009e2ad  lea     rcx, g_pmCs; lpCriticalSection
0x18009e2b4  call    cs:__imp_LeaveCriticalSection
0x18009e2ba  xor     r9d, r9d
0x18009e2bd  lea     r8, aErrcode0x8x; "errCode (0x%8x)"
0x18009e2c4  xor     edx, edx; struct _GUID *
0x18009e2c6  mov     rcx, rdi; char *
0x18009e2c9  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x18009e2ce  mov     rcx, rdi; char *
0x18009e2d1  call    ?Exit@WwanLog@@SAXPEBD@Z; WwanLog::Exit(char const *)
0x18009e2d6  xor     eax, eax
0x18009e2d8  jmp     short loc_18009E342
0x18009e2da  mov     ebx, eax
0x18009e2dc  mov     r9d, eax
0x18009e2df  lea     r8, aFailedToInitia; "Failed to initialize the critical secti"...
0x18009e2e6  xor     edx, edx; struct _GUID *
0x18009e2e8  lea     rcx, aWwanpminit; "WwanPmInit"
0x18009e2ef  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18009e2f4  lea     rdi, aWwanpminit; "WwanPmInit"
0x18009e2fb  mov     rcx, cs:qword_180152868
0x18009e302  call    _deleteSchemaCollection
0x18009e307  call    cs:__imp_CoUninitialize
0x18009e30d  call    ?WwanRegDeinit@@YAXXZ; WwanRegDeinit(void)
0x18009e312  call    ?WwanFsDeinit@@YAXXZ; WwanFsDeinit(void)
0x18009e317  lea     rcx, g_pmCs; lpCriticalSection
0x18009e31e  call    cs:__imp_LeaveCriticalSection
0x18009e324  mov     r9d, ebx
0x18009e327  lea     r8, aErrcode0x8x; "errCode (0x%8x)"
0x18009e32e  xor     edx, edx; struct _GUID *
0x18009e330  mov     rcx, rdi; char *
0x18009e333  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x18009e338  mov     rcx, rdi; char *
0x18009e33b  call    ?Exit@WwanLog@@SAXPEBD@Z; WwanLog::Exit(char const *)
0x18009e340  mov     eax, ebx
0x18009e342  mov     rbx, [rsp+28h+arg_8]
0x18009e347  add     rsp, 20h
0x18009e34b  pop     rdi
0x18009e34c  retn
```
