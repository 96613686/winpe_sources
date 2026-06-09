# __security_check_cookie

- ea: `0x180001570`
- end: `0x18000158e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `16`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002674`
- `0x180002920`
- `0x180002eb8`
- `0x180003288`
- `0x180003804`
- `0x180003b80`
- `0x18000532c`
- `0x1800057f0`
- `0x180005a10`
- `0x180005be0`
- `0x180007438`
- `0x18000a870`
- `0x18000a920`
- `0x18000ab10`
- `0x18000ae44`
- `0x18000b464`

## callees

- `0x180001570`
- `0x180001bd0`

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
0x180001570  cmp     rcx, cs:__security_cookie
0x180001577  jnz     short ReportFailure
0x180001579  rol     rcx, 10h
0x18000157d  test    cx, 0FFFFh
0x180001582  jnz     short RestoreRcx
0x180001584  retn
0x180001585  ror     rcx, 10h; StackCookie
0x180001589  jmp     __report_gsfailure
```
