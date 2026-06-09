# CControlPanelNavLink::~CControlPanelNavLink(void)

- ea: `0x18002cafc`
- end: `0x18002cb31`
- name: `??1CControlPanelNavLink@@QEAA@XZ`
- size: `53`
- prototype: `void __fastcall(CControlPanelNavLink *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002cbf4`

## callees

- `0x18002cb38`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cb09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cb13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cb09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cb13`
- `USER32!DestroyIcon` at `0x18002cb1d`
- `USER32!DestroyIcon` at `0x18002cb1d`

## pseudocode

```c
void __fastcall CControlPanelNavLink::~CControlPanelNavLink(CControlPanelNavLink *this)
{
  CoTaskMemFree(*((LPVOID *)this + 1));
  CoTaskMemFree(*((LPVOID *)this + 2));
  DestroyIcon(*((HICON *)this + 3));
  CControlPanelNavLinkCommand::~CControlPanelNavLinkCommand((CControlPanelNavLink *)((char *)this + 32));
}

```

## disassembly

```asm
0x18002cafc  push    rbx
0x18002cafe  sub     rsp, 20h
0x18002cb02  mov     rbx, rcx
0x18002cb05  mov     rcx, [rcx+8]; pv
0x18002cb09  call    cs:__imp_CoTaskMemFree
0x18002cb0f  mov     rcx, [rbx+10h]; pv
0x18002cb13  call    cs:__imp_CoTaskMemFree
0x18002cb19  mov     rcx, [rbx+18h]; hIcon
0x18002cb1d  call    cs:__imp_DestroyIcon
0x18002cb23  lea     rcx, [rbx+20h]; this
0x18002cb27  add     rsp, 20h
0x18002cb2b  pop     rbx
0x18002cb2c  jmp     ??1CControlPanelNavLinkCommand@@QEAA@XZ; CControlPanelNavLinkCommand::~CControlPanelNavLinkCommand(void)
```
