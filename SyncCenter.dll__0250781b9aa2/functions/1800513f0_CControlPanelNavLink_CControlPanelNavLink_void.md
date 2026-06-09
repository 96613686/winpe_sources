# CControlPanelNavLink::~CControlPanelNavLink(void)

- ea: `0x1800513f0`
- end: `0x180051425`
- name: `??1CControlPanelNavLink@@QEAA@XZ`
- size: `53`
- prototype: `void __fastcall(CControlPanelNavLink *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800514b0`

## callees

- `0x18005142c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800513fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051407`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800513fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051407`
- `USER32!DestroyIcon` at `0x180051411`
- `USER32!DestroyIcon` at `0x180051411`

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
0x1800513f0  push    rbx
0x1800513f2  sub     rsp, 20h
0x1800513f6  mov     rbx, rcx
0x1800513f9  mov     rcx, [rcx+8]; pv
0x1800513fd  call    cs:__imp_CoTaskMemFree
0x180051403  mov     rcx, [rbx+10h]; pv
0x180051407  call    cs:__imp_CoTaskMemFree
0x18005140d  mov     rcx, [rbx+18h]; hIcon
0x180051411  call    cs:__imp_DestroyIcon
0x180051417  lea     rcx, [rbx+20h]; this
0x18005141b  add     rsp, 20h
0x18005141f  pop     rbx
0x180051420  jmp     ??1CControlPanelNavLinkCommand@@QEAA@XZ; CControlPanelNavLinkCommand::~CControlPanelNavLinkCommand(void)
```
