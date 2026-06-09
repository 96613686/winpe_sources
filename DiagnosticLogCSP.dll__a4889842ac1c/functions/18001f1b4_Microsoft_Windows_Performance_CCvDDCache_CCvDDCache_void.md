# Microsoft::Windows::Performance::CCvDDCache::~CCvDDCache(void)

- ea: `0x18001f1b4`
- end: `0x18001f277`
- name: `??1CCvDDCache@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `195`
- prototype: `void __fastcall(Microsoft::Windows::Performance::CCvDDCache *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001f2ec`
- `0x18003612e`

## callees

- `0x180001bc8`
- `0x18001d38c`
- `0x18001d3e8`
- `0x18001d484`
- `0x18001ee54`
- `0x18001f1b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
    operator delete(v4, 0x28u);
  }
  operator delete(*v1, 0x28u);
  v5 = *(_QWORD **)(*((_QWORD *)this + 4) + 8LL);
  while ( !*((_BYTE *)v5 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>>>(
      (__int64)this + 32,
      (__int64)this + 32,
      v5[2]);
    v6 = v5;
    v5 = (_QWORD *)*v5;
    operator delete(v6, 0x30u);
  }
  operator delete(*((void **)this + 4), 0x30u);
  std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>(
    (__int64)this + 16,
    (__int64)this + 16,
    *(_QWORD *)(*((_QWORD *)this + 2) + 8LL));
  operator delete(*((void **)this + 2), 0x38u);
  std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::~list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>((void **)this);
}

```

## disassembly

```asm
0x18001f1b4  push    rbx
0x18001f1b6  push    rsi
0x18001f1b7  push    rdi
0x18001f1b8  push    r14
0x18001f1ba  sub     rsp, 28h
0x18001f1be  lea     rdi, [rcx+30h]
0x18001f1c2  mov     rsi, rcx
0x18001f1c5  mov     rax, [rdi]
0x18001f1c8  mov     r14d, 28h ; '('
0x18001f1ce  mov     rbx, [rax+8]
0x18001f1d2  jmp     short loc_18001F1F1
0x18001f1d4  mov     r8, [rbx+10h]
0x18001f1d8  mov     rdx, rdi
0x18001f1db  mov     rcx, rdi
0x18001f1de  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@PEBGPEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@PEBG@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@PEBGPEAX@std@@@1@PEAU?$_Tree_node@PEBGPEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<ushort const *>>::_Erase_tree<std::allocator<std::_Tree_node<ushort const *,void *>>>(std::allocator<std::_Tree_node<ushort const *,void *>> &,std::_Tree_node<ushort const *,void *> *)
0x18001f1e3  mov     rcx, rbx; void *
0x18001f1e6  mov     rdx, r14; unsigned __int64
0x18001f1e9  mov     rbx, [rbx]
0x18001f1ec  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f1f1  cmp     byte ptr [rbx+19h], 0
0x18001f1f5  jz      short loc_18001F1D4
0x18001f1f7  mov     rcx, [rdi]; void *
0x18001f1fa  mov     rdx, r14; unsigned __int64
0x18001f1fd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f202  lea     rdi, [rsi+20h]
0x18001f206  mov     r14d, 30h ; '0'
0x18001f20c  mov     rax, [rdi]
0x18001f20f  mov     rbx, [rax+8]
0x18001f213  jmp     short loc_18001F232
0x18001f215  mov     r8, [rbx+10h]
0x18001f219  mov     rdx, rdi
0x18001f21c  mov     rcx, rdi
0x18001f21f  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>>>(std::allocator<std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *)
0x18001f224  mov     rcx, rbx; void *
0x18001f227  mov     rdx, r14; unsigned __int64
0x18001f22a  mov     rbx, [rbx]
0x18001f22d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f232  cmp     byte ptr [rbx+19h], 0
0x18001f236  jz      short loc_18001F215
0x18001f238  mov     rcx, [rdi]; void *
0x18001f23b  mov     rdx, r14; unsigned __int64
0x18001f23e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f243  lea     rbx, [rsi+10h]
0x18001f247  mov     r8, [rbx]
0x18001f24a  mov     rdx, rbx
0x18001f24d  mov     rcx, rbx
0x18001f250  mov     r8, [r8+8]
0x18001f254  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>(std::allocator<std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>> &,std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *> *)
0x18001f259  mov     rcx, [rbx]; void *
0x18001f25c  mov     edx, 38h ; '8'; unsigned __int64
0x18001f261  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f266  mov     rcx, rsi
0x18001f269  add     rsp, 28h
0x18001f26d  pop     r14
0x18001f26f  pop     rdi
0x18001f270  pop     rsi
0x18001f271  pop     rbx
0x18001f272  jmp     ??1?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@QEAA@XZ; std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::~list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>(void)
```
