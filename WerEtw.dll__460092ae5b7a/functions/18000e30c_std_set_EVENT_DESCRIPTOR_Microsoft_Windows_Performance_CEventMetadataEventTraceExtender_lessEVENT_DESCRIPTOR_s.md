# std::set<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>>::~set<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>>(void)

- ea: `0x18000e30c`
- end: `0x18000e35e`
- name: `??1?$set@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@@std@@QEAA@XZ`
- size: `82`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800282ab`
- `0x1800288f2`

## callees

- `0x180001894`
- `0x18000c564`
- `0x18000e30c`

## pseudocode

```c
void __fastcall std::set<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>>::~set<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>>(
        void **a1)
{
  _QWORD *v2; // rbx
  void *v3; // rcx

  v2 = (_QWORD *)*((_QWORD *)*a1 + 1);
  while ( !*((_BYTE *)v2 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>>>(
      (__int64)a1,
      (__int64)a1,
      v2[2]);
    v3 = v2;
    v2 = (_QWORD *)*v2;
    operator delete(v3);
  }
  operator delete(*a1);
}

```

## disassembly

```asm
0x18000e30c  mov     [rsp+arg_0], rbx
0x18000e311  push    rdi
0x18000e312  sub     rsp, 20h
0x18000e316  mov     rax, [rcx]
0x18000e319  mov     rdi, rcx
0x18000e31c  mov     rbx, [rax+8]
0x18000e320  jmp     short loc_18000E341
0x18000e322  mov     r8, [rbx+10h]
0x18000e326  mov     rdx, rdi
0x18000e329  mov     rcx, rdi
0x18000e32c  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>>>(std::allocator<std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *)
0x18000e331  mov     rcx, rbx; Block
0x18000e334  mov     edx, 30h ; '0'
0x18000e339  mov     rbx, [rbx]
0x18000e33c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e341  cmp     byte ptr [rbx+19h], 0
0x18000e345  jz      short loc_18000E322
0x18000e347  mov     rcx, [rdi]; Block
0x18000e34a  mov     edx, 30h ; '0'
0x18000e34f  mov     rbx, [rsp+28h+arg_0]
0x18000e354  add     rsp, 20h
0x18000e358  pop     rdi
0x18000e359  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
