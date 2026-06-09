# GetSharedPCKeyIfExists(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong)

- ea: `0x180016c08`
- end: `0x180016d53`
- name: `?GetSharedPCKeyIfExists@@YAPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `331`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015db0`

## callees

- `0x180003530`
- `0x18000a584`
- `0x18000ccd4`
- `0x18000ccf4`
- `0x18000cd50`
- `0x18000cfc0`
- `0x180013dcc`
- `0x180016c08`
- `0x180016d5c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016c68`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016cbf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016c68`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016cbf`

## string_xrefs

- `0x180016c79`: `shellcommon\shell\sharedpc\accountmanager\Common\sharedpclocalaccountcontroller.h`
- `0x180016cfb`: `shellcommon\shell\sharedpc\accountmanager\Common\sharedpclocalaccountcontroller.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
HKEY GetSharedPCKeyIfExists()
{
  const WCHAR *v0; // rax
  unsigned int v1; // eax
  const WCHAR *v2; // rax
  LSTATUS v3; // eax
  unsigned __int64 v4; // r9
  HKEY v6; // rbx
  unsigned int phkResult; // [rsp+20h] [rbp-50h]
  int phkResulta; // [rsp+20h] [rbp-50h]
  HKEY v10; // [rsp+30h] [rbp-40h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v12[32]; // [rsp+40h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  GetSharedPCTargetPath((__int64)v12);
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v0 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v0, 0, 0x20019u, &hKey);
  if ( v1 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x4E,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\Common\\sharedpclocalaccountcontroller.h",
      (const char *)v1,
      phkResult);
  v10 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v10,
    0);
  v2 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  v3 = RegOpenKeyExW(hKey, v2, 0, 0xF003Fu, &v10);
  v4 = (unsigned int)v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( (int)(v4 + 0x80000000) >= 0 && (_DWORD)v4 != -2147024894 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x52,
      (int)"shellcommon\\shell\\sharedpc\\accountmanager\\Common\\sharedpclocalaccountcontroller.h",
      (const char *)v4,
      phkResulta);
  v6 = v10;
  v10 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v10);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  std::wstring::_Tidy_deallocate((__int64)v12);
  return v6;
}

```

## disassembly

```asm
0x180016c08  mov     [rsp-8+arg_8], rbx
0x180016c0d  push    rbp
0x180016c0e  mov     rbp, rsp
0x180016c11  sub     rsp, 70h
0x180016c15  mov     rax, cs:__security_cookie
0x180016c1c  xor     rax, rsp
0x180016c1f  mov     [rbp+var_10], rax
0x180016c23  mov     rbx, rcx
0x180016c26  lea     rcx, [rbp+var_30]
0x180016c2a  call    ?GetSharedPCTargetPath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GetSharedPCTargetPath(void)
0x180016c2f  nop
0x180016c30  mov     [rbp+hKey], 0
0x180016c38  xor     edx, edx
0x180016c3a  lea     rcx, [rbp+hKey]
0x180016c3e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180016c43  lea     rcx, [rbp+var_30]
0x180016c47  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180016c4c  mov     rdx, rax; lpSubKey
0x180016c4f  lea     rax, [rbp+hKey]
0x180016c53  mov     qword ptr [rsp+70h+phkResult], rax; unsigned int
0x180016c58  mov     r9d, 20019h; samDesired
0x180016c5e  xor     r8d, r8d; ulOptions
0x180016c61  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016c68  call    cs:__imp_RegOpenKeyExW
0x180016c6e  mov     rcx, [rbp+8]; this
0x180016c72  test    eax, eax
0x180016c74  jz      short loc_180016C8B
0x180016c76  mov     r9d, eax; char *
0x180016c79  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\sharedpc\\accountma"...
0x180016c80  mov     edx, 4Eh ; 'N'; void *
0x180016c85  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180016c8b  mov     [rbp+var_40], 0
0x180016c93  xor     edx, edx
0x180016c95  lea     rcx, [rbp+var_40]
0x180016c99  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180016c9e  mov     rcx, rbx
0x180016ca1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180016ca6  lea     rcx, [rbp+var_40]
0x180016caa  mov     qword ptr [rsp+70h+phkResult], rcx; int
0x180016caf  mov     r9d, 0F003Fh; samDesired
0x180016cb5  xor     r8d, r8d; ulOptions
0x180016cb8  mov     rdx, rax; lpSubKey
0x180016cbb  mov     rcx, [rbp+hKey]; hKey
0x180016cbf  call    cs:__imp_RegOpenKeyExW
0x180016cc5  mov     r9d, eax
0x180016cc8  test    eax, eax
0x180016cca  jle     short loc_180016CD7
0x180016ccc  movzx   r9d, ax
0x180016cd0  or      r9d, 80070000h; char *
0x180016cd7  mov     ecx, 80000000h
0x180016cdc  lea     eax, [r9+rcx]
0x180016ce0  test    ecx, eax
0x180016ce2  jnz     short loc_180016CF1
0x180016ce4  cmp     r9d, 80070002h
0x180016ceb  jz      short loc_180016CF1
0x180016ced  mov     al, 1
0x180016cef  jmp     short loc_180016CF3
0x180016cf1  xor     al, al
0x180016cf3  mov     rcx, [rbp+8]; this
0x180016cf7  test    al, al
0x180016cf9  jz      short loc_180016D0D
0x180016cfb  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\sharedpc\\accountma"...
0x180016d02  mov     edx, 52h ; 'R'; void *
0x180016d07  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180016d0d  mov     rbx, [rbp+var_40]
0x180016d11  mov     [rbp+var_40], 0
0x180016d19  lea     rcx, [rbp+var_40]
0x180016d1d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180016d22  nop
0x180016d23  lea     rcx, [rbp+hKey]
0x180016d27  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180016d2c  nop
0x180016d2d  lea     rcx, [rbp+var_30]
0x180016d31  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180016d36  mov     rax, rbx
0x180016d39  mov     rcx, [rbp+var_10]
0x180016d3d  xor     rcx, rsp; StackCookie
0x180016d40  call    __security_check_cookie
0x180016d45  mov     rbx, [rsp+70h+arg_8]
0x180016d4d  add     rsp, 70h
0x180016d51  pop     rbp
0x180016d52  retn
```
