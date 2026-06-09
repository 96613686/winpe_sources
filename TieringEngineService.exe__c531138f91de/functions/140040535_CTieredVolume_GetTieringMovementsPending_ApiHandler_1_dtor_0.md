# _CTieredVolume::GetTieringMovementsPending_ApiHandler_::_1_::dtor$0

- ea: `0x140040535`
- end: `0x140040541`
- name: `_CTieredVolume::GetTieringMovementsPending_ApiHandler_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140005420`

## pseudocode

```c
void __fastcall CTieredVolume::GetTieringMovementsPending_ApiHandler_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CHResultImp::~CHResultImp((CHResultImp *)(a2 + 72));
}

```

## disassembly

```asm
0x140040535  lea     rcx, [rdx+48h]; this
0x14004053c  jmp     ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
```
