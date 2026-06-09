# CConflictPropsItemInfo::~CConflictPropsItemInfo(void)

- ea: `0x18003db20`
- end: `0x18003db70`
- name: `??1CConflictPropsItemInfo@@QEAA@XZ`
- size: `80`
- prototype: `void __fastcall(CConflictPropsItemInfo *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003dbf8`

## callees

- `0x180007f44`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db69`

## pseudocode

```c
void __fastcall CConflictPropsItemInfo::~CConflictPropsItemInfo(CConflictPropsItemInfo *this)
{
  SafeRelease<ISyncMgrSyncItemContainer>((__int64 *)this);
  CoTaskMemFree(*((LPVOID *)this + 1));
  CoTaskMemFree(*((LPVOID *)this + 2));
  CoTaskMemFree(*((LPVOID *)this + 3));
  CoTaskMemFree(*((LPVOID *)this + 4));
  CoTaskMemFree(*((LPVOID *)this + 5));
  CoTaskMemFree(*((LPVOID *)this + 6));
}

```

## disassembly

```asm
0x18003db20  push    rbx
0x18003db22  sub     rsp, 20h
0x18003db26  mov     rbx, rcx
0x18003db29  call    ??$SafeRelease@UISyncMgrSyncItemContainer@@@@YAXPEAPEAUISyncMgrSyncItemContainer@@@Z; SafeRelease<ISyncMgrSyncItemContainer>(ISyncMgrSyncItemContainer * *)
0x18003db2e  mov     rcx, [rbx+8]; pv
0x18003db32  call    cs:__imp_CoTaskMemFree
0x18003db38  mov     rcx, [rbx+10h]; pv
0x18003db3c  call    cs:__imp_CoTaskMemFree
0x18003db42  mov     rcx, [rbx+18h]; pv
0x18003db46  call    cs:__imp_CoTaskMemFree
0x18003db4c  mov     rcx, [rbx+20h]; pv
0x18003db50  call    cs:__imp_CoTaskMemFree
0x18003db56  mov     rcx, [rbx+28h]; pv
0x18003db5a  call    cs:__imp_CoTaskMemFree
0x18003db60  mov     rcx, [rbx+30h]
0x18003db64  add     rsp, 20h
0x18003db68  pop     rbx
0x18003db69  jmp     cs:__imp_CoTaskMemFree
```
