# OSIntegration::DEH::ErrorReportingExtensionHandler::ProcessErrorReportingModules(OSIntegration::DEH::ErrorReportingModule,bool,bool)

- ea: `0x18010a59c`
- end: `0x18010a84d`
- name: `?ProcessErrorReportingModules@ErrorReportingExtensionHandler@DEH@OSIntegration@@AEAAXUErrorReportingModule@23@_N1@Z`
- size: `689`
- prototype: `__int64 __fastcall(__int64, __int64, char, char)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18010a2f4`
- `0x18010a344`

## callees

- `0x18003193c`
- `0x180033ca0`
- `0x180066780`
- `0x1800aed10`
- `0x1800ef2ec`
- `0x18010a478`
- `0x18010a59c`
- `0x18010a9f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18010a60c`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18010a60c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010a71c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010a71c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010a76d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010a76d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18010a7ae`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18010a7ae`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18010a6c5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18010a6c5`
- `ntdll!RtlWow64IsWowGuestMachineSupported` at `0x18010a64a`
- `ntdll!RtlWow64IsWowGuestMachineSupported` at `0x18010a64a`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x18010a676`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x18010a7fb`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x18010a676`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x18010a7fb`

## string_xrefs

- `0x18010a623`: `onecore\admin\appmodel\osim\src\deh\errorreporting\errorreportingextensionhandler.cpp`
- `0x18010a6dc`: `onecore\admin\appmodel\osim\src\deh\errorreporting\errorreportingextensionhandler.cpp`
- `0x18010a753`: `onecore\admin\appmodel\osim\src\deh\errorreporting\errorreportingextensionhandler.cpp`
- `0x18010a789`: `onecore\admin\appmodel\osim\src\deh\errorreporting\errorreportingextensionhandler.cpp`
- `0x18010a7e0`: `onecore\admin\appmodel\osim\src\deh\errorreporting\errorreportingextensionhandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OSIntegration::DEH::ErrorReportingExtensionHandler::ProcessErrorReportingModules(
        __int64 a1,
        __int64 a2,
        char a3,
        char a4)
{
  HKEY *v7; // rax
  unsigned int v8; // eax
  HKEY v9; // rdi
  int IsWowGuestMachineSupported; // eax
  void *v11; // rdx
  unsigned int v12; // r8d
  REGSAM samDesired; // esi
  HKEY *phkResult; // rax
  unsigned int Key; // eax
  const WCHAR *v16; // rdx
  unsigned int v17; // eax
  unsigned int v18; // r8d
  unsigned int v19; // edi
  unsigned int v20; // eax
  const WCHAR *v21; // rdx
  unsigned int v22; // eax
  unsigned int v23; // r8d
  unsigned int v24; // edi
  unsigned int dwOptions; // [rsp+20h] [rbp-39h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-39h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-39h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-39h]
  unsigned int dwOptionsd; // [rsp+20h] [rbp-39h]
  unsigned int dwOptionse; // [rsp+20h] [rbp-39h]
  _BYTE v32[4]; // [rsp+50h] [rbp-9h] BYREF
  unsigned __int16 v33; // [rsp+54h] [rbp-5h] BYREF
  HKEY v34; // [rsp+58h] [rbp-1h] BYREF
  BYTE Data[8]; // [rsp+60h] [rbp+7h] BYREF
  HKEY hKey[2]; // [rsp+68h] [rbp+Fh] BYREF
  char v37; // [rsp+78h] [rbp+1Fh]
  __int64 v38; // [rsp+80h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v38 = a2;
  hKey[0] = 0;
  v34 = 0;
  v33 = 0;
  v32[0] = 0;
  hKey[1] = (HKEY)&v33;
  v37 = 1;
  if ( *(_BYTE *)(a1 + 40) )
  {
    v7 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(hKey);
    v8 = RegOpenCurrentUser(0x20019u, v7);
    if ( v8 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xEA,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\errorreporting\\errorreportingextensionhandler.cpp",
        (const char *)v8,
        dwOptions);
    v9 = hKey[0];
  }
  else
  {
    v9 = HKEY_LOCAL_MACHINE;
  }
  IsWowGuestMachineSupported = RtlWow64IsWowGuestMachineSupported(*(unsigned __int16 *)(a2 + 32), v32);
  if ( IsWowGuestMachineSupported < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      v11,
      v12,
      (const char *)(unsigned int)IsWowGuestMachineSupported,
      dwOptions);
  samDesired = 983103;
  if ( v32[0] )
  {
    v33 = Wow64SetThreadDefaultGuestMachine(*(unsigned __int16 *)(a2 + 32));
    samDesired = 983615;
  }
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v34);
  if ( a3 )
  {
    Key = RegCreateKeyExW(
            v9,
            L"Software\\Microsoft\\Windows\\Windows Error Reporting\\RuntimeExceptionHelperModules",
            0,
            0,
            0,
            samDesired,
            0,
            phkResult,
            0);
    if ( Key )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x103,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\errorreporting\\errorreportingextensionhandler.cpp",
        (const char *)Key,
        dwOptionsa);
    *(_DWORD *)Data = 0;
    if ( *(_QWORD *)(a2 + 24) <= 7u )
      v16 = (const WCHAR *)a2;
    else
      v16 = *(const WCHAR **)a2;
    v17 = RegSetValueExW(v34, v16, 0, 4u, Data, 4u);
    v19 = v17;
    if ( v17 )
    {
      wil::details::in1diag3::Log_Win32(retaddr, (void *)0x10B, v18, (const char *)v17, dwOptionsb);
      if ( !a4 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x10E,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\errorreporting\\errorreportingextensionhandler.cpp",
          (const char *)v19,
          dwOptionsc);
    }
  }
  else
  {
    v20 = RegOpenKeyExW(
            v9,
            L"Software\\Microsoft\\Windows\\Windows Error Reporting\\RuntimeExceptionHelperModules",
            0,
            samDesired,
            phkResult);
    if ( v20 != 2 )
    {
      if ( v20 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x11B,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\errorreporting\\errorreportingextensionhandler.cpp",
          (const char *)v20,
          dwOptionsd);
      if ( *(_QWORD *)(a2 + 24) <= 7u )
        v21 = (const WCHAR *)a2;
      else
        v21 = *(const WCHAR **)a2;
      v22 = RegDeleteValueW(v34, v21);
      v24 = v22;
      if ( (v22 & 0xFFFFFFFD) != 0 )
      {
        wil::details::in1diag3::Log_Win32(retaddr, (void *)0x123, v23, (const char *)v22, dwOptionsd);
        if ( !a4 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x126,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\errorreporting\\errorreportingextensionhandler.cpp",
            (const char *)v24,
            dwOptionse);
      }
    }
  }
  if ( v33 )
    Wow64SetThreadDefaultGuestMachine(v33);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v34);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
  return std::wstring::_Tidy_deallocate(a2);
}

```

## disassembly

```asm
0x18010a59c  mov     [rsp-8+arg_0], rbx
0x18010a5a1  mov     [rsp-8+arg_10], rsi
0x18010a5a6  push    rbp
0x18010a5a7  push    rdi
0x18010a5a8  push    r12
0x18010a5aa  push    r14
0x18010a5ac  push    r15
0x18010a5ae  lea     rbp, [rsp-37h]
0x18010a5b3  sub     rsp, 90h
0x18010a5ba  mov     rax, cs:__security_cookie
0x18010a5c1  xor     rax, rsp
0x18010a5c4  mov     [rbp+57h+var_28], rax
0x18010a5c8  mov     r14b, r9b
0x18010a5cb  mov     r15b, r8b
0x18010a5ce  mov     rbx, rdx
0x18010a5d1  mov     [rbp+57h+var_30], rdx
0x18010a5d5  xor     r12d, r12d
0x18010a5d8  mov     [rbp+57h+hKey], r12
0x18010a5dc  mov     [rbp+57h+var_58], r12
0x18010a5e0  mov     [rbp+57h+var_5C], r12w
0x18010a5e5  mov     [rbp+57h+var_60], r12b
0x18010a5e9  lea     rax, [rbp+57h+var_5C]
0x18010a5ed  mov     [rbp+57h+var_40], rax
0x18010a5f1  mov     [rbp+57h+var_38], 1
0x18010a5f5  cmp     [rcx+28h], r12b
0x18010a5f9  jz      short loc_18010A63B
0x18010a5fb  lea     rcx, [rbp+57h+hKey]
0x18010a5ff  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18010a604  mov     rdx, rax; phkResult
0x18010a607  mov     ecx, 20019h; samDesired
0x18010a60c  call    cs:__imp_RegOpenCurrentUser
0x18010a613  nop     dword ptr [rax+rax+00h]
0x18010a618  mov     rcx, [rbp+5Fh]; this
0x18010a61c  test    eax, eax
0x18010a61e  jz      short loc_18010A635
0x18010a620  mov     r9d, eax; char *
0x18010a623  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18010a62a  mov     edx, 0EAh; void *
0x18010a62f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18010a635  mov     rdi, [rbp+57h+hKey]
0x18010a639  jmp     short loc_18010A642
0x18010a63b  mov     rdi, 0FFFFFFFF80000002h
0x18010a642  lea     rdx, [rbp+57h+var_60]
0x18010a646  movzx   ecx, word ptr [rbx+20h]
0x18010a64a  call    cs:__imp_RtlWow64IsWowGuestMachineSupported
0x18010a651  nop     dword ptr [rax+rax+00h]
0x18010a656  mov     rcx, [rbp+5Fh]; this
0x18010a65a  test    eax, eax
0x18010a65c  jns     short loc_18010A667
0x18010a65e  mov     r9d, eax; char *
0x18010a661  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18010a667  mov     esi, 0F003Fh
0x18010a66c  cmp     [rbp+57h+var_60], r12b
0x18010a670  jz      short loc_18010A68B
0x18010a672  movzx   ecx, word ptr [rbx+20h]
0x18010a676  call    cs:__imp_Wow64SetThreadDefaultGuestMachine
0x18010a67d  nop     dword ptr [rax+rax+00h]
0x18010a682  mov     [rbp+57h+var_5C], ax
0x18010a686  mov     esi, 0F023Fh
0x18010a68b  lea     rcx, [rbp+57h+var_58]
0x18010a68f  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18010a694  xor     r8d, r8d; ulOptions
0x18010a697  lea     rdx, aSoftwareMicros_19; "Software\\Microsoft\\Windows\\Windows E"...
0x18010a69e  mov     rcx, rdi; hKey
0x18010a6a1  test    r15b, r15b
0x18010a6a4  jz      loc_18010A765
0x18010a6aa  mov     [rsp+0B0h+lpdwDisposition], r12; lpdwDisposition
0x18010a6af  mov     [rsp+0B0h+phkResult], rax; phkResult
0x18010a6b4  mov     [rsp+0B0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18010a6b9  mov     [rsp+0B0h+samDesired], esi; samDesired
0x18010a6bd  mov     [rsp+0B0h+dwOptions], r12d; unsigned int
0x18010a6c2  xor     r9d, r9d; lpClass
0x18010a6c5  call    cs:__imp_RegCreateKeyExW
0x18010a6cc  nop     dword ptr [rax+rax+00h]
0x18010a6d1  mov     rcx, [rbp+5Fh]; this
0x18010a6d5  test    eax, eax
0x18010a6d7  jz      short loc_18010A6EE
0x18010a6d9  mov     r9d, eax; char *
0x18010a6dc  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18010a6e3  mov     edx, 103h; void *
0x18010a6e8  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18010a6ee  mov     dword ptr [rbp+57h+Data], r12d
0x18010a6f2  cmp     qword ptr [rbx+18h], 7
0x18010a6f7  jbe     short loc_18010A6FE
0x18010a6f9  mov     rdx, [rbx]
0x18010a6fc  jmp     short loc_18010A701
0x18010a6fe  mov     rdx, rbx; lpValueName
0x18010a701  mov     r9d, 4; dwType
0x18010a707  mov     [rsp+0B0h+samDesired], r9d; cbData
0x18010a70c  lea     rax, [rbp+57h+Data]
0x18010a710  mov     qword ptr [rsp+0B0h+dwOptions], rax; unsigned int
0x18010a715  xor     r8d, r8d; Reserved
0x18010a718  mov     rcx, [rbp+57h+var_58]; hKey
0x18010a71c  call    cs:__imp_RegSetValueExW
0x18010a723  nop     dword ptr [rax+rax+00h]
0x18010a728  mov     edi, eax
0x18010a72a  test    eax, eax
0x18010a72c  jz      loc_18010A7F2
0x18010a732  mov     rcx, [rbp+5Fh]; this
0x18010a736  mov     r9d, eax; char *
0x18010a739  mov     edx, 10Bh; void *
0x18010a73e  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18010a743  test    r14b, r14b
0x18010a746  jnz     loc_18010A7F2
0x18010a74c  mov     rcx, [rbp+5Fh]; this
0x18010a750  mov     r9d, edi; char *
0x18010a753  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18010a75a  mov     edx, 10Eh; void *
0x18010a75f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18010a765  mov     qword ptr [rsp+0B0h+dwOptions], rax; unsigned int
0x18010a76a  mov     r9d, esi; samDesired
0x18010a76d  call    cs:__imp_RegOpenKeyExW
0x18010a774  nop     dword ptr [rax+rax+00h]
0x18010a779  cmp     eax, 2
0x18010a77c  jz      short loc_18010A7F2
0x18010a77e  test    eax, eax
0x18010a780  jz      short loc_18010A79B
0x18010a782  mov     rcx, [rbp+5Fh]; this
0x18010a786  mov     r9d, eax; char *
0x18010a789  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18010a790  mov     edx, 11Bh; void *
0x18010a795  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18010a79b  cmp     qword ptr [rbx+18h], 7
0x18010a7a0  jbe     short loc_18010A7A7
0x18010a7a2  mov     rdx, [rbx]
0x18010a7a5  jmp     short loc_18010A7AA
0x18010a7a7  mov     rdx, rbx; lpValueName
0x18010a7aa  mov     rcx, [rbp+57h+var_58]; hKey
0x18010a7ae  call    cs:__imp_RegDeleteValueW
0x18010a7b5  nop     dword ptr [rax+rax+00h]
0x18010a7ba  mov     edi, eax
0x18010a7bc  test    eax, 0FFFFFFFDh
0x18010a7c1  jz      short loc_18010A7F2
0x18010a7c3  mov     rcx, [rbp+5Fh]; this
0x18010a7c7  mov     r9d, eax; char *
0x18010a7ca  mov     edx, 123h; void *
0x18010a7cf  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18010a7d4  test    r14b, r14b
0x18010a7d7  jnz     short loc_18010A7F2
0x18010a7d9  mov     rcx, [rbp+5Fh]; this
0x18010a7dd  mov     r9d, edi; char *
0x18010a7e0  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18010a7e7  mov     edx, 126h; void *
0x18010a7ec  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18010a7f2  movzx   ecx, [rbp+57h+var_5C]
0x18010a7f6  test    cx, cx
0x18010a7f9  jz      short loc_18010A808
0x18010a7fb  call    cs:__imp_Wow64SetThreadDefaultGuestMachine
0x18010a802  nop     dword ptr [rax+rax+00h]
0x18010a807  nop
0x18010a808  lea     rcx, [rbp+57h+var_58]
0x18010a80c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010a811  nop
0x18010a812  lea     rcx, [rbp+57h+hKey]
0x18010a816  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010a81b  nop
0x18010a81c  mov     rcx, rbx
0x18010a81f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010a824  mov     rcx, [rbp+57h+var_28]
0x18010a828  xor     rcx, rsp; StackCookie
0x18010a82b  call    __security_check_cookie
0x18010a830  lea     r11, [rsp+0B0h+var_20]
0x18010a838  mov     rbx, [r11+30h]
0x18010a83c  mov     rsi, [r11+40h]
0x18010a840  mov     rsp, r11
0x18010a843  pop     r15
0x18010a845  pop     r14
0x18010a847  pop     r12
0x18010a849  pop     rdi
0x18010a84a  pop     rbp
0x18010a84b  retn
```
