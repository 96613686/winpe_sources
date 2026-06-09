# _GetJsonFromUrl_::_1_::dtor$0

- ea: `0x1400116e0`
- end: `0x1400116ec`
- name: `_GetJsonFromUrl_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140009e48`

## pseudocode

```c
__int64 __fastcall GetJsonFromUrl_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(a2 + 88);
}

```

## disassembly

```asm
0x1400116e0  lea     rcx, [rdx+58h]
0x1400116e7  jmp     ??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(void)
```
