# wificx::utils::GuidCreate(_GUID *)

- ea: `0x14004bf80`
- end: `0x14004bf96`
- name: `?GuidCreate@utils@wificx@@YAJPEAU_GUID@@@Z`
- size: `22`
- prototype: `__int64 __fastcall(wificx::utils *__hidden this, struct _GUID *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1400d44d8`

## import_xrefs

- `ntoskrnl!ExUuidCreate` at `0x14004bf84`
- `ntoskrnl!ExUuidCreate` at `0x14004bf84`

## pseudocode

```c
NTSTATUS __fastcall wificx::utils::GuidCreate(UUID *this, struct _GUID *a2)
{
  return ExUuidCreate(this);
}

```

## disassembly

```asm
0x14004bf80  sub     rsp, 28h
0x14004bf84  call    cs:__imp_ExUuidCreate
0x14004bf8b  nop     dword ptr [rax+rax+00h]
0x14004bf90  add     rsp, 28h
0x14004bf94  retn
```
