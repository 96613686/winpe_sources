# Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::GetCapabilitiesKey(ulong)

- ea: `0x180029d34`
- end: `0x180029e78`
- name: `?GetCapabilitiesKey@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z`
- size: `324`
- prototype: `PHKEY __fastcall(PHKEY phkResult, int)`
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800296d8`
- `0x180029960`
- `0x18002a020`
- `0x18002a164`

## callees

- `0x180003c80`
- `0x18000a248`
- `0x18000f9e4`
- `0x18000fc2c`
- `0x18001b444`
- `0x1800207a4`
- `0x1800236ac`
- `0x180023b38`
- `0x180025080`
- `0x180029d34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180029e27`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180029e27`

## string_xrefs

- `0x180029d69`: `Software\Microsoft\Windows\CurrentVersion\CapabilityAccessManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
PHKEY __fastcall Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::GetCapabilitiesKey(
        PHKEY phkResult,
        int a2)
{
  __int64 v4; // rdx
  __int64 v5; // r9
  unsigned __int64 v6; // r8
  __int64 v7; // rax
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  const WCHAR *v14; // rax
  unsigned int Key; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-19h]
  _BYTE Src[16]; // [rsp+60h] [rbp+27h] BYREF
  unsigned __int64 v19; // [rsp+70h] [rbp+37h]
  unsigned __int64 v20; // [rsp+78h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  std::wstring::wstring((__int64)Src, (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\CapabilityAccessManager");
  v6 = v19;
  if ( v19 >= v20 )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Src);
  }
  else
  {
    ++v19;
    v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src, v4, v6, v5);
    *(_WORD *)(v7 + 2 * v8) = 92;
    *(_WORD *)(v7 + 2 * v8 + 2) = 0;
  }
  v9 = std::_WChar_traits<unsigned short>::length(L"Capabilities");
  std::wstring::_Append<unsigned short>(Src, v10, v9);
  *phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    phkResult,
    0);
  v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src, v11, v12, v13);
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v14, 0, 0, 0, a2 | 0x100, 0, phkResult, 0);
  if ( Key )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x21F,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilitypolicystore.cpp",
      (const char *)Key,
      dwOptions);
  std::wstring::_Tidy_deallocate(Src);
  return phkResult;
}

```

## disassembly

```asm
0x180029d34  mov     [rsp-8+arg_10], rbx
0x180029d39  mov     [rsp-8+arg_18], rdi
0x180029d3e  push    rbp
0x180029d3f  lea     rbp, [rsp-57h]
0x180029d44  sub     rsp, 90h
0x180029d4b  mov     rax, cs:__security_cookie
0x180029d52  xor     rax, rsp
0x180029d55  mov     [rbp+57h+var_10], rax
0x180029d59  mov     edi, edx
0x180029d5b  mov     rbx, rcx
0x180029d5e  mov     [rbp+57h+var_38], rcx
0x180029d62  mov     [rbp+57h+var_40], 0
0x180029d69  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180029d70  lea     rcx, [rbp+57h+Src]
0x180029d74  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029d79  nop
0x180029d7a  mov     r8, [rbp+57h+var_20]
0x180029d7e  lea     rcx, [rbp+57h+Src]; Src
0x180029d82  cmp     r8, [rbp+57h+var_18]
0x180029d86  jnb     short loc_180029DA9
0x180029d88  lea     rax, [r8+1]
0x180029d8c  mov     [rbp+57h+var_20], rax
0x180029d90  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180029d95  mov     rdx, rax
0x180029d98  mov     word ptr [rax+r8*2], 5Ch ; '\'
0x180029d9f  xor     eax, eax
0x180029da1  mov     [rdx+r8*2+2], ax
0x180029da7  jmp     short loc_180029DB4
0x180029da9  mov     r9d, 5Ch ; '\'
0x180029daf  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x180029db4  lea     rcx, aCapabilities; "Capabilities"
0x180029dbb  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180029dc0  mov     r8, rax
0x180029dc3  mov     rdx, rcx
0x180029dc6  lea     rcx, [rbp+57h+Src]
0x180029dca  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180029dcf  mov     qword ptr [rbx], 0
0x180029dd6  mov     [rbp+57h+var_40], 1
0x180029ddd  xor     edx, edx
0x180029ddf  mov     rcx, rbx
0x180029de2  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180029de7  bts     edi, 8
0x180029deb  lea     rcx, [rbp+57h+Src]
0x180029def  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180029df4  mov     rdx, rax; lpSubKey
0x180029df7  mov     [rsp+90h+lpdwDisposition], 0; lpdwDisposition
0x180029e00  mov     [rsp+90h+phkResult], rbx; phkResult
0x180029e05  mov     [rsp+90h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180029e0e  mov     [rsp+90h+samDesired], edi; samDesired
0x180029e12  mov     [rsp+90h+dwOptions], 0; unsigned int
0x180029e1a  xor     r9d, r9d; lpClass
0x180029e1d  xor     r8d, r8d; Reserved
0x180029e20  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180029e27  call    cs:__imp_RegCreateKeyExW
0x180029e2d  mov     rcx, [rbp+5Fh]; this
0x180029e31  test    eax, eax
0x180029e33  jz      short loc_180029E4A
0x180029e35  mov     r9d, eax; char *
0x180029e38  lea     r8, aOnecoreBaseDev_1; "onecore\\base\\devices\\cam\\core\\capa"...
0x180029e3f  mov     edx, 21Fh; void *
0x180029e44  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180029e4a  lea     rcx, [rbp+57h+Src]
0x180029e4e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029e53  mov     rax, rbx
0x180029e56  mov     rcx, [rbp+57h+var_10]
0x180029e5a  xor     rcx, rsp; StackCookie
0x180029e5d  call    __security_check_cookie
0x180029e62  lea     r11, [rsp+90h+var_s0]
0x180029e6a  mov     rbx, [r11+20h]
0x180029e6e  mov     rdi, [r11+28h]
0x180029e72  mov     rsp, r11
0x180029e75  pop     rbp
0x180029e76  retn
```
