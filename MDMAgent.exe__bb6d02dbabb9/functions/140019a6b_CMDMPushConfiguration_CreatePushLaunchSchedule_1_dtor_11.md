# _CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$11

- ea: `0x140019a6b`
- end: `0x140019a77`
- name: `_CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$11`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400048f4`

## pseudocode

```c
__int64 __fastcall CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor_11(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>::~ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>(a2 + 144);
}

```

## disassembly

```asm
0x140019a6b  lea     rcx, [rdx+90h]
0x140019a72  jmp     ??1?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>::~ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>(void)
```
