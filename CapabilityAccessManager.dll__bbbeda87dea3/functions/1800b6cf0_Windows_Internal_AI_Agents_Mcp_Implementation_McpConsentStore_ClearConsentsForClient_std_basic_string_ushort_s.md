# Windows::Internal::AI::Agents::Mcp::Implementation::McpConsentStore::ClearConsentsForClient(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800b6cf0`
- end: `0x1800b6da5`
- name: `?ClearConsentsForClient@McpConsentStore@Implementation@Mcp@Agents@AI@Internal@Windows@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180098720`

## callees

- `0x18002392c`
- `0x180029408`
- `0x1800299c4`
- `0x18002f280`
- `0x18005829c`
- `0x1800b6cf0`
- `0x1800b7d6c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800b6d52`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800b6d52`
- `ext-ms-win-capabilityaccessmanager-storage-l1-1-0!EraseUInt64MCPSettingsForClient` at `0x1800b6d26`
- `ext-ms-win-capabilityaccessmanager-storage-l1-1-0!EraseUInt64MCPSettingsForClient` at `0x1800b6d26`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::AI::Agents::Mcp::Implementation::McpConsentStore::ClearConsentsForClient(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rdx
  __int64 v5; // rax
  __int64 result; // rax
  unsigned int v7; // eax
  unsigned int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HKEY hKey; // [rsp+40h] [rbp+18h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID59213523>::GetImpl'::`2'::impl) )
  {
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
    result = EraseUInt64MCPSettingsForClient(v5);
    if ( (int)result < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE5,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\mcpconsentstore.cpp",
        (const char *)(unsigned int)result,
        v8);
  }
  else
  {
    hKey = 0;
    Windows::Internal::AI::Agents::Mcp::Implementation::McpConsentStore::OpenTemporaryRegistryStoreWithOffset(
      &hKey,
      v4,
      a1,
      a2);
    v7 = RegDeleteTreeW(hKey, 0);
    if ( v7 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xF1,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\mcpconsentstore.cpp",
        (const char *)v7,
        v8);
    return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  return result;
}

```

## disassembly

```asm
0x1800b6cf0  mov     [rsp+arg_0], rbx
0x1800b6cf5  push    rdi; int
0x1800b6cf6  sub     rsp, 20h
0x1800b6cfa  mov     rbx, rdx
0x1800b6cfd  mov     rdi, rcx
0x1800b6d00  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID59213523@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID59213523@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523> `wil::Feature<__WilFeatureTraits_Feature_ID59213523>::GetImpl(void)'::`2'::impl
0x1800b6d07  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59213523@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523>::__private_IsEnabled(void)
0x1800b6d0c  test    al, al
0x1800b6d0e  jz      short loc_1800B6D32
0x1800b6d10  mov     rcx, rbx
0x1800b6d13  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b6d18  mov     rdx, rax
0x1800b6d1b  mov     rcx, rdi
0x1800b6d1e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b6d23  mov     rcx, rax
0x1800b6d26  call    cs:__imp_EraseUInt64MCPSettingsForClient
0x1800b6d2c  test    eax, eax
0x1800b6d2e  js      short loc_1800B6D8B
0x1800b6d30  jmp     short loc_1800B6D6B
0x1800b6d32  mov     [rsp+28h+hKey], 0
0x1800b6d3b  mov     r9, rbx
0x1800b6d3e  mov     r8, rdi
0x1800b6d41  lea     rcx, [rsp+28h+hKey]; phkResult
0x1800b6d46  call    ?OpenTemporaryRegistryStoreWithOffset@McpConsentStore@Implementation@Mcp@Agents@AI@Internal@Windows@@CAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; Windows::Internal::AI::Agents::Mcp::Implementation::McpConsentStore::OpenTemporaryRegistryStoreWithOffset(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,ulong,std::wstring const &,std::wstring const &)
0x1800b6d4b  xor     edx, edx; lpSubKey
0x1800b6d4d  mov     rcx, [rsp+28h+hKey]; hKey
0x1800b6d52  call    cs:__imp_RegDeleteTreeW
0x1800b6d58  mov     rcx, [rsp+28h]; this
0x1800b6d5d  test    eax, eax
0x1800b6d5f  jnz     short loc_1800B6D76
0x1800b6d61  lea     rcx, [rsp+28h+hKey]
0x1800b6d66  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b6d6b  mov     rbx, [rsp+28h+arg_0]
0x1800b6d70  add     rsp, 20h
0x1800b6d74  pop     rdi
0x1800b6d75  retn
0x1800b6d76  mov     r9d, eax; char *
0x1800b6d79  lea     r8, aOnecoreBaseDev_34; "onecore\\base\\devices\\cam\\core\\mcpc"...
0x1800b6d80  mov     edx, 0F1h; void *
0x1800b6d85  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800b6d8b  mov     rcx, [rsp+28h]; this
0x1800b6d90  mov     r9d, eax; char *
0x1800b6d93  lea     r8, aOnecoreBaseDev_34; "onecore\\base\\devices\\cam\\core\\mcpc"...
0x1800b6d9a  mov     edx, 0E5h; void *
0x1800b6d9f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
