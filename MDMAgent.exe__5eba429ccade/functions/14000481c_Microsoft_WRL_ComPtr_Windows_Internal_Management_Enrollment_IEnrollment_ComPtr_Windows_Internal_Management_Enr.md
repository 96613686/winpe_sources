# Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>::~ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>(void)

- ea: `0x14000481c`
- end: `0x140004821`
- name: `??1?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `16`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140018b6c`
- `0x140018b7e`
- `0x140018bd8`
- `0x140018c20`
- `0x140018c7a`
- `0x140018ce6`
- `0x140018cf8`
- `0x140018d0a`
- `0x140018d40`
- `0x140018d52`
- `0x140018d64`
- `0x140018d76`
- `0x140018d88`
- `0x140018d9a`
- `0x140018dac`
- `0x140018e69`

## callees

- `0x140005e94`

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
0x14000481c  jmp     ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
```
