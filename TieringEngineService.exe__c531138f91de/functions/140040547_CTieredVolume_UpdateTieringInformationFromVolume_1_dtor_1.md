# _CTieredVolume::UpdateTieringInformationFromVolume_::_1_::dtor$1

- ea: `0x140040547`
- end: `0x140040553`
- name: `_CTieredVolume::UpdateTieringInformationFromVolume_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x14000be6c`

## pseudocode

```c
__int64 __fastcall CTieredVolume::UpdateTieringInformationFromVolume_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return CAutoTearDown__lambda_e7db9997110632555d662c145a93a2b8___::_CAutoTearDown__lambda_e7db9997110632555d662c145a93a2b8___(a2 + 104);
}

```

## disassembly

```asm
0x140040547  lea     rcx, [rdx+68h]
0x14004054e  jmp     CAutoTearDown__lambda_e7db9997110632555d662c145a93a2b8______CAutoTearDown__lambda_e7db9997110632555d662c145a93a2b8___
```
