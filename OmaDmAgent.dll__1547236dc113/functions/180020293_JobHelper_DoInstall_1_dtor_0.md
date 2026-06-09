# _JobHelper::DoInstall_::_1_::dtor$0

- ea: `0x180020293`
- end: `0x18002029f`
- name: `_JobHelper::DoInstall_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000bd00`

## pseudocode

```c
void __fastcall JobHelper::DoInstall_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  _SwJob::~_SwJob(*(_SwJob **)(a2 + 128));
}

```

## disassembly

```asm
0x180020293  mov     rcx, [rdx+80h]; this
0x18002029a  jmp     ??1_SwJob@@QEAA@XZ; _SwJob::~_SwJob(void)
```
