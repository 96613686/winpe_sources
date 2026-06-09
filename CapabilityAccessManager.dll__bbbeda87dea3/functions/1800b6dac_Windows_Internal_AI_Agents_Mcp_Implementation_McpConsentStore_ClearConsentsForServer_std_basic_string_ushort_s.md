# Windows::Internal::AI::Agents::Mcp::Implementation::McpConsentStore::ClearConsentsForServer(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800b6dac`
- end: `0x1800b6f83`
- name: `?ClearConsentsForServer@McpConsentStore@Implementation@Mcp@Agents@AI@Internal@Windows@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `471`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task`

## callers

- `0x1800988e0`

## callees

- `0x1800094c0`
- `0x18001c3b4`
- `0x18002392c`
- `0x1800257a4`
- `0x180029408`
- `0x1800299c4`
- `0x18002a564`
- `0x18002f280`
- `0x18003afa0`
- `0x18003ce34`
- `0x18005829c`
- `0x180058ac4`
- `0x1800b6dac`
- `0x1800b7d6c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800b6ef0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800b6ef0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b6edf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b6edf`
- `ext-ms-win-capabilityaccessmanager-storage-l1-1-0!EraseUInt64MCPSettingsForServer` at `0x1800b6e01`
- `ext-ms-win-capabilityaccessmanager-storage-l1-1-0!EraseUInt64MCPSettingsForServer` at `0x1800b6e01`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::AI::Agents::Mcp::Implementation::McpConsentStore::ClearConsentsForServer(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rax
  __int64 result; // rax
  __int64 v6; // rbx
  __int64 v7; // rsi
  __int64 v8; // rax
  __int64 v9; // r8
  const WCHAR *v10; // rax
  unsigned int v11; // eax
  int phkResult; // [rsp+20h] [rbp-60h]
  unsigned int phkResulta; // [rsp+20h] [rbp-60h]
  HKEY v14; // [rsp+30h] [rbp-50h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v16[3]; // [rsp+40h] [rbp-40h] BYREF
  _OWORD v17[2]; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID59213523>::GetImpl'::`2'::impl) )
  {
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
    result = EraseUInt64MCPSettingsForServer(v4);
    if ( (int)result < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB3,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\mcpconsentstore.cpp",
        (const char *)(unsigned int)result,
        phkResult);
  }
  else
  {
    hKey = 0;
    v17[0] = 0;
    v17[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v17[0]) = 0;
    Windows::Internal::AI::Agents::Mcp::Implementation::McpConsentStore::OpenTemporaryRegistryStoreWithOffset(&hKey);
    std::wstring::_Tidy_deallocate(v17);
    Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(v16, hKey, 0);
    v14 = 0;
    v6 = v16[0];
    v7 = v16[1];
    while ( v6 != v7 )
    {
      std::wstring::wstring(v17, v6);
      std::wstring::_Append<unsigned short>(v17, L"\\");
      v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
      v9 = -1;
      do
        ++v9;
      while ( *(_WORD *)(v8 + 2 * v9) );
      std::wstring::_Append<unsigned short>(v17, v8);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &v14,
        0);
      v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
      if ( RegOpenKeyExW(hKey, v10, 0, 0xF013Fu, &v14) != 2 )
      {
        v11 = RegDeleteTreeW(v14, 0);
        if ( v11 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0xDA,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\mcpconsentstore.cpp",
            (const char *)v11,
            phkResulta);
      }
      std::wstring::_Tidy_deallocate(v17);
      v6 += 32;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v14);
    std::vector<std::wstring>::_Tidy(v16);
    return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  return result;
}

```

## disassembly

```asm
0x1800b6dac  mov     [rsp-18h+arg_10], rbx
0x1800b6db1  mov     [rsp-18h+arg_18], rsi
0x1800b6db6  push    rbp
0x1800b6db7  push    rdi
0x1800b6db8  push    r14
0x1800b6dba  mov     rbp, rsp
0x1800b6dbd  sub     rsp, 80h
0x1800b6dc4  mov     rax, cs:__security_cookie
0x1800b6dcb  xor     rax, rsp
0x1800b6dce  mov     [rbp+var_8], rax
0x1800b6dd2  mov     rbx, rdx
0x1800b6dd5  mov     rdi, rcx
0x1800b6dd8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID59213523@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID59213523@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523> `wil::Feature<__WilFeatureTraits_Feature_ID59213523>::GetImpl(void)'::`2'::impl
0x1800b6ddf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59213523@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523>::__private_IsEnabled(void)
0x1800b6de4  xor     r14d, r14d
0x1800b6de7  test    al, al
0x1800b6de9  jz      short loc_1800B6E14
0x1800b6deb  mov     rcx, rbx
0x1800b6dee  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b6df3  mov     rdx, rax
0x1800b6df6  mov     rcx, rdi
0x1800b6df9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b6dfe  mov     rcx, rax
0x1800b6e01  call    cs:__imp_EraseUInt64MCPSettingsForServer
0x1800b6e07  test    eax, eax
0x1800b6e09  js      loc_1800B6F6A
0x1800b6e0f  jmp     loc_1800B6F31
0x1800b6e14  mov     [rbp+hKey], r14
0x1800b6e18  xorps   xmm0, xmm0
0x1800b6e1b  movups  [rbp+var_28], xmm0
0x1800b6e1f  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800b6e27  movdqu  [rbp+var_18], xmm1
0x1800b6e2c  mov     word ptr [rbp+var_28], r14w
0x1800b6e31  mov     r9, rbx
0x1800b6e34  lea     r8, [rbp+var_28]
0x1800b6e38  lea     rcx, [rbp+hKey]; phkResult
0x1800b6e3c  call    ?OpenTemporaryRegistryStoreWithOffset@McpConsentStore@Implementation@Mcp@Agents@AI@Internal@Windows@@CAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; Windows::Internal::AI::Agents::Mcp::Implementation::McpConsentStore::OpenTemporaryRegistryStoreWithOffset(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,ulong,std::wstring const &,std::wstring const &)
0x1800b6e41  nop
0x1800b6e42  lea     rcx, [rbp+var_28]
0x1800b6e46  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b6e4b  xor     r8d, r8d
0x1800b6e4e  mov     rdx, [rbp+hKey]
0x1800b6e52  lea     rcx, [rbp+var_40]
0x1800b6e56  call    ?RegGetKeyArray@Private@CapabilityAccess@Internal@Windows@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAUHKEY__@@PEBG@Z; Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(HKEY__ *,ushort const *)
0x1800b6e5b  nop
0x1800b6e5c  mov     [rbp+var_50], r14
0x1800b6e60  mov     rbx, [rbp+var_40]
0x1800b6e64  mov     rsi, [rbp+var_38]
0x1800b6e68  jmp     loc_1800B6F0B
0x1800b6e6d  mov     rdx, rbx
0x1800b6e70  lea     rcx, [rbp+var_28]
0x1800b6e74  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800b6e79  nop
0x1800b6e7a  mov     r8d, 1
0x1800b6e80  lea     rdx, asc_1800D35BC; "\\"
0x1800b6e87  lea     rcx, [rbp+var_28]
0x1800b6e8b  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800b6e90  mov     rcx, rdi
0x1800b6e93  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b6e98  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800b6e9c  inc     r8
0x1800b6e9f  cmp     [rax+r8*2], r14w
0x1800b6ea4  jnz     short loc_1800B6E9C
0x1800b6ea6  mov     rdx, rax
0x1800b6ea9  lea     rcx, [rbp+var_28]
0x1800b6ead  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800b6eb2  xor     edx, edx
0x1800b6eb4  lea     rcx, [rbp+var_50]
0x1800b6eb8  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800b6ebd  lea     rcx, [rbp+var_28]
0x1800b6ec1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b6ec6  mov     rdx, rax; lpSubKey
0x1800b6ec9  lea     rax, [rbp+var_50]
0x1800b6ecd  mov     qword ptr [rsp+80h+phkResult], rax; unsigned int
0x1800b6ed2  mov     r9d, 0F013Fh; samDesired
0x1800b6ed8  xor     r8d, r8d; ulOptions
0x1800b6edb  mov     rcx, [rbp+hKey]; hKey
0x1800b6edf  call    cs:__imp_RegOpenKeyExW
0x1800b6ee5  cmp     eax, 2
0x1800b6ee8  jz      short loc_1800B6EFE
0x1800b6eea  xor     edx, edx; lpSubKey
0x1800b6eec  mov     rcx, [rbp+var_50]; hKey
0x1800b6ef0  call    cs:__imp_RegDeleteTreeW
0x1800b6ef6  mov     rcx, [rbp+18h]; this
0x1800b6efa  test    eax, eax
0x1800b6efc  jnz     short loc_1800B6F55
0x1800b6efe  lea     rcx, [rbp+var_28]
0x1800b6f02  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b6f07  add     rbx, 20h ; ' '
0x1800b6f0b  cmp     rbx, rsi
0x1800b6f0e  jnz     loc_1800B6E6D
0x1800b6f14  lea     rcx, [rbp+var_50]
0x1800b6f18  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b6f1d  nop
0x1800b6f1e  lea     rcx, [rbp+var_40]
0x1800b6f22  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800b6f27  nop
0x1800b6f28  lea     rcx, [rbp+hKey]
0x1800b6f2c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b6f31  mov     rcx, [rbp+var_8]
0x1800b6f35  xor     rcx, rsp; StackCookie
0x1800b6f38  call    __security_check_cookie
0x1800b6f3d  lea     r11, [rsp+80h+var_s0]
0x1800b6f45  mov     rbx, [r11+30h]
0x1800b6f49  mov     rsi, [r11+38h]
0x1800b6f4d  mov     rsp, r11
0x1800b6f50  pop     r14
0x1800b6f52  pop     rdi
0x1800b6f53  pop     rbp
0x1800b6f54  retn
0x1800b6f55  mov     r9d, eax; char *
0x1800b6f58  lea     r8, aOnecoreBaseDev_34; "onecore\\base\\devices\\cam\\core\\mcpc"...
0x1800b6f5f  mov     edx, 0DAh; void *
0x1800b6f64  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800b6f6a  mov     rcx, [rbp+18h]; this
0x1800b6f6e  mov     r9d, eax; char *
0x1800b6f71  lea     r8, aOnecoreBaseDev_34; "onecore\\base\\devices\\cam\\core\\mcpc"...
0x1800b6f78  mov     edx, 0B3h; void *
0x1800b6f7d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
