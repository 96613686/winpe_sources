# _CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor$17

- ea: `0x140019afb`
- end: `0x140019b07`
- name: `_CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor$17`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400048f4`

## pseudocode

```c
__int64 __fastcall CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor_17(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>::~ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>(a2 + 184);
}

```

## disassembly

```asm
0x140019afb  lea     rcx, [rdx+0B8h]
0x140019b02  jmp     ??1?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>::~ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>(void)
```
