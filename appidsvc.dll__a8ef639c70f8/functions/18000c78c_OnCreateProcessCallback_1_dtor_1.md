# _OnCreateProcessCallback_::_1_::dtor$1

- ea: `0x18000c78c`
- end: `0x18000c798`
- name: `_OnCreateProcessCallback_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006144`

## pseudocode

```c
void __fastcall OnCreateProcessCallback_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  std::unique_ptr<_TP_WORK,tp_work_deleter>::~unique_ptr<_TP_WORK,tp_work_deleter>((struct _TP_WORK **)(a2 + 144));
}

```

## disassembly

```asm
0x18000c78c  lea     rcx, [rdx+90h]
0x18000c793  jmp     ??1?$unique_ptr@U_TP_WORK@@Utp_work_deleter@@@std@@QEAA@XZ; std::unique_ptr<_TP_WORK,tp_work_deleter>::~unique_ptr<_TP_WORK,tp_work_deleter>(void)
```
