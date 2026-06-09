# __security_check_cookie

- ea: `0x180001460`
- end: `0x18000147e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `58`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800023c4`
- `0x1800026b8`
- `0x1800029c8`
- `0x180002a50`
- `0x180003dc4`
- `0x180004a10`
- `0x1800063a0`
- `0x180007870`
- `0x1800084a0`
- `0x180008bb8`
- `0x180008d84`
- `0x180008ea0`
- `0x180009348`
- `0x180009a00`
- `0x18000a2d0`
- `0x18000a870`
- `0x18000c2e0`
- `0x18000c6b0`
- `0x18000c780`
- `0x18000e1a8`
- `0x18000e3f8`
- `0x18000e664`
- `0x18000e938`
- `0x18000f010`
- `0x18000fef0`
- `0x180010870`
- `0x180011d44`
- `0x18001274c`
- `0x180013a58`
- `0x180013bb8`
- `0x180014370`
- `0x180016410`
- `0x180016758`
- `0x1800170b4`
- `0x180017340`
- `0x1800174cc`
- `0x180018dc0`
- `0x18001ae94`
- `0x18001b4f0`
- `0x18001bf80`
- `0x18001c0b0`
- `0x18001c1d0`
- `0x18001c490`
- `0x18001cad0`
- `0x18001cc60`
- `0x1800203fc`
- `0x180020a34`
- `0x18002112c`
- `0x180022970`
- `0x180022a80`

## callees

- `0x180001460`
- `0x180001b00`

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
0x180001460  cmp     rcx, cs:__security_cookie
0x180001467  jnz     short ReportFailure
0x180001469  rol     rcx, 10h
0x18000146d  test    cx, 0FFFFh
0x180001472  jnz     short RestoreRcx
0x180001474  retn
0x180001475  ror     rcx, 10h; StackCookie
0x180001479  jmp     __report_gsfailure
```
