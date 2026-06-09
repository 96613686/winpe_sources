# __security_check_cookie

- ea: `0x180165920`
- end: `0x18016593e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `341`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800010c0`
- `0x1800011a0`
- `0x180001500`
- `0x1800015c0`
- `0x180001674`
- `0x1800018c0`
- `0x180001b30`
- `0x180001e60`
- `0x1800020d0`
- `0x180002250`
- `0x180002360`
- `0x1800025d0`
- `0x1800028a0`
- `0x1800031b0`
- `0x180003740`
- `0x180004140`
- `0x180004cf0`
- `0x1800051a0`
- `0x180005fb0`
- `0x180006bd0`
- `0x180007b60`
- `0x180007ca0`
- `0x180008750`
- `0x18000a720`
- `0x18000a870`
- `0x18000a9e0`
- `0x18000aed0`
- `0x18000b220`
- `0x18000b570`
- `0x18000b8e0`
- `0x18000bc30`
- `0x18000c260`
- `0x18000c600`
- `0x18000cc20`
- `0x18000cf90`
- `0x18000d5c0`
- `0x18000d980`
- `0x18000dfc0`
- `0x1800100f0`
- `0x1800125c0`
- `0x180013000`
- `0x1800134b0`
- `0x180013a50`
- `0x180015000`
- `0x180015760`
- `0x1800163e0`
- `0x180017be0`
- `0x180018160`
- `0x180018fc0`
- `0x180019e70`

## callees

- `0x180165920`
- `0x180166150`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
ReportFailure:
    sub_180166150(StackCookie);
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
0x180165920  cmp     rcx, cs:__security_cookie
0x180165927  jnz     short ReportFailure
0x180165929  rol     rcx, 10h
0x18016592d  test    cx, 0FFFFh
0x180165932  jnz     short RestoreRcx
0x180165934  retn
0x180165935  ror     rcx, 10h
0x180165939  jmp     sub_180166150
```
