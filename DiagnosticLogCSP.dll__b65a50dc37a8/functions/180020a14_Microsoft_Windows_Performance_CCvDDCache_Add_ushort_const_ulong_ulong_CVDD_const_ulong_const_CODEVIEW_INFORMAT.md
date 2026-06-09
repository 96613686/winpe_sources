# Microsoft::Windows::Performance::CCvDDCache::Add(ushort const *,ulong,ulong,_CVDD const *,ulong const *,CODEVIEW_INFORMATION_1 const *,ulong,ulong,EMBEDDED_PDB_INFORMATION *,bool,ushort const *,bool *)

- ea: `0x180020a14`
- end: `0x180020cde`
- name: `?Add@CCvDDCache@Performance@Windows@Microsoft@@QEAAJPEBGKKPEBT_CVDD@@PEBKPEBUCODEVIEW_INFORMATION_1@@KKPEAUEMBEDDED_PDB_INFORMATION@@_N0PEA_N@Z`
- size: `714`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CCvDDCache *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, const union _CVDD *, const unsigned int *, const struct CODEVIEW_INFORMATION_1 *, unsigned int, unsigned int, struct EMBEDDED_PDB_INFORMATION *, bool, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180021250`

## callees

- `0x180001b90`
- `0x180001bf8`
- `0x18000a924`
- `0x1800103a8`
- `0x18001ea00`
- `0x18001f074`
- `0x18001ff78`
- `0x180020760`
- `0x1800208a0`
- `0x180020a14`
- `0x180027b70`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Microsoft::Windows::Performance::CCvDDCache::Add(
        Microsoft::Windows::Performance::CCvDDCache *this,
        const unsigned __int16 *a2,
        int a3,
        int a4,
        const union _CVDD *a5,
        const unsigned int *a6,
        const struct CODEVIEW_INFORMATION_1 *a7,
        unsigned int a8,
        unsigned int a9,
        struct EMBEDDED_PDB_INFORMATION *a10,
        char a11,
        const unsigned __int16 *a12,
        bool *a13)
{
  __int64 v17; // rbx
  __int64 v18; // r8
  __int64 v19; // rdx
  const union _CVDD *v20; // rbx
  __int64 v21; // rax
  const union _CVDD *v22; // rcx
  const union _CVDD *v23; // rax
  const union _CVDD *v25; // [rsp+68h] [rbp-150h] BYREF
  unsigned int v26; // [rsp+70h] [rbp-148h]
  unsigned int v27; // [rsp+74h] [rbp-144h]
  int v28; // [rsp+78h] [rbp-140h] BYREF
  const struct CODEVIEW_INFORMATION_1 *v29; // [rsp+80h] [rbp-138h]
  const unsigned int *v30; // [rsp+88h] [rbp-130h] BYREF
  _OWORD v31[2]; // [rsp+98h] [rbp-120h] BYREF
  _OWORD v32[2]; // [rsp+B8h] [rbp-100h] BYREF
  _BYTE v33[32]; // [rsp+E0h] [rbp-D8h] BYREF
  _BYTE v34[40]; // [rsp+100h] [rbp-B8h] BYREF
  void *v35; // [rsp+128h] [rbp-90h]
  void *v36; // [rsp+130h] [rbp-88h]
  void *v37; // [rsp+138h] [rbp-80h]
  _BYTE v38[48]; // [rsp+140h] [rbp-78h] BYREF

  v28 = a3;
  v25 = a5;
  v30 = a6;
  v29 = a7;
  v27 = a8;
  v26 = a9;
  memset(v32, 0, sizeof(v32));
  v17 = -1;
  v18 = -1;
  do
    ++v18;
  while ( a12[v18] );
  std::wstring::_Construct<1,unsigned short const *>(v32, a12, v18);
  memset(v31, 0, sizeof(v31));
  do
    ++v17;
  while ( a2[v17] );
  std::wstring::_Construct<1,unsigned short const *>(v31, a2, v17);
  v19 = Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(
          (unsigned int)v33,
          (unsigned int)v31,
          (unsigned int)v32,
          a4,
          (__int64)v25,
          (__int64)v30,
          (__int64)v29,
          a3,
          v27,
          v26,
          (__int64)a10,
          a11);
  std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::push_back(this, v19);
  std::vector<char>::~vector<char>(v38);
  operator delete(v37);
  v37 = 0;
  operator delete(v36);
  v36 = 0;
  operator delete(v35);
  v35 = 0;
  std::wstring::~wstring(v34);
  std::wstring::~wstring(v33);
  std::wstring::~wstring(v31);
  std::wstring::~wstring(v32);
  v20 = (const union _CVDD *)(*(_QWORD *)(*(_QWORD *)this + 8LL) + 16LL);
  v21 = std::map<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::operator[](
          (char *)this + 16,
          &v28);
  if ( *((_QWORD *)v20 + 3) <= 7u )
    v22 = v20;
  else
    v22 = *(const union _CVDD **)v20;
  v25 = v22;
  *(_QWORD *)std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](
               v21,
               &v25) = v20;
  if ( *((_QWORD *)v20 + 3) <= 7u )
    v23 = v20;
  else
    v23 = *(const union _CVDD **)v20;
  v25 = v23;
  *(_QWORD *)std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](
               (char *)this + 32,
               &v25) = v20;
  if ( a13 )
  {
    v25 = v20;
    *a13 = *(_BYTE *)(std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::insert<0,0>(
                        (char *)this + 48,
                        &v30,
                        &v25)
                    + 8);
  }
  if ( a10 && *(_DWORD *)a10 )
    *((_QWORD *)a10 + 1) = *((_QWORD *)v20 + 12);
  return 0;
}

```

## disassembly

```asm
0x180020a14  push    rbx
0x180020a16  push    rsi
0x180020a17  push    rdi
0x180020a18  push    r12
0x180020a1a  push    r13
0x180020a1c  push    r14
0x180020a1e  push    r15
0x180020a20  sub     rsp, 180h
0x180020a27  mov     rax, cs:__security_cookie
0x180020a2e  xor     rax, rsp
0x180020a31  mov     [rsp+1B8h+var_48], rax
0x180020a39  mov     r13d, r9d
0x180020a3c  mov     r12d, r8d
0x180020a3f  mov     r15, rdx
0x180020a42  mov     rsi, rcx
0x180020a45  mov     rdx, [rsp+1B8h+arg_58]
0x180020a4d  mov     rdi, [rsp+1B8h+arg_48]
0x180020a55  mov     [rsp+1B8h+var_140], r8d
0x180020a5a  mov     rax, [rsp+1B8h+arg_20]
0x180020a62  mov     [rsp+1B8h+var_150], rax
0x180020a67  mov     rax, [rsp+1B8h+arg_28]
0x180020a6f  mov     [rsp+1B8h+var_130], rax
0x180020a77  mov     rax, [rsp+1B8h+arg_30]
0x180020a7f  mov     [rsp+1B8h+var_138], rax
0x180020a87  mov     eax, [rsp+1B8h+arg_38]
0x180020a8e  mov     [rsp+1B8h+var_144], eax
0x180020a92  mov     eax, [rsp+1B8h+arg_40]
0x180020a99  mov     [rsp+1B8h+var_148], eax
0x180020a9d  mov     al, [rsp+1B8h+arg_50]
0x180020aa4  mov     [rsp+1B8h+var_158], al
0x180020aa8  mov     r14, [rsp+1B8h+arg_60]
0x180020ab0  xorps   xmm0, xmm0
0x180020ab3  movups  [rsp+1B8h+var_100], xmm0
0x180020abb  xorps   xmm1, xmm1
0x180020abe  movdqu  [rsp+1B8h+var_F0], xmm1
0x180020ac7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180020acb  mov     r8, rbx
0x180020ace  xor     eax, eax
0x180020ad0  inc     r8
0x180020ad3  cmp     [rdx+r8*2], ax
0x180020ad8  jnz     short loc_180020AD0
0x180020ada  lea     rcx, [rsp+1B8h+var_100]
0x180020ae2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180020ae7  nop
0x180020ae8  xorps   xmm0, xmm0
0x180020aeb  movups  [rsp+1B8h+var_120], xmm0
0x180020af3  xorps   xmm1, xmm1
0x180020af6  movdqu  [rsp+1B8h+var_110], xmm1
0x180020aff  xor     eax, eax
0x180020b01  inc     rbx
0x180020b04  cmp     [r15+rbx*2], ax
0x180020b09  jnz     short loc_180020B01
0x180020b0b  mov     r8, rbx
0x180020b0e  mov     rdx, r15
0x180020b11  lea     rcx, [rsp+1B8h+var_120]
0x180020b19  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180020b1e  nop
0x180020b1f  mov     al, [rsp+1B8h+var_158]
0x180020b23  mov     [rsp+1B8h+var_160], al
0x180020b27  mov     [rsp+1B8h+var_168], rdi
0x180020b2c  mov     eax, [rsp+1B8h+var_148]
0x180020b30  mov     [rsp+1B8h+var_170], eax
0x180020b34  mov     eax, [rsp+1B8h+var_144]
0x180020b38  mov     [rsp+1B8h+var_178], eax
0x180020b3c  mov     [rsp+1B8h+var_180], r12d
0x180020b41  mov     rax, [rsp+1B8h+var_138]
0x180020b49  mov     [rsp+1B8h+var_188], rax
0x180020b4e  mov     rax, [rsp+1B8h+var_130]
0x180020b56  mov     [rsp+1B8h+var_190], rax
0x180020b5b  mov     rax, [rsp+1B8h+var_150]
0x180020b60  mov     [rsp+1B8h+var_198], rax
0x180020b65  mov     r9d, r13d
0x180020b68  lea     r8, [rsp+1B8h+var_100]
0x180020b70  lea     rdx, [rsp+1B8h+var_120]
0x180020b78  lea     rcx, [rsp+1B8h+var_D8]
0x180020b80  call    ??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0KPEBT_CVDD@@PEBKPEBUCODEVIEW_INFORMATION_1@@KKKPEBUEMBEDDED_PDB_INFORMATION@@_N@Z; Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(std::wstring const &,std::wstring const &,ulong,_CVDD const *,ulong const *,CODEVIEW_INFORMATION_1 const *,ulong,ulong,ulong,EMBEDDED_PDB_INFORMATION const *,bool)
0x180020b85  nop
0x180020b86  mov     rdx, rax
0x180020b89  mov     rcx, rsi
0x180020b8c  call    ?push_back@?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@QEAAX$$QEAUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z; std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::push_back(Microsoft::Windows::Performance::CCvDDCache::CCvDD &&)
0x180020b91  nop
0x180020b92  lea     rcx, [rsp+1B8h+var_78]
0x180020b9a  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180020b9f  mov     rcx, [rsp+1B8h+var_80]; void *
0x180020ba7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020bac  xor     r15d, r15d
0x180020baf  mov     [rsp+1B8h+var_80], r15
0x180020bb7  mov     rcx, [rsp+1B8h+var_88]; void *
0x180020bbf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020bc4  mov     [rsp+1B8h+var_88], r15
0x180020bcc  mov     rcx, [rsp+1B8h+var_90]; void *
0x180020bd4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020bd9  mov     [rsp+1B8h+var_90], r15
0x180020be1  lea     rcx, [rsp+1B8h+var_B8]
0x180020be9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180020bee  lea     rcx, [rsp+1B8h+var_D8]
0x180020bf6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180020bfb  nop
0x180020bfc  lea     rcx, [rsp+1B8h+var_120]
0x180020c04  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180020c09  nop
0x180020c0a  lea     rcx, [rsp+1B8h+var_100]
0x180020c12  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180020c17  mov     rax, [rsi]
0x180020c1a  mov     rbx, [rax+8]
0x180020c1e  add     rbx, 10h
0x180020c22  lea     rcx, [rsi+10h]
0x180020c26  lea     rdx, [rsp+1B8h+var_140]
0x180020c2b  call    ??A?$map@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@QEAAAEAV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@1@AEBK@Z; std::map<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::operator[](ulong const &)
0x180020c30  cmp     qword ptr [rbx+18h], 7
0x180020c35  jbe     short loc_180020C3C
0x180020c37  mov     rcx, [rbx]
0x180020c3a  jmp     short loc_180020C3F
0x180020c3c  mov     rcx, rbx
0x180020c3f  mov     [rsp+1B8h+var_150], rcx
0x180020c44  lea     rdx, [rsp+1B8h+var_150]
0x180020c49  mov     rcx, rax
0x180020c4c  call    ??A?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@$$QEAPEBG@Z; std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](ushort const * &&)
0x180020c51  mov     [rax], rbx
0x180020c54  cmp     qword ptr [rbx+18h], 7
0x180020c59  jbe     short loc_180020C60
0x180020c5b  mov     rax, [rbx]
0x180020c5e  jmp     short loc_180020C63
0x180020c60  mov     rax, rbx
0x180020c63  mov     [rsp+1B8h+var_150], rax
0x180020c68  lea     rcx, [rsi+20h]
0x180020c6c  lea     rdx, [rsp+1B8h+var_150]
0x180020c71  call    ??A?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@$$QEAPEBG@Z; std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](ushort const * &&)
0x180020c76  mov     [rax], rbx
0x180020c79  test    r14, r14
0x180020c7c  jz      short loc_180020C9F
0x180020c7e  mov     [rsp+1B8h+var_150], rbx
0x180020c83  lea     rcx, [rsi+30h]
0x180020c87  lea     r8, [rsp+1B8h+var_150]
0x180020c8c  lea     rdx, [rsp+1B8h+var_130]
0x180020c94  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessCCvDDPtrByImageId@2345@V?$allocator@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@_N@1@$$QEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z; std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::insert<0,0>(Microsoft::Windows::Performance::CCvDDCache::CCvDD const * &&)
0x180020c99  mov     al, [rax+8]
0x180020c9c  mov     [r14], al
0x180020c9f  test    rdi, rdi
0x180020ca2  jz      short loc_180020CB1
0x180020ca4  cmp     [rdi], r15d
0x180020ca7  jz      short loc_180020CB1
0x180020ca9  mov     rax, [rbx+60h]
0x180020cad  mov     [rdi+8], rax
0x180020cb1  xor     eax, eax
0x180020cb3  jmp     short loc_180020CBA
0x180020cb5  mov     eax, 8007000Eh
0x180020cba  mov     rcx, [rsp+1B8h+var_48]
0x180020cc2  xor     rcx, rsp; StackCookie
0x180020cc5  call    __security_check_cookie
0x180020cca  add     rsp, 180h
0x180020cd1  pop     r15
0x180020cd3  pop     r14
0x180020cd5  pop     r13
0x180020cd7  pop     r12
0x180020cd9  pop     rdi
0x180020cda  pop     rsi
0x180020cdb  pop     rbx
0x180020cdc  retn
```
