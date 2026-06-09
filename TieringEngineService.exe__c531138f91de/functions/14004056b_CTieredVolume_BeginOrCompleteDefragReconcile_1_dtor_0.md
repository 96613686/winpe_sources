# _CTieredVolume::BeginOrCompleteDefragReconcile_::_1_::dtor$0

- ea: `0x14004056b`
- end: `0x140040577`
- name: `_CTieredVolume::BeginOrCompleteDefragReconcile_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140005420`

## pseudocode

```c
void __fastcall CTieredVolume::BeginOrCompleteDefragReconcile_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CHResultImp::~CHResultImp((CHResultImp *)(a2 + 96));
}

```

## disassembly

```asm
0x14004056b  lea     rcx, [rdx+60h]; this
0x140040572  jmp     ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
```
