# __security_check_cookie

- ea: `0x18000c5b0`
- end: `0x18000c5ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800027cc`
- `0x1800049d0`
- `0x180005e60`
- `0x180006830`
- `0x180007d60`
- `0x180008040`
- `0x180008990`
- `0x1800090a0`
- `0x180009310`
- `0x180009a50`
- `0x180009fb0`

## callees

- `0x180002250`
- `0x18000c5b0`

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
0x18000c5b0  cmp     rcx, cs:__security_cookie
0x18000c5b7  jnz     short ReportFailure
0x18000c5b9  rol     rcx, 10h
0x18000c5bd  test    cx, 0FFFFh
0x18000c5c2  jnz     short RestoreRcx
0x18000c5c4  retn
0x18000c5c5  ror     rcx, 10h
0x18000c5c9  jmp     __report_gsfailure
```
