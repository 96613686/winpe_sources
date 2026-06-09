# _CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$11

- ea: `0x140018d0a`
- end: `0x140018d16`
- name: `_CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$11`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000481c`

## pseudocode

```c
__int64 __fastcall CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor_11(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>::~ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>(a2 + 144);
}

```

## disassembly

```asm
0x140018d0a  lea     rcx, [rdx+90h]
0x140018d11  jmp     ??1?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>::~ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>(void)
```
