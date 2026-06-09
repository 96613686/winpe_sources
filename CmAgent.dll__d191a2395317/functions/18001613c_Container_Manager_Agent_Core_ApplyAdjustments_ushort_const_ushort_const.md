# Container::Manager::Agent::Core::ApplyAdjustments(ushort const *,ushort const *)

- ea: `0x18001613c`
- end: `0x180016417`
- name: `?ApplyAdjustments@Core@Agent@Manager@Container@@YAJPEBG0@Z`
- size: `731`
- prototype: `__int64 __fastcall(Container::Manager::Agent::Core *this, const unsigned __int16 *, const unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x180004940`

## callees

- `0x180002140`
- `0x180002534`
- `0x1800045e4`
- `0x180005934`
- `0x1800059f8`
- `0x1800063e8`
- `0x18000892c`
- `0x18000bc38`
- `0x180010e00`
- `0x180015658`
- `0x18001613c`
- `0x18001bb20`
- `0x180026b2c`

## string_xrefs

- `0x1800161ef`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x180016246`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`

## pseudocode

```c
__int64 __fastcall Container::Manager::Agent::Core::ApplyAdjustments(
        Container::Manager::Agent::Core *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4)
{
  __int64 v6; // rax
  int v7; // ebx
  __m128i si128; // xmm6
  int v9; // eax
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  int v13; // [rsp+28h] [rbp-E0h]
  void *v14[2]; // [rsp+38h] [rbp-D0h] BYREF
  __int16 v15; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE v16[48]; // [rsp+58h] [rbp-B0h] BYREF
  __m128i v17; // [rsp+88h] [rbp-80h]
  __m128i v18; // [rsp+98h] [rbp-70h]
  __m128i v19; // [rsp+A8h] [rbp-60h]
  Container::Manager::Agent::Core *v20; // [rsp+B8h] [rbp-50h]
  __int64 v21; // [rsp+C0h] [rbp-48h]
  void *v22[2]; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v23; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v24; // [rsp+E8h] [rbp-20h]
  void *v25[2]; // [rsp+F0h] [rbp-18h] BYREF
  __int128 v26; // [rsp+100h] [rbp-8h] BYREF
  __int64 v27; // [rsp+110h] [rbp+8h]
  __int64 v28; // [rsp+118h] [rbp+10h] BYREF
  __int128 v29; // [rsp+120h] [rbp+18h]
  __int128 v30; // [rsp+130h] [rbp+28h]
  __int64 v31; // [rsp+140h] [rbp+38h]
  __m128i v32; // [rsp+148h] [rbp+40h]
  __m128i v33; // [rsp+158h] [rbp+50h]
  __m128i v34; // [rsp+168h] [rbp+60h]
  _QWORD v35[42]; // [rsp+178h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+310h] [rbp+208h]

  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v35,
    "ApplyAdjustments",
    a3,
    a4);
  v35[0] = &CmAgentTraceProvider::ApplyAdjustments::`vftable';
  CmAgentTraceProvider::ApplyAdjustments::StartActivity(
    (CmAgentTraceProvider::ApplyAdjustments *)v35,
    (const unsigned __int16 *)this);
  v14[0] = &v15;
  v14[1] = &v15;
  v15 = 0;
  v20 = this;
  v6 = -1;
  do
    ++v6;
  while ( *((_WORD *)this + v6) );
  v21 = v6;
  if ( !(unsigned __int8)Csl::Path::Assign((Csl::Path *)v14) )
  {
    v7 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5CA,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
      (const char *)0x8007000ELL,
      v13);
    goto LABEL_8;
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  *(__m128i *)v16 = si128;
  *(__m128i *)&v16[16] = si128;
  *(__m128i *)&v16[32] = si128;
  v17 = si128;
  v18 = si128;
  v19 = si128;
  v9 = Csl::MarshalFromJson<Container::Manager::Image::ImageAdjustments>(a2, v16);
  v7 = v9;
  if ( v9 < 0 )
  {
    v10 = (unsigned int)v9;
    v11 = 1486;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
      (const char *)v10,
      v13);
    Container::Manager::Image::ImageAdjustments::~ImageAdjustments((Container::Manager::Image::ImageAdjustments *)v16);
LABEL_8:
    if ( v14[0] != &v15 )
      operator delete(v14[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_21;
  }
  *(_OWORD *)v25 = 0;
  v26 = 0;
  v27 = 0;
  *(_OWORD *)v22 = 0;
  v23 = 0;
  v24 = 0;
  v28 = *(_QWORD *)v16;
  v29 = *(_OWORD *)&v16[8];
  *(__m128i *)v16 = si128;
  *(_QWORD *)&v16[16] = -1;
  v30 = *(_OWORD *)&v16[24];
  v31 = *(_QWORD *)&v16[40];
  *(_QWORD *)&v16[24] = -1;
  *(__m128i *)&v16[32] = si128;
  v32 = v17;
  v33 = v18;
  v17 = si128;
  v18.m128i_i64[0] = -1;
  v34 = v19;
  v18.m128i_i64[1] = -1;
  v19 = si128;
  LOBYTE(v13) = 1;
  v7 = Container::Manager::Image::ApplyAdjustments(
         v14,
         (Container::Manager::Image::ImageAdjustments *)&v28,
         (__int64)v22,
         (__int64)v25);
  if ( (_BYTE)v24 && v22[0] != &v23 )
    operator delete(v22[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( (_BYTE)v27 && v25[0] != &v26 )
    operator delete(v25[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v7 < 0 )
  {
    v10 = (unsigned int)v7;
    v11 = 1494;
    goto LABEL_7;
  }
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v35,
    0);
  Container::Manager::Image::ImageAdjustments::~ImageAdjustments((Container::Manager::Image::ImageAdjustments *)v16);
  if ( v14[0] != &v15 )
    operator delete(v14[0], (const struct std::nothrow_t *)&std::nothrow);
  v7 = 0;
LABEL_21:
  v35[0] = &CmAgentTraceProvider::ApplyAdjustments::`vftable';
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v35);
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v35);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001613c  mov     rax, rsp
0x18001613f  mov     [rax+18h], rbx
0x180016143  push    rbp
0x180016144  push    rsi
0x180016145  push    rdi
0x180016146  push    r14
0x180016148  push    r15
0x18001614a  lea     rbp, [rax-208h]
0x180016151  sub     rsp, 2E0h
0x180016158  movaps  xmmword ptr [rax-38h], xmm6
0x18001615c  mov     rax, cs:__security_cookie
0x180016163  xor     rax, rsp
0x180016166  mov     [rbp+200h+var_40], rax
0x18001616d  mov     rdi, rdx
0x180016170  mov     rbx, rcx
0x180016173  lea     rdx, aApplyadjustmen; "ApplyAdjustments"
0x18001617a  lea     rcx, [rbp+200h+var_190]
0x18001617e  call    ??0?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180016183  lea     r15, ??_7ApplyAdjustments@CmAgentTraceProvider@@6B@; const CmAgentTraceProvider::ApplyAdjustments::`vftable'
0x18001618a  mov     [rbp+200h+var_190], r15
0x18001618e  mov     rdx, rbx; unsigned __int16 *
0x180016191  lea     rcx, [rbp+200h+var_190]; this
0x180016195  call    ?StartActivity@ApplyAdjustments@CmAgentTraceProvider@@QEAAXPEBG@Z; CmAgentTraceProvider::ApplyAdjustments::StartActivity(ushort const *)
0x18001619a  nop
0x18001619b  lea     rax, [rsp+300h+var_2C0]
0x1800161a0  mov     [rsp+300h+var_2D0], rax
0x1800161a5  lea     rax, [rsp+300h+var_2C0]
0x1800161aa  mov     qword ptr [rsp+300h+var_2C8], rax
0x1800161af  xor     esi, esi
0x1800161b1  mov     [rsp+300h+var_2C0], si
0x1800161b6  mov     [rbp+200h+var_250], rbx
0x1800161ba  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800161be  mov     rax, r14
0x1800161c1  inc     rax
0x1800161c4  cmp     [rbx+rax*2], si
0x1800161c8  jnz     short loc_1800161C1
0x1800161ca  mov     [rbp+200h+var_248], rax
0x1800161ce  lea     rdx, [rbp+200h+var_250]
0x1800161d2  lea     rcx, [rsp+300h+var_2D0]; this
0x1800161d7  call    ?Assign@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Assign(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x1800161dc  test    al, al
0x1800161de  jnz     short loc_180016202
0x1800161e0  mov     rcx, [rbp+208h]; this
0x1800161e7  mov     ebx, 8007000Eh
0x1800161ec  mov     r9d, ebx; char *
0x1800161ef  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x1800161f6  mov     edx, 5CAh; void *
0x1800161fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016200  jmp     short loc_180016263
0x180016202  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18001620a  movdqa  [rsp+300h+var_2B8+8], xmm6
0x180016210  movdqa  [rsp+300h+var_2A8+8], xmm6
0x180016216  movdqa  [rsp+300h+var_298+8], xmm6
0x18001621c  movdqa  [rbp+200h+var_280], xmm6
0x180016221  movdqa  [rbp+200h+var_270], xmm6
0x180016226  movdqa  [rbp+200h+var_260], xmm6
0x18001622b  lea     rdx, [rsp+300h+var_2B8+8]
0x180016230  mov     rcx, rdi
0x180016233  call    ??$MarshalFromJson@UImageAdjustments@Image@Manager@Container@@@Csl@@YAJPEBGAEAUImageAdjustments@Image@Manager@Container@@@Z; Csl::MarshalFromJson<Container::Manager::Image::ImageAdjustments>(ushort const *,Container::Manager::Image::ImageAdjustments &)
0x180016238  mov     ebx, eax
0x18001623a  test    eax, eax
0x18001623c  jns     short loc_180016287
0x18001623e  mov     r9d, eax; char *
0x180016241  mov     edx, 5CEh; void *
0x180016246  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x18001624d  mov     rcx, [rbp+208h]; this
0x180016254  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016259  lea     rcx, [rsp+300h+var_2B8+8]; this
0x18001625e  call    ??1ImageAdjustments@Image@Manager@Container@@QEAA@XZ; Container::Manager::Image::ImageAdjustments::~ImageAdjustments(void)
0x180016263  mov     rcx, [rsp+300h+var_2D0]; void *
0x180016268  lea     rax, [rsp+300h+var_2C0]
0x18001626d  cmp     rcx, rax
0x180016270  jz      loc_1800163D3
0x180016276  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001627d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016282  jmp     loc_1800163D3
0x180016287  xorps   xmm0, xmm0
0x18001628a  xor     eax, eax
0x18001628c  movups  xmmword ptr [rbp+200h+var_218], xmm0
0x180016290  movups  [rbp+200h+var_208], xmm0
0x180016294  mov     [rbp+200h+var_1F8], rax
0x180016298  xorps   xmm1, xmm1
0x18001629b  movups  xmmword ptr [rbp+200h+var_240], xmm1
0x18001629f  movups  [rbp+200h+var_230], xmm1
0x1800162a3  mov     [rbp+200h+var_220], rax
0x1800162a7  mov     rax, qword ptr [rsp+300h+var_2B8+8]
0x1800162ac  mov     [rbp+200h+var_1F0], rax
0x1800162b0  mov     rax, qword ptr [rsp+300h+var_2A8]
0x1800162b5  mov     qword ptr [rbp+200h+var_1E8], rax
0x1800162b9  mov     rax, qword ptr [rsp+300h+var_2A8+8]
0x1800162be  mov     qword ptr [rbp+200h+var_1E8+8], rax
0x1800162c2  movdqa  [rsp+300h+var_2B8+8], xmm6
0x1800162c8  mov     qword ptr [rsp+300h+var_2A8+8], r14
0x1800162cd  mov     rax, qword ptr [rsp+300h+var_298]
0x1800162d2  mov     qword ptr [rbp+200h+var_1D8], rax
0x1800162d6  mov     rax, qword ptr [rsp+300h+var_298+8]
0x1800162db  mov     qword ptr [rbp+200h+var_1D8+8], rax
0x1800162df  mov     rax, [rsp+300h+var_288]
0x1800162e4  mov     [rbp+200h+var_1C8], rax
0x1800162e8  mov     qword ptr [rsp+300h+var_298], r14
0x1800162ed  movdqa  [rsp+300h+var_298+8], xmm6
0x1800162f3  mov     rax, qword ptr [rbp+200h+var_280]
0x1800162f7  mov     qword ptr [rbp+200h+var_1C0], rax
0x1800162fb  mov     rax, qword ptr [rbp+200h+var_280+8]
0x1800162ff  mov     qword ptr [rbp+200h+var_1C0+8], rax
0x180016303  mov     rax, qword ptr [rbp+200h+var_270]
0x180016307  mov     qword ptr [rbp+200h+var_1B0], rax
0x18001630b  movdqa  [rbp+200h+var_280], xmm6
0x180016310  mov     qword ptr [rbp+200h+var_270], r14
0x180016314  mov     rax, qword ptr [rbp+200h+var_270+8]
0x180016318  mov     qword ptr [rbp+200h+var_1B0+8], rax
0x18001631c  mov     rax, qword ptr [rbp+200h+var_260]
0x180016320  mov     qword ptr [rbp+200h+var_1A0], rax
0x180016324  mov     rax, qword ptr [rbp+200h+var_260+8]
0x180016328  mov     qword ptr [rbp+200h+var_1A0+8], rax
0x18001632c  mov     qword ptr [rbp+200h+var_270+8], r14
0x180016330  movdqa  [rbp+200h+var_260], xmm6
0x180016335  mov     byte ptr [rsp+300h+var_2E0], 1
0x18001633a  lea     r9, [rbp+200h+var_218]
0x18001633e  lea     r8, [rbp+200h+var_240]
0x180016342  lea     rdx, [rbp+200h+var_1F0]
0x180016346  lea     rcx, [rsp+300h+var_2D0]
0x18001634b  call    ?ApplyAdjustments@Image@Manager@Container@@YAJAEBVPath@Csl@@UImageAdjustments@123@AEBV?$optional@VPath@Csl@@@utl@@2_N@Z; Container::Manager::Image::ApplyAdjustments(Csl::Path const &,Container::Manager::Image::ImageAdjustments,utl::optional<Csl::Path> const &,utl::optional<Csl::Path> const &,bool)
0x180016350  mov     ebx, eax
0x180016352  cmp     byte ptr [rbp+200h+var_220], sil
0x180016356  jz      short loc_180016371
0x180016358  mov     rcx, [rbp+200h+var_240]; void *
0x18001635c  lea     rax, [rbp+200h+var_230]
0x180016360  cmp     rcx, rax
0x180016363  jz      short loc_180016371
0x180016365  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001636c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016371  cmp     byte ptr [rbp+200h+var_1F8], sil
0x180016375  jz      short loc_180016390
0x180016377  mov     rcx, [rbp+200h+var_218]; void *
0x18001637b  lea     rax, [rbp+200h+var_208]
0x18001637f  cmp     rcx, rax
0x180016382  jz      short loc_180016390
0x180016384  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001638b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016390  test    ebx, ebx
0x180016392  jns     short loc_1800163A1
0x180016394  mov     r9d, ebx
0x180016397  mov     edx, 5D6h
0x18001639c  jmp     loc_180016246
0x1800163a1  xor     edx, edx
0x1800163a3  lea     rcx, [rbp+200h+var_190]
0x1800163a7  call    ?Stop@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800163ac  lea     rcx, [rsp+300h+var_2B8+8]; this
0x1800163b1  call    ??1ImageAdjustments@Image@Manager@Container@@QEAA@XZ; Container::Manager::Image::ImageAdjustments::~ImageAdjustments(void)
0x1800163b6  mov     rcx, [rsp+300h+var_2D0]; void *
0x1800163bb  lea     rax, [rsp+300h+var_2C0]
0x1800163c0  cmp     rcx, rax
0x1800163c3  jz      short loc_1800163D1
0x1800163c5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800163cc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800163d1  mov     ebx, esi
0x1800163d3  mov     [rbp+200h+var_190], r15
0x1800163d7  lea     rcx, [rbp+200h+var_190]
0x1800163db  call    ?Destroy@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800163e0  lea     rcx, [rbp+200h+var_190]
0x1800163e4  call    ??1?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800163e9  mov     eax, ebx
0x1800163eb  mov     rcx, [rbp+200h+var_40]
0x1800163f2  xor     rcx, rsp; StackCookie
0x1800163f5  call    __security_check_cookie
0x1800163fa  lea     r11, [rsp+300h+var_20]
0x180016402  mov     rbx, [r11+40h]
0x180016406  movaps  xmm6, xmmword ptr [r11-10h]
0x18001640b  mov     rsp, r11
0x18001640e  pop     r15
0x180016410  pop     r14
0x180016412  pop     rdi
0x180016413  pop     rsi
0x180016414  pop     rbp
0x180016415  retn
```
