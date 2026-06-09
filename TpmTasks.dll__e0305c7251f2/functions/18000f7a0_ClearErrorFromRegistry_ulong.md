# ClearErrorFromRegistry(ulong)

- ea: `0x18000f7a0`
- end: `0x18000f8a3`
- name: `?ClearErrorFromRegistry@@YAXK@Z`
- size: `259`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x18001e5d0`

## callees

- `0x1800078b0`
- `0x180009d98`
- `0x18000e48c`
- `0x18000f7a0`
- `0x180014350`
- `0x180023634`
- `0x18002386c`
- `0x1800243e8`
- `0x18003c0b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000f843`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000f859`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000f843`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000f859`

## string_xrefs

- `0x18000f80a`: `LastUpdateError`
- `0x18000f81f`: `LastUpdateErrorReason`
- `0x18000f7df`: `Unknown update type %x, cannot clear error from registry\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall ClearErrorFromRegistry(unsigned int a1)
{
  __int64 v2; // rcx
  const WCHAR *v3; // rax
  const WCHAR *v4; // rax
  HKEY hKey; // [rsp+20h] [rbp-19h] BYREF
  _BYTE v6[16]; // [rsp+28h] [rbp-11h] BYREF
  __int64 v7; // [rsp+38h] [rbp-1h]
  _BYTE v8[32]; // [rsp+48h] [rbp+Fh] BYREF
  _BYTE v9[32]; // [rsp+68h] [rbp+2Fh] BYREF

  hKey = 0;
  GetRegistryPrefixForUpdateType(v6, a1);
  if ( v7 )
  {
    if ( (int)wil::reg::open_unique_key_nothrow(
                v2,
                L"SYSTEM\\CurrentControlSet\\Control\\SecureBoot\\Servicing",
                &hKey,
                1) >= 0 )
    {
      std::operator+<unsigned short>(v9, v6, L"LastUpdateError");
      std::operator+<unsigned short>(v8, v6, L"LastUpdateErrorReason");
      v3 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v9);
      RegDeleteValueW(hKey, v3);
      v4 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v8);
      RegDeleteValueW(hKey, v4);
      std::wstring::_Tidy_deallocate(v8);
      std::wstring::_Tidy_deallocate(v9);
    }
  }
  else
  {
    SBServicingLogMessage((wchar_t *)L"Unknown update type %x, cannot clear error from registry\n", a1);
  }
  std::wstring::_Tidy_deallocate(v6);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x18000f7a0  mov     [rsp-8+arg_8], rbx
0x18000f7a5  push    rbp
0x18000f7a6  lea     rbp, [rsp-57h]
0x18000f7ab  sub     rsp, 90h
0x18000f7b2  mov     rax, cs:__security_cookie
0x18000f7b9  xor     rax, rsp
0x18000f7bc  mov     [rbp+57h+var_8], rax
0x18000f7c0  mov     ebx, ecx
0x18000f7c2  mov     [rbp+57h+hKey], 0
0x18000f7ca  mov     edx, ecx
0x18000f7cc  lea     rcx, [rbp+57h+var_68]
0x18000f7d0  call    ?GetRegistryPrefixForUpdateType@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; GetRegistryPrefixForUpdateType(ulong)
0x18000f7d5  nop
0x18000f7d6  cmp     [rbp+57h+var_58], 0
0x18000f7db  jnz     short loc_18000F7F0
0x18000f7dd  mov     edx, ebx
0x18000f7df  lea     rcx, aUnknownUpdateT; "Unknown update type %x, cannot clear er"...
0x18000f7e6  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18000f7eb  jmp     loc_18000F873
0x18000f7f0  mov     r9d, 1
0x18000f7f6  lea     r8, [rbp+57h+hKey]
0x18000f7fa  lea     rdx, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Control\\Sec"...
0x18000f801  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18000f806  test    eax, eax
0x18000f808  js      short loc_18000F873
0x18000f80a  lea     r8, aLastupdateerro; "LastUpdateError"
0x18000f811  lea     rdx, [rbp+57h+var_68]
0x18000f815  lea     rcx, [rbp+57h+var_28]
0x18000f819  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18000f81e  nop
0x18000f81f  lea     r8, aLastupdateerro_0; "LastUpdateErrorReason"
0x18000f826  lea     rdx, [rbp+57h+var_68]
0x18000f82a  lea     rcx, [rbp+57h+var_48]
0x18000f82e  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18000f833  lea     rcx, [rbp+57h+var_28]
0x18000f837  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000f83c  mov     rdx, rax; lpValueName
0x18000f83f  mov     rcx, [rbp+57h+hKey]; hKey
0x18000f843  call    cs:__imp_RegDeleteValueW
0x18000f849  lea     rcx, [rbp+57h+var_48]
0x18000f84d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000f852  mov     rdx, rax; lpValueName
0x18000f855  mov     rcx, [rbp+57h+hKey]; hKey
0x18000f859  call    cs:__imp_RegDeleteValueW
0x18000f85f  lea     rcx, [rbp+57h+var_48]
0x18000f863  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f868  nop
0x18000f869  lea     rcx, [rbp+57h+var_28]
0x18000f86d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f872  nop
0x18000f873  lea     rcx, [rbp+57h+var_68]
0x18000f877  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f87c  nop
0x18000f87d  lea     rcx, [rbp+57h+hKey]
0x18000f881  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000f886  mov     rcx, [rbp+57h+var_8]
0x18000f88a  xor     rcx, rsp; StackCookie
0x18000f88d  call    __security_check_cookie
0x18000f892  mov     rbx, [rsp+90h+arg_8]
0x18000f89a  add     rsp, 90h
0x18000f8a1  pop     rbp
0x18000f8a2  retn
```
