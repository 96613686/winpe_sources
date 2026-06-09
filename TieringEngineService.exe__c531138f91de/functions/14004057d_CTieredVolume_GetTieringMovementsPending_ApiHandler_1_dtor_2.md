# _CTieredVolume::GetTieringMovementsPending_ApiHandler_::_1_::dtor$2

- ea: `0x14004057d`
- end: `0x140040589`
- name: `_CTieredVolume::GetTieringMovementsPending_ApiHandler_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x14001e2d4`

## pseudocode

```c
void __fastcall CTieredVolume::GetTieringMovementsPending_ApiHandler_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  TieringPinnedSession::~TieringPinnedSession((TieringPinnedSession *)(a2 + 128));
}

```

## disassembly

```asm
0x14004057d  lea     rcx, [rdx+80h]; this
0x140040584  jmp     ??1TieringPinnedSession@@QEAA@XZ; TieringPinnedSession::~TieringPinnedSession(void)
```
