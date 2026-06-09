# DdcRegistry::GetQWORDValue(HKEY__ *,ushort const *,ushort const *,unsigned __int64 &)

- ea: `0x18001bae4`
- end: `0x18001bbe2`
- name: `?GetQWORDValue@DdcRegistry@@SAJPEAUHKEY__@@PEBG1AEA_K@Z`
- size: `254`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, BYTE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019648`

## callees

- `0x1800050b8`
- `0x18001bae4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bbca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bbca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bb26`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bb26`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001bb88`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001bb88`

## string_xrefs

- `0x18001bb5a`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcregistry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DdcRegistry::GetQWORDValue(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        BYTE *a4)
{
  LSTATUS v6; // eax
  int v7; // edx
  int v8; // ecx
  unsigned int v9; // ebx
  LSTATUS v10; // eax
  int v11; // edx
  int v12; // ecx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+8h] BYREF
  int v16; // [rsp+54h] [rbp+Ch]

  v16 = HIDWORD(a1);
  cbData = 8;
  hKey = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20019u, &hKey);
  v9 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v9 = (unsigned __int16)v6 | 0x80070000;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v8,
        v7,
        v9,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistry.cpp",
        145,
        "CBR(0L == dwResult)");
  }
  else
  {
    v10 = RegQueryValueExW(hKey, a3, 0, 0, a4, &cbData);
    v9 = v10;
    if ( v10 )
    {
      if ( v10 > 0 )
        v9 = (unsigned __int16)v10 | 0x80070000;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v12,
          v11,
          v9,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistry.cpp",
          154,
          "CBR(0L == dwResult)");
    }
    else
    {
      v9 = 0;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x18001bae4  mov     rax, rsp
0x18001bae7  mov     [rax+10h], rbx
0x18001baeb  mov     [rax+18h], rsi
0x18001baef  mov     [rax+8], rcx
0x18001baf3  push    rdi
0x18001baf4  sub     rsp, 40h
0x18001baf8  mov     dword ptr [rax+8], 8
0x18001baff  mov     rdi, r9
0x18001bb02  mov     qword ptr [rax-18h], 0
0x18001bb0a  lea     rax, [rax-18h]
0x18001bb0e  mov     rsi, r8
0x18001bb11  mov     [rsp+48h+phkResult], rax; phkResult
0x18001bb16  mov     r9d, 20019h; samDesired
0x18001bb1c  xor     r8d, r8d; ulOptions
0x18001bb1f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001bb26  call    cs:__imp_RegOpenKeyExW
0x18001bb2c  mov     ebx, eax
0x18001bb2e  test    eax, eax
0x18001bb30  jz      short loc_18001BB6B
0x18001bb32  jle     short loc_18001BB3D
0x18001bb34  movzx   ebx, ax
0x18001bb37  or      ebx, 80070000h
0x18001bb3d  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001bb44  jz      short loc_18001BBC0
0x18001bb46  lea     rax, aCbr0lDwresult; "CBR(0L == dwResult)"
0x18001bb4d  mov     [rsp+48h+lpcbData], rax
0x18001bb52  mov     dword ptr [rsp+48h+phkResult], 291h
0x18001bb5a  lea     r9, aOnecoreuapShel_0; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001bb61  mov     r8d, ebx
0x18001bb64  call    McTemplateU0dsqs_EventWriteTransfer
0x18001bb69  jmp     short loc_18001BBC0
0x18001bb6b  mov     rcx, [rsp+48h+hKey]; hKey
0x18001bb70  lea     rax, [rsp+48h+cbData]
0x18001bb75  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18001bb7a  xor     r9d, r9d; lpType
0x18001bb7d  xor     r8d, r8d; lpReserved
0x18001bb80  mov     [rsp+48h+phkResult], rdi; lpData
0x18001bb85  mov     rdx, rsi; lpValueName
0x18001bb88  call    cs:__imp_RegQueryValueExW
0x18001bb8e  mov     ebx, eax
0x18001bb90  test    eax, eax
0x18001bb92  jz      short loc_18001BBBE
0x18001bb94  jle     short loc_18001BB9F
0x18001bb96  movzx   ebx, ax
0x18001bb99  or      ebx, 80070000h
0x18001bb9f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001bba6  jz      short loc_18001BBC0
0x18001bba8  lea     rax, aCbr0lDwresult; "CBR(0L == dwResult)"
0x18001bbaf  mov     [rsp+48h+lpcbData], rax
0x18001bbb4  mov     dword ptr [rsp+48h+phkResult], 29Ah
0x18001bbbc  jmp     short loc_18001BB5A
0x18001bbbe  xor     ebx, ebx
0x18001bbc0  mov     rcx, [rsp+48h+hKey]; hKey
0x18001bbc5  test    rcx, rcx
0x18001bbc8  jz      short loc_18001BBD0
0x18001bbca  call    cs:__imp_RegCloseKey
0x18001bbd0  mov     rsi, [rsp+48h+arg_10]
0x18001bbd5  mov     eax, ebx
0x18001bbd7  mov     rbx, [rsp+48h+arg_8]
0x18001bbdc  add     rsp, 40h
0x18001bbe0  pop     rdi
0x18001bbe1  retn
```
