# Container::Manager::Core::Details::ServicingOrchestrator::CleanupWorkThread(void)

- ea: `0x18006ab70`
- end: `0x18006b4c3`
- name: `?CleanupWorkThread@ServicingOrchestrator@Details@Core@Manager@Container@@AEAAJXZ`
- size: `2387`
- prototype: `__int64 __fastcall(Container::Manager::Core::Details::ServicingOrchestrator *__hidden this)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18006b4d0`

## callees

- `0x180004bd0`
- `0x180004fc4`
- `0x18000da88`
- `0x180016774`
- `0x18002d070`
- `0x18002d4ac`
- `0x1800393cc`
- `0x18003943c`
- `0x18003bb80`
- `0x18003c7d0`
- `0x1800493c8`
- `0x180049454`
- `0x180049508`
- `0x18004feb4`
- `0x180057b10`
- `0x1800584e4`
- `0x180058bdc`
- `0x18005a30c`
- `0x180068f14`
- `0x18006931c`
- `0x1800693b8`
- `0x18006ab70`
- `0x18006e1f0`
- `0x18006f8a0`
- `0x180071f58`
- `0x1800c44ac`
- `0x1801974ec`
- `0x180197558`

## import_xrefs

- `DismApi!DismGetPackageInfo` at `0x18006ad38`
- `DismApi!DismGetPackageInfo` at `0x18006ad38`
- `DismApi!DismDelete` at `0x18006ac8b`
- `DismApi!DismDelete` at `0x18006ae52`
- `DismApi!DismDelete` at `0x18006af68`
- `DismApi!DismDelete` at `0x18006b016`
- `DismApi!DismDelete` at `0x18006b3e4`
- `DismApi!DismDelete` at `0x18006b447`
- `DismApi!DismDelete` at `0x18006ac8b`
- `DismApi!DismDelete` at `0x18006ae52`
- `DismApi!DismDelete` at `0x18006af68`
- `DismApi!DismDelete` at `0x18006b016`
- `DismApi!DismDelete` at `0x18006b3e4`
- `DismApi!DismDelete` at `0x18006b447`
- `DismApi!DismGetPackages` at `0x18006ac35`
- `DismApi!DismGetPackages` at `0x18006ac35`

## pseudocode

```c
__int64 __fastcall Container::Manager::Core::Details::ServicingOrchestrator::CleanupWorkThread(
        Container::Manager::Core::Details::ServicingOrchestrator *this)
{
  enum UpdateType v1; // ebx
  Container::Manager::Core::Details::ServicingOrchestrator *v2; // r12
  int IsUpdateInProgress; // eax
  const unsigned __int16 *v4; // rdx
  unsigned int v5; // edi
  int v7; // eax
  unsigned int LayerSequenceNumberMap; // ebx
  int Packages; // eax
  __int64 v10; // r8
  unsigned int v11; // edi
  __int64 v12; // rsi
  __int64 v13; // rbx
  __int64 v14; // rax
  __int64 v15; // rcx
  int PackageInfo; // eax
  __int64 v17; // rcx
  unsigned int v18; // ebx
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // r8
  __int64 v26; // rcx
  __int64 v27; // rdx
  __m128i si128; // xmm6
  __int64 v29; // rcx
  int v30; // eax
  __int64 v31; // rcx
  int v32; // edi
  __int64 v33; // rcx
  void *v34; // rbx
  void *v35; // rcx
  _BYTE *v36; // r15
  Container::Manager::Core::ResourceHandle **v37; // rbx
  Container::Manager::Core::ResourceHandle **i; // r14
  __int64 v39; // rax
  Container::Manager::Core::Details::Layer *v40; // r13
  char *v41; // r11
  _QWORD *v42; // rdi
  _QWORD *v43; // r11
  __int64 v44; // rax
  __int64 v45; // rdi
  const struct _GUID *Id; // rsi
  const struct _GUID *v47; // rax
  __int64 v48; // rcx
  int v49; // eax
  unsigned int v50; // esi
  _BYTE *v51; // r12
  _BYTE *v52; // rdi
  _QWORD *j; // rsi
  int v54; // eax
  __int64 v55; // rcx
  bool v56; // r9
  Container::Manager::Core::ResourceHandle *v57; // rdi
  Container::Manager::Core::Details::ResourceBroker **v58; // rsi
  char *v59; // rdi
  bool v60; // r9
  __int64 v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // rcx
  void *v64; // rcx
  void *v65; // rdi
  int v66; // [rsp+20h] [rbp-E0h]
  int v67; // [rsp+20h] [rbp-E0h]
  int v68; // [rsp+20h] [rbp-E0h]
  int v69; // [rsp+20h] [rbp-E0h]
  int v70; // [rsp+20h] [rbp-E0h]
  bool v71; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v72; // [rsp+48h] [rbp-B8h] BYREF
  Container::Manager::Core::Details::ServicingOrchestrator *v73; // [rsp+50h] [rbp-B0h]
  unsigned int v74; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v75; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v76; // [rsp+68h] [rbp-98h] BYREF
  char v77; // [rsp+6Ch] [rbp-94h]
  _QWORD v78[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD *v79; // [rsp+80h] [rbp-80h]
  __int64 v80; // [rsp+88h] [rbp-78h]
  void *v81[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v82; // [rsp+A0h] [rbp-60h]
  __int64 v83; // [rsp+B0h] [rbp-50h]
  _QWORD v84[4]; // [rsp+B8h] [rbp-48h] BYREF
  void *v85[2]; // [rsp+D8h] [rbp-28h] BYREF
  _WORD v86[8]; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v87[2]; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v88[2]; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v89[2]; // [rsp+118h] [rbp+18h] BYREF
  struct _GUID v90; // [rsp+128h] [rbp+28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v73 = this;
  v71 = 0;
  v1 = 0;
  v2 = this;
  do
  {
    IsUpdateInProgress = Container::Manager::Core::Details::ServicingOrchestrator::IsUpdateInProgress(v2, v1, &v71);
    v5 = IsUpdateInProgress;
    if ( IsUpdateInProgress < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB26,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
        (const char *)(unsigned int)IsUpdateInProgress,
        v66);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x912,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
        (const char *)v5,
        v70);
      return v5;
    }
    if ( v71 )
      return 0;
    ++v1;
  }
  while ( (unsigned int)v1 < (utDriver|utSoftware) );
  v76 = 0;
  v77 = 0;
  v7 = Csl::DismHelper::Initialize((Csl::DismHelper *)&v76, v4);
  LayerSequenceNumberMap = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x91B,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
      (const char *)(unsigned int)v7,
      v66);
    goto LABEL_109;
  }
  v74 = 0;
  v75 = 0;
  Packages = DismGetPackages(v76, &v75, &v74);
  LayerSequenceNumberMap = Packages;
  if ( Packages < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x175,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\csldism.cpp",
      (const char *)(unsigned int)Packages,
      v66);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x91F,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
      (const char *)LayerSequenceNumberMap,
      v67);
    goto LABEL_11;
  }
  v80 = 0;
  v78[0] = v78;
  v11 = 0;
  v78[1] = v78;
  v79 = v78;
  if ( !v74 )
  {
LABEL_37:
    v26 = *((_QWORD *)v2 + 16);
    v84[0] = v84;
    v84[3] = 0;
    v84[1] = v84;
    v84[2] = v84;
    v83 = 0;
    *(_OWORD *)v81 = 0;
    v82 = 0;
    LayerSequenceNumberMap = Container::Manager::Core::Details::ServicingOrchestrator::GetLayerSequenceNumberMap(
                               v26,
                               v84,
                               v81);
    if ( (_BYTE)v83 )
      utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(v81);
    if ( (LayerSequenceNumberMap & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x955,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
        (const char *)LayerSequenceNumberMap,
        v66);
      utl::_Tree<_GUID,utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,unsigned long>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,unsigned long>>>,0>::clear(v84);
      goto LABEL_48;
    }
    si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    v29 = *((_QWORD *)v2 + 16);
    *(_QWORD *)&v82 = -1;
    *(__m128i *)v81 = si128;
    v30 = Container::Manager::Core::Details::ResourceBroker::EnumerateResourceHandles(
            v29,
            2,
            L"ServicingOrchestrator_Start_Layer",
            v81);
    v32 = v30;
    if ( v30 >= 0 )
    {
      v36 = v81[0];
      v37 = (Container::Manager::Core::ResourceHandle **)v81[1];
      for ( i = (Container::Manager::Core::ResourceHandle **)v81[0]; ; ++i )
      {
        if ( i == v37 )
        {
          if ( v36 != (_BYTE *)-1LL )
          {
            utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(
              v31,
              v36,
              ((char *)v37 - v36) >> 3);
            operator delete(v36, (const struct std::nothrow_t *)&std::nothrow);
          }
          utl::_Tree<_GUID,utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,unsigned long>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,unsigned long>>>,0>::clear(v84);
          utl::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>>,0>::~_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>>,0>(v78);
          if ( v75 )
            DismDelete();
          Csl::DismHelper::~DismHelper((Csl::DismHelper *)&v76);
          return 0;
        }
        v39 = Container::Manager::Core::ResourceHandle::Get<Container::Manager::Core::Details::Layer>(*i);
        v40 = (Container::Manager::Core::Details::Layer *)v39;
        if ( (*(_BYTE *)(v39 + 288) & 0x10) != 0 && !*(_BYTE *)(v39 + 360) )
        {
          if ( v79 == v78 )
            goto LABEL_68;
          v41 = (char *)v78[0];
          v42 = v78;
          do
          {
            if ( (unsigned __int8)utl::operator<<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
                                    v41 + 24,
                                    (char *)v40 + 80) )
            {
              v44 = 2;
            }
            else
            {
              v42 = v43;
              v44 = 1;
            }
            v41 = (char *)v43[v44];
          }
          while ( v41 != (char *)&utl::_TreeSentinel );
          if ( v42 == v78
            || (unsigned __int8)utl::operator<<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
                                  (char *)v40 + 80,
                                  v42 + 3) )
          {
LABEL_68:
            utl::_Tree<_GUID,utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,unsigned long>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,unsigned long>>>,0>::find<void>(
              v84,
              v87,
              (char *)v40 + 140);
            v45 = v87[0];
            if ( (_QWORD *)v87[0] == v84 )
              break;
            Id = Container::Manager::Core::ResourceHandle::GetId(*i);
            v47 = Container::Manager::Core::ResourceHandle::GetId(*(Container::Manager::Core::ResourceHandle **)(v45 + 40));
            if ( *(_QWORD *)&v47->Data1 != *(_QWORD *)&Id->Data1 )
              break;
            v31 = *(_QWORD *)v47->Data4;
            if ( v31 != *(_QWORD *)Id->Data4 )
              break;
          }
        }
LABEL_90:
        ;
      }
      v48 = *((_QWORD *)v2 + 16);
      *(_QWORD *)&v82 = -1;
      *(__m128i *)v81 = si128;
      v49 = Container::Manager::Core::Details::ResourceBroker::EnumerateIncomingNeighborHandles(
              v48,
              (_DWORD)v40,
              2,
              1,
              (__int64)L"ServicingOrchestrator_Start_Storage",
              (__int64)v81,
              1);
      v50 = v49;
      if ( v49 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x98E,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
          (const char *)(unsigned int)v49,
          v69);
        v65 = v81[0];
        if ( v81[0] != (void *)-1LL )
        {
          utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(
            v63,
            v81[0],
            ((char *)v81[1] - (char *)v81[0]) >> 3);
          v64 = v65;
          goto LABEL_103;
        }
LABEL_104:
        if ( v36 != (_BYTE *)-1LL )
        {
          utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(
            v63,
            v36,
            ((char *)v37 - v36) >> 3);
          operator delete(v36, (const struct std::nothrow_t *)&std::nothrow);
        }
        utl::_Tree<_GUID,utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,unsigned long>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,unsigned long>>>,0>::clear(v84);
        utl::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>>,0>::~_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>>,0>(v78);
        if ( v75 )
          DismDelete();
        LayerSequenceNumberMap = v50;
        goto LABEL_109;
      }
      v51 = v81[0];
      v52 = v81[1];
      for ( j = v81[0]; j != (_QWORD *)v52; ++j )
      {
        if ( (*(_BYTE *)(Container::Manager::Core::ResourceHandle::Get<Container::Manager::Core::Details::ContainerStorage>(*j)
                       + 272)
            & 0x20) != 0 )
        {
          if ( *((_DWORD *)v40 + 13) == 5
            || !*((_DWORD *)v40 + 13)
            || (v54 = Container::Manager::Core::Details::Layer::DeleteOverlayConfigurationIfNeeded(v40),
                v50 = v54,
                v54 >= 0) )
          {
            if ( v51 != (_BYTE *)-1LL )
            {
              utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(
                v31,
                v51,
                (v52 - v51) >> 3);
              operator delete(v51, (const struct std::nothrow_t *)&std::nothrow);
            }
            v2 = v73;
            goto LABEL_90;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x9A8,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
            (const char *)(unsigned int)v54,
            v69);
          if ( v51 == (_BYTE *)-1LL )
            goto LABEL_104;
          utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(
            v63,
            v51,
            (v52 - v51) >> 3);
          v64 = v51;
LABEL_103:
          operator delete(v64, (const struct std::nothrow_t *)&std::nothrow);
          goto LABEL_104;
        }
      }
      v90 = *Container::Manager::Core::ResourceHandle::GetId(*i);
      utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(
        v55,
        v51,
        (v52 - v51) >> 3);
      v57 = *i;
      *i = 0;
      if ( v57 )
      {
        Container::Manager::Core::ResourceHandle::~ResourceHandle(v57);
        operator delete(v57, (const struct std::nothrow_t *)0x58);
      }
      if ( *((_DWORD *)v40 + 13) == 5 || !*((_DWORD *)v40 + 13) )
      {
        v58 = (Container::Manager::Core::Details::ResourceBroker **)v73;
        v59 = (char *)v73 + 176;
        if ( (char *)utl::_Tree<_GUID,_GUID,utl::less<_GUID>,utl::allocator<_GUID>,0>::_FindImpl<_GUID>(
                       (char *)v73 + 176,
                       v40) != v59 )
          goto LABEL_87;
        v32 = Container::Manager::Core::Details::ResourceBroker::DeleteResourceTree(
                v58[16],
                &v90,
                (enum ResourceType)2,
                v60);
        if ( v32 >= 0 )
          goto LABEL_87;
        v61 = 2499;
      }
      else
      {
        v58 = (Container::Manager::Core::Details::ResourceBroker **)v73;
        v32 = Container::Manager::Core::Details::ResourceBroker::DeleteResourceTree(
                *((Container::Manager::Core::Details::ResourceBroker **)v73 + 16),
                &v90,
                (enum ResourceType)2,
                v56);
        if ( v32 >= 0 )
        {
LABEL_87:
          if ( v51 != (_BYTE *)-1LL )
          {
            utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(
              v31,
              v51,
              0);
            operator delete(v51, (const struct std::nothrow_t *)&std::nothrow);
          }
          v2 = (Container::Manager::Core::Details::ServicingOrchestrator *)v58;
          goto LABEL_90;
        }
        v61 = 2513;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v61,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
        (const char *)(unsigned int)v32,
        v69);
      if ( v51 != (_BYTE *)-1LL )
      {
        utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(
          v62,
          v51,
          0);
        operator delete(v51, (const struct std::nothrow_t *)&std::nothrow);
      }
      if ( v36 != (_BYTE *)-1LL )
      {
        utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(
          v62,
          v36,
          ((char *)v37 - v36) >> 3);
        v35 = v36;
        goto LABEL_52;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x95C,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
        (const char *)(unsigned int)v30,
        v66);
      v34 = v81[0];
      if ( v81[0] != (void *)-1LL )
      {
        utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(
          v33,
          v81[0],
          ((char *)v81[1] - (char *)v81[0]) >> 3);
        v35 = v34;
LABEL_52:
        operator delete(v35, (const struct std::nothrow_t *)&std::nothrow);
      }
    }
    utl::_Tree<_GUID,utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,unsigned long>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,unsigned long>>>,0>::clear(v84);
    utl::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>>,0>::~_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>>,0>(v78);
    if ( v75 )
      DismDelete();
    LayerSequenceNumberMap = v32;
    goto LABEL_109;
  }
  while ( 1 )
  {
    v12 = v75;
    v13 = 32LL * v11;
    v87[0] = L"Package_for_RollupFix";
    v14 = -1;
    v87[1] = 21;
    v15 = *(_QWORD *)(v13 + v75);
    v88[0] = v15;
    do
      ++v14;
    while ( *(_WORD *)(v15 + 2 * v14) );
    LOBYTE(v10) = 1;
    v88[1] = v14;
    if ( (unsigned __int8)Csl::StringStartsWith(v88, v87, v10) )
      break;
LABEL_36:
    if ( ++v11 >= v74 )
      goto LABEL_37;
  }
  v72 = 0;
  PackageInfo = DismGetPackageInfo(v76, *(_QWORD *)(v13 + v12), 1, &v72);
  LayerSequenceNumberMap = PackageInfo;
  if ( PackageInfo < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x156,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\csldism.cpp",
      (const char *)(unsigned int)PackageInfo,
      v66);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x931,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
      (const char *)LayerSequenceNumberMap,
      v68);
    goto LABEL_46;
  }
  v17 = v72;
  v18 = 0;
  if ( !*(_DWORD *)(v72 + 156) )
  {
LABEL_34:
    if ( v17 )
      DismDelete();
    goto LABEL_36;
  }
  while ( 1 )
  {
    v89[1] = 7;
    v19 = *(_QWORD *)(*(_QWORD *)(v17 + 148) + 24LL * v18);
    v89[0] = L"version";
    v20 = -1;
    *(_QWORD *)&v90.Data1 = v19;
    do
      ++v20;
    while ( *(_WORD *)(v19 + 2 * v20) );
    *(_QWORD *)v90.Data4 = v20;
    if ( (unsigned __int8)Csl::StringEqualIgnoreCase(&v90, v89) )
      break;
    v17 = v72;
    if ( ++v18 >= *(_DWORD *)(v72 + 156) )
      goto LABEL_34;
  }
  v21 = *(_QWORD *)(*(_QWORD *)(v72 + 148) + 24LL * v18 + 8);
  v85[0] = v86;
  v85[1] = v86;
  v86[0] = 0;
  if ( v21 )
  {
    v22 = -1;
    do
      ++v22;
    while ( *(_WORD *)(v21 + 2 * v22) );
  }
  else
  {
    v22 = 0;
  }
  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                          v85,
                          v21,
                          v22) )
  {
    v24 = utl::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,0>::_NewNodeConstruct<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>(
            v23,
            v85);
    utl::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,0>::_EmplaceImpl(
      v78,
      v81,
      v25,
      v24);
    if ( !v81[0] )
    {
      v27 = 2371;
      goto LABEL_43;
    }
    if ( v85[0] != v86 )
      operator delete(v85[0], (const struct std::nothrow_t *)&std::nothrow);
    v17 = v72;
    goto LABEL_34;
  }
  v27 = 2366;
LABEL_43:
  LayerSequenceNumberMap = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v27,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
    (const char *)0x8007000ELL,
    v66);
  if ( v85[0] != v86 )
    operator delete(v85[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_46:
  if ( v72 )
    DismDelete();
LABEL_48:
  utl::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>>,0>::~_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>>,0>(v78);
LABEL_11:
  if ( v75 )
    DismDelete();
LABEL_109:
  Csl::DismHelper::~DismHelper((Csl::DismHelper *)&v76);
  return LayerSequenceNumberMap;
}

```

## disassembly

```asm
0x18006ab70  mov     rax, rsp
0x18006ab73  push    rbp
0x18006ab74  push    rbx
0x18006ab75  push    rsi
0x18006ab76  push    rdi
0x18006ab77  push    r12
0x18006ab79  push    r13
0x18006ab7b  push    r14
0x18006ab7d  push    r15
0x18006ab7f  lea     rbp, [rsp-58h]
0x18006ab84  sub     rsp, 158h
0x18006ab8b  movaps  xmmword ptr [rax-58h], xmm6
0x18006ab8f  mov     rax, cs:__security_cookie
0x18006ab96  xor     rax, rsp
0x18006ab99  mov     [rbp+90h+var_58], rax
0x18006ab9d  xor     r13d, r13d
0x18006aba0  mov     [rsp+190h+var_140], rcx
0x18006aba5  mov     [rsp+190h+var_150], r13b
0x18006abaa  mov     ebx, r13d
0x18006abad  mov     r12, rcx
0x18006abb0  lea     r8, [rsp+190h+var_150]; bool *
0x18006abb5  mov     edx, ebx; enum UpdateType
0x18006abb7  mov     rcx, r12; this
0x18006abba  call    ?IsUpdateInProgress@ServicingOrchestrator@Details@Core@Manager@Container@@AEBAJW4UpdateType@12345@AEA_N@Z; Container::Manager::Core::Details::ServicingOrchestrator::IsUpdateInProgress(Container::Manager::Core::Details::ServicingOrchestrator::UpdateType,bool &)
0x18006abbf  mov     edi, eax
0x18006abc1  test    eax, eax
0x18006abc3  js      loc_18006B462
0x18006abc9  mov     al, [rsp+190h+var_150]
0x18006abcd  test    al, al
0x18006abcf  jnz     short loc_18006ABDC
0x18006abd1  inc     ebx
0x18006abd3  cmp     ebx, 3
0x18006abd6  jb      short loc_18006ABB0
0x18006abd8  test    al, al
0x18006abda  jz      short loc_18006ABE3
0x18006abdc  xor     eax, eax
0x18006abde  jmp     loc_18006B49A
0x18006abe3  lea     rcx, [rsp+190h+var_128]; this
0x18006abe8  mov     [rsp+190h+var_128], r13d
0x18006abed  mov     [rsp+190h+var_124], r13b
0x18006abf2  call    ?Initialize@DismHelper@Csl@@QEAAJPEBG@Z; Csl::DismHelper::Initialize(ushort const *)
0x18006abf7  mov     ebx, eax
0x18006abf9  test    eax, eax
0x18006abfb  jns     short loc_18006AC1D
0x18006abfd  mov     rcx, [rbp+98h]; this
0x18006ac04  lea     r8, aOnecoreBaseGen_65; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18006ac0b  mov     r9d, eax; char *
0x18006ac0e  mov     edx, 91Bh; void *
0x18006ac13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ac18  jmp     loc_18006B3F2
0x18006ac1d  mov     ecx, [rsp+190h+var_128]
0x18006ac21  lea     r8, [rsp+190h+var_138]
0x18006ac26  lea     rdx, [rsp+190h+var_130]
0x18006ac2b  mov     [rsp+190h+var_138], r13d
0x18006ac30  mov     [rsp+190h+var_130], r13
0x18006ac35  call    cs:__imp_DismGetPackages
0x18006ac3c  nop     dword ptr [rax+rax+00h]
0x18006ac41  mov     ebx, eax
0x18006ac43  test    eax, eax
0x18006ac45  jns     short loc_18006AC9C
0x18006ac47  mov     rcx, [rbp+98h]; this
0x18006ac4e  lea     r8, aOnecoreBaseGen_21; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18006ac55  mov     r9d, eax; char *
0x18006ac58  mov     edx, 175h; void *
0x18006ac5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ac62  mov     rcx, [rbp+98h]; this
0x18006ac69  lea     r8, aOnecoreBaseGen_65; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18006ac70  mov     r9d, ebx; char *
0x18006ac73  mov     edx, 91Fh; void *
0x18006ac78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ac7d  mov     rcx, [rsp+190h+var_130]
0x18006ac82  test    rcx, rcx
0x18006ac85  jz      loc_18006B3F2
0x18006ac8b  call    cs:__imp_DismDelete
0x18006ac92  nop     dword ptr [rax+rax+00h]
0x18006ac97  jmp     loc_18006B3F2
0x18006ac9c  lea     rax, [rsp+190h+var_120]
0x18006aca1  mov     [rbp+90h+var_108], r13
0x18006aca5  mov     [rsp+190h+var_120], rax
0x18006acaa  lea     r15, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18006acb1  lea     rax, [rsp+190h+var_120]
0x18006acb6  or      r14, 0FFFFFFFFFFFFFFFFh
0x18006acba  mov     edi, r13d
0x18006acbd  mov     [rsp+190h+var_118], rax
0x18006acc2  mov     [rbp+90h+var_110], rax
0x18006acc6  cmp     [rsp+190h+var_138], r13d
0x18006accb  jbe     loc_18006AE6A
0x18006acd1  mov     rsi, [rsp+190h+var_130]
0x18006acd6  lea     rax, aPackageForRoll; "Package_for_RollupFix"
0x18006acdd  mov     ebx, edi
0x18006acdf  shl     rbx, 5
0x18006ace3  mov     [rbp+90h+var_98], rax
0x18006ace7  mov     rax, r14
0x18006acea  mov     [rbp+90h+var_90], 15h
0x18006acf2  mov     rcx, [rbx+rsi]
0x18006acf6  mov     [rbp+90h+var_88], rcx
0x18006acfa  inc     rax
0x18006acfd  cmp     [rcx+rax*2], r13w
0x18006ad02  jnz     short loc_18006ACFA
0x18006ad04  mov     r8b, 1
0x18006ad07  mov     [rbp+90h+var_80], rax
0x18006ad0b  lea     rdx, [rbp+90h+var_98]
0x18006ad0f  lea     rcx, [rbp+90h+var_88]
0x18006ad13  call    ?StringStartsWith@Csl@@YA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@0_N@Z; Csl::StringStartsWith(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &,utl::basic_string_view<ushort,utl::char_traits<ushort>> const &,bool)
0x18006ad18  test    al, al
0x18006ad1a  jz      loc_18006AE5E
0x18006ad20  mov     ecx, [rsp+190h+var_128]
0x18006ad24  lea     r9, [rsp+190h+var_148]
0x18006ad29  mov     [rsp+190h+var_148], r13
0x18006ad2e  mov     r8d, 1
0x18006ad34  mov     rdx, [rbx+rsi]
0x18006ad38  call    cs:__imp_DismGetPackageInfo
0x18006ad3f  nop     dword ptr [rax+rax+00h]
0x18006ad44  mov     ebx, eax
0x18006ad46  test    eax, eax
0x18006ad48  js      loc_18006AF28
0x18006ad4e  mov     rcx, [rsp+190h+var_148]
0x18006ad53  mov     ebx, r13d
0x18006ad56  cmp     [rcx+9Ch], r13d
0x18006ad5d  jbe     loc_18006AE4D
0x18006ad63  mov     eax, ebx
0x18006ad65  mov     [rbp+90h+var_70], 7
0x18006ad6d  lea     rsi, [rax+rax*2]
0x18006ad71  mov     rax, [rcx+94h]
0x18006ad78  mov     rcx, [rax+rsi*8]
0x18006ad7c  lea     rax, aVersion; "version"
0x18006ad83  mov     [rbp+90h+var_78], rax
0x18006ad87  mov     rax, r14
0x18006ad8a  mov     qword ptr [rbp+90h+var_68.Data1], rcx
0x18006ad8e  inc     rax
0x18006ad91  cmp     [rcx+rax*2], r13w
0x18006ad96  jnz     short loc_18006AD8E
0x18006ad98  lea     rdx, [rbp+90h+var_78]
0x18006ad9c  mov     qword ptr [rbp+90h+var_68.Data4], rax
0x18006ada0  lea     rcx, [rbp+90h+var_68]
0x18006ada4  call    ?StringEqualIgnoreCase@Csl@@YA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@0@Z; Csl::StringEqualIgnoreCase(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &,utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x18006ada9  test    al, al
0x18006adab  jnz     short loc_18006ADC1
0x18006adad  mov     rcx, [rsp+190h+var_148]
0x18006adb2  inc     ebx
0x18006adb4  cmp     ebx, [rcx+9Ch]
0x18006adba  jb      short loc_18006AD63
0x18006adbc  jmp     loc_18006AE4D
0x18006adc1  mov     rax, [rsp+190h+var_148]
0x18006adc6  mov     rcx, [rax+94h]
0x18006adcd  lea     rax, [rbp+90h+var_A8]
0x18006add1  mov     rdx, [rcx+rsi*8+8]
0x18006add6  mov     [rbp+90h+var_B8], rax
0x18006adda  lea     rax, [rbp+90h+var_A8]
0x18006adde  mov     [rbp+90h+var_B0], rax
0x18006ade2  mov     [rbp+90h+var_A8], r13w
0x18006ade7  test    rdx, rdx
0x18006adea  jz      short loc_18006ADFB
0x18006adec  mov     r8, r14
0x18006adef  inc     r8
0x18006adf2  cmp     [rdx+r8*2], r13w
0x18006adf7  jnz     short loc_18006ADEF
0x18006adf9  jmp     short loc_18006ADFE
0x18006adfb  mov     r8, r13
0x18006adfe  lea     rcx, [rbp+90h+var_B8]
0x18006ae02  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18006ae07  test    al, al
0x18006ae09  jz      loc_18006AEF1
0x18006ae0f  lea     rdx, [rbp+90h+var_B8]
0x18006ae13  call    ??$_NewNodeConstruct@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@?$_Tree@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@U?$less@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@$0A@@utl@@AEAAPEAU?$_TreeNode@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@1@$$QEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@@Z; utl::_Tree<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::less<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,0>::_NewNodeConstruct<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x18006ae18  mov     r9, rax
0x18006ae1b  lea     rdx, [rbp+90h+var_100]
0x18006ae1f  lea     rcx, [rsp+190h+var_120]
0x18006ae24  call    ?_EmplaceImpl@?$_Tree@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@U?$less@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@$0A@@utl@@AEAA?AU?$pair@V?$_TreeConstIt@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@utl@@_N@2@PEAU?$_TreeNode@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@0@Z; utl::_Tree<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::less<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,0>::_EmplaceImpl(utl::_TreeNode<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>> *,utl::_TreeNode<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>> *)
0x18006ae29  cmp     [rbp+90h+var_100], r13
0x18006ae2d  jz      loc_18006AEEA
0x18006ae33  mov     rcx, [rbp+90h+var_B8]; void *
0x18006ae37  lea     rax, [rbp+90h+var_A8]
0x18006ae3b  cmp     rcx, rax
0x18006ae3e  jz      short loc_18006AE48
0x18006ae40  mov     rdx, r15; struct std::nothrow_t *
0x18006ae43  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006ae48  mov     rcx, [rsp+190h+var_148]
0x18006ae4d  test    rcx, rcx
0x18006ae50  jz      short loc_18006AE5E
0x18006ae52  call    cs:__imp_DismDelete
0x18006ae59  nop     dword ptr [rax+rax+00h]
0x18006ae5e  inc     edi
0x18006ae60  cmp     edi, [rsp+190h+var_138]
0x18006ae64  jb      loc_18006ACD1
0x18006ae6a  mov     rcx, [r12+80h]
0x18006ae72  lea     rax, [rbp+90h+var_D8]
0x18006ae76  mov     [rbp+90h+var_D8], rax
0x18006ae7a  lea     r8, [rbp+90h+var_100]
0x18006ae7e  lea     rax, [rbp+90h+var_D8]
0x18006ae82  mov     [rbp+90h+var_C0], r13
0x18006ae86  xorps   xmm0, xmm0
0x18006ae89  mov     [rbp+90h+var_D0], rax
0x18006ae8d  mov     [rbp+90h+var_C8], rax
0x18006ae91  lea     rdx, [rbp+90h+var_D8]
0x18006ae95  xor     eax, eax
0x18006ae97  mov     [rbp+90h+var_E0], rax
0x18006ae9b  movups  xmmword ptr [rbp+90h+var_100], xmm0
0x18006ae9f  movups  [rbp+90h+var_F0], xmm0
0x18006aea3  call    ?GetLayerSequenceNumberMap@ServicingOrchestrator@Details@Core@Manager@Container@@SAJAEAVResourceBroker@2345@AEAV?$map@U_GUID@@U?$pair@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@K@utl@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@U?$pair@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@K@utl@@@utl@@@3@@utl@@AEBV?$optional@V?$set@U_GUID@@U?$less@U_GUID@@@utl@@V?$allocator@U_GUID@@@3@@utl@@@8@@Z; Container::Manager::Core::Details::ServicingOrchestrator::GetLayerSequenceNumberMap(Container::Manager::Core::Details::ResourceBroker &,utl::map<_GUID,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,ulong>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,ulong>>>> &,utl::optional<utl::set<_GUID,utl::less<_GUID>,utl::allocator<_GUID>>> const &)
0x18006aea8  mov     ebx, eax
0x18006aeaa  cmp     byte ptr [rbp+90h+var_E0], r13b
0x18006aeae  jz      short loc_18006AEB9
0x18006aeb0  lea     rcx, [rbp+90h+var_100]
0x18006aeb4  call    ??1?$_Tree@PEAVContainerHandle@Core@Manager@Container@@PEAV1234@U?$less@PEAVContainerHandle@Core@Manager@Container@@@utl@@V?$allocator@PEAVContainerHandle@Core@Manager@Container@@@6@$0A@@utl@@IEAA@XZ; utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(void)
0x18006aeb9  test    ebx, ebx
0x18006aebb  jns     loc_18006AF83
0x18006aec1  mov     rcx, [rbp+98h]; this
0x18006aec8  lea     r8, aOnecoreBaseGen_65; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18006aecf  mov     r9d, ebx; char *
0x18006aed2  mov     edx, 955h; void *
0x18006aed7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006aedc  lea     rcx, [rbp+90h+var_D8]
0x18006aee0  call    ?clear@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@U?$pair@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@K@utl@@@utl@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@U?$pair@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@K@utl@@@utl@@@3@$0A@@utl@@QEAAXXZ; utl::_Tree<_GUID,utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,ulong>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,ulong>>>,0>::clear(void)
0x18006aee5  jmp     loc_18006AF74
0x18006aeea  mov     edx, 943h
0x18006aeef  jmp     short loc_18006AEF6
0x18006aef1  mov     edx, 93Eh; void *
0x18006aef6  mov     rcx, [rbp+98h]; this
0x18006aefd  lea     r8, aOnecoreBaseGen_65; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18006af04  mov     ebx, 8007000Eh
0x18006af09  mov     r9d, ebx; char *
0x18006af0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006af11  mov     rcx, [rbp+90h+var_B8]; void *
0x18006af15  lea     rax, [rbp+90h+var_A8]
0x18006af19  cmp     rcx, rax
0x18006af1c  jz      short loc_18006AF5E
0x18006af1e  mov     rdx, r15; struct std::nothrow_t *
0x18006af21  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006af26  jmp     short loc_18006AF5E
0x18006af28  mov     rcx, [rbp+98h]; this
0x18006af2f  lea     r8, aOnecoreBaseGen_21; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18006af36  mov     r9d, ebx; char *
0x18006af39  mov     edx, 156h; void *
0x18006af3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006af43  mov     rcx, [rbp+98h]; this
0x18006af4a  lea     r8, aOnecoreBaseGen_65; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18006af51  mov     r9d, ebx; char *
0x18006af54  mov     edx, 931h; void *
0x18006af59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006af5e  mov     rcx, [rsp+190h+var_148]
0x18006af63  test    rcx, rcx
0x18006af66  jz      short loc_18006AF74
0x18006af68  call    cs:__imp_DismDelete
0x18006af6f  nop     dword ptr [rax+rax+00h]
0x18006af74  lea     rcx, [rsp+190h+var_120]
0x18006af79  call    ??1?$_Tree@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@K@2@U?$less@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@K@utl@@@2@$0A@@utl@@IEAA@XZ; utl::_Tree<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ulong>,utl::less<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ulong>>,0>::~_Tree<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ulong>,utl::less<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ulong>>,0>(void)
0x18006af7e  jmp     loc_18006AC7D
0x18006af83  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18006af8b  lea     r9, [rbp+90h+var_100]
0x18006af8f  mov     rcx, [r12+80h]
0x18006af97  lea     r8, aServicingorche; "ServicingOrchestrator_Start_Layer"
0x18006af9e  mov     edx, 2
0x18006afa3  mov     qword ptr [rbp+90h+var_F0], r14
0x18006afa7  movdqu  xmmword ptr [rbp+90h+var_100], xmm6
0x18006afac  call    ?EnumerateResourceHandles@ResourceBroker@Details@Core@Manager@Container@@QEAAJW4ResourceType@2345@PEBGAEAV?$vector@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@V?$allocator@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@@Z; Container::Manager::Core::Details::ResourceBroker::EnumerateResourceHandles(Container::Manager::Core::Details::ResourceType,ushort const *,utl::vector<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>> &)
0x18006afb1  mov     edi, eax
0x18006afb3  test    eax, eax
0x18006afb5  jns     short loc_18006B029
0x18006afb7  mov     rcx, [rbp+98h]; this
0x18006afbe  lea     r8, aOnecoreBaseGen_65; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18006afc5  mov     r9d, eax; char *
0x18006afc8  mov     edx, 95Ch; void *
0x18006afcd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006afd2  mov     rbx, [rbp+90h+var_100]
0x18006afd6  cmp     rbx, r14
0x18006afd9  jz      short loc_18006AFF9
0x18006afdb  mov     r8, [rbp+90h+var_100+8]
0x18006afdf  mov     rdx, rbx
0x18006afe2  sub     r8, rbx
0x18006afe5  sar     r8, 3
0x18006afe9  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@0@PEAV?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@_K@Z; utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>> &,wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>> *,unsigned __int64)
0x18006afee  mov     rdx, r15; struct std::nothrow_t *
0x18006aff1  mov     rcx, rbx; void *
0x18006aff4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006aff9  lea     rcx, [rbp+90h+var_D8]
0x18006affd  call    ?clear@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@U?$pair@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@K@utl@@@utl@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@U?$pair@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@K@utl@@@utl@@@3@$0A@@utl@@QEAAXXZ; utl::_Tree<_GUID,utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,ulong>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,ulong>>>,0>::clear(void)
0x18006b002  lea     rcx, [rsp+190h+var_120]
0x18006b007  call    ??1?$_Tree@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@K@2@U?$less@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@K@utl@@@2@$0A@@utl@@IEAA@XZ; utl::_Tree<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ulong>,utl::less<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ulong>>,0>::~_Tree<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ulong>,utl::less<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ulong>>,0>(void)
0x18006b00c  mov     rcx, [rsp+190h+var_130]
0x18006b011  test    rcx, rcx
0x18006b014  jz      short loc_18006B022
0x18006b016  call    cs:__imp_DismDelete
0x18006b01d  nop     dword ptr [rax+rax+00h]
0x18006b022  mov     ebx, edi
0x18006b024  jmp     loc_18006B3F2
0x18006b029  mov     r15, [rbp+90h+var_100]
0x18006b02d  mov     rbx, [rbp+90h+var_100+8]
0x18006b031  mov     r14, r15
0x18006b034  cmp     r14, rbx
0x18006b037  jz      loc_18006B403
0x18006b03d  mov     rcx, [r14]
0x18006b040  call    ??$Get@VLayer@Details@Core@Manager@Container@@@ResourceHandle@Core@Manager@Container@@QEBAPEAVLayer@Details@123@XZ; Container::Manager::Core::ResourceHandle::Get<Container::Manager::Core::Details::Layer>(void)
0x18006b045  mov     r13, rax
0x18006b048  test    byte ptr [rax+120h], 10h
0x18006b04f  jz      loc_18006B270
0x18006b055  cmp     byte ptr [rax+168h], 0
0x18006b05c  jnz     loc_18006B270
0x18006b062  lea     rax, [rsp+190h+var_120]
0x18006b067  cmp     [rbp+90h+var_110], rax
  ... truncated ...
```
