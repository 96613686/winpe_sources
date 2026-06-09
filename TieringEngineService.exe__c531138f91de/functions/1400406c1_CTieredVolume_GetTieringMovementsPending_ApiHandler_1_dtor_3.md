# _CTieredVolume::GetTieringMovementsPending_ApiHandler_::_1_::dtor$3

- ea: `0x1400406c1`
- end: `0x1400406cd`
- name: `_CTieredVolume::GetTieringMovementsPending_ApiHandler_::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x14002d3c4`

## pseudocode

```c
void __fastcall CTieredVolume::GetTieringMovementsPending_ApiHandler_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  std::unique_ptr<CTieredVolume::CSmartTieringMovementSession>::~unique_ptr<CTieredVolume::CSmartTieringMovementSession>((CTieredVolume::CSmartTieringMovementSession **)(a2 + 192));
}

```

## disassembly

```asm
0x1400406c1  lea     rcx, [rdx+0C0h]
0x1400406c8  jmp     ??1?$unique_ptr@VCSmartTieringMovementSession@CTieredVolume@@U?$default_delete@VCSmartTieringMovementSession@CTieredVolume@@@std@@@std@@QEAA@XZ; std::unique_ptr<CTieredVolume::CSmartTieringMovementSession>::~unique_ptr<CTieredVolume::CSmartTieringMovementSession>(void)
```
