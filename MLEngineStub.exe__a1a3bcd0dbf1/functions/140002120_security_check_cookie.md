# __security_check_cookie

- ea: `0x140002120`
- end: `0x14000213e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `27`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x1400012bc`
- `0x14000193c`
- `0x140002454`
- `0x140003208`
- `0x14000349c`
- `0x140003a38`
- `0x140003e08`
- `0x140004374`
- `0x1400046f0`
- `0x140005ebc`
- `0x1400063a0`
- `0x140006614`
- `0x140006dd8`
- `0x140006ed8`
- `0x140007ec8`
- `0x140008058`
- `0x1400083e4`
- `0x14000869c`
- `0x1400088ac`
- `0x1400091b4`
- `0x140009390`
- `0x1400095d8`
- `0x14000966c`
- `0x14000980c`
- `0x140009d9c`
- `0x14000a678`

## callees

- `0x140002120`
- `0x1400027d0`

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
0x140002120  cmp     rcx, cs:__security_cookie
0x140002127  jnz     short loc_140002139
0x140002129  rol     rcx, 10h
0x14000212d  test    cx, 0FFFFh
0x140002132  jnz     short loc_140002135
0x140002134  retn
0x140002135  ror     rcx, 10h; StackCookie
0x140002139  jmp     __report_gsfailure
```
