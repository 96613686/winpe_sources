# RegDeleteTreeRecurse

- ea: `0x180028104`
- end: `0x1800281ad`
- name: `RegDeleteTreeRecurse`
- size: `169`
- prototype: `__int64 __fastcall(RegistryKey *this)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180026cb8`
- `0x180028104`

## callees

- `0x1800027c0`
- `0x180008e3c`
- `0x18000d954`
- `0x18000d9b4`
- `0x180018490`
- `0x180026bdc`
- `0x1800270e4`
- `0x180027ef4`
- `0x180028104`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RegDeleteTreeRecurse(HKEY *this)
{
  const WCHAR *v2; // rax
  const wchar_t *v3; // rax
  HKEY v5; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v6[32]; // [rsp+38h] [rbp-30h] BYREF

  std::wstring::wstring((__int64)v6);
  while ( RegistryKey::GetSubKeyByIndex(this, 0, (__int64)v6) )
  {
    v2 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    RegistryKey::OpenSubKey(this, (RegistryKey *)&v5, v2, 9, 0);
    RegDeleteTreeRecurse((RegistryKey *)&v5);
    v3 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    RegistryKey::DeleteEmptySubKey((RegistryKey *)this, v3);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v5);
  }
  return std::wstring::_Tidy_deallocate((__int64)v6);
}

```

## disassembly

```asm
0x180028104  push    rbx
0x180028106  sub     rsp, 60h
0x18002810a  mov     rax, cs:__security_cookie
0x180028111  xor     rax, rsp
0x180028114  mov     [rsp+68h+var_10], rax
0x180028119  mov     rbx, rcx
0x18002811c  lea     rcx, [rsp+68h+var_30]
0x180028121  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180028126  nop
0x180028127  jmp     short loc_18002817D
0x180028129  lea     rcx, [rsp+68h+var_30]
0x18002812e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180028133  mov     r8, rax
0x180028136  mov     [rsp+68h+var_48], 0
0x18002813f  mov     r9d, 9
0x180028145  lea     rdx, [rsp+68h+var_38]
0x18002814a  mov     rcx, rbx
0x18002814d  call    ?OpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z; RegistryKey::OpenSubKey(wchar_t const *,ulong,void *)
0x180028152  nop
0x180028153  lea     rcx, [rsp+68h+var_38]; this
0x180028158  call    RegDeleteTreeRecurse
0x18002815d  lea     rcx, [rsp+68h+var_30]
0x180028162  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180028167  mov     rdx, rax; wchar_t *
0x18002816a  mov     rcx, rbx; this
0x18002816d  call    ?DeleteEmptySubKey@RegistryKey@@QEBAXPEB_W@Z; RegistryKey::DeleteEmptySubKey(wchar_t const *)
0x180028172  nop
0x180028173  lea     rcx, [rsp+68h+var_38]
0x180028178  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002817d  lea     r8, [rsp+68h+var_30]
0x180028182  xor     edx, edx
0x180028184  mov     rcx, rbx
0x180028187  call    ?GetSubKeyByIndex@RegistryKey@@QEBA_NKAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; RegistryKey::GetSubKeyByIndex(ulong,std::wstring &)
0x18002818c  test    al, al
0x18002818e  jnz     short loc_180028129
0x180028190  lea     rcx, [rsp+68h+var_30]
0x180028195  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002819a  mov     rcx, [rsp+68h+var_10]
0x18002819f  xor     rcx, rsp; StackCookie
0x1800281a2  call    __security_check_cookie
0x1800281a7  add     rsp, 60h
0x1800281ab  pop     rbx
0x1800281ac  retn
```
