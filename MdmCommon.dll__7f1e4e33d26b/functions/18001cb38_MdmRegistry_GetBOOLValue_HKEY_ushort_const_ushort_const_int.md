# MdmRegistry::GetBOOLValue(HKEY__ *,ushort const *,ushort const *,int &)

- ea: `0x18001cb38`
- end: `0x18001cbb0`
- name: `?GetBOOLValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAH@Z`
- size: `120`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003d40`
- `0x180013004`

## callees

- `0x180006548`
- `0x18001cb38`
- `0x18001cd64`

## string_xrefs

- `0x18001cb80`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmregistry.cpp`

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
  DWORDValue = MdmRegistry::GetDWORDValue(a1, a2, a3, v10);
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
0x18001cb38  mov     [rsp+arg_0], rbx
0x18001cb3d  push    rdi
0x18001cb3e  sub     rsp, 40h
0x18001cb42  mov     rdi, r9
0x18001cb45  mov     [rsp+48h+var_18], 0
0x18001cb4d  lea     r9, [rsp+48h+var_18]; unsigned int *
0x18001cb52  call    ?GetDWORDValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAK@Z; MdmRegistry::GetDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong &)
0x18001cb57  mov     ebx, eax
0x18001cb59  test    eax, eax
0x18001cb5b  jz      short loc_18001CB96
0x18001cb5d  jle     short loc_18001CB68
0x18001cb5f  movzx   ebx, ax
0x18001cb62  or      ebx, 80070000h
0x18001cb68  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001cb6f  jz      short loc_18001CBA3
0x18001cb71  lea     rax, aCbrDwresult0l; "CBR(dwResult == 0L)"
0x18001cb78  mov     r8d, ebx
0x18001cb7b  mov     [rsp+48h+var_20], rax
0x18001cb80  lea     r9, aOnecoreuapShel_0; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001cb87  mov     [rsp+48h+var_28], 239h
0x18001cb8f  call    McTemplateU0dsqs_EventWriteTransfer
0x18001cb94  jmp     short loc_18001CBA3
0x18001cb96  xor     ecx, ecx
0x18001cb98  xor     ebx, ebx
0x18001cb9a  cmp     [rsp+48h+var_18], ecx
0x18001cb9e  setnz   cl
0x18001cba1  mov     [rdi], ecx
0x18001cba3  mov     eax, ebx
0x18001cba5  mov     rbx, [rsp+48h+arg_0]
0x18001cbaa  add     rsp, 40h
0x18001cbae  pop     rdi
0x18001cbaf  retn
```
