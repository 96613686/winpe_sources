# _CTieredVolume::GetTieringMovementsPending_ApiHandler_::_1_::dtor$1

- ea: `0x1400406af`
- end: `0x1400406bb`
- name: `_CTieredVolume::GetTieringMovementsPending_ApiHandler_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x14001e2d4`

## pseudocode

```c
void __fastcall CTieredVolume::GetTieringMovementsPending_ApiHandler_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  TieringPinnedSession::~TieringPinnedSession((TieringPinnedSession *)(a2 + 208));
}

```

## disassembly

```asm
0x1400406af  lea     rcx, [rdx+0D0h]; this
0x1400406b6  jmp     ??1TieringPinnedSession@@QEAA@XZ; TieringPinnedSession::~TieringPinnedSession(void)
```
