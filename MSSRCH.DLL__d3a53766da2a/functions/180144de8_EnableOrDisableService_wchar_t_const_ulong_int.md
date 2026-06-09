# _EnableOrDisableService(wchar_t const *,ulong &,int)

- ea: `0x180144de8`
- end: `0x180145195`
- name: `?_EnableOrDisableService@@YAKPEB_WAEAKH@Z`
- size: `941`
- prototype: `unsigned int __fastcall(const wchar_t *, unsigned int *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180145b20`

## callees

- `0x1800495c0`
- `0x1800f61f8`
- `0x180119140`
- `0x18014094c`
- `0x180144de8`
- `0x180149c64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180144e3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180144e43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180144f0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180144f5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145011`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801450e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801450f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180144e3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180144e43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180144f0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180144f5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145011`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801450e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801450f1`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1801450da`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1801450da`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180144f00`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180144ffa`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180144f00`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180144ffa`
- `WDSCORE!CurrentIP` at `0x180144e4b`
- `WDSCORE!CurrentIP` at `0x180144f66`
- `WDSCORE!CurrentIP` at `0x180145019`
- `WDSCORE!CurrentIP` at `0x1801450f9`
- `WDSCORE!CurrentIP` at `0x180144e4b`
- `WDSCORE!CurrentIP` at `0x180144f66`
- `WDSCORE!CurrentIP` at `0x180145019`
- `WDSCORE!CurrentIP` at `0x1801450f9`
- `WDSCORE!WdsSetupLogMessageW` at `0x180144eb0`
- `WDSCORE!WdsSetupLogMessageW` at `0x180144fd0`
- `WDSCORE!WdsSetupLogMessageW` at `0x180145083`
- `WDSCORE!WdsSetupLogMessageW` at `0x180145163`
- `WDSCORE!WdsSetupLogMessageW` at `0x180144eb0`
- `WDSCORE!WdsSetupLogMessageW` at `0x180144fd0`
- `WDSCORE!WdsSetupLogMessageW` at `0x180145083`
- `WDSCORE!WdsSetupLogMessageW` at `0x180145163`

## string_xrefs

- `0x180144e8a`: `onecoreuap\base\appmodel\search\mssrch\dll\sysprep.cxx`
- `0x180144faa`: `onecoreuap\base\appmodel\search\mssrch\dll\sysprep.cxx`
- `0x18014505d`: `onecoreuap\base\appmodel\search\mssrch\dll\sysprep.cxx`
- `0x18014513d`: `onecoreuap\base\appmodel\search\mssrch\dll\sysprep.cxx`
- `0x180144e7e`: `_EnableOrDisableService`
- `0x180144f9e`: `_EnableOrDisableService`
- `0x180145051`: `_EnableOrDisableService`
- `0x180145131`: `_EnableOrDisableService`
- `0x180144e5a`: `MSS: Error 0x%X occurred while obtaining service handle for %ls in call _EnableOrDisableService.`
- `0x180144f7a`: `MSS: QueryServiceConfig call failed with error  0x%X for service %ls.`
- `0x18014502d`: `MSS: QueryServiceConfig call failed with error  0x%X for service %ls.`
- `0x18014510d`: `MSS: QueryServiceConfig call failed with error  0x%X for service %ls.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall _EnableOrDisableService(const wchar_t *a1, unsigned int *a2, DWORD a3, const wchar_t *a4)
{
  DWORD v4; // edi
  SC_HANDLE v7; // rbx
  DWORD LastError; // r15d
  DWORD v9; // esi
  __int64 v10; // rdi
  struct tagLOG_PARTIAL_MSG *v11; // rax
  struct _QUERY_SERVICE_CONFIGW *v12; // r13
  DWORD v13; // esi
  __int64 v14; // rdi
  struct tagLOG_PARTIAL_MSG *v15; // rax
  DWORD v16; // esi
  __int64 v17; // rdi
  struct tagLOG_PARTIAL_MSG *v18; // rax
  DWORD v19; // r8d
  DWORD v20; // edi
  __int64 v21; // rbx
  struct tagLOG_PARTIAL_MSG *v22; // rax
  SC_HANDLE hService; // [rsp+60h] [rbp-68h] BYREF
  int v25; // [rsp+68h] [rbp-60h] BYREF
  DWORD cbBufSize; // [rsp+70h] [rbp-58h]
  struct _QUERY_SERVICE_CONFIGW *v27; // [rsp+78h] [rbp-50h]
  int v28; // [rsp+80h] [rbp-48h]
  void *retaddr; // [rsp+C8h] [rbp+0h]
  DWORD pcbBytesNeeded; // [rsp+E0h] [rbp+18h] BYREF

  pcbBytesNeeded = a3;
  v4 = a3;
  CSafeServiceHandle::CSafeServiceHandle((CSafeServiceHandle *)&hService, a1, 0xF01FFu, a4);
  v7 = hService;
  if ( hService )
  {
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
    v9 = GetLastError();
    v10 = CurrentIP();
    v11 = ConstructPartialMsgW(
            0x2000000u,
            "MSS: Error 0x%X occurred while obtaining service handle for %ls in call _EnableOrDisableService.",
            LastError,
            a1);
    WdsSetupLogMessageW(
      v11,
      983040,
      L"D",
      0,
      727,
      L"onecoreuap\\base\\appmodel\\search\\mssrch\\dll\\sysprep.cxx",
      L"_EnableOrDisableService",
      v10,
      v9,
      0,
      0);
    v4 = pcbBytesNeeded;
  }
  v12 = 0;
  v27 = 0;
  cbBufSize = 0;
  v25 = 0;
  v28 = 0;
  if ( LastError )
  {
    if ( v4 )
      goto LABEL_14;
LABEL_15:
    v19 = *a2;
    goto LABEL_16;
  }
  if ( !v4 )
    goto LABEL_15;
  pcbBytesNeeded = 0;
  if ( QueryServiceConfigW(v7, 0, 0, &pcbBytesNeeded) )
    goto LABEL_10;
  LastError = GetLastError();
  if ( LastError == 122 && pcbBytesNeeded )
  {
    try
    {
      LastError = 0;
      CBlob::Allocate((CBlob *)&v25, pcbBytesNeeded);
      v12 = v27;
    }
    catch ( ... )
    {
      indexer::result::details::result_from_caught_exception<1>(
        retaddr,
        747,
        "onecoreuap\\base\\appmodel\\search\\mssrch\\dll\\sysprep.cxx");
    }
    goto LABEL_10;
  }
  v13 = GetLastError();
  v14 = CurrentIP();
  v15 = ConstructPartialMsgW(
          0x2000000u,
          "MSS: QueryServiceConfig call failed with error  0x%X for service %ls.",
          LastError,
          a1);
  WdsSetupLogMessageW(
    v15,
    983040,
    L"D",
    0,
    757,
    L"onecoreuap\\base\\appmodel\\search\\mssrch\\dll\\sysprep.cxx",
    L"_EnableOrDisableService",
    v14,
    v13,
    0,
    0);
  if ( !LastError )
  {
LABEL_10:
    pcbBytesNeeded = 0;
    if ( QueryServiceConfigW(v7, v12, cbBufSize, &pcbBytesNeeded) )
    {
      *a2 = v12->dwStartType;
    }
    else
    {
      LastError = GetLastError();
      v16 = GetLastError();
      v17 = CurrentIP();
      v18 = ConstructPartialMsgW(
              0x2000000u,
              "MSS: QueryServiceConfig call failed with error  0x%X for service %ls.",
              LastError,
              a1);
      WdsSetupLogMessageW(
        v18,
        983040,
        L"D",
        0,
        773,
        L"onecoreuap\\base\\appmodel\\search\\mssrch\\dll\\sysprep.cxx",
        L"_EnableOrDisableService",
        v17,
        v16,
        0,
        0);
    }
  }
LABEL_14:
  v19 = 4;
LABEL_16:
  if ( !LastError && !ChangeServiceConfigW(v7, 0xFFFFFFFF, v19, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
  {
    LastError = GetLastError();
    v20 = GetLastError();
    v21 = CurrentIP();
    v22 = ConstructPartialMsgW(
            0x2000000u,
            "MSS: QueryServiceConfig call failed with error  0x%X for service %ls.",
            LastError,
            a1);
    WdsSetupLogMessageW(
      v22,
      983040,
      L"D",
      0,
      803,
      L"onecoreuap\\base\\appmodel\\search\\mssrch\\dll\\sysprep.cxx",
      L"_EnableOrDisableService",
      v21,
      v20,
      0,
      0);
  }
  CBlob::Free((CBlob *)&v25);
  CSafeServiceHandle::~CSafeServiceHandle((CSafeServiceHandle *)&hService);
  return LastError;
}

```

## disassembly

```asm
0x180144de8  mov     rax, rsp
0x180144deb  mov     [rax+18h], r8d
0x180144def  mov     [rax+10h], rdx
0x180144df3  mov     [rax+8], rcx
0x180144df7  push    rbx
0x180144df8  push    rsi
0x180144df9  push    rdi
0x180144dfa  push    r12
0x180144dfc  push    r13
0x180144dfe  push    r14
0x180144e00  push    r15
0x180144e02  sub     rsp, 90h
0x180144e09  mov     edi, r8d
0x180144e0c  mov     r12, rdx
0x180144e0f  mov     r13, rcx
0x180144e12  mov     r8d, 0F01FFh; unsigned int
0x180144e18  mov     rdx, rcx; wchar_t *
0x180144e1b  lea     rcx, [rax-68h]; this
0x180144e1f  call    ??0CSafeServiceHandle@@QEAA@PEB_WK0@Z; CSafeServiceHandle::CSafeServiceHandle(wchar_t const *,ulong,wchar_t const *)
0x180144e24  nop
0x180144e25  mov     rbx, [rsp+0C8h+hService]
0x180144e2a  xor     r14d, r14d
0x180144e2d  test    rbx, rbx
0x180144e30  jz      short loc_180144E3A
0x180144e32  mov     r15d, r14d
0x180144e35  jmp     loc_180144EBD
0x180144e3a  call    cs:__imp_GetLastError
0x180144e40  mov     r15d, eax
0x180144e43  call    cs:__imp_GetLastError
0x180144e49  mov     esi, eax
0x180144e4b  call    cs:__imp_CurrentIP
0x180144e51  mov     rdi, rax
0x180144e54  mov     r9, r13
0x180144e57  mov     r8d, r15d
0x180144e5a  lea     rdx, aMssError0xXOcc; "MSS: Error 0x%X occurred while obtainin"...
0x180144e61  mov     ecx, 2000000h; unsigned int
0x180144e66  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180144e6b  mov     dword ptr [rsp+0C8h+lpDisplayName], r14d
0x180144e70  mov     [rsp+0C8h+lpPassword], r14
0x180144e75  mov     dword ptr [rsp+0C8h+lpServiceStartName], esi
0x180144e79  mov     [rsp+0C8h+lpDependencies], rdi
0x180144e7e  lea     rsi, aEnableordisabl; "_EnableOrDisableService"
0x180144e85  mov     [rsp+0C8h+lpdwTagId], rsi
0x180144e8a  lea     rsi, aOnecoreuapBase_219; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180144e91  mov     [rsp+0C8h+lpLoadOrderGroup], rsi
0x180144e96  mov     dword ptr [rsp+0C8h+lpBinaryPathName], 2D7h
0x180144e9e  xor     r9d, r9d
0x180144ea1  lea     r8, aD_2; "D"
0x180144ea8  mov     edx, 0F0000h
0x180144ead  mov     rcx, rax
0x180144eb0  call    cs:__imp_WdsSetupLogMessageW
0x180144eb6  mov     edi, [rsp+0C8h+pcbBytesNeeded]
0x180144ebd  mov     r13, r14
0x180144ec0  mov     [rsp+0C8h+var_50], r14
0x180144ec5  mov     [rsp+0C8h+cbBufSize], r14d
0x180144eca  mov     [rsp+0C8h+var_60], r14d
0x180144ecf  mov     [rsp+0C8h+var_48], r14d
0x180144ed7  test    r15d, r15d
0x180144eda  jnz     loc_180145095
0x180144ee0  test    edi, edi
0x180144ee2  jz      loc_1801450A1
0x180144ee8  mov     [rsp+0C8h+pcbBytesNeeded], r14d
0x180144ef0  lea     r9, [rsp+0C8h+pcbBytesNeeded]; pcbBytesNeeded
0x180144ef8  xor     r8d, r8d; cbBufSize
0x180144efb  xor     edx, edx; lpServiceConfig
0x180144efd  mov     rcx, rbx; hService
0x180144f00  call    cs:__imp_QueryServiceConfigW
0x180144f06  test    eax, eax
0x180144f08  jnz     loc_180144FDF
0x180144f0e  call    cs:__imp_GetLastError
0x180144f14  mov     r15d, eax
0x180144f17  cmp     eax, 7Ah ; 'z'
0x180144f1a  jnz     short loc_180144F5E
0x180144f1c  mov     edx, [rsp+0C8h+pcbBytesNeeded]; unsigned int
0x180144f23  test    edx, edx
0x180144f25  jz      short loc_180144F5E
0x180144f27  mov     r15d, r14d
0x180144f2a  lea     rcx, [rsp+0C8h+var_60]; this
0x180144f2f  call    ?Allocate@CBlob@@QEAAXK@Z; CBlob::Allocate(ulong)
0x180144f34  nop
0x180144f35  mov     r13, [rsp+0C8h+var_50]
0x180144f3a  jmp     loc_180144FDF
0x180144f3f  xor     r14d, r14d
0x180144f42  mov     r12, [rsp+0C8h+arg_8]
0x180144f4a  mov     r15d, [rsp+0C8h+arg_18]
0x180144f52  mov     rbx, [rsp+0C8h+hService]
0x180144f57  mov     r13, [rsp+0C8h+var_50]
0x180144f5c  jmp     short loc_180144FD6
0x180144f5e  call    cs:__imp_GetLastError
0x180144f64  mov     esi, eax
0x180144f66  call    cs:__imp_CurrentIP
0x180144f6c  mov     rdi, rax
0x180144f6f  mov     r9, [rsp+0C8h+arg_0]
0x180144f77  mov     r8d, r15d
0x180144f7a  lea     rdx, aMssQueryservic; "MSS: QueryServiceConfig call failed wit"...
0x180144f81  mov     ecx, 2000000h; unsigned int
0x180144f86  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180144f8b  mov     dword ptr [rsp+0C8h+lpDisplayName], r14d
0x180144f90  mov     [rsp+0C8h+lpPassword], r14
0x180144f95  mov     dword ptr [rsp+0C8h+lpServiceStartName], esi
0x180144f99  mov     [rsp+0C8h+lpDependencies], rdi
0x180144f9e  lea     rcx, aEnableordisabl; "_EnableOrDisableService"
0x180144fa5  mov     [rsp+0C8h+lpdwTagId], rcx
0x180144faa  lea     rcx, aOnecoreuapBase_219; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180144fb1  mov     [rsp+0C8h+lpLoadOrderGroup], rcx
0x180144fb6  mov     dword ptr [rsp+0C8h+lpBinaryPathName], 2F5h
0x180144fbe  xor     r9d, r9d
0x180144fc1  lea     r8, aD_2; "D"
0x180144fc8  mov     edx, 0F0000h
0x180144fcd  mov     rcx, rax
0x180144fd0  call    cs:__imp_WdsSetupLogMessageW
0x180144fd6  test    r15d, r15d
0x180144fd9  jnz     loc_180145099
0x180144fdf  mov     [rsp+0C8h+pcbBytesNeeded], r14d
0x180144fe7  lea     r9, [rsp+0C8h+pcbBytesNeeded]; pcbBytesNeeded
0x180144fef  mov     r8d, [rsp+0C8h+cbBufSize]; cbBufSize
0x180144ff4  mov     rdx, r13; lpServiceConfig
0x180144ff7  mov     rcx, rbx; hService
0x180144ffa  call    cs:__imp_QueryServiceConfigW
0x180145000  test    eax, eax
0x180145002  jnz     loc_18014508B
0x180145008  call    cs:__imp_GetLastError
0x18014500e  mov     r15d, eax
0x180145011  call    cs:__imp_GetLastError
0x180145017  mov     esi, eax
0x180145019  call    cs:__imp_CurrentIP
0x18014501f  mov     rdi, rax
0x180145022  mov     r9, [rsp+0C8h+arg_0]
0x18014502a  mov     r8d, r15d
0x18014502d  lea     rdx, aMssQueryservic; "MSS: QueryServiceConfig call failed wit"...
0x180145034  mov     ecx, 2000000h; unsigned int
0x180145039  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18014503e  mov     dword ptr [rsp+0C8h+lpDisplayName], r14d
0x180145043  mov     [rsp+0C8h+lpPassword], r14
0x180145048  mov     dword ptr [rsp+0C8h+lpServiceStartName], esi
0x18014504c  mov     [rsp+0C8h+lpDependencies], rdi
0x180145051  lea     rcx, aEnableordisabl; "_EnableOrDisableService"
0x180145058  mov     [rsp+0C8h+lpdwTagId], rcx
0x18014505d  lea     rcx, aOnecoreuapBase_219; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180145064  mov     [rsp+0C8h+lpLoadOrderGroup], rcx
0x180145069  mov     dword ptr [rsp+0C8h+lpBinaryPathName], 305h
0x180145071  xor     r9d, r9d
0x180145074  lea     r8, aD_2; "D"
0x18014507b  mov     edx, 0F0000h
0x180145080  mov     rcx, rax
0x180145083  call    cs:__imp_WdsSetupLogMessageW
0x180145089  jmp     short loc_180145099
0x18014508b  mov     eax, [r13+4]
0x18014508f  mov     [r12], eax
0x180145093  jmp     short loc_180145099
0x180145095  test    edi, edi
0x180145097  jz      short loc_1801450A1
0x180145099  mov     r8d, 4
0x18014509f  jmp     short loc_1801450A5
0x1801450a1  mov     r8d, [r12]; dwStartType
0x1801450a5  test    r15d, r15d
0x1801450a8  jnz     loc_18014516A
0x1801450ae  mov     [rsp+0C8h+lpDisplayName], r14; lpDisplayName
0x1801450b3  mov     [rsp+0C8h+lpPassword], r14; lpPassword
0x1801450b8  mov     [rsp+0C8h+lpServiceStartName], r14; lpServiceStartName
0x1801450bd  mov     [rsp+0C8h+lpDependencies], r14; lpDependencies
0x1801450c2  mov     [rsp+0C8h+lpdwTagId], r14; lpdwTagId
0x1801450c7  mov     [rsp+0C8h+lpLoadOrderGroup], r14; lpLoadOrderGroup
0x1801450cc  mov     [rsp+0C8h+lpBinaryPathName], r14; lpBinaryPathName
0x1801450d1  or      edx, 0FFFFFFFFh; dwServiceType
0x1801450d4  mov     r9d, edx; dwErrorControl
0x1801450d7  mov     rcx, rbx; hService
0x1801450da  call    cs:__imp_ChangeServiceConfigW
0x1801450e0  test    eax, eax
0x1801450e2  jnz     loc_18014516A
0x1801450e8  call    cs:__imp_GetLastError
0x1801450ee  mov     r15d, eax
0x1801450f1  call    cs:__imp_GetLastError
0x1801450f7  mov     edi, eax
0x1801450f9  call    cs:__imp_CurrentIP
0x1801450ff  mov     rbx, rax
0x180145102  mov     r9, [rsp+0C8h+arg_0]
0x18014510a  mov     r8d, r15d
0x18014510d  lea     rdx, aMssQueryservic; "MSS: QueryServiceConfig call failed wit"...
0x180145114  mov     ecx, 2000000h; unsigned int
0x180145119  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18014511e  mov     dword ptr [rsp+0C8h+lpDisplayName], r14d
0x180145123  mov     [rsp+0C8h+lpPassword], r14
0x180145128  mov     dword ptr [rsp+0C8h+lpServiceStartName], edi
0x18014512c  mov     [rsp+0C8h+lpDependencies], rbx
0x180145131  lea     rcx, aEnableordisabl; "_EnableOrDisableService"
0x180145138  mov     [rsp+0C8h+lpdwTagId], rcx
0x18014513d  lea     rcx, aOnecoreuapBase_219; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180145144  mov     [rsp+0C8h+lpLoadOrderGroup], rcx
0x180145149  mov     dword ptr [rsp+0C8h+lpBinaryPathName], 323h
0x180145151  xor     r9d, r9d
0x180145154  lea     r8, aD_2; "D"
0x18014515b  mov     edx, 0F0000h
0x180145160  mov     rcx, rax
0x180145163  call    cs:__imp_WdsSetupLogMessageW
0x180145169  nop
0x18014516a  lea     rcx, [rsp+0C8h+var_60]; this
0x18014516f  call    ?Free@CBlob@@AEAAXXZ; CBlob::Free(void)
0x180145174  nop
0x180145175  lea     rcx, [rsp+0C8h+hService]; this
0x18014517a  call    ??1CSafeServiceHandle@@QEAA@XZ; CSafeServiceHandle::~CSafeServiceHandle(void)
0x18014517f  mov     eax, r15d
0x180145182  add     rsp, 90h
0x180145189  pop     r15
0x18014518b  pop     r14
0x18014518d  pop     r13
0x18014518f  pop     r12
0x180145191  pop     rdi
0x180145192  pop     rsi
0x180145193  pop     rbx
0x180145194  retn
```
