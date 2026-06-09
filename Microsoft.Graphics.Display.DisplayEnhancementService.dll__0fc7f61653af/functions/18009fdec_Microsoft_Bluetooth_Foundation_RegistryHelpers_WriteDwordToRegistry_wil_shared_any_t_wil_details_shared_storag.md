# Microsoft::Bluetooth::Foundation::RegistryHelpers::WriteDwordToRegistry<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>>>(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong)

- ea: `0x18009fdec`
- end: `0x18009fe4f`
- name: `??$WriteDwordToRegistry@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@RegistryHelpers@Foundation@Bluetooth@Microsoft@@SAXAEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b1dbc`
- `0x1800b2238`

## callees

- `0x18000fa0c`
- `0x180013578`
- `0x18009fdec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009fe26`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009fe26`

## string_xrefs

- `0x18009fe35`: `onecore\private\drivers\inc\bluetooth\foundation\RegistryHelpers.h`

## pseudocode

```c
unsigned int __fastcall Microsoft::Bluetooth::Foundation::RegistryHelpers::WriteDwordToRegistry<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>>>(
        __int64 a1,
        __int64 a2,
        int a3)
{
  const WCHAR *v3; // rax
  HKEY *v4; // r8
  HKEY v5; // rcx
  unsigned int result; // eax
  unsigned int lpData; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int Data; // [rsp+50h] [rbp+18h] BYREF

  Data = a3;
  v3 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2, a2, a1);
  v5 = *v4;
  if ( *v4 )
    v5 = *(HKEY *)v5;
  result = RegSetValueExW(v5, v3, 0, 4u, (const BYTE *)&Data, 4u);
  if ( result )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x27,
      (unsigned int)"onecore\\private\\drivers\\inc\\bluetooth\\foundation\\RegistryHelpers.h",
      (const char *)result,
      lpData);
  return result;
}

```

## disassembly

```asm
0x18009fdec  mov     [rsp+Data], r8d
0x18009fdf1  sub     rsp, 38h
0x18009fdf5  mov     r8, rcx
0x18009fdf8  mov     rcx, rdx
0x18009fdfb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009fe00  mov     rcx, [r8]
0x18009fe03  test    rcx, rcx
0x18009fe06  jz      short loc_18009FE0B
0x18009fe08  mov     rcx, [rcx]; hKey
0x18009fe0b  mov     r9d, 4; dwType
0x18009fe11  lea     rdx, [rsp+38h+Data]
0x18009fe16  mov     [rsp+38h+cbData], r9d; cbData
0x18009fe1b  xor     r8d, r8d; Reserved
0x18009fe1e  mov     [rsp+38h+lpData], rdx; unsigned int
0x18009fe23  mov     rdx, rax; lpValueName
0x18009fe26  call    cs:__imp_RegSetValueExW
0x18009fe2c  test    eax, eax
0x18009fe2e  jz      short loc_18009FE4A
0x18009fe30  mov     rcx, [rsp+38h]; this
0x18009fe35  lea     r8, aOnecorePrivate; "onecore\\private\\drivers\\inc\\bluetoo"...
0x18009fe3c  mov     r9d, eax; char *
0x18009fe3f  mov     edx, 27h ; '''; void *
0x18009fe44  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18009fe4a  add     rsp, 38h
0x18009fe4e  retn
```
