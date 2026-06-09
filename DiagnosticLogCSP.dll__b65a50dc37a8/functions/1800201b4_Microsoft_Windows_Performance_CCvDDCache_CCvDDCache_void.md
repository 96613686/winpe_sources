# Microsoft::Windows::Performance::CCvDDCache::~CCvDDCache(void)

- ea: `0x1800201b4`
- end: `0x180020277`
- name: `??1CCvDDCache@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `195`
- prototype: `void __fastcall(Microsoft::Windows::Performance::CCvDDCache *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800202fc`
- `0x1800378e0`

## callees

- `0x180001bf8`
- `0x18001e324`
- `0x18001e380`
- `0x18001e41c`
- `0x18001fe48`
- `0x1800201b4`

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
0x1800201b4  push    rbx
0x1800201b6  push    rsi
0x1800201b7  push    rdi
0x1800201b8  push    r14
0x1800201ba  sub     rsp, 28h
0x1800201be  lea     rdi, [rcx+30h]
0x1800201c2  mov     rsi, rcx
0x1800201c5  mov     rax, [rdi]
0x1800201c8  mov     r14d, 28h ; '('
0x1800201ce  mov     rbx, [rax+8]
0x1800201d2  jmp     short loc_1800201F1
0x1800201d4  mov     r8, [rbx+10h]
0x1800201d8  mov     rdx, rdi
0x1800201db  mov     rcx, rdi
0x1800201de  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@PEBGPEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@PEBG@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@PEBGPEAX@std@@@1@PEAU?$_Tree_node@PEBGPEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<ushort const *>>::_Erase_tree<std::allocator<std::_Tree_node<ushort const *,void *>>>(std::allocator<std::_Tree_node<ushort const *,void *>> &,std::_Tree_node<ushort const *,void *> *)
0x1800201e3  mov     rcx, rbx; void *
0x1800201e6  mov     rdx, r14; unsigned __int64
0x1800201e9  mov     rbx, [rbx]
0x1800201ec  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800201f1  cmp     byte ptr [rbx+19h], 0
0x1800201f5  jz      short loc_1800201D4
0x1800201f7  mov     rcx, [rdi]; void *
0x1800201fa  mov     rdx, r14; unsigned __int64
0x1800201fd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020202  lea     rdi, [rsi+20h]
0x180020206  mov     r14d, 30h ; '0'
0x18002020c  mov     rax, [rdi]
0x18002020f  mov     rbx, [rax+8]
0x180020213  jmp     short loc_180020232
0x180020215  mov     r8, [rbx+10h]
0x180020219  mov     rdx, rdi
0x18002021c  mov     rcx, rdi
0x18002021f  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>>>(std::allocator<std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *)
0x180020224  mov     rcx, rbx; void *
0x180020227  mov     rdx, r14; unsigned __int64
0x18002022a  mov     rbx, [rbx]
0x18002022d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020232  cmp     byte ptr [rbx+19h], 0
0x180020236  jz      short loc_180020215
0x180020238  mov     rcx, [rdi]; void *
0x18002023b  mov     rdx, r14; unsigned __int64
0x18002023e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020243  lea     rbx, [rsi+10h]
0x180020247  mov     r8, [rbx]
0x18002024a  mov     rdx, rbx
0x18002024d  mov     rcx, rbx
0x180020250  mov     r8, [r8+8]
0x180020254  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>(std::allocator<std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>> &,std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *> *)
0x180020259  mov     rcx, [rbx]; void *
0x18002025c  mov     edx, 38h ; '8'; unsigned __int64
0x180020261  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020266  mov     rcx, rsi
0x180020269  add     rsp, 28h
0x18002026d  pop     r14
0x18002026f  pop     rdi
0x180020270  pop     rsi
0x180020271  pop     rbx
0x180020272  jmp     ??1?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@QEAA@XZ; std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::~list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>(void)
```
