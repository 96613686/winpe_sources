# __security_check_cookie

- ea: `0x140013950`
- end: `0x14001396e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `25`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140004910`
- `0x14000a84c`
- `0x14000b0bc`
- `0x14000be30`
- `0x14000fee8`
- `0x140011250`
- `0x1400114a4`
- `0x140011fb0`
- `0x1400137ac`
- `0x14001f1c4`
- `0x14001f964`
- `0x14001fca8`
- `0x1400208c0`
- `0x140021710`
- `0x140023ab8`
- `0x140024a24`
- `0x140025358`
- `0x140025630`
- `0x140026f6c`
- `0x1400275b4`
- `0x1400276a4`
- `0x140028344`
- `0x140028628`
- `0x140028b50`
- `0x14002b138`

## callees

- `0x140010730`
- `0x140013950`

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
0x140013950  cmp     rcx, cs:__security_cookie
0x140013957  jnz     short ReportFailure
0x140013959  rol     rcx, 10h
0x14001395d  test    cx, 0FFFFh
0x140013962  jnz     short RestoreRcx
0x140013964  retn
0x140013965  ror     rcx, 10h; StackCookie
0x140013969  jmp     __report_gsfailure
```
