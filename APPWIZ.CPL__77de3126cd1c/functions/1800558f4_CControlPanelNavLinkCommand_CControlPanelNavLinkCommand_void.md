# CControlPanelNavLinkCommand::~CControlPanelNavLinkCommand(void)

- ea: `0x1800558f4`
- end: `0x18005592f`
- name: `??1CControlPanelNavLinkCommand@@QEAA@XZ`
- size: `59`
- prototype: `void __fastcall(CControlPanelNavLinkCommand *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800558b8`

## callees

- `0x180044bd8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055901`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055913`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055901`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055913`

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
0x1800558f4  push    rbx
0x1800558f6  sub     rsp, 20h
0x1800558fa  mov     rbx, rcx
0x1800558fd  mov     rcx, [rcx+8]; pv
0x180055901  call    cs:__imp_CoTaskMemFree
0x180055907  mov     rcx, [rbx+10h]; pv
0x18005590b  mov     qword ptr [rbx+8], 0
0x180055913  call    cs:__imp_CoTaskMemFree
0x180055919  mov     rcx, [rbx+28h]; lpMem
0x18005591d  mov     qword ptr [rbx+10h], 0
0x180055925  add     rsp, 20h
0x180055929  pop     rbx
0x18005592a  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
