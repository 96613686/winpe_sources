# _CXMLComparison::SaveMVKeys_::_1_::dtor$0

- ea: `0x180011bdd`
- end: `0x180011be9`
- name: `_CXMLComparison::SaveMVKeys_::_1_::dtor$0`
- size: `12`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006d64`

## pseudocode

```c
_QWORD *__fastcall CXMLComparison::SaveMVKeys_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IClassFactory>::~ComPtr<IClassFactory>((_QWORD *)(a2 + 56));
}

```

## disassembly

```asm
0x180011bdd  lea     rcx, [rdx+38h]
0x180011be4  jmp     ??1?$ComPtr@UIClassFactory@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IClassFactory>::~ComPtr<IClassFactory>(void)
```
