# _CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$20

- ea: `0x140019ae9`
- end: `0x140019af5`
- name: `_CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$20`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400048f4`

## pseudocode

```c
__int64 __fastcall CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor_20(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>::~ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>(a2 + 216);
}

```

## disassembly

```asm
0x140019ae9  lea     rcx, [rdx+0D8h]
0x140019af0  jmp     ??1?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>::~ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>(void)
```
