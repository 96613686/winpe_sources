# _anonymous_namespace_::GetCursorOutputPath

- ea: `0x18002b67c`
- end: `0x18002b75c`
- name: `_anonymous_namespace_::GetCursorOutputPath`
- size: `224`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002af70`
- `0x18002b2b4`

## callees

- `0x180003980`
- `0x18000cf94`
- `0x1800126e4`
- `0x1800166d4`
- `0x180016770`
- `0x180024304`
- `0x18002aeb8`
- `0x18002b67c`
- `0x18002c4a0`

## import_xrefs

- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18002b6d1`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18002b6d1`

## string_xrefs

- `0x18002b6e3`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\cursorutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall anonymous_namespace_::GetCursorOutputPath(__int64 a1, __int64 a2)
{
  HRESULT v4; // eax
  __int64 v5; // rax
  PWSTR ppszPath; // [rsp+20h] [rbp-38h] BYREF
  int v8; // [rsp+28h] [rbp-30h]
  __int64 v9; // [rsp+30h] [rbp-28h]
  __int64 v10; // [rsp+38h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v9 = a1;
  v10 = a2;
  v8 = 0;
  ppszPath = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppszPath,
    0);
  v4 = SHGetKnownFolderPath(&FOLDERID_LocalAppData, 0, 0, &ppszPath);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\cursorutils.cpp",
      (const char *)(unsigned int)v4,
      (int)ppszPath);
  std::wstring::wstring(a1, ppszPath);
  v8 = 1;
  std::wstring::append(a1, L"\\Microsoft\\Windows\\Cursors");
  v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  std::wstring::append(a1, v5);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPath);
  std::wstring::_Tidy_deallocate(a2);
  return a1;
}

```

## disassembly

```asm
0x18002b67c  mov     r11, rsp
0x18002b67f  mov     [r11+18h], rbx
0x18002b683  push    rdi
0x18002b684  sub     rsp, 50h
0x18002b688  mov     rax, cs:__security_cookie
0x18002b68f  xor     rax, rsp
0x18002b692  mov     [rsp+58h+var_18], rax
0x18002b697  mov     rdi, rdx
0x18002b69a  mov     rbx, rcx
0x18002b69d  mov     [r11-28h], rcx
0x18002b6a1  mov     [r11-20h], rdx
0x18002b6a5  mov     [rsp+58h+var_30], 0
0x18002b6ad  mov     qword ptr [r11-38h], 0
0x18002b6b5  xor     edx, edx
0x18002b6b7  lea     rcx, [r11-38h]
0x18002b6bb  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002b6c0  lea     r9, [rsp+58h+ppszPath]; ppszPath
0x18002b6c5  xor     r8d, r8d; hToken
0x18002b6c8  xor     edx, edx; dwFlags
0x18002b6ca  lea     rcx, FOLDERID_LocalAppData; rfid
0x18002b6d1  call    cs:__imp_SHGetKnownFolderPath
0x18002b6d7  mov     rcx, [rsp+58h]; this
0x18002b6dc  test    eax, eax
0x18002b6de  jns     short loc_18002B6F5
0x18002b6e0  mov     r9d, eax; char *
0x18002b6e3  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002b6ea  mov     edx, 51h ; 'Q'; void *
0x18002b6ef  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002b6f5  mov     rdx, [rsp+58h+ppszPath]
0x18002b6fa  mov     rcx, rbx
0x18002b6fd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002b702  mov     [rsp+58h+var_30], 1
0x18002b70a  lea     rdx, aMicrosoftWindo_0; "\\Microsoft\\Windows\\Cursors"
0x18002b711  mov     rcx, rbx
0x18002b714  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002b719  mov     rcx, rdi
0x18002b71c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002b721  mov     rdx, rax
0x18002b724  mov     rcx, rbx
0x18002b727  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002b72c  nop
0x18002b72d  lea     rcx, [rsp+58h+ppszPath]
0x18002b732  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b737  nop
0x18002b738  mov     rcx, rdi
0x18002b73b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b740  mov     rax, rbx
0x18002b743  mov     rcx, [rsp+58h+var_18]
0x18002b748  xor     rcx, rsp; StackCookie
0x18002b74b  call    __security_check_cookie
0x18002b750  mov     rbx, [rsp+58h+arg_10]
0x18002b755  add     rsp, 50h
0x18002b759  pop     rdi
0x18002b75a  retn
```
