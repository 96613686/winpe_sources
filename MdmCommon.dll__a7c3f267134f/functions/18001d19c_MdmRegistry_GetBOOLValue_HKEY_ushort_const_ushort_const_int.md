# MdmRegistry::GetBOOLValue(HKEY__ *,ushort const *,ushort const *,int &)

- ea: `0x18001d19c`
- end: `0x18001d215`
- name: `?GetBOOLValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAH@Z`
- size: `121`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003d50`
- `0x1800133e8`

## callees

- `0x1800065c0`
- `0x18001d19c`
- `0x18001d3e4`

## string_xrefs

- `0x18001d1e4`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmregistry.cpp`

## pseudocode

```c
__int64 __fastcall MdmRegistry::GetBOOLValue(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, int *a4)
{
  int DWORDValue; // eax
  int v6; // edx
  int v7; // ecx
  unsigned int v8; // ebx
  unsigned int v10[6]; // [rsp+30h] [rbp-18h] BYREF

  v10[0] = 0;
  DWORDValue = MdmRegistry::GetDWORDValue(a1, a2, a3, (BYTE *)v10);
  v8 = DWORDValue;
  if ( DWORDValue )
  {
    if ( DWORDValue > 0 )
      v8 = (unsigned __int16)DWORDValue | 0x80070000;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v7,
        v6,
        v8,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmregistry.cpp",
        57,
        "CBR(dwResult == 0L)");
  }
  else
  {
    v8 = 0;
    *a4 = v10[0] != 0;
  }
  return v8;
}

```

## disassembly

```asm
0x18001d19c  mov     [rsp+arg_0], rbx
0x18001d1a1  push    rdi
0x18001d1a2  sub     rsp, 40h
0x18001d1a6  mov     rdi, r9
0x18001d1a9  mov     [rsp+48h+var_18], 0
0x18001d1b1  lea     r9, [rsp+48h+var_18]; unsigned int *
0x18001d1b6  call    ?GetDWORDValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAK@Z; MdmRegistry::GetDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong &)
0x18001d1bb  mov     ebx, eax
0x18001d1bd  test    eax, eax
0x18001d1bf  jz      short loc_18001D1FA
0x18001d1c1  jle     short loc_18001D1CC
0x18001d1c3  movzx   ebx, ax
0x18001d1c6  or      ebx, 80070000h
0x18001d1cc  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001d1d3  jz      short loc_18001D207
0x18001d1d5  lea     rax, aCbrDwresult0l; "CBR(dwResult == 0L)"
0x18001d1dc  mov     r8d, ebx
0x18001d1df  mov     [rsp+48h+var_20], rax
0x18001d1e4  lea     r9, aOnecoreuapShel_0; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001d1eb  mov     [rsp+48h+var_28], 239h
0x18001d1f3  call    McTemplateU0dsqs_EventWriteTransfer
0x18001d1f8  jmp     short loc_18001D207
0x18001d1fa  xor     ecx, ecx
0x18001d1fc  xor     ebx, ebx
0x18001d1fe  cmp     [rsp+48h+var_18], ecx
0x18001d202  setnz   cl
0x18001d205  mov     [rdi], ecx
0x18001d207  mov     eax, ebx
0x18001d209  mov     rbx, [rsp+48h+arg_0]
0x18001d20e  add     rsp, 40h
0x18001d212  pop     rdi
0x18001d213  retn
```
