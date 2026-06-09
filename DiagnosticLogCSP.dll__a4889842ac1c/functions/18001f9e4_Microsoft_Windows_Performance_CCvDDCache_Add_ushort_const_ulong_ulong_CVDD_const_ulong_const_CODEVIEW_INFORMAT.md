# Microsoft::Windows::Performance::CCvDDCache::Add(ushort const *,ulong,ulong,_CVDD const *,ulong const *,CODEVIEW_INFORMATION_1 const *,ulong,ulong,EMBEDDED_PDB_INFORMATION *,bool,ushort const *,bool *)

- ea: `0x18001f9e4`
- end: `0x18001fcae`
- name: `?Add@CCvDDCache@Performance@Windows@Microsoft@@QEAAJPEBGKKPEBT_CVDD@@PEBKPEBUCODEVIEW_INFORMATION_1@@KKPEAUEMBEDDED_PDB_INFORMATION@@_N0PEA_N@Z`
- size: `714`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CCvDDCache *this, const unsigned __int16 *, int, int, const union _CVDD *, const unsigned int *, const struct CODEVIEW_INFORMATION_1 *, unsigned int, unsigned int, const void **, char, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180020204`

## callees

- `0x180001b60`
- `0x180001bc8`
- `0x18000a600`
- `0x18000fb98`
- `0x18001da68`
- `0x18001e0d4`
- `0x18001ef84`
- `0x18001f744`
- `0x18001f880`
- `0x18001f9e4`
- `0x180026a08`

## pseudocode

```c
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
        const void **a10,
        char a11,
        const unsigned __int16 *a12,
        bool *a13)
{
  unsigned __int64 v17; // rbx
  unsigned __int64 v18; // r8
  __int64 v19; // rdx
  const union _CVDD *v20; // rbx
  __int64 *v21; // rax
  const union _CVDD *v22; // rcx
  const union _CVDD *v23; // rax
  const union _CVDD *v25; // [rsp+68h] [rbp-150h] BYREF
  int v26; // [rsp+70h] [rbp-148h]
  int v27; // [rsp+74h] [rbp-144h]
  int v28; // [rsp+78h] [rbp-140h] BYREF
  const struct CODEVIEW_INFORMATION_1 *v29; // [rsp+80h] [rbp-138h]
  const unsigned int *v30; // [rsp+88h] [rbp-130h] BYREF
  _OWORD v31[2]; // [rsp+98h] [rbp-120h] BYREF
  _OWORD v32[2]; // [rsp+B8h] [rbp-100h] BYREF
  char *v33[4]; // [rsp+E0h] [rbp-D8h] BYREF
  char *v34; // [rsp+100h] [rbp-B8h] BYREF
  void *v35; // [rsp+128h] [rbp-90h]
  void *v36; // [rsp+130h] [rbp-88h]
  void *v37; // [rsp+138h] [rbp-80h]
  char *v38; // [rsp+140h] [rbp-78h] BYREF

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
  std::wstring::_Construct<1,unsigned short const *>((char **)v32, a12, v18);
  memset(v31, 0, sizeof(v31));
  do
    ++v17;
  while ( a2[v17] );
  std::wstring::_Construct<1,unsigned short const *>((char **)v31, a2, v17);
  v19 = Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(
          (__int64)v33,
          (__int64)v31,
          (__int64)v32,
          a4,
          (__int64)v25,
          (__int64)v30,
          (__int64)v29,
          a3,
          v27,
          v26,
          a10,
          a11);
  std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::push_back(this, v19);
  std::vector<char>::~vector<char>(&v38);
  operator delete(v37);
  v37 = 0;
  operator delete(v36);
  v36 = 0;
  operator delete(v35);
  v35 = 0;
  std::wstring::~wstring(&v34);
  std::wstring::~wstring(v33);
  std::wstring::~wstring((char **)v31);
  std::wstring::~wstring((char **)v32);
  v20 = (const union _CVDD *)(*(_QWORD *)(*(_QWORD *)this + 8LL) + 16LL);
  v21 = (__int64 *)std::map<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::operator[](
                     (__int64 *)this + 2,
                     (unsigned int *)&v28);
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
               (__int64 *)this + 4,
               &v25) = v20;
  if ( a13 )
  {
    v25 = v20;
    *a13 = *(_BYTE *)(std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::insert<0,0>(
                        (__int64 *)this + 6,
                        (__int64)&v30,
                        (__int64 *)&v25)
                    + 8);
  }
  if ( a10 && *(_DWORD *)a10 )
    a10[1] = (const void *)*((_QWORD *)v20 + 12);
  return 0;
}

```

## disassembly

```asm
0x18001f9e4  push    rbx
0x18001f9e6  push    rsi
0x18001f9e7  push    rdi
0x18001f9e8  push    r12
0x18001f9ea  push    r13
0x18001f9ec  push    r14
0x18001f9ee  push    r15
0x18001f9f0  sub     rsp, 180h
0x18001f9f7  mov     rax, cs:__security_cookie
0x18001f9fe  xor     rax, rsp
0x18001fa01  mov     [rsp+1B8h+var_48], rax
0x18001fa09  mov     r13d, r9d
0x18001fa0c  mov     r12d, r8d
0x18001fa0f  mov     r15, rdx
0x18001fa12  mov     rsi, rcx
0x18001fa15  mov     rdx, [rsp+1B8h+arg_58]
0x18001fa1d  mov     rdi, [rsp+1B8h+arg_48]
0x18001fa25  mov     [rsp+1B8h+var_140], r8d
0x18001fa2a  mov     rax, [rsp+1B8h+arg_20]
0x18001fa32  mov     [rsp+1B8h+var_150], rax
0x18001fa37  mov     rax, [rsp+1B8h+arg_28]
0x18001fa3f  mov     [rsp+1B8h+var_130], rax
0x18001fa47  mov     rax, [rsp+1B8h+arg_30]
0x18001fa4f  mov     [rsp+1B8h+var_138], rax
0x18001fa57  mov     eax, [rsp+1B8h+arg_38]
0x18001fa5e  mov     [rsp+1B8h+var_144], eax
0x18001fa62  mov     eax, [rsp+1B8h+arg_40]
0x18001fa69  mov     [rsp+1B8h+var_148], eax
0x18001fa6d  mov     al, [rsp+1B8h+arg_50]
0x18001fa74  mov     [rsp+1B8h+var_158], al
0x18001fa78  mov     r14, [rsp+1B8h+arg_60]
0x18001fa80  xorps   xmm0, xmm0
0x18001fa83  movups  [rsp+1B8h+var_100], xmm0
0x18001fa8b  xorps   xmm1, xmm1
0x18001fa8e  movdqu  [rsp+1B8h+var_F0], xmm1
0x18001fa97  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001fa9b  mov     r8, rbx
0x18001fa9e  xor     eax, eax
0x18001faa0  inc     r8
0x18001faa3  cmp     [rdx+r8*2], ax
0x18001faa8  jnz     short loc_18001FAA0
0x18001faaa  lea     rcx, [rsp+1B8h+var_100]
0x18001fab2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001fab7  nop
0x18001fab8  xorps   xmm0, xmm0
0x18001fabb  movups  [rsp+1B8h+var_120], xmm0
0x18001fac3  xorps   xmm1, xmm1
0x18001fac6  movdqu  [rsp+1B8h+var_110], xmm1
0x18001facf  xor     eax, eax
0x18001fad1  inc     rbx
0x18001fad4  cmp     [r15+rbx*2], ax
0x18001fad9  jnz     short loc_18001FAD1
0x18001fadb  mov     r8, rbx
0x18001fade  mov     rdx, r15
0x18001fae1  lea     rcx, [rsp+1B8h+var_120]
0x18001fae9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001faee  nop
0x18001faef  mov     al, [rsp+1B8h+var_158]
0x18001faf3  mov     [rsp+1B8h+var_160], al
0x18001faf7  mov     [rsp+1B8h+var_168], rdi
0x18001fafc  mov     eax, [rsp+1B8h+var_148]
0x18001fb00  mov     [rsp+1B8h+var_170], eax
0x18001fb04  mov     eax, [rsp+1B8h+var_144]
0x18001fb08  mov     [rsp+1B8h+var_178], eax
0x18001fb0c  mov     [rsp+1B8h+var_180], r12d
0x18001fb11  mov     rax, [rsp+1B8h+var_138]
0x18001fb19  mov     [rsp+1B8h+var_188], rax
0x18001fb1e  mov     rax, [rsp+1B8h+var_130]
0x18001fb26  mov     [rsp+1B8h+var_190], rax
0x18001fb2b  mov     rax, [rsp+1B8h+var_150]
0x18001fb30  mov     [rsp+1B8h+var_198], rax
0x18001fb35  mov     r9d, r13d
0x18001fb38  lea     r8, [rsp+1B8h+var_100]
0x18001fb40  lea     rdx, [rsp+1B8h+var_120]
0x18001fb48  lea     rcx, [rsp+1B8h+var_D8]
0x18001fb50  call    ??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0KPEBT_CVDD@@PEBKPEBUCODEVIEW_INFORMATION_1@@KKKPEBUEMBEDDED_PDB_INFORMATION@@_N@Z; Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(std::wstring const &,std::wstring const &,ulong,_CVDD const *,ulong const *,CODEVIEW_INFORMATION_1 const *,ulong,ulong,ulong,EMBEDDED_PDB_INFORMATION const *,bool)
0x18001fb55  nop
0x18001fb56  mov     rdx, rax
0x18001fb59  mov     rcx, rsi
0x18001fb5c  call    ?push_back@?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@QEAAX$$QEAUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z; std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::push_back(Microsoft::Windows::Performance::CCvDDCache::CCvDD &&)
0x18001fb61  nop
0x18001fb62  lea     rcx, [rsp+1B8h+var_78]
0x18001fb6a  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18001fb6f  mov     rcx, [rsp+1B8h+var_80]; void *
0x18001fb77  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fb7c  xor     r15d, r15d
0x18001fb7f  mov     [rsp+1B8h+var_80], r15
0x18001fb87  mov     rcx, [rsp+1B8h+var_88]; void *
0x18001fb8f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fb94  mov     [rsp+1B8h+var_88], r15
0x18001fb9c  mov     rcx, [rsp+1B8h+var_90]; void *
0x18001fba4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fba9  mov     [rsp+1B8h+var_90], r15
0x18001fbb1  lea     rcx, [rsp+1B8h+var_B8]
0x18001fbb9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001fbbe  lea     rcx, [rsp+1B8h+var_D8]
0x18001fbc6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001fbcb  nop
0x18001fbcc  lea     rcx, [rsp+1B8h+var_120]
0x18001fbd4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001fbd9  nop
0x18001fbda  lea     rcx, [rsp+1B8h+var_100]
0x18001fbe2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001fbe7  mov     rax, [rsi]
0x18001fbea  mov     rbx, [rax+8]
0x18001fbee  add     rbx, 10h
0x18001fbf2  lea     rcx, [rsi+10h]
0x18001fbf6  lea     rdx, [rsp+1B8h+var_140]
0x18001fbfb  call    ??A?$map@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@QEAAAEAV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@1@AEBK@Z; std::map<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::operator[](ulong const &)
0x18001fc00  cmp     qword ptr [rbx+18h], 7
0x18001fc05  jbe     short loc_18001FC0C
0x18001fc07  mov     rcx, [rbx]
0x18001fc0a  jmp     short loc_18001FC0F
0x18001fc0c  mov     rcx, rbx
0x18001fc0f  mov     [rsp+1B8h+var_150], rcx
0x18001fc14  lea     rdx, [rsp+1B8h+var_150]
0x18001fc19  mov     rcx, rax
0x18001fc1c  call    ??A?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@$$QEAPEBG@Z; std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](ushort const * &&)
0x18001fc21  mov     [rax], rbx
0x18001fc24  cmp     qword ptr [rbx+18h], 7
0x18001fc29  jbe     short loc_18001FC30
0x18001fc2b  mov     rax, [rbx]
0x18001fc2e  jmp     short loc_18001FC33
0x18001fc30  mov     rax, rbx
0x18001fc33  mov     [rsp+1B8h+var_150], rax
0x18001fc38  lea     rcx, [rsi+20h]
0x18001fc3c  lea     rdx, [rsp+1B8h+var_150]
0x18001fc41  call    ??A?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@$$QEAPEBG@Z; std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](ushort const * &&)
0x18001fc46  mov     [rax], rbx
0x18001fc49  test    r14, r14
0x18001fc4c  jz      short loc_18001FC6F
0x18001fc4e  mov     [rsp+1B8h+var_150], rbx
0x18001fc53  lea     rcx, [rsi+30h]
0x18001fc57  lea     r8, [rsp+1B8h+var_150]
0x18001fc5c  lea     rdx, [rsp+1B8h+var_130]
0x18001fc64  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessCCvDDPtrByImageId@2345@V?$allocator@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@_N@1@$$QEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z; std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::insert<0,0>(Microsoft::Windows::Performance::CCvDDCache::CCvDD const * &&)
0x18001fc69  mov     al, [rax+8]
0x18001fc6c  mov     [r14], al
0x18001fc6f  test    rdi, rdi
0x18001fc72  jz      short loc_18001FC81
0x18001fc74  cmp     [rdi], r15d
0x18001fc77  jz      short loc_18001FC81
0x18001fc79  mov     rax, [rbx+60h]
0x18001fc7d  mov     [rdi+8], rax
0x18001fc81  xor     eax, eax
0x18001fc83  jmp     short loc_18001FC8A
0x18001fc85  mov     eax, 8007000Eh
0x18001fc8a  mov     rcx, [rsp+1B8h+var_48]
0x18001fc92  xor     rcx, rsp; StackCookie
0x18001fc95  call    __security_check_cookie
0x18001fc9a  add     rsp, 180h
0x18001fca1  pop     r15
0x18001fca3  pop     r14
0x18001fca5  pop     r13
0x18001fca7  pop     r12
0x18001fca9  pop     rdi
0x18001fcaa  pop     rsi
0x18001fcab  pop     rbx
0x18001fcac  retn
```
