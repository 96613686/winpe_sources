# TSgMap<unsigned __int64 *,long (*)(void *,_GUID const &,void * *)>::~TSgMap<unsigned __int64 *,long (*)(void *,_GUID const &,void * *)>(void)

- ea: `0x1800085f8`
- end: `0x18000866b`
- name: `??1?$TSgMap@PEA_KP6AJPEAXAEBU_GUID@@PEAPEAX@Z@@UEAA@XZ`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180008920`

## callees

- `0x1800085f8`
- `0x18000969c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180008613`
- `KERNEL32!DeleteCriticalSection` at `0x180008613`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000863a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000864a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000863a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000864a`

## pseudocode

```c
void __fastcall TSgMap<unsigned __int64 *,long (*)(void *,_GUID const &,void * *)>::~TSgMap<unsigned __int64 *,long (*)(void *,_GUID const &,void * *)>(
        __int64 a1)
{
  _QWORD *v2; // rdi
  void *v3; // rcx

  *(_QWORD *)a1 = &TSgMap<unsigned __int64 *,long (*)(void *,_GUID const &,void * *)>::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  v2 = *(_QWORD **)(*(_QWORD *)(a1 + 8) + 8LL);
  while ( !*((_BYTE *)v2 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<_GUID>>::_Erase_tree<std::allocator<std::_Tree_node<_GUID,void *>>>(
      a1 + 8,
      a1 + 8,
      v2[2]);
    v3 = v2;
    v2 = (_QWORD *)*v2;
    free(v3);
  }
  free(*(void **)(a1 + 8));
  *(_QWORD *)(a1 + 8) = 19937;
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x1800085f8  mov     [rsp+arg_0], rbx
0x1800085fd  push    rdi
0x1800085fe  sub     rsp, 20h
0x180008602  lea     rax, ??_7?$TSgMap@PEA_KP6AJPEAXAEBU_GUID@@PEAPEAX@Z@@6B@; const TSgMap<unsigned __int64 *,long (*)(void *,_GUID const &,void * *)>::`vftable'
0x180008609  mov     rbx, rcx
0x18000860c  mov     [rcx], rax
0x18000860f  add     rcx, 18h; lpCriticalSection
0x180008613  call    cs:__imp_DeleteCriticalSection
0x180008619  mov     rax, [rbx+8]
0x18000861d  mov     rdi, [rax+8]
0x180008621  jmp     short loc_180008640
0x180008623  mov     r8, [rdi+10h]
0x180008627  lea     rdx, [rbx+8]
0x18000862b  lea     rcx, [rbx+8]
0x18000862f  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U_GUID@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U_GUID@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U_GUID@@PEAX@std@@@1@PEAU?$_Tree_node@U_GUID@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<_GUID>>::_Erase_tree<std::allocator<std::_Tree_node<_GUID,void *>>>(std::allocator<std::_Tree_node<_GUID,void *>> &,std::_Tree_node<_GUID,void *> *)
0x180008634  mov     rcx, rdi; Block
0x180008637  mov     rdi, [rdi]
0x18000863a  call    cs:__imp_free
0x180008640  cmp     byte ptr [rdi+19h], 0
0x180008644  jz      short loc_180008623
0x180008646  mov     rcx, [rbx+8]; Block
0x18000864a  call    cs:__imp_free
0x180008650  mov     qword ptr [rbx+8], 4DE1h
0x180008658  mov     qword ptr [rbx+10h], 0
0x180008660  mov     rbx, [rsp+28h+arg_0]
0x180008665  add     rsp, 20h
0x180008669  pop     rdi
0x18000866a  retn
```
