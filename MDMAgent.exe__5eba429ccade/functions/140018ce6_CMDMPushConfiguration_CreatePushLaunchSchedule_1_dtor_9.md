# _CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$9

- ea: `0x140018ce6`
- end: `0x140018cf2`
- name: `_CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$9`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000481c`

## pseudocode

```c
__int64 __fastcall CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor_9(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>::~ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>(a2 + 120);
}

```

## disassembly

```asm
0x140018ce6  lea     rcx, [rdx+78h]
0x140018ced  jmp     ??1?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>::~ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>(void)
```
