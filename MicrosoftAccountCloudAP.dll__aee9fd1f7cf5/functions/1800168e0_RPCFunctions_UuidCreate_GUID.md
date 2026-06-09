# RPCFunctions::UuidCreate(_GUID *)

- ea: `0x1800168e0`
- end: `0x1800168ea`
- name: `?UuidCreate@RPCFunctions@@UEAAJPEAU_GUID@@@Z`
- size: `10`
- prototype: `__int64 __fastcall(RPCFunctions *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1800168e3`

## pseudocode

```c
RPC_STATUS __fastcall RPCFunctions::UuidCreate(RPCFunctions *this, struct _GUID *a2)
{
  return UuidCreate(a2);
}

```

## disassembly

```asm
0x1800168e0  mov     rcx, rdx
0x1800168e3  jmp     cs:__imp_UuidCreate
```
