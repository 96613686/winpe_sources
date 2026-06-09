# GenericFailureRepair::assembleDescription(AttributeList *)

- ea: `0x18000b380`
- end: `0x18000b3c0`
- name: `?assembleDescription@GenericFailureRepair@@UEAAPEAGPEAVAttributeList@@@Z`
- size: `64`
- prototype: `unsigned __int16 *__fastcall(GenericFailureRepair *__hidden this, struct AttributeList *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000b380`
- `0x18000fa20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b39d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b39d`

## pseudocode

```c
unsigned __int16 *__fastcall GenericFailureRepair::assembleDescription(
        GenericFailureRepair *this,
        struct AttributeList *a2)
{
  void *v4; // rcx

  v4 = (void *)*((_QWORD *)this + 4);
  if ( (unsigned __int64)v4 >= 0x10000 )
    CoTaskMemFree(v4);
  *((_QWORD *)this + 4) = 123;
  return Repair::assembleDescription(this, a2);
}

```

## disassembly

```asm
0x18000b380  mov     [rsp+arg_0], rbx
0x18000b385  push    rdi
0x18000b386  sub     rsp, 20h
0x18000b38a  mov     rbx, rcx
0x18000b38d  mov     rdi, rdx
0x18000b390  mov     rcx, [rcx+20h]; pv
0x18000b394  cmp     rcx, 10000h
0x18000b39b  jb      short loc_18000B3A3
0x18000b39d  call    cs:__imp_CoTaskMemFree
0x18000b3a3  mov     rdx, rdi; struct AttributeList *
0x18000b3a6  mov     qword ptr [rbx+20h], 7Bh ; '{'
0x18000b3ae  mov     rcx, rbx; this
0x18000b3b1  mov     rbx, [rsp+28h+arg_0]
0x18000b3b6  add     rsp, 20h
0x18000b3ba  pop     rdi
0x18000b3bb  jmp     ?assembleDescription@Repair@@UEAAPEAGPEAVAttributeList@@@Z; Repair::assembleDescription(AttributeList *)
```
