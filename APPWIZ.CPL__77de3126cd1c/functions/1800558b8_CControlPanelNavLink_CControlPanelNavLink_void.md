# CControlPanelNavLink::~CControlPanelNavLink(void)

- ea: `0x1800558b8`
- end: `0x1800558ed`
- name: `??1CControlPanelNavLink@@QEAA@XZ`
- size: `53`
- prototype: `void __fastcall(CControlPanelNavLink *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180055978`

## callees

- `0x1800558f4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800558c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800558cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800558c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800558cf`
- `USER32!DestroyIcon` at `0x1800558d9`
- `USER32!DestroyIcon` at `0x1800558d9`

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
0x1800558b8  push    rbx
0x1800558ba  sub     rsp, 20h
0x1800558be  mov     rbx, rcx
0x1800558c1  mov     rcx, [rcx+8]; pv
0x1800558c5  call    cs:__imp_CoTaskMemFree
0x1800558cb  mov     rcx, [rbx+10h]; pv
0x1800558cf  call    cs:__imp_CoTaskMemFree
0x1800558d5  mov     rcx, [rbx+18h]; hIcon
0x1800558d9  call    cs:__imp_DestroyIcon
0x1800558df  lea     rcx, [rbx+20h]; this
0x1800558e3  add     rsp, 20h
0x1800558e7  pop     rbx
0x1800558e8  jmp     ??1CControlPanelNavLinkCommand@@QEAA@XZ; CControlPanelNavLinkCommand::~CControlPanelNavLinkCommand(void)
```
