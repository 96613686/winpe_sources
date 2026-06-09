# __security_check_cookie

- ea: `0x1800022b0`
- end: `0x1800022ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `167`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002f48`
- `0x18000aa50`
- `0x18000bba4`
- `0x18000c030`
- `0x18000c310`
- `0x18000c9a4`
- `0x18000cea0`
- `0x18000d36c`
- `0x18000d88c`
- `0x18000dd70`
- `0x18000e2a0`
- `0x18000e798`
- `0x18000ec6c`
- `0x18000ede8`
- `0x18000fae8`
- `0x18000fe78`
- `0x1800101fc`
- `0x18001059c`
- `0x180010938`
- `0x180010cf0`
- `0x180011224`
- `0x1800113b0`
- `0x180013c40`
- `0x180013f68`
- `0x1800142b4`
- `0x180014344`
- `0x180015a70`
- `0x180016d20`
- `0x180018f1c`
- `0x18001bf40`
- `0x18001c718`
- `0x18001d19c`
- `0x18001d390`
- `0x18001d640`
- `0x18001e960`
- `0x1800202fc`
- `0x1800208a8`
- `0x180020db4`
- `0x180021994`
- `0x180021e58`
- `0x180022300`
- `0x180022ad0`
- `0x1800243b4`
- `0x180024fb0`
- `0x180026758`
- `0x180026980`
- `0x180026c34`
- `0x180026ea0`
- `0x1800270a8`
- `0x180027310`

## callees

- `0x1800022b0`
- `0x180002b60`

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
0x1800022b0  cmp     rcx, cs:__security_cookie
0x1800022b7  jnz     short loc_1800022C9
0x1800022b9  rol     rcx, 10h
0x1800022bd  test    cx, 0FFFFh
0x1800022c2  jnz     short loc_1800022C5
0x1800022c4  retn
0x1800022c5  ror     rcx, 10h; StackCookie
0x1800022c9  jmp     __report_gsfailure
```
