# Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>::~ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>(void)

- ea: `0x1400048f4`
- end: `0x1400048f9`
- name: `??1?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `16`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400198cd`
- `0x1400198df`
- `0x140019939`
- `0x140019981`
- `0x1400199db`
- `0x140019a47`
- `0x140019a59`
- `0x140019a6b`
- `0x140019aa1`
- `0x140019ab3`
- `0x140019ac5`
- `0x140019ad7`
- `0x140019ae9`
- `0x140019afb`
- `0x140019b0d`
- `0x140019bca`

## callees

- `0x140006098`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>::~ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>(
        __int64 a1)
{
  return Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(a1);
}

```

## disassembly

```asm
0x1400048f4  jmp     ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
```
