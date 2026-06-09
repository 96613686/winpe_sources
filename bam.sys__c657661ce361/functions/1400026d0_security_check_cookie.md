# __security_check_cookie

- ea: `0x1400026d0`
- end: `0x1400026ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `47`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x140001670`
- `0x140001730`
- `0x140001cd4`
- `0x1400020d8`
- `0x140002338`
- `0x14000259c`
- `0x14000b410`
- `0x14000b8c0`
- `0x14000b9ac`
- `0x14000baac`
- `0x14000bea0`
- `0x14000c18c`
- `0x14000c5b0`
- `0x14000c6f0`
- `0x14000c9f4`
- `0x14000cc54`
- `0x14000d040`
- `0x14000dea8`
- `0x14000ea54`
- `0x14000f1a0`
- `0x14000f460`
- `0x140010cb0`
- `0x140010e20`
- `0x140011160`
- `0x140011660`
- `0x140011a98`
- `0x140011c68`
- `0x14001202c`
- `0x140012450`
- `0x140012530`
- `0x140012c84`
- `0x140012eec`
- `0x1400132ac`
- `0x140013740`
- `0x140013c7c`
- `0x140013d40`
- `0x140014180`
- `0x140014648`
- `0x14001474c`
- `0x140014d20`
- `0x140014f90`
- `0x140015100`
- `0x1400153a0`
- `0x140015608`
- `0x140015878`
- `0x1400162ac`

## callees

- `0x140001660`
- `0x1400026d0`

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
0x1400026d0  cmp     rcx, cs:__security_cookie
0x1400026d7  jnz     short ReportFailure
0x1400026d9  rol     rcx, 10h
0x1400026dd  test    cx, 0FFFFh
0x1400026e2  jnz     short RestoreRcx
0x1400026e4  retn
0x1400026e5  ror     rcx, 10h; StackCookie
0x1400026e9  jmp     __report_gsfailure
```
