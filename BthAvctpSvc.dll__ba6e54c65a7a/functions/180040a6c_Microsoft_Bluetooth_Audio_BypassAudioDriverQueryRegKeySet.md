# Microsoft::Bluetooth::Audio::BypassAudioDriverQueryRegKeySet

- ea: `0x180040a6c`
- end: `0x180040afc`
- name: `Microsoft::Bluetooth::Audio::BypassAudioDriverQueryRegKeySet`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180041708`

## callees

- `0x180015b1c`
- `0x180019f80`
- `0x180040a6c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180040ad9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180040ad9`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x180040a98`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x180040a98`

## string_xrefs

- `0x180040a91`: `SYSTEM\CurrentControlSet\Services\BthAvctpSvc\Parameters\Settings`

## pseudocode

```c
bool Microsoft::Bluetooth::Audio::BypassAudioDriverQueryRegKeySet()
{
  bool v0; // bl
  int pvData; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp+18h] BYREF

  v0 = 0;
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  if ( !RegOpenKeyW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\BthAvctpSvc\\Parameters\\Settings",
          &phkResult) )
  {
    pvData = 0;
    pcbData = 4;
    if ( !RegGetValueW(phkResult, 0, L"BypassAudioDriverQuery", 0x18u, 0, &pvData, &pcbData) )
      v0 = pvData != 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  return v0;
}

```

## disassembly

```asm
0x180040a6c  push    rbx
0x180040a6e  sub     rsp, 40h
0x180040a72  xor     ebx, ebx
0x180040a74  lea     rcx, [rsp+48h+phkResult]
0x180040a79  xor     edx, edx
0x180040a7b  mov     [rsp+48h+phkResult], rbx
0x180040a80  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180040a85  lea     r8, [rsp+48h+phkResult]; phkResult
0x180040a8a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180040a91  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\Bt"...
0x180040a98  call    cs:__imp_RegOpenKeyW
0x180040a9e  test    eax, eax
0x180040aa0  jnz     short loc_180040AEA
0x180040aa2  mov     rcx, [rsp+48h+phkResult]; hkey
0x180040aa7  lea     rax, [rsp+48h+arg_8]
0x180040aac  mov     [rsp+48h+pcbData], rax; pcbData
0x180040ab1  lea     r9d, [rbx+18h]; dwFlags
0x180040ab5  lea     rax, [rsp+48h+arg_0]
0x180040aba  mov     [rsp+48h+arg_0], ebx
0x180040abe  mov     [rsp+48h+pvData], rax; pvData
0x180040ac3  lea     r8, aBypassaudiodri; "BypassAudioDriverQuery"
0x180040aca  xor     edx, edx; lpSubKey
0x180040acc  mov     [rsp+48h+pdwType], rbx; pdwType
0x180040ad1  mov     [rsp+48h+arg_8], 4
0x180040ad9  call    cs:__imp_RegGetValueW
0x180040adf  test    eax, eax
0x180040ae1  jnz     short loc_180040AEA
0x180040ae3  cmp     [rsp+48h+arg_0], ebx
0x180040ae7  setnz   bl
0x180040aea  lea     rcx, [rsp+48h+phkResult]
0x180040aef  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180040af4  mov     al, bl
0x180040af6  add     rsp, 40h
0x180040afa  pop     rbx
0x180040afb  retn
```
