# _CTieredVolume::UpdateTieringInformationFromVolume_::_1_::dtor$3

- ea: `0x140040559`
- end: `0x140040565`
- name: `_CTieredVolume::UpdateTieringInformationFromVolume_::_1_::dtor$3`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x14000be6c`

## pseudocode

```c
__int64 __fastcall CTieredVolume::UpdateTieringInformationFromVolume_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return CAutoTearDown__lambda_e7db9997110632555d662c145a93a2b8___::_CAutoTearDown__lambda_e7db9997110632555d662c145a93a2b8___(a2 + 112);
}

```

## disassembly

```asm
0x140040559  lea     rcx, [rdx+70h]
0x140040560  jmp     CAutoTearDown__lambda_e7db9997110632555d662c145a93a2b8______CAutoTearDown__lambda_e7db9997110632555d662c145a93a2b8___
```
