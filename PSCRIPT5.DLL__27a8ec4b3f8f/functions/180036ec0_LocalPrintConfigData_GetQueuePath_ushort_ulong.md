# LocalPrintConfigData::GetQueuePath(ushort *,ulong)

- ea: `0x180036ec0`
- end: `0x180036f17`
- name: `?GetQueuePath@LocalPrintConfigData@@UEAAJPEAGK@Z`
- size: `87`
- prototype: `int __fastcall(LocalPrintConfigData *this, BYTE *, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180036ec0`

## import_xrefs

- `WINSPOOL!GetPrinterDataW` at `0x180036ef9`
- `WINSPOOL!GetPrinterDataW` at `0x180036ef9`

## string_xrefs

- `0x180036eee`: `PrintQueueV4DriverDirectory`

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
0x180036ec0  sub     rsp, 38h
0x180036ec4  mov     rcx, [rcx+70h]; hPrinter
0x180036ec8  lea     eax, [r8+r8]
0x180036ecc  lea     r8, [rsp+38h+arg_10]
0x180036ed1  mov     [rsp+38h+arg_10], 0
0x180036ed9  mov     [rsp+38h+pcbNeeded], r8; pcbNeeded
0x180036ede  mov     r9, rdx; pData
0x180036ee1  lea     r8, [rsp+38h+pType]; pType
0x180036ee6  mov     [rsp+38h+pType], 0
0x180036eee  lea     rdx, aPrintqueuev4dr; "PrintQueueV4DriverDirectory"
0x180036ef5  mov     [rsp+38h+nSize], eax; nSize
0x180036ef9  call    cs:__imp_GetPrinterDataW
0x180036f00  nop     dword ptr [rax+rax+00h]
0x180036f05  test    eax, eax
0x180036f07  jle     short loc_180036F11
0x180036f09  movzx   eax, ax
0x180036f0c  or      eax, 80070000h
0x180036f11  add     rsp, 38h
0x180036f15  retn
```
