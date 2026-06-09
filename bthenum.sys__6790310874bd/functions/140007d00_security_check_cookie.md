# __security_check_cookie

- ea: `0x140007d00`
- end: `0x140007d1e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `21`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400020d8`
- `0x140002660`
- `0x140003b54`
- `0x140003c44`
- `0x140007a78`
- `0x140007bcc`
- `0x14001849c`
- `0x140019058`
- `0x14001bb54`
- `0x14001bc4c`
- `0x14001bda0`
- `0x14001c8d0`
- `0x14001ca00`
- `0x14001cf90`
- `0x14001d960`
- `0x14001dba4`
- `0x14001df2c`
- `0x14001e1e0`
- `0x14001f300`
- `0x140020078`
- `0x140020704`

## callees

- `0x1400010c0`
- `0x140007d00`

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
0x140007d00  cmp     rcx, cs:__security_cookie
0x140007d07  jnz     short ReportFailure
0x140007d09  rol     rcx, 10h
0x140007d0d  test    cx, 0FFFFh
0x140007d12  jnz     short RestoreRcx
0x140007d14  retn
0x140007d15  ror     rcx, 10h; StackCookie
0x140007d19  jmp     __report_gsfailure
```
