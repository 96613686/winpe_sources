# PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)

- ea: `0x18000c06c`
- end: `0x18000c093`
- name: `?FreeStalePrintJobInfo@PrintJobCleanUpUtil@@YAXPEAUStalePrintJobInfo@1@@Z`
- size: `39`
- prototype: `void __fastcall(LPVOID *this, struct PrintJobCleanUpUtil::StalePrintJobInfo *)`
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008074`
- `0x18000fe1c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c078`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c078`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall PrintJobCleanUpUtil::FreeStalePrintJobInfo(
        LPVOID *this,
        struct PrintJobCleanUpUtil::StalePrintJobInfo *a2)
{
  CoTaskMemFree(*this);
  *this = 0;
  this[1] = 0;
}

```

## disassembly

```asm
0x18000c06c  push    rbx
0x18000c06e  sub     rsp, 20h
0x18000c072  mov     rbx, rcx
0x18000c075  mov     rcx, [rcx]; pv
0x18000c078  call    cs:__imp_CoTaskMemFree
0x18000c07e  mov     qword ptr [rbx], 0
0x18000c085  mov     qword ptr [rbx+8], 0
0x18000c08d  add     rsp, 20h
0x18000c091  pop     rbx
0x18000c092  retn
```
