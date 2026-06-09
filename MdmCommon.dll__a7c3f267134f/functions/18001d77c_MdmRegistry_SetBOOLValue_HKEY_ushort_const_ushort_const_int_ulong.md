# MdmRegistry::SetBOOLValue(HKEY__ *,ushort const *,ushort const *,int,ulong)

- ea: `0x18001d77c`
- end: `0x18001d7dd`
- name: `?SetBOOLValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1HK@Z`
- size: `97`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800140a4`
- `0x180014344`

## callees

- `0x1800065c0`
- `0x18001d77c`
- `0x18001d7e4`

## string_xrefs

- `0x18001d7bc`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmregistry.cpp`

## pseudocode

```c
__int64 __fastcall MdmRegistry::SetBOOLValue(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, int a4)
{
  int v4; // eax
  int v5; // edx
  int v6; // ecx
  unsigned int v7; // ebx

  v4 = MdmRegistry::SetDWORDValue(a1, a2, a3, a4 != 0);
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
0x18001d77c  push    rbx
0x18001d77e  sub     rsp, 30h
0x18001d782  mov     eax, r9d
0x18001d785  xor     r9d, r9d
0x18001d788  test    eax, eax
0x18001d78a  setnz   r9b; unsigned int
0x18001d78e  call    ?SetDWORDValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1KK@Z; MdmRegistry::SetDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong,ulong)
0x18001d793  mov     ebx, eax
0x18001d795  test    eax, eax
0x18001d797  jz      short loc_18001D7D2
0x18001d799  jle     short loc_18001D7A4
0x18001d79b  movzx   ebx, ax
0x18001d79e  or      ebx, 80070000h
0x18001d7a4  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001d7ab  jz      short loc_18001D7D4
0x18001d7ad  lea     rax, aCbrDwresult0l; "CBR(dwResult == 0L)"
0x18001d7b4  mov     r8d, ebx
0x18001d7b7  mov     [rsp+38h+var_10], rax
0x18001d7bc  lea     r9, aOnecoreuapShel_0; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001d7c3  mov     [rsp+38h+var_18], 209h
0x18001d7cb  call    McTemplateU0dsqs_EventWriteTransfer
0x18001d7d0  jmp     short loc_18001D7D4
0x18001d7d2  xor     ebx, ebx
0x18001d7d4  mov     eax, ebx
0x18001d7d6  add     rsp, 30h
0x18001d7da  pop     rbx
0x18001d7db  retn
```
