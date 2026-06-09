# __security_check_cookie

- ea: `0x18001d6c0`
- end: `0x18001d6de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `62`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800027d4`
- `0x180002c80`
- `0x180002ed0`
- `0x180003050`
- `0x1800032a0`
- `0x180003bb8`
- `0x180003dbc`
- `0x18000474c`
- `0x1800049c0`
- `0x180005a90`
- `0x180005e40`
- `0x180006240`
- `0x180006660`
- `0x180006f60`
- `0x180007300`
- `0x1800079c4`
- `0x180008a50`
- `0x18000989c`
- `0x180009a44`
- `0x180009d90`
- `0x18000b2b0`
- `0x18000b568`
- `0x18000c004`
- `0x18000c11c`
- `0x18000d638`
- `0x18000d83c`
- `0x18000e528`
- `0x18000e7e0`
- `0x180010104`
- `0x1800103bc`
- `0x1800107f0`
- `0x1800112e4`
- `0x180011b9c`
- `0x180012084`
- `0x180012238`
- `0x18001297c`
- `0x180012b24`
- `0x180012d2c`
- `0x180012e6c`
- `0x1800148a0`
- `0x180014fa4`
- `0x1800151fc`
- `0x180015424`
- `0x180015564`
- `0x180015664`
- `0x180015b1c`
- `0x180015d04`
- `0x1800160d0`
- `0x1800164f8`
- `0x180016630`

## callees

- `0x180001630`
- `0x18001d6c0`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
ReportFailure:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto ReportFailure;
  }
}

```

## disassembly

```asm
0x18001d6c0  cmp     rcx, cs:__security_cookie
0x18001d6c7  jnz     short ReportFailure
0x18001d6c9  rol     rcx, 10h
0x18001d6cd  test    cx, 0FFFFh
0x18001d6d2  jnz     short RestoreRcx
0x18001d6d4  retn
0x18001d6d5  ror     rcx, 10h
0x18001d6d9  jmp     __report_gsfailure
```
