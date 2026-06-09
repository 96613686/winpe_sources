# Microsoft::Windows::Performance::CCvDDCache::Add(ushort const *,ulong,ulong,_CVDD const *,ulong const *,CODEVIEW_INFORMATION_1 const *,ulong,ulong,EMBEDDED_PDB_INFORMATION *,bool,ushort const *,bool *)

- ea: `0x1800093c0`
- end: `0x18000965d`
- name: `?Add@CCvDDCache@Performance@Windows@Microsoft@@QEAAJPEBGKKPEBT_CVDD@@PEBKPEBUCODEVIEW_INFORMATION_1@@KKPEAUEMBEDDED_PDB_INFORMATION@@_N0PEA_N@Z`
- size: `669`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CCvDDCache *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, const union _CVDD *, const unsigned int *, const struct CODEVIEW_INFORMATION_1 *, unsigned int, unsigned int, struct EMBEDDED_PDB_INFORMATION *, bool, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000a30c`

## callees

- `0x180008d5c`
- `0x1800093c0`
- `0x180009660`
- `0x18000d080`
- `0x18000d360`
- `0x18000d48c`
- `0x18000d560`
- `0x180013598`
- `0x1800268f4`
- `0x180026e30`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
  __int64 v17; // rax
  __int64 v18; // rax
  const unsigned int *v19; // rbx
  __int64 *v20; // rdi
  __int64 v21; // rax
  __int64 result; // rax
  __int64 v23; // [rsp+68h] [rbp-180h] BYREF
  __int64 *v24; // [rsp+70h] [rbp-178h] BYREF
  int v25; // [rsp+78h] [rbp-170h]
  const unsigned int *v26; // [rsp+80h] [rbp-168h] BYREF
  __int64 v27[3]; // [rsp+88h] [rbp-160h] BYREF
  _BYTE v28[8]; // [rsp+A0h] [rbp-148h] BYREF
  void *Block; // [rsp+A8h] [rbp-140h]
  __int64 v30; // [rsp+B8h] [rbp-130h]
  unsigned __int64 v31; // [rsp+C0h] [rbp-128h]
  _BYTE v32[8]; // [rsp+C8h] [rbp-120h] BYREF
  void *v33; // [rsp+D0h] [rbp-118h]
  __int64 v34; // [rsp+E0h] [rbp-108h]
  unsigned __int64 v35; // [rsp+E8h] [rbp-100h]
  _BYTE v36[176]; // [rsp+F0h] [rbp-F8h] BYREF

  v27[2] = -2;
  LODWORD(v24) = a3;
  v26 = a6;
  v27[0] = (__int64)a7;
  LODWORD(v23) = a8;
  v25 = a9;
  try
  {
    v35 = 7;
    v34 = 0;
    LOWORD(v33) = 0;
    std::wstring::assign(v32, a12);
    v31 = 7;
    v30 = 0;
    LOWORD(Block) = 0;
    std::wstring::assign(v28, a2);
    v17 = Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(
            (__int64)v36,
            (__int64)v28,
            (__int64)v32,
            a4,
            (__int64)a5,
            (__int64)v26,
            v27[0],
            a3,
            v23,
            v25,
            a10,
            a11);
    std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::push_back(this, v17);
    Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD((Microsoft::Windows::Performance::CCvDDCache::CCvDD *)v36);
    if ( v31 >= 8 )
      operator delete(Block);
    v31 = 7;
    v30 = 0;
    LOWORD(Block) = 0;
    if ( v35 >= 8 )
      operator delete(v33);
    v18 = *((_QWORD *)this + 1);
    v19 = (const unsigned int *)(*(_QWORD *)(v18 + 8) + 16LL);
    v20 = (__int64 *)(*(_QWORD *)(v18 + 8) + 24LL);
    if ( *(_QWORD *)(*(_QWORD *)(v18 + 8) + 48LL) < 8u )
      v23 = *(_QWORD *)(v18 + 8) + 24LL;
    else
      v23 = *v20;
    v21 = std::map<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::operator[](
            (char *)this + 24,
            &v24);
    *(_QWORD *)std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](
                 v21,
                 &v23) = v19;
    if ( *((_QWORD *)v19 + 4) < 8u )
      v24 = v20;
    else
      v24 = (__int64 *)*v20;
    *(_QWORD *)std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](
                 (char *)this + 48,
                 &v24) = v19;
    if ( a13 )
    {
      v26 = v19;
      *a13 = *(_BYTE *)(std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::insert(
                          (char *)this + 72,
                          v27,
                          &v26)
                      + 8);
    }
    if ( a10 && *(_DWORD *)a10 )
      a10[1] = (const void *)*((_QWORD *)v19 + 15);
    result = 0;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800093c0  mov     r11, rsp
0x1800093c3  push    rbx
0x1800093c4  push    rsi
0x1800093c5  push    rdi
0x1800093c6  push    r12
0x1800093c8  push    r13
0x1800093ca  push    r14
0x1800093cc  push    r15
0x1800093ce  sub     rsp, 1B0h
0x1800093d5  mov     qword ptr [r11-150h], 0FFFFFFFFFFFFFFFEh
0x1800093e0  mov     rax, cs:__security_cookie
0x1800093e7  xor     rax, rsp
0x1800093ea  mov     [rsp+1E8h+var_48], rax
0x1800093f2  mov     r12d, r9d
0x1800093f5  mov     edi, r8d
0x1800093f8  mov     rbx, rdx
0x1800093fb  mov     rsi, rcx
0x1800093fe  mov     dword ptr [rsp+1E8h+var_178], r8d
0x180009403  mov     r13, [rsp+1E8h+arg_20]
0x18000940b  mov     rax, [rsp+1E8h+arg_28]
0x180009413  mov     [rsp+1E8h+var_168], rax
0x18000941b  mov     rax, [rsp+1E8h+arg_30]
0x180009423  mov     [rsp+1E8h+var_160], rax
0x18000942b  mov     eax, [rsp+1E8h+arg_38]
0x180009432  mov     dword ptr [rsp+1E8h+var_180], eax
0x180009436  mov     eax, [rsp+1E8h+arg_40]
0x18000943d  mov     [rsp+1E8h+var_170], eax
0x180009441  mov     r14, [rsp+1E8h+arg_48]
0x180009449  mov     al, [rsp+1E8h+arg_50]
0x180009450  mov     [rsp+1E8h+var_188], al
0x180009454  mov     rdx, [rsp+1E8h+arg_58]
0x18000945c  mov     r15, [rsp+1E8h+arg_60]
0x180009464  mov     qword ptr [r11-100h], 7
0x18000946f  xor     eax, eax
0x180009471  mov     [r11-108h], rax
0x180009478  mov     word ptr [rsp+1E8h+var_118], ax
0x180009480  lea     rcx, [r11-120h]
0x180009487  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000948c  nop
0x18000948d  mov     [rsp+1E8h+var_128], 7
0x180009499  xor     eax, eax
0x18000949b  mov     [rsp+1E8h+var_130], rax
0x1800094a3  mov     word ptr [rsp+1E8h+Block], ax
0x1800094ab  mov     rdx, rbx
0x1800094ae  lea     rcx, [rsp+1E8h+var_148]
0x1800094b6  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x1800094bb  nop
0x1800094bc  mov     al, [rsp+1E8h+var_188]
0x1800094c0  mov     [rsp+1E8h+var_190], al
0x1800094c4  mov     [rsp+1E8h+var_198], r14
0x1800094c9  mov     eax, [rsp+1E8h+var_170]
0x1800094cd  mov     [rsp+1E8h+var_1A0], eax
0x1800094d1  mov     eax, dword ptr [rsp+1E8h+var_180]
0x1800094d5  mov     [rsp+1E8h+var_1A8], eax
0x1800094d9  mov     [rsp+1E8h+var_1B0], edi
0x1800094dd  mov     rax, [rsp+1E8h+var_160]
0x1800094e5  mov     [rsp+1E8h+var_1B8], rax
0x1800094ea  mov     rax, [rsp+1E8h+var_168]
0x1800094f2  mov     [rsp+1E8h+var_1C0], rax
0x1800094f7  mov     [rsp+1E8h+var_1C8], r13
0x1800094fc  mov     r9d, r12d
0x1800094ff  lea     r8, [rsp+1E8h+var_120]
0x180009507  lea     rdx, [rsp+1E8h+var_148]
0x18000950f  lea     rcx, [rsp+1E8h+var_F8]
0x180009517  call    ??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@0KPEBT_CVDD@@PEBKPEBUCODEVIEW_INFORMATION_1@@KKKPEBUEMBEDDED_PDB_INFORMATION@@_N@Z; Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(std::wstring const &,std::wstring const &,ulong,_CVDD const *,ulong const *,CODEVIEW_INFORMATION_1 const *,ulong,ulong,ulong,EMBEDDED_PDB_INFORMATION const *,bool)
0x18000951c  nop
0x18000951d  mov     rdx, rax
0x180009520  mov     rcx, rsi
0x180009523  call    ?push_back@?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@QEAAXAEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z; std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::push_back(Microsoft::Windows::Performance::CCvDDCache::CCvDD const &)
0x180009528  nop
0x180009529  lea     rcx, [rsp+1E8h+var_F8]; this
0x180009531  call    ??1CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(void)
0x180009536  nop
0x180009537  cmp     [rsp+1E8h+var_128], 8
0x180009540  jb      short loc_18000954F
0x180009542  mov     rcx, [rsp+1E8h+Block]; Block
0x18000954a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000954f  mov     [rsp+1E8h+var_128], 7
0x18000955b  xor     r12d, r12d
0x18000955e  mov     [rsp+1E8h+var_130], r12
0x180009566  mov     word ptr [rsp+1E8h+Block], r12w
0x18000956f  cmp     [rsp+1E8h+var_100], 8
0x180009578  jb      short loc_180009587
0x18000957a  mov     rcx, [rsp+1E8h+var_118]; Block
0x180009582  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009587  mov     rax, [rsi+8]
0x18000958b  mov     rbx, [rax+8]
0x18000958f  add     rbx, 10h
0x180009593  lea     rdi, [rbx+8]
0x180009597  cmp     qword ptr [rbx+20h], 8
0x18000959c  jb      short loc_1800095A8
0x18000959e  mov     rax, [rdi]
0x1800095a1  mov     [rsp+1E8h+var_180], rax
0x1800095a6  jmp     short loc_1800095AD
0x1800095a8  mov     [rsp+1E8h+var_180], rdi
0x1800095ad  lea     rcx, [rsi+18h]
0x1800095b1  lea     rdx, [rsp+1E8h+var_178]
0x1800095b6  call    ??A?$map@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@QEAAAEAV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@1@AEBK@Z; std::map<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::operator[](ulong const &)
0x1800095bb  lea     rdx, [rsp+1E8h+var_180]
0x1800095c0  mov     rcx, rax
0x1800095c3  call    ??A?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@AEBQEBG@Z; std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](ushort const * const &)
0x1800095c8  mov     [rax], rbx
0x1800095cb  cmp     qword ptr [rbx+20h], 8
0x1800095d0  jb      short loc_1800095DC
0x1800095d2  mov     rax, [rdi]
0x1800095d5  mov     [rsp+1E8h+var_178], rax
0x1800095da  jmp     short loc_1800095E1
0x1800095dc  mov     [rsp+1E8h+var_178], rdi
0x1800095e1  lea     rcx, [rsi+30h]
0x1800095e5  lea     rdx, [rsp+1E8h+var_178]
0x1800095ea  call    ??A?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@AEBQEBG@Z; std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](ushort const * const &)
0x1800095ef  mov     [rax], rbx
0x1800095f2  test    r15, r15
0x1800095f5  jz      short loc_18000961E
0x1800095f7  mov     [rsp+1E8h+var_168], rbx
0x1800095ff  lea     rcx, [rsi+48h]
0x180009603  lea     r8, [rsp+1E8h+var_168]
0x18000960b  lea     rdx, [rsp+1E8h+var_160]
0x180009613  call    ?insert@?$_Tree@V?$_Tset_traits@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessCCvDDPtrByImageId@2345@V?$allocator@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@Viterator@?$_Tree@V?$_Tset_traits@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessCCvDDPtrByImageId@2345@V?$allocator@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@$0A@@std@@@std@@_N@2@AEBQEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z; std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::insert(Microsoft::Windows::Performance::CCvDDCache::CCvDD const * const &)
0x180009618  mov     al, [rax+8]
0x18000961b  mov     [r15], al
0x18000961e  test    r14, r14
0x180009621  jz      short loc_180009630
0x180009623  cmp     [r14], r12d
0x180009626  jz      short loc_180009630
0x180009628  mov     rax, [rbx+78h]
0x18000962c  mov     [r14+8], rax
0x180009630  xor     eax, eax
0x180009632  jmp     short loc_180009639
0x180009634  mov     eax, 8007000Eh
0x180009639  mov     rcx, [rsp+1E8h+var_48]
0x180009641  xor     rcx, rsp; StackCookie
0x180009644  call    __security_check_cookie
0x180009649  add     rsp, 1B0h
0x180009650  pop     r15
0x180009652  pop     r14
0x180009654  pop     r13
0x180009656  pop     r12
0x180009658  pop     rdi
0x180009659  pop     rsi
0x18000965a  pop     rbx
0x18000965b  retn
```
