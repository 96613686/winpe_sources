# Microsoft::Bluetooth::Audio::SetBatsTransportPreference

- ea: `0x18003d060`
- end: `0x18003d134`
- name: `Microsoft::Bluetooth::Audio::SetBatsTransportPreference`
- size: `212`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003d140`

## callees

- `0x180015b1c`
- `0x180019f80`
- `0x18003d060`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003d126`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003d126`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003d0bc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003d0bc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d0a6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d0a6`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18003d0ee`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18003d0ee`

## string_xrefs

- `0x18003d098`: `System\CurrentControlSet\Services\BthAvctpSvc\Parameters\Bats`
- `0x18003d0e7`: `System\CurrentControlSet\Services\BthAvctpSvc\Parameters\Bats`

## pseudocode

```c
char __fastcall Microsoft::Bluetooth::Audio::SetBatsTransportPreference(int a1)
{
  char v2; // bl
  BOOL Data; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  if ( a1 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    if ( !RegCreateKeyW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Services\\BthAvctpSvc\\Parameters\\Bats",
            &hKey) )
    {
      Data = a1 == 2;
      if ( !RegSetValueExW(hKey, L"UserPrefersClassicAudio", 0, 4u, (const BYTE *)&Data, 4u) )
      {
        v2 = 1;
        goto LABEL_5;
      }
    }
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Services\\BthAvctpSvc\\Parameters\\Bats",
            0,
            2u,
            &hKey) )
      RegDeleteValueW(hKey, L"UserPrefersClassicAudio");
  }
  v2 = 0;
LABEL_5:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v2;
}

```

## disassembly

```asm
0x18003d060  mov     [rsp+hKey], rdx
0x18003d065  push    rbx
0x18003d066  sub     rsp, 30h
0x18003d06a  xor     edx, edx
0x18003d06c  mov     [rsp+38h+hKey], 0
0x18003d075  test    ecx, ecx
0x18003d077  mov     ebx, ecx
0x18003d079  lea     rcx, [rsp+38h+hKey]
0x18003d07e  jnz     short loc_18003D0D6
0x18003d080  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003d085  lea     rax, [rsp+38h+hKey]
0x18003d08a  mov     r9d, 2; samDesired
0x18003d090  xor     r8d, r8d; ulOptions
0x18003d093  mov     [rsp+38h+phkResult], rax; phkResult
0x18003d098  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Bt"...
0x18003d09f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003d0a6  call    cs:__imp_RegOpenKeyExW
0x18003d0ac  test    eax, eax
0x18003d0ae  jnz     short loc_18003D0C2
0x18003d0b0  mov     rcx, [rsp+38h+hKey]; hKey
0x18003d0b5  lea     rdx, ValueName; "UserPrefersClassicAudio"
0x18003d0bc  call    cs:__imp_RegDeleteValueW
0x18003d0c2  xor     ebx, ebx
0x18003d0c4  lea     rcx, [rsp+38h+hKey]
0x18003d0c9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003d0ce  mov     al, bl
0x18003d0d0  add     rsp, 30h
0x18003d0d4  pop     rbx
0x18003d0d5  retn
0x18003d0d6  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003d0db  lea     r8, [rsp+38h+hKey]; phkResult
0x18003d0e0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003d0e7  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Bt"...
0x18003d0ee  call    cs:__imp_RegCreateKeyW
0x18003d0f4  test    eax, eax
0x18003d0f6  jnz     short loc_18003D0C2
0x18003d0f8  mov     rcx, [rsp+38h+hKey]; hKey
0x18003d0fd  lea     rdx, ValueName; "UserPrefersClassicAudio"
0x18003d104  mov     r9d, 4; dwType
0x18003d10a  cmp     ebx, 2
0x18003d10d  mov     [rsp+38h+cbData], r9d; cbData
0x18003d112  setz    al
0x18003d115  xor     r8d, r8d; Reserved
0x18003d118  mov     [rsp+38h+Data], eax
0x18003d11c  lea     rax, [rsp+38h+Data]
0x18003d121  mov     [rsp+38h+phkResult], rax; lpData
0x18003d126  call    cs:__imp_RegSetValueExW
0x18003d12c  test    eax, eax
0x18003d12e  jnz     short loc_18003D0C2
0x18003d130  mov     bl, 1
0x18003d132  jmp     short loc_18003D0C4
```
