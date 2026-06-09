# __security_check_cookie

- ea: `0x180017c00`
- end: `0x180017c1e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `29`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002d84`
- `0x180004c48`
- `0x180006530`
- `0x1800069c0`
- `0x180009c84`
- `0x18000ac38`
- `0x18000b604`
- `0x18000cab0`
- `0x18000d4b0`
- `0x18000dc98`
- `0x18000fecc`
- `0x180010168`
- `0x180010f58`
- `0x180011324`
- `0x180011708`
- `0x180012174`
- `0x1800124f0`
- `0x180013204`
- `0x180013438`
- `0x1800136bc`
- `0x180013f90`
- `0x18001531c`
- `0x180015d90`
- `0x180015ea0`
- `0x1800165d0`
- `0x180016794`
- `0x1800174e0`
- `0x1800175a8`
- `0x180017adc`

## callees

- `0x180001a20`
- `0x180017c00`

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
0x180017c00  cmp     rcx, cs:__security_cookie
0x180017c07  jnz     short ReportFailure
0x180017c09  rol     rcx, 10h
0x180017c0d  test    cx, 0FFFFh
0x180017c12  jnz     short RestoreRcx
0x180017c14  retn
0x180017c15  ror     rcx, 10h
0x180017c19  jmp     __report_gsfailure
```
