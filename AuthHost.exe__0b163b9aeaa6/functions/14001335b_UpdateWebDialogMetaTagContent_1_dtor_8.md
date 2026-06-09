# _UpdateWebDialogMetaTagContent_::_1_::dtor$8

- ea: `0x14001335b`
- end: `0x140013367`
- name: `_UpdateWebDialogMetaTagContent_::_1_::dtor$8`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140003a80`

## pseudocode

```c
__int64 __fastcall UpdateWebDialogMetaTagContent_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IHTMLElement>::~ComPtr<IHTMLElement>((__int64 *)(a2 + 88));
}

```

## disassembly

```asm
0x14001335b  lea     rcx, [rdx+58h]
0x140013362  jmp     ??1?$ComPtr@UIHTMLElement@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IHTMLElement>::~ComPtr<IHTMLElement>(void)
```
