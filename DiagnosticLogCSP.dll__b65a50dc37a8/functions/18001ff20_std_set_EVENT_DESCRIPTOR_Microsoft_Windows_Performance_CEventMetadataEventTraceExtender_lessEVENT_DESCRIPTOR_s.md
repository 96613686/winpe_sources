# std::set<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>>::~set<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>>(void)

- ea: `0x18001ff20`
- end: `0x18001ff72`
- name: `??1?$set@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@@std@@QEAA@XZ`
- size: `82`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180037a5c`
- `0x180038091`

## callees

- `0x180001bf8`
- `0x18001e41c`
- `0x18001ff20`

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
0x18001ff20  mov     [rsp+arg_0], rbx
0x18001ff25  push    rdi
0x18001ff26  sub     rsp, 20h
0x18001ff2a  mov     rax, [rcx]
0x18001ff2d  mov     rdi, rcx
0x18001ff30  mov     rbx, [rax+8]
0x18001ff34  jmp     short loc_18001FF55
0x18001ff36  mov     r8, [rbx+10h]
0x18001ff3a  mov     rdx, rdi
0x18001ff3d  mov     rcx, rdi
0x18001ff40  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>>>(std::allocator<std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *)
0x18001ff45  mov     rcx, rbx; void *
0x18001ff48  mov     edx, 30h ; '0'; unsigned __int64
0x18001ff4d  mov     rbx, [rbx]
0x18001ff50  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ff55  cmp     byte ptr [rbx+19h], 0
0x18001ff59  jz      short loc_18001FF36
0x18001ff5b  mov     rcx, [rdi]; void *
0x18001ff5e  mov     edx, 30h ; '0'; unsigned __int64
0x18001ff63  mov     rbx, [rsp+28h+arg_0]
0x18001ff68  add     rsp, 20h
0x18001ff6c  pop     rdi
0x18001ff6d  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
