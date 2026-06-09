# _CSystemPopupWindow::_SetButtonsOnDialog_::_1_::dtor$1

- ea: `0x140009902`
- end: `0x14000990e`
- name: `_CSystemPopupWindow::_SetButtonsOnDialog_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400031c4`

## pseudocode

```c
_QWORD *__fastcall CSystemPopupWindow::_SetButtonsOnDialog_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IPopupWindowFactory>::~ComPtr<IPopupWindowFactory>((_QWORD *)(a2 + 40));
}

```

## disassembly

```asm
0x140009902  lea     rcx, [rdx+28h]
0x140009909  jmp     ??1?$ComPtr@UIPopupWindowFactory@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IPopupWindowFactory>::~ComPtr<IPopupWindowFactory>(void)
```
