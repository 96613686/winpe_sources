# ProviderSubSystem_Common_Globals::InitializeTransmitSize(void)

- ea: `0x14001ff6c`
- end: `0x140020001`
- name: `?InitializeTransmitSize@ProviderSubSystem_Common_Globals@@SAKXZ`
- size: `149`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001f9c4`

## callees

- `0x14001ff6c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001ffe5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001ffe5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001ffa4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001ffa4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001fff0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001fff0`

## pseudocode

```c
__int64 ProviderSubSystem_Common_Globals::InitializeTransmitSize(void)
{
  DWORD cbData; // [rsp+40h] [rbp+8h] BYREF
  DWORD Type; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  *(_DWORD *)&ProviderSubSystem_Common_Globals::s_TransmitBufferSize = 0x40000;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\WBEM\\CIMOM", 0, 0x20119u, &hKey) )
  {
    Type = 4;
    cbData = 4;
    RegQueryValueExW(
      hKey,
      L"Sink Transmit Buffer Size",
      0,
      &Type,
      &ProviderSubSystem_Common_Globals::s_TransmitBufferSize,
      &cbData);
    RegCloseKey(hKey);
  }
  return *(unsigned int *)&ProviderSubSystem_Common_Globals::s_TransmitBufferSize;
}

```

## disassembly

```asm
0x14001ff6c  sub     rsp, 38h
0x14001ff70  lea     rax, [rsp+38h+hKey]
0x14001ff75  mov     cs:?s_TransmitBufferSize@ProviderSubSystem_Common_Globals@@2KA, 40000h; ulong ProviderSubSystem_Common_Globals::s_TransmitBufferSize
0x14001ff7f  mov     r9d, 20119h; samDesired
0x14001ff85  mov     [rsp+38h+phkResult], rax; phkResult
0x14001ff8a  xor     r8d, r8d; ulOptions
0x14001ff8d  mov     [rsp+38h+hKey], 0
0x14001ff96  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\WBEM\\CIMOM"
0x14001ff9d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001ffa4  call    cs:__imp_RegOpenKeyExW
0x14001ffaa  test    eax, eax
0x14001ffac  jnz     short loc_14001FFF6
0x14001ffae  mov     rcx, [rsp+38h+hKey]; hKey
0x14001ffb3  lea     r9, [rsp+38h+Type]; lpType
0x14001ffb8  mov     eax, 4
0x14001ffbd  lea     rdx, aSinkTransmitBu; "Sink Transmit Buffer Size"
0x14001ffc4  mov     [rsp+38h+Type], eax
0x14001ffc8  xor     r8d, r8d; lpReserved
0x14001ffcb  mov     [rsp+38h+cbData], eax
0x14001ffcf  lea     rax, [rsp+38h+cbData]
0x14001ffd4  mov     [rsp+38h+lpcbData], rax; lpcbData
0x14001ffd9  lea     rax, ?s_TransmitBufferSize@ProviderSubSystem_Common_Globals@@2KA; ulong ProviderSubSystem_Common_Globals::s_TransmitBufferSize
0x14001ffe0  mov     [rsp+38h+phkResult], rax; lpData
0x14001ffe5  call    cs:__imp_RegQueryValueExW
0x14001ffeb  mov     rcx, [rsp+38h+hKey]; hKey
0x14001fff0  call    cs:__imp_RegCloseKey
0x14001fff6  mov     eax, cs:?s_TransmitBufferSize@ProviderSubSystem_Common_Globals@@2KA; ulong ProviderSubSystem_Common_Globals::s_TransmitBufferSize
0x14001fffc  add     rsp, 38h
0x140020000  retn
```
