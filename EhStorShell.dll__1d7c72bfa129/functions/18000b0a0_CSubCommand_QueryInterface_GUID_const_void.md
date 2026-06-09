# CSubCommand::QueryInterface(_GUID const &,void * *)

- ea: `0x18000b0a0`
- end: `0x18000b0b4`
- name: `?QueryInterface@CSubCommand@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `20`
- prototype: `HRESULT __fastcall(CSubCommand *this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `SHLWAPI!__imp_QISearch` at `0x18000b0ad`

## pseudocode

```c
HRESULT __fastcall CSubCommand::QueryInterface(CSubCommand *this, const struct _GUID *a2, void **a3)
{
  return QISearch(this, (LPCQITAB)&`CSubCommand::QueryInterface'::`2'::qit, a2, a3);
}

```

## disassembly

```asm
0x18000b0a0  mov     r9, r8
0x18000b0a3  mov     r8, rdx
0x18000b0a6  lea     rdx, ?qit@?1??QueryInterface@CSubCommand@@UEAAJAEBU_GUID@@PEAPEAX@Z@4QBUQITAB@@B; QITAB const near * const `CSubCommand::QueryInterface(_GUID const &,void * *)'::`2'::qit
0x18000b0ad  jmp     cs:__imp_QISearch
```
