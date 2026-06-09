# _CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$28

- ea: `0x140019b0d`
- end: `0x140019b19`
- name: `_CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$28`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400048f4`

## pseudocode

```c
__int64 __fastcall CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor_28(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>::~ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>(a2 + 224);
}

```

## disassembly

```asm
0x140019b0d  lea     rcx, [rdx+0E0h]
0x140019b14  jmp     ??1?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>::~ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>(void)
```
