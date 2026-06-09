# _CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor$13

- ea: `0x140018cf8`
- end: `0x140018d04`
- name: `_CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor$13`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000481c`

## pseudocode

```c
__int64 __fastcall CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor_13(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>::~ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>(a2 + 136);
}

```

## disassembly

```asm
0x140018cf8  lea     rcx, [rdx+88h]
0x140018cff  jmp     ??1?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>::~ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>(void)
```
