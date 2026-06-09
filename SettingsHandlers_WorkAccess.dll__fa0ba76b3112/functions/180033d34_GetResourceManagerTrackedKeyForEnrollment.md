# GetResourceManagerTrackedKeyForEnrollment

- ea: `0x180033d34`
- end: `0x180033ed8`
- name: `GetResourceManagerTrackedKeyForEnrollment`
- size: `420`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800327c4`
- `0x180034548`

## callees

- `0x18000526c`
- `0x1800058fc`
- `0x18002ed1c`
- `0x180033d34`
- `0x1800349f0`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180033d58`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180033d58`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033dba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033e23`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033e70`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033dba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033e23`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033e70`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033d7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033de6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033d7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033de6`

## string_xrefs

- `0x180033e3c`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`
- `0x180033e84`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`

## pseudocode

```c
__int64 __fastcall GetResourceManagerTrackedKeyForEnrollment(LPCWSTR lpSubKey, HKEY *a2)
{
  char IsStateSeparationEnabled; // al
  HKEY v5; // rbx
  unsigned int v6; // eax
  __int64 v7; // rdx
  unsigned int v8; // ebx
  unsigned int v9; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-10h]
  unsigned int phkResulta; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF
  HKEY v15; // [rsp+60h] [rbp+30h] BYREF
  char v16; // [rsp+68h] [rbp+38h] BYREF

  *a2 = 0;
  hKey = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v5 = hKey;
  if ( IsStateSeparationEnabled )
  {
    if ( hKey )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v16);
      RegCloseKey(v5);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v16);
    }
    hKey = 0;
    v6 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"OSDATA\\Software\\Microsoft\\EnterpriseResourceManager\\Tracked",
           0,
           0x20119u,
           &hKey);
    if ( v6 )
    {
      v7 = 168;
LABEL_10:
      v8 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v7,
             (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\accountenthusiast.cpp",
             (const char *)v6,
             phkResult);
      goto LABEL_14;
    }
  }
  else
  {
    if ( hKey )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v16);
      RegCloseKey(v5);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v16);
    }
    hKey = 0;
    v6 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\EnterpriseResourceManager\\Tracked",
           0,
           0x20119u,
           &hKey);
    if ( v6 )
    {
      v7 = 173;
      goto LABEL_10;
    }
  }
  v15 = 0;
  v9 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20119u, &v15);
  if ( v9 )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xB2,
           (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\accountenthusiast.cpp",
           (const char *)v9,
           phkResulta);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v15);
  }
  else
  {
    *a2 = v15;
    v15 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v15);
    v8 = 0;
  }
LABEL_14:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v8;
}

```

## disassembly

```asm
0x180033d34  mov     [rsp-18h+arg_0], rbx
0x180033d39  push    rbp
0x180033d3a  push    rsi
0x180033d3b  push    rdi
0x180033d3c  mov     rbp, rsp
0x180033d3f  sub     rsp, 30h
0x180033d43  mov     rdi, rdx
0x180033d46  mov     qword ptr [rdx], 0
0x180033d4d  mov     rsi, rcx
0x180033d50  mov     [rbp+hKey], 0
0x180033d58  call    cs:__imp_RtlIsStateSeparationEnabled
0x180033d5f  nop     dword ptr [rax+rax+00h]
0x180033d64  mov     rbx, [rbp+hKey]
0x180033d68  test    al, al
0x180033d6a  jz      short loc_180033DD5
0x180033d6c  test    rbx, rbx
0x180033d6f  jz      short loc_180033D92
0x180033d71  lea     rcx, [rbp+arg_18]; this
0x180033d75  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180033d7a  mov     rcx, rbx; hKey
0x180033d7d  call    cs:__imp_RegCloseKey
0x180033d84  nop     dword ptr [rax+rax+00h]
0x180033d89  lea     rcx, [rbp+arg_18]; this
0x180033d8d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180033d92  lea     rax, [rbp+hKey]
0x180033d96  mov     [rbp+hKey], 0
0x180033d9e  mov     r9d, 20119h; samDesired
0x180033da4  mov     qword ptr [rsp+30h+phkResult], rax; phkResult
0x180033da9  xor     r8d, r8d; ulOptions
0x180033dac  lea     rdx, SubKey; "OSDATA\\Software\\Microsoft\\Enterprise"...
0x180033db3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180033dba  call    cs:__imp_RegOpenKeyExW
0x180033dc1  nop     dword ptr [rax+rax+00h]
0x180033dc6  test    eax, eax
0x180033dc8  jz      loc_180033E4F
0x180033dce  mov     edx, 0A8h
0x180033dd3  jmp     short loc_180033E38
0x180033dd5  test    rbx, rbx
0x180033dd8  jz      short loc_180033DFB
0x180033dda  lea     rcx, [rbp+arg_18]; this
0x180033dde  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180033de3  mov     rcx, rbx; hKey
0x180033de6  call    cs:__imp_RegCloseKey
0x180033ded  nop     dword ptr [rax+rax+00h]
0x180033df2  lea     rcx, [rbp+arg_18]; this
0x180033df6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180033dfb  lea     rax, [rbp+hKey]
0x180033dff  mov     [rbp+hKey], 0
0x180033e07  mov     r9d, 20119h; samDesired
0x180033e0d  mov     qword ptr [rsp+30h+phkResult], rax; unsigned int
0x180033e12  xor     r8d, r8d; ulOptions
0x180033e15  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\EnterpriseResource"...
0x180033e1c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180033e23  call    cs:__imp_RegOpenKeyExW
0x180033e2a  nop     dword ptr [rax+rax+00h]
0x180033e2f  test    eax, eax
0x180033e31  jz      short loc_180033E4F
0x180033e33  mov     edx, 0ADh; void *
0x180033e38  mov     rcx, [rbp+18h]; this
0x180033e3c  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x180033e43  mov     r9d, eax; char *
0x180033e46  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180033e4b  mov     ebx, eax
0x180033e4d  jmp     short loc_180033EBF
0x180033e4f  mov     rcx, [rbp+hKey]; hKey
0x180033e53  lea     rax, [rbp+arg_10]
0x180033e57  mov     r9d, 20119h; samDesired
0x180033e5d  mov     qword ptr [rsp+30h+phkResult], rax; unsigned int
0x180033e62  xor     r8d, r8d; ulOptions
0x180033e65  mov     [rbp+arg_10], 0
0x180033e6d  mov     rdx, rsi; lpSubKey
0x180033e70  call    cs:__imp_RegOpenKeyExW
0x180033e77  nop     dword ptr [rax+rax+00h]
0x180033e7c  test    eax, eax
0x180033e7e  jz      short loc_180033EA5
0x180033e80  mov     rcx, [rbp+18h]; this
0x180033e84  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x180033e8b  mov     r9d, eax; char *
0x180033e8e  mov     edx, 0B2h; void *
0x180033e93  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180033e98  lea     rcx, [rbp+arg_10]
0x180033e9c  mov     ebx, eax
0x180033e9e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180033ea3  jmp     short loc_180033EBF
0x180033ea5  mov     rax, [rbp+arg_10]
0x180033ea9  lea     rcx, [rbp+arg_10]
0x180033ead  mov     [rdi], rax
0x180033eb0  mov     [rbp+arg_10], 0
0x180033eb8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180033ebd  xor     ebx, ebx
0x180033ebf  lea     rcx, [rbp+hKey]
0x180033ec3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180033ec8  mov     eax, ebx
0x180033eca  mov     rbx, [rsp+30h+arg_0]
0x180033ecf  add     rsp, 30h
0x180033ed3  pop     rdi
0x180033ed4  pop     rsi
0x180033ed5  pop     rbp
0x180033ed6  retn
```
