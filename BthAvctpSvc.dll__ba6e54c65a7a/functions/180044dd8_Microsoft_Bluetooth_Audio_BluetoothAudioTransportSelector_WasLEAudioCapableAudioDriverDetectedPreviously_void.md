# Microsoft::Bluetooth::Audio::BluetoothAudioTransportSelector::WasLEAudioCapableAudioDriverDetectedPreviously(void)

- ea: `0x180044dd8`
- end: `0x180044e7b`
- name: `?WasLEAudioCapableAudioDriverDetectedPreviously@BluetoothAudioTransportSelector@Audio@Bluetooth@Microsoft@@AEBA_NXZ`
- size: `163`
- prototype: `bool __fastcall(Microsoft::Bluetooth::Audio::BluetoothAudioTransportSelector *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180041708`

## callees

- `0x180015b1c`
- `0x180019f80`
- `0x180044dd8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180044e16`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180044e16`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180044e57`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180044e57`

## string_xrefs

- `0x180044e08`: `System\CurrentControlSet\Services\BthAvctpSvc\Parameters\Bats`

## pseudocode

```c
bool __fastcall Microsoft::Bluetooth::Audio::BluetoothAudioTransportSelector::WasLEAudioCapableAudioDriverDetectedPreviously(
        Microsoft::Bluetooth::Audio::BluetoothAudioTransportSelector *this)
{
  bool v1; // bl
  Microsoft::Bluetooth::Audio::BluetoothAudioTransportSelector *pvData; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hkey; // [rsp+60h] [rbp+18h] BYREF

  pvData = this;
  v1 = 0;
  hkey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\BthAvctpSvc\\Parameters\\Bats",
          0,
          0x20019u,
          &hkey) )
  {
    LODWORD(pvData) = 0;
    pcbData = 4;
    if ( !RegGetValueW(
            hkey,
            0,
            Microsoft::Bluetooth::Audio::BluetoothAudioTransportSelector::c_leAudioCapableAudioDriverDetected,
            0x10u,
            0,
            &pvData,
            &pcbData) )
      v1 = (_DWORD)pvData != 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return v1;
}

```

## disassembly

```asm
0x180044dd8  mov     [rsp+arg_0], rcx
0x180044ddd  push    rbx
0x180044dde  sub     rsp, 40h
0x180044de2  xor     ebx, ebx
0x180044de4  lea     rcx, [rsp+48h+hkey]
0x180044de9  xor     edx, edx
0x180044deb  mov     [rsp+48h+hkey], rbx
0x180044df0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180044df5  lea     rax, [rsp+48h+hkey]
0x180044dfa  mov     r9d, 20019h; samDesired
0x180044e00  xor     r8d, r8d; ulOptions
0x180044e03  mov     [rsp+48h+phkResult], rax; phkResult
0x180044e08  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Bt"...
0x180044e0f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180044e16  call    cs:__imp_RegOpenKeyExW
0x180044e1c  test    eax, eax
0x180044e1e  jnz     short loc_180044E69
0x180044e20  mov     r8, cs:?c_leAudioCapableAudioDriverDetected@BluetoothAudioTransportSelector@Audio@Bluetooth@Microsoft@@0V?$basic_zstring_view@G@wil@@B; lpValue
0x180044e27  lea     rax, [rsp+48h+arg_8]
0x180044e2c  mov     rcx, [rsp+48h+hkey]; hkey
0x180044e31  lea     r9d, [rbx+10h]; dwFlags
0x180044e35  mov     [rsp+48h+pcbData], rax; pcbData
0x180044e3a  xor     edx, edx; lpSubKey
0x180044e3c  lea     rax, [rsp+48h+arg_0]
0x180044e41  mov     dword ptr [rsp+48h+arg_0], ebx
0x180044e45  mov     [rsp+48h+pvData], rax; pvData
0x180044e4a  mov     [rsp+48h+phkResult], rbx; pdwType
0x180044e4f  mov     [rsp+48h+arg_8], 4
0x180044e57  call    cs:__imp_RegGetValueW
0x180044e5d  test    eax, eax
0x180044e5f  jnz     short loc_180044E69
0x180044e61  cmp     dword ptr [rsp+48h+arg_0], ebx
0x180044e65  jz      short loc_180044E69
0x180044e67  mov     bl, 1
0x180044e69  lea     rcx, [rsp+48h+hkey]
0x180044e6e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180044e73  mov     al, bl
0x180044e75  add     rsp, 40h
0x180044e79  pop     rbx
0x180044e7a  retn
```
