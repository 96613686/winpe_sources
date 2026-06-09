# CCommandHandler::SetSite(IUnknown *)

- ea: `0x18000b230`
- end: `0x18000b245`
- name: `?SetSite@CCommandHandler@@UEAAJPEAUIUnknown@@@Z`
- size: `21`
- prototype: `__int64 __fastcall(IUnknown **this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_Set` at `0x18000b238`
- `SHLWAPI!__imp_IUnknown_Set` at `0x18000b238`

## pseudocode

```c
__int64 __fastcall CCommandHandler::SetSite(IUnknown **this, struct IUnknown *a2)
{
  IUnknown_Set(this + 6, a2);
  return 0;
}

```

## disassembly

```asm
0x18000b230  sub     rsp, 28h
0x18000b234  add     rcx, 30h ; '0'; ppunk
0x18000b238  call    cs:__imp_IUnknown_Set
0x18000b23e  xor     eax, eax
0x18000b240  add     rsp, 28h
0x18000b244  retn
```
