# _InstallPackage_::_1_::dtor$2

- ea: `0x180020845`
- end: `0x180020851`
- name: `_InstallPackage_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180015034`

## pseudocode

```c
__int64 __fastcall InstallPackage_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::~ComPtr<Windows::Foundation::IUriRuntimeClass>(a2 + 72);
}

```

## disassembly

```asm
0x180020845  lea     rcx, [rdx+48h]
0x18002084c  jmp     ??1?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::~ComPtr<Windows::Foundation::IUriRuntimeClass>(void)
```
