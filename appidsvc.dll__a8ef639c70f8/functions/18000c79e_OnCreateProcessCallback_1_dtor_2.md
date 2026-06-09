# _OnCreateProcessCallback_::_1_::dtor$2

- ea: `0x18000c79e`
- end: `0x18000c7aa`
- name: `_OnCreateProcessCallback_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006360`

## pseudocode

```c
void __fastcall OnCreateProcessCallback_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  RridCoUninitialize::~RridCoUninitialize((RridCoUninitialize *)(a2 + 272));
}

```

## disassembly

```asm
0x18000c79e  lea     rcx, [rdx+110h]; this
0x18000c7a5  jmp     ??1RridCoUninitialize@@QEAA@XZ; RridCoUninitialize::~RridCoUninitialize(void)
```
