# Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::GetEditionCapabilityPolicyRootKey(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)

- ea: `0x180029f0c`
- end: `0x18002a018`
- name: `?GetEditionCapabilityPolicyRootKey@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@KAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `268`
- prototype: `__int64 __fastcall(PHKEY phkResult)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002bb68`

## callees

- `0x180003c80`
- `0x18000f9e4`
- `0x18000fc2c`
- `0x180013b8c`
- `0x18001b444`
- `0x1800207a4`
- `0x1800238e0`
- `0x180023b38`
- `0x180029f0c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180029fd1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180029fd1`

## string_xrefs

- `0x180029f32`: `Software\Microsoft\Windows\CurrentVersion\CapabilityAccessManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::GetEditionCapabilityPolicyRootKey(
        PHKEY phkResult)
{
  __int64 v2; // rax
  __int64 v3; // rcx
  __int64 v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  const WCHAR *v11; // rax
  LSTATUS Key; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-68h]
  _BYTE v15[32]; // [rsp+50h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  std::wstring::wstring(v15);
  v2 = std::_WChar_traits<unsigned short>::length(L"Software\\Microsoft\\Windows\\CurrentVersion\\CapabilityAccessManager");
  std::wstring::_Append<unsigned short>(v15, v3, v2);
  v4 = std::_WChar_traits<unsigned short>::length(L"\\");
  std::wstring::_Append<unsigned short>(v15, v5, v4);
  v6 = std::_WChar_traits<unsigned short>::length(&stru_180055278);
  std::wstring::_Append<unsigned short>(v15, v7, v6);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    phkResult,
    0);
  v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15, v8, v9, v10);
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v11, 0, 0, 0, 0x20119u, 0, phkResult, 0);
  if ( Key < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0xA79,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilitypolicystore.cpp",
      (const char *)(unsigned int)Key,
      dwOptions);
  return std::wstring::_Tidy_deallocate(v15);
}

```

## disassembly

```asm
0x180029f0c  push    rbx
0x180029f0e  sub     rsp, 80h
0x180029f15  mov     rax, cs:__security_cookie
0x180029f1c  xor     rax, rsp
0x180029f1f  mov     [rsp+88h+var_18], rax
0x180029f24  mov     rbx, rcx
0x180029f27  lea     rcx, [rsp+88h+var_38]
0x180029f2c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180029f31  nop
0x180029f32  lea     rcx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180029f39  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180029f3e  mov     r8, rax
0x180029f41  mov     rdx, rcx
0x180029f44  lea     rcx, [rsp+88h+var_38]
0x180029f49  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180029f4e  lea     rcx, asc_18004DF50; "\\"
0x180029f55  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180029f5a  mov     r8, rax
0x180029f5d  mov     rdx, rcx
0x180029f60  lea     rcx, [rsp+88h+var_38]
0x180029f65  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180029f6a  lea     rcx, stru_180055278
0x180029f71  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180029f76  mov     r8, rax
0x180029f79  mov     rdx, rcx
0x180029f7c  lea     rcx, [rsp+88h+var_38]
0x180029f81  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180029f86  xor     edx, edx
0x180029f88  mov     rcx, rbx
0x180029f8b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180029f90  lea     rcx, [rsp+88h+var_38]
0x180029f95  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180029f9a  mov     rdx, rax; lpSubKey
0x180029f9d  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x180029fa6  mov     [rsp+88h+phkResult], rbx; phkResult
0x180029fab  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180029fb4  mov     [rsp+88h+samDesired], 20119h; samDesired
0x180029fbc  mov     [rsp+88h+dwOptions], 0; int
0x180029fc4  xor     r9d, r9d; lpClass
0x180029fc7  xor     r8d, r8d; Reserved
0x180029fca  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180029fd1  call    cs:__imp_RegCreateKeyExW
0x180029fd7  mov     rcx, [rsp+88h]; this
0x180029fdf  test    eax, eax
0x180029fe1  jns     short loc_180029FF8
0x180029fe3  mov     r9d, eax; char *
0x180029fe6  lea     r8, aOnecoreBaseDev_1; "onecore\\base\\devices\\cam\\core\\capa"...
0x180029fed  mov     edx, 0A79h; void *
0x180029ff2  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180029ff8  lea     rcx, [rsp+88h+var_38]
0x180029ffd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a002  mov     rcx, [rsp+88h+var_18]
0x18002a007  xor     rcx, rsp; StackCookie
0x18002a00a  call    __security_check_cookie
0x18002a00f  add     rsp, 80h
0x18002a016  pop     rbx
0x18002a017  retn
```
