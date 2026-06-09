# Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IShellExperienceManagerFactory>::operator&(void)

- ea: `0x18000cdf4`
- end: `0x18000ce1b`
- name: `??I?$ComPtr@UIShellExperienceManagerFactory@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA?AV?$ComPtrRef@V?$ComPtr@UIShellExperienceManagerFactory@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@@Details@12@XZ`
- size: `39`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000c464`
- `0x180012960`
- `0x180013bd0`
- `0x1800148f8`
- `0x180014df0`

## callees

- `0x18000bf70`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IShellExperienceManagerFactory>::operator&(
        __int64 a1,
        __int64 a2)
{
  Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IInspectable>>::ComPtrRef<Microsoft::WRL::ComPtr<IInspectable>>(
    a2,
    a1);
  return a2;
}

```

## disassembly

```asm
0x18000cdf4  mov     [rsp+arg_8], rdx
0x18000cdf9  mov     [rsp+arg_0], rcx
0x18000cdfe  sub     rsp, 28h
0x18000ce02  mov     rdx, [rsp+28h+arg_0]
0x18000ce07  mov     rcx, [rsp+28h+arg_8]
0x18000ce0c  call    ??0?$ComPtrRef@V?$ComPtr@UIInspectable@@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@PEAV?$ComPtr@UIInspectable@@@23@@Z; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IInspectable>>::ComPtrRef<Microsoft::WRL::ComPtr<IInspectable>>(Microsoft::WRL::ComPtr<IInspectable> *)
0x18000ce11  mov     rax, [rsp+28h+arg_8]
0x18000ce16  add     rsp, 28h
0x18000ce1a  retn
```
