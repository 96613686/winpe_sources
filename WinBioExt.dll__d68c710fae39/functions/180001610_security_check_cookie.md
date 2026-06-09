# __security_check_cookie

- ea: `0x180001610`
- end: `0x18000162e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002928`
- `0x180002bc4`
- `0x180003168`
- `0x180003518`
- `0x180003b04`
- `0x180003e80`
- `0x18000579c`
- `0x180005c50`
- `0x180006b8c`
- `0x180007824`
- `0x180008428`
- `0x180008ce0`
- `0x180009b54`
- `0x180009e68`

## callees

- `0x180001610`
- `0x180001c00`

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
0x180001610  cmp     rcx, cs:__security_cookie
0x180001617  jnz     short ReportFailure
0x180001619  rol     rcx, 10h
0x18000161d  test    cx, 0FFFFh
0x180001622  jnz     short RestoreRcx
0x180001624  retn
0x180001625  ror     rcx, 10h; StackCookie
0x180001629  jmp     __report_gsfailure
```
