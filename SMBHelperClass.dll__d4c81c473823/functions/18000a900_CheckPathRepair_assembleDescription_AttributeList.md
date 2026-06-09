# CheckPathRepair::assembleDescription(AttributeList *)

- ea: `0x18000a900`
- end: `0x18000a958`
- name: `?assembleDescription@CheckPathRepair@@UEAAPEAGPEAVAttributeList@@@Z`
- size: `88`
- prototype: `unsigned __int16 *__fastcall(CheckPathRepair *__hidden this, struct AttributeList *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000a900`
- `0x18000d750`
- `0x18000fa20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a91d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a91d`

## string_xrefs

- `0x18000a923`: `PathCandidates`

## pseudocode

```c
unsigned __int16 *__fastcall CheckPathRepair::assembleDescription(CheckPathRepair *this, struct AttributeList *a2)
{
  void *v4; // rcx

  v4 = (void *)*((_QWORD *)this + 4);
  if ( (unsigned __int64)v4 >= 0x10000 )
    CoTaskMemFree(v4);
  *((_QWORD *)this + 4) = (-(__int64)((unsigned int)AttributeList::attributeExists(a2, L"PathCandidates") != 0)
                         & 0xFFFFFFFFFFFFFFF5uLL)
                        + 124;
  return Repair::assembleDescription(this, a2);
}

```

## disassembly

```asm
0x18000a900  mov     [rsp+arg_0], rbx
0x18000a905  push    rdi
0x18000a906  sub     rsp, 20h
0x18000a90a  mov     rbx, rcx
0x18000a90d  mov     rdi, rdx
0x18000a910  mov     rcx, [rcx+20h]; pv
0x18000a914  cmp     rcx, 10000h
0x18000a91b  jb      short loc_18000A923
0x18000a91d  call    cs:__imp_CoTaskMemFree
0x18000a923  lea     rdx, aPathcandidates; "PathCandidates"
0x18000a92a  mov     rcx, rdi; this
0x18000a92d  call    ?attributeExists@AttributeList@@QEAAHPEAG@Z; AttributeList::attributeExists(ushort *)
0x18000a932  neg     eax
0x18000a934  mov     rdx, rdi; struct AttributeList *
0x18000a937  sbb     rcx, rcx
0x18000a93a  and     rcx, 0FFFFFFFFFFFFFFF5h
0x18000a93e  add     rcx, 7Ch ; '|'
0x18000a942  mov     [rbx+20h], rcx
0x18000a946  mov     rcx, rbx; this
0x18000a949  mov     rbx, [rsp+28h+arg_0]
0x18000a94e  add     rsp, 20h
0x18000a952  pop     rdi
0x18000a953  jmp     ?assembleDescription@Repair@@UEAAPEAGPEAVAttributeList@@@Z; Repair::assembleDescription(AttributeList *)
```
