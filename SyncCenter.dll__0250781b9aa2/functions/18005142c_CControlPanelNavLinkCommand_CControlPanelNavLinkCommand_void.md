# CControlPanelNavLinkCommand::~CControlPanelNavLinkCommand(void)

- ea: `0x18005142c`
- end: `0x180051467`
- name: `??1CControlPanelNavLinkCommand@@QEAA@XZ`
- size: `59`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800513f0`

## callees

- `0x180009940`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051439`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005144b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051439`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005144b`

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
  CZeroInitNew::operator delete(v3);
}

```

## disassembly

```asm
0x18005142c  push    rbx
0x18005142e  sub     rsp, 20h
0x180051432  mov     rbx, rcx
0x180051435  mov     rcx, [rcx+8]; pv
0x180051439  call    cs:__imp_CoTaskMemFree
0x18005143f  mov     rcx, [rbx+10h]; pv
0x180051443  mov     qword ptr [rbx+8], 0
0x18005144b  call    cs:__imp_CoTaskMemFree
0x180051451  mov     rcx, [rbx+28h]; lpMem
0x180051455  mov     qword ptr [rbx+10h], 0
0x18005145d  add     rsp, 20h
0x180051461  pop     rbx
0x180051462  jmp     ??3CZeroInitNew@@SAXPEAX@Z; CZeroInitNew::operator delete(void *)
```
