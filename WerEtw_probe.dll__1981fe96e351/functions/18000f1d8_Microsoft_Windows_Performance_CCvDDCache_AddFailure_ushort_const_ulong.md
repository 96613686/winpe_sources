# Microsoft::Windows::Performance::CCvDDCache::AddFailure(ushort const *,ulong)

- ea: `0x18000f1d8`
- end: `0x18000f3c5`
- name: `?AddFailure@CCvDDCache@Performance@Windows@Microsoft@@QEAAJPEBGK@Z`
- size: `493`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CCvDDCache *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000f5dc`

## callees

- `0x180001870`
- `0x180001894`
- `0x18000b398`
- `0x18000b534`
- `0x18000d4bc`
- `0x18000e364`
- `0x18000eb20`
- `0x18000ec5c`
- `0x18000f1d8`
- `0x180015c0c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Microsoft::Windows::Performance::CCvDDCache::AddFailure(
        Microsoft::Windows::Performance::CCvDDCache *this,
        const unsigned __int16 *a2,
        int a3)
{
  __int64 v6; // r8
  __int64 v7; // rdx
  _QWORD *v8; // rbx
  __int64 v9; // rax
  _QWORD *v10; // rcx
  int v12; // [rsp+60h] [rbp-108h] BYREF
  _QWORD *v13; // [rsp+68h] [rbp-100h] BYREF
  _OWORD v14[2]; // [rsp+70h] [rbp-F8h] BYREF
  _OWORD v15[2]; // [rsp+90h] [rbp-D8h] BYREF
  _BYTE v16[32]; // [rsp+B0h] [rbp-B8h] BYREF
  _BYTE v17[40]; // [rsp+D0h] [rbp-98h] BYREF
  void *v18; // [rsp+F8h] [rbp-70h]
  void *v19; // [rsp+100h] [rbp-68h]
  void *Block; // [rsp+108h] [rbp-60h]
  _BYTE v21[48]; // [rsp+110h] [rbp-58h] BYREF

  v12 = a3;
  memset(v15, 0, sizeof(v15));
  std::wstring::_Construct<1,unsigned short const *>(v15, &word_18002D338);
  memset(v14, 0, sizeof(v14));
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  std::wstring::_Construct<1,unsigned short const *>(v14, a2);
  v7 = Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(
         (__int64)v16,
         (__int64)v14,
         (__int64)v15,
         0,
         0,
         0,
         0,
         a3,
         0,
         0,
         0,
         0);
  std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::push_back(this, v7);
  std::vector<char>::~vector<char>(v21);
  operator delete(Block);
  Block = 0;
  operator delete(v19);
  v19 = 0;
  operator delete(v18);
  v18 = 0;
  std::wstring::~wstring(v17);
  std::wstring::~wstring(v16);
  std::wstring::~wstring(v14);
  std::wstring::~wstring(v15);
  v8 = (_QWORD *)(*(_QWORD *)(*(_QWORD *)this + 8LL) + 16LL);
  v9 = std::map<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::operator[](
         (char *)this + 16,
         &v12);
  if ( v8[3] <= 7u )
    v10 = v8;
  else
    v10 = (_QWORD *)*v8;
  v13 = v10;
  *(_QWORD *)std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](
               v9,
               &v13) = 0;
  if ( v8[3] > 7u )
    v8 = (_QWORD *)*v8;
  v13 = v8;
  *(_QWORD *)std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](
               (char *)this + 32,
               &v13) = 0;
  return 0;
}

```

## disassembly

```asm
0x18000f1d8  mov     [rsp+arg_18], rbx
0x18000f1dd  push    rsi
0x18000f1de  push    rdi
0x18000f1df  push    r14
0x18000f1e1  sub     rsp, 150h
0x18000f1e8  mov     rax, cs:__security_cookie
0x18000f1ef  xor     rax, rsp
0x18000f1f2  mov     [rsp+168h+var_28], rax
0x18000f1fa  mov     esi, r8d
0x18000f1fd  mov     rbx, rdx
0x18000f200  mov     rdi, rcx
0x18000f203  mov     [rsp+168h+var_108], r8d
0x18000f208  xorps   xmm0, xmm0
0x18000f20b  movups  [rsp+168h+var_D8], xmm0
0x18000f213  xorps   xmm1, xmm1
0x18000f216  movdqu  [rsp+168h+var_C8], xmm1
0x18000f21f  xor     r8d, r8d
0x18000f222  lea     rdx, word_18002D338
0x18000f229  lea     rcx, [rsp+168h+var_D8]
0x18000f231  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000f236  nop
0x18000f237  xorps   xmm0, xmm0
0x18000f23a  movups  [rsp+168h+var_F8], xmm0
0x18000f23f  xorps   xmm1, xmm1
0x18000f242  movdqu  [rsp+168h+var_E8], xmm1
0x18000f24b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000f24f  xor     r14d, r14d
0x18000f252  inc     r8
0x18000f255  cmp     [rbx+r8*2], r14w
0x18000f25a  jnz     short loc_18000F252
0x18000f25c  mov     rdx, rbx
0x18000f25f  lea     rcx, [rsp+168h+var_F8]
0x18000f264  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000f269  nop
0x18000f26a  mov     [rsp+168h+var_110], r14b
0x18000f26f  mov     [rsp+168h+var_118], r14
0x18000f274  mov     [rsp+168h+var_120], r14d
0x18000f279  mov     [rsp+168h+var_128], r14d
0x18000f27e  mov     [rsp+168h+var_130], esi
0x18000f282  mov     [rsp+168h+var_138], r14
0x18000f287  mov     [rsp+168h+var_140], r14
0x18000f28c  mov     [rsp+168h+var_148], r14
0x18000f291  xor     r9d, r9d
0x18000f294  lea     r8, [rsp+168h+var_D8]
0x18000f29c  lea     rdx, [rsp+168h+var_F8]
0x18000f2a1  lea     rcx, [rsp+168h+var_B8]
0x18000f2a9  call    ??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0KPEBT_CVDD@@PEBKPEBUCODEVIEW_INFORMATION_1@@KKKPEBUEMBEDDED_PDB_INFORMATION@@_N@Z; Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(std::wstring const &,std::wstring const &,ulong,_CVDD const *,ulong const *,CODEVIEW_INFORMATION_1 const *,ulong,ulong,ulong,EMBEDDED_PDB_INFORMATION const *,bool)
0x18000f2ae  nop
0x18000f2af  mov     rdx, rax
0x18000f2b2  mov     rcx, rdi
0x18000f2b5  call    ?push_back@?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@QEAAX$$QEAUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z; std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::push_back(Microsoft::Windows::Performance::CCvDDCache::CCvDD &&)
0x18000f2ba  nop
0x18000f2bb  lea     rcx, [rsp+168h+var_58]
0x18000f2c3  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18000f2c8  mov     rcx, [rsp+168h+Block]; Block
0x18000f2d0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f2d5  mov     [rsp+168h+Block], r14
0x18000f2dd  mov     rcx, [rsp+168h+var_68]; Block
0x18000f2e5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f2ea  mov     [rsp+168h+var_68], r14
0x18000f2f2  mov     rcx, [rsp+168h+var_70]; Block
0x18000f2fa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f2ff  mov     [rsp+168h+var_70], r14
0x18000f307  lea     rcx, [rsp+168h+var_98]
0x18000f30f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f314  lea     rcx, [rsp+168h+var_B8]
0x18000f31c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f321  nop
0x18000f322  lea     rcx, [rsp+168h+var_F8]
0x18000f327  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f32c  nop
0x18000f32d  lea     rcx, [rsp+168h+var_D8]
0x18000f335  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f33a  mov     rax, [rdi]
0x18000f33d  mov     rbx, [rax+8]
0x18000f341  add     rbx, 10h
0x18000f345  lea     rcx, [rdi+10h]
0x18000f349  lea     rdx, [rsp+168h+var_108]
0x18000f34e  call    ??A?$map@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@QEAAAEAV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@1@AEBK@Z; std::map<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::operator[](ulong const &)
0x18000f353  cmp     qword ptr [rbx+18h], 7
0x18000f358  jbe     short loc_18000F35F
0x18000f35a  mov     rcx, [rbx]
0x18000f35d  jmp     short loc_18000F362
0x18000f35f  mov     rcx, rbx
0x18000f362  mov     [rsp+168h+var_100], rcx
0x18000f367  lea     rdx, [rsp+168h+var_100]
0x18000f36c  mov     rcx, rax
0x18000f36f  call    ??A?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@$$QEAPEBG@Z; std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](ushort const * &&)
0x18000f374  mov     [rax], r14
0x18000f377  cmp     qword ptr [rbx+18h], 7
0x18000f37c  jbe     short loc_18000F381
0x18000f37e  mov     rbx, [rbx]
0x18000f381  mov     [rsp+168h+var_100], rbx
0x18000f386  lea     rcx, [rdi+20h]
0x18000f38a  lea     rdx, [rsp+168h+var_100]
0x18000f38f  call    ??A?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@$$QEAPEBG@Z; std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](ushort const * &&)
0x18000f394  mov     [rax], r14
0x18000f397  xor     eax, eax
0x18000f399  jmp     short loc_18000F3A0
0x18000f39b  mov     eax, 8007000Eh
0x18000f3a0  mov     rcx, [rsp+168h+var_28]
0x18000f3a8  xor     rcx, rsp; StackCookie
0x18000f3ab  call    __security_check_cookie
0x18000f3b0  mov     rbx, [rsp+168h+arg_18]
0x18000f3b8  add     rsp, 150h
0x18000f3bf  pop     r14
0x18000f3c1  pop     rdi
0x18000f3c2  pop     rsi
0x18000f3c3  retn
```
