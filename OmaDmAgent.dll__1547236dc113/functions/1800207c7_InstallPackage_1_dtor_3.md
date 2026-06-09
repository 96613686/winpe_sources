# _InstallPackage_::_1_::dtor$3

- ea: `0x1800207c7`
- end: `0x1800207d3`
- name: `_InstallPackage_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180015034`

## pseudocode

```c
__int64 __fastcall InstallPackage_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::~ComPtr<Windows::Foundation::IUriRuntimeClass>(a2 + 88);
}

```

## disassembly

```asm
0x1800207c7  lea     rcx, [rdx+58h]
0x1800207ce  jmp     ??1?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::~ComPtr<Windows::Foundation::IUriRuntimeClass>(void)
```
