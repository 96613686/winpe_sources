# _CSystemPopupWindow::_SetContentElement_::_1_::dtor$2

- ea: `0x140009938`
- end: `0x140009944`
- name: `_CSystemPopupWindow::_SetContentElement_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140007f04`

## pseudocode

```c
__int64 __fastcall CSystemPopupWindow::_SetContentElement_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return wistd::unique_ptr<DirectUI::Element,DuiDestroyer<DirectUI::Element>>::~unique_ptr<DirectUI::Element,DuiDestroyer<DirectUI::Element>>(a2 + 48);
}

```

## disassembly

```asm
0x140009938  lea     rcx, [rdx+30h]
0x14000993f  jmp     ??1?$unique_ptr@VElement@DirectUI@@U?$DuiDestroyer@VElement@DirectUI@@@@@wistd@@QEAA@XZ; wistd::unique_ptr<DirectUI::Element,DuiDestroyer<DirectUI::Element>>::~unique_ptr<DirectUI::Element,DuiDestroyer<DirectUI::Element>>(void)
```
