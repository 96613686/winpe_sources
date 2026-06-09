# Kerb3961::YouMustLinkWithTheWholearchiveFlag(void)

- ea: `0x18000df98`
- end: `0x18000dfb7`
- name: `?YouMustLinkWithTheWholearchiveFlag@Kerb3961@@YAXXZ`
- size: `31`
- prototype: `void __fastcall(Kerb3961 *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c400`

## callees

- `0x1800033f4`
- `0x18000df98`

## string_xrefs

- `0x18000dfaa`: `You must pass the /WHOLEARCHIVE flag to the linker`

## pseudocode

```c
void __fastcall Kerb3961::YouMustLinkWithTheWholearchiveFlag(Kerb3961 *this, const unsigned __int16 *a2)
{
  if ( !Kerb3961::g_dynamicInitializationDone )
    Kerb3961::ConsistencyFail((Kerb3961 *)L"You must pass the /WHOLEARCHIVE flag to the linker", a2);
}

```

## disassembly

```asm
0x18000df98  sub     rsp, 28h
0x18000df9c  cmp     cs:?g_dynamicInitializationDone@Kerb3961@@3_NA, 0; bool Kerb3961::g_dynamicInitializationDone
0x18000dfa3  jz      short loc_18000DFAA
0x18000dfa5  add     rsp, 28h
0x18000dfa9  retn
0x18000dfaa  lea     rcx, aYouMustPassThe; "You must pass the /WHOLEARCHIVE flag to"...
0x18000dfb1  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
