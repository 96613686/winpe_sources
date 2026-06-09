# __security_check_cookie

- ea: `0x180001ed0`
- end: `0x180001eee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `26`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001124`
- `0x1800013d8`
- `0x1800016d0`
- `0x180003214`
- `0x1800034a8`
- `0x180004378`
- `0x1800044e4`
- `0x1800046e0`
- `0x1800064b4`
- `0x180006868`
- `0x180007f20`
- `0x180008618`
- `0x18000a07c`
- `0x18000af80`
- `0x18000b188`
- `0x18000b550`
- `0x18000bc00`
- `0x18000c244`
- `0x18000c2e8`
- `0x18000ed18`
- `0x18000ee8c`
- `0x18000f228`
- `0x18000f380`
- `0x18000f450`
- `0x18000ff30`

## callees

- `0x180001ed0`
- `0x180002490`

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
0x180001ed0  cmp     rcx, cs:__security_cookie
0x180001ed7  jnz     short ReportFailure
0x180001ed9  rol     rcx, 10h
0x180001edd  test    cx, 0FFFFh
0x180001ee2  jnz     short RestoreRcx
0x180001ee4  retn
0x180001ee5  ror     rcx, 10h; StackCookie
0x180001ee9  jmp     __report_gsfailure
```
