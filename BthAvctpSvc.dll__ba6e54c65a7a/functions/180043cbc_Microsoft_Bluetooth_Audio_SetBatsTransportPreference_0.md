# Microsoft::Bluetooth::Audio::SetBatsTransportPreference_0

- ea: `0x180043cbc`
- end: `0x180043d90`
- name: `Microsoft::Bluetooth::Audio::SetBatsTransportPreference_0`
- size: `212`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180041708`

## callees

- `0x180015b1c`
- `0x180019f80`
- `0x180043cbc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180043d82`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180043d82`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180043d18`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180043d18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043d02`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043d02`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180043d4a`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180043d4a`

## string_xrefs

- `0x180043cf4`: `System\CurrentControlSet\Services\BthAvctpSvc\Parameters\Bats`
- `0x180043d43`: `System\CurrentControlSet\Services\BthAvctpSvc\Parameters\Bats`

## pseudocode

```c
char __fastcall Microsoft::Bluetooth::Audio::SetBatsTransportPreference_0(int a1)
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
      if ( !RegSetValueExW(hKey, L"SystemCurrentlyPrefersClassicAudio", 0, 4u, (const BYTE *)&Data, 4u) )
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
      RegDeleteValueW(hKey, L"SystemCurrentlyPrefersClassicAudio");
  }
  v2 = 0;
LABEL_5:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v2;
}

```

## disassembly

```asm
0x180043cbc  mov     [rsp+hKey], rdx
0x180043cc1  push    rbx
0x180043cc2  sub     rsp, 30h
0x180043cc6  xor     edx, edx
0x180043cc8  mov     [rsp+38h+hKey], 0
0x180043cd1  test    ecx, ecx
0x180043cd3  mov     ebx, ecx
0x180043cd5  lea     rcx, [rsp+38h+hKey]
0x180043cda  jnz     short loc_180043D32
0x180043cdc  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180043ce1  lea     rax, [rsp+38h+hKey]
0x180043ce6  mov     r9d, 2; samDesired
0x180043cec  xor     r8d, r8d; ulOptions
0x180043cef  mov     [rsp+38h+phkResult], rax; phkResult
0x180043cf4  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Bt"...
0x180043cfb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180043d02  call    cs:__imp_RegOpenKeyExW
0x180043d08  test    eax, eax
0x180043d0a  jnz     short loc_180043D1E
0x180043d0c  mov     rcx, [rsp+38h+hKey]; hKey
0x180043d11  lea     rdx, aSystemcurrentl; "SystemCurrentlyPrefersClassicAudio"
0x180043d18  call    cs:__imp_RegDeleteValueW
0x180043d1e  xor     ebx, ebx
0x180043d20  lea     rcx, [rsp+38h+hKey]
0x180043d25  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180043d2a  mov     al, bl
0x180043d2c  add     rsp, 30h
0x180043d30  pop     rbx
0x180043d31  retn
0x180043d32  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180043d37  lea     r8, [rsp+38h+hKey]; phkResult
0x180043d3c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180043d43  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Bt"...
0x180043d4a  call    cs:__imp_RegCreateKeyW
0x180043d50  test    eax, eax
0x180043d52  jnz     short loc_180043D1E
0x180043d54  mov     rcx, [rsp+38h+hKey]; hKey
0x180043d59  lea     rdx, aSystemcurrentl; "SystemCurrentlyPrefersClassicAudio"
0x180043d60  mov     r9d, 4; dwType
0x180043d66  cmp     ebx, 2
0x180043d69  mov     [rsp+38h+cbData], r9d; cbData
0x180043d6e  setz    al
0x180043d71  xor     r8d, r8d; Reserved
0x180043d74  mov     [rsp+38h+Data], eax
0x180043d78  lea     rax, [rsp+38h+Data]
0x180043d7d  mov     [rsp+38h+phkResult], rax; lpData
0x180043d82  call    cs:__imp_RegSetValueExW
0x180043d88  test    eax, eax
0x180043d8a  jnz     short loc_180043D1E
0x180043d8c  mov     bl, 1
0x180043d8e  jmp     short loc_180043D20
```
