# std::_List_node<std::pair<uint const,PresentTraceConsumerCore::MakeResidentStartData>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<uint const,PresentTraceConsumerCore::MakeResidentStartData>,void *>>>(std::allocator<std::_List_node<std::pair<uint const,PresentTraceConsumerCore::MakeResidentStartData>,void *>> &,std::_List_node<std::pair<uint const,PresentTraceConsumerCore::MakeResidentStartData>,void *> *)

- ea: `0x180016950`
- end: `0x180016984`
- name: `??$_Free_non_head@V?$allocator@U?$_List_node@U?$pair@$$CBIUMakeResidentStartData@PresentTraceConsumerCore@@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@$$CBIUMakeResidentStartData@PresentTraceConsumerCore@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBIUMakeResidentStartData@PresentTraceConsumerCore@@@std@@PEAX@std@@@1@PEAU01@@Z`
- size: `52`
- prototype: `void __fastcall(__int64, _QWORD **)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180017d0c`
- `0x180018128`
- `0x18001c67c`

## callees

- `0x18000b550`
- `0x180016950`

## pseudocode

```c
void __fastcall std::_List_node<std::pair<unsigned int const,PresentTraceConsumerCore::MakeResidentStartData>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<unsigned int const,PresentTraceConsumerCore::MakeResidentStartData>,void *>>>(
        __int64 a1,
        _QWORD **a2)
{
  _QWORD *v2; // rcx
  _QWORD *v3; // rbx

  *a2[1] = 0;
  v2 = *a2;
  if ( *a2 )
  {
    do
    {
      v3 = (_QWORD *)*v2;
      std::_Deallocate<16>(v2, 0x28u);
      v2 = v3;
    }
    while ( v3 );
  }
}

```

## disassembly

```asm
0x180016950  push    rbx
0x180016952  sub     rsp, 20h
0x180016956  mov     rax, [rdx+8]
0x18001695a  mov     qword ptr [rax], 0
0x180016961  mov     rcx, [rdx]
0x180016964  test    rcx, rcx
0x180016967  jz      short loc_18001697E
0x180016969  mov     rbx, [rcx]
0x18001696c  mov     edx, 28h ; '('
0x180016971  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180016976  mov     rcx, rbx
0x180016979  test    rbx, rbx
0x18001697c  jnz     short loc_180016969
0x18001697e  add     rsp, 20h
0x180016982  pop     rbx
0x180016983  retn
```
