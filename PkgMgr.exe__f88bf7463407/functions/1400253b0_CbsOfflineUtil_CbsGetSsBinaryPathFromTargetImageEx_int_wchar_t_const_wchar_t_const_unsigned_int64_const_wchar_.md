# CbsOfflineUtil::CbsGetSsBinaryPathFromTargetImageEx(int,wchar_t const *,wchar_t const *,unsigned __int64 const *,wchar_t const *,wchar_t * *,wchar_t * *,unsigned __int64 *)

- ea: `0x1400253b0`
- end: `0x140025650`
- name: `?CbsGetSsBinaryPathFromTargetImageEx@CbsOfflineUtil@@UEAAJHPEB_W0PEB_K0PEAPEA_W2PEA_K@Z`
- size: `672`
- prototype: `int(CbsOfflineUtil *__hidden this, int, const wchar_t *, const wchar_t *, const unsigned __int64 *, const wchar_t *, wchar_t **, wchar_t **, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x140002360`
- `0x1400056ac`
- `0x140024bd8`
- `0x140024c94`
- `0x1400251e4`
- `0x1400253b0`
- `0x140025824`
- `0x1400258f0`
- `0x140025b30`
- `0x140025d80`
- `0x140025e0c`

## pseudocode

```c
__int64 __fastcall CbsOfflineUtil::CbsGetSsBinaryPathFromTargetImageEx(
        CbsOfflineUtil *this,
        int a2,
        wchar_t *a3,
        wchar_t *a4,
        unsigned __int64 *a5,
        wchar_t *a6,
        wchar_t **a7,
        wchar_t **a8,
        unsigned __int64 *a9)
{
  int v10; // eax
  const wchar_t *v12; // rcx
  wchar_t *v13; // r12
  unsigned __int64 *v14; // rdx
  int TemporyFolderForShimBinary; // eax
  int v16; // ebx
  __int64 v17; // rdx
  unsigned __int64 v18; // r9
  bool v19; // dl
  int v20; // eax
  int SssFromTargetImage; // eax
  __int64 v22; // rdx
  wchar_t *v23; // rax
  int v25; // [rsp+20h] [rbp-A9h]
  wchar_t *v26; // [rsp+30h] [rbp-99h] BYREF
  wchar_t *v27; // [rsp+38h] [rbp-91h] BYREF
  unsigned __int64 *v28; // [rsp+40h] [rbp-89h]
  wchar_t *v29; // [rsp+48h] [rbp-81h]
  const wchar_t *v30; // [rsp+50h] [rbp-79h]
  wchar_t **v31; // [rsp+58h] [rbp-71h]
  unsigned __int64 v32; // [rsp+60h] [rbp-69h] BYREF
  __int128 v33; // [rsp+70h] [rbp-59h] BYREF
  __int64 v34; // [rsp+80h] [rbp-49h]
  __int64 v35; // [rsp+88h] [rbp-41h]
  __int64 v36; // [rsp+90h] [rbp-39h]
  __int64 v37; // [rsp+98h] [rbp-31h]
  __int64 v38; // [rsp+A0h] [rbp-29h]
  __int64 v39; // [rsp+A8h] [rbp-21h]
  char v40; // [rsp+B0h] [rbp-19h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+3Fh]

  v10 = a2;
  v12 = a6;
  v31 = a8;
  LODWORD(v32) = a2;
  v13 = 0;
  v14 = a5;
  v29 = a4;
  v28 = a5;
  v30 = a6;
  v27 = 0;
  v26 = 0;
  if ( a9 )
    *a9 = 0;
  if ( !*((_QWORD *)this + 3) )
  {
    if ( !*((_QWORD *)this + 2) )
    {
      TemporyFolderForShimBinary = CbsOfflineUtil::CreateTemporyFolderForShimBinary(this);
      v16 = TemporyFolderForShimBinary;
      if ( TemporyFolderForShimBinary < 0 )
      {
        v17 = 179;
LABEL_9:
        v18 = (unsigned int)TemporyFolderForShimBinary;
LABEL_10:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"onecore\\base\\cbs\\offlineutil\\cbsofflineimagestack.cpp",
          (const char *)v18,
          v25);
        goto LABEL_39;
      }
    }
    TemporyFolderForShimBinary = CbsLoadSssFromTargetImageEx(a3, (CbsOfflineUtil *)((char *)this + 24));
    v16 = TemporyFolderForShimBinary;
    if ( TemporyFolderForShimBinary < 0 )
    {
      v17 = 182;
      goto LABEL_9;
    }
    v10 = v32;
    v12 = v30;
    v14 = v28;
  }
  if ( !*((_QWORD *)this + 4) )
  {
    TemporyFolderForShimBinary = Windows::AutoSsShim::Bind(
                                   (CbsOfflineUtil *)((char *)this + 24),
                                   a3,
                                   v10 != 0,
                                   v12,
                                   v14);
    v16 = TemporyFolderForShimBinary;
    if ( TemporyFolderForShimBinary < 0 )
    {
      v17 = 190;
      goto LABEL_9;
    }
    if ( *((_QWORD *)this + 7) )
    {
      v20 = Windows::AutoSsShim::Preload((CbsOfflineUtil *)((char *)this + 24), v19);
      v16 = 0;
      if ( v20 != -2147024809 )
        v16 = v20;
      if ( v16 < 0 )
      {
        v18 = (unsigned int)v16;
        v17 = 220;
        goto LABEL_10;
      }
    }
  }
  TemporyFolderForShimBinary = CbsGetSsBinaryPathByShim(v29, (CbsOfflineUtil *)((char *)this + 24), &v27);
  v16 = TemporyFolderForShimBinary;
  if ( TemporyFolderForShimBinary < 0 )
  {
    v17 = 227;
    goto LABEL_9;
  }
  if ( a9 && *((_QWORD *)this + 10) )
  {
    v32 = 0;
    TemporyFolderForShimBinary = Windows::AutoSsShim::GetVersion(
                                   (CbsOfflineUtil *)((char *)this + 24),
                                   (union _SSS_VERSION *)&v32);
    v16 = TemporyFolderForShimBinary;
    if ( TemporyFolderForShimBinary < 0 )
    {
      v17 = 235;
      goto LABEL_9;
    }
    *a9 = v32;
  }
  if ( a7 )
  {
    v34 = 0;
    v33 = 0;
    v35 = 0;
    v36 = 0;
    v37 = 0;
    v38 = 0;
    v39 = 0;
    v40 = 0;
    SssFromTargetImage = CbsLoadSssFromTargetImageEx(a3, (Windows::AutoSsShim *)&v33);
    v16 = SssFromTargetImage;
    if ( SssFromTargetImage < 0 )
    {
      v22 = 246;
LABEL_30:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecore\\base\\cbs\\offlineutil\\cbsofflineimagestack.cpp",
        (const char *)(unsigned int)SssFromTargetImage,
        v25);
      Windows::AutoSsShim::~AutoSsShim((Windows::AutoSsShim *)&v33);
      goto LABEL_39;
    }
    SssFromTargetImage = Windows::AutoSsShim::Bind((Windows::AutoSsShim *)&v33, a3, 0, 0, v28);
    v16 = SssFromTargetImage;
    if ( SssFromTargetImage < 0 )
    {
      v22 = 247;
      goto LABEL_30;
    }
    SssFromTargetImage = CbsGetSsBinaryPathByShim(v29, (Windows::AutoSsShim *)&v33, &v26);
    v16 = SssFromTargetImage;
    if ( SssFromTargetImage < 0 )
    {
      v22 = 248;
      goto LABEL_30;
    }
    Windows::AutoSsShim::~AutoSsShim((Windows::AutoSsShim *)&v33);
    v13 = v26;
  }
  v23 = v27;
  v27 = 0;
  *v31 = v23;
  if ( a7 )
  {
    v26 = 0;
    *a7 = v13;
  }
  v16 = 0;
LABEL_39:
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(&v26);
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(&v27);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1400253b0  mov     [rsp-8+arg_8], rbx
0x1400253b5  push    rbp
0x1400253b6  push    rsi
0x1400253b7  push    rdi
0x1400253b8  push    r12
0x1400253ba  push    r13
0x1400253bc  push    r14
0x1400253be  push    r15
0x1400253c0  lea     rbp, [rsp-7]
0x1400253c5  sub     rsp, 0D0h
0x1400253cc  mov     rax, cs:__security_cookie
0x1400253d3  xor     rax, rsp
0x1400253d6  mov     [rbp+37h+var_40], rax
0x1400253da  mov     r15, [rbp+37h+arg_40]
0x1400253e1  mov     r13, r8
0x1400253e4  mov     r8, [rbp+37h+arg_38]
0x1400253e8  mov     eax, edx
0x1400253ea  mov     r14, [rbp+37h+arg_30]
0x1400253ee  mov     rdi, rcx
0x1400253f1  mov     rcx, [rbp+37h+arg_28]
0x1400253f5  mov     [rbp+37h+var_A8], r8
0x1400253f9  xor     r8d, r8d
0x1400253fc  mov     dword ptr [rbp+37h+var_A0], edx
0x1400253ff  mov     r12d, r8d
0x140025402  mov     rdx, [rbp+37h+arg_20]
0x140025406  mov     [rsp+100h+var_B8], r9
0x14002540b  mov     [rsp+100h+var_C0], rdx
0x140025410  mov     [rbp+37h+var_B0], rcx
0x140025414  mov     [rsp+100h+var_C8], r8
0x140025419  mov     [rsp+100h+var_D0], r8
0x14002541e  test    r15, r15
0x140025421  jz      short loc_140025426
0x140025423  mov     [r15], r8
0x140025426  lea     rsi, [rdi+18h]
0x14002542a  cmp     [rsi], r8
0x14002542d  jnz     short loc_14002548B
0x14002542f  cmp     [rdi+10h], r8
0x140025433  jnz     short loc_14002544A
0x140025435  mov     rcx, rdi; this
0x140025438  call    ?CreateTemporyFolderForShimBinary@CbsOfflineUtil@@AEAAJXZ; CbsOfflineUtil::CreateTemporyFolderForShimBinary(void)
0x14002543d  mov     ebx, eax
0x14002543f  test    eax, eax
0x140025441  jns     short loc_14002544A
0x140025443  mov     edx, 0B3h
0x140025448  jmp     short loc_140025467
0x14002544a  mov     r8, [rdi+10h]
0x14002544e  mov     rdx, rsi; this
0x140025451  mov     rcx, r13; wchar_t *
0x140025454  call    CbsLoadSssFromTargetImageEx
0x140025459  xor     r8d, r8d
0x14002545c  mov     ebx, eax
0x14002545e  test    eax, eax
0x140025460  jns     short loc_14002547F
0x140025462  mov     edx, 0B6h; void *
0x140025467  mov     r9d, eax; char *
0x14002546a  mov     rcx, [rbp+3Fh]; this
0x14002546e  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\offlineutil\\cbsoff"...
0x140025475  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002547a  jmp     loc_140025613
0x14002547f  mov     eax, dword ptr [rbp+37h+var_A0]
0x140025482  mov     rcx, [rbp+37h+var_B0]
0x140025486  mov     rdx, [rsp+100h+var_C0]
0x14002548b  cmp     [rdi+20h], r8
0x14002548f  jnz     short loc_1400254DD
0x140025491  test    eax, eax
0x140025493  mov     qword ptr [rsp+100h+var_E0], rdx; unsigned __int64 *
0x140025498  mov     r9, rcx; wchar_t *
0x14002549b  mov     rdx, r13; wchar_t *
0x14002549e  setnz   r8b; bool
0x1400254a2  mov     rcx, rsi; this
0x1400254a5  call    ?Bind@AutoSsShim@Windows@@QEAAJQEB_W_N0PEB_K@Z; Windows::AutoSsShim::Bind(wchar_t const * const,bool,wchar_t const * const,unsigned __int64 const *)
0x1400254aa  mov     ebx, eax
0x1400254ac  test    eax, eax
0x1400254ae  jns     short loc_1400254B7
0x1400254b0  mov     edx, 0BEh
0x1400254b5  jmp     short loc_140025467
0x1400254b7  cmp     [rdi+38h], r12
0x1400254bb  jz      short loc_1400254DD
0x1400254bd  mov     rcx, rsi; this
0x1400254c0  call    ?Preload@AutoSsShim@Windows@@QEAAJ_N@Z; Windows::AutoSsShim::Preload(bool)
0x1400254c5  xor     ebx, ebx
0x1400254c7  cmp     eax, 80070057h
0x1400254cc  cmovnz  ebx, eax
0x1400254cf  test    ebx, ebx
0x1400254d1  jns     short loc_1400254DD
0x1400254d3  mov     r9d, ebx
0x1400254d6  mov     edx, 0DCh
0x1400254db  jmp     short loc_14002546A
0x1400254dd  mov     rcx, [rsp+100h+var_B8]; wchar_t *
0x1400254e2  lea     r8, [rsp+100h+var_C8]
0x1400254e7  mov     rdx, rsi; this
0x1400254ea  call    CbsGetSsBinaryPathByShim
0x1400254ef  mov     ebx, eax
0x1400254f1  test    eax, eax
0x1400254f3  jns     short loc_1400254FF
0x1400254f5  mov     edx, 0E3h
0x1400254fa  jmp     loc_140025467
0x1400254ff  test    r15, r15
0x140025502  jz      short loc_140025535
0x140025504  cmp     [rdi+50h], r12
0x140025508  jz      short loc_140025535
0x14002550a  xor     edi, edi
0x14002550c  lea     rdx, [rbp+37h+var_A0]; union _SSS_VERSION *
0x140025510  mov     rcx, rsi; this
0x140025513  mov     [rbp+37h+var_A0], rdi
0x140025517  call    ?GetVersion@AutoSsShim@Windows@@QEAAJPEAT_SSS_VERSION@@@Z; Windows::AutoSsShim::GetVersion(_SSS_VERSION *)
0x14002551c  mov     ebx, eax
0x14002551e  test    eax, eax
0x140025520  jns     short loc_14002552C
0x140025522  mov     edx, 0EBh
0x140025527  jmp     loc_140025467
0x14002552c  mov     rax, [rbp+37h+var_A0]
0x140025530  mov     [r15], rax
0x140025533  jmp     short loc_140025537
0x140025535  xor     edi, edi
0x140025537  test    r14, r14
0x14002553a  jz      loc_1400255F3
0x140025540  xorps   xmm0, xmm0
0x140025543  mov     [rbp+37h+var_80], rdi
0x140025547  xor     r8d, r8d
0x14002554a  movdqa  [rbp+37h+var_90], xmm0
0x14002554f  lea     rdx, [rbp+37h+var_90]; this
0x140025553  mov     [rbp+37h+var_78], rdi
0x140025557  mov     rcx, r13; wchar_t *
0x14002555a  mov     [rbp+37h+var_70], rdi
0x14002555e  mov     [rbp+37h+var_68], rdi
0x140025562  mov     [rbp+37h+var_60], rdi
0x140025566  mov     [rbp+37h+var_58], rdi
0x14002556a  mov     [rbp+37h+var_50], dil
0x14002556e  call    CbsLoadSssFromTargetImageEx
0x140025573  mov     ebx, eax
0x140025575  test    eax, eax
0x140025577  jns     short loc_14002559C
0x140025579  mov     edx, 0F6h; void *
0x14002557e  mov     rcx, [rbp+3Fh]; this
0x140025582  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\offlineutil\\cbsoff"...
0x140025589  mov     r9d, eax; char *
0x14002558c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140025591  lea     rcx, [rbp+37h+var_90]; this
0x140025595  call    ??1AutoSsShim@Windows@@QEAA@XZ; Windows::AutoSsShim::~AutoSsShim(void)
0x14002559a  jmp     short loc_140025613
0x14002559c  mov     rax, [rsp+100h+var_C0]
0x1400255a1  lea     rcx, [rbp+37h+var_90]; this
0x1400255a5  xor     r9d, r9d; wchar_t *
0x1400255a8  mov     qword ptr [rsp+100h+var_E0], rax; unsigned __int64 *
0x1400255ad  xor     r8d, r8d; bool
0x1400255b0  mov     rdx, r13; wchar_t *
0x1400255b3  call    ?Bind@AutoSsShim@Windows@@QEAAJQEB_W_N0PEB_K@Z; Windows::AutoSsShim::Bind(wchar_t const * const,bool,wchar_t const * const,unsigned __int64 const *)
0x1400255b8  mov     ebx, eax
0x1400255ba  test    eax, eax
0x1400255bc  jns     short loc_1400255C5
0x1400255be  mov     edx, 0F7h
0x1400255c3  jmp     short loc_14002557E
0x1400255c5  mov     rcx, [rsp+100h+var_B8]; wchar_t *
0x1400255ca  lea     r8, [rsp+100h+var_D0]
0x1400255cf  lea     rdx, [rbp+37h+var_90]; this
0x1400255d3  call    CbsGetSsBinaryPathByShim
0x1400255d8  mov     ebx, eax
0x1400255da  test    eax, eax
0x1400255dc  jns     short loc_1400255E5
0x1400255de  mov     edx, 0F8h
0x1400255e3  jmp     short loc_14002557E
0x1400255e5  lea     rcx, [rbp+37h+var_90]; this
0x1400255e9  call    ??1AutoSsShim@Windows@@QEAA@XZ; Windows::AutoSsShim::~AutoSsShim(void)
0x1400255ee  mov     r12, [rsp+100h+var_D0]
0x1400255f3  mov     rax, [rsp+100h+var_C8]
0x1400255f8  mov     rcx, [rbp+37h+var_A8]
0x1400255fc  mov     [rsp+100h+var_C8], rdi
0x140025601  mov     [rcx], rax
0x140025604  test    r14, r14
0x140025607  jz      short loc_140025611
0x140025609  mov     [rsp+100h+var_D0], rdi
0x14002560e  mov     [r14], r12
0x140025611  mov     ebx, edi
0x140025613  lea     rcx, [rsp+100h+var_D0]
0x140025618  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoHeapPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(void)
0x14002561d  lea     rcx, [rsp+100h+var_C8]
0x140025622  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoHeapPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(void)
0x140025627  mov     eax, ebx
0x140025629  mov     rcx, [rbp+37h+var_40]
0x14002562d  xor     rcx, rsp; StackCookie
0x140025630  call    __security_check_cookie
0x140025635  mov     rbx, [rsp+100h+arg_8]
0x14002563d  add     rsp, 0D0h
0x140025644  pop     r15
0x140025646  pop     r14
0x140025648  pop     r13
0x14002564a  pop     r12
0x14002564c  pop     rdi
0x14002564d  pop     rsi
0x14002564e  pop     rbp
0x14002564f  retn
```
