# _CSystemPopupWindow::_SetButtonsOnDialog_::_1_::dtor$2

- ea: `0x1400098f0`
- end: `0x1400098fc`
- name: `_CSystemPopupWindow::_SetButtonsOnDialog_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400031c4`

## pseudocode

```c
_QWORD *__fastcall CSystemPopupWindow::_SetButtonsOnDialog_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IPopupWindowFactory>::~ComPtr<IPopupWindowFactory>((_QWORD *)(a2 + 32));
}

```

## disassembly

```asm
0x1400098f0  lea     rcx, [rdx+20h]
0x1400098f7  jmp     ??1?$ComPtr@UIPopupWindowFactory@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IPopupWindowFactory>::~ComPtr<IPopupWindowFactory>(void)
```
