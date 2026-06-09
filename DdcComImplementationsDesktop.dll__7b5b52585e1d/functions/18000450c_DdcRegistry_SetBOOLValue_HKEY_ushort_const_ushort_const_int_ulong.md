# DdcRegistry::SetBOOLValue(HKEY__ *,ushort const *,ushort const *,int,ulong)

- ea: `0x18000450c`
- end: `0x180004566`
- name: `?SetBOOLValue@DdcRegistry@@SAJPEAUHKEY__@@PEBG1HK@Z`
- size: `90`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002c50`

## callees

- `0x1800026ac`
- `0x18000450c`
- `0x18000456c`

## string_xrefs

- `0x180004546`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcregistry.cpp`

## pseudocode

```c
__int64 __fastcall DdcRegistry::SetBOOLValue(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  int v3; // eax
  int v4; // edx
  int v5; // ecx
  unsigned int v6; // ebx
  unsigned int v8; // [rsp+20h] [rbp-18h]

  v3 = DdcRegistry::SetDWORDValue(a1, a2, a3, 1u, v8);
  v6 = v3;
  if ( v3 )
  {
    if ( v3 > 0 )
      v6 = (unsigned __int16)v3 | 0x80070000;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v5,
        v4,
        v6,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistry.cpp",
        68,
        (__int64)"CBR(dwResult == 0L)");
  }
  else
  {
    return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x18000450c  push    rbx
0x18000450e  sub     rsp, 30h
0x180004512  mov     r9d, 1; unsigned int
0x180004518  call    ?SetDWORDValue@DdcRegistry@@SAJPEAUHKEY__@@PEBG1KK@Z; DdcRegistry::SetDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong,ulong)
0x18000451d  mov     ebx, eax
0x18000451f  test    eax, eax
0x180004521  jz      short loc_18000455C
0x180004523  jle     short loc_18000452E
0x180004525  movzx   ebx, ax
0x180004528  or      ebx, 80070000h
0x18000452e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180004535  jz      short loc_18000455E
0x180004537  lea     rax, aCbrDwresult0l; "CBR(dwResult == 0L)"
0x18000453e  mov     r8d, ebx
0x180004541  mov     [rsp+38h+var_10], rax
0x180004546  lea     r9, aOnecoreuapShel_0; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18000454d  mov     [rsp+38h+var_18], 244h
0x180004555  call    McTemplateU0dsqs_EventWriteTransfer
0x18000455a  jmp     short loc_18000455E
0x18000455c  xor     ebx, ebx
0x18000455e  mov     eax, ebx
0x180004560  add     rsp, 30h
0x180004564  pop     rbx
0x180004565  retn
```
