# Microsoft::Windows::Performance::CCvDDCache::Add(ushort const *,ulong,ulong,_CVDD const *,ulong const *,CODEVIEW_INFORMATION_1 const *,ulong,ulong,EMBEDDED_PDB_INFORMATION *,bool,ushort const *,bool *)

- ea: `0x18000edc4`
- end: `0x18000f08e`
- name: `?Add@CCvDDCache@Performance@Windows@Microsoft@@QEAAJPEBGKKPEBT_CVDD@@PEBKPEBUCODEVIEW_INFORMATION_1@@KKPEAUEMBEDDED_PDB_INFORMATION@@_N0PEA_N@Z`
- size: `714`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CCvDDCache *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, const union _CVDD *, const unsigned int *, const struct CODEVIEW_INFORMATION_1 *, unsigned int, unsigned int, struct EMBEDDED_PDB_INFORMATION *, bool, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000f5dc`

## callees

- `0x180001870`
- `0x180001894`
- `0x18000b398`
- `0x18000b534`
- `0x18000cd80`
- `0x18000d4bc`
- `0x18000e364`
- `0x18000eb20`
- `0x18000ec5c`
- `0x18000edc4`
- `0x180015c0c`

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
  void *Block; // [rsp+138h] [rbp-80h]
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
  std::wstring::_Construct<1,unsigned short const *>(v32, a12);
  memset(v31, 0, sizeof(v31));
  do
    ++v17;
  while ( a2[v17] );
  std::wstring::_Construct<1,unsigned short const *>(v31, a2);
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
  operator delete(Block);
  Block = 0;
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
0x18000edc4  push    rbx
0x18000edc6  push    rsi
0x18000edc7  push    rdi
0x18000edc8  push    r12
0x18000edca  push    r13
0x18000edcc  push    r14
0x18000edce  push    r15
0x18000edd0  sub     rsp, 180h
0x18000edd7  mov     rax, cs:__security_cookie
0x18000edde  xor     rax, rsp
0x18000ede1  mov     [rsp+1B8h+var_48], rax
0x18000ede9  mov     r13d, r9d
0x18000edec  mov     r12d, r8d
0x18000edef  mov     r15, rdx
0x18000edf2  mov     rsi, rcx
0x18000edf5  mov     rdx, [rsp+1B8h+arg_58]
0x18000edfd  mov     rdi, [rsp+1B8h+arg_48]
0x18000ee05  mov     [rsp+1B8h+var_140], r8d
0x18000ee0a  mov     rax, [rsp+1B8h+arg_20]
0x18000ee12  mov     [rsp+1B8h+var_150], rax
0x18000ee17  mov     rax, [rsp+1B8h+arg_28]
0x18000ee1f  mov     [rsp+1B8h+var_130], rax
0x18000ee27  mov     rax, [rsp+1B8h+arg_30]
0x18000ee2f  mov     [rsp+1B8h+var_138], rax
0x18000ee37  mov     eax, [rsp+1B8h+arg_38]
0x18000ee3e  mov     [rsp+1B8h+var_144], eax
0x18000ee42  mov     eax, [rsp+1B8h+arg_40]
0x18000ee49  mov     [rsp+1B8h+var_148], eax
0x18000ee4d  mov     al, [rsp+1B8h+arg_50]
0x18000ee54  mov     [rsp+1B8h+var_158], al
0x18000ee58  mov     r14, [rsp+1B8h+arg_60]
0x18000ee60  xorps   xmm0, xmm0
0x18000ee63  movups  [rsp+1B8h+var_100], xmm0
0x18000ee6b  xorps   xmm1, xmm1
0x18000ee6e  movdqu  [rsp+1B8h+var_F0], xmm1
0x18000ee77  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000ee7b  mov     r8, rbx
0x18000ee7e  xor     eax, eax
0x18000ee80  inc     r8
0x18000ee83  cmp     [rdx+r8*2], ax
0x18000ee88  jnz     short loc_18000EE80
0x18000ee8a  lea     rcx, [rsp+1B8h+var_100]
0x18000ee92  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000ee97  nop
0x18000ee98  xorps   xmm0, xmm0
0x18000ee9b  movups  [rsp+1B8h+var_120], xmm0
0x18000eea3  xorps   xmm1, xmm1
0x18000eea6  movdqu  [rsp+1B8h+var_110], xmm1
0x18000eeaf  xor     eax, eax
0x18000eeb1  inc     rbx
0x18000eeb4  cmp     [r15+rbx*2], ax
0x18000eeb9  jnz     short loc_18000EEB1
0x18000eebb  mov     r8, rbx
0x18000eebe  mov     rdx, r15
0x18000eec1  lea     rcx, [rsp+1B8h+var_120]
0x18000eec9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000eece  nop
0x18000eecf  mov     al, [rsp+1B8h+var_158]
0x18000eed3  mov     [rsp+1B8h+var_160], al
0x18000eed7  mov     [rsp+1B8h+var_168], rdi
0x18000eedc  mov     eax, [rsp+1B8h+var_148]
0x18000eee0  mov     [rsp+1B8h+var_170], eax
0x18000eee4  mov     eax, [rsp+1B8h+var_144]
0x18000eee8  mov     [rsp+1B8h+var_178], eax
0x18000eeec  mov     [rsp+1B8h+var_180], r12d
0x18000eef1  mov     rax, [rsp+1B8h+var_138]
0x18000eef9  mov     [rsp+1B8h+var_188], rax
0x18000eefe  mov     rax, [rsp+1B8h+var_130]
0x18000ef06  mov     [rsp+1B8h+var_190], rax
0x18000ef0b  mov     rax, [rsp+1B8h+var_150]
0x18000ef10  mov     [rsp+1B8h+var_198], rax
0x18000ef15  mov     r9d, r13d
0x18000ef18  lea     r8, [rsp+1B8h+var_100]
0x18000ef20  lea     rdx, [rsp+1B8h+var_120]
0x18000ef28  lea     rcx, [rsp+1B8h+var_D8]
0x18000ef30  call    ??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0KPEBT_CVDD@@PEBKPEBUCODEVIEW_INFORMATION_1@@KKKPEBUEMBEDDED_PDB_INFORMATION@@_N@Z; Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(std::wstring const &,std::wstring const &,ulong,_CVDD const *,ulong const *,CODEVIEW_INFORMATION_1 const *,ulong,ulong,ulong,EMBEDDED_PDB_INFORMATION const *,bool)
0x18000ef35  nop
0x18000ef36  mov     rdx, rax
0x18000ef39  mov     rcx, rsi
0x18000ef3c  call    ?push_back@?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@QEAAX$$QEAUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z; std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::push_back(Microsoft::Windows::Performance::CCvDDCache::CCvDD &&)
0x18000ef41  nop
0x18000ef42  lea     rcx, [rsp+1B8h+var_78]
0x18000ef4a  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18000ef4f  mov     rcx, [rsp+1B8h+Block]; Block
0x18000ef57  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ef5c  xor     r15d, r15d
0x18000ef5f  mov     [rsp+1B8h+Block], r15
0x18000ef67  mov     rcx, [rsp+1B8h+var_88]; Block
0x18000ef6f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ef74  mov     [rsp+1B8h+var_88], r15
0x18000ef7c  mov     rcx, [rsp+1B8h+var_90]; Block
0x18000ef84  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ef89  mov     [rsp+1B8h+var_90], r15
0x18000ef91  lea     rcx, [rsp+1B8h+var_B8]
0x18000ef99  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ef9e  lea     rcx, [rsp+1B8h+var_D8]
0x18000efa6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000efab  nop
0x18000efac  lea     rcx, [rsp+1B8h+var_120]
0x18000efb4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000efb9  nop
0x18000efba  lea     rcx, [rsp+1B8h+var_100]
0x18000efc2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000efc7  mov     rax, [rsi]
0x18000efca  mov     rbx, [rax+8]
0x18000efce  add     rbx, 10h
0x18000efd2  lea     rcx, [rsi+10h]
0x18000efd6  lea     rdx, [rsp+1B8h+var_140]
0x18000efdb  call    ??A?$map@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@QEAAAEAV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@1@AEBK@Z; std::map<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::operator[](ulong const &)
0x18000efe0  cmp     qword ptr [rbx+18h], 7
0x18000efe5  jbe     short loc_18000EFEC
0x18000efe7  mov     rcx, [rbx]
0x18000efea  jmp     short loc_18000EFEF
0x18000efec  mov     rcx, rbx
0x18000efef  mov     [rsp+1B8h+var_150], rcx
0x18000eff4  lea     rdx, [rsp+1B8h+var_150]
0x18000eff9  mov     rcx, rax
0x18000effc  call    ??A?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@$$QEAPEBG@Z; std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](ushort const * &&)
0x18000f001  mov     [rax], rbx
0x18000f004  cmp     qword ptr [rbx+18h], 7
0x18000f009  jbe     short loc_18000F010
0x18000f00b  mov     rax, [rbx]
0x18000f00e  jmp     short loc_18000F013
0x18000f010  mov     rax, rbx
0x18000f013  mov     [rsp+1B8h+var_150], rax
0x18000f018  lea     rcx, [rsi+20h]
0x18000f01c  lea     rdx, [rsp+1B8h+var_150]
0x18000f021  call    ??A?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@$$QEAPEBG@Z; std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](ushort const * &&)
0x18000f026  mov     [rax], rbx
0x18000f029  test    r14, r14
0x18000f02c  jz      short loc_18000F04F
0x18000f02e  mov     [rsp+1B8h+var_150], rbx
0x18000f033  lea     rcx, [rsi+30h]
0x18000f037  lea     r8, [rsp+1B8h+var_150]
0x18000f03c  lea     rdx, [rsp+1B8h+var_130]
0x18000f044  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessCCvDDPtrByImageId@2345@V?$allocator@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@_N@1@$$QEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z; std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::insert<0,0>(Microsoft::Windows::Performance::CCvDDCache::CCvDD const * &&)
0x18000f049  mov     al, [rax+8]
0x18000f04c  mov     [r14], al
0x18000f04f  test    rdi, rdi
0x18000f052  jz      short loc_18000F061
0x18000f054  cmp     [rdi], r15d
0x18000f057  jz      short loc_18000F061
0x18000f059  mov     rax, [rbx+60h]
0x18000f05d  mov     [rdi+8], rax
0x18000f061  xor     eax, eax
0x18000f063  jmp     short loc_18000F06A
0x18000f065  mov     eax, 8007000Eh
0x18000f06a  mov     rcx, [rsp+1B8h+var_48]
0x18000f072  xor     rcx, rsp; StackCookie
0x18000f075  call    __security_check_cookie
0x18000f07a  add     rsp, 180h
0x18000f081  pop     r15
0x18000f083  pop     r14
0x18000f085  pop     r13
0x18000f087  pop     r12
0x18000f089  pop     rdi
0x18000f08a  pop     rsi
0x18000f08b  pop     rbx
0x18000f08c  retn
```
