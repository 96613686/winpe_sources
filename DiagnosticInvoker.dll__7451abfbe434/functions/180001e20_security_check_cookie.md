# __security_check_cookie

- ea: `0x180001e20`
- end: `0x180001e3e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `28`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000108c`
- `0x180001270`
- `0x1800013c4`
- `0x180001540`
- `0x1800016a8`
- `0x1800032d0`
- `0x180003564`
- `0x180003b08`
- `0x180003ed8`
- `0x180004444`
- `0x1800047c0`
- `0x180005fcc`
- `0x180006490`
- `0x1800068b0`
- `0x180006f28`
- `0x180007088`
- `0x180007b98`
- `0x18000881c`
- `0x18000b994`
- `0x18000c780`
- `0x18000dad0`
- `0x18000e070`
- `0x18000e5b0`
- `0x18000eca0`
- `0x18000f718`
- `0x18000f780`
- `0x18000fa58`
- `0x18000ff2c`

## callees

- `0x180001e20`
- `0x1800024e0`

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
0x180001e20  cmp     rcx, cs:__security_cookie
0x180001e27  jnz     short ReportFailure
0x180001e29  rol     rcx, 10h
0x180001e2d  test    cx, 0FFFFh
0x180001e32  jnz     short RestoreRcx
0x180001e34  retn
0x180001e35  ror     rcx, 10h; StackCookie
0x180001e39  jmp     __report_gsfailure
```
