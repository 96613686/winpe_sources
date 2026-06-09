# __security_check_cookie

- ea: `0x18002e060`
- end: `0x18002e07e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `47`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800030c4`
- `0x180003af4`
- `0x1800050c4`
- `0x180008190`
- `0x180008344`
- `0x1800085ac`
- `0x18000c9e8`
- `0x18000d014`
- `0x18000e5ec`
- `0x18000ec24`
- `0x18000f04c`
- `0x18000f918`
- `0x1800102a4`
- `0x1800103a0`
- `0x180010c1c`
- `0x180011c54`
- `0x1800153fc`
- `0x180016564`
- `0x18001687c`
- `0x180018c24`
- `0x1800190dc`
- `0x1800196ec`
- `0x180019808`
- `0x18001a03c`
- `0x18001a394`
- `0x18001bccc`
- `0x18001c36c`
- `0x18001ca70`
- `0x18001d3b4`
- `0x18001d924`
- `0x18001e10c`
- `0x18001edac`
- `0x18001f5c4`
- `0x18002010c`
- `0x180020608`
- `0x180021160`
- `0x180022ad8`
- `0x180023bbc`
- `0x1800272f0`
- `0x180029350`
- `0x180029640`
- `0x180029830`
- `0x180029d10`
- `0x18002bfc8`
- `0x18002cd74`
- `0x18002d574`
- `0x18002df28`

## callees

- `0x180001690`
- `0x18002e060`

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
0x18002e060  cmp     rcx, cs:__security_cookie
0x18002e067  jnz     short ReportFailure
0x18002e069  rol     rcx, 10h
0x18002e06d  test    cx, 0FFFFh
0x18002e072  jnz     short RestoreRcx
0x18002e074  retn
0x18002e075  ror     rcx, 10h
0x18002e079  jmp     __report_gsfailure
```
