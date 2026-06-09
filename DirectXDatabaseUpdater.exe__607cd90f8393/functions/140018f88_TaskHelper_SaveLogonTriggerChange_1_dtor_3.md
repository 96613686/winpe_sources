# _TaskHelper::SaveLogonTriggerChange_::_1_::dtor$3

- ea: `0x140018f88`
- end: `0x140018f94`
- name: `_TaskHelper::SaveLogonTriggerChange_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1400136e0`

## pseudocode

```c
HRESULT __fastcall TaskHelper::SaveLogonTriggerChange_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return _variant_t::~_variant_t((VARIANTARG *)(a2 + 104));
}

```

## disassembly

```asm
0x140018f88  lea     rcx, [rdx+68h]; pvarg
0x140018f8f  jmp     ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
```
