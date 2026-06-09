# CNetworkExplorerFolder::Release(void)

- ea: `0x1800057e0`
- end: `0x1800057f0`
- name: `?Release@CNetworkExplorerFolder@@UEAAKXZ`
- size: `16`
- prototype: `unsigned int __fastcall(CNetworkExplorerFolder *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ae90`
- `0x18000aea0`
- `0x18000aeb0`
- `0x18000aec0`
- `0x18000aed0`
- `0x18000aee0`
- `0x18000aef0`
- `0x18000af00`

## callees

- `0x180010010`

## pseudocode

```c
__int64 __fastcall CNetworkExplorerFolder::Release(CNetworkExplorerFolder *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 16LL))(*((_QWORD *)this + 3));
}

```

## disassembly

```asm
0x1800057e0  mov     rcx, [rcx+18h]
0x1800057e4  mov     rax, [rcx]
0x1800057e7  mov     rax, [rax+10h]
0x1800057eb  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
