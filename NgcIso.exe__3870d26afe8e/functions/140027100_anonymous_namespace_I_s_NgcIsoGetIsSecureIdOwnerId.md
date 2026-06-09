# _anonymous_namespace_::I_s_NgcIsoGetIsSecureIdOwnerId

- ea: `0x140027100`
- end: `0x14002741f`
- name: `_anonymous_namespace_::I_s_NgcIsoGetIsSecureIdOwnerId`
- size: `799`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `broker_com_uri`

## callees

- `0x140009be0`
- `0x140009fa0`
- `0x14000b3a0`
- `0x14000b678`
- `0x14000d490`
- `0x14000e034`
- `0x14000f6a0`
- `0x1400104f0`
- `0x1400104fc`
- `0x140015fa8`
- `0x140017adc`
- `0x140018884`
- `0x14001dc88`
- `0x14001e3fc`
- `0x1400204e4`
- `0x140021ec4`
- `0x140027100`
- `0x14002d108`
- `0x14002ef8c`
- `0x14003d360`
- `0x140071010`

## string_xrefs

- `0x1400271c6`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x140027207`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x14002726f`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x1400272ff`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x140027355`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall anonymous_namespace_::I_s_NgcIsoGetIsSecureIdOwnerId(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        _DWORD *a5,
        _QWORD *a6)
{
  __int64 v9; // r14
  int v10; // eax
  unsigned int v11; // ebx
  int OwnerId; // eax
  bool v13; // si
  int v14; // eax
  size_t v15; // rbx
  void *v16; // rax
  void *v17; // rdi
  int v19; // [rsp+30h] [rbp-D0h] BYREF
  void *v20; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v21; // [rsp+40h] [rbp-C0h] BYREF
  std::_Ref_count_base *v22; // [rsp+48h] [rbp-B8h]
  _BYTE v23[24]; // [rsp+50h] [rbp-B0h] BYREF
  void *Buf2[3]; // [rsp+68h] [rbp-98h] BYREF
  void *Src; // [rsp+80h] [rbp-80h] BYREF
  __int64 v26; // [rsp+88h] [rbp-78h]
  _OWORD Buf1[2]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v28[112]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v29[112]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v30; // [rsp+1A0h] [rbp+A0h]
  __int64 v31; // [rsp+1A8h] [rbp+A8h]
  _QWORD v32[42]; // [rsp+1D0h] [rbp+D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+268h]

  wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v32);
  v32[0] = &LogProvider::NgcIsoGetIsSecureIdOwnerId::`vftable';
  LogProvider::NgcIsoGetIsSecureIdOwnerId::StartActivity((LogProvider::NgcIsoGetIsSecureIdOwnerId *)v32);
  std::shared_ptr<NgcIsoContainerImpl>::shared_ptr<NgcIsoContainerImpl>(&v21, a2);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v23);
  LOBYTE(v19) = 0;
  v9 = v21;
  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v21 + 32LL))(v21, a3, a4, v23);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5DC,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
      (const char *)(unsigned int)v10,
      (int)&v19);
    goto LABEL_6;
  }
  Properties::FromCbor<Properties::SoftwareKeyMaterial>(v28, v23);
  if ( v30 == v31 )
  {
    v11 = -2146893821;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5E0,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
      (const char *)0x80090003LL,
      (int)&v19);
LABEL_5:
    Properties::SoftwareKeyMaterial::~SoftwareKeyMaterial((Properties::SoftwareKeyMaterial *)v28);
LABEL_6:
    std::vector<unsigned char>::_Tidy(v23);
    if ( v22 )
      std::_Ref_count_base::_Decref(v22);
    goto LABEL_22;
  }
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(Buf2);
  OwnerId = ClientAuth::GetOwnerId(v29, Buf2);
  v11 = OwnerId;
  if ( OwnerId < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5E3,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
      (const char *)(unsigned int)OwnerId,
      (int)&v19);
LABEL_10:
    std::vector<unsigned char>::_Tidy(Buf2);
    goto LABEL_5;
  }
  Buf1[0] = *(_OWORD *)(v9 + 28);
  Buf1[1] = *(_OWORD *)(v9 + 44);
  if ( (void *)((char *)Buf2[1] - (char *)Buf2[0]) != (void *)32 || (v13 = 1, memcmp_0(Buf1, Buf2[0], 0x20u)) )
    v13 = 0;
  std::vector<unsigned char>::vector<unsigned char>(Buf1, 1);
  **(_BYTE **)&Buf1[0] = v13;
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&Src);
  v14 = ClientAuth::EncryptData();
  v11 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5F0,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
      (const char *)(unsigned int)v14,
      (int)&v19);
LABEL_16:
    std::vector<unsigned char>::_Tidy(&Src);
    std::vector<unsigned char>::_Tidy(Buf1);
    goto LABEL_10;
  }
  v15 = v26 - (_QWORD)Src;
  v16 = MIDL_user_allocate(v26 - (_QWORD)Src);
  v17 = v16;
  v20 = v16;
  if ( !v16 )
  {
    v11 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5F3,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
      (const char *)0x8007000ELL,
      (int)&v19);
    std::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>(&v20);
    goto LABEL_16;
  }
  memcpy_0(v16, Src, v15);
  v20 = 0;
  *a6 = v17;
  *a5 = v15;
  LogProvider::NgcIsoGetIsSecureIdOwnerId::Stop((LogProvider::NgcIsoGetIsSecureIdOwnerId *)v32, v13);
  std::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>(&v20);
  std::vector<unsigned char>::_Tidy(&Src);
  std::vector<unsigned char>::_Tidy(Buf1);
  std::vector<unsigned char>::_Tidy(Buf2);
  Properties::SoftwareKeyMaterial::~SoftwareKeyMaterial((Properties::SoftwareKeyMaterial *)v28);
  std::vector<unsigned char>::_Tidy(v23);
  if ( v22 )
    std::_Ref_count_base::_Decref(v22);
  v11 = 0;
LABEL_22:
  LogProvider::NgcIsoGetIsSecureIdOwnerId::~NgcIsoGetIsSecureIdOwnerId((LogProvider::NgcIsoGetIsSecureIdOwnerId *)v32);
  return v11;
}

```

## disassembly

```asm
0x140027100  push    rbp
0x140027102  push    rbx
0x140027103  push    rsi
0x140027104  push    rdi
0x140027105  push    r12
0x140027107  push    r14
0x140027109  push    r15
0x14002710b  lea     rbp, [rsp-230h]
0x140027113  sub     rsp, 330h
0x14002711a  mov     rax, cs:__security_cookie
0x140027121  xor     rax, rsp
0x140027124  mov     [rbp+260h+var_40], rax
0x14002712b  mov     rsi, r9
0x14002712e  mov     edi, r8d
0x140027131  mov     rbx, rdx
0x140027134  mov     r15, [rbp+260h+arg_20]
0x14002713b  mov     r12, [rbp+260h+arg_28]
0x140027142  lea     rdx, aNgcisogetissec; "NgcIsoGetIsSecureIdOwnerId"
0x140027149  lea     rcx, [rbp+260h+var_190]; struct wil::details::IFailureCallback *
0x140027150  call    ??0?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140027155  lea     rax, ??_7NgcIsoGetIsSecureIdOwnerId@LogProvider@@6B@; const LogProvider::NgcIsoGetIsSecureIdOwnerId::`vftable'
0x14002715c  mov     [rbp+260h+var_190], rax
0x140027163  lea     rcx, [rbp+260h+var_190]; this
0x14002716a  call    ?StartActivity@NgcIsoGetIsSecureIdOwnerId@LogProvider@@QEAAXXZ; LogProvider::NgcIsoGetIsSecureIdOwnerId::StartActivity(void)
0x14002716f  nop
0x140027170  mov     rdx, rbx
0x140027173  lea     rcx, [rsp+360h+var_320]
0x140027178  call    ??0?$shared_ptr@VNgcIsoContainerImpl@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<NgcIsoContainerImpl>::shared_ptr<NgcIsoContainerImpl>(std::shared_ptr<NgcIsoContainerImpl> const &)
0x14002717d  nop
0x14002717e  lea     rcx, [rsp+360h+var_310]
0x140027183  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x140027188  nop
0x140027189  mov     byte ptr [rsp+360h+var_330], 0
0x14002718e  mov     r14, [rsp+360h+var_320]
0x140027193  mov     rax, [r14]
0x140027196  lea     rcx, [rsp+360h+var_330]
0x14002719b  mov     qword ptr [rsp+360h+var_340], rcx; int
0x1400271a0  lea     r9, [rsp+360h+var_310]
0x1400271a5  mov     r8, rsi
0x1400271a8  mov     edx, edi
0x1400271aa  mov     rcx, r14
0x1400271ad  mov     rax, [rax+20h]
0x1400271b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400271b6  mov     ebx, eax
0x1400271b8  test    eax, eax
0x1400271ba  jns     short loc_1400271D9
0x1400271bc  mov     rcx, [rbp+268h]; this
0x1400271c3  mov     r9d, eax; char *
0x1400271c6  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1400271cd  mov     edx, 5DCh; void *
0x1400271d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400271d7  jmp     short loc_140027223
0x1400271d9  lea     rdx, [rsp+360h+var_310]
0x1400271de  lea     rcx, [rbp+260h+var_2A0]
0x1400271e2  call    ??$FromCbor@USoftwareKeyMaterial@Properties@@@Properties@@YA?AUSoftwareKeyMaterial@0@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; Properties::FromCbor<Properties::SoftwareKeyMaterial>(std::vector<uchar> const &)
0x1400271e7  nop
0x1400271e8  mov     rax, [rbp+260h+var_1B8]
0x1400271ef  cmp     [rbp+260h+var_1C0], rax
0x1400271f6  jnz     short loc_140027246
0x1400271f8  mov     rcx, [rbp+268h]; this
0x1400271ff  mov     ebx, 80090003h
0x140027204  mov     r9d, ebx; char *
0x140027207  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x14002720e  mov     edx, 5E0h; void *
0x140027213  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140027218  nop
0x140027219  lea     rcx, [rbp+260h+var_2A0]; this
0x14002721d  call    ??1SoftwareKeyMaterial@Properties@@UEAA@XZ; Properties::SoftwareKeyMaterial::~SoftwareKeyMaterial(void)
0x140027222  nop
0x140027223  lea     rcx, [rsp+360h+var_310]
0x140027228  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x14002722d  nop
0x14002722e  mov     rcx, [rsp+360h+var_318]; this
0x140027233  test    rcx, rcx
0x140027236  jz      loc_1400273F0
0x14002723c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140027241  jmp     loc_1400273F0
0x140027246  lea     rcx, [rsp+360h+Buf2]
0x14002724b  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x140027250  nop
0x140027251  lea     rdx, [rsp+360h+Buf2]
0x140027256  lea     rcx, [rbp+260h+var_230]
0x14002725a  call    ?GetOwnerId@ClientAuth@@SAJAEBV?$vector@EV?$allocator@E@std@@@std@@AEAV23@@Z; ClientAuth::GetOwnerId(std::vector<uchar> const &,std::vector<uchar> &)
0x14002725f  mov     ebx, eax
0x140027261  test    eax, eax
0x140027263  jns     short loc_14002728D
0x140027265  mov     rcx, [rbp+268h]; this
0x14002726c  mov     r9d, eax; char *
0x14002726f  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140027276  mov     edx, 5E3h; void *
0x14002727b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140027280  nop
0x140027281  lea     rcx, [rsp+360h+Buf2]
0x140027286  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x14002728b  jmp     short loc_140027219
0x14002728d  movups  xmm0, xmmword ptr [r14+1Ch]
0x140027292  movups  [rbp+260h+Buf1], xmm0
0x140027296  movups  xmm1, xmmword ptr [r14+2Ch]
0x14002729b  movups  [rbp+260h+var_2B8], xmm1
0x14002729f  mov     rdx, [rsp+360h+Buf2]; Buf2
0x1400272a4  mov     rax, [rsp+360h+var_2F0]
0x1400272a9  sub     rax, rdx
0x1400272ac  mov     r8d, 20h ; ' '; Size
0x1400272b2  cmp     rax, r8
0x1400272b5  jnz     short loc_1400272C7
0x1400272b7  mov     sil, 1
0x1400272ba  lea     rcx, [rbp+260h+Buf1]; Buf1
0x1400272be  call    memcmp_0
0x1400272c3  test    eax, eax
0x1400272c5  jz      short loc_1400272CA
0x1400272c7  xor     sil, sil
0x1400272ca  mov     edx, 1
0x1400272cf  lea     rcx, [rbp+260h+Buf1]
0x1400272d3  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1400272d8  nop
0x1400272d9  mov     rax, qword ptr [rbp+260h+Buf1]
0x1400272dd  mov     [rax], sil
0x1400272e0  lea     rcx, [rbp+260h+Src]
0x1400272e4  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x1400272e9  nop
0x1400272ea  call    ?EncryptData@ClientAuth@@SAJAEBV?$vector@EV?$allocator@E@std@@@std@@0AEAV23@@Z; ClientAuth::EncryptData(std::vector<uchar> const &,std::vector<uchar> const &,std::vector<uchar> &)
0x1400272ef  mov     ebx, eax
0x1400272f1  test    eax, eax
0x1400272f3  jns     short loc_140027329
0x1400272f5  mov     rcx, [rbp+268h]; this
0x1400272fc  mov     r9d, eax; char *
0x1400272ff  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140027306  mov     edx, 5F0h; void *
0x14002730b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140027310  nop
0x140027311  lea     rcx, [rbp+260h+Src]
0x140027315  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x14002731a  nop
0x14002731b  lea     rcx, [rbp+260h+Buf1]
0x14002731f  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140027324  jmp     loc_140027281
0x140027329  mov     rbx, [rbp+260h+var_2D8]
0x14002732d  sub     rbx, [rbp+260h+Src]
0x140027331  mov     rcx, rbx; size
0x140027334  call    MIDL_user_allocate
0x140027339  mov     rdi, rax
0x14002733c  mov     [rsp+360h+var_328], rax
0x140027341  test    rax, rax
0x140027344  jnz     short loc_140027372
0x140027346  mov     rcx, [rbp+268h]; this
0x14002734d  mov     ebx, 8007000Eh
0x140027352  mov     r9d, ebx; char *
0x140027355  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x14002735c  mov     edx, 5F3h; void *
0x140027361  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140027366  lea     rcx, [rsp+360h+var_328]
0x14002736b  call    ??1?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@std@@QEAA@XZ; std::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::~unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>(void)
0x140027370  jmp     short loc_140027311
0x140027372  mov     r8, rbx; Size
0x140027375  mov     rdx, [rbp+260h+Src]; Src
0x140027379  mov     rcx, rdi; void *
0x14002737c  call    memcpy_0
0x140027381  mov     [rsp+360h+var_328], 0
0x14002738a  mov     [r12], rdi
0x14002738e  mov     [r15], ebx
0x140027391  mov     dl, sil; bool
0x140027394  lea     rcx, [rbp+260h+var_190]; this
0x14002739b  call    ?Stop@NgcIsoGetIsSecureIdOwnerId@LogProvider@@QEAAX_N@Z; LogProvider::NgcIsoGetIsSecureIdOwnerId::Stop(bool)
0x1400273a0  lea     rcx, [rsp+360h+var_328]
0x1400273a5  call    ??1?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@std@@QEAA@XZ; std::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::~unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>(void)
0x1400273aa  nop
0x1400273ab  lea     rcx, [rbp+260h+Src]
0x1400273af  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1400273b4  nop
0x1400273b5  lea     rcx, [rbp+260h+Buf1]
0x1400273b9  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1400273be  nop
0x1400273bf  lea     rcx, [rsp+360h+Buf2]
0x1400273c4  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1400273c9  nop
0x1400273ca  lea     rcx, [rbp+260h+var_2A0]; this
0x1400273ce  call    ??1SoftwareKeyMaterial@Properties@@UEAA@XZ; Properties::SoftwareKeyMaterial::~SoftwareKeyMaterial(void)
0x1400273d3  nop
0x1400273d4  lea     rcx, [rsp+360h+var_310]
0x1400273d9  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1400273de  nop
0x1400273df  mov     rcx, [rsp+360h+var_318]; this
0x1400273e4  test    rcx, rcx
0x1400273e7  jz      short loc_1400273EE
0x1400273e9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400273ee  xor     ebx, ebx
0x1400273f0  lea     rcx, [rbp+260h+var_190]; this
0x1400273f7  call    ??1NgcIsoGetIsSecureIdOwnerId@LogProvider@@QEAA@XZ; LogProvider::NgcIsoGetIsSecureIdOwnerId::~NgcIsoGetIsSecureIdOwnerId(void)
0x1400273fc  mov     eax, ebx
0x1400273fe  mov     rcx, [rbp+260h+var_40]
0x140027405  xor     rcx, rsp; StackCookie
0x140027408  call    __security_check_cookie
0x14002740d  add     rsp, 330h
0x140027414  pop     r15
0x140027416  pop     r14
0x140027418  pop     r12
0x14002741a  pop     rdi
0x14002741b  pop     rsi
0x14002741c  pop     rbx
0x14002741d  pop     rbp
0x14002741e  retn
```
