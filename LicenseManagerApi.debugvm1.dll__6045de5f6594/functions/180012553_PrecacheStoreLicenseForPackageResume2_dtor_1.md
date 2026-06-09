# PrecacheStoreLicenseForPackageResume2$dtor$1

- ea: `0x180012553`
- end: `0x18001255f`
- name: `PrecacheStoreLicenseForPackageResume2$dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006b58`

## pseudocode

```c
__int64 __fastcall PrecacheStoreLicenseForPackageResume2_dtor_1(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::~HandleT<RpcBindingHandleTraits>(a2 + 64);
}

```

## disassembly

```asm
0x180012553  lea     rcx, [rdx+40h]
0x18001255a  jmp     ??1?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::~HandleT<RpcBindingHandleTraits>(void)
```
