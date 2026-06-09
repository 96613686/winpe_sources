# MdmRegistry::SetBOOLValue(HKEY__ *,ushort const *,ushort const *,int,ulong)

- ea: `0x18001d0d0`
- end: `0x18001d130`
- name: `?SetBOOLValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1HK@Z`
- size: `96`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013ca4`
- `0x180013f40`

## callees

- `0x180006548`
- `0x18001d0d0`
- `0x18001d138`

## string_xrefs

- `0x18001d110`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmregistry.cpp`

## pseudocode

```c
__int64 __fastcall MdmRegistry::SetBOOLValue(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, int a4)
{
  int v4; // eax
  int v5; // edx
  int v6; // ecx
  unsigned int v7; // ebx
  unsigned int v9; // [rsp+20h] [rbp-18h]

  v4 = MdmRegistry::SetDWORDValue(a1, a2, a3, a4 != 0, v9);
  v7 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      v7 = (unsigned __int16)v4 | 0x80070000;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v6,
        v5,
        v7,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmregistry.cpp",
        9,
        "CBR(dwResult == 0L)");
  }
  else
  {
    return 0;
  }
  return v7;
}

```

## disassembly

```asm
0x18001d0d0  push    rbx
0x18001d0d2  sub     rsp, 30h
0x18001d0d6  mov     eax, r9d
0x18001d0d9  xor     r9d, r9d
0x18001d0dc  test    eax, eax
0x18001d0de  setnz   r9b; unsigned int
0x18001d0e2  call    ?SetDWORDValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1KK@Z; MdmRegistry::SetDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong,ulong)
0x18001d0e7  mov     ebx, eax
0x18001d0e9  test    eax, eax
0x18001d0eb  jz      short loc_18001D126
0x18001d0ed  jle     short loc_18001D0F8
0x18001d0ef  movzx   ebx, ax
0x18001d0f2  or      ebx, 80070000h
0x18001d0f8  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001d0ff  jz      short loc_18001D128
0x18001d101  lea     rax, aCbrDwresult0l; "CBR(dwResult == 0L)"
0x18001d108  mov     r8d, ebx
0x18001d10b  mov     [rsp+38h+var_10], rax
0x18001d110  lea     r9, aOnecoreuapShel_0; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001d117  mov     [rsp+38h+var_18], 209h
0x18001d11f  call    McTemplateU0dsqs_EventWriteTransfer
0x18001d124  jmp     short loc_18001D128
0x18001d126  xor     ebx, ebx
0x18001d128  mov     eax, ebx
0x18001d12a  add     rsp, 30h
0x18001d12e  pop     rbx
0x18001d12f  retn
```
