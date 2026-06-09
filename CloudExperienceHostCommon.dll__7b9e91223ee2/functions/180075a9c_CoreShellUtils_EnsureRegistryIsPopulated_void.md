# CoreShellUtils::EnsureRegistryIsPopulated(void)

- ea: `0x180075a9c`
- end: `0x180075b3f`
- name: `?EnsureRegistryIsPopulated@CoreShellUtils@@YAXXZ`
- size: `163`
- prototype: `void __fastcall(CoreShellUtils *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800763c4`
- `0x180076d64`

## callees

- `0x18001475c`
- `0x1800756a0`
- `0x180075a9c`
- `0x1800774f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180075aea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180075aea`
- `api-ms-win-shcore-registry-l1-1-0!SHCopyKeyW` at `0x180075b19`
- `api-ms-win-shcore-registry-l1-1-0!SHCopyKeyW` at `0x180075b19`

## string_xrefs

- `0x180075adc`: `Software\Microsoft\CoreShell\Composer`

## pseudocode

```c
void __fastcall CoreShellUtils::EnsureRegistryIsPopulated(CoreShellUtils *this)
{
  HKEY hkeySrc; // [rsp+40h] [rbp+8h] BYREF
  HKEY hkeyDest; // [rsp+48h] [rbp+10h] BYREF

  if ( !`CoreShellUtils::EnsureRegistryIsPopulated'::`2'::registryHasBeenChecked
    && !CoreShellUtils::CheckForDefaultClassIdExistance(this) )
  {
    CoreShellUtils::OpenComposerClassRegistrationBaseKeyWithoutChecks(&hkeyDest);
    hkeySrc = 0;
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\CoreShell\\Composer", 0, 0xF003Fu, &hkeySrc) )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkeySrc);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkeyDest);
      return;
    }
    SHCopyKeyW(hkeySrc, 0, hkeyDest, 0);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkeySrc);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkeyDest);
  }
  `CoreShellUtils::EnsureRegistryIsPopulated'::`2'::registryHasBeenChecked = 1;
}

```

## disassembly

```asm
0x180075a9c  sub     rsp, 38h
0x180075aa0  cmp     cs:?registryHasBeenChecked@?1??EnsureRegistryIsPopulated@CoreShellUtils@@YAXXZ@4_NA, 0; bool `CoreShellUtils::EnsureRegistryIsPopulated(void)'::`2'::registryHasBeenChecked
0x180075aa7  jnz     loc_180075B33
0x180075aad  call    ?CheckForDefaultClassIdExistance@CoreShellUtils@@YA_NXZ; CoreShellUtils::CheckForDefaultClassIdExistance(void)
0x180075ab2  test    al, al
0x180075ab4  jnz     short loc_180075B33
0x180075ab6  lea     rcx, [rsp+38h+hkeyDest]
0x180075abb  call    ?OpenComposerClassRegistrationBaseKeyWithoutChecks@CoreShellUtils@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; CoreShellUtils::OpenComposerClassRegistrationBaseKeyWithoutChecks(void)
0x180075ac0  lea     rax, [rsp+38h+hkeySrc]
0x180075ac5  mov     [rsp+38h+hkeySrc], 0
0x180075ace  mov     r9d, 0F003Fh; samDesired
0x180075ad4  mov     [rsp+38h+phkResult], rax; phkResult
0x180075ad9  xor     r8d, r8d; ulOptions
0x180075adc  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\CoreShell\\Compose"...
0x180075ae3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180075aea  call    cs:__imp_RegOpenKeyExW
0x180075af0  test    eax, eax
0x180075af2  jz      short loc_180075B0A
0x180075af4  lea     rcx, [rsp+38h+hkeySrc]
0x180075af9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180075afe  lea     rcx, [rsp+38h+hkeyDest]
0x180075b03  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180075b08  jmp     short loc_180075B3A
0x180075b0a  mov     r8, [rsp+38h+hkeyDest]; hkeyDest
0x180075b0f  xor     r9d, r9d; fReserved
0x180075b12  mov     rcx, [rsp+38h+hkeySrc]; hkeySrc
0x180075b17  xor     edx, edx; pszSrcSubKey
0x180075b19  call    cs:__imp_SHCopyKeyW
0x180075b1f  lea     rcx, [rsp+38h+hkeySrc]
0x180075b24  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180075b29  lea     rcx, [rsp+38h+hkeyDest]
0x180075b2e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180075b33  mov     cs:?registryHasBeenChecked@?1??EnsureRegistryIsPopulated@CoreShellUtils@@YAXXZ@4_NA, 1; bool `CoreShellUtils::EnsureRegistryIsPopulated(void)'::`2'::registryHasBeenChecked
0x180075b3a  add     rsp, 38h
0x180075b3e  retn
```
