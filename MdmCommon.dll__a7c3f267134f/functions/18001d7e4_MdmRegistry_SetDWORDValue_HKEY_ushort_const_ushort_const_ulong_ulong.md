# MdmRegistry::SetDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong,ulong)

- ea: `0x18001d7e4`
- end: `0x18001d901`
- name: `?SetDWORDValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1KK@Z`
- size: `285`
- prototype: `static int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800140a4`
- `0x18001d77c`

## callees

- `0x1800065c0`
- `0x18001d7e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d8e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d8e7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d89f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d89f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d82d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d82d`

## string_xrefs

- `0x18001d86b`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmregistry.cpp`

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
0x18001d7e4  mov     r11, rsp
0x18001d7e7  mov     [r11+8], rbx
0x18001d7eb  mov     [r11+20h], r9d
0x18001d7ef  push    rdi
0x18001d7f0  sub     rsp, 60h
0x18001d7f4  mov     qword ptr [r11-28h], 0
0x18001d7fc  lea     rax, [r11-18h]
0x18001d800  mov     [r11-30h], rax
0x18001d804  mov     rdi, r8
0x18001d807  mov     qword ptr [r11-38h], 0
0x18001d80f  xor     r9d, r9d; lpClass
0x18001d812  mov     [rsp+68h+samDesired], 20006h; samDesired
0x18001d81a  xor     r8d, r8d; Reserved
0x18001d81d  mov     [rsp+68h+dwOptions], 0; dwOptions
0x18001d825  mov     qword ptr [r11-18h], 0
0x18001d82d  call    cs:__imp_RegCreateKeyExW
0x18001d834  nop     dword ptr [rax+rax+00h]
0x18001d839  mov     ebx, eax
0x18001d83b  test    eax, eax
0x18001d83d  jz      short loc_18001D87C
0x18001d83f  jle     short loc_18001D84A
0x18001d841  movzx   ebx, ax
0x18001d844  or      ebx, 80070000h
0x18001d84a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001d851  jz      loc_18001D8DD
0x18001d857  lea     rax, aCbr0lDwresult; "CBR(0L == dwResult)"
0x18001d85e  mov     qword ptr [rsp+68h+samDesired], rax
0x18001d863  mov     [rsp+68h+dwOptions], 10Dh
0x18001d86b  lea     r9, aOnecoreuapShel_0; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001d872  mov     r8d, ebx
0x18001d875  call    McTemplateU0dsqs_EventWriteTransfer
0x18001d87a  jmp     short loc_18001D8DD
0x18001d87c  mov     rcx, [rsp+68h+hKey]; hKey
0x18001d881  lea     rax, [rsp+68h+Data]
0x18001d889  mov     r9d, 4; dwType
0x18001d88f  xor     r8d, r8d; Reserved
0x18001d892  mov     [rsp+68h+samDesired], r9d; cbData
0x18001d897  mov     rdx, rdi; lpValueName
0x18001d89a  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x18001d89f  call    cs:__imp_RegSetValueExW
0x18001d8a6  nop     dword ptr [rax+rax+00h]
0x18001d8ab  mov     ebx, eax
0x18001d8ad  test    eax, eax
0x18001d8af  jz      short loc_18001D8DB
0x18001d8b1  jle     short loc_18001D8BC
0x18001d8b3  movzx   ebx, ax
0x18001d8b6  or      ebx, 80070000h
0x18001d8bc  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001d8c3  jz      short loc_18001D8DD
0x18001d8c5  lea     rax, aCbr0lDwresult; "CBR(0L == dwResult)"
0x18001d8cc  mov     qword ptr [rsp+68h+samDesired], rax
0x18001d8d1  mov     [rsp+68h+dwOptions], 116h
0x18001d8d9  jmp     short loc_18001D86B
0x18001d8db  xor     ebx, ebx
0x18001d8dd  mov     rcx, [rsp+68h+hKey]; hKey
0x18001d8e2  test    rcx, rcx
0x18001d8e5  jz      short loc_18001D8F3
0x18001d8e7  call    cs:__imp_RegCloseKey
0x18001d8ee  nop     dword ptr [rax+rax+00h]
0x18001d8f3  mov     eax, ebx
0x18001d8f5  mov     rbx, [rsp+68h+arg_0]
0x18001d8fa  add     rsp, 60h
0x18001d8fe  pop     rdi
0x18001d8ff  retn
```
