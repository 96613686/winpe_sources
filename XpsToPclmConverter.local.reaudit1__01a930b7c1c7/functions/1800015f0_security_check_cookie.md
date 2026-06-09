# __security_check_cookie

- ea: `0x1800015f0`
- end: `0x18000160e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `53`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800067d0`
- `0x1800076d0`
- `0x180007c74`
- `0x180007f20`
- `0x180008bc8`
- `0x180008d30`
- `0x180008ef8`
- `0x1800095d4`
- `0x180009988`
- `0x18000acf0`
- `0x18000b3d4`
- `0x18000c49c`
- `0x18000cf90`
- `0x18000d198`
- `0x18000f924`
- `0x180010290`
- `0x180012f34`
- `0x180014204`
- `0x180014a14`
- `0x1800152f4`
- `0x18001583c`
- `0x1800158e4`
- `0x1800159d0`
- `0x180015bf0`
- `0x180015de4`
- `0x180016218`
- `0x180016704`
- `0x1800168d0`
- `0x180016da4`
- `0x180017418`
- `0x180017c6c`
- `0x180017d98`
- `0x18001806c`
- `0x180018334`
- `0x180018640`
- `0x180018950`
- `0x1800189c4`
- `0x180018e10`
- `0x180018fb0`
- `0x1800194a0`
- `0x180019610`
- `0x1800196c0`
- `0x180019930`
- `0x1800199e0`
- `0x180019db0`
- `0x18001a2b0`
- `0x18001a3a0`
- `0x18001a61c`
- `0x18001a7d0`
- `0x18001a854`

## callees

- `0x1800015f0`
- `0x180001cb0`

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
0x1800015f0  cmp     rcx, cs:__security_cookie
0x1800015f7  jnz     short ReportFailure
0x1800015f9  rol     rcx, 10h
0x1800015fd  test    cx, 0FFFFh
0x180001602  jnz     short RestoreRcx
0x180001604  retn
0x180001605  ror     rcx, 10h; StackCookie
0x180001609  jmp     __report_gsfailure
```
