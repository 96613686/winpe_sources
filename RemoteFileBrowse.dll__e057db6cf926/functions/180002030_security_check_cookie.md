# __security_check_cookie

- ea: `0x180002030`
- end: `0x18000204e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `46`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001200`
- `0x180001760`
- `0x180001960`
- `0x180001ad0`
- `0x180002764`
- `0x180003324`
- `0x1800035e0`
- `0x180004450`
- `0x180004738`
- `0x18000499c`
- `0x180004fa4`
- `0x180005250`
- `0x180005f70`
- `0x180006690`
- `0x180006d48`
- `0x180007b30`
- `0x180007e50`
- `0x180008800`
- `0x1800088e4`
- `0x180008ae0`
- `0x180008d90`
- `0x18000a0e8`
- `0x18000ba9c`
- `0x18000ed34`
- `0x1800108a8`
- `0x180010a80`
- `0x180010bec`
- `0x180010d00`
- `0x180010e20`
- `0x1800114f0`
- `0x18001213c`
- `0x18001277c`
- `0x180013484`
- `0x180013604`
- `0x180013b1c`
- `0x180013bb0`
- `0x180014080`
- `0x180014570`
- `0x180014910`
- `0x1800150c0`
- `0x180015660`
- `0x180015e20`
- `0x180016124`
- `0x180016600`
- `0x180016830`
- `0x180016f04`

## callees

- `0x180002030`
- `0x180002c10`

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
0x180002030  cmp     rcx, cs:__security_cookie
0x180002037  jnz     short ReportFailure
0x180002039  rol     rcx, 10h
0x18000203d  test    cx, 0FFFFh
0x180002042  jnz     short RestoreRcx
0x180002044  retn
0x180002045  ror     rcx, 10h; StackCookie
0x180002049  jmp     __report_gsfailure
```
