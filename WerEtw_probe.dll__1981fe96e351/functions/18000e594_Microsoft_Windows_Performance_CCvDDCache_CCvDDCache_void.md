# Microsoft::Windows::Performance::CCvDDCache::~CCvDDCache(void)

- ea: `0x18000e594`
- end: `0x18000e657`
- name: `??1CCvDDCache@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `195`
- prototype: `void __fastcall(Microsoft::Windows::Performance::CCvDDCache *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000e6cc`
- `0x180028141`

## callees

- `0x180001894`
- `0x18000c46c`
- `0x18000c4c8`
- `0x18000c564`
- `0x18000e234`
- `0x18000e594`

## pseudocode

```c
void __fastcall Microsoft::Windows::Performance::CCvDDCache::~CCvDDCache(
        Microsoft::Windows::Performance::CCvDDCache *this)
{
  void **v1; // rdi
  _QWORD *v3; // rbx
  void *v4; // rcx
  _QWORD *v5; // rbx
  void *v6; // rcx

  v1 = (void **)((char *)this + 48);
  v3 = *(_QWORD **)(*((_QWORD *)this + 6) + 8LL);
  while ( !*((_BYTE *)v3 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<unsigned short const *>>::_Erase_tree<std::allocator<std::_Tree_node<unsigned short const *,void *>>>(
      v1,
      v1,
      v3[2]);
    v4 = v3;
    v3 = (_QWORD *)*v3;
    operator delete(v4);
  }
  operator delete(*v1);
  v5 = *(_QWORD **)(*((_QWORD *)this + 4) + 8LL);
  while ( !*((_BYTE *)v5 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>>>(
      (__int64)this + 32,
      (__int64)this + 32,
      v5[2]);
    v6 = v5;
    v5 = (_QWORD *)*v5;
    operator delete(v6);
  }
  operator delete(*((void **)this + 4));
  std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>(
    (char *)this + 16,
    (char *)this + 16,
    *(_QWORD *)(*((_QWORD *)this + 2) + 8LL));
  operator delete(*((void **)this + 2));
  std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::~list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>(this);
}

```

## disassembly

```asm
0x18000e594  push    rbx
0x18000e596  push    rsi
0x18000e597  push    rdi
0x18000e598  push    r14
0x18000e59a  sub     rsp, 28h
0x18000e59e  lea     rdi, [rcx+30h]
0x18000e5a2  mov     rsi, rcx
0x18000e5a5  mov     rax, [rdi]
0x18000e5a8  mov     r14d, 28h ; '('
0x18000e5ae  mov     rbx, [rax+8]
0x18000e5b2  jmp     short loc_18000E5D1
0x18000e5b4  mov     r8, [rbx+10h]
0x18000e5b8  mov     rdx, rdi
0x18000e5bb  mov     rcx, rdi
0x18000e5be  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@PEBGPEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@PEBG@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@PEBGPEAX@std@@@1@PEAU?$_Tree_node@PEBGPEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<ushort const *>>::_Erase_tree<std::allocator<std::_Tree_node<ushort const *,void *>>>(std::allocator<std::_Tree_node<ushort const *,void *>> &,std::_Tree_node<ushort const *,void *> *)
0x18000e5c3  mov     rcx, rbx; Block
0x18000e5c6  mov     rdx, r14
0x18000e5c9  mov     rbx, [rbx]
0x18000e5cc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e5d1  cmp     byte ptr [rbx+19h], 0
0x18000e5d5  jz      short loc_18000E5B4
0x18000e5d7  mov     rcx, [rdi]; Block
0x18000e5da  mov     rdx, r14
0x18000e5dd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e5e2  lea     rdi, [rsi+20h]
0x18000e5e6  mov     r14d, 30h ; '0'
0x18000e5ec  mov     rax, [rdi]
0x18000e5ef  mov     rbx, [rax+8]
0x18000e5f3  jmp     short loc_18000E612
0x18000e5f5  mov     r8, [rbx+10h]
0x18000e5f9  mov     rdx, rdi
0x18000e5fc  mov     rcx, rdi
0x18000e5ff  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>>>(std::allocator<std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *)
0x18000e604  mov     rcx, rbx; Block
0x18000e607  mov     rdx, r14
0x18000e60a  mov     rbx, [rbx]
0x18000e60d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e612  cmp     byte ptr [rbx+19h], 0
0x18000e616  jz      short loc_18000E5F5
0x18000e618  mov     rcx, [rdi]; Block
0x18000e61b  mov     rdx, r14
0x18000e61e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e623  lea     rbx, [rsi+10h]
0x18000e627  mov     r8, [rbx]
0x18000e62a  mov     rdx, rbx
0x18000e62d  mov     rcx, rbx
0x18000e630  mov     r8, [r8+8]
0x18000e634  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>(std::allocator<std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>> &,std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *> *)
0x18000e639  mov     rcx, [rbx]; Block
0x18000e63c  mov     edx, 38h ; '8'
0x18000e641  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e646  mov     rcx, rsi
0x18000e649  add     rsp, 28h
0x18000e64d  pop     r14
0x18000e64f  pop     rdi
0x18000e650  pop     rsi
0x18000e651  pop     rbx
0x18000e652  jmp     ??1?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@QEAA@XZ; std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::~list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>(void)
```
