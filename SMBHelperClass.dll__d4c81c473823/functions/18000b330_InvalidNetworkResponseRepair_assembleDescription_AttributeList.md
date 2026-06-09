# InvalidNetworkResponseRepair::assembleDescription(AttributeList *)

- ea: `0x18000b330`
- end: `0x18000b370`
- name: `?assembleDescription@InvalidNetworkResponseRepair@@UEAAPEAGPEAVAttributeList@@@Z`
- size: `64`
- prototype: `unsigned __int16 *__fastcall(InvalidNetworkResponseRepair *__hidden this, struct AttributeList *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000b330`
- `0x18000fa20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b34d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b34d`

## pseudocode

```c
unsigned __int16 *__fastcall InvalidNetworkResponseRepair::assembleDescription(
        InvalidNetworkResponseRepair *this,
        struct AttributeList *a2)
{
  void *v4; // rcx

  v4 = (void *)*((_QWORD *)this + 4);
  if ( (unsigned __int64)v4 >= 0x10000 )
    CoTaskMemFree(v4);
  *((_QWORD *)this + 4) = 133;
  return Repair::assembleDescription(this, a2);
}

```

## disassembly

```asm
0x18000b330  mov     [rsp+arg_0], rbx
0x18000b335  push    rdi
0x18000b336  sub     rsp, 20h
0x18000b33a  mov     rbx, rcx
0x18000b33d  mov     rdi, rdx
0x18000b340  mov     rcx, [rcx+20h]; pv
0x18000b344  cmp     rcx, 10000h
0x18000b34b  jb      short loc_18000B353
0x18000b34d  call    cs:__imp_CoTaskMemFree
0x18000b353  mov     rdx, rdi; struct AttributeList *
0x18000b356  mov     qword ptr [rbx+20h], 85h
0x18000b35e  mov     rcx, rbx; this
0x18000b361  mov     rbx, [rsp+28h+arg_0]
0x18000b366  add     rsp, 20h
0x18000b36a  pop     rdi
0x18000b36b  jmp     ?assembleDescription@Repair@@UEAAPEAGPEAVAttributeList@@@Z; Repair::assembleDescription(AttributeList *)
```
