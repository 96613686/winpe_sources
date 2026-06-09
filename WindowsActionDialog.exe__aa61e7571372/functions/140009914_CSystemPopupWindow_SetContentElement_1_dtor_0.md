# _CSystemPopupWindow::_SetContentElement_::_1_::dtor$0

- ea: `0x140009914`
- end: `0x140009920`
- name: `_CSystemPopupWindow::_SetContentElement_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140007edc`

## pseudocode

```c
void __fastcall CSystemPopupWindow::_SetContentElement_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  wistd::unique_ptr<DirectUI::DUIXmlParser,DuiDestroyer<DirectUI::DUIXmlParser>>::~unique_ptr<DirectUI::DUIXmlParser,DuiDestroyer<DirectUI::DUIXmlParser>>((DirectUI::DUIXmlParser **)(a2 + 56));
}

```

## disassembly

```asm
0x140009914  lea     rcx, [rdx+38h]
0x14000991b  jmp     ??1?$unique_ptr@VDUIXmlParser@DirectUI@@U?$DuiDestroyer@VDUIXmlParser@DirectUI@@@@@wistd@@QEAA@XZ; wistd::unique_ptr<DirectUI::DUIXmlParser,DuiDestroyer<DirectUI::DUIXmlParser>>::~unique_ptr<DirectUI::DUIXmlParser,DuiDestroyer<DirectUI::DUIXmlParser>>(void)
```
