# DuplicateNameRepair::assembleDescription(AttributeList *)

- ea: `0x18000b2e0`
- end: `0x18000b320`
- name: `?assembleDescription@DuplicateNameRepair@@UEAAPEAGPEAVAttributeList@@@Z`
- size: `64`
- prototype: `unsigned __int16 *__fastcall(DuplicateNameRepair *__hidden this, struct AttributeList *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000b2e0`
- `0x18000fa20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b2fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b2fd`

## pseudocode

```c
unsigned __int16 *__fastcall DuplicateNameRepair::assembleDescription(
        DuplicateNameRepair *this,
        struct AttributeList *a2)
{
  void *v4; // rcx

  v4 = (void *)*((_QWORD *)this + 4);
  if ( (unsigned __int64)v4 >= 0x10000 )
    CoTaskMemFree(v4);
  *((_QWORD *)this + 4) = 131;
  return Repair::assembleDescription(this, a2);
}

```

## disassembly

```asm
0x18000b2e0  mov     [rsp+arg_0], rbx
0x18000b2e5  push    rdi
0x18000b2e6  sub     rsp, 20h
0x18000b2ea  mov     rbx, rcx
0x18000b2ed  mov     rdi, rdx
0x18000b2f0  mov     rcx, [rcx+20h]; pv
0x18000b2f4  cmp     rcx, 10000h
0x18000b2fb  jb      short loc_18000B303
0x18000b2fd  call    cs:__imp_CoTaskMemFree
0x18000b303  mov     rdx, rdi; struct AttributeList *
0x18000b306  mov     qword ptr [rbx+20h], 83h
0x18000b30e  mov     rcx, rbx; this
0x18000b311  mov     rbx, [rsp+28h+arg_0]
0x18000b316  add     rsp, 20h
0x18000b31a  pop     rdi
0x18000b31b  jmp     ?assembleDescription@Repair@@UEAAPEAGPEAVAttributeList@@@Z; Repair::assembleDescription(AttributeList *)
```
