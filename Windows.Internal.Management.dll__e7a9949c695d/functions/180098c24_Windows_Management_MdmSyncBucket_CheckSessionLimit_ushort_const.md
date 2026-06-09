# Windows::Management::MdmSyncBucket::CheckSessionLimit(ushort const *)

- ea: `0x180098c24`
- end: `0x180098f7c`
- name: `?CheckSessionLimit@MdmSyncBucket@Management@Windows@@SAJPEBG@Z`
- size: `856`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180099170`

## callees

- `0x18000a2a4`
- `0x180015f40`
- `0x180015f70`
- `0x18003446c`
- `0x180039990`
- `0x1800927b4`
- `0x180098c24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180098cac`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180098cac`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180098f36`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180098f4f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180098f36`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180098f4f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098cb6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098cb6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098f2c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098f45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098f2c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098f45`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180098d5c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180098d5c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180098cfa`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180098d44`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180098dbf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180098e38`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180098cfa`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180098d44`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180098dbf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180098e38`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180098e76`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180098eea`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180098e76`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180098eea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180098c6f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180098c6f`

## string_xrefs

- `0x180098d1b`: `LastTokenDrain`
- `0x180098ed1`: `LastTokenDrain`

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
0x180098c24  mov     [rsp-8+arg_0], rbx
0x180098c29  push    rbp
0x180098c2a  push    rsi
0x180098c2b  push    rdi
0x180098c2c  push    r14
0x180098c2e  push    r15
0x180098c30  lea     rbp, [rsp-37h]
0x180098c35  sub     rsp, 90h
0x180098c3c  lea     rax, [rbp+57h+hkey]
0x180098c40  mov     [rbp+57h+var_50], 1
0x180098c44  mov     [rbp+57h+var_60], rax
0x180098c48  xor     r14d, r14d
0x180098c4b  lea     rax, [rbp+57h+var_58]
0x180098c4f  mov     [rbp+57h+hkey], r14
0x180098c53  mov     rdx, rcx; lpSubKey
0x180098c56  mov     [rsp+0B0h+phkResult], rax; unsigned int
0x180098c5b  mov     r9d, 2001Fh; samDesired
0x180098c61  mov     [rbp+57h+var_58], r14
0x180098c65  xor     r8d, r8d; ulOptions
0x180098c68  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180098c6f  call    cs:__imp_RegOpenKeyExW
0x180098c75  lea     rcx, [rbp+57h+var_60]
0x180098c79  mov     ebx, eax
0x180098c7b  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180098c80  test    ebx, ebx
0x180098c82  jz      short loc_180098CA3
0x180098c84  mov     rcx, [rbp+5Fh]; this
0x180098c88  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\winr"...
0x180098c8f  mov     r9d, ebx; char *
0x180098c92  mov     edx, 319h; void *
0x180098c97  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180098c9c  mov     ebx, eax
0x180098c9e  jmp     loc_180098F5A
0x180098ca3  xor     r8d, r8d; Flags
0x180098ca6  lea     rcx, [rbp+57h+CriticalSection]; lpCriticalSection
0x180098caa  xor     edx, edx; dwSpinCount
0x180098cac  call    cs:__imp_InitializeCriticalSectionEx
0x180098cb2  lea     rcx, [rbp+57h+CriticalSection]; lpCriticalSection
0x180098cb6  call    cs:__imp_EnterCriticalSection
0x180098cbc  mov     rcx, [rbp+57h+hkey]; hkey
0x180098cc0  lea     rax, [rbp+57h+arg_10]
0x180098cc4  mov     [rsp+0B0h+pcbData], rax; pcbData
0x180098cc9  lea     r8, ?g_syncSessionCount@@3QBGB; "SessionCount"
0x180098cd0  mov     r15d, 4
0x180098cd6  mov     dword ptr [rbp+57h+pdwType], r14d
0x180098cda  lea     rax, [rbp+57h+arg_8]
0x180098cde  mov     dword ptr [rbp+57h+arg_8], r14d
0x180098ce2  mov     [rsp+0B0h+pvData], rax; pvData
0x180098ce7  xor     edx, edx; lpSubKey
0x180098ce9  lea     rax, [rbp+57h+pdwType]
0x180098ced  mov     [rbp+57h+arg_10], r15d
0x180098cf1  lea     r9d, [r15+0Ch]; dwFlags
0x180098cf5  mov     [rsp+0B0h+phkResult], rax; pdwType
0x180098cfa  call    cs:__imp_RegGetValueW
0x180098d00  mov     rcx, [rbp+57h+hkey]; hkey
0x180098d04  lea     r9d, [r15+3Ch]; dwFlags
0x180098d08  test    eax, eax
0x180098d0a  mov     [rbp+57h+arg_10], r14d
0x180098d0e  lea     rax, [rbp+57h+arg_8]
0x180098d12  mov     [rbp+57h+pdwType], r14
0x180098d16  mov     [rsp+0B0h+pcbData], rax; pcbData
0x180098d1b  lea     r8, ?g_lastSyncTime@@3QBGB; "LastTokenDrain"
0x180098d22  lea     rax, [rbp+57h+pdwType]
0x180098d26  mov     esi, r14d
0x180098d29  cmovz   esi, dword ptr [rbp+57h+arg_8]
0x180098d2d  xor     edx, edx; lpSubKey
0x180098d2f  mov     [rsp+0B0h+pvData], rax; pvData
0x180098d34  lea     rax, [rbp+57h+arg_10]
0x180098d38  mov     [rsp+0B0h+phkResult], rax; pdwType
0x180098d3d  mov     dword ptr [rbp+57h+arg_8], 8
0x180098d44  call    cs:__imp_RegGetValueW
0x180098d4a  mov     rbx, r14
0x180098d4d  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r14
0x180098d51  test    eax, eax
0x180098d53  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180098d57  cmovz   rbx, [rbp+57h+pdwType]
0x180098d5c  call    cs:__imp_GetSystemTimeAsFileTime
0x180098d62  mov     rdi, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x180098d66  lea     r8, [rbp+57h+arg_8]; unsigned __int64 *
0x180098d6a  mov     rcx, rdi; unsigned __int64
0x180098d6d  mov     [rbp+57h+arg_8], r14
0x180098d71  mov     rdx, rbx; unsigned __int64
0x180098d74  call    ?ULongLongSub@@YAJ_K0PEA_K@Z; ULongLongSub(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180098d79  mov     rbx, [rbp+57h+arg_8]
0x180098d7d  lea     r9d, [r15+0Ch]; dwFlags
0x180098d81  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180098d85  mov     dword ptr [rbp+57h+pdwType], r14d
0x180098d89  test    eax, eax
0x180098d8b  mov     dword ptr [rbp+57h+arg_8], r14d
0x180098d8f  lea     rax, [rbp+57h+arg_10]
0x180098d93  mov     [rbp+57h+arg_10], r15d
0x180098d97  mov     [rsp+0B0h+pcbData], rax; pcbData
0x180098d9c  lea     r8, ?g_interval@@3QBGB; "IntervalDrain"
0x180098da3  cmovs   rbx, rcx
0x180098da7  lea     rax, [rbp+57h+arg_8]
0x180098dab  mov     rcx, [rbp+57h+hkey]; hkey
0x180098daf  xor     edx, edx; lpSubKey
0x180098db1  mov     [rsp+0B0h+pvData], rax; pvData
0x180098db6  lea     rax, [rbp+57h+pdwType]
0x180098dba  mov     [rsp+0B0h+phkResult], rax; pdwType
0x180098dbf  call    cs:__imp_RegGetValueW
0x180098dc5  test    eax, eax
0x180098dc7  jnz     short loc_180098DD2
0x180098dc9  imul    eax, dword ptr [rbp+57h+arg_8], 2710h
0x180098dd0  jmp     short loc_180098DD7
0x180098dd2  mov     eax, 11E1A300h
0x180098dd7  mov     ecx, eax
0x180098dd9  xor     edx, edx
0x180098ddb  mov     rax, rbx
0x180098dde  div     rcx
0x180098de1  mov     ecx, 0FFFFFFFFh
0x180098de6  cmp     rax, rcx
0x180098de9  ja      short loc_180098DF1
0x180098deb  test    eax, eax
0x180098ded  jz      short loc_180098DFE
0x180098def  jmp     short loc_180098DF3
0x180098df1  mov     eax, ecx
0x180098df3  cmp     esi, eax
0x180098df5  jb      short loc_180098DFB
0x180098df7  sub     esi, eax
0x180098df9  jmp     short loc_180098DFE
0x180098dfb  mov     esi, r14d
0x180098dfe  mov     rcx, [rbp+57h+hkey]; hkey
0x180098e02  lea     rax, [rbp+57h+arg_10]
0x180098e06  mov     [rsp+0B0h+pcbData], rax; pcbData
0x180098e0b  lea     r8, ?g_syncSessionLimit@@3QBGB; "SessionLimit"
0x180098e12  lea     rax, [rbp+57h+arg_8]
0x180098e16  mov     dword ptr [rbp+57h+pdwType], r14d
0x180098e1a  mov     [rsp+0B0h+pvData], rax; pvData
0x180098e1f  mov     r9d, 10h; dwFlags
0x180098e25  lea     rax, [rbp+57h+pdwType]
0x180098e29  mov     dword ptr [rbp+57h+arg_8], r14d
0x180098e2d  xor     edx, edx; lpSubKey
0x180098e2f  mov     [rsp+0B0h+phkResult], rax; pdwType
0x180098e34  mov     [rbp+57h+arg_10], r15d
0x180098e38  call    cs:__imp_RegGetValueW
0x180098e3e  test    eax, eax
0x180098e40  mov     ecx, 0Fh
0x180098e45  cmovz   ecx, dword ptr [rbp+57h+arg_8]
0x180098e49  cmp     esi, ecx
0x180098e4b  jnb     loc_180098F41
0x180098e51  mov     rcx, [rbp+57h+hkey]; hKey
0x180098e55  lea     eax, [rsi+1]
0x180098e58  mov     dword ptr [rbp+57h+arg_8], eax
0x180098e5b  lea     rdx, ?g_syncSessionCount@@3QBGB; "SessionCount"
0x180098e62  lea     rax, [rbp+57h+arg_8]
0x180098e66  mov     dword ptr [rsp+0B0h+pvData], r15d; cbData
0x180098e6b  mov     r9d, r15d; dwType
0x180098e6e  mov     [rsp+0B0h+phkResult], rax; int
0x180098e73  xor     r8d, r8d; Reserved
0x180098e76  call    cs:__imp_RegSetValueExW
0x180098e7c  mov     ebx, eax
0x180098e7e  mov     r15d, 80070000h
0x180098e84  test    eax, eax
0x180098e86  jle     short loc_180098E8E
0x180098e88  movzx   ebx, ax
0x180098e8b  or      ebx, r15d
0x180098e8e  lea     rsi, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\winr"...
0x180098e95  test    ebx, ebx
0x180098e97  jns     short loc_180098EC1
0x180098e99  mov     rcx, [rbp+5Fh]; this
0x180098e9d  mov     r9d, ebx; char *
0x180098ea0  mov     r8, rsi; unsigned int
0x180098ea3  mov     edx, 2B5h; void *
0x180098ea8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098ead  mov     rcx, [rbp+5Fh]; this
0x180098eb1  mov     r9d, ebx; char *
0x180098eb4  mov     r8, rsi; unsigned int
0x180098eb7  mov     edx, 34Ch; void *
0x180098ebc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180098ec1  mov     rcx, [rbp+57h+hkey]; hKey
0x180098ec5  lea     rax, [rbp+57h+arg_8]
0x180098ec9  mov     dword ptr [rsp+0B0h+pvData], 8; cbData
0x180098ed1  lea     rdx, ?g_lastSyncTime@@3QBGB; "LastTokenDrain"
0x180098ed8  mov     r9d, 0Bh; dwType
0x180098ede  mov     [rsp+0B0h+phkResult], rax; int
0x180098ee3  xor     r8d, r8d; Reserved
0x180098ee6  mov     [rbp+57h+arg_8], rdi
0x180098eea  call    cs:__imp_RegSetValueExW
0x180098ef0  mov     ebx, eax
0x180098ef2  test    eax, eax
0x180098ef4  jle     short loc_180098EFC
0x180098ef6  movzx   ebx, ax
0x180098ef9  or      ebx, r15d
0x180098efc  test    ebx, ebx
0x180098efe  jns     short loc_180098F28
0x180098f00  mov     rcx, [rbp+5Fh]; this
0x180098f04  mov     r9d, ebx; char *
0x180098f07  mov     r8, rsi; unsigned int
0x180098f0a  mov     edx, 2FDh; void *
0x180098f0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098f14  mov     rcx, [rbp+5Fh]; this
0x180098f18  mov     r9d, ebx; char *
0x180098f1b  mov     r8, rsi; unsigned int
0x180098f1e  mov     edx, 34Dh; void *
0x180098f23  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180098f28  lea     rcx, [rbp+57h+CriticalSection]; lpCriticalSection
0x180098f2c  call    cs:__imp_LeaveCriticalSection
0x180098f32  lea     rcx, [rbp+57h+CriticalSection]; lpCriticalSection
0x180098f36  call    cs:__imp_DeleteCriticalSection
0x180098f3c  mov     ebx, r14d
0x180098f3f  jmp     short loc_180098F5A
0x180098f41  lea     rcx, [rbp+57h+CriticalSection]; lpCriticalSection
0x180098f45  call    cs:__imp_LeaveCriticalSection
0x180098f4b  lea     rcx, [rbp+57h+CriticalSection]; lpCriticalSection
0x180098f4f  call    cs:__imp_DeleteCriticalSection
0x180098f55  mov     ebx, 800704C4h
0x180098f5a  lea     rcx, [rbp+57h+hkey]
0x180098f5e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180098f63  mov     eax, ebx
0x180098f65  mov     rbx, [rsp+0B0h+arg_0]
0x180098f6d  add     rsp, 90h
0x180098f74  pop     r15
0x180098f76  pop     r14
0x180098f78  pop     rdi
0x180098f79  pop     rsi
0x180098f7a  pop     rbp
0x180098f7b  retn
```
