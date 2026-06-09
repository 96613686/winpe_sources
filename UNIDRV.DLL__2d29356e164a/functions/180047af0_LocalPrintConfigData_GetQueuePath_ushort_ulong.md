# LocalPrintConfigData::GetQueuePath(ushort *,ulong)

- ea: `0x180047af0`
- end: `0x180047b40`
- name: `?GetQueuePath@LocalPrintConfigData@@UEAAJPEAGK@Z`
- size: `80`
- prototype: `int(LocalPrintConfigData *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180047af0`

## import_xrefs

- `WINSPOOL!GetPrinterDataW` at `0x180047b29`
- `WINSPOOL!GetPrinterDataW` at `0x180047b29`

## string_xrefs

- `0x180047b1e`: `PrintQueueV4DriverDirectory`

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
0x180047af0  sub     rsp, 38h
0x180047af4  mov     rcx, [rcx+70h]; hPrinter
0x180047af8  lea     eax, [r8+r8]
0x180047afc  lea     r8, [rsp+38h+arg_10]
0x180047b01  mov     [rsp+38h+arg_10], 0
0x180047b09  mov     [rsp+38h+pcbNeeded], r8; pcbNeeded
0x180047b0e  mov     r9, rdx; pData
0x180047b11  lea     r8, [rsp+38h+pType]; pType
0x180047b16  mov     [rsp+38h+pType], 0
0x180047b1e  lea     rdx, aPrintqueuev4dr; "PrintQueueV4DriverDirectory"
0x180047b25  mov     [rsp+38h+nSize], eax; nSize
0x180047b29  call    cs:__imp_GetPrinterDataW
0x180047b2f  test    eax, eax
0x180047b31  jle     short loc_180047B3B
0x180047b33  movzx   eax, ax
0x180047b36  or      eax, 80070000h
0x180047b3b  add     rsp, 38h
0x180047b3f  retn
```
