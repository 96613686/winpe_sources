# winrt::Windows::UI::ViewManagement::Core::implementation::GetDesktopRegistryKey(ushort const *)

- ea: `0x18002d628`
- end: `0x18002d6d2`
- name: `?GetDesktopRegistryKey@implementation@Core@ViewManagement@UI@Windows@winrt@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z`
- size: `170`
- prototype: `__int64 __fastcall(unsigned int, LPCWSTR lpSubKey)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800290dc`
- `0x180029b04`
- `0x180029de4`

## callees

- `0x180028fc0`
- `0x18002a130`
- `0x18002c4f4`
- `0x18002cfe4`
- `0x18002d2b0`
- `0x18002d628`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d672`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d672`

## string_xrefs

- `0x18002d6c0`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\util.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HKEY *__fastcall winrt::Windows::UI::ViewManagement::Core::implementation::GetDesktopRegistryKey(
        HKEY *a1,
        LPCWSTR lpSubKey)
{
  unsigned int v4; // eax
  PHKEY v5; // rax
  unsigned int phkResult; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HKEY v9; // [rsp+60h] [rbp+18h] BYREF

  *a1 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    a1,
    0);
  v4 = RegOpenKeyExW(HKEY_CURRENT_USER, lpSubKey, 0, 0xF003Fu, a1);
  if ( v4 == 2 )
  {
    v5 = anonymous_namespace_::CreateRegistryKeyWithAcl(&v9, HKEY_CURRENT_USER, lpSubKey);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(
      a1,
      v5);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v9);
  }
  else if ( v4 )
  {
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x105,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\util.cpp",
      (const char *)v4,
      phkResult);
  }
  return a1;
}

```

## disassembly

```asm
0x18002d628  mov     rax, rsp
0x18002d62b  mov     [rax+10h], rbx
0x18002d62f  mov     [rax+8], rcx
0x18002d633  push    rdi
0x18002d634  sub     rsp, 40h
0x18002d638  mov     rdi, rdx
0x18002d63b  mov     rbx, rcx
0x18002d63e  mov     dword ptr [rax-18h], 0
0x18002d645  mov     qword ptr [rcx], 0
0x18002d64c  mov     dword ptr [rax-18h], 1
0x18002d653  xor     edx, edx
0x18002d655  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002d65a  mov     qword ptr [rsp+48h+phkResult], rbx; unsigned int
0x18002d65f  mov     r9d, 0F003Fh; samDesired
0x18002d665  xor     r8d, r8d; ulOptions
0x18002d668  mov     rdx, rdi; lpSubKey
0x18002d66b  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002d672  call    cs:__imp_RegOpenKeyExW
0x18002d678  cmp     eax, 2
0x18002d67b  jnz     short loc_18002D6B4
0x18002d67d  mov     r8, rdi; lpSubKey
0x18002d680  mov     rdx, 0FFFFFFFF80000001h; hKey
0x18002d687  lea     rcx, [rsp+48h+arg_10]; phkResult
0x18002d68c  call    _anonymous_namespace___CreateRegistryKeyWithAcl
0x18002d691  mov     rdx, rax
0x18002d694  mov     rcx, rbx
0x18002d697  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&)
0x18002d69c  lea     rcx, [rsp+48h+arg_10]
0x18002d6a1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002d6a6  mov     rax, rbx
0x18002d6a9  mov     rbx, [rsp+48h+arg_8]
0x18002d6ae  add     rsp, 40h
0x18002d6b2  pop     rdi
0x18002d6b3  retn
0x18002d6b4  test    eax, eax
0x18002d6b6  jz      short loc_18002D6A6
0x18002d6b8  mov     rcx, [rsp+48h]; this
0x18002d6bd  mov     r9d, eax; char *
0x18002d6c0  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002d6c7  mov     edx, 105h; void *
0x18002d6cc  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
