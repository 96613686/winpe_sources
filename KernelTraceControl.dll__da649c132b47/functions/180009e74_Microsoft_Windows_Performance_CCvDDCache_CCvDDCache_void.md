# Microsoft::Windows::Performance::CCvDDCache::~CCvDDCache(void)

- ea: `0x180009e74`
- end: `0x180009f76`
- name: `??1CCvDDCache@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `258`
- prototype: `void __fastcall(Microsoft::Windows::Performance::CCvDDCache *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000f658`
- `0x180027f6b`
- `0x180028396`

## callees

- `0x180009660`
- `0x180009e74`
- `0x18000d24c`
- `0x18000d2d0`
- `0x180010388`
- `0x1800268f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Microsoft::Windows::Performance::CCvDDCache::~CCvDDCache(
        Microsoft::Windows::Performance::CCvDDCache *this)
{
  char *v2; // rbp
  _QWORD *v3; // rdi
  _QWORD *i; // rbx
  _QWORD **v5; // rax
  _QWORD *v6; // rdi
  _QWORD *v7; // rbx

  v2 = (char *)this + 72;
  v3 = *(_QWORD **)(*((_QWORD *)this + 10) + 8LL);
  for ( i = v3; !*((_BYTE *)i + 33); v3 = i )
  {
    std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::_Erase(
      v2,
      i[2]);
    i = (_QWORD *)*i;
    operator delete(v3);
  }
  *(_QWORD *)(*((_QWORD *)v2 + 1) + 8LL) = *((_QWORD *)v2 + 1);
  *((_QWORD *)v2 + 2) = 0;
  **((_QWORD **)v2 + 1) = *((_QWORD *)v2 + 1);
  *(_QWORD *)(*((_QWORD *)v2 + 1) + 16LL) = *((_QWORD *)v2 + 1);
  operator delete(*((void **)v2 + 1));
  *((_QWORD *)v2 + 1) = 0;
  *((_QWORD *)v2 + 2) = 0;
  std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Tidy((__int64)this + 48);
  std::_Tree<std::_Tmap_traits<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>();
  v5 = (_QWORD **)*((_QWORD *)this + 1);
  v6 = *v5;
  *v5 = v5;
  *(_QWORD *)(*((_QWORD *)this + 1) + 8LL) = *((_QWORD *)this + 1);
  *((_QWORD *)this + 2) = 0;
  if ( v6 != *((_QWORD **)this + 1) )
  {
    do
    {
      v7 = (_QWORD *)*v6;
      Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD((Microsoft::Windows::Performance::CCvDDCache::CCvDD *)(v6 + 2));
      operator delete(v6);
      v6 = v7;
    }
    while ( v7 != *((_QWORD **)this + 1) );
  }
  operator delete(*((void **)this + 1));
  *((_QWORD *)this + 1) = 0;
}

```

## disassembly

```asm
0x180009e74  mov     rax, rsp
0x180009e77  mov     [rax+8], rcx
0x180009e7b  push    rbp
0x180009e7c  push    rsi
0x180009e7d  push    rdi
0x180009e7e  push    r14
0x180009e80  push    r15
0x180009e82  sub     rsp, 40h
0x180009e86  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180009e8e  mov     [rax+18h], rbx
0x180009e92  mov     r14, rcx
0x180009e95  lea     rbp, [rcx+48h]
0x180009e99  mov     [rsp+68h+arg_8], rbp
0x180009e9e  mov     rdi, [rbp+8]
0x180009ea2  xor     r15d, r15d
0x180009ea5  mov     rdi, [rdi+8]
0x180009ea9  mov     rbx, rdi
0x180009eac  cmp     [rdi+21h], r15b
0x180009eb0  jnz     short loc_180009ED2
0x180009eb2  mov     rdx, [rbx+10h]
0x180009eb6  mov     rcx, rbp
0x180009eb9  call    ?_Erase@?$_Tree@V?$_Tset_traits@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessCCvDDPtrByImageId@2345@V?$allocator@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tset_traits@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessCCvDDPtrByImageId@2345@V?$allocator@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@$0A@@std@@@2@@Z; std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::_Erase(std::_Tree_nod<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::_Node *)
0x180009ebe  mov     rbx, [rbx]
0x180009ec1  mov     rcx, rdi; Block
0x180009ec4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009ec9  mov     rdi, rbx
0x180009ecc  cmp     [rbx+21h], r15b
0x180009ed0  jz      short loc_180009EB2
0x180009ed2  mov     rax, [rbp+8]
0x180009ed6  mov     [rax+8], rax
0x180009eda  mov     [rbp+10h], r15
0x180009ede  mov     rax, [rbp+8]
0x180009ee2  mov     [rax], rax
0x180009ee5  mov     rax, [rbp+8]
0x180009ee9  mov     [rax+10h], rax
0x180009eed  mov     rcx, [rbp+8]; Block
0x180009ef1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009ef6  mov     [rbp+8], r15
0x180009efa  mov     [rbp+10h], r15
0x180009efe  lea     rcx, [r14+30h]
0x180009f02  mov     [rsp+68h+arg_8], rcx
0x180009f07  call    ?_Tidy@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Tidy(void)
0x180009f0c  nop
0x180009f0d  lea     rcx, [r14+18h]
0x180009f11  mov     [rsp+68h+arg_8], rcx
0x180009f16  call    ??1?$_Tree@V?$_Tmap_traits@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::~_Tree<std::_Tmap_traits<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>(void)
0x180009f1b  nop
0x180009f1c  mov     rax, [r14+8]
0x180009f20  mov     rdi, [rax]
0x180009f23  mov     [rax], rax
0x180009f26  mov     rax, [r14+8]
0x180009f2a  mov     [rax+8], rax
0x180009f2e  mov     [r14+10h], r15
0x180009f32  cmp     rdi, [r14+8]
0x180009f36  jz      short loc_180009F55
0x180009f38  mov     rbx, [rdi]
0x180009f3b  lea     rcx, [rdi+10h]; this
0x180009f3f  call    ??1CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(void)
0x180009f44  mov     rcx, rdi; Block
0x180009f47  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009f4c  mov     rdi, rbx
0x180009f4f  cmp     rbx, [r14+8]
0x180009f53  jnz     short loc_180009F38
0x180009f55  mov     rcx, [r14+8]; Block
0x180009f59  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009f5e  mov     [r14+8], r15
0x180009f62  mov     rbx, [rsp+68h+arg_10]
0x180009f6a  add     rsp, 40h
0x180009f6e  pop     r15
0x180009f70  pop     r14
0x180009f72  pop     rdi
0x180009f73  pop     rsi
0x180009f74  pop     rbp
0x180009f75  retn
```
