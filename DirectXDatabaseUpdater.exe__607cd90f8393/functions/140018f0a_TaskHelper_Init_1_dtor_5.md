# _TaskHelper::Init_::_1_::dtor$5

- ea: `0x140018f0a`
- end: `0x140018f16`
- name: `_TaskHelper::Init_::_1_::dtor$5`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x14001366c`

## pseudocode

```c
void __fastcall TaskHelper::Init_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  _bstr_t::~_bstr_t((_bstr_t *)(a2 + 448));
}

```

## disassembly

```asm
0x140018f0a  lea     rcx, [rdx+1C0h]; this
0x140018f11  jmp     ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
```
