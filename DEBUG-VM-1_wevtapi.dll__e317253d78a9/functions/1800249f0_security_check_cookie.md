# __security_check_cookie

- ea: `0x1800249f0`
- end: `0x180024a0e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `65`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000108c`
- `0x180001174`
- `0x180001840`
- `0x180001f34`
- `0x1800023e8`
- `0x180005ad4`
- `0x1800071b0`
- `0x180007fb8`
- `0x18000ab80`
- `0x18000b8b4`
- `0x18000ba30`
- `0x18000c490`
- `0x18000d650`
- `0x18000d818`
- `0x18000dac0`
- `0x18000dff8`
- `0x18000e248`
- `0x18000e5b0`
- `0x18000e778`
- `0x18000ec98`
- `0x18000f3ec`
- `0x180013cc4`
- `0x180014938`
- `0x180014bb0`
- `0x18001b210`
- `0x18001b3d4`
- `0x18001bbcc`
- `0x18001c6e4`
- `0x18001db8c`
- `0x18001e798`
- `0x18001ecf0`
- `0x180021a2c`
- `0x18002404c`
- `0x1800243cc`
- `0x180026e30`
- `0x18002786c`
- `0x180027b4c`
- `0x180028900`
- `0x18002968c`
- `0x180029780`
- `0x180029de4`
- `0x180029f4c`
- `0x18002a234`
- `0x18002a894`
- `0x18002ab50`
- `0x18002bc98`
- `0x18002bfa4`
- `0x18002cd34`
- `0x18002d738`
- `0x18002d908`

## callees

- `0x1800249f0`
- `0x1800250f0`

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
0x1800249f0  cmp     rcx, cs:__security_cookie
0x1800249f7  jnz     short ReportFailure
0x1800249f9  rol     rcx, 10h
0x1800249fd  test    cx, 0FFFFh
0x180024a02  jnz     short RestoreRcx
0x180024a04  retn
0x180024a05  ror     rcx, 10h; StackCookie
0x180024a09  jmp     __report_gsfailure
```
