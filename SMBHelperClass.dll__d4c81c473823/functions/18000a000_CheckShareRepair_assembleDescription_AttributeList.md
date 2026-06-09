# CheckShareRepair::assembleDescription(AttributeList *)

- ea: `0x18000a000`
- end: `0x18000a057`
- name: `?assembleDescription@CheckShareRepair@@UEAAPEAGPEAVAttributeList@@@Z`
- size: `87`
- prototype: `unsigned __int16 *__fastcall(CheckShareRepair *__hidden this, struct AttributeList *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000a000`
- `0x18000d750`
- `0x18000fa20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a01d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a01d`

## pseudocode

```c
unsigned __int16 *__fastcall CheckShareRepair::assembleDescription(CheckShareRepair *this, struct AttributeList *a2)
{
  void *v4; // rcx

  v4 = (void *)*((_QWORD *)this + 4);
  if ( (unsigned __int64)v4 >= 0x10000 )
    CoTaskMemFree(v4);
  *((_QWORD *)this + 4) = (unsigned int)AttributeList::attributeExists(a2, L"ShareCandidates") != 0 ? 127LL : 122LL;
  return Repair::assembleDescription(this, a2);
}

```

## disassembly

```asm
0x18000a000  mov     [rsp+arg_0], rbx
0x18000a005  push    rdi
0x18000a006  sub     rsp, 20h
0x18000a00a  mov     rbx, rcx
0x18000a00d  mov     rdi, rdx
0x18000a010  mov     rcx, [rcx+20h]; pv
0x18000a014  cmp     rcx, 10000h
0x18000a01b  jb      short loc_18000A023
0x18000a01d  call    cs:__imp_CoTaskMemFree
0x18000a023  lea     rdx, aSharecandidate; "ShareCandidates"
0x18000a02a  mov     rcx, rdi; this
0x18000a02d  call    ?attributeExists@AttributeList@@QEAAHPEAG@Z; AttributeList::attributeExists(ushort *)
0x18000a032  neg     eax
0x18000a034  mov     rdx, rdi; struct AttributeList *
0x18000a037  sbb     rcx, rcx
0x18000a03a  and     ecx, 5
0x18000a03d  add     rcx, 7Ah ; 'z'
0x18000a041  mov     [rbx+20h], rcx
0x18000a045  mov     rcx, rbx; this
0x18000a048  mov     rbx, [rsp+28h+arg_0]
0x18000a04d  add     rsp, 20h
0x18000a051  pop     rdi
0x18000a052  jmp     ?assembleDescription@Repair@@UEAAPEAGPEAVAttributeList@@@Z; Repair::assembleDescription(AttributeList *)
```
