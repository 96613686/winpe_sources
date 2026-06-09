# _CONFIG_HISTORY::Initialize_::_1_::dtor$0

- ea: `0x180009090`
- end: `0x18000909c`
- name: `_CONFIG_HISTORY::Initialize_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callees

- `0x180001048`

## pseudocode

```c
void __fastcall CONFIG_HISTORY::Initialize_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 72));
}

```

## disassembly

```asm
0x180009090  mov     rcx, [rdx+48h]; Block
0x180009097  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
