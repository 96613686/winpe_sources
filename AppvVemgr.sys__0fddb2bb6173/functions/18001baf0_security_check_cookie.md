# __security_check_cookie

- ea: `0x18001baf0`
- end: `0x18001bb0e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `22`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001f78`
- `0x180002d7c`
- `0x180007f88`
- `0x18000fd14`
- `0x18000fd5c`
- `0x18000fdc0`
- `0x18000fe44`
- `0x180010058`
- `0x180010374`
- `0x1800107e4`
- `0x1800109c4`
- `0x180012004`
- `0x180012264`
- `0x1800124d0`
- `0x180012d7c`
- `0x180013af0`
- `0x18001aea0`
- `0x18001b3cc`
- `0x18001b94c`
- `0x18002bda8`
- `0x18002c91c`
- `0x18002e078`

## callees

- `0x180001010`
- `0x18001baf0`

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
0x18001baf0  cmp     rcx, cs:__security_cookie
0x18001baf7  jnz     short ReportFailure
0x18001baf9  rol     rcx, 10h
0x18001bafd  test    cx, 0FFFFh
0x18001bb02  jnz     short RestoreRcx
0x18001bb04  retn
0x18001bb05  ror     rcx, 10h; StackCookie
0x18001bb09  jmp     __report_gsfailure
```
