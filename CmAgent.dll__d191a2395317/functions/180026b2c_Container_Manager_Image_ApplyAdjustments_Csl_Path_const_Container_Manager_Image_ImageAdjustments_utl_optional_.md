# Container::Manager::Image::ApplyAdjustments(Csl::Path const &,Container::Manager::Image::ImageAdjustments,utl::optional<Csl::Path> const &,utl::optional<Csl::Path> const &,bool)

- ea: `0x180026b2c`
- end: `0x18002759e`
- name: `?ApplyAdjustments@Image@Manager@Container@@YAJAEBVPath@Csl@@UImageAdjustments@123@AEBV?$optional@VPath@Csl@@@utl@@2_N@Z`
- size: `2674`
- prototype: `__int64 __fastcall(_QWORD *, Container::Manager::Image::ImageAdjustments *, __int64, __int64)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001613c`

## callees

- `0x180002164`
- `0x180002534`
- `0x180003ce4`
- `0x1800045e4`
- `0x180007b4c`
- `0x18000af30`
- `0x18000b904`
- `0x180013748`
- `0x1800146cc`
- `0x180015658`
- `0x180026a50`
- `0x180026b2c`
- `0x1800275a4`
- `0x1800279c4`
- `0x180027c74`
- `0x180029070`
- `0x180029684`
- `0x18002a444`
- `0x18002a594`
- `0x18002a600`
- `0x18002a6b4`

## import_xrefs

- `DismApi!DismOpenSession` at `0x180026c88`
- `DismApi!DismOpenSession` at `0x180026c88`
- `DismApi!DismInitialize` at `0x180026c63`
- `DismApi!DismInitialize` at `0x180026c63`
- `DismApi!DismShutdown` at `0x180026c9a`
- `DismApi!DismShutdown` at `0x180026c9a`

## pseudocode

```c
__int64 __fastcall Container::Manager::Image::ApplyAdjustments(
        _QWORD *a1,
        Container::Manager::Image::ImageAdjustments *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v7; // rdx
  void *v8; // rcx
  int v9; // ebx
  void *v10; // rcx
  void *v11; // rdi
  __int64 v12; // rdx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rbx
  __int64 v16; // rdi
  int v17; // esi
  __int64 v18; // rdx
  __int64 v19; // rbx
  __int64 v20; // rdi
  _DWORD *v21; // rbx
  _DWORD *v22; // rdi
  int v23; // eax
  int *v24; // rdi
  int *v25; // rsi
  __m128i si128; // xmm6
  void **v27; // rax
  void **v28; // rcx
  int v29; // r8d
  __int64 v30; // rdx
  void **v31; // rax
  const char *v32; // r9
  void **v33; // rbx
  __int128 v34; // xmm0
  __int64 v35; // xmm1_8
  char v36; // al
  void **v37; // rcx
  int v38; // r8d
  void **v39; // r12
  unsigned __int8 v40; // dl
  void **v41; // r9
  _BYTE *v42; // r9
  __int64 v43; // rcx
  wil::details::in1diag3 *v44; // rcx
  void *v45; // rbx
  __int64 v46; // rdx
  void *v47; // rbx
  void *v48; // rcx
  _QWORD *i; // rbx
  int v50; // eax
  int v51; // edi
  unsigned __int64 v52; // rcx
  _QWORD *v53; // rax
  unsigned __int64 v54; // rax
  int ContainerUserProfile; // eax
  int v56; // eax
  int v58; // eax
  void *v59[2]; // [rsp+28h] [rbp-E0h] BYREF
  unsigned int v60[4]; // [rsp+38h] [rbp-D0h] BYREF
  void **v61; // [rsp+48h] [rbp-C0h] BYREF
  void ***v62; // [rsp+50h] [rbp-B8h]
  void ***v63; // [rsp+58h] [rbp-B0h]
  __int64 v64; // [rsp+60h] [rbp-A8h]
  void *v65[2]; // [rsp+68h] [rbp-A0h] BYREF
  _WORD v66[8]; // [rsp+78h] [rbp-90h] BYREF
  void *v67[2]; // [rsp+88h] [rbp-80h] BYREF
  _WORD v68[8]; // [rsp+98h] [rbp-70h] BYREF
  void **v69; // [rsp+A8h] [rbp-60h] BYREF
  unsigned __int8 v70; // [rsp+B0h] [rbp-58h]
  void *v71[2]; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v72; // [rsp+C8h] [rbp-40h]
  void *v73[2]; // [rsp+D0h] [rbp-38h] BYREF
  _WORD v74[8]; // [rsp+E0h] [rbp-28h] BYREF
  void *v75[2]; // [rsp+F0h] [rbp-18h] BYREF
  _WORD v76[20]; // [rsp+100h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+160h] [rbp+58h]
  int v78; // [rsp+168h] [rbp+60h] BYREF
  char v79; // [rsp+16Ch] [rbp+64h]
  __int64 v80; // [rsp+180h] [rbp+78h]

  v80 = a4;
  v59[0] = v60;
  v59[1] = v60;
  LOWORD(v60[0]) = 0;
  if ( *(_BYTE *)(a4 + 32) )
  {
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             v59,
                             *(_QWORD *)a4,
                             (__int64)(*(_QWORD *)(a4 + 8) - *(_QWORD *)a4) >> 1) )
    {
      v7 = 1330;
LABEL_4:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
        (const char *)0x8007000ELL,
        (int)v59[0]);
      v8 = v59[0];
      if ( v59[0] != v60 )
LABEL_126:
        operator delete(v8, (const struct std::nothrow_t *)&std::nothrow);
LABEL_127:
      v9 = -2147024882;
      goto LABEL_139;
    }
  }
  else if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                v59,
                                *a1,
                                (__int64)(a1[1] - *a1) >> 1) )
  {
    v7 = 1334;
    goto LABEL_4;
  }
  if ( *(_QWORD *)a2 != *((_QWORD *)a2 + 1) || *((_QWORD *)a2 + 9) != *((_QWORD *)a2 + 10) )
  {
    if ( *(_BYTE *)(a4 + 32) )
    {
      v9 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x540,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
             (const char *)0x32,
             (unsigned int)v59[0]);
      goto LABEL_12;
    }
    v11 = v59[0];
    v78 = 0;
    v79 = 0;
    v9 = DismInitialize(2, 0, 0);
    if ( v9 < 0 )
    {
      v12 = 78;
LABEL_20:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\csldism.cpp",
        (const char *)(unsigned int)v9,
        (int)v59[0]);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\csldism.cpp",
        (const char *)(unsigned int)v9,
        (int)v59[0]);
      v14 = 1349;
LABEL_21:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
        (const char *)(unsigned int)v9,
        (int)v59[0]);
      Csl::DismHelper::~DismHelper((Csl::DismHelper *)&v78);
LABEL_12:
      v10 = v59[0];
      if ( v59[0] != v60 )
        goto LABEL_138;
      goto LABEL_139;
    }
    v9 = DismOpenSession(v11, 0, 0, &v78);
    if ( v9 < 0 )
    {
      v13 = DismShutdown();
      if ( v13 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x57,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\csldism.cpp",
          (const char *)(unsigned int)v13,
          (int)v59[0]);
      v12 = 88;
      goto LABEL_20;
    }
    v15 = *(_QWORD *)a2;
    v16 = *((_QWORD *)a2 + 1);
    v79 = 1;
    if ( v15 != v16 )
    {
      while ( v15 != v16 )
      {
        if ( *(_DWORD *)(v15 + 32) == 1 )
        {
          v17 = Csl::DismHelper::EnableFeature(&v78, v15);
          if ( v17 < 0 )
          {
            v18 = 1359;
            goto LABEL_27;
          }
        }
        else
        {
          v17 = Csl::DismHelper::DisableFeature(&v78, v15);
          if ( v17 < 0 )
          {
            v18 = 1366;
            goto LABEL_27;
          }
        }
        v15 += 40;
      }
    }
    v19 = *((_QWORD *)a2 + 9);
    v20 = *((_QWORD *)a2 + 10);
    if ( v19 != v20 )
    {
      if ( *(_BYTE *)(a3 + 32) )
      {
        while ( 1 )
        {
          if ( v19 == v20 )
            goto LABEL_43;
          if ( !*(_BYTE *)(a3 + 32) )
            __int2c();
          v17 = Container::Manager::Image::_anonymous_namespace_::ApplyPackageAdjustment(&v78, v19, a3);
          if ( v17 < 0 )
            break;
          v19 += 40;
        }
        v18 = 1382;
LABEL_27:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
          (const char *)(unsigned int)v17,
          (int)v59[0]);
        Csl::DismHelper::~DismHelper((Csl::DismHelper *)&v78);
LABEL_28:
        if ( v59[0] != v60 )
          operator delete(v59[0], (const struct std::nothrow_t *)&std::nothrow);
        v9 = v17;
        goto LABEL_139;
      }
      v9 = -2147024809;
      v14 = 1377;
      goto LABEL_21;
    }
LABEL_43:
    Csl::DismHelper::~DismHelper((Csl::DismHelper *)&v78);
  }
  v21 = (_DWORD *)*((_QWORD *)a2 + 6);
  v22 = (_DWORD *)*((_QWORD *)a2 + 7);
  while ( v21 != v22 )
  {
    if ( *v21 != 1 )
    {
      v23 = Container::Manager::Image::_anonymous_namespace_::ApplyCommandAdjustment(v59, v21);
      v17 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x599,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
          (const char *)(unsigned int)v23,
          (int)v59[0]);
        goto LABEL_28;
      }
    }
    v21 += 10;
  }
  v24 = (int *)*((_QWORD *)a2 + 3);
  v25 = (int *)*((_QWORD *)a2 + 4);
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v61 = (void **)&v61;
  v62 = &v61;
  v63 = &v61;
  v64 = 0;
  while ( v24 != v25 )
  {
    if ( (unsigned int)v24[27] > 1 )
      goto LABEL_84;
    if ( v63 == &v61 )
      goto LABEL_63;
    v27 = v61;
    v28 = (void **)&v61;
    v29 = *v24;
    do
    {
      if ( *((_DWORD *)v27 + 6) < v29 )
      {
        v30 = 2;
      }
      else
      {
        v28 = v27;
        v30 = 1;
      }
      v27 = (void **)v27[v30];
    }
    while ( v27 != &utl::_TreeSentinel );
    if ( v28 == (void **)&v61 || v29 < *((_DWORD *)v28 + 6) )
    {
LABEL_63:
      v72 = -1;
      *(__m128i *)v71 = si128;
      if ( !(unsigned __int8)utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>::emplace_back<Container::Manager::Image::RegistryAdjustment,0>(
                               v71,
                               v24) )
      {
        v44 = retaddr;
        v46 = 1466;
LABEL_87:
        wil::details::in1diag3::Return_Hr(
          v44,
          (void *)v46,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
          (const char *)0x8007000ELL,
          (int)v59[0]);
        v47 = v71[0];
        if ( v71[0] != (void *)-1LL )
        {
          utl::_RangeDestroyApc<utl::allocator<Container::Manager::Image::RegistryAdjustment>>(
            (char *)v71[1] - (char *)v71[0],
            v71[0],
            ((char *)v71[1] - (char *)v71[0]) / 120 + (char *)v71[1] - (char *)v71[0]);
          v48 = v47;
          goto LABEL_124;
        }
        goto LABEL_125;
      }
      v31 = (void **)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
      v33 = v31;
      if ( v31 )
      {
        v34 = *(_OWORD *)v71;
        *((_DWORD *)v31 + 6) = *v24;
        v35 = v72;
        *((_OWORD *)v31 + 2) = v34;
        v31[6] = (void *)v35;
        *(__m128i *)v71 = si128;
        if ( v63 == &v61 )
        {
          *v31 = (char *)&v61 + 1;
          v36 = 1;
          v33[1] = &utl::_TreeSentinel;
          v33[2] = &utl::_TreeSentinel;
          ++v64;
          v61 = v33;
          v62 = (void ***)v33;
          v63 = (void ***)v33;
LABEL_80:
          v44 = retaddr;
          if ( !v33 )
          {
            v46 = 1472;
            goto LABEL_87;
          }
          if ( !v36 )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x5C1,
              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
              v32);
          v45 = v71[0];
          if ( v71[0] != (void *)-1LL )
          {
            utl::_RangeDestroyApc<utl::allocator<Container::Manager::Image::RegistryAdjustment>>(
              (char *)v71[1] - (char *)v71[0],
              v71[0],
              ((char *)v71[1] - (char *)v71[0]) / 120 + (char *)v71[1] - (char *)v71[0]);
            operator delete(v45, (const struct std::nothrow_t *)&std::nothrow);
          }
          goto LABEL_84;
        }
        v37 = v61;
        v38 = *((_DWORD *)v31 + 6);
        v39 = 0;
        do
        {
          if ( v38 < *((_DWORD *)v37 + 6) )
          {
            v40 = 0;
          }
          else
          {
            v39 = v37;
            v40 = 1;
          }
          v41 = v37;
          v37 = (void **)v37[v40 + 1];
        }
        while ( v37 != &utl::_TreeSentinel );
        if ( v39 && *((_DWORD *)v39 + 6) < v38 )
          v39 = 0;
        v69 = v41;
        v70 = v40;
        if ( !v39 )
        {
          utl::_Tree<enum Container::Manager::Image::RegistryHive,utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>,utl::less<enum Container::Manager::Image::RegistryHive>,utl::allocator<utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>>,0>::_InsertAt(
            &v61,
            &v69,
            v31);
          v36 = 1;
          goto LABEL_80;
        }
        v42 = v31[4];
        if ( v42 != (void *)-1LL )
        {
          v43 = (_BYTE *)v31[5] - (_BYTE *)v42;
          v31[5] = v42;
          utl::_RangeDestroyApc<utl::allocator<Container::Manager::Image::RegistryAdjustment>>(
            v43,
            v42,
            v43 / 120 + v43);
          operator delete(v33[4], (const struct std::nothrow_t *)&std::nothrow);
        }
        operator delete(v33, (const struct std::nothrow_t *)&std::nothrow);
        v33 = v39;
      }
      v36 = 0;
      goto LABEL_80;
    }
    if ( !(unsigned __int8)utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>::emplace_back<Container::Manager::Image::RegistryAdjustment,0>(
                             v28 + 4,
                             v24) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5B4,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
        (const char *)0x8007000ELL,
        (int)v59[0]);
      goto LABEL_125;
    }
LABEL_84:
    v24 += 30;
  }
  for ( i = v63; i != &v61; i = (_QWORD *)v52 )
  {
    v50 = Container::Manager::Image::_anonymous_namespace_::ProcessHive((__int64)v59, *((unsigned int *)i + 6), i + 4);
    v51 = v50;
    if ( v50 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5C7,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
        (const char *)(unsigned int)v50,
        (int)v59[0]);
      utl::_Tree<enum Container::Manager::Image::RegistryHive,utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>,utl::less<enum Container::Manager::Image::RegistryHive>,utl::allocator<utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>>,0>::~_Tree<enum Container::Manager::Image::RegistryHive,utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>,utl::less<enum Container::Manager::Image::RegistryHive>,utl::allocator<utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>>,0>(&v61);
      if ( v59[0] != v60 )
        operator delete(v59[0], (const struct std::nothrow_t *)&std::nothrow);
      v9 = v51;
      goto LABEL_139;
    }
    v52 = i[2];
    if ( (void **)v52 == &utl::_TreeSentinel )
    {
      v53 = (_QWORD *)(*i & 0xFFFFFFFFFFFFFFFEuLL);
      v52 = (unsigned __int64)v53;
      if ( (_QWORD *)v53[2] == i && (_QWORD *)*v53 != i )
      {
        v52 = *v53 & 0xFFFFFFFFFFFFFFFEuLL;
        if ( *(_QWORD **)(v52 + 16) == v53 && *(_QWORD **)v52 != v53 )
        {
          do
          {
            v54 = v52;
            v52 = *(_QWORD *)v52 & 0xFFFFFFFFFFFFFFFEuLL;
          }
          while ( *(_QWORD *)(v52 + 16) == v54 );
        }
      }
    }
    else
    {
      if ( i == (_QWORD *)v52 )
        __int2c();
      while ( *(void ***)(v52 + 8) != &utl::_TreeSentinel )
        v52 = *(_QWORD *)(v52 + 8);
    }
  }
  v66[0] = 0;
  v65[0] = v66;
  v65[1] = v66;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v65,
                           L"ContainerUser",
                           13) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5CE,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL,
      (int)v59[0]);
LABEL_123:
    v48 = v65[0];
    if ( v65[0] == v66 )
      goto LABEL_125;
LABEL_124:
    operator delete(v48, (const struct std::nothrow_t *)&std::nothrow);
LABEL_125:
    utl::_Tree<enum Container::Manager::Image::RegistryHive,utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>,utl::less<enum Container::Manager::Image::RegistryHive>,utl::allocator<utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>>,0>::~_Tree<enum Container::Manager::Image::RegistryHive,utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>,utl::less<enum Container::Manager::Image::RegistryHive>,utl::allocator<utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>>,0>(&v61);
    v8 = v59[0];
    if ( v59[0] == v60 )
      goto LABEL_127;
    goto LABEL_126;
  }
  v68[0] = 0;
  v67[0] = v68;
  v67[1] = v68;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v67,
                           L"S-1-5-93-2-2",
                           12) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D1,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL,
      (int)v59[0]);
LABEL_121:
    if ( v67[0] != v68 )
      operator delete(v67[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_123;
  }
  ContainerUserProfile = Container::Manager::Image::_anonymous_namespace_::CreateContainerUserProfile(v59, v67, v65);
  v9 = ContainerUserProfile;
  if ( ContainerUserProfile < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D5,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)ContainerUserProfile,
      (int)v59[0]);
    goto LABEL_133;
  }
  v74[0] = 0;
  v73[0] = v74;
  v73[1] = v74;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v73,
                           L"ContainerAdministrator",
                           22) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D9,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL,
      (int)v59[0]);
LABEL_119:
    if ( v73[0] != v74 )
      operator delete(v73[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_121;
  }
  v76[0] = 0;
  v75[0] = v76;
  v75[1] = v76;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v75,
                           L"S-1-5-93-2-1",
                           12) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5DC,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL,
      (int)v59[0]);
    if ( v75[0] != v76 )
      operator delete(v75[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_119;
  }
  v56 = Container::Manager::Image::_anonymous_namespace_::CreateContainerUserProfile(v59, v75, v73);
  v9 = v56;
  if ( v56 >= 0 )
  {
    if ( !*(_BYTE *)(v80 + 32) )
    {
      v58 = Container::Manager::Image::_anonymous_namespace_::RebuildCatDb(v59);
      if ( v58 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x5E7,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
          (const char *)(unsigned int)v58,
          (int)v59[0]);
    }
    if ( v75[0] != v76 )
      operator delete(v75[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v73[0] != v74 )
      operator delete(v73[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v67[0] != v68 )
      operator delete(v67[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v65[0] != v66 )
      operator delete(v65[0], (const struct std::nothrow_t *)&std::nothrow);
    utl::_Tree<enum Container::Manager::Image::RegistryHive,utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>,utl::less<enum Container::Manager::Image::RegistryHive>,utl::allocator<utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>>,0>::~_Tree<enum Container::Manager::Image::RegistryHive,utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>,utl::less<enum Container::Manager::Image::RegistryHive>,utl::allocator<utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>>,0>(&v61);
    if ( v59[0] != v60 )
      operator delete(v59[0], (const struct std::nothrow_t *)&std::nothrow);
    Container::Manager::Image::ImageAdjustments::~ImageAdjustments(a2);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5E0,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
    (const char *)(unsigned int)v56,
    (int)v59[0]);
  if ( v75[0] != v76 )
    operator delete(v75[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v73[0] != v74 )
    operator delete(v73[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_133:
  if ( v67[0] != v68 )
    operator delete(v67[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v65[0] != v66 )
    operator delete(v65[0], (const struct std::nothrow_t *)&std::nothrow);
  utl::_Tree<enum Container::Manager::Image::RegistryHive,utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>,utl::less<enum Container::Manager::Image::RegistryHive>,utl::allocator<utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>>,0>::~_Tree<enum Container::Manager::Image::RegistryHive,utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>,utl::less<enum Container::Manager::Image::RegistryHive>,utl::allocator<utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>>,0>(&v61);
  v10 = v59[0];
  if ( v59[0] == v60 )
    goto LABEL_139;
LABEL_138:
  operator delete(v10, (const struct std::nothrow_t *)&std::nothrow);
LABEL_139:
  Container::Manager::Image::ImageAdjustments::~ImageAdjustments(a2);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180026b2c  mov     rax, rsp
0x180026b2f  mov     [rax+10h], rbx
0x180026b33  mov     [rax+20h], r9
0x180026b37  push    rbp
0x180026b38  push    rsi
0x180026b39  push    rdi
0x180026b3a  push    r12
0x180026b3c  push    r13
0x180026b3e  push    r14
0x180026b40  push    r15
0x180026b42  lea     rbp, [rax-58h]
0x180026b46  sub     rsp, 120h
0x180026b4d  movaps  xmmword ptr [rax-48h], xmm6
0x180026b51  xor     r13d, r13d
0x180026b54  lea     rax, [rsp+150h+var_120]
0x180026b59  mov     r12, r9
0x180026b5c  mov     r14, r8
0x180026b5f  mov     [rsp+150h+var_130], rax; int
0x180026b64  lea     rax, [rsp+150h+var_120]
0x180026b69  mov     r15, rdx
0x180026b6c  mov     qword ptr [rsp+150h+var_128], rax
0x180026b71  mov     word ptr [rsp+150h+var_120], r13w
0x180026b77  cmp     [r9+20h], r13b
0x180026b7b  jz      short loc_180026BD2
0x180026b7d  mov     r8, [r9+8]
0x180026b81  lea     rcx, [rsp+150h+var_130]
0x180026b86  sub     r8, [r9]
0x180026b89  mov     rdx, [r9]
0x180026b8c  sar     r8, 1
0x180026b8f  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180026b94  test    al, al
0x180026b96  jnz     short loc_180026BF4
0x180026b98  mov     edx, 532h; void *
0x180026b9d  mov     rcx, [rbp+58h]; this
0x180026ba1  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x180026ba8  mov     r9d, 8007000Eh; char *
0x180026bae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026bb3  mov     rcx, [rsp+150h+var_130]
0x180026bb8  lea     rax, [rsp+150h+var_120]
0x180026bbd  cmp     rcx, rax
0x180026bc0  jz      loc_1800273F6
0x180026bc6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180026bcd  jmp     loc_1800273F1
0x180026bd2  mov     r8, [rcx+8]
0x180026bd6  sub     r8, [rcx]
0x180026bd9  mov     rdx, [rcx]
0x180026bdc  lea     rcx, [rsp+150h+var_130]
0x180026be1  sar     r8, 1
0x180026be4  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180026be9  test    al, al
0x180026beb  jnz     short loc_180026BF4
0x180026bed  mov     edx, 536h
0x180026bf2  jmp     short loc_180026B9D
0x180026bf4  mov     rax, [r15+8]
0x180026bf8  cmp     [r15], rax
0x180026bfb  jnz     short loc_180026C0B
0x180026bfd  mov     rax, [r15+50h]
0x180026c01  cmp     [r15+48h], rax
0x180026c05  jz      loc_180026DFD
0x180026c0b  cmp     [r12+20h], r13b
0x180026c10  jz      short loc_180026C4E
0x180026c12  mov     rcx, [rbp+58h]; this
0x180026c16  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x180026c1d  mov     r9d, 32h ; '2'; char *
0x180026c23  mov     edx, 540h; void *
0x180026c28  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180026c2d  mov     ebx, eax
0x180026c2f  mov     rcx, [rsp+150h+var_130]
0x180026c34  lea     rax, [rsp+150h+var_120]
0x180026c39  cmp     rcx, rax
0x180026c3c  jz      loc_1800274AB
0x180026c42  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180026c49  jmp     loc_1800274A6
0x180026c4e  mov     rdi, [rsp+150h+var_130]
0x180026c53  xor     edx, edx
0x180026c55  xor     r8d, r8d
0x180026c58  mov     [rbp+50h+arg_0], r13d
0x180026c5c  mov     [rbp+50h+arg_4], r13b
0x180026c60  lea     ecx, [rdx+2]
0x180026c63  call    cs:__imp_DismInitialize
0x180026c6a  nop     dword ptr [rax+rax+00h]
0x180026c6f  mov     ebx, eax
0x180026c71  test    eax, eax
0x180026c73  jns     short loc_180026C7C
0x180026c75  mov     edx, 4Eh ; 'N'
0x180026c7a  jmp     short loc_180026CC7
0x180026c7c  lea     r9, [rbp+50h+arg_0]
0x180026c80  xor     r8d, r8d
0x180026c83  xor     edx, edx
0x180026c85  mov     rcx, rdi
0x180026c88  call    cs:__imp_DismOpenSession
0x180026c8f  nop     dword ptr [rax+rax+00h]
0x180026c94  mov     ebx, eax
0x180026c96  test    eax, eax
0x180026c98  jns     short loc_180026D18
0x180026c9a  call    cs:__imp_DismShutdown
0x180026ca1  nop     dword ptr [rax+rax+00h]
0x180026ca6  mov     rcx, [rbp+58h]; this
0x180026caa  test    eax, eax
0x180026cac  jns     short loc_180026CC2
0x180026cae  mov     r9d, eax; char *
0x180026cb1  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180026cb8  mov     edx, 57h ; 'W'; void *
0x180026cbd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180026cc2  mov     edx, 58h ; 'X'; void *
0x180026cc7  mov     rcx, [rbp+58h]; this
0x180026ccb  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180026cd2  mov     r9d, ebx; char *
0x180026cd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026cda  mov     rcx, [rbp+58h]; this
0x180026cde  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180026ce5  mov     r9d, ebx; char *
0x180026ce8  mov     edx, 2Eh ; '.'; void *
0x180026ced  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026cf2  mov     edx, 545h; void *
0x180026cf7  mov     rcx, [rbp+58h]; this
0x180026cfb  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x180026d02  mov     r9d, ebx; char *
0x180026d05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026d0a  lea     rcx, [rbp+50h+arg_0]; this
0x180026d0e  call    ??1DismHelper@Csl@@QEAA@XZ; Csl::DismHelper::~DismHelper(void)
0x180026d13  jmp     loc_180026C2F
0x180026d18  mov     rbx, [r15]
0x180026d1b  mov     rdi, [r15+8]
0x180026d1f  mov     [rbp+50h+arg_4], 1
0x180026d23  cmp     rbx, rdi
0x180026d26  jz      short loc_180026DA0
0x180026d28  cmp     rbx, rdi
0x180026d2b  jz      short loc_180026DA0
0x180026d2d  cmp     dword ptr [rbx+20h], 1
0x180026d31  lea     rcx, [rbp+50h+arg_0]
0x180026d35  mov     rdx, rbx
0x180026d38  jnz     short loc_180026D88
0x180026d3a  call    ?EnableFeature@DismHelper@Csl@@QEAAJAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Csl::DismHelper::EnableFeature(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180026d3f  mov     esi, eax
0x180026d41  test    eax, eax
0x180026d43  jns     short loc_180026D93
0x180026d45  mov     edx, 54Fh; void *
0x180026d4a  mov     rcx, [rbp+58h]; this
0x180026d4e  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x180026d55  mov     r9d, esi; char *
0x180026d58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026d5d  lea     rcx, [rbp+50h+arg_0]; this
0x180026d61  call    ??1DismHelper@Csl@@QEAA@XZ; Csl::DismHelper::~DismHelper(void)
0x180026d66  mov     rcx, [rsp+150h+var_130]; void *
0x180026d6b  lea     rax, [rsp+150h+var_120]
0x180026d70  cmp     rcx, rax
0x180026d73  jz      short loc_180026D81
0x180026d75  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180026d7c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180026d81  mov     ebx, esi
0x180026d83  jmp     loc_1800274AB
0x180026d88  call    ?DisableFeature@DismHelper@Csl@@QEAAJAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Csl::DismHelper::DisableFeature(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180026d8d  mov     esi, eax
0x180026d8f  test    eax, eax
0x180026d91  js      short loc_180026D99
0x180026d93  add     rbx, 28h ; '('
0x180026d97  jmp     short loc_180026D28
0x180026d99  mov     edx, 556h
0x180026d9e  jmp     short loc_180026D4A
0x180026da0  mov     rbx, [r15+48h]
0x180026da4  mov     rdi, [r15+50h]
0x180026da8  cmp     rbx, rdi
0x180026dab  jz      short loc_180026DF4
0x180026dad  cmp     [r14+20h], r13b
0x180026db1  jnz     short loc_180026DC2
0x180026db3  mov     ebx, 80070057h
0x180026db8  mov     edx, 561h
0x180026dbd  jmp     loc_180026CF7
0x180026dc2  cmp     rbx, rdi
0x180026dc5  jz      short loc_180026DF4
0x180026dc7  cmp     [r14+20h], r13b
0x180026dcb  jnz     short loc_180026DCF
0x180026dcd  int     2Ch; Windows NT - assertion failure
0x180026dcf  mov     r8, r14
0x180026dd2  lea     rcx, [rbp+50h+arg_0]
0x180026dd6  mov     rdx, rbx
0x180026dd9  call    Container__Manager__Image___anonymous_namespace___ApplyPackageAdjustment
0x180026dde  mov     esi, eax
0x180026de0  test    eax, eax
0x180026de2  js      short loc_180026DEA
0x180026de4  add     rbx, 28h ; '('
0x180026de8  jmp     short loc_180026DC2
0x180026dea  mov     edx, 566h
0x180026def  jmp     loc_180026D4A
0x180026df4  lea     rcx, [rbp+50h+arg_0]; this
0x180026df8  call    ??1DismHelper@Csl@@QEAA@XZ; Csl::DismHelper::~DismHelper(void)
0x180026dfd  mov     rbx, [r15+30h]
0x180026e01  mov     rdi, [r15+38h]
0x180026e05  cmp     rbx, rdi
0x180026e08  jz      short loc_180026E45
0x180026e0a  cmp     dword ptr [rbx], 1
0x180026e0d  jz      short loc_180026E22
0x180026e0f  mov     rdx, rbx
0x180026e12  lea     rcx, [rsp+150h+var_130]
0x180026e17  call    Container__Manager__Image___anonymous_namespace___ApplyCommandAdjustment
0x180026e1c  mov     esi, eax
0x180026e1e  test    eax, eax
0x180026e20  js      short loc_180026E28
0x180026e22  add     rbx, 28h ; '('
0x180026e26  jmp     short loc_180026E05
0x180026e28  mov     rcx, [rbp+58h]; this
0x180026e2c  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x180026e33  mov     r9d, esi; char *
0x180026e36  mov     edx, 599h; void *
0x180026e3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026e40  jmp     loc_180026D66
0x180026e45  mov     rdi, [r15+18h]
0x180026e49  lea     rax, [rsp+150h+var_110]
0x180026e4e  mov     rsi, [r15+20h]
0x180026e52  lea     r14, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180026e59  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180026e61  lea     r12, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x180026e68  mov     [rsp+150h+var_110], rax
0x180026e6d  lea     rax, [rsp+150h+var_110]
0x180026e72  mov     [rsp+150h+var_108], rax
0x180026e77  mov     [rsp+150h+var_100], rax
0x180026e7c  mov     [rsp+150h+var_F8], r13
0x180026e81  cmp     rdi, rsi
0x180026e84  jz      loc_180027148
0x180026e8a  cmp     dword ptr [rdi+6Ch], 1
0x180026e8e  ja      loc_1800270BB
0x180026e94  lea     rax, [rsp+150h+var_110]
0x180026e99  cmp     [rsp+150h+var_100], rax
0x180026e9e  jz      short loc_180026F0F
0x180026ea0  mov     rax, [rsp+150h+var_110]
0x180026ea5  lea     rcx, [rsp+150h+var_110]
0x180026eaa  mov     r8d, [rdi]
0x180026ead  cmp     [rax+18h], r8d
0x180026eb1  jl      short loc_180026EBD
0x180026eb3  mov     rcx, rax
0x180026eb6  mov     edx, 8
0x180026ebb  jmp     short loc_180026EC2
0x180026ebd  mov     edx, 10h
0x180026ec2  mov     rax, [rax+rdx]
0x180026ec6  cmp     rax, r12
0x180026ec9  jnz     short loc_180026EAD
0x180026ecb  lea     rax, [rsp+150h+var_110]
0x180026ed0  cmp     rcx, rax
0x180026ed3  jz      short loc_180026F0F
0x180026ed5  cmp     r8d, [rcx+18h]
0x180026ed9  jl      short loc_180026F0F
0x180026edb  add     rcx, 20h ; ' '
0x180026edf  mov     rdx, rdi
0x180026ee2  call    ??$emplace_back@URegistryAdjustment@Image@Manager@Container@@$0A@@?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@utl@@@utl@@QEAA_N$$QEAURegistryAdjustment@Image@Manager@Container@@@Z; utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>::emplace_back<Container::Manager::Image::RegistryAdjustment,0>(Container::Manager::Image::RegistryAdjustment &&)
0x180026ee7  test    al, al
0x180026ee9  jnz     loc_1800270BB
0x180026eef  mov     rcx, [rbp+58h]; this
0x180026ef3  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x180026efa  mov     r9d, 8007000Eh; char *
0x180026f00  mov     edx, 5B4h; void *
0x180026f05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026f0a  jmp     loc_1800273D5
0x180026f0f  mov     rdx, rdi
0x180026f12  mov     [rbp+50h+var_90], 0FFFFFFFFFFFFFFFFh
0x180026f1a  lea     rcx, [rbp+50h+var_A0]
0x180026f1e  movdqu  xmmword ptr [rbp+50h+var_A0], xmm6
0x180026f23  call    ??$emplace_back@URegistryAdjustment@Image@Manager@Container@@$0A@@?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@utl@@@utl@@QEAA_N$$QEAURegistryAdjustment@Image@Manager@Container@@@Z; utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>::emplace_back<Container::Manager::Image::RegistryAdjustment,0>(Container::Manager::Image::RegistryAdjustment &&)
0x180026f28  test    al, al
0x180026f2a  jz      loc_18002713D
0x180026f30  mov     rdx, r14; struct std::nothrow_t *
0x180026f33  mov     ecx, 38h ; '8'; unsigned __int64
0x180026f38  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180026f3d  mov     rbx, rax
0x180026f40  test    rax, rax
0x180026f43  jz      loc_180027065
0x180026f49  mov     eax, [rdi]
0x180026f4b  movups  xmm0, xmmword ptr [rbp+50h+var_A0]
0x180026f4f  mov     [rbx+18h], eax
0x180026f52  lea     rax, [rsp+150h+var_110]
0x180026f57  movsd   xmm1, [rbp+50h+var_90]
0x180026f5c  movups  xmmword ptr [rbx+20h], xmm0
0x180026f60  movsd   qword ptr [rbx+30h], xmm1
0x180026f65  movdqu  xmmword ptr [rbp+50h+var_A0], xmm6
0x180026f6a  cmp     [rsp+150h+var_100], rax
0x180026f6f  jnz     short loc_180026FA0
0x180026f71  lea     rax, [rsp+150h+var_110]
0x180026f76  or      rax, 1
0x180026f7a  mov     [rbx], rax
0x180026f7d  mov     al, 1
0x180026f7f  mov     [rbx+8], r12
0x180026f83  mov     [rbx+10h], r12
0x180026f87  inc     [rsp+150h+var_F8]
0x180026f8c  mov     [rsp+150h+var_110], rbx
0x180026f91  mov     [rsp+150h+var_108], rbx
0x180026f96  mov     [rsp+150h+var_100], rbx
0x180026f9b  jmp     loc_180027068
0x180026fa0  mov     rcx, [rsp+150h+var_110]
0x180026fa5  lea     r10, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x180026fac  mov     r8d, [rbx+18h]
0x180026fb0  xor     r12d, r12d
0x180026fb3  cmp     r8d, [rcx+18h]
0x180026fb7  jl      short loc_180026FC0
0x180026fb9  mov     r12, rcx
0x180026fbc  mov     dl, 1
0x180026fbe  jmp     short loc_180026FC2
0x180026fc0  xor     dl, dl
0x180026fc2  movzx   eax, dl
0x180026fc5  mov     r9, rcx
0x180026fc8  mov     rcx, [rcx+rax*8+8]
  ... truncated ...
```
