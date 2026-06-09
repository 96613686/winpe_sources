# MaxConnectionsRepair::assembleDescription(AttributeList *)

- ea: `0x18000b290`
- end: `0x18000b2d0`
- name: `?assembleDescription@MaxConnectionsRepair@@UEAAPEAGPEAVAttributeList@@@Z`
- size: `64`
- prototype: `unsigned __int16 *__fastcall(MaxConnectionsRepair *__hidden this, struct AttributeList *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000b290`
- `0x18000fa20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b2ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b2ad`

## pseudocode

```c
unsigned __int16 *__fastcall MaxConnectionsRepair::assembleDescription(
        MaxConnectionsRepair *this,
        struct AttributeList *a2)
{
  void *v4; // rcx

  v4 = (void *)*((_QWORD *)this + 4);
  if ( (unsigned __int64)v4 >= 0x10000 )
    CoTaskMemFree(v4);
  *((_QWORD *)this + 4) = 129;
  return Repair::assembleDescription(this, a2);
}

```

## disassembly

```asm
0x18000b290  mov     [rsp+arg_0], rbx
0x18000b295  push    rdi
0x18000b296  sub     rsp, 20h
0x18000b29a  mov     rbx, rcx
0x18000b29d  mov     rdi, rdx
0x18000b2a0  mov     rcx, [rcx+20h]; pv
0x18000b2a4  cmp     rcx, 10000h
0x18000b2ab  jb      short loc_18000B2B3
0x18000b2ad  call    cs:__imp_CoTaskMemFree
0x18000b2b3  mov     rdx, rdi; struct AttributeList *
0x18000b2b6  mov     qword ptr [rbx+20h], 81h
0x18000b2be  mov     rcx, rbx; this
0x18000b2c1  mov     rbx, [rsp+28h+arg_0]
0x18000b2c6  add     rsp, 20h
0x18000b2ca  pop     rdi
0x18000b2cb  jmp     ?assembleDescription@Repair@@UEAAPEAGPEAVAttributeList@@@Z; Repair::assembleDescription(AttributeList *)
```
