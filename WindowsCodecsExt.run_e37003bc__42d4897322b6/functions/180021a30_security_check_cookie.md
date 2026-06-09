# __security_check_cookie

- ea: `0x180021a30`
- end: `0x180021a4e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `41`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002aa0`
- `0x1800038e0`
- `0x180004194`
- `0x180005540`
- `0x180005900`
- `0x180005db0`
- `0x180007670`
- `0x180008990`
- `0x180008f24`
- `0x18000a2b8`
- `0x18000a3b0`
- `0x18000ab60`
- `0x18000b7b0`
- `0x18000bd40`
- `0x18000cf80`
- `0x180010960`
- `0x180010cf0`
- `0x180011308`
- `0x18001179c`
- `0x180011ad4`
- `0x180012840`
- `0x180013670`
- `0x180013b04`
- `0x180014e90`
- `0x180015440`
- `0x180017560`
- `0x1800180a0`
- `0x1800183f8`
- `0x18001883c`
- `0x180018d78`
- `0x18001a40c`
- `0x18001a730`
- `0x18001d240`
- `0x18001da20`
- `0x18001f140`
- `0x18001f708`
- `0x18001fd80`
- `0x180020020`
- `0x1800236f0`
- `0x18002c2c0`
- `0x180032d40`

## callees

- `0x180021a30`
- `0x180021fc0`

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
0x180021a30  cmp     rcx, cs:__security_cookie
0x180021a37  jnz     short ReportFailure
0x180021a39  rol     rcx, 10h
0x180021a3d  test    cx, 0FFFFh
0x180021a42  jnz     short RestoreRcx
0x180021a44  retn
0x180021a45  ror     rcx, 10h; StackCookie
0x180021a49  jmp     __report_gsfailure
```
