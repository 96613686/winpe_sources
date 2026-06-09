# ProviderSubSystem_Common_Globals::InitializeDefaultStackSize(void)

- ea: `0x14001feb8`
- end: `0x14001ff66`
- name: `?InitializeDefaultStackSize@ProviderSubSystem_Common_Globals@@SAKXZ`
- size: `174`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001f9c4`

## callees

- `0x14001feb8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001ff32`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001ff32`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001fef3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001fef3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001ff40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001ff40`

## pseudocode

```c
__int64 ProviderSubSystem_Common_Globals::InitializeDefaultStackSize(void)
{
  DWORD Type; // [rsp+40h] [rbp+10h] BYREF
  int Data; // [rsp+48h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  ProviderSubSystem_Common_Globals::s_DefaultStackSize = 0x8000;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Wbem\\Cimom", 0, 0x20119u, &hKey) )
  {
    Data = 0;
    Type = 4;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"DefaultRpcStackSize", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      ProviderSubSystem_Common_Globals::s_DefaultStackSize = Data << 10;
    RegCloseKey(hKey);
  }
  return ProviderSubSystem_Common_Globals::s_DefaultStackSize;
}

```

## disassembly

```asm
0x14001feb8  push    rbp
0x14001feba  mov     rbp, rsp
0x14001febd  sub     rsp, 30h
0x14001fec1  lea     rax, [rbp+hKey]
0x14001fec5  mov     cs:?s_DefaultStackSize@ProviderSubSystem_Common_Globals@@2KA, 8000h; ulong ProviderSubSystem_Common_Globals::s_DefaultStackSize
0x14001fecf  mov     r9d, 20119h; samDesired
0x14001fed5  mov     [rsp+30h+phkResult], rax; phkResult
0x14001feda  xor     r8d, r8d; ulOptions
0x14001fedd  mov     [rbp+hKey], 0
0x14001fee5  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Wbem\\Cimom"
0x14001feec  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001fef3  call    cs:__imp_RegOpenKeyExW
0x14001fef9  test    eax, eax
0x14001fefb  jnz     short loc_14001FF46
0x14001fefd  mov     rcx, [rbp+hKey]; hKey
0x14001ff01  lea     r9, [rbp+Type]; lpType
0x14001ff05  mov     [rbp+Data], eax
0x14001ff08  lea     rdx, aDefaultrpcstac; "DefaultRpcStackSize"
0x14001ff0f  lea     rax, [rbp+cbData]
0x14001ff13  mov     [rbp+Type], 4
0x14001ff1a  mov     [rsp+30h+lpcbData], rax; lpcbData
0x14001ff1f  xor     r8d, r8d; lpReserved
0x14001ff22  lea     rax, [rbp+Data]
0x14001ff26  mov     [rbp+cbData], 4
0x14001ff2d  mov     [rsp+30h+phkResult], rax; lpData
0x14001ff32  call    cs:__imp_RegQueryValueExW
0x14001ff38  test    eax, eax
0x14001ff3a  jz      short loc_14001FF52
0x14001ff3c  mov     rcx, [rbp+hKey]; hKey
0x14001ff40  call    cs:__imp_RegCloseKey
0x14001ff46  mov     eax, cs:?s_DefaultStackSize@ProviderSubSystem_Common_Globals@@2KA; ulong ProviderSubSystem_Common_Globals::s_DefaultStackSize
0x14001ff4c  add     rsp, 30h
0x14001ff50  pop     rbp
0x14001ff51  retn
0x14001ff52  cmp     [rbp+Type], 4
0x14001ff56  jnz     short loc_14001FF3C
0x14001ff58  mov     eax, [rbp+Data]
0x14001ff5b  shl     eax, 0Ah
0x14001ff5e  mov     cs:?s_DefaultStackSize@ProviderSubSystem_Common_Globals@@2KA, eax; ulong ProviderSubSystem_Common_Globals::s_DefaultStackSize
0x14001ff64  jmp     short loc_14001FF3C
```
