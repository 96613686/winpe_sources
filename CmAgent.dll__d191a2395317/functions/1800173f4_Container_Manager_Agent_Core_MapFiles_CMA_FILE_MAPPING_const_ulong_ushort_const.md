# Container::Manager::Agent::Core::MapFiles(_CMA_FILE_MAPPING * const,ulong,ushort const *)

- ea: `0x1800173f4`
- end: `0x18001782f`
- name: `?MapFiles@Core@Agent@Manager@Container@@YAJQEAU_CMA_FILE_MAPPING@@KPEBG@Z`
- size: `1083`
- prototype: `__int64 __fastcall(Container::Manager::Agent::Core *this, struct _CMA_FILE_MAPPING *const, const wchar_t *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x180004c30`

## callees

- `0x180002140`
- `0x180002534`
- `0x1800045e4`
- `0x180005934`
- `0x1800059f8`
- `0x1800063e8`
- `0x18000892c`
- `0x18000af30`
- `0x18000bb98`
- `0x18000bc38`
- `0x18000cd00`
- `0x1800173f4`
- `0x18001bc8c`
- `0x1800254bc`

## string_xrefs

- `0x180017485`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x180017531`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x18001773e`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x1800177b5`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x1800177fe`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Container::Manager::Agent::Core::MapFiles(
        Container::Manager::Agent::Core *this,
        struct _CMA_FILE_MAPPING *const a2,
        const wchar_t *a3,
        const unsigned __int16 *a4)
{
  unsigned int v5; // r14d
  struct Path *v7; // rdx
  int SystemDrivePath; // eax
  unsigned int v9; // edi
  void *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rax
  unsigned int v13; // esi
  const wchar_t *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  int v21; // eax
  __int64 v23; // rdx
  __int64 v24; // rdx
  int v25; // [rsp+20h] [rbp-E0h]
  void *v26; // [rsp+40h] [rbp-C0h] BYREF
  char *v27; // [rsp+48h] [rbp-B8h]
  _WORD v28[8]; // [rsp+50h] [rbp-B0h] BYREF
  void *v29; // [rsp+60h] [rbp-A0h] BYREF
  char *v30; // [rsp+68h] [rbp-98h]
  _WORD v31[8]; // [rsp+70h] [rbp-90h] BYREF
  void *v32[2]; // [rsp+80h] [rbp-80h] BYREF
  _WORD v33[8]; // [rsp+90h] [rbp-70h] BYREF
  const wchar_t *v34; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  void *v36[2]; // [rsp+B0h] [rbp-50h] BYREF
  _WORD v37[8]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v38; // [rsp+D0h] [rbp-30h]
  __int64 v39; // [rsp+D8h] [rbp-28h]
  _QWORD v40[42]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v5 = (unsigned int)a2;
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v40,
    "MapFiles",
    a3,
    a4);
  v40[0] = &CmAgentTraceProvider::MapFiles::`vftable';
  CmAgentTraceProvider::MapFiles::StartActivity((CmAgentTraceProvider::MapFiles *)v40);
  v26 = v28;
  v27 = (char *)v28;
  v28[0] = 0;
  SystemDrivePath = Csl::GetSystemDrivePath((Csl *)&v26, v7);
  v9 = SystemDrivePath;
  if ( SystemDrivePath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5FC,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
      (const char *)(unsigned int)SystemDrivePath,
      v25);
    v10 = v26;
    if ( v26 != v28 )
    {
LABEL_44:
      operator delete(v10, (const struct std::nothrow_t *)&std::nothrow);
      goto LABEL_36;
    }
    goto LABEL_36;
  }
  v29 = v31;
  v30 = (char *)v31;
  v31[0] = 0;
  v34 = L"\\\\?\\vmsmb\\VSMB-{dcc079ae-60ba-4d07-847c-3493609c0870}\\";
  v35 = 54;
  if ( !(unsigned __int8)Csl::Path::Assign((Csl::Path *)&v29) )
  {
    v11 = 1535;
    goto LABEL_10;
  }
  v34 = a3;
  v12 = -1;
  do
    ++v12;
  while ( a3[v12] );
  v35 = v12;
  if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)&v29) )
  {
    v11 = 1536;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
      (const char *)0x8007000ELL,
      v25);
LABEL_11:
    if ( v29 != v31 )
      operator delete(v29, (const struct std::nothrow_t *)&std::nothrow);
    if ( v26 != v28 )
      operator delete(v26, (const struct std::nothrow_t *)&std::nothrow);
    v9 = -2147024882;
    goto LABEL_36;
  }
  v13 = 0;
  if ( v5 )
  {
    while ( 1 )
    {
      v32[0] = v33;
      v32[1] = v33;
      v33[0] = 0;
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               v32,
                               v26,
                               (v27 - (_BYTE *)v26) >> 1) )
      {
        v24 = 1545;
LABEL_51:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v24,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
          (const char *)0x8007000ELL,
          v25);
        goto LABEL_52;
      }
      v14 = (const wchar_t *)*((_QWORD *)this + 2 * v13);
      v34 = v14;
      v15 = -1;
      do
        ++v15;
      while ( v14[v15] );
      v35 = v15;
      if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v32) )
      {
        v24 = 1546;
        goto LABEL_51;
      }
      v36[0] = v37;
      v36[1] = v37;
      v37[0] = 0;
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               v36,
                               v29,
                               (v30 - (_BYTE *)v29) >> 1) )
      {
        v23 = 1549;
        goto LABEL_46;
      }
      v16 = *((_QWORD *)this + 2 * v13 + 1);
      v38 = v16;
      v17 = -1;
      do
        ++v17;
      while ( *(_WORD *)(v16 + 2 * v17) );
      v39 = v17;
      if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v36) )
      {
        v23 = 1550;
LABEL_46:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v23,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
          (const char *)0x8007000ELL,
          v25);
        if ( v36[0] != v37 )
          operator delete(v36[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_52:
        if ( v32[0] != v33 )
          operator delete(v32[0], (const struct std::nothrow_t *)&std::nothrow);
        goto LABEL_11;
      }
      v25 = (int)v36[0];
      v21 = BfSetupFilterInternal(v19, v18, v20, v32[0]);
      v9 = v21;
      if ( v21 < 0 )
        break;
      if ( v36[0] != v37 )
        operator delete(v36[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v32[0] != v33 )
        operator delete(v32[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( ++v13 >= v5 )
        goto LABEL_31;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x615,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
      (const char *)(unsigned int)v21,
      v25);
    if ( v36[0] != v37 )
      operator delete(v36[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v32[0] != v33 )
      operator delete(v32[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v29 != v31 )
      operator delete(v29, (const struct std::nothrow_t *)&std::nothrow);
    v10 = v26;
    if ( v26 == v28 )
      goto LABEL_36;
    goto LABEL_44;
  }
LABEL_31:
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v40,
    0);
  if ( v29 != v31 )
    operator delete(v29, (const struct std::nothrow_t *)&std::nothrow);
  if ( v26 != v28 )
    operator delete(v26, (const struct std::nothrow_t *)&std::nothrow);
  v9 = 0;
LABEL_36:
  v40[0] = &CmAgentTraceProvider::MapFiles::`vftable';
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v40);
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v40);
  return v9;
}

```

## disassembly

```asm
0x1800173f4  push    rbp
0x1800173f6  push    rbx
0x1800173f7  push    rsi
0x1800173f8  push    rdi
0x1800173f9  push    r12
0x1800173fb  push    r13
0x1800173fd  push    r14
0x1800173ff  push    r15
0x180017401  lea     rbp, [rsp-148h]
0x180017409  sub     rsp, 248h
0x180017410  mov     rax, cs:__security_cookie
0x180017417  xor     rax, rsp
0x18001741a  mov     [rbp+180h+var_50], rax
0x180017421  mov     rbx, r8
0x180017424  mov     r14d, edx
0x180017427  mov     r15, rcx
0x18001742a  lea     rdx, aMapfiles
0x180017431  lea     rcx, [rbp+180h+var_1A0]
0x180017435  call    ??0?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z
0x18001743a  lea     rax, ??_7MapFiles@CmAgentTraceProvider@@6B@
0x180017441  mov     [rbp+180h+var_1A0], rax
0x180017445  lea     rcx, [rbp+180h+var_1A0]; this
0x180017449  call    ?StartActivity@MapFiles@CmAgentTraceProvider@@QEAAXXZ
0x18001744e  lea     rax, [rsp+280h+var_230]
0x180017453  mov     [rsp+280h+var_240], rax
0x180017458  lea     rax, [rsp+280h+var_230]
0x18001745d  mov     [rsp+280h+var_238], rax
0x180017462  xor     r12d, r12d
0x180017465  mov     [rsp+280h+var_230], r12w
0x18001746b  lea     rcx, [rsp+280h+var_240]; this
0x180017470  call    ?GetSystemDrivePath@Csl@@YAJAEAVPath@1@@Z
0x180017475  mov     edi, eax
0x180017477  test    eax, eax
0x180017479  jns     short loc_1800174B5
0x18001747b  mov     rcx, [rbp+188h]; this
0x180017482  mov     r9d, eax; char *
0x180017485  lea     r8, aOnecoreBaseGen_8
0x18001748c  mov     edx, 5FCh; void *
0x180017491  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180017496  mov     rcx, [rsp+280h+var_240]
0x18001749b  lea     rax, [rsp+280h+var_230]
0x1800174a0  cmp     rcx, rax
0x1800174a3  jz      loc_1800176F1
0x1800174a9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B
0x1800174b0  jmp     loc_1800177A6
0x1800174b5  lea     rax, [rsp+280h+var_210]
0x1800174ba  mov     [rsp+280h+var_220], rax
0x1800174bf  lea     rax, [rsp+280h+var_210]
0x1800174c4  mov     [rsp+280h+var_218], rax
0x1800174c9  mov     [rsp+280h+var_210], r12w
0x1800174cf  lea     rax, aVmsmbVsmbDcc07
0x1800174d6  mov     [rbp+180h+var_1E0], rax
0x1800174da  mov     [rbp+180h+var_1D8], 36h ; '6'
0x1800174e2  lea     rdx, [rbp+180h+var_1E0]
0x1800174e6  lea     rcx, [rsp+280h+var_220]; this
0x1800174eb  call    ?Assign@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z
0x1800174f0  test    al, al
0x1800174f2  jnz     short loc_1800174FB
0x1800174f4  mov     edx, 5FFh
0x1800174f9  jmp     short loc_18001752B
0x1800174fb  mov     [rbp+180h+var_1E0], rbx
0x1800174ff  or      r13, 0FFFFFFFFFFFFFFFFh
0x180017503  mov     rax, r13
0x180017506  inc     rax
0x180017509  cmp     [rbx+rax*2], r12w
0x18001750e  jnz     short loc_180017506
0x180017510  mov     [rbp+180h+var_1D8], rax
0x180017514  lea     rdx, [rbp+180h+var_1E0]
0x180017518  lea     rcx, [rsp+280h+var_220]; this
0x18001751d  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z
0x180017522  test    al, al
0x180017524  jnz     short loc_180017583
0x180017526  mov     edx, 600h; void *
0x18001752b  mov     r9d, 8007000Eh; char *
0x180017531  lea     r8, aOnecoreBaseGen_8
0x180017538  mov     rcx, [rbp+188h]; this
0x18001753f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180017544  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B
0x18001754b  lea     rax, [rsp+280h+var_210]
0x180017550  mov     rcx, [rsp+280h+var_220]; void *
0x180017555  cmp     rcx, rax
0x180017558  jz      short loc_180017562
0x18001755a  mov     rdx, rbx; struct std::nothrow_t *
0x18001755d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x180017562  lea     rax, [rsp+280h+var_230]
0x180017567  mov     rcx, [rsp+280h+var_240]; void *
0x18001756c  cmp     rcx, rax
0x18001756f  jz      short loc_180017579
0x180017571  mov     rdx, rbx; struct std::nothrow_t *
0x180017574  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x180017579  mov     edi, 8007000Eh
0x18001757e  jmp     loc_1800176F1
0x180017583  mov     esi, r12d
0x180017586  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B
0x18001758d  test    r14d, r14d
0x180017590  jz      loc_1800176B5
0x180017596  lea     rax, [rbp+180h+var_1F0]
0x18001759a  mov     [rbp+180h+var_200], rax
0x18001759e  lea     rax, [rbp+180h+var_1F0]
0x1800175a2  mov     [rbp+180h+var_1F8], rax
0x1800175a6  mov     [rbp+180h+var_1F0], r12w
0x1800175ab  mov     rdx, [rsp+280h+var_240]
0x1800175b0  mov     r8, [rsp+280h+var_238]
0x1800175b5  sub     r8, rdx
0x1800175b8  sar     r8, 1
0x1800175bb  lea     rcx, [rbp+180h+var_200]
0x1800175bf  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z
0x1800175c4  test    al, al
0x1800175c6  jz      loc_1800177F3
0x1800175cc  mov     edi, esi
0x1800175ce  add     rdi, rdi
0x1800175d1  mov     rcx, [r15+rdi*8]
0x1800175d5  mov     [rbp+180h+var_1E0], rcx
0x1800175d9  mov     rax, r13
0x1800175dc  inc     rax
0x1800175df  cmp     [rcx+rax*2], r12w
0x1800175e4  jnz     short loc_1800175DC
0x1800175e6  mov     [rbp+180h+var_1D8], rax
0x1800175ea  lea     rdx, [rbp+180h+var_1E0]
0x1800175ee  lea     rcx, [rbp+180h+var_200]; this
0x1800175f2  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z
0x1800175f7  test    al, al
0x1800175f9  jz      loc_1800177EC
0x1800175ff  lea     rax, [rbp+180h+var_1C0]
0x180017603  mov     [rbp+180h+var_1D0], rax
0x180017607  lea     rax, [rbp+180h+var_1C0]
0x18001760b  mov     [rbp+180h+var_1C8], rax
0x18001760f  mov     [rbp+180h+var_1C0], r12w
0x180017614  mov     rdx, [rsp+280h+var_220]
0x180017619  mov     r8, [rsp+280h+var_218]
0x18001761e  sub     r8, rdx
0x180017621  sar     r8, 1
0x180017624  lea     rcx, [rbp+180h+var_1D0]
0x180017628  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z
0x18001762d  test    al, al
0x18001762f  jz      loc_1800177E5
0x180017635  mov     rcx, [r15+rdi*8+8]
0x18001763a  mov     [rbp+180h+var_1B0], rcx
0x18001763e  mov     rax, r13
0x180017641  inc     rax
0x180017644  cmp     [rcx+rax*2], r12w
0x180017649  jnz     short loc_180017641
0x18001764b  mov     [rbp+180h+var_1A8], rax
0x18001764f  lea     rdx, [rbp+180h+var_1B0]
0x180017653  lea     rcx, [rbp+180h+var_1D0]; this
0x180017657  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z
0x18001765c  test    al, al
0x18001765e  jz      loc_1800177B0
0x180017664  mov     rax, [rbp+180h+var_1D0]
0x180017668  mov     qword ptr [rsp+280h+var_260], rax; int
0x18001766d  mov     r9, [rbp+180h+var_200]
0x180017671  call    BfSetupFilterInternal
0x180017676  mov     edi, eax
0x180017678  test    eax, eax
0x18001767a  js      loc_180017734
0x180017680  mov     rcx, [rbp+180h+var_1D0]; void *
0x180017684  lea     rax, [rbp+180h+var_1C0]
0x180017688  cmp     rcx, rax
0x18001768b  jz      short loc_180017695
0x18001768d  mov     rdx, rbx; struct std::nothrow_t *
0x180017690  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x180017695  mov     rcx, [rbp+180h+var_200]; void *
0x180017699  lea     rax, [rbp+180h+var_1F0]
0x18001769d  cmp     rcx, rax
0x1800176a0  jz      short loc_1800176AA
0x1800176a2  mov     rdx, rbx; struct std::nothrow_t *
0x1800176a5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x1800176aa  inc     esi
0x1800176ac  cmp     esi, r14d
0x1800176af  jb      loc_180017596
0x1800176b5  xor     edx, edx
0x1800176b7  lea     rcx, [rbp+180h+var_1A0]
0x1800176bb  call    ?Stop@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z
0x1800176c0  mov     rcx, [rsp+280h+var_220]; void *
0x1800176c5  lea     rax, [rsp+280h+var_210]
0x1800176ca  cmp     rcx, rax
0x1800176cd  jz      short loc_1800176D7
0x1800176cf  mov     rdx, rbx; struct std::nothrow_t *
0x1800176d2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x1800176d7  mov     rcx, [rsp+280h+var_240]; void *
0x1800176dc  lea     rax, [rsp+280h+var_230]
0x1800176e1  cmp     rcx, rax
0x1800176e4  jz      short loc_1800176EE
0x1800176e6  mov     rdx, rbx; struct std::nothrow_t *
0x1800176e9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x1800176ee  mov     edi, r12d
0x1800176f1  lea     rax, ??_7MapFiles@CmAgentTraceProvider@@6B@
0x1800176f8  mov     [rbp+180h+var_1A0], rax
0x1800176fc  lea     rcx, [rbp+180h+var_1A0]
0x180017700  call    ?Destroy@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ
0x180017705  lea     rcx, [rbp+180h+var_1A0]
0x180017709  call    ??1?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ
0x18001770e  mov     eax, edi
0x180017710  mov     rcx, [rbp+180h+var_50]
0x180017717  xor     rcx, rsp; StackCookie
0x18001771a  call    __security_check_cookie
0x18001771f  add     rsp, 248h
0x180017726  pop     r15
0x180017728  pop     r14
0x18001772a  pop     r13
0x18001772c  pop     r12
0x18001772e  pop     rdi
0x18001772f  pop     rsi
0x180017730  pop     rbx
0x180017731  pop     rbp
0x180017732  retn
0x180017734  mov     rcx, [rbp+188h]; this
0x18001773b  mov     r9d, eax; char *
0x18001773e  lea     r8, aOnecoreBaseGen_8
0x180017745  mov     edx, 615h; void *
0x18001774a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x18001774f  mov     rcx, [rbp+180h+var_1D0]; void *
0x180017753  lea     rax, [rbp+180h+var_1C0]
0x180017757  cmp     rcx, rax
0x18001775a  jz      short loc_180017764
0x18001775c  mov     rdx, rbx; struct std::nothrow_t *
0x18001775f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x180017764  mov     rcx, [rbp+180h+var_200]; void *
0x180017768  lea     rax, [rbp+180h+var_1F0]
0x18001776c  cmp     rcx, rax
0x18001776f  jz      short loc_180017779
0x180017771  mov     rdx, rbx; struct std::nothrow_t *
0x180017774  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x180017779  mov     rcx, [rsp+280h+var_220]; void *
0x18001777e  lea     rax, [rsp+280h+var_210]
0x180017783  cmp     rcx, rax
0x180017786  jz      short loc_180017790
0x180017788  mov     rdx, rbx; struct std::nothrow_t *
0x18001778b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x180017790  mov     rcx, [rsp+280h+var_240]; void *
0x180017795  lea     rax, [rsp+280h+var_230]
0x18001779a  cmp     rcx, rax
0x18001779d  jz      loc_1800176F1
0x1800177a3  mov     rdx, rbx; struct std::nothrow_t *
0x1800177a6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x1800177ab  jmp     loc_1800176F1
0x1800177b0  mov     edx, 60Eh; void *
0x1800177b5  lea     r8, aOnecoreBaseGen_8
0x1800177bc  mov     r9d, 8007000Eh; char *
0x1800177c2  mov     rcx, [rbp+188h]; this
0x1800177c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x1800177ce  mov     rcx, [rbp+180h+var_1D0]; void *
0x1800177d2  lea     rax, [rbp+180h+var_1C0]
0x1800177d6  cmp     rcx, rax
0x1800177d9  jz      short loc_180017811
0x1800177db  mov     rdx, rbx; struct std::nothrow_t *
0x1800177de  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x1800177e3  jmp     short loc_180017811
0x1800177e5  mov     edx, 60Dh
0x1800177ea  jmp     short loc_1800177B5
0x1800177ec  mov     edx, 60Ah
0x1800177f1  jmp     short loc_1800177F8
0x1800177f3  mov     edx, 609h; void *
0x1800177f8  mov     r9d, 8007000Eh; char *
0x1800177fe  lea     r8, aOnecoreBaseGen_8
0x180017805  mov     rcx, [rbp+188h]; this
0x18001780c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180017811  lea     rax, [rbp+180h+var_1F0]
0x180017815  mov     rcx, [rbp+180h+var_200]; void *
0x180017819  cmp     rcx, rax
0x18001781c  jz      loc_18001754B
0x180017822  mov     rdx, rbx; struct std::nothrow_t *
0x180017825  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x18001782a  jmp     loc_18001754B
```
