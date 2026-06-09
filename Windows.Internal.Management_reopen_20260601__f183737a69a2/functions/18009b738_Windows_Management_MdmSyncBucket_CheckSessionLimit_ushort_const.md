# Windows::Management::MdmSyncBucket::CheckSessionLimit(ushort const *)

- ea: `0x18009b738`
- end: `0x18009bae5`
- name: `?CheckSessionLimit@MdmSyncBucket@Management@Windows@@SAJPEBG@Z`
- size: `941`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18009bcfc`

## callees

- `0x18000a5c4`
- `0x180016668`
- `0x180016698`
- `0x180033500`
- `0x180038c94`
- `0x180094f14`
- `0x18009b738`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18009b7c6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18009b7c6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009ba8c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009bab1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009ba8c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009bab1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009b7d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009b7d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ba7c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009baa1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ba7c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009baa1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18009b88e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18009b88e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009b820`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009b870`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009b8f7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009b976`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009b820`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009b870`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009b8f7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009b976`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009b9ba`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009ba34`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009b9ba`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009ba34`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009b783`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009b783`

## string_xrefs

- `0x18009b847`: `LastTokenDrain`
- `0x18009ba1b`: `LastTokenDrain`

## pseudocode

```c
__int64 __fastcall Windows::Management::MdmSyncBucket::CheckSessionLimit(LPCWSTR lpSubKey)
{
  unsigned int v1; // ebx
  unsigned int v2; // ebx
  LSTATUS ValueW; // eax
  unsigned int dwLowDateTime; // esi
  LSTATUS v5; // eax
  unsigned __int64 v6; // rbx
  struct _FILETIME v7; // rdi
  int v8; // eax
  unsigned __int64 v9; // rbx
  unsigned int v10; // eax
  unsigned __int64 v11; // rax
  LSTATUS v12; // eax
  unsigned int v13; // ecx
  LSTATUS v14; // eax
  unsigned int v15; // ebx
  LSTATUS v16; // eax
  unsigned int v17; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-39h]
  int phkResulta; // [rsp+20h] [rbp-39h]
  int phkResultc; // [rsp+20h] [rbp-39h]
  int phkResultb; // [rsp+20h] [rbp-39h]
  int phkResultd; // [rsp+20h] [rbp-39h]
  HKEY hkey; // [rsp+40h] [rbp-19h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-11h] BYREF
  HKEY *p_hkey; // [rsp+50h] [rbp-9h] BYREF
  HKEY v27; // [rsp+58h] [rbp-1h] BYREF
  char v28; // [rsp+60h] [rbp+7h]
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+68h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  struct _FILETIME pvData; // [rsp+C8h] [rbp+6Fh] BYREF
  DWORD pcbData; // [rsp+D0h] [rbp+77h] BYREF
  unsigned __int64 pdwType; // [rsp+D8h] [rbp+7Fh] BYREF

  v28 = 1;
  p_hkey = &hkey;
  hkey = 0;
  v27 = 0;
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2001Fu, &v27);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hkey);
  if ( v1 )
  {
    v2 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x319,
           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\winrt\\lib\\mdmsync\\mdmsession.cpp",
           (const char *)v1,
           phkResult);
    goto LABEL_32;
  }
  InitializeCriticalSectionEx(&CriticalSection, 0, 0);
  EnterCriticalSection(&CriticalSection);
  LODWORD(pdwType) = 0;
  pvData.dwLowDateTime = 0;
  pcbData = 4;
  ValueW = RegGetValueW(hkey, 0, L"SessionCount", 0x10u, (LPDWORD)&pdwType, &pvData, &pcbData);
  pcbData = 0;
  pdwType = 0;
  dwLowDateTime = 0;
  if ( !ValueW )
    dwLowDateTime = pvData.dwLowDateTime;
  pvData.dwLowDateTime = 8;
  v5 = RegGetValueW(hkey, 0, L"LastTokenDrain", 0x40u, &pcbData, &pdwType, (LPDWORD)&pvData);
  v6 = 0;
  SystemTimeAsFileTime = 0;
  if ( !v5 )
    v6 = pdwType;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v7 = SystemTimeAsFileTime;
  pvData = 0;
  v8 = ULongLongSub(*(_QWORD *)&SystemTimeAsFileTime, v6, (unsigned __int64 *)&pvData);
  v9 = (unsigned __int64)pvData;
  LODWORD(pdwType) = 0;
  pvData.dwLowDateTime = 0;
  pcbData = 4;
  if ( v8 < 0 )
    v9 = -1;
  if ( RegGetValueW(hkey, 0, L"IntervalDrain", 0x10u, (LPDWORD)&pdwType, &pvData, &pcbData) )
    v10 = 300000000;
  else
    v10 = 10000 * pvData.dwLowDateTime;
  v11 = v9 / v10;
  if ( v11 > 0xFFFFFFFF )
  {
    LODWORD(v11) = -1;
    goto LABEL_16;
  }
  if ( (_DWORD)v11 )
  {
LABEL_16:
    if ( dwLowDateTime < (unsigned int)v11 )
      dwLowDateTime = 0;
    else
      dwLowDateTime -= v11;
  }
  LODWORD(pdwType) = 0;
  pvData.dwLowDateTime = 0;
  pcbData = 4;
  v12 = RegGetValueW(hkey, 0, L"SessionLimit", 0x10u, (LPDWORD)&pdwType, &pvData, &pcbData);
  v13 = 15;
  if ( !v12 )
    v13 = pvData.dwLowDateTime;
  if ( dwLowDateTime >= v13 )
  {
    LeaveCriticalSection(&CriticalSection);
    DeleteCriticalSection(&CriticalSection);
    v2 = -2147023676;
  }
  else
  {
    pvData.dwLowDateTime = dwLowDateTime + 1;
    v14 = RegSetValueExW(hkey, L"SessionCount", 0, 4u, (const BYTE *)&pvData, 4u);
    v15 = v14;
    if ( v14 > 0 )
      v15 = (unsigned __int16)v14 | 0x80070000;
    if ( (v15 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B5,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\winrt\\lib\\mdmsync\\mdmsession.cpp",
        (const char *)v15,
        phkResulta);
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x34C,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\winrt\\lib\\mdmsync\\mdmsession.cpp",
        (const char *)v15,
        phkResultc);
    }
    pvData = v7;
    v16 = RegSetValueExW(hkey, L"LastTokenDrain", 0, 0xBu, (const BYTE *)&pvData, 8u);
    v17 = v16;
    if ( v16 > 0 )
      v17 = (unsigned __int16)v16 | 0x80070000;
    if ( (v17 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2FD,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\winrt\\lib\\mdmsync\\mdmsession.cpp",
        (const char *)v17,
        phkResultb);
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x34D,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\winrt\\lib\\mdmsync\\mdmsession.cpp",
        (const char *)v17,
        phkResultd);
    }
    LeaveCriticalSection(&CriticalSection);
    DeleteCriticalSection(&CriticalSection);
    v2 = 0;
  }
LABEL_32:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return v2;
}

```

## disassembly

```asm
0x18009b738  mov     [rsp-8+arg_0], rbx
0x18009b73d  push    rbp
0x18009b73e  push    rsi
0x18009b73f  push    rdi
0x18009b740  push    r14
0x18009b742  push    r15
0x18009b744  lea     rbp, [rsp-37h]
0x18009b749  sub     rsp, 90h
0x18009b750  lea     rax, [rbp+57h+hkey]
0x18009b754  mov     [rbp+57h+var_50], 1
0x18009b758  mov     [rbp+57h+var_60], rax
0x18009b75c  xor     r14d, r14d
0x18009b75f  lea     rax, [rbp+57h+var_58]
0x18009b763  mov     [rbp+57h+hkey], r14
0x18009b767  mov     rdx, rcx; lpSubKey
0x18009b76a  mov     [rsp+0B0h+phkResult], rax; unsigned int
0x18009b76f  mov     r9d, 2001Fh; samDesired
0x18009b775  mov     [rbp+57h+var_58], r14
0x18009b779  xor     r8d, r8d; ulOptions
0x18009b77c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009b783  call    cs:__imp_RegOpenKeyExW
0x18009b78a  nop     dword ptr [rax+rax+00h]
0x18009b78f  lea     rcx, [rbp+57h+var_60]
0x18009b793  mov     ebx, eax
0x18009b795  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18009b79a  test    ebx, ebx
0x18009b79c  jz      short loc_18009B7BD
0x18009b79e  mov     rcx, [rbp+5Fh]; this
0x18009b7a2  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\winr"...
0x18009b7a9  mov     r9d, ebx; char *
0x18009b7ac  mov     edx, 319h; void *
0x18009b7b1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009b7b6  mov     ebx, eax
0x18009b7b8  jmp     loc_18009BAC2
0x18009b7bd  xor     r8d, r8d; Flags
0x18009b7c0  lea     rcx, [rbp+57h+CriticalSection]; lpCriticalSection
0x18009b7c4  xor     edx, edx; dwSpinCount
0x18009b7c6  call    cs:__imp_InitializeCriticalSectionEx
0x18009b7cd  nop     dword ptr [rax+rax+00h]
0x18009b7d2  lea     rcx, [rbp+57h+CriticalSection]; lpCriticalSection
0x18009b7d6  call    cs:__imp_EnterCriticalSection
0x18009b7dd  nop     dword ptr [rax+rax+00h]
0x18009b7e2  mov     rcx, [rbp+57h+hkey]; hkey
0x18009b7e6  lea     rax, [rbp+57h+arg_10]
0x18009b7ea  mov     [rsp+0B0h+pcbData], rax; pcbData
0x18009b7ef  lea     r8, ?g_syncSessionCount@@3QBGB; "SessionCount"
0x18009b7f6  mov     r15d, 4
0x18009b7fc  mov     dword ptr [rbp+57h+pdwType], r14d
0x18009b800  lea     rax, [rbp+57h+arg_8]
0x18009b804  mov     dword ptr [rbp+57h+arg_8], r14d
0x18009b808  mov     [rsp+0B0h+pvData], rax; pvData
0x18009b80d  xor     edx, edx; lpSubKey
0x18009b80f  lea     rax, [rbp+57h+pdwType]
0x18009b813  mov     [rbp+57h+arg_10], r15d
0x18009b817  lea     r9d, [r15+0Ch]; dwFlags
0x18009b81b  mov     [rsp+0B0h+phkResult], rax; pdwType
0x18009b820  call    cs:__imp_RegGetValueW
0x18009b827  nop     dword ptr [rax+rax+00h]
0x18009b82c  mov     rcx, [rbp+57h+hkey]; hkey
0x18009b830  lea     r9d, [r15+3Ch]; dwFlags
0x18009b834  test    eax, eax
0x18009b836  mov     [rbp+57h+arg_10], r14d
0x18009b83a  lea     rax, [rbp+57h+arg_8]
0x18009b83e  mov     [rbp+57h+pdwType], r14
0x18009b842  mov     [rsp+0B0h+pcbData], rax; pcbData
0x18009b847  lea     r8, ?g_lastSyncTime@@3QBGB; "LastTokenDrain"
0x18009b84e  lea     rax, [rbp+57h+pdwType]
0x18009b852  mov     esi, r14d
0x18009b855  cmovz   esi, dword ptr [rbp+57h+arg_8]
0x18009b859  xor     edx, edx; lpSubKey
0x18009b85b  mov     [rsp+0B0h+pvData], rax; pvData
0x18009b860  lea     rax, [rbp+57h+arg_10]
0x18009b864  mov     [rsp+0B0h+phkResult], rax; pdwType
0x18009b869  mov     dword ptr [rbp+57h+arg_8], 8
0x18009b870  call    cs:__imp_RegGetValueW
0x18009b877  nop     dword ptr [rax+rax+00h]
0x18009b87c  mov     rbx, r14
0x18009b87f  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r14
0x18009b883  test    eax, eax
0x18009b885  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18009b889  cmovz   rbx, [rbp+57h+pdwType]
0x18009b88e  call    cs:__imp_GetSystemTimeAsFileTime
0x18009b895  nop     dword ptr [rax+rax+00h]
0x18009b89a  mov     rdi, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x18009b89e  lea     r8, [rbp+57h+arg_8]; unsigned __int64 *
0x18009b8a2  mov     rcx, rdi; unsigned __int64
0x18009b8a5  mov     [rbp+57h+arg_8], r14
0x18009b8a9  mov     rdx, rbx; unsigned __int64
0x18009b8ac  call    ?ULongLongSub@@YAJ_K0PEA_K@Z; ULongLongSub(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18009b8b1  mov     rbx, [rbp+57h+arg_8]
0x18009b8b5  lea     r9d, [r15+0Ch]; dwFlags
0x18009b8b9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18009b8bd  mov     dword ptr [rbp+57h+pdwType], r14d
0x18009b8c1  test    eax, eax
0x18009b8c3  mov     dword ptr [rbp+57h+arg_8], r14d
0x18009b8c7  lea     rax, [rbp+57h+arg_10]
0x18009b8cb  mov     [rbp+57h+arg_10], r15d
0x18009b8cf  mov     [rsp+0B0h+pcbData], rax; pcbData
0x18009b8d4  lea     r8, ?g_interval@@3QBGB; "IntervalDrain"
0x18009b8db  cmovs   rbx, rcx
0x18009b8df  lea     rax, [rbp+57h+arg_8]
0x18009b8e3  mov     rcx, [rbp+57h+hkey]; hkey
0x18009b8e7  xor     edx, edx; lpSubKey
0x18009b8e9  mov     [rsp+0B0h+pvData], rax; pvData
0x18009b8ee  lea     rax, [rbp+57h+pdwType]
0x18009b8f2  mov     [rsp+0B0h+phkResult], rax; pdwType
0x18009b8f7  call    cs:__imp_RegGetValueW
0x18009b8fe  nop     dword ptr [rax+rax+00h]
0x18009b903  test    eax, eax
0x18009b905  jnz     short loc_18009B910
0x18009b907  imul    eax, dword ptr [rbp+57h+arg_8], 2710h
0x18009b90e  jmp     short loc_18009B915
0x18009b910  mov     eax, 11E1A300h
0x18009b915  mov     ecx, eax
0x18009b917  xor     edx, edx
0x18009b919  mov     rax, rbx
0x18009b91c  div     rcx
0x18009b91f  mov     ecx, 0FFFFFFFFh
0x18009b924  cmp     rax, rcx
0x18009b927  ja      short loc_18009B92F
0x18009b929  test    eax, eax
0x18009b92b  jz      short loc_18009B93C
0x18009b92d  jmp     short loc_18009B931
0x18009b92f  mov     eax, ecx
0x18009b931  cmp     esi, eax
0x18009b933  jb      short loc_18009B939
0x18009b935  sub     esi, eax
0x18009b937  jmp     short loc_18009B93C
0x18009b939  mov     esi, r14d
0x18009b93c  mov     rcx, [rbp+57h+hkey]; hkey
0x18009b940  lea     rax, [rbp+57h+arg_10]
0x18009b944  mov     [rsp+0B0h+pcbData], rax; pcbData
0x18009b949  lea     r8, ?g_syncSessionLimit@@3QBGB; "SessionLimit"
0x18009b950  lea     rax, [rbp+57h+arg_8]
0x18009b954  mov     dword ptr [rbp+57h+pdwType], r14d
0x18009b958  mov     [rsp+0B0h+pvData], rax; pvData
0x18009b95d  mov     r9d, 10h; dwFlags
0x18009b963  lea     rax, [rbp+57h+pdwType]
0x18009b967  mov     dword ptr [rbp+57h+arg_8], r14d
0x18009b96b  xor     edx, edx; lpSubKey
0x18009b96d  mov     [rsp+0B0h+phkResult], rax; pdwType
0x18009b972  mov     [rbp+57h+arg_10], r15d
0x18009b976  call    cs:__imp_RegGetValueW
0x18009b97d  nop     dword ptr [rax+rax+00h]
0x18009b982  test    eax, eax
0x18009b984  mov     ecx, 0Fh
0x18009b989  cmovz   ecx, dword ptr [rbp+57h+arg_8]
0x18009b98d  cmp     esi, ecx
0x18009b98f  jnb     loc_18009BA9D
0x18009b995  mov     rcx, [rbp+57h+hkey]; hKey
0x18009b999  lea     eax, [rsi+1]
0x18009b99c  mov     dword ptr [rbp+57h+arg_8], eax
0x18009b99f  lea     rdx, ?g_syncSessionCount@@3QBGB; "SessionCount"
0x18009b9a6  lea     rax, [rbp+57h+arg_8]
0x18009b9aa  mov     dword ptr [rsp+0B0h+pvData], r15d; cbData
0x18009b9af  mov     r9d, r15d; dwType
0x18009b9b2  mov     [rsp+0B0h+phkResult], rax; int
0x18009b9b7  xor     r8d, r8d; Reserved
0x18009b9ba  call    cs:__imp_RegSetValueExW
0x18009b9c1  nop     dword ptr [rax+rax+00h]
0x18009b9c6  mov     ebx, eax
0x18009b9c8  mov     r15d, 80070000h
0x18009b9ce  test    eax, eax
0x18009b9d0  jle     short loc_18009B9D8
0x18009b9d2  movzx   ebx, ax
0x18009b9d5  or      ebx, r15d
0x18009b9d8  lea     rsi, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\winr"...
0x18009b9df  test    ebx, ebx
0x18009b9e1  jns     short loc_18009BA0B
0x18009b9e3  mov     rcx, [rbp+5Fh]; this
0x18009b9e7  mov     r9d, ebx; char *
0x18009b9ea  mov     r8, rsi; unsigned int
0x18009b9ed  mov     edx, 2B5h; void *
0x18009b9f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009b9f7  mov     rcx, [rbp+5Fh]; this
0x18009b9fb  mov     r9d, ebx; char *
0x18009b9fe  mov     r8, rsi; unsigned int
0x18009ba01  mov     edx, 34Ch; void *
0x18009ba06  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009ba0b  mov     rcx, [rbp+57h+hkey]; hKey
0x18009ba0f  lea     rax, [rbp+57h+arg_8]
0x18009ba13  mov     dword ptr [rsp+0B0h+pvData], 8; cbData
0x18009ba1b  lea     rdx, ?g_lastSyncTime@@3QBGB; "LastTokenDrain"
0x18009ba22  mov     r9d, 0Bh; dwType
0x18009ba28  mov     [rsp+0B0h+phkResult], rax; int
0x18009ba2d  xor     r8d, r8d; Reserved
0x18009ba30  mov     [rbp+57h+arg_8], rdi
0x18009ba34  call    cs:__imp_RegSetValueExW
0x18009ba3b  nop     dword ptr [rax+rax+00h]
0x18009ba40  mov     ebx, eax
0x18009ba42  test    eax, eax
0x18009ba44  jle     short loc_18009BA4C
0x18009ba46  movzx   ebx, ax
0x18009ba49  or      ebx, r15d
0x18009ba4c  test    ebx, ebx
0x18009ba4e  jns     short loc_18009BA78
0x18009ba50  mov     rcx, [rbp+5Fh]; this
0x18009ba54  mov     r9d, ebx; char *
0x18009ba57  mov     r8, rsi; unsigned int
0x18009ba5a  mov     edx, 2FDh; void *
0x18009ba5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009ba64  mov     rcx, [rbp+5Fh]; this
0x18009ba68  mov     r9d, ebx; char *
0x18009ba6b  mov     r8, rsi; unsigned int
0x18009ba6e  mov     edx, 34Dh; void *
0x18009ba73  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009ba78  lea     rcx, [rbp+57h+CriticalSection]; lpCriticalSection
0x18009ba7c  call    cs:__imp_LeaveCriticalSection
0x18009ba83  nop     dword ptr [rax+rax+00h]
0x18009ba88  lea     rcx, [rbp+57h+CriticalSection]; lpCriticalSection
0x18009ba8c  call    cs:__imp_DeleteCriticalSection
0x18009ba93  nop     dword ptr [rax+rax+00h]
0x18009ba98  mov     ebx, r14d
0x18009ba9b  jmp     short loc_18009BAC2
0x18009ba9d  lea     rcx, [rbp+57h+CriticalSection]; lpCriticalSection
0x18009baa1  call    cs:__imp_LeaveCriticalSection
0x18009baa8  nop     dword ptr [rax+rax+00h]
0x18009baad  lea     rcx, [rbp+57h+CriticalSection]; lpCriticalSection
0x18009bab1  call    cs:__imp_DeleteCriticalSection
0x18009bab8  nop     dword ptr [rax+rax+00h]
0x18009babd  mov     ebx, 800704C4h
0x18009bac2  lea     rcx, [rbp+57h+hkey]
0x18009bac6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009bacb  mov     eax, ebx
0x18009bacd  mov     rbx, [rsp+0B0h+arg_0]
0x18009bad5  add     rsp, 90h
0x18009badc  pop     r15
0x18009bade  pop     r14
0x18009bae0  pop     rdi
0x18009bae1  pop     rsi
0x18009bae2  pop     rbp
0x18009bae3  retn
```
