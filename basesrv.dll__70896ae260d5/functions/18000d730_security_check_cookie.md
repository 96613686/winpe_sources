# __security_check_cookie

- ea: `0x18000d730`
- end: `0x18000d74e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `20`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180002190`
- `0x180002250`
- `0x1800029f0`
- `0x180002f50`
- `0x180004210`
- `0x180004d80`
- `0x180005210`
- `0x180006700`
- `0x180006ba0`
- `0x180007f20`
- `0x18000b6c0`
- `0x18000b7ac`
- `0x18000ba38`
- `0x18000c61c`
- `0x18000cbc0`
- `0x18000cd80`
- `0x18000d34c`
- `0x18000d494`
- `0x18000d60c`

## callees

- `0x180007580`
- `0x18000d730`

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
0x18000d730  cmp     rcx, cs:__security_cookie
0x18000d737  jnz     short loc_18000D749
0x18000d739  rol     rcx, 10h
0x18000d73d  test    cx, 0FFFFh
0x18000d742  jnz     short loc_18000D745
0x18000d744  retn
0x18000d745  ror     rcx, 10h
0x18000d749  jmp     __report_gsfailure
```
