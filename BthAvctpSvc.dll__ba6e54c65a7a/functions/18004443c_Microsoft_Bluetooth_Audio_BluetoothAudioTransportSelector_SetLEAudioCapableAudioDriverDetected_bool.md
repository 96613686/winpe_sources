# Microsoft::Bluetooth::Audio::BluetoothAudioTransportSelector::SetLEAudioCapableAudioDriverDetected(bool)

- ea: `0x18004443c`
- end: `0x1800444f2`
- name: `?SetLEAudioCapableAudioDriverDetected@BluetoothAudioTransportSelector@Audio@Bluetooth@Microsoft@@AEAAX_N@Z`
- size: `182`
- prototype: `void __fastcall(Microsoft::Bluetooth::Audio::BluetoothAudioTransportSelector *__hidden this, bool)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180041708`
- `0x180041f4c`
- `0x18004209c`

## callees

- `0x18000e0e0`
- `0x180015b1c`
- `0x180019f80`
- `0x18004443c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800444a8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800444a8`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180044471`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180044471`

## string_xrefs

- `0x180044463`: `System\CurrentControlSet\Services\BthAvctpSvc\Parameters\Bats`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::Bluetooth::Audio::BluetoothAudioTransportSelector::SetLEAudioCapableAudioDriverDetected(
        Microsoft::Bluetooth::Audio::BluetoothAudioTransportSelector *this,
        unsigned __int8 a2)
{
  int v2; // ebx
  unsigned int v3; // eax
  unsigned int v4; // eax
  const char *v5; // r9
  __int64 *v6; // rdx
  __int64 v7; // [rsp+0h] [rbp-38h] BYREF
  BYTE *lpData; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  Microsoft::Bluetooth::Audio::BluetoothAudioTransportSelector *Data; // [rsp+40h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp+18h] BYREF

  Data = this;
  v2 = a2;
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v3 = RegCreateKeyW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\BthAvctpSvc\\Parameters\\Bats",
         &phkResult);
  if ( v3 )
  {
    try
    {
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x4BF,
        (unsigned int)"onecore\\drivers\\bluetooth\\audio\\internal\\bluetoothaudiotransportselector\\bluetoothaudiotrans"
                      "portselector.cpp",
        (const char *)v3,
        (unsigned int)lpData);
    }
    catch ( ... )
    {
      v6 = &v7;
      wil::details::in1diag3::Log_CaughtException(
        (wil::details::in1diag3 *)v6[7],
        (void *)0x4CA,
        (unsigned int)"onecore\\drivers\\bluetooth\\audio\\internal\\bluetoothaudiotransportselector\\bluetoothaudiotrans"
                      "portselector.cpp",
        v5);
      return;
    }
  }
  LODWORD(Data) = v2;
  v4 = RegSetValueExW(
         phkResult,
         Microsoft::Bluetooth::Audio::BluetoothAudioTransportSelector::c_leAudioCapableAudioDriverDetected,
         0,
         4u,
         (const BYTE *)&Data,
         4u);
  if ( v4 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x4C8,
      (unsigned int)"onecore\\drivers\\bluetooth\\audio\\internal\\bluetoothaudiotransportselector\\bluetoothaudiotransportselector.cpp",
      (const char *)v4,
      (unsigned int)lpData);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
}

```

## disassembly

```asm
0x18004443c  mov     [rsp+Data], rcx
0x180044441  push    rbx
0x180044442  sub     rsp, 30h
0x180044446  movzx   ebx, dl
0x180044449  mov     [rsp+38h+phkResult], 0
0x180044452  xor     edx, edx
0x180044454  lea     rcx, [rsp+38h+phkResult]
0x180044459  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004445e  lea     r8, [rsp+38h+phkResult]; phkResult
0x180044463  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Bt"...
0x18004446a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180044471  call    cs:__imp_RegCreateKeyW
0x180044477  mov     rcx, [rsp+38h]; this
0x18004447c  test    eax, eax
0x18004447e  jnz     short loc_1800444C8
0x180044480  mov     dword ptr [rsp+38h+Data], ebx
0x180044484  mov     r9d, 4; dwType
0x18004448a  mov     [rsp+38h+cbData], r9d; cbData
0x18004448f  lea     rax, [rsp+38h+Data]
0x180044494  mov     [rsp+38h+lpData], rax; unsigned int
0x180044499  xor     r8d, r8d; Reserved
0x18004449c  mov     rdx, cs:?c_leAudioCapableAudioDriverDetected@BluetoothAudioTransportSelector@Audio@Bluetooth@Microsoft@@0V?$basic_zstring_view@G@wil@@B; lpValueName
0x1800444a3  mov     rcx, [rsp+38h+phkResult]; hKey
0x1800444a8  call    cs:__imp_RegSetValueExW
0x1800444ae  mov     rcx, [rsp+38h]; this
0x1800444b3  test    eax, eax
0x1800444b5  jnz     short loc_1800444DC
0x1800444b7  lea     rcx, [rsp+38h+phkResult]
0x1800444bc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800444c1  nop
0x1800444c2  add     rsp, 30h
0x1800444c6  pop     rbx
0x1800444c7  retn
0x1800444c8  mov     r9d, eax; char *
0x1800444cb  lea     r8, aOnecoreDrivers; "onecore\\drivers\\bluetooth\\audio\\int"...
0x1800444d2  mov     edx, 4BFh; void *
0x1800444d7  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800444dc  mov     r9d, eax; char *
0x1800444df  lea     r8, aOnecoreDrivers; "onecore\\drivers\\bluetooth\\audio\\int"...
0x1800444e6  mov     edx, 4C8h; void *
0x1800444eb  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
