# _UpdateWebDialogMetaTagContent_::_1_::dtor$1

- ea: `0x140013283`
- end: `0x14001328f`
- name: `_UpdateWebDialogMetaTagContent_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140003a80`

## pseudocode

```c
__int64 __fastcall UpdateWebDialogMetaTagContent_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IHTMLElement>::~ComPtr<IHTMLElement>((__int64 *)(a2 + 120));
}

```

## disassembly

```asm
0x140013283  lea     rcx, [rdx+78h]
0x14001328a  jmp     ??1?$ComPtr@UIHTMLElement@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IHTMLElement>::~ComPtr<IHTMLElement>(void)
```
