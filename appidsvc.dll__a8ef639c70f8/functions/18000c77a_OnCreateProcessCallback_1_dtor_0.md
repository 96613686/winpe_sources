# _OnCreateProcessCallback_::_1_::dtor$0

- ea: `0x18000c77a`
- end: `0x18000c786`
- name: `_OnCreateProcessCallback_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006164`

## pseudocode

```c
void __fastcall OnCreateProcessCallback_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  std::unique_ptr<ON_CREATE_PROC_DATA>::~unique_ptr<ON_CREATE_PROC_DATA>((void ***)(a2 + 136));
}

```

## disassembly

```asm
0x18000c77a  lea     rcx, [rdx+88h]
0x18000c781  jmp     ??1?$unique_ptr@VON_CREATE_PROC_DATA@@U?$default_delete@VON_CREATE_PROC_DATA@@@std@@@std@@QEAA@XZ; std::unique_ptr<ON_CREATE_PROC_DATA>::~unique_ptr<ON_CREATE_PROC_DATA>(void)
```
