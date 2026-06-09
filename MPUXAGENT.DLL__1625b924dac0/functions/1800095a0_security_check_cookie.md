# __security_check_cookie

- ea: `0x1800095a0`
- end: `0x1800095be`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `222`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001000`
- `0x1800010ac`
- `0x180001310`
- `0x1800015a8`
- `0x180001874`
- `0x180001ae8`
- `0x180001dc8`
- `0x1800020cc`
- `0x180002354`
- `0x1800025ec`
- `0x180002898`
- `0x180002b58`
- `0x180002c0c`
- `0x180003040`
- `0x180003630`
- `0x1800039f4`
- `0x180003b34`
- `0x180003dc4`
- `0x180003eb0`
- `0x180004158`
- `0x1800042dc`
- `0x18000449c`
- `0x180004610`
- `0x180004848`
- `0x1800048c0`
- `0x1800049bc`
- `0x180004bac`
- `0x180004dc0`
- `0x180004ec0`
- `0x180005030`
- `0x180005318`
- `0x180005620`
- `0x1800057b4`
- `0x180005850`
- `0x180005e34`
- `0x180006558`
- `0x180006718`
- `0x1800067b4`
- `0x180006864`
- `0x180006914`
- `0x180006b78`
- `0x1800070ac`
- `0x1800076f8`
- `0x180007860`
- `0x180007914`
- `0x180007a38`
- `0x180007dac`
- `0x180008160`
- `0x180009190`
- `0x180009b6c`

## callees

- `0x1800095a0`
- `0x18000a380`

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
0x1800095a0  cmp     rcx, cs:__security_cookie
0x1800095a7  jnz     short ReportFailure
0x1800095a9  rol     rcx, 10h
0x1800095ad  test    cx, 0FFFFh
0x1800095b2  jnz     short RestoreRcx
0x1800095b4  retn
0x1800095b5  ror     rcx, 10h; StackCookie
0x1800095b9  jmp     __report_gsfailure
```
