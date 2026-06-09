# Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(void)

- ea: `0x140009e48`
- end: `0x140009e4d`
- name: `??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `20`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001137a`
- `0x14001138c`
- `0x14001139e`
- `0x140011496`
- `0x1400114fb`
- `0x14001150d`
- `0x14001151f`
- `0x1400115c0`
- `0x1400115d2`
- `0x14001162c`
- `0x140011662`
- `0x140011686`
- `0x1400116bc`
- `0x1400116e0`
- `0x140011794`
- `0x1400117b8`
- `0x140011813`
- `0x1400118e9`
- `0x140011915`
- `0x1400119f5`

## callees

- `0x14000d49c`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(
        __int64 a1)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(a1);
}

```

## disassembly

```asm
0x140009e48  jmp     ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
```
