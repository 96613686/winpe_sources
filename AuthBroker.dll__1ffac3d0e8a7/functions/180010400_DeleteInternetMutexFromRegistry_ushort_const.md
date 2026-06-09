# _DeleteInternetMutexFromRegistry(ushort const *)

- ea: `0x180010400`
- end: `0x18001048c`
- name: `?_DeleteInternetMutexFromRegistry@@YAJPEBG@Z`
- size: `140`
- prototype: `__int64 __fastcall(const wchar_t *regValue)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ecc8`
- `0x1800201b0`

## callees

- `0x18000ed64`
- `0x18000f544`
- `0x180010400`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180010451`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180010451`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010433`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010433`

## string_xrefs

- `0x180010465`: `onecore\ds\security\webauth\authbroker\lib\brokeractivate.cpp`

## pseudocode

```c
__int64 __fastcall _DeleteInternetMutexFromRegistry(const wchar_t *regValue)
{
  LSTATUS v2; // eax
  unsigned int v3; // edx
  unsigned int v4; // ebx
  void *retaddr; // [rsp+38h] [rbp+0h]
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (__cdecl*)(HKEY__ *),&RegCloseKey,wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t> > > hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey.m_ptr = 0;
  v2 = RegOpenKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\WebAuthBridge\\Internet",
         0,
         2u,
         &hKey.m_ptr);
  if ( v2 == 2 )
    goto LABEL_7;
  if ( !v2 )
  {
    v2 = RegDeleteValueW(hKey.m_ptr, regValue);
    if ( v2 )
    {
      v3 = 1094;
      goto LABEL_6;
    }
LABEL_7:
    v4 = 0;
    goto LABEL_8;
  }
  v3 = 1093;
LABEL_6:
  v4 = wil::details::in1diag3::Return_Win32(
         retaddr,
         v3,
         "onecore\\ds\\security\\webauth\\authbroker\\lib\\brokeractivate.cpp",
         v2);
LABEL_8:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v4;
}

```

## disassembly

```asm
0x180010400  push    rbx
0x180010402  sub     rsp, 30h
0x180010406  mov     rbx, regValue
0x180010409  mov     [rsp+38h+hKey.m_ptr], 0
0x180010412  lea     rax, [rsp+38h+hKey]
0x180010417  mov     regValue, 0FFFFFFFF80000001h; hKey
0x18001041e  mov     r9d, 2; samDesired
0x180010424  mov     [rsp+38h+phkResult], rax; phkResult
0x180010429  xor     r8d, r8d; ulOptions
0x18001042c  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180010433  call    cs:__imp_RegOpenKeyExW
0x180010439  cmp     eax, 2
0x18001043c  jz      short loc_180010478
0x18001043e  test    eax, eax
0x180010440  jz      short loc_180010449
0x180010442  mov     edx, 445h
0x180010447  jmp     short loc_180010460
0x180010449  mov     regValue, [rsp+38h+hKey.m_ptr]; hKey
0x18001044e  mov     rdx, rbx; lpValueName
0x180010451  call    cs:__imp_RegDeleteValueW
0x180010457  test    eax, eax
0x180010459  jz      short loc_180010478
0x18001045b  mov     edx, 446h; lineNumber
0x180010460  mov     regValue, [rsp+38h]; callerReturnAddress
0x180010465  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\webauth\\authbro"...
0x18001046c  mov     r9d, eax; err
0x18001046f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180010474  mov     ebx, eax
0x180010476  jmp     short loc_18001047A
0x180010478  xor     ebx, ebx
0x18001047a  lea     regValue, [rsp+38h+hKey]; this
0x18001047f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180010484  mov     eax, ebx
0x180010486  add     rsp, 30h
0x18001048a  pop     rbx
0x18001048b  retn
```
