# __security_check_cookie

- ea: `0x140007750`
- end: `0x14000776e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `15`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x14000116c`
- `0x14000125c`
- `0x1400017c8`
- `0x140002ac0`
- `0x1400037d0`
- `0x140003e54`
- `0x140004c20`
- `0x1400061c4`
- `0x1400068e0`
- `0x140006a78`
- `0x140006c94`
- `0x140006de4`
- `0x140007330`
- `0x1400076cc`

## callees

- `0x1400014a0`
- `0x140007750`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
LABEL_4:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto LABEL_4;
  }
}

```

## disassembly

```asm
0x140007750  cmp     rcx, cs:__security_cookie
0x140007757  jnz     short loc_140007769
0x140007759  rol     rcx, 10h
0x14000775d  test    cx, 0FFFFh
0x140007762  jnz     short loc_140007765
0x140007764  retn
0x140007765  ror     rcx, 10h
0x140007769  jmp     __report_gsfailure
```
