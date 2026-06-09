# _anonymous_namespace_::GetSvgInputPath

- ea: `0x18002b89c`
- end: `0x18002b94b`
- name: `_anonymous_namespace_::GetSvgInputPath`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18002ab30`

## callees

- `0x18000cf94`
- `0x1800126e4`
- `0x180024304`
- `0x18002aeb8`
- `0x18002b89c`
- `0x18002c4a0`

## import_xrefs

- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18002b8dd`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18002b8dd`

## string_xrefs

- `0x18002b8ef`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\cursorutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall anonymous_namespace_::GetSvgInputPath(__int64 a1, __int64 a2)
{
  HRESULT v4; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  PWSTR ppszPath; // [rsp+50h] [rbp+18h] BYREF

  ppszPath = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppszPath,
    0);
  v4 = SHGetKnownFolderPath(&FOLDERID_Windows, 0, 0, &ppszPath);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\cursorutils.cpp",
      (const char *)(unsigned int)v4,
      0);
  std::wstring::wstring(a1, ppszPath);
  std::wstring::append(a1, L"\\Cursors");
  std::wstring::append(a1, *(_QWORD *)(a2 + 8));
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPath);
  return a1;
}

```

## disassembly

```asm
0x18002b89c  mov     rax, rsp
0x18002b89f  mov     [rax+10h], rbx
0x18002b8a3  mov     [rax+8], rcx
0x18002b8a7  push    rdi
0x18002b8a8  sub     rsp, 30h
0x18002b8ac  mov     rdi, rdx
0x18002b8af  mov     rbx, rcx
0x18002b8b2  mov     dword ptr [rax-18h], 0
0x18002b8b9  mov     qword ptr [rax+18h], 0
0x18002b8c1  xor     edx, edx
0x18002b8c3  lea     rcx, [rax+18h]
0x18002b8c7  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002b8cc  lea     r9, [rsp+38h+ppszPath]; ppszPath
0x18002b8d1  xor     r8d, r8d; hToken
0x18002b8d4  xor     edx, edx; dwFlags
0x18002b8d6  lea     rcx, FOLDERID_Windows; rfid
0x18002b8dd  call    cs:__imp_SHGetKnownFolderPath
0x18002b8e3  mov     rcx, [rsp+38h]; this
0x18002b8e8  test    eax, eax
0x18002b8ea  jns     short loc_18002B901
0x18002b8ec  mov     r9d, eax; char *
0x18002b8ef  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002b8f6  mov     edx, 45h ; 'E'; void *
0x18002b8fb  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002b901  mov     rdx, [rsp+38h+ppszPath]
0x18002b906  mov     rcx, rbx
0x18002b909  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002b90e  mov     [rsp+38h+var_18], 1
0x18002b916  lea     rdx, aCursors; "\\Cursors"
0x18002b91d  mov     rcx, rbx
0x18002b920  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002b925  mov     rdx, [rdi+8]
0x18002b929  mov     rcx, rbx
0x18002b92c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002b931  nop
0x18002b932  lea     rcx, [rsp+38h+ppszPath]
0x18002b937  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b93c  mov     rax, rbx
0x18002b93f  mov     rbx, [rsp+38h+arg_8]
0x18002b944  add     rsp, 30h
0x18002b948  pop     rdi
0x18002b949  retn
```
