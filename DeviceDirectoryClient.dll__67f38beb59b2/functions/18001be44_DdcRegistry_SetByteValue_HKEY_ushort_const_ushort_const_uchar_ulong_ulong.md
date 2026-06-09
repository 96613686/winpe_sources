# DdcRegistry::SetByteValue(HKEY__ *,ushort const *,ushort const *,uchar *,ulong,ulong)

- ea: `0x18001be44`
- end: `0x18001bf4d`
- name: `?SetByteValue@DdcRegistry@@SAJPEAUHKEY__@@PEBG1PEAEKK@Z`
- size: `265`
- prototype: `static int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000df90`
- `0x1800253e0`

## callees

- `0x1800050b8`
- `0x18001be44`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bf35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bf35`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001bef3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001bef3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001be90`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001be90`

## string_xrefs

- `0x18001bec4`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcregistry.cpp`

## pseudocode

```c
__int64 __fastcall DdcRegistry::SetByteValue(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int8 *a4)
{
  LSTATUS v6; // eax
  int v7; // edx
  int v8; // ecx
  unsigned int v9; // ebx
  LSTATUS v10; // eax
  int v11; // edx
  int v12; // ecx
  HKEY hKey; // [rsp+50h] [rbp-18h] BYREF

  hKey = 0;
  v6 = RegCreateKeyExW(a1, a2, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
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
        96,
        "CBR(0L == dwResult)");
  }
  else
  {
    v10 = RegSetValueExW(hKey, a3, 0, 3u, a4, 8u);
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
          106,
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
0x18001be44  mov     r11, rsp
0x18001be47  mov     [r11+8], rbx
0x18001be4b  mov     [r11+10h], rsi
0x18001be4f  push    rdi
0x18001be50  sub     rsp, 60h
0x18001be54  mov     qword ptr [r11-28h], 0
0x18001be5c  lea     rax, [r11-18h]
0x18001be60  mov     [r11-30h], rax
0x18001be64  mov     rdi, r9
0x18001be67  mov     qword ptr [r11-38h], 0
0x18001be6f  mov     rsi, r8
0x18001be72  mov     [rsp+68h+samDesired], 0F003Fh; samDesired
0x18001be7a  xor     r9d, r9d; lpClass
0x18001be7d  xor     r8d, r8d; Reserved
0x18001be80  mov     [rsp+68h+dwOptions], 0; dwOptions
0x18001be88  mov     qword ptr [r11-18h], 0
0x18001be90  call    cs:__imp_RegCreateKeyExW
0x18001be96  mov     ebx, eax
0x18001be98  test    eax, eax
0x18001be9a  jz      short loc_18001BED5
0x18001be9c  jle     short loc_18001BEA7
0x18001be9e  movzx   ebx, ax
0x18001bea1  or      ebx, 80070000h
0x18001bea7  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001beae  jz      short loc_18001BF2B
0x18001beb0  lea     rax, aCbr0lDwresult; "CBR(0L == dwResult)"
0x18001beb7  mov     qword ptr [rsp+68h+samDesired], rax
0x18001bebc  mov     [rsp+68h+dwOptions], 60h ; '`'
0x18001bec4  lea     r9, aOnecoreuapShel_0; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001becb  mov     r8d, ebx
0x18001bece  call    McTemplateU0dsqs_EventWriteTransfer
0x18001bed3  jmp     short loc_18001BF2B
0x18001bed5  mov     rcx, [rsp+68h+hKey]; hKey
0x18001beda  mov     r9d, 3; dwType
0x18001bee0  mov     [rsp+68h+samDesired], 8; cbData
0x18001bee8  xor     r8d, r8d; Reserved
0x18001beeb  mov     rdx, rsi; lpValueName
0x18001beee  mov     qword ptr [rsp+68h+dwOptions], rdi; lpData
0x18001bef3  call    cs:__imp_RegSetValueExW
0x18001bef9  mov     ebx, eax
0x18001befb  test    eax, eax
0x18001befd  jz      short loc_18001BF29
0x18001beff  jle     short loc_18001BF0A
0x18001bf01  movzx   ebx, ax
0x18001bf04  or      ebx, 80070000h
0x18001bf0a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001bf11  jz      short loc_18001BF2B
0x18001bf13  lea     rax, aCbr0lDwresult; "CBR(0L == dwResult)"
0x18001bf1a  mov     qword ptr [rsp+68h+samDesired], rax
0x18001bf1f  mov     [rsp+68h+dwOptions], 6Ah ; 'j'
0x18001bf27  jmp     short loc_18001BEC4
0x18001bf29  xor     ebx, ebx
0x18001bf2b  mov     rcx, [rsp+68h+hKey]; hKey
0x18001bf30  test    rcx, rcx
0x18001bf33  jz      short loc_18001BF3B
0x18001bf35  call    cs:__imp_RegCloseKey
0x18001bf3b  mov     rsi, [rsp+68h+arg_8]
0x18001bf40  mov     eax, ebx
0x18001bf42  mov     rbx, [rsp+68h+arg_0]
0x18001bf47  add     rsp, 60h
0x18001bf4b  pop     rdi
0x18001bf4c  retn
```
