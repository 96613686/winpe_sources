# _anonymous_namespace_::I_s_NgcIsoSignHash

- ea: `0x140029f40`
- end: `0x14002a554`
- name: `_anonymous_namespace_::I_s_NgcIsoSignHash`
- size: `1556`
- prototype: ``
- caller_count: `0`
- callee_count: `27`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140009b1c`
- `0x140009fa0`
- `0x14000b3a0`
- `0x14000b3b8`
- `0x14000b678`
- `0x14000d490`
- `0x14000e034`
- `0x14000f6a0`
- `0x1400104fc`
- `0x140017adc`
- `0x140018884`
- `0x1400188c4`
- `0x140018904`
- `0x14001ca34`
- `0x14001d238`
- `0x14001d448`
- `0x14001dc88`
- `0x14001e874`
- `0x14001e944`
- `0x14001eb80`
- `0x1400204e4`
- `0x140029f40`
- `0x14002e2cc`
- `0x14002e3fc`
- `0x14003d360`
- `0x140048c40`
- `0x140071010`

## string_xrefs

- `0x14002a068`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x14002a14f`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x14002a1a2`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x14002a2d1`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x14002a327`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x14002a39a`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x14002a41e`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x14002a4dd`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall anonymous_namespace_::I_s_NgcIsoSignHash(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        unsigned int a12,
        __int64 a13,
        int a14,
        __int64 a15,
        __int64 a16,
        _DWORD *a17,
        _QWORD *a18,
        _DWORD *a19,
        _QWORD *a20,
        _DWORD *a21)
{
  char v24; // dl
  __int64 v25; // r15
  int v26; // eax
  unsigned int v27; // ebx
  Properties::SoftwareKeyMaterial *v28; // rax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  _DWORD *v33; // rax
  _DWORD *v34; // rbx
  void *v35; // rax
  void *v36; // rbx
  int v38; // [rsp+20h] [rbp-E0h]
  int v39; // [rsp+80h] [rbp-80h] BYREF
  _DWORD *v40; // [rsp+88h] [rbp-78h] BYREF
  __int64 v41; // [rsp+90h] [rbp-70h] BYREF
  void *Src; // [rsp+98h] [rbp-68h] BYREF
  __int64 v43; // [rsp+A0h] [rbp-60h]
  int v44[2]; // [rsp+B0h] [rbp-50h] BYREF
  std::_Ref_count_base *v45; // [rsp+B8h] [rbp-48h]
  void *v46; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE *v47; // [rsp+C8h] [rbp-38h]
  _BYTE v48[24]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v49[3]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v50[3]; // [rsp+108h] [rbp+8h] BYREF
  _QWORD *v51; // [rsp+120h] [rbp+20h]
  __int64 v52; // [rsp+128h] [rbp+28h]
  __int64 v53; // [rsp+130h] [rbp+30h]
  _DWORD *v54; // [rsp+138h] [rbp+38h]
  _DWORD *v55; // [rsp+140h] [rbp+40h]
  _BYTE v56[112]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v57[112]; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v58; // [rsp+230h] [rbp+130h]
  __int64 v59; // [rsp+238h] [rbp+138h]
  _BYTE v60[112]; // [rsp+2B0h] [rbp+1B0h] BYREF
  _BYTE v61[112]; // [rsp+320h] [rbp+220h] BYREF
  __int64 v62; // [rsp+390h] [rbp+290h]
  __int64 v63; // [rsp+398h] [rbp+298h]
  _QWORD v64[42]; // [rsp+410h] [rbp+310h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5A8h] [rbp+4A8h]

  v52 = a10;
  v41 = a13;
  v53 = a16;
  v55 = a17;
  v54 = a19;
  v51 = a20;
  v40 = a21;
  wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v64);
  v64[0] = &LogProvider::NgcIsoSignHash::`vftable';
  LogProvider::NgcIsoSignHash::StartActivity((LogProvider::NgcIsoSignHash *)v64);
  std::shared_ptr<NgcIsoContainerImpl>::shared_ptr<NgcIsoContainerImpl>(v44, a2);
  *a19 = 0;
  *v51 = 0;
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v48);
  LOBYTE(v39) = v24;
  v25 = *(_QWORD *)v44;
  v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _BYTE *))(**(_QWORD **)v44 + 32LL))(
          *(_QWORD *)v44,
          a7,
          a8,
          v48);
  v27 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x61F,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
      (const char *)(unsigned int)v26,
      (int)&v39);
LABEL_39:
    std::vector<unsigned char>::_Tidy(v48);
    if ( v45 )
      std::_Ref_count_base::_Decref(v45);
    LogProvider::NgcIsoSignHash::~NgcIsoSignHash((LogProvider::NgcIsoSignHash *)v64);
    return v27;
  }
  *v40 = (_BYTE)v39 == 1;
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&v46);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&Src);
  if ( a4 != 1 )
  {
    if ( a4 != 2 )
    {
      v27 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x666,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
        (const char *)0x80070057LL,
        (int)&v39);
      goto LABEL_38;
    }
    Properties::FromCbor<Properties::TpmKeyMaterial>(v60, v48);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v50);
    if ( v62 != v63 )
      std::vector<unsigned char>::operator=(v50, v61);
    v38 = Properties::TpmKeyMaterial::TpmKeyMaterial(v56, v60);
    v31 = NgcIsoContainerImpl::TpmSign(v25, a3, a5, a6);
    v27 = v31;
    if ( v31 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x65B,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
        (const char *)(unsigned int)v31,
        v38);
LABEL_19:
      std::vector<unsigned char>::_Tidy(v50);
      Properties::TpmKeyMaterial::~TpmKeyMaterial((Properties::TpmKeyMaterial *)v60);
      goto LABEL_38;
    }
    if ( v50[0] != v50[1] )
    {
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v49);
      v32 = ClientAuth::EncryptData();
      v27 = v32;
      if ( v32 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x660,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
          (const char *)(unsigned int)v32,
          v38);
        std::vector<unsigned char>::_Tidy(v49);
        goto LABEL_19;
      }
      std::vector<unsigned char>::operator=(&Src, v49);
      std::vector<unsigned char>::_Tidy(v49);
    }
    std::vector<unsigned char>::_Tidy(v50);
    Properties::TpmKeyMaterial::~TpmKeyMaterial((Properties::TpmKeyMaterial *)v60);
    goto LABEL_25;
  }
  Properties::FromCbor<Properties::SoftwareKeyMaterial>(v56, v48);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v49);
  if ( v58 != v59 )
    std::vector<unsigned char>::operator=(v49, v57);
  v28 = (Properties::SoftwareKeyMaterial *)Properties::SoftwareKeyMaterial::SoftwareKeyMaterial(v60, v56);
  v29 = NgcIsoContainerImpl::SoftwareSign(v25, a3, a5, a6, v28, a11, a12, v41, a14, (__int64)&Src);
  v27 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63A,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
      (const char *)(unsigned int)v29,
      v38);
LABEL_8:
    std::vector<unsigned char>::_Tidy(v49);
    Properties::SoftwareKeyMaterial::~SoftwareKeyMaterial((Properties::SoftwareKeyMaterial *)v56);
LABEL_38:
    std::vector<unsigned char>::_Tidy(&Src);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v46);
    goto LABEL_39;
  }
  if ( v49[0] != v49[1] )
  {
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v50);
    v30 = ClientAuth::EncryptData();
    v27 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x63F,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
        (const char *)(unsigned int)v30,
        v38);
      std::vector<unsigned char>::_Tidy(v50);
      goto LABEL_8;
    }
    std::vector<unsigned char>::operator=(&Src, v50);
    std::vector<unsigned char>::_Tidy(v50);
  }
  std::vector<unsigned char>::_Tidy(v49);
  Properties::SoftwareKeyMaterial::~SoftwareKeyMaterial((Properties::SoftwareKeyMaterial *)v56);
LABEL_25:
  v33 = MIDL_user_allocate(v43 - (_QWORD)Src);
  v34 = v33;
  v40 = v33;
  if ( !v33 )
  {
    v27 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66A,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
      (const char *)0x8007000ELL,
      v38);
LABEL_32:
    std::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>(&v40);
    goto LABEL_38;
  }
  memcpy_0(v33, Src, v43 - (_QWORD)Src);
  v40 = 0;
  *v51 = v34;
  *v54 = v43 - (_DWORD)Src;
  if ( (unsigned __int8)VsmUtils::Velocity::IsEnabled<wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>>()
    && v47 != v46
    && a18 )
  {
    v35 = MIDL_user_allocate(v47 - (_BYTE *)v46);
    v36 = v35;
    v41 = (__int64)v35;
    if ( !v35 )
    {
      v27 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x676,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
        (const char *)0x8007000ELL,
        v38);
      std::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>(&v41);
      goto LABEL_32;
    }
    memcpy_0(v35, v46, v47 - (_BYTE *)v46);
    v41 = 0;
    *a18 = v36;
    *v55 = (_DWORD)v47 - (_DWORD)v46;
    std::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>(&v41);
  }
  wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v64);
  std::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>(&v40);
  std::vector<unsigned char>::_Tidy(&Src);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v46);
  std::vector<unsigned char>::_Tidy(v48);
  if ( v45 )
    std::_Ref_count_base::_Decref(v45);
  LogProvider::NgcIsoSignHash::~NgcIsoSignHash((LogProvider::NgcIsoSignHash *)v64);
  return 0;
}

```

## disassembly

```asm
0x140029f40  mov     [rsp-8+arg_0], rbx
0x140029f45  push    rbp
0x140029f46  push    rsi
0x140029f47  push    rdi
0x140029f48  push    r12
0x140029f4a  push    r13
0x140029f4c  push    r14
0x140029f4e  push    r15
0x140029f50  lea     rbp, [rsp-470h]
0x140029f58  sub     rsp, 570h
0x140029f5f  mov     rax, cs:__security_cookie
0x140029f66  xor     rax, rsp
0x140029f69  mov     [rbp+4A0h+var_40], rax
0x140029f70  mov     esi, r9d
0x140029f73  mov     r12, r8
0x140029f76  mov     rbx, rdx
0x140029f79  mov     rdi, [rbp+4A0h+arg_38]
0x140029f80  mov     rax, [rbp+4A0h+arg_48]
0x140029f87  mov     [rbp+4A0h+var_478], rax
0x140029f8b  mov     r13, [rbp+4A0h+arg_50]
0x140029f92  mov     rax, [rbp+4A0h+arg_60]
0x140029f99  mov     [rbp+4A0h+var_510], rax
0x140029f9d  mov     rax, [rbp+4A0h+arg_78]
0x140029fa4  mov     [rbp+4A0h+var_470], rax
0x140029fa8  mov     rax, [rbp+4A0h+arg_80]
0x140029faf  mov     [rbp+4A0h+var_460], rax
0x140029fb3  mov     r14, [rbp+4A0h+arg_88]
0x140029fba  mov     r15, [rbp+4A0h+arg_90]
0x140029fc1  mov     [rbp+4A0h+var_468], r15
0x140029fc5  mov     rax, [rbp+4A0h+arg_98]
0x140029fcc  mov     [rbp+4A0h+var_480], rax
0x140029fd0  mov     rax, [rbp+4A0h+arg_A0]
0x140029fd7  mov     [rbp+4A0h+var_518], rax
0x140029fdb  lea     rdx, aNgcisosignhash; "NgcIsoSignHash"
0x140029fe2  lea     rcx, [rbp+4A0h+var_190]; struct wil::details::IFailureCallback *
0x140029fe9  call    ??0?$ActivityBase@VLogProvider@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140029fee  lea     rax, ??_7NgcIsoSignHash@LogProvider@@6B@; const LogProvider::NgcIsoSignHash::`vftable'
0x140029ff5  mov     [rbp+4A0h+var_190], rax
0x140029ffc  lea     rcx, [rbp+4A0h+var_190]; this
0x14002a003  call    ?StartActivity@NgcIsoSignHash@LogProvider@@QEAAXXZ; LogProvider::NgcIsoSignHash::StartActivity(void)
0x14002a008  nop
0x14002a009  mov     rdx, rbx
0x14002a00c  lea     rcx, [rbp+4A0h+var_4F0]
0x14002a010  call    ??0?$shared_ptr@VNgcIsoContainerImpl@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<NgcIsoContainerImpl>::shared_ptr<NgcIsoContainerImpl>(std::shared_ptr<NgcIsoContainerImpl> const &)
0x14002a015  nop
0x14002a016  xor     edx, edx
0x14002a018  mov     [r15], edx
0x14002a01b  mov     rax, [rbp+4A0h+var_480]
0x14002a01f  mov     [rax], rdx
0x14002a022  lea     rcx, [rbp+4A0h+var_4C8]
0x14002a026  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x14002a02b  nop
0x14002a02c  mov     byte ptr [rbp+4A0h+var_520], dl
0x14002a02f  mov     r15, qword ptr [rbp+4A0h+var_4F0]
0x14002a033  mov     rax, [r15]
0x14002a036  lea     rcx, [rbp+4A0h+var_520]
0x14002a03a  mov     [rsp+5A0h+var_580], rcx; int
0x14002a03f  lea     r9, [rbp+4A0h+var_4C8]
0x14002a043  mov     r8, rdi
0x14002a046  mov     edx, [rbp+4A0h+arg_30]
0x14002a04c  mov     rcx, r15
0x14002a04f  mov     rax, [rax+20h]
0x14002a053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a058  mov     ebx, eax
0x14002a05a  test    eax, eax
0x14002a05c  jns     short loc_14002A07E
0x14002a05e  mov     rcx, [rbp+4A8h]; this
0x14002a065  mov     r9d, eax; char *
0x14002a068  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x14002a06f  mov     edx, 61Fh; void *
0x14002a074  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002a079  jmp     loc_14002A503
0x14002a07e  xor     eax, eax
0x14002a080  cmp     byte ptr [rbp+4A0h+var_520], 1
0x14002a084  setz    al
0x14002a087  mov     rcx, [rbp+4A0h+var_518]
0x14002a08b  mov     [rcx], eax
0x14002a08d  lea     rcx, [rbp+4A0h+var_4E0]
0x14002a091  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x14002a096  nop
0x14002a097  lea     rcx, [rbp+4A0h+Src]
0x14002a09b  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x14002a0a0  nop
0x14002a0a1  cmp     esi, 1
0x14002a0a4  jnz     loc_14002A1EF
0x14002a0aa  lea     rdx, [rbp+4A0h+var_4C8]
0x14002a0ae  lea     rcx, [rbp+4A0h+var_450]
0x14002a0b2  call    ??$FromCbor@USoftwareKeyMaterial@Properties@@@Properties@@YA?AUSoftwareKeyMaterial@0@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; Properties::FromCbor<Properties::SoftwareKeyMaterial>(std::vector<uchar> const &)
0x14002a0b7  nop
0x14002a0b8  lea     rcx, [rbp+4A0h+var_4B0]
0x14002a0bc  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x14002a0c1  nop
0x14002a0c2  mov     rax, [rbp+4A0h+var_368]
0x14002a0c9  cmp     [rbp+4A0h+var_370], rax
0x14002a0d0  jz      short loc_14002A0E2
0x14002a0d2  lea     rdx, [rbp+4A0h+var_3E0]
0x14002a0d9  lea     rcx, [rbp+4A0h+var_4B0]
0x14002a0dd  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> const &)
0x14002a0e2  lea     rdx, [rbp+4A0h+var_450]
0x14002a0e6  lea     rcx, [rbp+4A0h+var_2F0]
0x14002a0ed  call    ??0SoftwareKeyMaterial@Properties@@QEAA@$$QEAU01@@Z; Properties::SoftwareKeyMaterial::SoftwareKeyMaterial(Properties::SoftwareKeyMaterial &&)
0x14002a0f2  mov     r9d, dword ptr [rbp+4A0h+arg_58]
0x14002a0f9  lea     rcx, [rbp+4A0h+Src]
0x14002a0fd  mov     [rsp+5A0h+var_558], rcx; __int64
0x14002a102  mov     r8d, [rbp+4A0h+arg_68]
0x14002a109  mov     [rsp+5A0h+var_560], r8d; int
0x14002a10e  mov     rcx, [rbp+4A0h+var_510]
0x14002a112  mov     [rsp+5A0h+var_568], rcx; __int64
0x14002a117  mov     [rsp+5A0h+var_570], r9; __int64
0x14002a11c  mov     [rsp+5A0h+var_578], r13; __int64
0x14002a121  mov     [rsp+5A0h+var_580], rax; int
0x14002a126  mov     r9d, [rbp+4A0h+arg_28]; int
0x14002a12d  mov     r8d, [rbp+4A0h+arg_20]; int
0x14002a134  mov     rdx, r12; int
0x14002a137  mov     rcx, r15; int
0x14002a13a  call    ?SoftwareSign@NgcIsoContainerImpl@@QEAAJ_KW4Algorithm@@KUSoftwareKeyMaterial@Properties@@PEBU_NGC_RPC_PADDING_INFO@@0PEBEKPEAV?$vector@EV?$allocator@E@std@@@std@@@Z; NgcIsoContainerImpl::SoftwareSign(unsigned __int64,Algorithm,ulong,Properties::SoftwareKeyMaterial,_NGC_RPC_PADDING_INFO const *,unsigned __int64,uchar const *,ulong,std::vector<uchar> *)
0x14002a13f  mov     ebx, eax
0x14002a141  test    eax, eax
0x14002a143  jns     short loc_14002A179
0x14002a145  mov     rcx, [rbp+4A8h]; this
0x14002a14c  mov     r9d, eax; char *
0x14002a14f  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x14002a156  mov     edx, 63Ah; void *
0x14002a15b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002a160  nop
0x14002a161  lea     rcx, [rbp+4A0h+var_4B0]
0x14002a165  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x14002a16a  nop
0x14002a16b  lea     rcx, [rbp+4A0h+var_450]; this
0x14002a16f  call    ??1SoftwareKeyMaterial@Properties@@UEAA@XZ; Properties::SoftwareKeyMaterial::~SoftwareKeyMaterial(void)
0x14002a174  jmp     loc_14002A4EF
0x14002a179  mov     rax, [rbp+4A0h+var_4A8]
0x14002a17d  cmp     [rbp+4A0h+var_4B0], rax
0x14002a181  jz      short loc_14002A1D7
0x14002a183  lea     rcx, [rbp+4A0h+var_498]
0x14002a187  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x14002a18c  nop
0x14002a18d  call    ?EncryptData@ClientAuth@@SAJAEBV?$vector@EV?$allocator@E@std@@@std@@0AEAV23@@Z; ClientAuth::EncryptData(std::vector<uchar> const &,std::vector<uchar> const &,std::vector<uchar> &)
0x14002a192  mov     ebx, eax
0x14002a194  test    eax, eax
0x14002a196  jns     short loc_14002A1BF
0x14002a198  mov     rcx, [rbp+4A8h]; this
0x14002a19f  mov     r9d, eax; char *
0x14002a1a2  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x14002a1a9  mov     edx, 63Fh; void *
0x14002a1ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002a1b3  nop
0x14002a1b4  lea     rcx, [rbp+4A0h+var_498]
0x14002a1b8  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x14002a1bd  jmp     short loc_14002A161
0x14002a1bf  lea     rdx, [rbp+4A0h+var_498]
0x14002a1c3  lea     rcx, [rbp+4A0h+Src]
0x14002a1c7  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> const &)
0x14002a1cc  nop
0x14002a1cd  lea     rcx, [rbp+4A0h+var_498]
0x14002a1d1  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x14002a1d6  nop
0x14002a1d7  lea     rcx, [rbp+4A0h+var_4B0]
0x14002a1db  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x14002a1e0  nop
0x14002a1e1  lea     rcx, [rbp+4A0h+var_450]; this
0x14002a1e5  call    ??1SoftwareKeyMaterial@Properties@@UEAA@XZ; Properties::SoftwareKeyMaterial::~SoftwareKeyMaterial(void)
0x14002a1ea  jmp     loc_14002A372
0x14002a1ef  cmp     esi, 2
0x14002a1f2  jnz     loc_14002A4CE
0x14002a1f8  lea     rdx, [rbp+4A0h+var_4C8]
0x14002a1fc  lea     rcx, [rbp+4A0h+var_2F0]
0x14002a203  call    ??$FromCbor@UTpmKeyMaterial@Properties@@@Properties@@YA?AUTpmKeyMaterial@0@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; Properties::FromCbor<Properties::TpmKeyMaterial>(std::vector<uchar> const &)
0x14002a208  nop
0x14002a209  lea     rcx, [rbp+4A0h+var_498]
0x14002a20d  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x14002a212  nop
0x14002a213  mov     rax, [rbp+4A0h+var_208]
0x14002a21a  cmp     [rbp+4A0h+var_210], rax
0x14002a221  jz      short loc_14002A233
0x14002a223  lea     rdx, [rbp+4A0h+var_280]
0x14002a22a  lea     rcx, [rbp+4A0h+var_498]
0x14002a22e  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> const &)
0x14002a233  lea     rdx, [rbp+4A0h+var_2F0]
0x14002a23a  lea     rcx, [rbp+4A0h+var_450]
0x14002a23e  call    ??0TpmKeyMaterial@Properties@@QEAA@$$QEAU01@@Z; Properties::TpmKeyMaterial::TpmKeyMaterial(Properties::TpmKeyMaterial &&)
0x14002a243  mov     r8, rax
0x14002a246  mov     edx, dword ptr [rbp+4A0h+arg_58]
0x14002a24c  lea     rax, [rbp+4A0h+Src]
0x14002a250  mov     [rsp+5A0h+var_530], rax
0x14002a255  lea     rax, [rbp+4A0h+var_4E0]
0x14002a259  mov     [rsp+5A0h+var_538], rax
0x14002a25e  mov     rax, [rbp+4A0h+var_470]
0x14002a262  mov     [rsp+5A0h+var_540], rax
0x14002a267  mov     ecx, [rbp+4A0h+arg_70]
0x14002a26d  mov     [rsp+5A0h+var_548], ecx
0x14002a271  mov     ecx, [rbp+4A0h+arg_68]
0x14002a277  mov     [rsp+5A0h+var_550], ecx
0x14002a27b  mov     rcx, [rbp+4A0h+var_510]
0x14002a27f  mov     [rsp+5A0h+var_558], rcx
0x14002a284  mov     qword ptr [rsp+5A0h+var_560], rdx
0x14002a289  mov     [rsp+5A0h+var_568], r13
0x14002a28e  mov     rax, [rbp+4A0h+var_478]
0x14002a292  mov     [rsp+5A0h+var_570], rax
0x14002a297  mov     rax, [rbp+4A0h+arg_40]
0x14002a29e  mov     [rsp+5A0h+var_578], rax
0x14002a2a3  mov     [rsp+5A0h+var_580], r8; int
0x14002a2a8  mov     r9d, [rbp+4A0h+arg_28]
0x14002a2af  mov     r8d, [rbp+4A0h+arg_20]
0x14002a2b6  mov     rdx, r12
0x14002a2b9  mov     rcx, r15
0x14002a2bc  call    ?TpmSign@NgcIsoContainerImpl@@QEAAJ_KW4Algorithm@@KUTpmKeyMaterial@Properties@@0PEBEPEBU_NGC_RPC_PADDING_INFO@@03KK3PEAV?$vector@EU?$secure_allocator@E@wil@@@std@@PEAV?$vector@EV?$allocator@E@std@@@7@@Z; NgcIsoContainerImpl::TpmSign(unsigned __int64,Algorithm,ulong,Properties::TpmKeyMaterial,unsigned __int64,uchar const *,_NGC_RPC_PADDING_INFO const *,unsigned __int64,uchar const *,ulong,ulong,uchar const *,std::vector<uchar,wil::secure_allocator<uchar>> *,std::vector<uchar> *)
0x14002a2c1  mov     ebx, eax
0x14002a2c3  test    eax, eax
0x14002a2c5  jns     short loc_14002A2FE
0x14002a2c7  mov     rcx, [rbp+4A8h]; this
0x14002a2ce  mov     r9d, eax; char *
0x14002a2d1  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x14002a2d8  mov     edx, 65Bh; void *
0x14002a2dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002a2e2  nop
0x14002a2e3  lea     rcx, [rbp+4A0h+var_498]
0x14002a2e7  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x14002a2ec  nop
0x14002a2ed  lea     rcx, [rbp+4A0h+var_2F0]; this
0x14002a2f4  call    ??1TpmKeyMaterial@Properties@@UEAA@XZ; Properties::TpmKeyMaterial::~TpmKeyMaterial(void)
0x14002a2f9  jmp     loc_14002A4EF
0x14002a2fe  mov     rax, [rbp+4A0h+var_490]
0x14002a302  cmp     [rbp+4A0h+var_498], rax
0x14002a306  jz      short loc_14002A35C
0x14002a308  lea     rcx, [rbp+4A0h+var_4B0]
0x14002a30c  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x14002a311  nop
0x14002a312  call    ?EncryptData@ClientAuth@@SAJAEBV?$vector@EV?$allocator@E@std@@@std@@0AEAV23@@Z; ClientAuth::EncryptData(std::vector<uchar> const &,std::vector<uchar> const &,std::vector<uchar> &)
0x14002a317  mov     ebx, eax
0x14002a319  test    eax, eax
0x14002a31b  jns     short loc_14002A344
0x14002a31d  mov     rcx, [rbp+4A8h]; this
0x14002a324  mov     r9d, eax; char *
0x14002a327  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x14002a32e  mov     edx, 660h; void *
0x14002a333  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002a338  nop
0x14002a339  lea     rcx, [rbp+4A0h+var_4B0]
0x14002a33d  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x14002a342  jmp     short loc_14002A2E3
0x14002a344  lea     rdx, [rbp+4A0h+var_4B0]
0x14002a348  lea     rcx, [rbp+4A0h+Src]
0x14002a34c  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> const &)
0x14002a351  nop
0x14002a352  lea     rcx, [rbp+4A0h+var_4B0]
0x14002a356  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x14002a35b  nop
0x14002a35c  lea     rcx, [rbp+4A0h+var_498]
0x14002a360  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x14002a365  nop
0x14002a366  lea     rcx, [rbp+4A0h+var_2F0]; this
0x14002a36d  call    ??1TpmKeyMaterial@Properties@@UEAA@XZ; Properties::TpmKeyMaterial::~TpmKeyMaterial(void)
0x14002a372  mov     rcx, [rbp+4A0h+var_500]
0x14002a376  sub     rcx, [rbp+4A0h+Src]; size
0x14002a37a  call    MIDL_user_allocate
0x14002a37f  mov     rbx, rax
0x14002a382  mov     [rbp+4A0h+var_518], rax
0x14002a386  test    rax, rax
0x14002a389  jnz     short loc_14002A3B0
0x14002a38b  mov     rcx, [rbp+4A8h]; this
0x14002a392  mov     ebx, 8007000Eh
0x14002a397  mov     r9d, ebx; char *
0x14002a39a  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x14002a3a1  mov     edx, 66Ah; void *
0x14002a3a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002a3ab  jmp     loc_14002A439
0x14002a3b0  mov     rdx, [rbp+4A0h+Src]; Src
0x14002a3b4  mov     r8, [rbp+4A0h+var_500]
0x14002a3b8  sub     r8, rdx; Size
0x14002a3bb  mov     rcx, rbx; void *
0x14002a3be  call    memcpy_0
0x14002a3c3  mov     [rbp+4A0h+var_518], 0
0x14002a3cb  mov     rax, [rbp+4A0h+var_480]
0x14002a3cf  mov     [rax], rbx
0x14002a3d2  mov     eax, dword ptr [rbp+4A0h+var_500]
0x14002a3d5  sub     eax, dword ptr [rbp+4A0h+Src]
0x14002a3d8  mov     rcx, [rbp+4A0h+var_468]
0x14002a3dc  mov     [rcx], eax
0x14002a3de  call    ??$IsEnabled@V?$Feature@U__WilFeatureTraits_Feature_MakeCredentialPRF@@@wil@@@Velocity@VsmUtils@@SA_NXZ; VsmUtils::Velocity::IsEnabled<wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>>(void)
0x14002a3e3  test    al, al
0x14002a3e5  jz      loc_14002A47A
0x14002a3eb  mov     rcx, [rbp+4A0h+var_4D8]
0x14002a3ef  sub     rcx, [rbp+4A0h+var_4E0]; size
0x14002a3f3  jz      loc_14002A47A
0x14002a3f9  test    r14, r14
0x14002a3fc  jz      short loc_14002A47A
0x14002a3fe  call    MIDL_user_allocate
0x14002a403  mov     rbx, rax
0x14002a406  mov     [rbp+4A0h+var_510], rax
0x14002a40a  test    rax, rax
0x14002a40d  jnz     short loc_14002A447
0x14002a40f  mov     rcx, [rbp+4A8h]; this
0x14002a416  mov     ebx, 8007000Eh
0x14002a41b  mov     r9d, ebx; char *
0x14002a41e  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x14002a425  mov     edx, 676h; void *
0x14002a42a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002a42f  lea     rcx, [rbp+4A0h+var_510]
0x14002a433  call    ??1?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@std@@QEAA@XZ; std::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::~unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>(void)
  ... truncated ...
```
