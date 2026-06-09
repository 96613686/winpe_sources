# _InstallPackage_::_1_::dtor$11

- ea: `0x1800208b1`
- end: `0x1800208bd`
- name: `_InstallPackage_::_1_::dtor$11`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180015034`

## pseudocode

```c
__int64 __fastcall InstallPackage_::_1_::dtor_11(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::~ComPtr<Windows::Foundation::IUriRuntimeClass>(a2 + 104);
}

```

## disassembly

```asm
0x1800208b1  lea     rcx, [rdx+68h]
0x1800208b8  jmp     ??1?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::~ComPtr<Windows::Foundation::IUriRuntimeClass>(void)
```
