# __security_check_cookie

- ea: `0x18004c8e0`
- end: `0x18004c8fe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `84`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800010f0`
- `0x18000120c`
- `0x180001304`
- `0x180001540`
- `0x180001630`
- `0x180001728`
- `0x180001830`
- `0x18000195c`
- `0x180001aac`
- `0x180001cc0`
- `0x180001e28`
- `0x180001f38`
- `0x180002058`
- `0x180002164`
- `0x180002264`
- `0x1800023a4`
- `0x18000248c`
- `0x180007ec0`
- `0x18000c69c`
- `0x18000c848`
- `0x18000c9ac`
- `0x18000d7a4`
- `0x1800108f4`
- `0x1800161f0`
- `0x180016558`
- `0x180017088`
- `0x180017cc8`
- `0x180018390`
- `0x18001b3b8`
- `0x18001b790`
- `0x18001bf00`
- `0x18001c6f0`
- `0x180020cc4`
- `0x1800244ac`
- `0x180025520`
- `0x180026a4c`
- `0x180026d6c`
- `0x180027040`
- `0x180027214`
- `0x180027a40`
- `0x180027c80`
- `0x180027f1c`
- `0x180028600`
- `0x180028810`
- `0x180028cec`
- `0x180028eb0`
- `0x18002a1e8`
- `0x18002a354`
- `0x18002a900`

## callees

- `0x180002700`
- `0x18004c8e0`

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
0x18004c8e0  cmp     rcx, cs:__security_cookie
0x18004c8e7  jnz     short loc_18004C8F9
0x18004c8e9  rol     rcx, 10h
0x18004c8ed  test    cx, 0FFFFh
0x18004c8f2  jnz     short loc_18004C8F5
0x18004c8f4  retn
0x18004c8f5  ror     rcx, 10h
0x18004c8f9  jmp     __report_gsfailure
```
