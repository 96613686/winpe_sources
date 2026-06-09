# NaturalLanguage6::TextChunk::BasicProcess(_com_ptr_t<_com_IIID<NaturalLanguage6::IRangedTextSource,&__s_GUID const _GUID_685d9b71_16da_49ba_bf67_a734b533217e>>,_com_ptr_t<_com_IIID<NaturalLanguage6::IRangedTextSink,&__s_GUID const _GUID_c349b170_b5ad_47bf_9a9c_85649e1674fd>>)

- ea: `0x18003a2a0`
- end: `0x18003a5a9`
- name: `?BasicProcess@TextChunk@NaturalLanguage6@@IEAAJV?$_com_ptr_t@V?$_com_IIID@UIRangedTextSource@NaturalLanguage6@@$1?_GUID_685d9b71_16da_49ba_bf67_a734b533217e@@3U__s_GUID@@B@@@@V?$_com_ptr_t@V?$_com_IIID@UIRangedTextSink@NaturalLanguage6@@$1?_GUID_c349b170_b5ad_47bf_9a9c_85649e1674fd@@3U__s_GUID@@B@@@@@Z`
- size: `777`
- prototype: `__int64 __fastcall(__int64 **this, __int64 *, struct NaturalLanguage6::IRangedTextSink **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18005a6a0`

## callees

- `0x180003e28`
- `0x180036b04`
- `0x18003757c`
- `0x18003a2a0`
- `0x18003a5b0`
- `0x18003a5fc`
- `0x180051c84`
- `0x1800b0010`

## import_xrefs

- `msvcrt!free` at `0x18003a2eb`
- `msvcrt!free` at `0x18003a2eb`

## pseudocode

```c
__int64 __fastcall NaturalLanguage6::TextChunk::BasicProcess(
        __int64 **this,
        __int64 *a2,
        struct NaturalLanguage6::IRangedTextSink **a3)
{
  __int64 *v6; // rcx
  __int64 v7; // rax
  struct IUnknown *v8; // rax
  __int64 v9; // rax
  __int64 *v10; // r12
  __int64 v11; // r13
  struct IUnknown *v12; // r15
  int v13; // eax
  __int64 v14; // r9
  struct IUnknown *v15; // rax
  __int16 IsEndOfText; // ax
  struct IUnknown *v17; // r15
  int v18; // eax
  _com_error *v20; // rbx
  __int64 v21; // [rsp+30h] [rbp-A8h] BYREF
  __int64 v22; // [rsp+38h] [rbp-A0h] BYREF
  __int64 v23; // [rsp+40h] [rbp-98h] BYREF
  __int64 v24; // [rsp+48h] [rbp-90h] BYREF
  void **v25; // [rsp+50h] [rbp-88h] BYREF
  char v26; // [rsp+58h] [rbp-80h]
  bool v27; // [rsp+59h] [rbp-7Fh]
  __int64 *v28; // [rsp+60h] [rbp-78h]
  __int64 *v29; // [rsp+68h] [rbp-70h]
  __int128 v30; // [rsp+70h] [rbp-68h]
  __int64 v31; // [rsp+80h] [rbp-58h]
  _BYTE v32[8]; // [rsp+88h] [rbp-50h] BYREF
  _com_error *v33; // [rsp+90h] [rbp-48h] BYREF
  void *retaddr; // [rsp+D8h] [rbp+0h]
  unsigned int v37; // [rsp+F8h] [rbp+20h] BYREF

  v31 = -2;
  try
  {
    CArray<_com_ptr_t<_com_IIID<NaturalLanguage6::ILexicon,&__s_GUID const _GUID_004cd7e2_8b63_4ef9_8d46_080cdbbe47af>>,CArrayAllocator_malloc>::DestructElements(
      this,
      this[6],
      this[7]);
    if ( !*((_BYTE *)this + 72) )
    {
      v6 = this[6];
      if ( v6 )
        free(v6);
      this[6] = 0;
      this[8] = 0;
    }
    this[7] = 0;
    v23 = 0;
    v7 = _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::operator->(a2);
    NaturalLanguage6::IRangedTextSource::GetRange(v7, &v22);
    v21 = v22;
    v23 = (unsigned int)v22;
    v25 = &NaturalLanguage6::SFlushBufferedCommits::`vftable';
    v26 = 1;
    v28 = &v21;
    v29 = &v23;
    *(_QWORD *)&v30 = this;
    v8 = (struct IUnknown *)_com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::operator->(a2);
    v27 = NaturalLanguage6::IRangedTextSource::GetIsEndOfText(v8) != 0;
    *((_QWORD *)&v30 + 1) = *a3;
    this[2][15] = (__int64)&v25;
    do
    {
      v9 = _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::operator->(a2);
      v22 = *(_QWORD *)NaturalLanguage6::IRangedTextSource::GetRange(v9, v32);
      v21 = v22;
      (*(void (__fastcall **)(__int64 *))(*this[2] + 328))(this[2]);
      v10 = this[2];
      v11 = *v10;
      v12 = (struct IUnknown *)_com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::operator->(a2);
      v24 = 0;
      v13 = ((__int64 (__fastcall *)(struct IUnknown *, __int64 *))v12->lpVtbl[1].QueryInterface)(v12, &v24);
      if ( v13 < 0 )
        _com_issue_errorex(v13, v12, &GUID_685d9b71_16da_49ba_bf67_a734b533217e);
      LOBYTE(v14) = 1;
      (*(void (__fastcall **)(__int64 *, __int64, _QWORD, __int64))(v11 + 40))(v10, v24, HIDWORD(v21), v14);
      (*(void (__fastcall **)(__int64 *))(*this[2] + 312))(this[2]);
      LODWORD(v22) = v21;
      v15 = (struct IUnknown *)_com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::operator->(a2);
      IsEndOfText = NaturalLanguage6::IRangedTextSource::GetIsEndOfText(v15);
      v27 = IsEndOfText != 0;
      if ( IsEndOfText )
        break;
      v17 = (struct IUnknown *)_com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::operator->(a2);
      LOWORD(v37) = 0;
      v18 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, unsigned int *))v17->lpVtbl[2].Release)(v17, v22, &v37);
      if ( v18 < 0 )
        _com_issue_errorex(v18, v17, &GUID_685d9b71_16da_49ba_bf67_a734b533217e);
    }
    while ( (_WORD)v37 );
    if ( (unsigned int)((this[2][12] - this[2][13]) >> 6) )
      NaturalLanguage6::TextChunk::FlushBufferedCommits((NaturalLanguage6::TextChunk *)this, *a3);
    this[2][15] = 0;
    v30 = 0;
  }
  catch ( _com_error *v33 )
  {
    v20 = v33;
    ImxTraceCatch(1, *((unsigned int *)v33 + 2), retaddr);
    v37 = *((_DWORD *)v20 + 2);
    if ( *a2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)*a2 + 16LL))(*a2);
    if ( *a3 )
      (*(void (__fastcall **)(struct NaturalLanguage6::IRangedTextSink *))(*(_QWORD *)*a3 + 16LL))(*a3);
    return v37;
  }
  catch ( exception )
  {
    ImxTraceCatch(2, 2147549183LL, retaddr);
    if ( *a2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)*a2 + 16LL))(*a2);
    if ( *a3 )
      (*(void (__fastcall **)(struct NaturalLanguage6::IRangedTextSink *))(*(_QWORD *)*a3 + 16LL))(*a3);
    return 2147549183LL;
  }
  CArray<_com_ptr_t<_com_IIID<NaturalLanguage6::ILexicon,&__s_GUID const _GUID_004cd7e2_8b63_4ef9_8d46_080cdbbe47af>>,CArrayAllocator_malloc>::DestructElements(
    this,
    this[6],
    this[7]);
  if ( !*((_BYTE *)this + 72) )
  {
    v6 = this[6];
    if ( v6 )
      free(v6);
    this[6] = 0;
    this[8] = 0;
  }
  this[7] = 0;
}

```

## disassembly

```asm
0x18003a2a0  mov     rax, rsp
0x18003a2a3  mov     [rax+18h], r8
0x18003a2a7  mov     [rax+10h], rdx
0x18003a2ab  push    rbx
0x18003a2ac  push    rsi
0x18003a2ad  push    rdi
0x18003a2ae  push    r12
0x18003a2b0  push    r13
0x18003a2b2  push    r14
0x18003a2b4  push    r15
0x18003a2b6  sub     rsp, 0A0h
0x18003a2bd  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x18003a2c5  mov     r14, r8
0x18003a2c8  mov     rsi, rdx
0x18003a2cb  mov     rdi, rcx
0x18003a2ce  mov     r8, [rcx+38h]
0x18003a2d2  mov     rdx, [rcx+30h]
0x18003a2d6  call    ?DestructElements@?$CArray@V?$_com_ptr_t@V?$_com_IIID@UILexicon@NaturalLanguage6@@$1?_GUID_004cd7e2_8b63_4ef9_8d46_080cdbbe47af@@3U__s_GUID@@B@@@@VCArrayAllocator_malloc@@@@AEAAXPEAX_K@Z; CArray<_com_ptr_t<_com_IIID<NaturalLanguage6::ILexicon,&__s_GUID const _GUID_004cd7e2_8b63_4ef9_8d46_080cdbbe47af>>,CArrayAllocator_malloc>::DestructElements(void *,unsigned __int64)
0x18003a2db  xor     ebx, ebx
0x18003a2dd  cmp     [rdi+48h], bl
0x18003a2e0  jnz     short loc_18003A2F9
0x18003a2e2  mov     rcx, [rdi+30h]; Block
0x18003a2e6  test    rcx, rcx
0x18003a2e9  jz      short loc_18003A2F1
0x18003a2eb  call    cs:__imp_free
0x18003a2f1  mov     [rdi+30h], rbx
0x18003a2f5  mov     [rdi+40h], rbx
0x18003a2f9  mov     [rdi+38h], rbx
0x18003a2fd  mov     [rsp+0D8h+var_A8], rbx
0x18003a302  mov     [rsp+0D8h+var_98], rbx
0x18003a307  mov     rcx, rsi
0x18003a30a  call    ??C?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@QEBAPEAUCUserData@@XZ; _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::operator->(void)
0x18003a30f  lea     rdx, [rsp+0D8h+var_A0]
0x18003a314  mov     rcx, rax
0x18003a317  call    ?GetRange@IRangedTextSource@NaturalLanguage6@@QEAA?AUSTextRange@2@XZ; NaturalLanguage6::IRangedTextSource::GetRange(void)
0x18003a31c  mov     rax, [rsp+0D8h+var_A0]
0x18003a321  mov     [rsp+0D8h+var_A8], rax
0x18003a326  mov     dword ptr [rsp+0D8h+var_98], eax
0x18003a32a  mov     dword ptr [rsp+0D8h+var_98+4], ebx
0x18003a32e  lea     rax, ??_7ILangDataUnloadListener@@6B@; const ILangDataUnloadListener::`vftable'
0x18003a335  mov     [rsp+0D8h+var_88], rax
0x18003a33a  lea     rax, ??_7SFlushBufferedCommits@NaturalLanguage6@@6B@; const NaturalLanguage6::SFlushBufferedCommits::`vftable'
0x18003a341  mov     [rsp+0D8h+var_88], rax
0x18003a346  mov     [rsp+0D8h+var_80], 1
0x18003a34b  lea     rax, [rsp+0D8h+var_A8]
0x18003a350  mov     [rsp+0D8h+var_78], rax
0x18003a355  lea     rax, [rsp+0D8h+var_98]
0x18003a35a  mov     [rsp+0D8h+var_70], rax
0x18003a35f  mov     qword ptr [rsp+0D8h+var_68], rdi
0x18003a364  mov     rcx, rsi
0x18003a367  call    ??C?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@QEBAPEAUCUserData@@XZ; _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::operator->(void)
0x18003a36c  mov     rcx, rax; this
0x18003a36f  call    ?GetIsEndOfText@IRangedTextSource@NaturalLanguage6@@QEAAFXZ; NaturalLanguage6::IRangedTextSource::GetIsEndOfText(void)
0x18003a374  test    ax, ax
0x18003a377  setnz   [rsp+0D8h+var_7F]
0x18003a37c  mov     rax, [r14]
0x18003a37f  mov     qword ptr [rsp+0D8h+var_68+8], rax
0x18003a384  mov     rax, [rdi+10h]
0x18003a388  lea     rcx, [rsp+0D8h+var_88]
0x18003a38d  mov     [rax+78h], rcx
0x18003a391  mov     rcx, rsi
0x18003a394  call    ??C?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@QEBAPEAUCUserData@@XZ; _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::operator->(void)
0x18003a399  lea     rdx, [rsp+0D8h+var_50]
0x18003a3a1  mov     rcx, rax
0x18003a3a4  call    ?GetRange@IRangedTextSource@NaturalLanguage6@@QEAA?AUSTextRange@2@XZ; NaturalLanguage6::IRangedTextSource::GetRange(void)
0x18003a3a9  mov     rcx, [rax]
0x18003a3ac  mov     [rsp+0D8h+var_A0], rcx
0x18003a3b1  mov     eax, ecx
0x18003a3b3  mov     dword ptr [rsp+0D8h+var_A8], ecx
0x18003a3b7  shr     rcx, 20h
0x18003a3bb  mov     dword ptr [rsp+0D8h+var_A8+4], ecx
0x18003a3bf  mov     rcx, [rdi+10h]
0x18003a3c3  mov     rax, [rcx]
0x18003a3c6  mov     rax, [rax+148h]
0x18003a3cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a3d2  mov     r12, [rdi+10h]
0x18003a3d6  mov     r13, [r12]
0x18003a3da  mov     rcx, rsi
0x18003a3dd  call    ??C?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@QEBAPEAUCUserData@@XZ; _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::operator->(void)
0x18003a3e2  mov     r15, rax
0x18003a3e5  mov     [rsp+0D8h+var_90], rbx
0x18003a3ea  mov     rcx, [rax]
0x18003a3ed  mov     rax, [rcx+18h]
0x18003a3f1  lea     rdx, [rsp+0D8h+var_90]
0x18003a3f6  mov     rcx, r15
0x18003a3f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a3fe  test    eax, eax
0x18003a400  jns     short loc_18003A413
0x18003a402  lea     r8, _GUID_685d9b71_16da_49ba_bf67_a734b533217e; struct _GUID *
0x18003a409  mov     rdx, r15; struct IUnknown *
0x18003a40c  mov     ecx, eax; int
0x18003a40e  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x18003a413  mov     r8d, dword ptr [rsp+0D8h+var_A8+4]
0x18003a418  mov     r9b, 1
0x18003a41b  mov     rdx, [rsp+0D8h+var_90]
0x18003a420  mov     rcx, r12
0x18003a423  mov     rax, [r13+28h]
0x18003a427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a42c  mov     rcx, [rdi+10h]
0x18003a430  mov     rax, [rcx]
0x18003a433  mov     rax, [rax+138h]
0x18003a43a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a43f  mov     eax, dword ptr [rsp+0D8h+var_A8]
0x18003a443  mov     dword ptr [rsp+0D8h+var_A0], eax
0x18003a447  mov     rcx, rsi
0x18003a44a  call    ??C?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@QEBAPEAUCUserData@@XZ; _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::operator->(void)
0x18003a44f  mov     rcx, rax; this
0x18003a452  call    ?GetIsEndOfText@IRangedTextSource@NaturalLanguage6@@QEAAFXZ; NaturalLanguage6::IRangedTextSource::GetIsEndOfText(void)
0x18003a457  test    ax, ax
0x18003a45a  setnz   [rsp+0D8h+var_7F]
0x18003a45f  test    ax, ax
0x18003a462  jnz     short loc_18003A4B6
0x18003a464  mov     rcx, rsi
0x18003a467  call    ??C?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@QEBAPEAUCUserData@@XZ; _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::operator->(void)
0x18003a46c  mov     r15, rax
0x18003a46f  mov     word ptr [rsp+0D8h+arg_18], bx
0x18003a477  mov     rcx, [rax]
0x18003a47a  mov     rax, [rcx+40h]
0x18003a47e  lea     r8, [rsp+0D8h+arg_18]
0x18003a486  mov     rdx, [rsp+0D8h+var_A0]
0x18003a48b  mov     rcx, r15
0x18003a48e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a493  test    eax, eax
0x18003a495  jns     short loc_18003A4A8
0x18003a497  lea     r8, _GUID_685d9b71_16da_49ba_bf67_a734b533217e; struct _GUID *
0x18003a49e  mov     rdx, r15; struct IUnknown *
0x18003a4a1  mov     ecx, eax; int
0x18003a4a3  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x18003a4a8  cmp     word ptr [rsp+0D8h+arg_18], bx
0x18003a4b0  jnz     loc_18003A391
0x18003a4b6  mov     rax, [rdi+10h]
0x18003a4ba  mov     rcx, [rax+60h]
0x18003a4be  sub     rcx, [rax+68h]
0x18003a4c2  sar     rcx, 6
0x18003a4c6  test    ecx, ecx
0x18003a4c8  jz      short loc_18003A4D5
0x18003a4ca  mov     rdx, [r14]; struct NaturalLanguage6::IRangedTextSink *
0x18003a4cd  mov     rcx, rdi; this
0x18003a4d0  call    ?FlushBufferedCommits@TextChunk@NaturalLanguage6@@QEAAXPEAUIRangedTextSink@2@@Z; NaturalLanguage6::TextChunk::FlushBufferedCommits(NaturalLanguage6::IRangedTextSink *)
0x18003a4d5  mov     rax, [rdi+10h]
0x18003a4d9  mov     [rax+78h], rbx
0x18003a4dd  xorps   xmm0, xmm0
0x18003a4e0  movdqu  [rsp+0D8h+var_68], xmm0
0x18003a4e6  mov     rcx, [rsi]
0x18003a4e9  test    rcx, rcx
0x18003a4ec  jz      short loc_18003A4FB
0x18003a4ee  mov     rax, [rcx]
0x18003a4f1  mov     rax, [rax+10h]
0x18003a4f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a4fa  nop
0x18003a4fb  mov     rcx, [r14]
0x18003a4fe  test    rcx, rcx
0x18003a501  jz      short loc_18003A50F
0x18003a503  mov     rax, [rcx]
0x18003a506  mov     rax, [rax+10h]
0x18003a50a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a50f  xor     eax, eax
0x18003a511  jmp     loc_18003A596
0x18003a516  mov     rax, [rsp+0D8h+arg_8]
0x18003a51e  mov     rcx, [rax]
0x18003a521  test    rcx, rcx
0x18003a524  jz      short loc_18003A533
0x18003a526  mov     rax, [rcx]
0x18003a529  mov     rax, [rax+10h]
0x18003a52d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a532  nop
0x18003a533  mov     rax, [rsp+0D8h+arg_10]
0x18003a53b  mov     rcx, [rax]
0x18003a53e  test    rcx, rcx
0x18003a541  jz      short loc_18003A54F
0x18003a543  mov     rax, [rcx]
0x18003a546  mov     rax, [rax+10h]
0x18003a54a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a54f  mov     eax, [rsp+0D8h+arg_18]
0x18003a556  jmp     short loc_18003A596
0x18003a558  mov     rax, [rsp+0D8h+arg_8]
0x18003a560  mov     rcx, [rax]
0x18003a563  test    rcx, rcx
0x18003a566  jz      short loc_18003A575
0x18003a568  mov     rax, [rcx]
0x18003a56b  mov     rax, [rax+10h]
0x18003a56f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a574  nop
0x18003a575  mov     rax, [rsp+0D8h+arg_10]
0x18003a57d  mov     rcx, [rax]
0x18003a580  test    rcx, rcx
0x18003a583  jz      short loc_18003A591
0x18003a585  mov     rax, [rcx]
0x18003a588  mov     rax, [rax+10h]
0x18003a58c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a591  mov     eax, 8000FFFFh
0x18003a596  add     rsp, 0A0h
0x18003a59d  pop     r15
0x18003a59f  pop     r14
0x18003a5a1  pop     r13
0x18003a5a3  pop     r12
0x18003a5a5  pop     rdi
0x18003a5a6  pop     rsi
0x18003a5a7  pop     rbx
0x18003a5a8  retn
```
