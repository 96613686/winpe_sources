# __security_check_cookie

- ea: `0x180016a40`
- end: `0x180016a5e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `61`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001c2c`
- `0x180004540`
- `0x180005470`
- `0x180005c74`
- `0x180006640`
- `0x180007db8`
- `0x180008098`
- `0x180008810`
- `0x180009ca0`
- `0x18000cb94`
- `0x18000cde0`
- `0x18000e460`
- `0x18000eaac`
- `0x18000f050`
- `0x18000f6e0`
- `0x18000fe30`
- `0x18001079c`
- `0x180010bb0`
- `0x180011050`
- `0x1800133d8`
- `0x180013540`
- `0x1800139f0`
- `0x180013bf8`
- `0x180013fc0`
- `0x18001405c`
- `0x180014640`
- `0x180014830`
- `0x1800185b8`
- `0x180018d78`
- `0x180019890`
- `0x180019bcc`
- `0x180019cec`
- `0x180019e6c`
- `0x18001a0d8`
- `0x18001a810`
- `0x18001aa20`
- `0x18001aca4`
- `0x18001c2bc`
- `0x18001c63c`
- `0x18001cc90`
- `0x18001e0bc`
- `0x18001e940`
- `0x18001faf0`
- `0x18001fc4c`
- `0x1800201e8`
- `0x1800205a8`
- `0x180020674`
- `0x180020ae0`
- `0x18002166c`
- `0x180023328`

## callees

- `0x180016a40`
- `0x180016a70`

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
0x180016a40  cmp     rcx, cs:__security_cookie
0x180016a47  jnz     short ReportFailure
0x180016a49  rol     rcx, 10h
0x180016a4d  test    cx, 0FFFFh
0x180016a52  jnz     short RestoreRcx
0x180016a54  retn
0x180016a55  ror     rcx, 10h; StackCookie
0x180016a59  jmp     __report_gsfailure
```
