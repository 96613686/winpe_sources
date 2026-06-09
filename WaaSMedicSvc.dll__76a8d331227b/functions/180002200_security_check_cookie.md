# __security_check_cookie

- ea: `0x180002200`
- end: `0x18000221e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `31`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x18000194c`
- `0x180002940`
- `0x18000357c`
- `0x180003828`
- `0x180003dd8`
- `0x1800041a8`
- `0x180004714`
- `0x180004a90`
- `0x1800063ec`
- `0x1800068d0`
- `0x180006aec`
- `0x180006d54`
- `0x180007074`
- `0x1800071c8`
- `0x18000865c`
- `0x180008794`
- `0x180008b20`
- `0x180008dd8`
- `0x180009010`
- `0x180009b34`
- `0x180009d10`
- `0x180009fc8`
- `0x18000a060`
- `0x18000a168`
- `0x18000a36c`
- `0x18000a41c`
- `0x18000aa84`
- `0x18000ae6c`
- `0x18000b4e8`

## callees

- `0x180002200`
- `0x180002b60`

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
0x180002200  cmp     rcx, cs:__security_cookie
0x180002207  jnz     short ReportFailure
0x180002209  rol     rcx, 10h
0x18000220d  test    cx, 0FFFFh
0x180002212  jnz     short RestoreRcx
0x180002214  retn
0x180002215  ror     rcx, 10h; StackCookie
0x180002219  jmp     __report_gsfailure
```
