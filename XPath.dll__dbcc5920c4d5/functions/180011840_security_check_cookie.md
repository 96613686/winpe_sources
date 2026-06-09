# __security_check_cookie

- ea: `0x180011840`
- end: `0x18001185e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800031d0`
- `0x18000a3a8`
- `0x18000a8f4`
- `0x18000b2f0`
- `0x18000b690`
- `0x18000bc00`
- `0x18000c550`
- `0x18001082c`
- `0x180010bc8`
- `0x180011778`

## callees

- `0x1800015f0`
- `0x180011840`

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
0x180011840  cmp     rcx, cs:__security_cookie
0x180011847  jnz     short ReportFailure
0x180011849  rol     rcx, 10h
0x18001184d  test    cx, 0FFFFh
0x180011852  jnz     short RestoreRcx
0x180011854  retn
0x180011855  ror     rcx, 10h
0x180011859  jmp     __report_gsfailure
```
