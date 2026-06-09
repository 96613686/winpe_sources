# _CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor$19

- ea: `0x140018d64`
- end: `0x140018d70`
- name: `_CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor$19`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000481c`

## pseudocode

```c
__int64 __fastcall CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor_19(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>::~ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>(a2 + 176);
}

```

## disassembly

```asm
0x140018d64  lea     rcx, [rdx+0B0h]
0x140018d6b  jmp     ??1?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>::~ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>(void)
```
