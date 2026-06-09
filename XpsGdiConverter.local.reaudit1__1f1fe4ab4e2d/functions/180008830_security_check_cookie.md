# __security_check_cookie

- ea: `0x180008830`
- end: `0x18000884e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `120`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001128`
- `0x1800013dc`
- `0x1800016d4`
- `0x180007f70`
- `0x1800081f0`
- `0x180008cd0`
- `0x18000a28c`
- `0x18000a528`
- `0x18000ac28`
- `0x18000adbc`
- `0x18000b174`
- `0x18000b528`
- `0x18000ca20`
- `0x18000cfa0`
- `0x18000ecc0`
- `0x18000eee0`
- `0x18000f670`
- `0x18000fb70`
- `0x18000fd0c`
- `0x180010670`
- `0x1800109e0`
- `0x1800123bc`
- `0x180013db4`
- `0x1800140f0`
- `0x180014568`
- `0x180016b74`
- `0x1800175dc`
- `0x1800185f0`
- `0x180018a70`
- `0x180018df4`
- `0x180018f78`
- `0x18001af74`
- `0x18001d1ec`
- `0x18001de6c`
- `0x18001e36c`
- `0x18001ec70`
- `0x18001f444`
- `0x18002028c`
- `0x180020988`
- `0x180020c14`
- `0x1800211f4`
- `0x1800230e0`
- `0x180023240`
- `0x180023598`
- `0x180023c50`
- `0x180025124`
- `0x1800255bc`
- `0x1800266dc`
- `0x180027054`

## callees

- `0x180008830`
- `0x180009180`

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
0x180008830  cmp     rcx, cs:__security_cookie
0x180008837  jnz     short ReportFailure
0x180008839  rol     rcx, 10h
0x18000883d  test    cx, 0FFFFh
0x180008842  jnz     short RestoreRcx
0x180008844  retn
0x180008845  ror     rcx, 10h; StackCookie
0x180008849  jmp     __report_gsfailure
```
