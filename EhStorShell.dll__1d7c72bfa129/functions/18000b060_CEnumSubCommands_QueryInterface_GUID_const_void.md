# CEnumSubCommands::QueryInterface(_GUID const &,void * *)

- ea: `0x18000b060`
- end: `0x18000b074`
- name: `?QueryInterface@CEnumSubCommands@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `20`
- prototype: `HRESULT __fastcall(CEnumSubCommands *this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `SHLWAPI!__imp_QISearch` at `0x18000b06d`

## pseudocode

```c
HRESULT __fastcall CEnumSubCommands::QueryInterface(CEnumSubCommands *this, const struct _GUID *a2, void **a3)
{
  return QISearch(this, (LPCQITAB)&`CEnumSubCommands::QueryInterface'::`2'::qit, a2, a3);
}

```

## disassembly

```asm
0x18000b060  mov     r9, r8
0x18000b063  mov     r8, rdx
0x18000b066  lea     rdx, ?qit@?1??QueryInterface@CEnumSubCommands@@UEAAJAEBU_GUID@@PEAPEAX@Z@4QBUQITAB@@B; QITAB const near * const `CEnumSubCommands::QueryInterface(_GUID const &,void * *)'::`2'::qit
0x18000b06d  jmp     cs:__imp_QISearch
```
