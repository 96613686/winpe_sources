# _TaskHelper::Init_::_1_::dtor$0

- ea: `0x140018ec2`
- end: `0x140018ece`
- name: `_TaskHelper::Init_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1400136e0`

## pseudocode

```c
HRESULT __fastcall TaskHelper::Init_::_1_::dtor_0(__int64 a1, VARIANTARG *a2)
{
  return _variant_t::~_variant_t(a2 + 5);
}

```

## disassembly

```asm
0x140018ec2  lea     rcx, [rdx+78h]; pvarg
0x140018ec9  jmp     ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
```
