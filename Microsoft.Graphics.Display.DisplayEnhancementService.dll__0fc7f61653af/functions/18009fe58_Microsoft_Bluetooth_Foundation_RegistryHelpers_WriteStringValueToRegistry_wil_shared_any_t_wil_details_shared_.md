# Microsoft::Bluetooth::Foundation::RegistryHelpers::WriteStringValueToRegistry<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>>>(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18009fe58`
- end: `0x18009fec8`
- name: `??$WriteStringValueToRegistry@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@RegistryHelpers@Foundation@Bluetooth@Microsoft@@SAXAEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z`
- size: `112`
- prototype: `unsigned int __fastcall(__int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b1f04`
- `0x1800b1fec`
- `0x1800b2020`
- `0x1800b2138`

## callees

- `0x18000fa0c`
- `0x180013578`
- `0x18009fe58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009fe9f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009fe9f`

## string_xrefs

- `0x18009feae`: `onecore\private\drivers\inc\bluetooth\foundation\RegistryHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
unsigned int __fastcall Microsoft::Bluetooth::Foundation::RegistryHelpers::WriteStringValueToRegistry<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rax
  __int64 v4; // rdx
  const WCHAR *v5; // rax
  const BYTE *v6; // r8
  DWORD cbData; // r10d
  HKEY *v8; // r9
  HKEY v9; // rcx
  unsigned int result; // eax
  unsigned int lpData; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v3 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3, a2, a3);
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v4, v4, v3);
  v9 = *v8;
  if ( *v8 )
    v9 = *(HKEY *)v9;
  result = RegSetValueExW(v9, v5, 0, 1u, v6, cbData);
  if ( result )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x62,
      (unsigned int)"onecore\\private\\drivers\\inc\\bluetooth\\foundation\\RegistryHelpers.h",
      (const char *)result,
      lpData);
  return result;
}

```

## disassembly

```asm
0x18009fe58  sub     rsp, 38h
0x18009fe5c  mov     eax, [r8+10h]
0x18009fe60  mov     r9, rcx
0x18009fe63  mov     rcx, r8
0x18009fe66  lea     r10d, ds:2[rax*2]
0x18009fe6e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009fe73  mov     rcx, rdx
0x18009fe76  mov     r8, rax
0x18009fe79  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009fe7e  mov     rcx, [r9]
0x18009fe81  test    rcx, rcx
0x18009fe84  jz      short loc_18009FE89
0x18009fe86  mov     rcx, [rcx]; hKey
0x18009fe89  mov     [rsp+38h+cbData], r10d; cbData
0x18009fe8e  mov     r9d, 1; dwType
0x18009fe94  mov     [rsp+38h+lpData], r8; unsigned int
0x18009fe99  mov     rdx, rax; lpValueName
0x18009fe9c  xor     r8d, r8d; Reserved
0x18009fe9f  call    cs:__imp_RegSetValueExW
0x18009fea5  test    eax, eax
0x18009fea7  jz      short loc_18009FEC3
0x18009fea9  mov     rcx, [rsp+38h]; this
0x18009feae  lea     r8, aOnecorePrivate; "onecore\\private\\drivers\\inc\\bluetoo"...
0x18009feb5  mov     r9d, eax; char *
0x18009feb8  mov     edx, 62h ; 'b'; void *
0x18009febd  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18009fec3  add     rsp, 38h
0x18009fec7  retn
```
