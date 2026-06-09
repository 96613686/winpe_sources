# __security_check_cookie

- ea: `0x18000c560`
- end: `0x18000c57e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `30`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800025fc`
- `0x180002898`
- `0x18000321c`
- `0x1800035c0`
- `0x180003990`
- `0x1800044b4`
- `0x18000482c`
- `0x1800055f8`
- `0x180005878`
- `0x180005984`
- `0x18000632c`
- `0x1800073a8`
- `0x180007db8`
- `0x180008050`
- `0x180008370`
- `0x1800085e0`
- `0x180008780`
- `0x180008910`
- `0x180008c90`
- `0x180009090`
- `0x1800098ac`
- `0x18000a378`
- `0x18000a550`
- `0x18000a680`
- `0x18000aa30`
- `0x18000b67c`
- `0x18000bd58`
- `0x18000c13c`
- `0x18000c4d4`

## callees

- `0x1800017e0`
- `0x18000c560`

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
0x18000c560  cmp     rcx, cs:__security_cookie
0x18000c567  jnz     short ReportFailure
0x18000c569  rol     rcx, 10h
0x18000c56d  test    cx, 0FFFFh
0x18000c572  jnz     short RestoreRcx
0x18000c574  retn
0x18000c575  ror     rcx, 10h
0x18000c579  jmp     __report_gsfailure
```
