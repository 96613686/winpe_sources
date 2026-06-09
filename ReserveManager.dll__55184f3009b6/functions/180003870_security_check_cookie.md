# __security_check_cookie

- ea: `0x180003870`
- end: `0x18000388e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `177`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x18000119c`
- `0x18000128c`
- `0x1800013b4`
- `0x180001470`
- `0x180001858`
- `0x1800018ec`
- `0x180001ba0`
- `0x180001eb4`
- `0x1800021b0`
- `0x180002550`
- `0x180002864`
- `0x180002910`
- `0x1800029d8`
- `0x180002a68`
- `0x180002b64`
- `0x180002c44`
- `0x180002ee8`
- `0x1800048a8`
- `0x180004ed8`
- `0x18000518c`
- `0x1800061c8`
- `0x180006598`
- `0x180006990`
- `0x180006c74`
- `0x180006ee4`
- `0x1800075f4`
- `0x180007a34`
- `0x180007e08`
- `0x180008544`
- `0x1800085e0`
- `0x180008a2c`
- `0x180008d40`
- `0x180008e4c`
- `0x1800091e4`
- `0x180009238`
- `0x180009290`
- `0x180009350`
- `0x18000990c`
- `0x18000ac20`
- `0x18000b0ac`
- `0x18000b344`
- `0x18000bd80`
- `0x18000c1b0`
- `0x18000c2d8`
- `0x18000ce14`
- `0x18000cf80`
- `0x18000d160`
- `0x18000d96c`
- `0x18000e854`

## callees

- `0x180003870`
- `0x180003e70`

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
0x180003870  cmp     rcx, cs:__security_cookie
0x180003877  jnz     short ReportFailure
0x180003879  rol     rcx, 10h
0x18000387d  test    cx, 0FFFFh
0x180003882  jnz     short RestoreRcx
0x180003884  retn
0x180003885  ror     rcx, 10h; StackCookie
0x180003889  jmp     __report_gsfailure
```
