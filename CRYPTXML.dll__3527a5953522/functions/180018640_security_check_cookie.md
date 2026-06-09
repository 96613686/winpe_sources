# __security_check_cookie

- ea: `0x180018640`
- end: `0x18001865e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `23`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180003650`
- `0x180004f90`
- `0x1800057a0`
- `0x180006150`
- `0x180007730`
- `0x1800080b0`
- `0x180009a10`
- `0x180009f80`
- `0x18000a310`
- `0x18000c990`
- `0x18000e290`
- `0x18000efc0`
- `0x18000f200`
- `0x18000f7d0`
- `0x18000fe50`
- `0x180010da0`
- `0x180012838`
- `0x180014ce0`
- `0x180014e14`
- `0x18001632c`
- `0x1800183e4`
- `0x18001858c`

## callees

- `0x180015440`
- `0x180018640`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
LABEL_4:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto LABEL_4;
  }
}

```

## disassembly

```asm
0x180018640  cmp     rcx, cs:__security_cookie
0x180018647  jnz     short loc_180018659
0x180018649  rol     rcx, 10h
0x18001864d  test    cx, 0FFFFh
0x180018652  jnz     short loc_180018655
0x180018654  retn
0x180018655  ror     rcx, 10h
0x180018659  jmp     __report_gsfailure
```
