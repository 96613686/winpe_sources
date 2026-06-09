# Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(void)

- ea: `0x140008368`
- end: `0x14000836d`
- name: `??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000ebf0`
- `0x14000ec92`
- `0x14000ecfe`
- `0x14000ed10`
- `0x14000ed34`
- `0x14000ed46`
- `0x14000edc4`

## callees

- `0x1400098dc`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(
        __int64 a1)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(a1);
}

```

## disassembly

```asm
0x140008368  jmp     ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
```
