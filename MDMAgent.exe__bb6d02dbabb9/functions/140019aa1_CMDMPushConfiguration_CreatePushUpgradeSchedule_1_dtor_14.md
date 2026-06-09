# _CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor$14

- ea: `0x140019aa1`
- end: `0x140019aad`
- name: `_CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor$14`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400048f4`

## pseudocode

```c
__int64 __fastcall CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor_14(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>::~ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>(a2 + 152);
}

```

## disassembly

```asm
0x140019aa1  lea     rcx, [rdx+98h]
0x140019aa8  jmp     ??1?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>::~ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>(void)
```
