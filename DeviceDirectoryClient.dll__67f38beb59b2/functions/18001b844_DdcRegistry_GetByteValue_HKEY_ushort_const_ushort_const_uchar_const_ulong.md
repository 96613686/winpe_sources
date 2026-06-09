# DdcRegistry::GetByteValue(HKEY__ *,ushort const *,ushort const *,uchar * const,ulong &)

- ea: `0x18001b844`
- end: `0x18001b9d9`
- name: `?GetByteValue@DdcRegistry@@SAJPEAUHKEY__@@PEBG1QEAEAEAK@Z`
- size: `405`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 *const, LPDWORD lpcbData)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a7b8`
- `0x180019648`
- `0x180024d9c`

## callees

- `0x1800050b8`
- `0x18001b844`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b9c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b9c1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b882`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b882`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001b8e0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001b972`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001b8e0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001b972`

## string_xrefs

- `0x18001b9a8`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcregistry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DdcRegistry::GetByteValue(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int8 *const a4,
        LPDWORD lpcbData)
{
  LSTATUS v7; // eax
  int v8; // edx
  int v9; // ecx
  unsigned int v10; // ebx
  LSTATUS v11; // eax
  int v12; // edx
  int v13; // ecx
  LSTATUS v14; // eax
  int v15; // edx
  int v16; // ecx
  DWORD cbData; // [rsp+30h] [rbp-18h] BYREF
  DWORD Type; // [rsp+34h] [rbp-14h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-10h] BYREF

  cbData = 0;
  Type = 3;
  hKey = 0;
  v7 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
  v10 = v7;
  if ( v7 )
  {
    if ( v7 > 0 )
      v10 = (unsigned __int16)v7 | 0x80070000;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v9,
        v8,
        v10,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistry.cpp",
        31,
        "CBR(0L == dwResult)");
  }
  else
  {
    v11 = RegQueryValueExW(hKey, a3, 0, 0, 0, &cbData);
    v10 = v11;
    if ( v11 )
    {
      if ( v11 > 0 )
        v10 = (unsigned __int16)v11 | 0x80070000;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v13,
          v12,
          v10,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistry.cpp",
          41,
          "CBR(0L == dwResult)");
    }
    else
    {
      v10 = 0;
      if ( cbData )
      {
        if ( *lpcbData >= cbData )
        {
          v14 = RegQueryValueExW(hKey, a3, 0, &Type, a4, lpcbData);
          if ( v14 )
          {
            v10 = v14 > 0 ? (unsigned __int16)v14 | 0x80070000 : v14;
            if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
              McTemplateU0dsqs_EventWriteTransfer(
                v16,
                v15,
                v10,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistry.cpp",
                59,
                "CBR(0L == dwResult)");
          }
        }
        else
        {
          v10 = -2147024774;
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              (_DWORD)lpcbData,
              v12,
              -2147024774,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistry.cpp",
              49,
              "CBR(cbValue >= cbSize)");
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v10;
}

```

## disassembly

```asm
0x18001b844  mov     rax, rsp
0x18001b847  mov     [rax+8], rbx
0x18001b84b  mov     [rax+10h], rsi
0x18001b84f  push    rdi
0x18001b850  sub     rsp, 40h
0x18001b854  mov     dword ptr [rax-18h], 0
0x18001b85b  mov     rsi, r9
0x18001b85e  mov     dword ptr [rax-14h], 3
0x18001b865  mov     rdi, r8
0x18001b868  mov     qword ptr [rax-10h], 0
0x18001b870  lea     rax, [rax-10h]
0x18001b874  mov     r9d, 20019h; samDesired
0x18001b87a  mov     [rsp+48h+phkResult], rax; phkResult
0x18001b87f  xor     r8d, r8d; ulOptions
0x18001b882  call    cs:__imp_RegOpenKeyExW
0x18001b888  mov     ebx, eax
0x18001b88a  test    eax, eax
0x18001b88c  jz      short loc_18001B8BF
0x18001b88e  jle     short loc_18001B899
0x18001b890  movzx   ebx, ax
0x18001b893  or      ebx, 80070000h
0x18001b899  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001b8a0  jz      loc_18001B9B7
0x18001b8a6  lea     rax, aCbr0lDwresult; "CBR(0L == dwResult)"
0x18001b8ad  mov     [rsp+48h+lpcbData], rax
0x18001b8b2  mov     dword ptr [rsp+48h+phkResult], 1Fh
0x18001b8ba  jmp     loc_18001B9A8
0x18001b8bf  mov     rcx, [rsp+48h+hKey]; hKey
0x18001b8c4  lea     rax, [rsp+48h+cbData]
0x18001b8c9  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18001b8ce  xor     r9d, r9d; lpType
0x18001b8d1  xor     r8d, r8d; lpReserved
0x18001b8d4  mov     [rsp+48h+phkResult], 0; lpData
0x18001b8dd  mov     rdx, rdi; lpValueName
0x18001b8e0  call    cs:__imp_RegQueryValueExW
0x18001b8e6  mov     ebx, eax
0x18001b8e8  test    eax, eax
0x18001b8ea  jz      short loc_18001B91D
0x18001b8ec  jle     short loc_18001B8F7
0x18001b8ee  movzx   ebx, ax
0x18001b8f1  or      ebx, 80070000h
0x18001b8f7  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001b8fe  jz      loc_18001B9B7
0x18001b904  lea     rax, aCbr0lDwresult; "CBR(0L == dwResult)"
0x18001b90b  mov     [rsp+48h+lpcbData], rax
0x18001b910  mov     dword ptr [rsp+48h+phkResult], 29h ; ')'
0x18001b918  jmp     loc_18001B9A8
0x18001b91d  mov     eax, [rsp+48h+cbData]
0x18001b921  xor     ebx, ebx
0x18001b923  test    eax, eax
0x18001b925  jz      loc_18001B9B7
0x18001b92b  mov     rcx, [rsp+48h+arg_20]
0x18001b930  cmp     [rcx], eax
0x18001b932  jnb     short loc_18001B958
0x18001b934  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001b93b  mov     ebx, 8007007Ah
0x18001b940  jz      short loc_18001B9B7
0x18001b942  lea     rax, aCbrCbvalueCbsi; "CBR(cbValue >= cbSize)"
0x18001b949  mov     [rsp+48h+lpcbData], rax
0x18001b94e  mov     dword ptr [rsp+48h+phkResult], 31h ; '1'
0x18001b956  jmp     short loc_18001B9A8
0x18001b958  mov     [rsp+48h+lpcbData], rcx; lpcbData
0x18001b95d  lea     r9, [rsp+48h+Type]; lpType
0x18001b962  mov     rcx, [rsp+48h+hKey]; hKey
0x18001b967  xor     r8d, r8d; lpReserved
0x18001b96a  mov     rdx, rdi; lpValueName
0x18001b96d  mov     [rsp+48h+phkResult], rsi; lpData
0x18001b972  call    cs:__imp_RegQueryValueExW
0x18001b978  test    eax, eax
0x18001b97a  jz      short loc_18001B9B7
0x18001b97c  jg      short loc_18001B982
0x18001b97e  mov     ebx, eax
0x18001b980  jmp     short loc_18001B98B
0x18001b982  movzx   ebx, ax
0x18001b985  or      ebx, 80070000h
0x18001b98b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001b992  jz      short loc_18001B9B7
0x18001b994  lea     rax, aCbr0lDwresult; "CBR(0L == dwResult)"
0x18001b99b  mov     [rsp+48h+lpcbData], rax
0x18001b9a0  mov     dword ptr [rsp+48h+phkResult], 3Bh ; ';'
0x18001b9a8  lea     r9, aOnecoreuapShel_0; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001b9af  mov     r8d, ebx
0x18001b9b2  call    McTemplateU0dsqs_EventWriteTransfer
0x18001b9b7  mov     rcx, [rsp+48h+hKey]; hKey
0x18001b9bc  test    rcx, rcx
0x18001b9bf  jz      short loc_18001B9C7
0x18001b9c1  call    cs:__imp_RegCloseKey
0x18001b9c7  mov     rsi, [rsp+48h+arg_8]
0x18001b9cc  mov     eax, ebx
0x18001b9ce  mov     rbx, [rsp+48h+arg_0]
0x18001b9d3  add     rsp, 40h
0x18001b9d7  pop     rdi
0x18001b9d8  retn
```
