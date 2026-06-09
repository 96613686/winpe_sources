# CNetworkExplorerFolder::QueryInterface(_GUID const &,void * *)

- ea: `0x180005960`
- end: `0x18000596f`
- name: `?QueryInterface@CNetworkExplorerFolder@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `15`
- prototype: `__int64 __fastcall(CNetworkExplorerFolder *__hidden this, const struct _GUID *, void **)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18000acb0`
- `0x18000acc0`
- `0x18000acd0`
- `0x18000ace0`
- `0x18000acf0`
- `0x18000ad00`
- `0x18000ad10`
- `0x18000ad20`

## callees

- `0x180010010`

## pseudocode

```c
__int64 __fastcall CNetworkExplorerFolder::QueryInterface(
        CNetworkExplorerFolder *this,
        const struct _GUID *a2,
        void **a3)
{
  return (***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 3))(
           *((_QWORD *)this + 3),
           a2,
           a3);
}

```

## disassembly

```asm
0x180005960  mov     rcx, [rcx+18h]
0x180005964  mov     rax, [rcx]
0x180005967  mov     rax, [rax]
0x18000596a  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
