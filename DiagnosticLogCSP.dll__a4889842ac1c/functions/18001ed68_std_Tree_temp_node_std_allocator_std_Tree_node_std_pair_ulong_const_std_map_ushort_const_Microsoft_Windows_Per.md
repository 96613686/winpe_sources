# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>(void)

- ea: `0x18001ed68`
- end: `0x18001ede5`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `125`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001f744`

## callees

- `0x180001bc8`
- `0x18001d484`
- `0x18001ed68`

## pseudocode

```c
void __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>(
        __int64 a1)
{
  __int64 v1; // rdi
  _QWORD *v3; // rbx
  void *v4; // rcx
  void *v5; // rcx

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 )
  {
    v3 = *(_QWORD **)(*(_QWORD *)(v1 + 40) + 8LL);
    while ( !*((_BYTE *)v3 + 25) )
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>>>(
        v1 + 40,
        v1 + 40,
        v3[2]);
      v4 = v3;
      v3 = (_QWORD *)*v3;
      operator delete(v4, 0x30u);
    }
    operator delete(*(void **)(v1 + 40), 0x30u);
  }
  v5 = *(void **)(a1 + 8);
  if ( v5 )
    operator delete(v5, 0x38u);
}

```

## disassembly

```asm
0x18001ed68  mov     [rsp+arg_0], rbx
0x18001ed6d  mov     [rsp+arg_8], rsi
0x18001ed72  push    rdi
0x18001ed73  sub     rsp, 20h
0x18001ed77  mov     rdi, [rcx+8]
0x18001ed7b  mov     rsi, rcx
0x18001ed7e  test    rdi, rdi
0x18001ed81  jz      short loc_18001EDC2
0x18001ed83  mov     rax, [rdi+28h]
0x18001ed87  mov     rbx, [rax+8]
0x18001ed8b  jmp     short loc_18001EDAE
0x18001ed8d  mov     r8, [rbx+10h]
0x18001ed91  lea     rdx, [rdi+28h]
0x18001ed95  lea     rcx, [rdi+28h]
0x18001ed99  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>>>(std::allocator<std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *)
0x18001ed9e  mov     rcx, rbx; void *
0x18001eda1  mov     edx, 30h ; '0'; unsigned __int64
0x18001eda6  mov     rbx, [rbx]
0x18001eda9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001edae  cmp     byte ptr [rbx+19h], 0
0x18001edb2  jz      short loc_18001ED8D
0x18001edb4  mov     rcx, [rdi+28h]; void *
0x18001edb8  mov     edx, 30h ; '0'; unsigned __int64
0x18001edbd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001edc2  mov     rcx, [rsi+8]; void *
0x18001edc6  test    rcx, rcx
0x18001edc9  jz      short loc_18001EDD5
0x18001edcb  mov     edx, 38h ; '8'; unsigned __int64
0x18001edd0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001edd5  mov     rbx, [rsp+28h+arg_0]
0x18001edda  mov     rsi, [rsp+28h+arg_8]
0x18001eddf  add     rsp, 20h
0x18001ede3  pop     rdi
0x18001ede4  retn
```
