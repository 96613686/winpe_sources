# __security_check_cookie

- ea: `0x180001760`
- end: `0x18000177e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `21`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000295c`
- `0x180002c08`
- `0x180003818`
- `0x180003bbc`
- `0x180003f8c`
- `0x1800049e4`
- `0x180004d60`
- `0x180005c88`
- `0x18000659c`
- `0x180007c1c`
- `0x180008630`
- `0x180008758`
- `0x18000a550`
- `0x18000a6dc`
- `0x18000cddc`
- `0x18000d0e4`
- `0x18000d7e0`
- `0x18000d9dc`
- `0x18000e494`
- `0x18000eb64`
- `0x18000f410`

## callees

- `0x180001760`
- `0x180001d50`

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
0x180001760  cmp     rcx, cs:__security_cookie
0x180001767  jnz     short ReportFailure
0x180001769  rol     rcx, 10h
0x18000176d  test    cx, 0FFFFh
0x180001772  jnz     short RestoreRcx
0x180001774  retn
0x180001775  ror     rcx, 10h; StackCookie
0x180001779  jmp     __report_gsfailure
```
