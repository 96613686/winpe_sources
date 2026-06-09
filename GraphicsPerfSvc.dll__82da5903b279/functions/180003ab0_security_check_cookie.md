# __security_check_cookie

- ea: `0x180003ab0`
- end: `0x180003ace`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `77`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800011a8`
- `0x18000145c`
- `0x180001754`
- `0x1800018d8`
- `0x18000199c`
- `0x180001a40`
- `0x180001d8c`
- `0x18000214c`
- `0x180002414`
- `0x180002578`
- `0x180002658`
- `0x180002738`
- `0x1800028d8`
- `0x180002da4`
- `0x180002e6c`
- `0x180002f30`
- `0x180002ff0`
- `0x180003098`
- `0x180004ac0`
- `0x18000516c`
- `0x180005418`
- `0x180006198`
- `0x180006304`
- `0x1800064d4`
- `0x180006c14`
- `0x180007010`
- `0x180008638`
- `0x180008d5c`
- `0x180009e0c`
- `0x18000abd0`
- `0x18000add8`
- `0x18000b060`
- `0x18000b350`
- `0x18000bab0`
- `0x18000bff0`
- `0x18000d310`
- `0x18000dbb4`
- `0x18000dd64`
- `0x18000f960`
- `0x180010070`
- `0x1800102e0`
- `0x180010880`
- `0x180011630`
- `0x1800125fc`
- `0x18001275c`
- `0x180012c84`
- `0x180013530`
- `0x180013700`
- `0x1800138b0`

## callees

- `0x180003ab0`
- `0x1800043b0`

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
0x180003ab0  cmp     rcx, cs:__security_cookie
0x180003ab7  jnz     short ReportFailure
0x180003ab9  rol     rcx, 10h
0x180003abd  test    cx, 0FFFFh
0x180003ac2  jnz     short RestoreRcx
0x180003ac4  retn
0x180003ac5  ror     rcx, 10h; StackCookie
0x180003ac9  jmp     __report_gsfailure
```
