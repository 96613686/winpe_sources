# Kerb3961::YouMustLinkWithTheWholearchiveFlag(void)

- ea: `0x18000d100`
- end: `0x18000d120`
- name: `?YouMustLinkWithTheWholearchiveFlag@Kerb3961@@YAXXZ`
- size: `32`
- prototype: `void __fastcall(Kerb3961 *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c140`

## callees

- `0x180003a38`
- `0x18000d100`

## string_xrefs

- `0x18000d113`: `You must pass the /WHOLEARCHIVE flag to the linker`

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
0x18000d100  sub     rsp, 28h
0x18000d104  cmp     cs:?g_dynamicInitializationDone@Kerb3961@@3_NA, 0; bool Kerb3961::g_dynamicInitializationDone
0x18000d10b  jz      short loc_18000D113
0x18000d10d  add     rsp, 28h
0x18000d111  retn
0x18000d113  lea     rcx, aYouMustPassThe; "You must pass the /WHOLEARCHIVE flag to"...
0x18000d11a  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
