# CNetworkExplorerFolder::AddRef(void)

- ea: `0x180005800`
- end: `0x180005810`
- name: `?AddRef@CNetworkExplorerFolder@@UEAAKXZ`
- size: `16`
- prototype: `unsigned int __fastcall(CNetworkExplorerFolder *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180009130`
- `0x180009140`
- `0x180009150`
- `0x180009160`
- `0x180009170`
- `0x180009180`
- `0x180009190`
- `0x1800091a0`

## callees

- `0x180010010`

## pseudocode

```c
__int64 __fastcall CNetworkExplorerFolder::AddRef(CNetworkExplorerFolder *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 8LL))(*((_QWORD *)this + 3));
}

```

## disassembly

```asm
0x180005800  mov     rcx, [rcx+18h]
0x180005804  mov     rax, [rcx]
0x180005807  mov     rax, [rax+8]
0x18000580b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
