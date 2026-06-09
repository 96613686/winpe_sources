# __security_check_cookie

- ea: `0x18000d404`
- end: `0x18000d423`
- name: `__security_check_cookie`
- size: `31`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `162`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000236c`
- `0x18000d424`
- `0x180010da0`
- `0x180011350`
- `0x180011be8`
- `0x18001219c`
- `0x180012a30`
- `0x180012fd8`
- `0x1800136f4`
- `0x1800145e0`
- `0x180014cfc`
- `0x180015690`
- `0x180015c38`
- `0x1800165dc`
- `0x180016b8c`
- `0x180017134`
- `0x180017858`
- `0x180018380`
- `0x180018930`
- `0x180019544`
- `0x180019740`
- `0x18001ba58`
- `0x18001df68`
- `0x18001ee3c`
- `0x18001f5dc`
- `0x18001f810`
- `0x180020240`
- `0x1800220a0`
- `0x180022858`
- `0x180023064`
- `0x180024454`
- `0x180024a0c`
- `0x180024e44`
- `0x180024ee8`
- `0x1800251bc`
- `0x180025ab4`
- `0x180025c70`
- `0x180025e18`
- `0x18002605c`
- `0x1800282fc`
- `0x180028864`
- `0x180028c80`
- `0x180029288`
- `0x180029bb0`
- `0x18002b1b8`
- `0x18002bd30`
- `0x18002d20c`
- `0x18002d94c`
- `0x18002e008`
- `0x18002e158`

## callees

- `0x18000d404`
- `0x18004c314`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie == qword_1800A3A40 )
  {
    v1 = __ROL8__(StackCookie, 16);
    if ( !(_WORD)v1 )
      return;
    StackCookie = __ROR8__(v1, 16);
  }
  sub_18004C314(StackCookie);
}

```

## disassembly

```asm
0x18000d404  cmp     rcx, cs:qword_1800A3A40
0x18000d40b  jnz     short loc_18000D41E
0x18000d40d  rol     rcx, 10h
0x18000d411  test    cx, 0FFFFh
0x18000d416  jnz     short loc_18000D41A
0x18000d418  rep retn
0x18000d41a  ror     rcx, 10h
0x18000d41e  jmp     sub_18004C314
```
