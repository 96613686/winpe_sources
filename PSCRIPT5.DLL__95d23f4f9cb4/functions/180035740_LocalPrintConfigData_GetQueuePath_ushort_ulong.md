# LocalPrintConfigData::GetQueuePath(ushort *,ulong)

- ea: `0x180035740`
- end: `0x180035790`
- name: `?GetQueuePath@LocalPrintConfigData@@UEAAJPEAGK@Z`
- size: `80`
- prototype: `int(LocalPrintConfigData *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180035740`

## import_xrefs

- `WINSPOOL!GetPrinterDataW` at `0x180035779`
- `WINSPOOL!GetPrinterDataW` at `0x180035779`

## string_xrefs

- `0x18003576e`: `PrintQueueV4DriverDirectory`

## pseudocode

```c
int __fastcall LocalPrintConfigData::GetQueuePath(LocalPrintConfigData *this, BYTE *a2, int a3)
{
  void *v3; // rcx
  int result; // eax
  DWORD pType; // [rsp+40h] [rbp+8h] BYREF
  DWORD pcbNeeded; // [rsp+50h] [rbp+18h] BYREF

  v3 = (void *)*((_QWORD *)this + 14);
  pcbNeeded = 0;
  pType = 0;
  result = GetPrinterDataW(v3, (LPWSTR)L"PrintQueueV4DriverDirectory", &pType, a2, 2 * a3, &pcbNeeded);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180035740  sub     rsp, 38h
0x180035744  mov     rcx, [rcx+70h]; hPrinter
0x180035748  lea     eax, [r8+r8]
0x18003574c  lea     r8, [rsp+38h+arg_10]
0x180035751  mov     [rsp+38h+arg_10], 0
0x180035759  mov     [rsp+38h+pcbNeeded], r8; pcbNeeded
0x18003575e  mov     r9, rdx; pData
0x180035761  lea     r8, [rsp+38h+pType]; pType
0x180035766  mov     [rsp+38h+pType], 0
0x18003576e  lea     rdx, aPrintqueuev4dr; "PrintQueueV4DriverDirectory"
0x180035775  mov     [rsp+38h+nSize], eax; nSize
0x180035779  call    cs:__imp_GetPrinterDataW
0x18003577f  test    eax, eax
0x180035781  jle     short loc_18003578B
0x180035783  movzx   eax, ax
0x180035786  or      eax, 80070000h
0x18003578b  add     rsp, 38h
0x18003578f  retn
```
