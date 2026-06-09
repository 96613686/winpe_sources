# MdmRegistry::SetDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong,ulong)

- ea: `0x18001d138`
- end: `0x18001d242`
- name: `?SetDWORDValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1KK@Z`
- size: `266`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013ca4`
- `0x18001d0d0`

## callees

- `0x180006548`
- `0x18001d138`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d22f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d22f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d1ed`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d1ed`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d181`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d181`

## string_xrefs

- `0x18001d1b9`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmregistry.cpp`

## pseudocode

```c
__int64 __fastcall MdmRegistry::SetDWORDValue(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, int a4)
{
  LSTATUS v5; // eax
  int v6; // edx
  int v7; // ecx
  unsigned int v8; // ebx
  LSTATUS v9; // eax
  int v10; // edx
  int v11; // ecx
  HKEY hKey; // [rsp+50h] [rbp-18h] BYREF
  int Data; // [rsp+88h] [rbp+20h] BYREF

  Data = a4;
  hKey = 0;
  v5 = RegCreateKeyExW(a1, a2, 0, 0, 0, 0x20006u, 0, &hKey, 0);
  v8 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v8 = (unsigned __int16)v5 | 0x80070000;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v7,
        v6,
        v8,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmregistry.cpp",
        13,
        "CBR(0L == dwResult)");
  }
  else
  {
    v9 = RegSetValueExW(hKey, a3, 0, 4u, (const BYTE *)&Data, 4u);
    v8 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v8 = (unsigned __int16)v9 | 0x80070000;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v11,
          v10,
          v8,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmregistry.cpp",
          22,
          "CBR(0L == dwResult)");
    }
    else
    {
      v8 = 0;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x18001d138  mov     r11, rsp
0x18001d13b  mov     [r11+8], rbx
0x18001d13f  mov     [r11+20h], r9d
0x18001d143  push    rdi
0x18001d144  sub     rsp, 60h
0x18001d148  mov     qword ptr [r11-28h], 0
0x18001d150  lea     rax, [r11-18h]
0x18001d154  mov     [r11-30h], rax
0x18001d158  mov     rdi, r8
0x18001d15b  mov     qword ptr [r11-38h], 0
0x18001d163  xor     r9d, r9d; lpClass
0x18001d166  mov     [rsp+68h+samDesired], 20006h; samDesired
0x18001d16e  xor     r8d, r8d; Reserved
0x18001d171  mov     [rsp+68h+dwOptions], 0; dwOptions
0x18001d179  mov     qword ptr [r11-18h], 0
0x18001d181  call    cs:__imp_RegCreateKeyExW
0x18001d187  mov     ebx, eax
0x18001d189  test    eax, eax
0x18001d18b  jz      short loc_18001D1CA
0x18001d18d  jle     short loc_18001D198
0x18001d18f  movzx   ebx, ax
0x18001d192  or      ebx, 80070000h
0x18001d198  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001d19f  jz      loc_18001D225
0x18001d1a5  lea     rax, aCbr0lDwresult; "CBR(0L == dwResult)"
0x18001d1ac  mov     qword ptr [rsp+68h+samDesired], rax
0x18001d1b1  mov     [rsp+68h+dwOptions], 10Dh
0x18001d1b9  lea     r9, aOnecoreuapShel_0; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001d1c0  mov     r8d, ebx
0x18001d1c3  call    McTemplateU0dsqs_EventWriteTransfer
0x18001d1c8  jmp     short loc_18001D225
0x18001d1ca  mov     rcx, [rsp+68h+hKey]; hKey
0x18001d1cf  lea     rax, [rsp+68h+Data]
0x18001d1d7  mov     r9d, 4; dwType
0x18001d1dd  xor     r8d, r8d; Reserved
0x18001d1e0  mov     [rsp+68h+samDesired], r9d; cbData
0x18001d1e5  mov     rdx, rdi; lpValueName
0x18001d1e8  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x18001d1ed  call    cs:__imp_RegSetValueExW
0x18001d1f3  mov     ebx, eax
0x18001d1f5  test    eax, eax
0x18001d1f7  jz      short loc_18001D223
0x18001d1f9  jle     short loc_18001D204
0x18001d1fb  movzx   ebx, ax
0x18001d1fe  or      ebx, 80070000h
0x18001d204  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001d20b  jz      short loc_18001D225
0x18001d20d  lea     rax, aCbr0lDwresult; "CBR(0L == dwResult)"
0x18001d214  mov     qword ptr [rsp+68h+samDesired], rax
0x18001d219  mov     [rsp+68h+dwOptions], 116h
0x18001d221  jmp     short loc_18001D1B9
0x18001d223  xor     ebx, ebx
0x18001d225  mov     rcx, [rsp+68h+hKey]; hKey
0x18001d22a  test    rcx, rcx
0x18001d22d  jz      short loc_18001D235
0x18001d22f  call    cs:__imp_RegCloseKey
0x18001d235  mov     eax, ebx
0x18001d237  mov     rbx, [rsp+68h+arg_0]
0x18001d23c  add     rsp, 60h
0x18001d240  pop     rdi
0x18001d241  retn
```
