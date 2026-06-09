# _RfbShellFolderBase::CompareIDs_::_1_::dtor$0

- ea: `0x180018881`
- end: `0x18001888d`
- name: `_RfbShellFolderBase::CompareIDs_::_1_::dtor$0`
- size: `12`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800058c4`

## pseudocode

```c
_QWORD *__fastcall RfbShellFolderBase::CompareIDs_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IFileDialogEvents>::~ComPtr<IFileDialogEvents>((_QWORD *)(a2 + 112));
}

```

## disassembly

```asm
0x180018881  lea     rcx, [rdx+70h]
0x180018888  jmp     ??1?$ComPtr@UIFileDialogEvents@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IFileDialogEvents>::~ComPtr<IFileDialogEvents>(void)
```
