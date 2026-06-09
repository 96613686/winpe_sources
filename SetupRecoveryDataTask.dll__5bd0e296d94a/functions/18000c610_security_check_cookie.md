# __security_check_cookie

- ea: `0x18000c610`
- end: `0x18000c62e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `46`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000108c`
- `0x18000290c`
- `0x180002ba8`
- `0x180003940`
- `0x180003ce4`
- `0x1800040f4`
- `0x180004140`
- `0x180004654`
- `0x180004840`
- `0x180004aa8`
- `0x180004ba0`
- `0x180004cc0`
- `0x180005054`
- `0x180005148`
- `0x180005430`
- `0x1800055e4`
- `0x180005960`
- `0x180005c34`
- `0x180005f60`
- `0x180006cf0`
- `0x180006d90`
- `0x18000713c`
- `0x1800072cc`
- `0x1800073d8`
- `0x1800074e4`
- `0x180007864`
- `0x1800078b8`
- `0x180007910`
- `0x1800079c8`
- `0x180007b94`
- `0x180007f30`
- `0x1800085a8`
- `0x180009480`
- `0x180009528`
- `0x1800098dc`
- `0x180009c50`
- `0x18000a210`
- `0x18000a924`
- `0x18000b320`
- `0x18000b430`
- `0x18000b780`
- `0x18000b928`
- `0x18000beb0`
- `0x18000c134`
- `0x18000c2d4`
- `0x18000c4fc`

## callees

- `0x180001f50`
- `0x18000c610`

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
0x18000c610  cmp     rcx, cs:__security_cookie
0x18000c617  jnz     short ReportFailure
0x18000c619  rol     rcx, 10h
0x18000c61d  test    cx, 0FFFFh
0x18000c622  jnz     short RestoreRcx
0x18000c624  retn
0x18000c625  ror     rcx, 10h
0x18000c629  jmp     __report_gsfailure
```
