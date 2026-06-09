# HandleValidationForDelegatedApp(HSTRING__ *,HSTRING__ *)

- ea: `0x14000d194`
- end: `0x14000d430`
- name: `?HandleValidationForDelegatedApp@@YAXPEAUHSTRING__@@0@Z`
- size: `668`
- prototype: `void __fastcall(HSTRING string, HSTRING)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000b114`

## callees

- `0x14000a13c`
- `0x14000c2c0`
- `0x14000cf8c`
- `0x14000d194`
- `0x14000fc20`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000d1c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000d1c5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000d203`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000d203`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000d257`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000d257`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000d2a2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000d2e3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000d327`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000d371`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000d3b2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000d3f3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000d2a2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000d2e3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000d327`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000d371`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000d3b2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000d3f3`

## string_xrefs

- `0x14000d3a7`: `LastValidationAttemptTime`
- `0x14000d31c`: `AllowedPaths`

## pseudocode

```c
void __fastcall HandleValidationForDelegatedApp(HSTRING string, HSTRING a2)
{
  const WCHAR *StringRawBuffer; // rax
  unsigned int v4; // eax
  int v5; // r8d
  unsigned int v6; // eax
  int v7; // r8d
  unsigned int v8; // eax
  int v9; // r8d
  unsigned int v10; // eax
  int v11; // r8d
  unsigned int v12; // eax
  int v13; // r8d
  unsigned int v14; // eax
  int v15; // r8d
  unsigned int v16; // eax
  int v17; // r8d
  unsigned int v18; // eax
  int v19; // r8d
  unsigned int dwOptions; // [rsp+20h] [rbp-50h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-50h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-50h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-50h]
  unsigned int dwOptionsd; // [rsp+20h] [rbp-50h]
  unsigned int dwOptionse; // [rsp+20h] [rbp-50h]
  unsigned int dwOptionsf; // [rsp+20h] [rbp-50h]
  unsigned int dwOptionsg; // [rsp+20h] [rbp-50h]
  DWORD cbData; // [rsp+50h] [rbp-20h] BYREF
  BYTE v29[4]; // [rsp+54h] [rbp-1Ch] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-18h] BYREF
  BYTE v31[8]; // [rsp+60h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]
  DWORD dwDisposition; // [rsp+90h] [rbp+20h] BYREF
  int Data; // [rsp+98h] [rbp+28h] BYREF

  GetSystemApplicationDataKeyForPackage(&hKey, string);
  phkResult = 0;
  dwDisposition = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  v4 = RegCreateKeyExW(hKey, StringRawBuffer, 0, 0, 0, 0xF003Fu, 0, &phkResult, &dwDisposition);
  if ( v4 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x2E9, v5, (const char *)v4, dwOptions);
  if ( dwDisposition == 1 )
    goto LABEL_7;
  Data = 0;
  cbData = 4;
  v6 = RegQueryValueExW(phkResult, L"IsDelegatedValidation", 0, 0, (LPBYTE)&Data, &cbData);
  if ( v6 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x2F6, v7, (const char *)v6, dwOptionsa);
  if ( !Data )
  {
LABEL_7:
    Data = 1;
    v8 = RegSetValueExW(phkResult, L"IsDelegatedValidation", 0, 4u, (const BYTE *)&Data, 4u);
    if ( v8 )
      wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x301, v9, (const char *)v8, dwOptionsb);
    cbData = 1;
    v10 = RegSetValueExW(phkResult, L"IsEnabledByCapability", 0, 4u, (const BYTE *)&cbData, 4u);
    if ( v10 )
      wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x305, v11, (const char *)v10, dwOptionsc);
    v12 = RegSetValueExW(phkResult, L"AllowedPaths", 0, 7u, L"*", 6u);
    if ( v12 )
      wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x30A, v13, (const char *)v12, dwOptionsd);
    *(_QWORD *)v31 = GetCurrentSystemTime();
    v14 = RegSetValueExW(phkResult, L"LastSuccessfulValidationTime", 0, 0xBu, v31, 8u);
    if ( v14 )
      wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x30E, v15, (const char *)v14, dwOptionse);
    v16 = RegSetValueExW(phkResult, L"LastValidationAttemptTime", 0, 0xBu, v31, 8u);
    if ( v16 )
      wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x311, v17, (const char *)v16, dwOptionsf);
    *(_DWORD *)v29 = 0;
    v18 = RegSetValueExW(phkResult, L"FailedValiationCount", 0, 4u, v29, 4u);
    if ( v18 )
      wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x315, v19, (const char *)v18, dwOptionsg);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x14000d194  mov     [rsp-8+arg_0], rbx
0x14000d199  push    rbp
0x14000d19a  mov     rbp, rsp
0x14000d19d  sub     rsp, 70h
0x14000d1a1  mov     rbx, rdx
0x14000d1a4  mov     rdx, rcx; string
0x14000d1a7  lea     rcx, [rbp+hKey]; phkResult
0x14000d1ab  call    ?GetSystemApplicationDataKeyForPackage@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHSTRING__@@@Z; GetSystemApplicationDataKeyForPackage(HSTRING__ *)
0x14000d1b0  nop
0x14000d1b1  mov     [rbp+var_18], 0
0x14000d1b9  mov     [rbp+dwDisposition], 0
0x14000d1c0  xor     edx, edx; length
0x14000d1c2  mov     rcx, rbx; string
0x14000d1c5  call    cs:__imp_WindowsGetStringRawBuffer
0x14000d1cb  lea     rcx, [rbp+dwDisposition]
0x14000d1cf  mov     [rsp+70h+lpdwDisposition], rcx; lpdwDisposition
0x14000d1d4  lea     rcx, [rbp+var_18]
0x14000d1d8  mov     [rsp+70h+phkResult], rcx; phkResult
0x14000d1dd  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14000d1e6  mov     [rsp+70h+samDesired], 0F003Fh; samDesired
0x14000d1ee  mov     [rsp+70h+dwOptions], 0; unsigned int
0x14000d1f6  xor     r9d, r9d; lpClass
0x14000d1f9  xor     r8d, r8d; Reserved
0x14000d1fc  mov     rdx, rax; lpSubKey
0x14000d1ff  mov     rcx, [rbp+hKey]; hKey
0x14000d203  call    cs:__imp_RegCreateKeyExW
0x14000d209  mov     rcx, [rbp+8]; this
0x14000d20d  test    eax, eax
0x14000d20f  jz      short loc_14000D21F
0x14000d211  mov     r9d, eax; char *
0x14000d214  mov     edx, 2E9h; void *
0x14000d219  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x14000d21f  mov     ebx, 4
0x14000d224  cmp     [rbp+dwDisposition], 1
0x14000d228  jz      short loc_14000D27D
0x14000d22a  mov     [rbp+Data], 0
0x14000d231  mov     [rbp+cbData], ebx
0x14000d234  lea     rax, [rbp+cbData]
0x14000d238  mov     qword ptr [rsp+70h+samDesired], rax; lpcbData
0x14000d23d  lea     rax, [rbp+Data]
0x14000d241  mov     qword ptr [rsp+70h+dwOptions], rax; unsigned int
0x14000d246  xor     r9d, r9d; lpType
0x14000d249  xor     r8d, r8d; lpReserved
0x14000d24c  lea     rdx, aIsdelegatedval; "IsDelegatedValidation"
0x14000d253  mov     rcx, [rbp+var_18]; hKey
0x14000d257  call    cs:__imp_RegQueryValueExW
0x14000d25d  mov     rcx, [rbp+8]; this
0x14000d261  test    eax, eax
0x14000d263  jz      short loc_14000D273
0x14000d265  mov     r9d, eax; char *
0x14000d268  mov     edx, 2F6h; void *
0x14000d26d  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x14000d273  cmp     [rbp+Data], 0
0x14000d277  jnz     loc_14000D40F
0x14000d27d  mov     [rbp+Data], 1
0x14000d284  mov     [rsp+70h+samDesired], ebx; cbData
0x14000d288  lea     rax, [rbp+Data]
0x14000d28c  mov     qword ptr [rsp+70h+dwOptions], rax; unsigned int
0x14000d291  mov     r9d, ebx; dwType
0x14000d294  xor     r8d, r8d; Reserved
0x14000d297  lea     rdx, aIsdelegatedval; "IsDelegatedValidation"
0x14000d29e  mov     rcx, [rbp+var_18]; hKey
0x14000d2a2  call    cs:__imp_RegSetValueExW
0x14000d2a8  mov     rcx, [rbp+8]; this
0x14000d2ac  test    eax, eax
0x14000d2ae  jz      short loc_14000D2BE
0x14000d2b0  mov     r9d, eax; char *
0x14000d2b3  mov     edx, 301h; void *
0x14000d2b8  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x14000d2be  mov     [rbp+cbData], 1
0x14000d2c5  mov     [rsp+70h+samDesired], ebx; cbData
0x14000d2c9  lea     rax, [rbp+cbData]
0x14000d2cd  mov     qword ptr [rsp+70h+dwOptions], rax; unsigned int
0x14000d2d2  mov     r9d, ebx; dwType
0x14000d2d5  xor     r8d, r8d; Reserved
0x14000d2d8  lea     rdx, aIsenabledbycap; "IsEnabledByCapability"
0x14000d2df  mov     rcx, [rbp+var_18]; hKey
0x14000d2e3  call    cs:__imp_RegSetValueExW
0x14000d2e9  mov     rcx, [rbp+8]; this
0x14000d2ed  test    eax, eax
0x14000d2ef  jz      short loc_14000D2FF
0x14000d2f1  mov     r9d, eax; char *
0x14000d2f4  mov     edx, 305h; void *
0x14000d2f9  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x14000d2ff  mov     [rsp+70h+samDesired], 6; cbData
0x14000d307  lea     rax, Data; "*"
0x14000d30e  mov     qword ptr [rsp+70h+dwOptions], rax; unsigned int
0x14000d313  mov     r9d, 7; dwType
0x14000d319  xor     r8d, r8d; Reserved
0x14000d31c  lea     rdx, aAllowedpaths; "AllowedPaths"
0x14000d323  mov     rcx, [rbp+var_18]; hKey
0x14000d327  call    cs:__imp_RegSetValueExW
0x14000d32d  mov     rcx, [rbp+8]; this
0x14000d331  test    eax, eax
0x14000d333  jz      short loc_14000D343
0x14000d335  mov     r9d, eax; char *
0x14000d338  mov     edx, 30Ah; void *
0x14000d33d  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x14000d343  call    ?GetCurrentSystemTime@@YA_KXZ; GetCurrentSystemTime(void)
0x14000d348  mov     qword ptr [rbp+var_10], rax
0x14000d34c  mov     [rsp+70h+samDesired], 8; cbData
0x14000d354  lea     rax, [rbp+var_10]
0x14000d358  mov     qword ptr [rsp+70h+dwOptions], rax; unsigned int
0x14000d35d  mov     r9d, 0Bh; dwType
0x14000d363  xor     r8d, r8d; Reserved
0x14000d366  lea     rdx, aLastsuccessful; "LastSuccessfulValidationTime"
0x14000d36d  mov     rcx, [rbp+var_18]; hKey
0x14000d371  call    cs:__imp_RegSetValueExW
0x14000d377  mov     rcx, [rbp+8]; this
0x14000d37b  test    eax, eax
0x14000d37d  jz      short loc_14000D38D
0x14000d37f  mov     r9d, eax; char *
0x14000d382  mov     edx, 30Eh; void *
0x14000d387  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x14000d38d  mov     [rsp+70h+samDesired], 8; cbData
0x14000d395  lea     rax, [rbp+var_10]
0x14000d399  mov     qword ptr [rsp+70h+dwOptions], rax; unsigned int
0x14000d39e  mov     r9d, 0Bh; dwType
0x14000d3a4  xor     r8d, r8d; Reserved
0x14000d3a7  lea     rdx, ValueName; "LastValidationAttemptTime"
0x14000d3ae  mov     rcx, [rbp+var_18]; hKey
0x14000d3b2  call    cs:__imp_RegSetValueExW
0x14000d3b8  mov     rcx, [rbp+8]; this
0x14000d3bc  test    eax, eax
0x14000d3be  jz      short loc_14000D3CE
0x14000d3c0  mov     r9d, eax; char *
0x14000d3c3  mov     edx, 311h; void *
0x14000d3c8  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x14000d3ce  mov     dword ptr [rbp+var_1C], 0
0x14000d3d5  mov     [rsp+70h+samDesired], ebx; cbData
0x14000d3d9  lea     rax, [rbp+var_1C]
0x14000d3dd  mov     qword ptr [rsp+70h+dwOptions], rax; unsigned int
0x14000d3e2  mov     r9d, ebx; dwType
0x14000d3e5  xor     r8d, r8d; Reserved
0x14000d3e8  lea     rdx, aFailedvaliatio; "FailedValiationCount"
0x14000d3ef  mov     rcx, [rbp+var_18]; hKey
0x14000d3f3  call    cs:__imp_RegSetValueExW
0x14000d3f9  mov     rcx, [rbp+8]; this
0x14000d3fd  test    eax, eax
0x14000d3ff  jz      short loc_14000D40F
0x14000d401  mov     r9d, eax; char *
0x14000d404  mov     edx, 315h; void *
0x14000d409  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x14000d40f  lea     rcx, [rbp+var_18]
0x14000d413  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14000d418  nop
0x14000d419  lea     rcx, [rbp+hKey]
0x14000d41d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14000d422  mov     rbx, [rsp+70h+arg_0]
0x14000d42a  add     rsp, 70h
0x14000d42e  pop     rbp
0x14000d42f  retn
```
