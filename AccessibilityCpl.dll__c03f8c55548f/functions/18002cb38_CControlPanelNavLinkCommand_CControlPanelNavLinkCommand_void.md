# CControlPanelNavLinkCommand::~CControlPanelNavLinkCommand(void)

- ea: `0x18002cb38`
- end: `0x18002cb73`
- name: `??1CControlPanelNavLinkCommand@@QEAA@XZ`
- size: `59`
- prototype: `void __fastcall(CControlPanelNavLinkCommand *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18002cafc`

## callees

- `0x180003178`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cb45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cb57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cb45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cb57`

## pseudocode

```c
void __fastcall CControlPanelNavLinkCommand::~CControlPanelNavLinkCommand(LPVOID *this)
{
  void *v2; // rcx
  void *v3; // rcx

  CoTaskMemFree(this[1]);
  v2 = this[2];
  this[1] = 0;
  CoTaskMemFree(v2);
  v3 = this[5];
  this[2] = 0;
  operator delete(v3);
}

```

## disassembly

```asm
0x18002cb38  push    rbx
0x18002cb3a  sub     rsp, 20h
0x18002cb3e  mov     rbx, rcx
0x18002cb41  mov     rcx, [rcx+8]; pv
0x18002cb45  call    cs:__imp_CoTaskMemFree
0x18002cb4b  mov     rcx, [rbx+10h]; pv
0x18002cb4f  mov     qword ptr [rbx+8], 0
0x18002cb57  call    cs:__imp_CoTaskMemFree
0x18002cb5d  mov     rcx, [rbx+28h]; lpMem
0x18002cb61  mov     qword ptr [rbx+10h], 0
0x18002cb69  add     rsp, 20h
0x18002cb6d  pop     rbx
0x18002cb6e  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
