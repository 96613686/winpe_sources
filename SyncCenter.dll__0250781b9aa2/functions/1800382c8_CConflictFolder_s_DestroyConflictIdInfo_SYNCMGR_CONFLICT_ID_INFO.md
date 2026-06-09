# CConflictFolder::s_DestroyConflictIdInfo(SYNCMGR_CONFLICT_ID_INFO *)

- ea: `0x1800382c8`
- end: `0x1800382fd`
- name: `?s_DestroyConflictIdInfo@CConflictFolder@@CAXPEAUSYNCMGR_CONFLICT_ID_INFO@@@Z`
- size: `53`
- prototype: `void __fastcall(struct SYNCMGR_CONFLICT_ID_INFO *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180037914`
- `0x180038304`

## callees

- `0x1800382c8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800382d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800382e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800382d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800382e9`

## pseudocode

```c
void __fastcall CConflictFolder::s_DestroyConflictIdInfo(struct SYNCMGR_CONFLICT_ID_INFO *a1)
{
  BYTE_BLOB *pblobExtra; // rcx

  if ( a1 )
  {
    CoTaskMemFree(a1->pblobID);
    pblobExtra = a1->pblobExtra;
    a1->pblobID = 0;
    CoTaskMemFree(pblobExtra);
    a1->pblobExtra = 0;
  }
}

```

## disassembly

```asm
0x1800382c8  test    rcx, rcx
0x1800382cb  jz      short locret_1800382FC
0x1800382cd  push    rbx
0x1800382ce  sub     rsp, 20h
0x1800382d2  mov     rbx, rcx
0x1800382d5  mov     rcx, [rcx]; pv
0x1800382d8  call    cs:__imp_CoTaskMemFree
0x1800382de  mov     rcx, [rbx+8]; pv
0x1800382e2  mov     qword ptr [rbx], 0
0x1800382e9  call    cs:__imp_CoTaskMemFree
0x1800382ef  mov     qword ptr [rbx+8], 0
0x1800382f7  add     rsp, 20h
0x1800382fb  pop     rbx
0x1800382fc  retn
```
