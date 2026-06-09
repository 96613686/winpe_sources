# _anonymous_namespace_::I_s_NgcIsoDecryptData

- ea: `0x1400251d0`
- end: `0x14002559a`
- name: `_anonymous_namespace_::I_s_NgcIsoDecryptData`
- size: `970`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `broker_com_uri`

## callees

- `0x140009b1c`
- `0x140009fa0`
- `0x14000b3a0`
- `0x14000b678`
- `0x14000d490`
- `0x14000e034`
- `0x14000f6a0`
- `0x1400104fc`
- `0x140017adc`
- `0x140018884`
- `0x1400188c4`
- `0x14001ca34`
- `0x14001d238`
- `0x14001d448`
- `0x14001dc88`
- `0x14001e13c`
- `0x14001e944`
- `0x1400251d0`
- `0x14002c730`
- `0x14002e3fc`
- `0x14003d360`
- `0x140047730`
- `0x1400483dc`
- `0x140071010`

## string_xrefs

- `0x1400252bc`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x140025362`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x140025436`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x140025493`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x14002552c`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall anonymous_namespace_::I_s_NgcIsoDecryptData(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        int a5,
        unsigned int a6,
        unsigned int a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        unsigned int a11,
        __int64 a12,
        _DWORD *a13,
        _QWORD *a14,
        _DWORD *a15)
{
  char v18; // dl
  __int64 v19; // r14
  int v20; // eax
  unsigned int v21; // ebx
  Properties::SoftwareKeyMaterial *v22; // rax
  int v23; // eax
  __int64 v24; // rdx
  int v25; // eax
  size_t v26; // rbx
  void *v27; // rax
  void *v28; // rdi
  int v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+50h] [rbp-B0h] BYREF
  void *v32; // [rsp+58h] [rbp-A8h] BYREF
  int v33[2]; // [rsp+60h] [rbp-A0h] BYREF
  std::_Ref_count_base *v34; // [rsp+68h] [rbp-98h]
  void *Src; // [rsp+70h] [rbp-90h] BYREF
  __int64 v36; // [rsp+78h] [rbp-88h]
  _BYTE v37[24]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v38; // [rsp+A0h] [rbp-60h]
  _DWORD *v39; // [rsp+A8h] [rbp-58h]
  _QWORD v40[42]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v41[352]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v42[352]; // [rsp+360h] [rbp+260h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+508h] [rbp+408h]

  v39 = a13;
  v38 = a14;
  wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v40);
  v40[0] = &LogProvider::NgcIsoDecryptData::`vftable';
  LogProvider::NgcIsoDecryptData::StartActivity((LogProvider::NgcIsoDecryptData *)v40);
  std::shared_ptr<NgcIsoContainerImpl>::shared_ptr<NgcIsoContainerImpl>(v33, a2);
  *a13 = 0;
  *v38 = 0;
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v37);
  LOBYTE(v31) = v18;
  v19 = *(_QWORD *)v33;
  v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _BYTE *))(**(_QWORD **)v33 + 32LL))(
          *(_QWORD *)v33,
          a7,
          a8,
          v37);
  v21 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x69C,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
      (const char *)(unsigned int)v20,
      (int)&v31);
LABEL_21:
    std::vector<unsigned char>::_Tidy(v37);
    if ( v34 )
      std::_Ref_count_base::_Decref(v34);
    LogProvider::NgcIsoDecryptData::~NgcIsoDecryptData((LogProvider::NgcIsoDecryptData *)v40);
    return v21;
  }
  *a15 = (_BYTE)v31 == 1;
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&Src);
  if ( a4 == 1 )
  {
    Properties::FromCbor<Properties::SoftwareKeyMaterial>(v41, v37);
    v22 = (Properties::SoftwareKeyMaterial *)Properties::SoftwareKeyMaterial::SoftwareKeyMaterial(v42, v41);
    v23 = NgcIsoContainerImpl::SoftwareDecrypt(v19, a3, a5, a6, v22, a11, a12, (__int64)&Src);
    v21 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6AE,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
        (const char *)(unsigned int)v23,
        v30);
      Properties::SoftwareKeyMaterial::~SoftwareKeyMaterial((Properties::SoftwareKeyMaterial *)v41);
LABEL_20:
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&Src);
      goto LABEL_21;
    }
    Properties::SoftwareKeyMaterial::~SoftwareKeyMaterial((Properties::SoftwareKeyMaterial *)v41);
    goto LABEL_13;
  }
  if ( a4 != 2 )
  {
    v21 = -2147024809;
    v24 = 1733;
    goto LABEL_19;
  }
  if ( a5 != 1 )
  {
    v21 = -2146893783;
    v24 = 1716;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
      (const char *)v21,
      (int)&v31);
    goto LABEL_20;
  }
  Properties::FromCbor<Properties::TpmKeyMaterial>(v42, v37);
  v30 = Properties::TpmKeyMaterial::TpmKeyMaterial(v41, v42);
  v25 = NgcIsoContainerImpl::TpmDecrypt(v19, a3, 1, a6);
  v21 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6C1,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
      (const char *)(unsigned int)v25,
      v30);
    Properties::TpmKeyMaterial::~TpmKeyMaterial((Properties::TpmKeyMaterial *)v42);
    goto LABEL_20;
  }
  Properties::TpmKeyMaterial::~TpmKeyMaterial((Properties::TpmKeyMaterial *)v42);
LABEL_13:
  v26 = v36 - (_QWORD)Src;
  v27 = MIDL_user_allocate(v36 - (_QWORD)Src);
  v28 = v27;
  v32 = v27;
  if ( !v27 )
  {
    v21 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6C9,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
      (const char *)0x8007000ELL,
      v30);
    std::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>(&v32);
    goto LABEL_20;
  }
  memcpy_0(v27, Src, v26);
  v32 = 0;
  *v38 = v28;
  *v39 = v26;
  wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop((__int64)v40);
  std::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>(&v32);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&Src);
  std::vector<unsigned char>::_Tidy(v37);
  if ( v34 )
    std::_Ref_count_base::_Decref(v34);
  LogProvider::NgcIsoDecryptData::~NgcIsoDecryptData((LogProvider::NgcIsoDecryptData *)v40);
  return 0;
}

```

## disassembly

```asm
0x1400251d0  mov     [rsp-8+arg_0], rbx
0x1400251d5  push    rbp
0x1400251d6  push    rsi
0x1400251d7  push    rdi
0x1400251d8  push    r12
0x1400251da  push    r13
0x1400251dc  push    r14
0x1400251de  push    r15
0x1400251e0  lea     rbp, [rsp-3D0h]
0x1400251e8  sub     rsp, 4D0h
0x1400251ef  mov     rax, cs:__security_cookie
0x1400251f6  xor     rax, rsp
0x1400251f9  mov     [rbp+400h+var_40], rax
0x140025200  mov     esi, r9d
0x140025203  mov     r15, r8
0x140025206  mov     rbx, rdx
0x140025209  mov     rdi, [rbp+400h+arg_38]
0x140025210  mov     r12, [rbp+400h+arg_58]
0x140025217  mov     r14, [rbp+400h+arg_60]
0x14002521e  mov     [rbp+400h+var_458], r14
0x140025222  mov     rax, [rbp+400h+arg_68]
0x140025229  mov     [rbp+400h+var_460], rax
0x14002522d  mov     r13, [rbp+400h+arg_70]
0x140025234  lea     rdx, aNgcisodecryptd; "NgcIsoDecryptData"
0x14002523b  lea     rcx, [rbp+400h+var_450]; struct wil::details::IFailureCallback *
0x14002523f  call    ??0?$ActivityBase@VLogProvider@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140025244  lea     rax, ??_7NgcIsoDecryptData@LogProvider@@6B@; const LogProvider::NgcIsoDecryptData::`vftable'
0x14002524b  mov     [rbp+400h+var_450], rax
0x14002524f  lea     rcx, [rbp+400h+var_450]; this
0x140025253  call    ?StartActivity@NgcIsoDecryptData@LogProvider@@QEAAXXZ; LogProvider::NgcIsoDecryptData::StartActivity(void)
0x140025258  nop
0x140025259  mov     rdx, rbx
0x14002525c  lea     rcx, [rsp+500h+var_4A0]
0x140025261  call    ??0?$shared_ptr@VNgcIsoContainerImpl@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<NgcIsoContainerImpl>::shared_ptr<NgcIsoContainerImpl>(std::shared_ptr<NgcIsoContainerImpl> const &)
0x140025266  nop
0x140025267  xor     edx, edx
0x140025269  mov     [r14], edx
0x14002526c  mov     rax, [rbp+400h+var_460]
0x140025270  mov     [rax], rdx
0x140025273  lea     rcx, [rbp+400h+var_478]
0x140025277  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x14002527c  nop
0x14002527d  mov     byte ptr [rsp+500h+var_4B0], dl
0x140025281  mov     r14, qword ptr [rsp+500h+var_4A0]
0x140025286  mov     rax, [r14]
0x140025289  lea     rcx, [rsp+500h+var_4B0]
0x14002528e  mov     [rsp+500h+var_4E0], rcx; int
0x140025293  lea     r9, [rbp+400h+var_478]
0x140025297  mov     r8, rdi
0x14002529a  mov     edx, [rbp+400h+arg_30]
0x1400252a0  mov     rcx, r14
0x1400252a3  mov     rax, [rax+20h]
0x1400252a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400252ac  mov     ebx, eax
0x1400252ae  test    eax, eax
0x1400252b0  jns     short loc_1400252D2
0x1400252b2  mov     rcx, [rbp+408h]; this
0x1400252b9  mov     r9d, eax; char *
0x1400252bc  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1400252c3  mov     edx, 69Ch; void *
0x1400252c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400252cd  jmp     loc_14002554B
0x1400252d2  xor     eax, eax
0x1400252d4  lea     ebx, [rax+1]
0x1400252d7  cmp     byte ptr [rsp+500h+var_4B0], bl
0x1400252db  setz    al
0x1400252de  mov     [r13+0], eax
0x1400252e2  lea     rcx, [rsp+500h+Src]
0x1400252e7  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x1400252ec  nop
0x1400252ed  cmp     esi, ebx
0x1400252ef  jnz     loc_140025396
0x1400252f5  lea     rdx, [rbp+400h+var_478]
0x1400252f9  lea     rcx, [rbp+400h+var_300]
0x140025300  call    ??$FromCbor@USoftwareKeyMaterial@Properties@@@Properties@@YA?AUSoftwareKeyMaterial@0@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; Properties::FromCbor<Properties::SoftwareKeyMaterial>(std::vector<uchar> const &)
0x140025305  nop
0x140025306  lea     rdx, [rbp+400h+var_300]
0x14002530d  lea     rcx, [rbp+400h+var_1A0]
0x140025314  call    ??0SoftwareKeyMaterial@Properties@@QEAA@$$QEAU01@@Z; Properties::SoftwareKeyMaterial::SoftwareKeyMaterial(Properties::SoftwareKeyMaterial &&)
0x140025319  mov     r8d, dword ptr [rbp+400h+arg_50]
0x140025320  lea     rcx, [rsp+500h+Src]
0x140025325  mov     [rsp+500h+var_4C8], rcx; __int64
0x14002532a  mov     [rsp+500h+var_4D0], r12; __int64
0x14002532f  mov     [rsp+500h+var_4D8], r8; __int64
0x140025334  mov     [rsp+500h+var_4E0], rax; int
0x140025339  mov     r9d, [rbp+400h+arg_28]; int
0x140025340  mov     r8d, [rbp+400h+arg_20]; int
0x140025347  mov     rdx, r15; int
0x14002534a  mov     rcx, r14; int
0x14002534d  call    ?SoftwareDecrypt@NgcIsoContainerImpl@@QEAAJ_KW4Algorithm@@KUSoftwareKeyMaterial@Properties@@0PEBEPEAV?$vector@EU?$secure_allocator@E@wil@@@std@@@Z; NgcIsoContainerImpl::SoftwareDecrypt(unsigned __int64,Algorithm,ulong,Properties::SoftwareKeyMaterial,unsigned __int64,uchar const *,std::vector<uchar,wil::secure_allocator<uchar>> *)
0x140025352  mov     ebx, eax
0x140025354  test    eax, eax
0x140025356  jns     short loc_140025385
0x140025358  mov     rcx, [rbp+408h]; this
0x14002535f  mov     r9d, eax; char *
0x140025362  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140025369  mov     edx, 6AEh; void *
0x14002536e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140025373  nop
0x140025374  lea     rcx, [rbp+400h+var_300]; this
0x14002537b  call    ??1SoftwareKeyMaterial@Properties@@UEAA@XZ; Properties::SoftwareKeyMaterial::~SoftwareKeyMaterial(void)
0x140025380  jmp     loc_140025540
0x140025385  lea     rcx, [rbp+400h+var_300]; this
0x14002538c  call    ??1SoftwareKeyMaterial@Properties@@UEAA@XZ; Properties::SoftwareKeyMaterial::~SoftwareKeyMaterial(void)
0x140025391  jmp     loc_140025465
0x140025396  cmp     esi, 2
0x140025399  jnz     loc_14002551F
0x14002539f  cmp     [rbp+400h+arg_20], ebx
0x1400253a5  jz      short loc_1400253B6
0x1400253a7  mov     ebx, 80090029h
0x1400253ac  mov     edx, 6B4h
0x1400253b1  jmp     loc_140025529
0x1400253b6  lea     rdx, [rbp+400h+var_478]
0x1400253ba  lea     rcx, [rbp+400h+var_1A0]
0x1400253c1  call    ??$FromCbor@UTpmKeyMaterial@Properties@@@Properties@@YA?AUTpmKeyMaterial@0@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; Properties::FromCbor<Properties::TpmKeyMaterial>(std::vector<uchar> const &)
0x1400253c6  nop
0x1400253c7  lea     rdx, [rbp+400h+var_1A0]
0x1400253ce  lea     rcx, [rbp+400h+var_300]
0x1400253d5  call    ??0TpmKeyMaterial@Properties@@QEAA@$$QEAU01@@Z; Properties::TpmKeyMaterial::TpmKeyMaterial(Properties::TpmKeyMaterial &&)
0x1400253da  mov     ecx, dword ptr [rbp+400h+arg_50]
0x1400253e0  lea     rdx, [rsp+500h+Src]
0x1400253e5  mov     [rsp+500h+var_4B8], rdx
0x1400253ea  mov     [rsp+500h+var_4C0], r12
0x1400253ef  mov     [rsp+500h+var_4C8], rcx
0x1400253f4  mov     rcx, [rbp+400h+arg_48]
0x1400253fb  mov     [rsp+500h+var_4D0], rcx
0x140025400  mov     rcx, [rbp+400h+arg_40]
0x140025407  mov     [rsp+500h+var_4D8], rcx
0x14002540c  mov     [rsp+500h+var_4E0], rax; int
0x140025411  mov     r9d, [rbp+400h+arg_28]
0x140025418  mov     r8d, ebx
0x14002541b  mov     rdx, r15
0x14002541e  mov     rcx, r14
0x140025421  call    ?TpmDecrypt@NgcIsoContainerImpl@@QEAAJ_KW4Algorithm@@KUTpmKeyMaterial@Properties@@0PEBE03PEAV?$vector@EU?$secure_allocator@E@wil@@@std@@@Z; NgcIsoContainerImpl::TpmDecrypt(unsigned __int64,Algorithm,ulong,Properties::TpmKeyMaterial,unsigned __int64,uchar const *,unsigned __int64,uchar const *,std::vector<uchar,wil::secure_allocator<uchar>> *)
0x140025426  mov     ebx, eax
0x140025428  test    eax, eax
0x14002542a  jns     short loc_140025459
0x14002542c  mov     rcx, [rbp+408h]; this
0x140025433  mov     r9d, eax; char *
0x140025436  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x14002543d  mov     edx, 6C1h; void *
0x140025442  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140025447  nop
0x140025448  lea     rcx, [rbp+400h+var_1A0]; this
0x14002544f  call    ??1TpmKeyMaterial@Properties@@UEAA@XZ; Properties::TpmKeyMaterial::~TpmKeyMaterial(void)
0x140025454  jmp     loc_140025540
0x140025459  lea     rcx, [rbp+400h+var_1A0]; this
0x140025460  call    ??1TpmKeyMaterial@Properties@@UEAA@XZ; Properties::TpmKeyMaterial::~TpmKeyMaterial(void)
0x140025465  mov     rbx, [rsp+500h+var_488]
0x14002546a  sub     rbx, [rsp+500h+Src]
0x14002546f  mov     rcx, rbx; size
0x140025472  call    MIDL_user_allocate
0x140025477  mov     rdi, rax
0x14002547a  mov     [rsp+500h+var_4A8], rax
0x14002547f  test    rax, rax
0x140025482  jnz     short loc_1400254B3
0x140025484  mov     rcx, [rbp+408h]; this
0x14002548b  mov     ebx, 8007000Eh
0x140025490  mov     r9d, ebx; char *
0x140025493  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x14002549a  mov     edx, 6C9h; void *
0x14002549f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400254a4  lea     rcx, [rsp+500h+var_4A8]
0x1400254a9  call    ??1?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@std@@QEAA@XZ; std::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::~unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>(void)
0x1400254ae  jmp     loc_140025540
0x1400254b3  mov     r8, rbx; Size
0x1400254b6  mov     rdx, [rsp+500h+Src]; Src
0x1400254bb  mov     rcx, rdi; void *
0x1400254be  call    memcpy_0
0x1400254c3  mov     [rsp+500h+var_4A8], 0
0x1400254cc  mov     rax, [rbp+400h+var_460]
0x1400254d0  mov     [rax], rdi
0x1400254d3  mov     rax, [rbp+400h+var_458]
0x1400254d7  mov     [rax], ebx
0x1400254d9  lea     rcx, [rbp+400h+var_450]
0x1400254dd  call    ?Stop@?$ActivityBase@VLogProvider@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400254e2  lea     rcx, [rsp+500h+var_4A8]
0x1400254e7  call    ??1?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@std@@QEAA@XZ; std::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::~unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>(void)
0x1400254ec  nop
0x1400254ed  lea     rcx, [rsp+500h+Src]
0x1400254f2  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x1400254f7  nop
0x1400254f8  lea     rcx, [rbp+400h+var_478]
0x1400254fc  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140025501  nop
0x140025502  mov     rcx, [rsp+500h+var_498]; this
0x140025507  test    rcx, rcx
0x14002550a  jz      short loc_140025512
0x14002550c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140025511  nop
0x140025512  lea     rcx, [rbp+400h+var_450]; this
0x140025516  call    ??1NgcIsoDecryptData@LogProvider@@QEAA@XZ; LogProvider::NgcIsoDecryptData::~NgcIsoDecryptData(void)
0x14002551b  xor     eax, eax
0x14002551d  jmp     short loc_140025570
0x14002551f  mov     ebx, 80070057h
0x140025524  mov     edx, 6C5h; void *
0x140025529  mov     r9d, ebx; char *
0x14002552c  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140025533  mov     rcx, [rbp+408h]; this
0x14002553a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002553f  nop
0x140025540  lea     rcx, [rsp+500h+Src]
0x140025545  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x14002554a  nop
0x14002554b  lea     rcx, [rbp+400h+var_478]
0x14002554f  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140025554  nop
0x140025555  mov     rcx, [rsp+500h+var_498]; this
0x14002555a  test    rcx, rcx
0x14002555d  jz      short loc_140025565
0x14002555f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140025564  nop
0x140025565  lea     rcx, [rbp+400h+var_450]; this
0x140025569  call    ??1NgcIsoDecryptData@LogProvider@@QEAA@XZ; LogProvider::NgcIsoDecryptData::~NgcIsoDecryptData(void)
0x14002556e  mov     eax, ebx
0x140025570  mov     rcx, [rbp+400h+var_40]
0x140025577  xor     rcx, rsp; StackCookie
0x14002557a  call    __security_check_cookie
0x14002557f  mov     rbx, [rsp+500h+arg_0]
0x140025587  add     rsp, 4D0h
0x14002558e  pop     r15
0x140025590  pop     r14
0x140025592  pop     r13
0x140025594  pop     r12
0x140025596  pop     rdi
0x140025597  pop     rsi
0x140025598  pop     rbp
0x140025599  retn
```
