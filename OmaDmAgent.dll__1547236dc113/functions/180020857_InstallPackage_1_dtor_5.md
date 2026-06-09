# _InstallPackage_::_1_::dtor$5

- ea: `0x180020857`
- end: `0x180020863`
- name: `_InstallPackage_::_1_::dtor$5`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180015034`

## pseudocode

```c
__int64 __fastcall InstallPackage_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::~ComPtr<Windows::Foundation::IUriRuntimeClass>(a2 + 64);
}

```

## disassembly

```asm
0x180020857  lea     rcx, [rdx+40h]
0x18002085e  jmp     ??1?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::~ComPtr<Windows::Foundation::IUriRuntimeClass>(void)
```
