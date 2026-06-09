# Windows::Internal::CapabilityAccess::Private::Globals::RegistryConfig::IsFirstBoot(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &)

- ea: `0x18002ede4`
- end: `0x18002ee72`
- name: `?IsFirstBoot@RegistryConfig@Globals@Private@CapabilityAccess@Internal@Windows@@CA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `142`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002ea0c`

## callees

- `0x180021550`
- `0x180023b38`
- `0x18002ede4`
- `0x18002f800`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ee46`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ee46`

## string_xrefs

- `0x18002ee00`: `OOBECompleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Windows::Internal::CapabilityAccess::Private::Globals::RegistryConfig::IsFirstBoot(
        Windows::Internal::CapabilityAccess::Private **a1)
{
  bool v2; // bl
  bool *phkResult; // [rsp+20h] [rbp-18h]
  unsigned __int16 v5; // [rsp+40h] [rbp+8h] BYREF
  HKEY v6; // [rsp+48h] [rbp+10h] BYREF

  v6 = 0;
  LOBYTE(v5) = 0;
  Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
    *a1,
    (HKEY)&stru_1800555D0,
    L"OOBECompleted",
    &v5,
    phkResult);
  if ( (_BYTE)v5 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v6,
      0);
    v2 = RegOpenKeyExW((HKEY)*a1, L"FirstBoot", 0, 0x20119u, &v6) == 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v6);
    return v2;
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v6);
    return 1;
  }
}

```

## disassembly

```asm
0x18002ede4  push    rbx
0x18002ede6  sub     rsp, 30h
0x18002edea  mov     rbx, rcx
0x18002eded  mov     [rsp+38h+arg_8], 0
0x18002edf6  mov     byte ptr [rsp+38h+arg_0], 0
0x18002edfb  lea     r9, [rsp+38h+arg_0]; unsigned __int16 *
0x18002ee00  lea     r8, aOobecompleted; "OOBECompleted"
0x18002ee07  lea     rdx, stru_1800555D0; HKEY
0x18002ee0e  mov     rcx, [rcx]; this
0x18002ee11  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x18002ee16  cmp     byte ptr [rsp+38h+arg_0], 0
0x18002ee1b  jz      short loc_18002EE60
0x18002ee1d  xor     edx, edx
0x18002ee1f  lea     rcx, [rsp+38h+arg_8]
0x18002ee24  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002ee29  lea     rax, [rsp+38h+arg_8]
0x18002ee2e  mov     [rsp+38h+phkResult], rax; phkResult
0x18002ee33  mov     r9d, 20119h; samDesired
0x18002ee39  xor     r8d, r8d; ulOptions
0x18002ee3c  lea     rdx, aFirstboot; "FirstBoot"
0x18002ee43  mov     rcx, [rbx]; hKey
0x18002ee46  call    cs:__imp_RegOpenKeyExW
0x18002ee4c  nop
0x18002ee4d  test    eax, eax
0x18002ee4f  setz    bl
0x18002ee52  lea     rcx, [rsp+38h+arg_8]
0x18002ee57  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002ee5c  mov     al, bl
0x18002ee5e  jmp     short loc_18002EE6C
0x18002ee60  lea     rcx, [rsp+38h+arg_8]
0x18002ee65  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002ee6a  mov     al, 1
0x18002ee6c  add     rsp, 30h
0x18002ee70  pop     rbx
0x18002ee71  retn
```
