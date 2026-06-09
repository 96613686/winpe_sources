# _CSystemPopupWindow::_CreateSystemPopupWindow_::_1_::dtor$0

- ea: `0x1400098de`
- end: `0x1400098ea`
- name: `_CSystemPopupWindow::_CreateSystemPopupWindow_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400031c4`

## pseudocode

```c
_QWORD *__fastcall CSystemPopupWindow::_CreateSystemPopupWindow_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IPopupWindowFactory>::~ComPtr<IPopupWindowFactory>((_QWORD *)(a2 + 48));
}

```

## disassembly

```asm
0x1400098de  lea     rcx, [rdx+30h]
0x1400098e5  jmp     ??1?$ComPtr@UIPopupWindowFactory@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IPopupWindowFactory>::~ComPtr<IPopupWindowFactory>(void)
```
