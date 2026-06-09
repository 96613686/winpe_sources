# __security_check_cookie

- ea: `0x1400023d0`
- end: `0x1400023ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `38`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x1400011dc`
- `0x14000126c`
- `0x14000134c`
- `0x1400013f8`
- `0x1400016d0`
- `0x140001794`
- `0x140001a48`
- `0x140001d40`
- `0x1400037e4`
- `0x140003aa0`
- `0x140004850`
- `0x140004b28`
- `0x140004c40`
- `0x140005590`
- `0x1400068c0`
- `0x140006dd0`
- `0x1400070a0`
- `0x14000728c`
- `0x140007634`
- `0x14000835c`
- `0x140008d3c`
- `0x140008f9c`
- `0x14000936c`
- `0x140009764`
- `0x140009bf0`
- `0x14000af58`
- `0x14000b804`
- `0x14000c81c`
- `0x14000cc0c`
- `0x14000cfc4`
- `0x14000e2a8`
- `0x14000e8c4`
- `0x14000f6dc`
- `0x14000f81c`
- `0x14000fb3c`
- `0x1400100ac`
- `0x14001114c`

## callees

- `0x1400023d0`
- `0x140002430`

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
0x1400023d0  cmp     rcx, cs:__security_cookie
0x1400023d7  jnz     short loc_1400023E9
0x1400023d9  rol     rcx, 10h
0x1400023dd  test    cx, 0FFFFh
0x1400023e2  jnz     short loc_1400023E5
0x1400023e4  retn
0x1400023e5  ror     rcx, 10h; StackCookie
0x1400023e9  jmp     __report_gsfailure
```
