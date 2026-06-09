# DdcRegistry::GetDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong &)

- ea: `0x18001b9e0`
- end: `0x18001bade`
- name: `?GetDWORDValue@DdcRegistry@@SAJPEAUHKEY__@@PEBG1AEAK@Z`
- size: `254`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, BYTE *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016aa4`
- `0x180019648`

## callees

- `0x1800050b8`
- `0x18001b9e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bac6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bac6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ba22`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ba22`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ba84`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ba84`

## string_xrefs

- `0x18001ba56`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcregistry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DdcRegistry::GetDWORDValue(
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
  cbData = 4;
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
        166,
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
          175,
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
0x18001b9e0  mov     rax, rsp
0x18001b9e3  mov     [rax+10h], rbx
0x18001b9e7  mov     [rax+18h], rsi
0x18001b9eb  mov     [rax+8], rcx
0x18001b9ef  push    rdi
0x18001b9f0  sub     rsp, 40h
0x18001b9f4  mov     dword ptr [rax+8], 4
0x18001b9fb  mov     rdi, r9
0x18001b9fe  mov     qword ptr [rax-18h], 0
0x18001ba06  lea     rax, [rax-18h]
0x18001ba0a  mov     rsi, r8
0x18001ba0d  mov     [rsp+48h+phkResult], rax; phkResult
0x18001ba12  mov     r9d, 20019h; samDesired
0x18001ba18  xor     r8d, r8d; ulOptions
0x18001ba1b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001ba22  call    cs:__imp_RegOpenKeyExW
0x18001ba28  mov     ebx, eax
0x18001ba2a  test    eax, eax
0x18001ba2c  jz      short loc_18001BA67
0x18001ba2e  jle     short loc_18001BA39
0x18001ba30  movzx   ebx, ax
0x18001ba33  or      ebx, 80070000h
0x18001ba39  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001ba40  jz      short loc_18001BABC
0x18001ba42  lea     rax, aCbr0lDwresult; "CBR(0L == dwResult)"
0x18001ba49  mov     [rsp+48h+lpcbData], rax
0x18001ba4e  mov     dword ptr [rsp+48h+phkResult], 0A6h
0x18001ba56  lea     r9, aOnecoreuapShel_0; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001ba5d  mov     r8d, ebx
0x18001ba60  call    McTemplateU0dsqs_EventWriteTransfer
0x18001ba65  jmp     short loc_18001BABC
0x18001ba67  mov     rcx, [rsp+48h+hKey]; hKey
0x18001ba6c  lea     rax, [rsp+48h+cbData]
0x18001ba71  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18001ba76  xor     r9d, r9d; lpType
0x18001ba79  xor     r8d, r8d; lpReserved
0x18001ba7c  mov     [rsp+48h+phkResult], rdi; lpData
0x18001ba81  mov     rdx, rsi; lpValueName
0x18001ba84  call    cs:__imp_RegQueryValueExW
0x18001ba8a  mov     ebx, eax
0x18001ba8c  test    eax, eax
0x18001ba8e  jz      short loc_18001BABA
0x18001ba90  jle     short loc_18001BA9B
0x18001ba92  movzx   ebx, ax
0x18001ba95  or      ebx, 80070000h
0x18001ba9b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001baa2  jz      short loc_18001BABC
0x18001baa4  lea     rax, aCbr0lDwresult; "CBR(0L == dwResult)"
0x18001baab  mov     [rsp+48h+lpcbData], rax
0x18001bab0  mov     dword ptr [rsp+48h+phkResult], 0AFh
0x18001bab8  jmp     short loc_18001BA56
0x18001baba  xor     ebx, ebx
0x18001babc  mov     rcx, [rsp+48h+hKey]; hKey
0x18001bac1  test    rcx, rcx
0x18001bac4  jz      short loc_18001BACC
0x18001bac6  call    cs:__imp_RegCloseKey
0x18001bacc  mov     rsi, [rsp+48h+arg_10]
0x18001bad1  mov     eax, ebx
0x18001bad3  mov     rbx, [rsp+48h+arg_8]
0x18001bad8  add     rsp, 40h
0x18001badc  pop     rdi
0x18001badd  retn
```
