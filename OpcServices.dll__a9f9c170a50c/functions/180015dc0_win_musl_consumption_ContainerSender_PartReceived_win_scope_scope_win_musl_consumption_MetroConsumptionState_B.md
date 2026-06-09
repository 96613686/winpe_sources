# win_musl::consumption::ContainerSender::PartReceived(win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>)

- ea: `0x180015dc0`
- end: `0x180016b41`
- name: `?PartReceived@ContainerSender@consumption@win_musl@@AEAAXV?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z`
- size: `3457`
- prototype: ``
- caller_count: `2`
- callee_count: `49`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180044950`
- `0x1800841a0`

## callees

- `0x1800016b0`
- `0x1800016dc`
- `0x1800019b0`
- `0x18000d200`
- `0x18000d950`
- `0x180010524`
- `0x180010a00`
- `0x180015114`
- `0x180015af4`
- `0x180015dc0`
- `0x180016b48`
- `0x180016cf4`
- `0x180017c10`
- `0x180017dd0`
- `0x1800186b8`
- `0x180018c00`
- `0x180018d18`
- `0x18001a810`
- `0x18001c5d0`
- `0x18001ca9c`
- `0x18003c494`
- `0x18003cfa0`
- `0x18003d9fc`
- `0x18003fe5c`
- `0x1800405c0`
- `0x1800415e8`
- `0x1800425d8`
- `0x1800431ac`
- `0x180044af8`
- `0x1800460f0`
- `0x18004f8d4`
- `0x18004faa8`
- `0x18005155c`
- `0x1800517a0`
- `0x1800654b0`
- `0x1800696e4`
- `0x180075cb0`
- `0x180079300`
- `0x180079480`
- `0x180084b24`
- `0x180085438`
- `0x1800aaf88`
- `0x1800cce54`
- `0x1800cd38c`
- `0x1800cdb60`
- `0x1800d5fe4`
- `0x1800e810c`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180015f1e`
- `msvcrt!memcpy_s` at `0x1800160d9`
- `msvcrt!memcpy_s` at `0x180015f1e`
- `msvcrt!memcpy_s` at `0x1800160d9`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x1800164db`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x1800164db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015e2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015e2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001632a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001632a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015e1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015e1c`

## string_xrefs

- `0x18001646a`: `PartUri`
- `0x180016432`: `Part has relationship content type, but its part Uri (%{PartUri}) is not a relationship Uri.`

## pseudocode

```c
// Hidden C++ exception states: #wind=41
void __fastcall win_musl::consumption::ContainerSender::PartReceived(__int64 a1, _QWORD *a2)
{
  char v4; // di
  __int64 v5; // rbx
  bool v6; // dl
  win_dox *v7; // rcx
  __int64 v8; // r12
  __int64 v9; // rax
  _QWORD *v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rdi
  unsigned __int64 v16; // rsi
  _QWORD *v17; // r8
  void **v18; // rcx
  unsigned __int64 v19; // rdx
  void **v20; // r8
  void **v21; // rcx
  __int64 *v22; // r9
  __int64 *v23; // rax
  _QWORD *v24; // rcx
  bool v25; // cf
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v29; // r9
  __int64 ByteCollection; // r12
  __int64 v31; // rdi
  int v32; // r13d
  unsigned __int64 v33; // rdx
  unsigned __int64 v34; // rsi
  _QWORD *v35; // r8
  void **v36; // rcx
  void **v37; // rcx
  _WORD *v38; // rax
  unsigned __int64 v39; // r10
  unsigned __int64 v40; // rcx
  void **v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // rdx
  _QWORD *v44; // rax
  _BYTE *v45; // r12
  __int64 v46; // r14
  void (__fastcall *v47)(__int64, __int64 *, char *, _QWORD, __int64 *, __int64); // rsi
  __int64 v48; // rdi
  __int64 v49; // rdx
  __int64 v50; // r8
  __int64 AbsoluteUri; // rax
  __int64 v53; // rdx
  __int64 v54; // r8
  __int64 v55; // r9
  __int64 v56; // rax
  __int64 v57; // rdx
  __int64 v58; // rdi
  __int64 v59; // rbx
  win_musl::Formatter *v60; // rax
  const wchar_t *v61; // rax
  __int64 v62; // rcx
  void **v63; // rdx
  const wchar_t *v64; // r8
  _WORD *v65; // rax
  _WORD *v66; // rax
  __int64 ContainerPartReceiver; // rax
  _QWORD *v68; // rdi
  const char *v69; // rdx
  __int64 v70; // r8
  _QWORD *v71; // rdi
  __int64 v72; // rdi
  __int64 v73; // rax
  __int64 v74; // rdx
  __int64 v75; // r8
  __int64 v76; // rsi
  __int64 v77; // rsi
  void (__fastcall *v78)(__int64, __int128 *); // rdi
  __int64 v79; // rax
  __int64 v80; // rdx
  __int64 v81; // r8
  __int64 v82; // r9
  __int64 v83; // rax
  __int64 v84; // rdi
  __int64 v85; // rbx
  win_musl::Formatter *v86; // rax
  struct win_musl::TStringEllipseBase *v87; // rax
  __int64 v88; // rdi
  __int64 v89; // rbx
  __int64 v90; // rbx
  win_musl::Formatter *v91; // rax
  struct win_musl::TStringEllipseBase *v92; // rax
  __int64 v93; // rax
  __int64 v94; // rdx
  __int64 v95; // r8
  __int64 v96; // r9
  __int64 v97; // rax
  __int64 v98; // rdx
  __int64 v99; // rax
  __int64 v100; // rdx
  __int64 v101; // r8
  __int64 v102; // rax
  __int64 v103; // r10
  int v104; // r9d
  __int64 v105; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD *v106; // [rsp+50h] [rbp-B8h] BYREF
  const char *v107; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v108; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v109; // [rsp+68h] [rbp-A0h]
  __int64 v110; // [rsp+70h] [rbp-98h]
  _BYTE *v111; // [rsp+78h] [rbp-90h] BYREF
  __int64 v112; // [rsp+80h] [rbp-88h]
  char v113[8]; // [rsp+88h] [rbp-80h] BYREF
  void *v114[2]; // [rsp+90h] [rbp-78h] BYREF
  unsigned __int64 v115; // [rsp+A0h] [rbp-68h]
  unsigned __int64 v116; // [rsp+A8h] [rbp-60h]
  __int64 v117; // [rsp+B0h] [rbp-58h]
  _QWORD *v118; // [rsp+B8h] [rbp-50h]
  __int64 v119; // [rsp+C0h] [rbp-48h]
  char v120[8]; // [rsp+C8h] [rbp-40h] BYREF
  void *Destination[2]; // [rsp+D0h] [rbp-38h] BYREF
  unsigned __int64 v122; // [rsp+E0h] [rbp-28h]
  unsigned __int64 v123; // [rsp+E8h] [rbp-20h]
  __int128 v124; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v125; // [rsp+100h] [rbp-8h]
  __int64 v126; // [rsp+108h] [rbp+0h]
  _QWORD v127[5]; // [rsp+118h] [rbp+10h] BYREF
  char v128[8]; // [rsp+140h] [rbp+38h] BYREF
  void *Block; // [rsp+148h] [rbp+40h]
  __int64 v130; // [rsp+158h] [rbp+50h]
  unsigned __int64 v131; // [rsp+160h] [rbp+58h]
  _BYTE v132[48]; // [rsp+168h] [rbp+60h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+198h] [rbp+90h] BYREF
  _DWORD v134[2]; // [rsp+1B0h] [rbp+A8h] BYREF
  const char *v135; // [rsp+1B8h] [rbp+B0h]
  char v136[56]; // [rsp+1C0h] [rbp+B8h] BYREF
  GUID v137; // [rsp+1F8h] [rbp+F0h]
  int v138; // [rsp+220h] [rbp+118h]
  _BYTE v139[48]; // [rsp+238h] [rbp+130h] BYREF
  _BYTE v140[96]; // [rsp+268h] [rbp+160h] BYREF
  _BYTE v141[160]; // [rsp+2C8h] [rbp+1C0h] BYREF

  v117 = -2;
  v118 = a2;
  v4 = 0;
  LODWORD(v105) = 0;
  v5 = a1 + 200;
  v119 = a1 + 200;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 200));
  v7 = (win_dox *)*(unsigned int *)(v5 + 44);
  *(_DWORD *)(v5 + 44) = (_DWORD)v7 + 1;
  if ( !(_DWORD)v7 )
    *(_DWORD *)(v5 + 40) = GetCurrentThreadId();
  LOBYTE(v7) = *(_BYTE *)(a1 + 256);
  win_dox::ThrowIfFailed(v7, v6);
  v8 = win_musl::InitOnceSingleton<win_musl::ContentType,win_musl::consumption::ContainerSender::RelationshipsContentTypeSingleton_tag>::Get<win_musl::consumption::ContainerSender::SingletonInitializer>();
  if ( *a2 && (v9 = a2[1]) != 0 )
  {
    v10 = (_QWORD *)(v9 + 8);
    if ( *(_QWORD *)(v9 + 32) >= 8u )
      v10 = (_QWORD *)*v10;
    win_dox::CreatePartUriInternal(&v108, v10);
    win_musl::MimeTable::FindContentType(a1 + 72, v128, &v108);
    if ( v130 )
    {
      win_musl::ContentTypeFromStdString(v141, v128);
      v15 = a2[1] + 40LL;
      v123 = 7;
      v122 = 0;
      LOWORD(Destination[0]) = 0;
      v16 = *(_QWORD *)(v15 + 24);
      if ( v120 == (char *)v15 )
      {
        std::wstring::erase(v120, *(_QWORD *)(v15 + 24), -1);
        std::wstring::erase(v120, 0, 0);
      }
      else
      {
        if ( v16 > 0x7FFFFFFFFFFFFFFELL )
          std::_String_base::_Xlen();
        if ( v123 < v16 )
        {
          std::wstring::_Copy(v120, *(_QWORD *)(v15 + 24), v122);
          if ( !v16 )
            goto LABEL_20;
        }
        else if ( !v16 )
        {
          v65 = (_WORD *)std::wstring::_Myptr(v120, v12, v13, v14);
          v122 = 0;
          *v65 = 0;
          goto LABEL_20;
        }
        v17 = (_QWORD *)(v15 + 8);
        if ( *(_QWORD *)(v15 + 32) >= 8u )
          v17 = (_QWORD *)*v17;
        v18 = Destination;
        if ( v123 >= 8 )
          v18 = (void **)Destination[0];
        memcpy_s(v18, 2 * v123, v17, 2 * v16);
        v21 = Destination;
        if ( v123 >= 8 )
          v21 = (void **)Destination[0];
        v122 = v16;
        *((_WORD *)v21 + v16) = 0;
      }
LABEL_20:
      v22 = *(__int64 **)(a1 + 160);
      v23 = (__int64 *)v22[1];
      while ( !*((_BYTE *)v23 + 65) )
      {
        v20 = Destination;
        if ( v123 >= 8 )
          v20 = (void **)Destination[0];
        v19 = v122;
        if ( v23[6] < v122 )
          v19 = v23[6];
        v24 = v23 + 4;
        if ( (unsigned __int64)v23[7] >= 8 )
          v24 = (_QWORD *)*v24;
        while ( v19 )
        {
          v25 = *(_WORD *)v24 < *(_WORD *)v20;
          if ( *(_WORD *)v24 != *(_WORD *)v20 )
            goto LABEL_30;
          v24 = (_QWORD *)((char *)v24 + 2);
          v20 = (void **)((char *)v20 + 2);
          --v19;
        }
        v25 = v23[6] < v122;
LABEL_30:
        if ( v25 )
        {
          v23 = (__int64 *)v23[2];
        }
        else
        {
          v22 = v23;
          v23 = (__int64 *)*v23;
        }
      }
      if ( v22 != *(__int64 **)(a1 + 160) )
      {
        v38 = (_WORD *)std::wstring::_Myptr(v22 + 3, v19, v20, v22);
        v40 = v39;
        if ( v122 < v39 )
          v40 = v122;
        v41 = Destination;
        if ( v123 >= 8 )
          v41 = (void **)Destination[0];
        while ( v40 )
        {
          if ( *(_WORD *)v41 != *v38 )
          {
            if ( *(_WORD *)v41 < *v38 )
              goto LABEL_34;
            goto LABEL_93;
          }
          v41 = (void **)((char *)v41 + 2);
          ++v38;
          --v40;
        }
        if ( v122 < v39 )
          goto LABEL_34;
LABEL_93:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
        {
          AbsoluteUri = win_dox::Uri::GetAbsoluteUri(&v108, v127);
          v56 = std::wstring::_Myptr(AbsoluteUri, v53, v54, v55);
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_26ae4a55cde332a86a17bdc34ef7b6d8_Traceguids, v56);
          LOBYTE(v57) = 1;
          std::wstring::_Tidy(v127, v57, 0);
        }
        goto LABEL_76;
      }
LABEL_34:
      if ( (unsigned __int8)win_musl::DetectPrefixCollision(v120, a1 + 152) )
      {
        std::wstring::wstring(v127, L"Part %{Part} has a prefix collision");
        v84 = win_musl::Formatter::Formatter(v140, v127);
        v85 = win_dox::Uri::GetAbsoluteUri(&v108, &v124);
        std::wstring::wstring(v132, L"Part");
        v86 = (win_musl::Formatter *)win_musl::Formatter::insert<std::wstring>(v84, v132, v85);
        v87 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v86);
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x11Du,
          0x80510004,
          v87);
        throw (SplException::THResultException *)pExceptionObject;
      }
      if ( win_dox::OpcPartUri::IsRelationshipsPartUri((win_dox::OpcPartUri *)&v108) )
      {
        if ( !(unsigned __int8)operator==(v141, v8) )
        {
          std::wstring::wstring(
            v127,
            L"Relationship part %{RelsPart} has non-relationship content type: %{ContentType}");
          v88 = win_musl::Formatter::Formatter(v140, v127);
          v89 = win_dox::Uri::GetAbsoluteUri(&v108, v139);
          std::wstring::wstring(v132, L"RelsPart");
          v90 = win_musl::Formatter::insert<std::wstring>(v88, v132, v89);
          std::wstring::wstring(&v124, L"ContentType");
          v91 = (win_musl::Formatter *)win_musl::Formatter::insert<std::wstring>(v90, &v124, v128);
          v92 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v91);
          win_musl::detail::ThrowBuilder<SplException::THResultException>(
            (SplException::TSystemException *)pExceptionObject,
            0x129u,
            0x80510005,
            v92);
          throw (SplException::THResultException *)pExceptionObject;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
        {
          v93 = win_dox::Uri::GetAbsoluteUri(&v108, v127);
          v97 = std::wstring::_Myptr(v93, v94, v95, v96);
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, WPP_26ae4a55cde332a86a17bdc34ef7b6d8_Traceguids, v97);
          LOBYTE(v98) = 1;
          std::wstring::_Tidy(v127, v98, 0);
        }
        v62 = 12;
        if ( v122 < 0xC )
          v62 = v122;
        v63 = Destination;
        if ( v123 >= 8 )
          v63 = (void **)Destination[0];
        v64 = L"/_RELS/.RELS";
        while ( v62 )
        {
          if ( *(_WORD *)v63 != *v64 )
            goto LABEL_76;
          v63 = (void **)((char *)v63 + 2);
          ++v64;
          --v62;
        }
        if ( v122 == 12 )
        {
          v77 = *(_QWORD *)(win_musl::consumption::MetroConsumptionState::GetContainerPartReceiver(*(_QWORD *)(a1 + 64))
                          + 8);
          v78 = *(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v77 + 40LL);
          win_dox::ByteCollection::ByteCollection(
            (win_dox::ByteCollection *)&v124,
            (const struct win_dox::ByteCollection *)(a2[1] + 88LL));
          v78(v77, &v124);
          *(_QWORD *)&v124 = &win_dox::OpcRelationshipSender::`vftable';
          v76 = 0;
          if ( *((_QWORD *)&v124 + 1) )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v124 + 1) + 16LL))(*((_QWORD *)&v124 + 1));
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert(
            a1 + 152,
            v132,
            v120);
          ContainerPartReceiver = win_musl::consumption::MetroConsumptionState::GetContainerPartReceiver(*(_QWORD *)(a1 + 64));
          if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(ContainerPartReceiver + 8) + 48LL))(*(_QWORD *)(ContainerPartReceiver + 8)) == 2 )
          {
            win_musl::consumption::MetroConsumptionState::IncrementOutstandingWork(*(win_musl::consumption::MetroConsumptionState **)(a1 + 64));
            v68 = (_QWORD *)win_scope::scope<IWin7InternalPartSender *,win_scope::const_policies<win_scope::com_policies>>::scope<IWin7InternalPartSender *,win_scope::const_policies<win_scope::com_policies>>(
                              &v107,
                              a1);
            v106 = v68;
            win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>(
              v127,
              v68);
            v127[1] = win_musl::consumption::ContainerSender::RootRelationshipFiber;
            v127[2] = 0;
            v127[3] = 0;
            if ( *v68 )
            {
              win_scope::close_com::close<win_musl::consumption::ContainerSender * *>(v68, v69, v70);
              *v68 = 0;
            }
            v71 = operator new(0x70u, v69, v70);
            v106 = v71;
            if ( v71 )
            {
              win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>(
                &v124,
                v127);
              *((_QWORD *)&v124 + 1) = win_musl::consumption::ContainerSender::RootRelationshipFiber;
              v125 = 0;
              v126 = 0;
              win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>(
                &v105,
                *(_QWORD *)(a1 + 64) + 32LL);
              v76 = win_musl::UnknownOnly<win_musl::FiberStream<win_musl::FiberStreamClient<win_musl::consumption::ContainerSender,win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>>>,win_mp_lib::null_type,win_mp_lib::null_type>::UnknownOnly<win_musl::FiberStream<win_musl::FiberStreamClient<win_musl::consumption::ContainerSender,win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>>>,win_mp_lib::null_type,win_mp_lib::null_type>(
                      v71,
                      &v105,
                      &v124);
            }
            v72 = 0;
            v106 = 0;
            if ( v76 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 8LL))(v76);
              v72 = v76;
              v106 = (_QWORD *)v76;
            }
            win_musl::FiberStream<win_musl::FiberStreamClient<win_musl::consumption::ContainerSender,win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>>>::GetByteReceiver(
              v72,
              v132);
            win_dox::ByteCollection::ByteCollection(
              (win_dox::ByteCollection *)&v111,
              (const struct win_dox::ByteCollection *)(a2[1] + 88LL));
            v73 = win_dox::CreateSenderBase<IByteCollection>::CreateSender(&v111, &v124);
            win_dox::StartSendBase<IByteSender>::StartSend<win_dox::ByteReceiver>(v73, v132);
            *(_QWORD *)&v124 = &win_dox::OpcRelationshipSender::`vftable';
            if ( *((_QWORD *)&v124 + 1) )
            {
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v124 + 1) + 16LL))(*((_QWORD *)&v124 + 1));
              *((_QWORD *)&v124 + 1) = 0;
            }
            if ( v112 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v112 + 16LL))(v112);
            win_dox::ByteReceiver::~ByteReceiver((win_dox::ByteReceiver *)v132);
            if ( v72 )
              win_scope::close_com::close<win_musl::consumption::ContainerSender * *>(&v106, v74, v75);
            if ( v127[0] )
              win_scope::close_com::close<win_musl::consumption::ContainerSender * *>(v127, v74, v75);
          }
        }
        goto LABEL_76;
      }
      if ( (unsigned __int8)operator==(v141, v8) )
      {
        std::wstring::wstring(
          v127,
          L"Part has relationship content type, but its part Uri (%{PartUri}) is not a relationship Uri.");
        v58 = win_musl::Formatter::Formatter(v140, v127);
        v59 = win_dox::Uri::GetAbsoluteUri(&v108, v139);
        std::wstring::wstring(v132, L"PartUri");
        v60 = (win_musl::Formatter *)win_musl::Formatter::insert<std::wstring>(v58, v132, v59);
        v61 = win_musl::Formatter::c_str(v60);
        win_musl::DebugLogHelper("(no filename)", &word_18013A0B6, 352, 1024, -2142175227, v61);
        v107 = "Unexpected HRESULT returned by API";
        exception::exception((exception *)pExceptionObject, &v107);
        memset_0(v136, 0, 0x68u);
        v135 = "(no filename)";
        v134[1] = 352;
        v138 = -1;
        pExceptionObject[0] = &SplException::THResultException::`vftable';
        v134[0] = -2142175227;
        v137 = GUID_NULL;
        if ( SplException::Functions )
          v138 = SplException::Functions(v134);
        throw (SplException::THResultException *)pExceptionObject;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
      {
        v99 = std::wstring::_Myptr(a2[1], v26, v27, v28);
        v102 = std::wstring::_Myptr(v128, v100, v101, v99);
        WPP_SF_SS(*(_QWORD *)(v103 + 56), 13, (unsigned int)WPP_26ae4a55cde332a86a17bdc34ef7b6d8_Traceguids, v104, v102);
      }
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert(
        a1 + 152,
        v132,
        v120);
      v111 = v132;
      ByteCollection = win_musl::consumption::MetroConsumptionState::ByteCollectionHolder::GetByteCollection(
                         a2[1],
                         v132);
      v31 = a2[1];
      v32 = *(_DWORD *)(v31 + 80);
      v107 = v113;
      v33 = 7;
      v116 = 7;
      v115 = 0;
      LOWORD(v114[0]) = 0;
      v34 = *(_QWORD *)(v31 + 24);
      if ( v113 == (char *)v31 )
      {
        std::wstring::erase(v113, *(_QWORD *)(v31 + 24), -1);
        std::wstring::erase(v113, 0, 0);
      }
      else
      {
        if ( v34 > 0x7FFFFFFFFFFFFFFELL )
          std::_String_base::_Xlen();
        if ( v34 > 7 )
        {
          std::wstring::_Copy(v113, *(_QWORD *)(v31 + 24), 0);
          v33 = v116;
          goto LABEL_44;
        }
        if ( v34 )
        {
LABEL_44:
          v35 = (_QWORD *)(v31 + 8);
          if ( *(_QWORD *)(v31 + 32) >= 8u )
            v35 = (_QWORD *)*v35;
          v36 = v114;
          if ( v33 >= 8 )
            v36 = (void **)v114[0];
          memcpy_s(v36, 2 * v33, v35, 2 * v34);
          v37 = v114;
          if ( v116 >= 8 )
            v37 = (void **)v114[0];
          v115 = v34;
          *((_WORD *)v37 + v34) = 0;
          goto LABEL_66;
        }
        v66 = (_WORD *)std::wstring::_Myptr(v113, 7, 0, v29);
        v115 = 0;
        *v66 = 0;
      }
LABEL_66:
      v124 = 0;
      v42 = *(_QWORD *)(a1 + 56);
      if ( v42 )
      {
        v43 = *(_QWORD *)(a1 + 64);
        if ( _InterlockedIncrement((volatile signed __int32 *)(v42 + 8)) == 1 )
          _InterlockedIncrement((volatile signed __int32 *)(v42 + 12));
        *(_QWORD *)&v124 = v42;
        *((_QWORD *)&v124 + 1) = v43;
      }
      v44 = (_QWORD *)win_musl::UnknownOnly<win_musl::consumption::ContainerPartSender,win_mp_lib::null_type,win_mp_lib::null_type>::CreateInstance<win_scope::scope<win_musl::consumption::MetroConsumptionState *,win_scope::const_policies<win_scope::shared_policies>>,std::wstring,enum __MIDL___MIDL_itf_opc2Eio_0000_0000_0002,win_dox::ByteCollection>(
                        (unsigned int)&v106,
                        (unsigned int)&v124,
                        (unsigned int)v113,
                        v32,
                        ByteCollection);
      v45 = (_BYTE *)*v44;
      if ( *v44 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v45 + 8LL))(*v44);
      v111 = v45;
      if ( v106 )
      {
        (*(void (__fastcall **)(_QWORD *))(*v106 + 16LL))(v106);
        v106 = 0;
      }
      v46 = *(_QWORD *)(win_musl::consumption::MetroConsumptionState::GetContainerPartReceiver(*(_QWORD *)(a1 + 64)) + 8);
      v47 = *(void (__fastcall **)(__int64, __int64 *, char *, _QWORD, __int64 *, __int64))(*(_QWORD *)v46 + 8LL);
      v48 = a2[1] + 104LL;
      v105 = 0;
      win_scope::detail::scope_helper<win_musl::ByteReceiverUnique<win_musl::consumption::ZipLocalConsumer,1,IUnknown> *,win_scope::const_policies<win_scope::types_6<win_scope::close_com,win_scope::convert_normal,win_scope::acquire_com,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_com>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::reset(
        &v105,
        v45);
      v47(v46, &v108, v128, *(unsigned int *)(a2[1] + 80LL), &v105, v48);
      if ( v45 )
        (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v45 + 16LL))(v45);
LABEL_76:
      if ( v123 >= 8 )
        operator delete(Destination[0]);
      v123 = 7;
      v122 = 0;
      LOWORD(Destination[0]) = 0;
      win_musl::ContentType::~ContentType((win_musl::ContentType *)v141);
      if ( v131 >= 8 )
        operator delete(Block);
      v131 = 7;
      v130 = 0;
      LOWORD(Block) = 0;
      if ( v110 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 16LL))(v110);
        v110 = 0;
      }
      if ( v109 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v109 + 16LL))(v109);
        v109 = 0;
      }
      if ( v108 )
      {
        win_scope::close_com::close<win_musl::consumption::ContainerSender * *>(&v108, v49, v50);
        v108 = 0;
      }
      if ( (*(_DWORD *)(v5 + 44))-- == 1 )
        *(_DWORD *)(v5 + 40) = 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)v5);
      if ( *a2 )
      {
        if ( a2[1] )
        {
          win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(a2);
          *a2 = 0;
          a2[1] = 0;
        }
      }
      return;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
    {
      v79 = win_dox::Uri::GetAbsoluteUri(&v108, v127);
      v4 = 1;
      v83 = std::wstring::_Myptr(v79, v80, v81, v82);
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, WPP_26ae4a55cde332a86a17bdc34ef7b6d8_Traceguids, v83);
    }
    if ( (v4 & 1) != 0 )
    {
      LOBYTE(v11) = 1;
      std::wstring::_Tidy(v127, v11, 0);
    }
    if ( v131 >= 8 )
      operator delete(Block);
    v131 = 7;
    v130 = 0;
    LOWORD(Block) = 0;
    win_dox::OpcPartUri::~OpcPartUri((win_dox::OpcPartUri *)&v108);
    win_musl::CriticalSection::Leave((win_musl::CriticalSection *)v5);
  }
  else
  {
    win_musl::consumption::MetroConsumptionState::TestClose(*(win_musl::consumption::MetroConsumptionState **)(a1 + 64));
    win_musl::CriticalSection::Leave((win_musl::CriticalSection *)v5);
  }
  if ( *a2 && a2[1] )
  {
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(a2);
    *a2 = 0;
    a2[1] = 0;
  }
}

```

## disassembly

```asm
0x180015dc0  mov     rax, rsp
0x180015dc3  push    rbp
0x180015dc4  push    rsi
0x180015dc5  push    rdi
0x180015dc6  push    r12
0x180015dc8  push    r13
0x180015dca  push    r14
0x180015dcc  push    r15
0x180015dce  lea     rbp, [rax-2A8h]
0x180015dd5  sub     rsp, 370h
0x180015ddc  mov     [rbp+2A0h+var_2F8], 0FFFFFFFFFFFFFFFEh
0x180015de4  mov     [rax+18h], rbx
0x180015de8  mov     rax, cs:__security_cookie
0x180015def  xor     rax, rsp
0x180015df2  mov     [rbp+2A0h+var_40], rax
0x180015df9  mov     r15, rdx
0x180015dfc  mov     r14, rcx
0x180015dff  mov     [rbp+2A0h+var_2F0], rdx
0x180015e03  xor     r13d, r13d
0x180015e06  mov     edi, r13d
0x180015e09  mov     dword ptr [rsp+3A0h+var_360], r13d
0x180015e0e  lea     rbx, [rcx+0C8h]
0x180015e15  mov     [rbp+2A0h+var_2E8], rbx
0x180015e19  mov     rcx, rbx; lpCriticalSection
0x180015e1c  call    cs:__imp_EnterCriticalSection
0x180015e22  mov     ecx, [rbx+2Ch]
0x180015e25  lea     eax, [rcx+1]
0x180015e28  mov     [rbx+2Ch], eax
0x180015e2b  test    ecx, ecx
0x180015e2d  jnz     short loc_180015E38
0x180015e2f  call    cs:__imp_GetCurrentThreadId
0x180015e35  mov     [rbx+28h], eax
0x180015e38  mov     cl, [r14+100h]; this
0x180015e3f  call    ?ThrowIfFailed@win_dox@@YAX_N@Z; win_dox::ThrowIfFailed(bool)
0x180015e44  call    ??$Get@VSingletonInitializer@ContainerSender@consumption@win_musl@@@?$InitOnceSingleton@UContentType@win_musl@@URelationshipsContentTypeSingleton_tag@ContainerSender@consumption@2@@win_musl@@SAPEAUContentType@1@VSingletonInitializer@ContainerSender@consumption@1@@Z; win_musl::InitOnceSingleton<win_musl::ContentType,win_musl::consumption::ContainerSender::RelationshipsContentTypeSingleton_tag>::Get<win_musl::consumption::ContainerSender::SingletonInitializer>(win_musl::consumption::ContainerSender::SingletonInitializer)
0x180015e49  mov     r12, rax
0x180015e4c  cmp     [r15], r13
0x180015e4f  jz      loc_180016105
0x180015e55  mov     rax, [r15+8]
0x180015e59  test    rax, rax
0x180015e5c  jz      loc_180016105
0x180015e62  lea     rdx, [rax+8]
0x180015e66  cmp     qword ptr [rax+20h], 8
0x180015e6b  jb      short loc_180015E70
0x180015e6d  mov     rdx, [rdx]
0x180015e70  lea     rcx, [rsp+3A0h+var_348]
0x180015e75  call    ?CreatePartUriInternal@win_dox@@YA?AVOpcPartUri@1@PEB_W@Z; win_dox::CreatePartUriInternal(wchar_t const *)
0x180015e7a  nop
0x180015e7b  lea     rcx, [r14+48h]
0x180015e7f  lea     r8, [rsp+3A0h+var_348]
0x180015e84  lea     rdx, [rbp+2A0h+var_268]
0x180015e88  call    ?FindContentType@MimeTable@win_musl@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBVOpcPartUri@win_dox@@@Z; win_musl::MimeTable::FindContentType(win_dox::OpcPartUri const &)
0x180015e8d  nop
0x180015e8e  cmp     [rbp+2A0h+var_250], r13
0x180015e92  jz      loc_180016563
0x180015e98  lea     rdx, [rbp+2A0h+var_268]
0x180015e9c  lea     rcx, [rbp+2A0h+var_E0]
0x180015ea3  call    ?ContentTypeFromStdString@win_musl@@YA?AUContentType@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@J@Z; win_musl::ContentTypeFromStdString(std::wstring const &,long)
0x180015ea8  nop
0x180015ea9  mov     rdi, [r15+8]
0x180015ead  add     rdi, 28h ; '('
0x180015eb1  mov     [rbp+2A0h+var_2C0], 7
0x180015eb9  mov     [rbp+2A0h+var_2C8], r13
0x180015ebd  mov     word ptr [rbp+2A0h+Destination], r13w
0x180015ec2  mov     rsi, [rdi+18h]
0x180015ec6  lea     rax, [rbp+2A0h+var_2E0]
0x180015eca  mov     rcx, 7FFFFFFFFFFFFFFEh
0x180015ed4  cmp     rax, rdi
0x180015ed7  jz      loc_1800168F5
0x180015edd  cmp     rsi, rcx
0x180015ee0  ja      loc_180016918
0x180015ee6  cmp     [rbp+2A0h+var_2C0], rsi
0x180015eea  jb      short loc_180015F3E
0x180015eec  test    rsi, rsi
0x180015eef  jz      loc_180016631
0x180015ef5  lea     r8, [rdi+8]
0x180015ef9  cmp     qword ptr [rdi+20h], 8
0x180015efe  jb      short loc_180015F03
0x180015f00  mov     r8, [r8]; Source
0x180015f03  mov     rdx, [rbp+2A0h+var_2C0]
0x180015f07  lea     rcx, [rbp+2A0h+Destination]
0x180015f0b  cmp     rdx, 8
0x180015f0f  cmovnb  rcx, [rbp+2A0h+Destination]; Destination
0x180015f14  lea     rdi, [rsi+rsi]
0x180015f18  add     rdx, rdx; DestinationSize
0x180015f1b  mov     r9, rdi; SourceSize
0x180015f1e  call    cs:__imp_memcpy_s
0x180015f24  lea     rcx, [rbp+2A0h+Destination]
0x180015f28  cmp     [rbp+2A0h+var_2C0], 8
0x180015f2d  cmovnb  rcx, [rbp+2A0h+Destination]
0x180015f32  mov     [rbp+2A0h+var_2C8], rsi
0x180015f36  xor     esi, esi
0x180015f38  mov     [rdi+rcx], si
0x180015f3c  jmp     short loc_180015F55
0x180015f3e  mov     r8, [rbp+2A0h+var_2C8]
0x180015f42  mov     rdx, rsi
0x180015f45  lea     rcx, [rbp+2A0h+var_2E0]
0x180015f49  call    ?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x180015f4e  test    rsi, rsi
0x180015f51  jnz     short loc_180015EF5
0x180015f53  xor     esi, esi
0x180015f55  lea     r13, [r14+98h]
0x180015f5c  mov     r9, [r13+8]
0x180015f60  mov     rax, [r9+8]
0x180015f64  cmp     [rax+41h], sil
0x180015f68  jnz     short loc_180015FC8
0x180015f6a  mov     rdi, [rbp+2A0h+var_2C8]
0x180015f6e  lea     r8, [rbp+2A0h+Destination]
0x180015f72  cmp     [rbp+2A0h+var_2C0], 8
0x180015f77  cmovnb  r8, [rbp+2A0h+Destination]
0x180015f7c  mov     rdx, rdi
0x180015f7f  cmp     [rax+30h], rdi
0x180015f83  cmovb   rdx, [rax+30h]
0x180015f88  lea     rcx, [rax+20h]
0x180015f8c  cmp     qword ptr [rax+38h], 8
0x180015f91  jb      short loc_180015F96
0x180015f93  mov     rcx, [rcx]
0x180015f96  test    rdx, rdx
0x180015f99  jz      loc_180016922
0x180015f9f  movzx   r10d, word ptr [rcx]
0x180015fa3  cmp     r10w, [r8]
0x180015fa7  jnz     short loc_180015FB6
0x180015fa9  add     rcx, 2
0x180015fad  add     r8, 2
0x180015fb1  dec     rdx
0x180015fb4  jmp     short loc_180015F96
0x180015fb6  jb      loc_1800160FC
0x180015fbc  mov     r9, rax
0x180015fbf  mov     rax, [rax]
0x180015fc2  cmp     [rax+41h], sil
0x180015fc6  jz      short loc_180015F6E
0x180015fc8  cmp     r9, [r14+0A0h]
0x180015fcf  jnz     loc_18001613F
0x180015fd5  mov     rdx, r13
0x180015fd8  lea     rcx, [rbp+2A0h+var_2E0]
0x180015fdc  call    ?DetectPrefixCollision@win_musl@@YA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEAV?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@@3@@Z; win_musl::DetectPrefixCollision(std::wstring &,std::set<std::wstring> &)
0x180015fe1  test    al, al
0x180015fe3  jnz     loc_18001692B
0x180015fe9  lea     rcx, [rsp+3A0h+var_348]; this
0x180015fee  call    ?IsRelationshipsPartUri@OpcPartUri@win_dox@@QEBA_NXZ; win_dox::OpcPartUri::IsRelationshipsPartUri(void)
0x180015ff3  mov     rdx, r12
0x180015ff6  lea     rcx, [rbp+2A0h+var_E0]
0x180015ffd  test    al, al
0x180015fff  jnz     loc_1800165B9
0x180016005  call    ??8@YA_NAEBUContentType@win_musl@@0@Z; operator==(win_musl::ContentType const &,win_musl::ContentType const &)
0x18001600a  test    al, al
0x18001600c  jnz     loc_180016432
0x180016012  lea     rax, WPP_GLOBAL_Control
0x180016019  mov     r10, cs:WPP_GLOBAL_Control
0x180016020  cmp     r10, rax
0x180016023  jz      short loc_180016030
0x180016025  test    byte ptr [r10+44h], 4
0x18001602a  jnz     loc_180016AD7
0x180016030  lea     r8, [rbp+2A0h+var_2E0]
0x180016034  lea     rdx, [rbp+2A0h+var_240]
0x180016038  mov     rcx, r13
0x18001603b  call    ?insert@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@Viterator@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@$0A@@std@@@std@@_N@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@2@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert(std::wstring const &)
0x180016040  lea     rax, [rbp+2A0h+var_240]
0x180016044  mov     [rsp+3A0h+var_330], rax
0x180016049  lea     rdx, [rbp+2A0h+var_240]
0x18001604d  mov     rcx, [r15+8]
0x180016051  call    ?GetByteCollection@ByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@QEBA?AVByteCollection@win_dox@@XZ; win_musl::consumption::MetroConsumptionState::ByteCollectionHolder::GetByteCollection(void)
0x180016056  mov     r12, rax
0x180016059  mov     rdi, [r15+8]
0x18001605d  mov     r13d, [rdi+50h]
0x180016061  lea     rax, [rbp+2A0h+var_320]
0x180016065  mov     [rsp+3A0h+var_350], rax
0x18001606a  mov     edx, 7
0x18001606f  mov     [rbp+2A0h+var_300], rdx
0x180016073  mov     r8, rsi
0x180016076  mov     [rbp+2A0h+var_308], rsi
0x18001607a  mov     word ptr [rbp+2A0h+var_318], si
0x18001607e  mov     rsi, [rdi+18h]
0x180016082  lea     rax, [rbp+2A0h+var_320]
0x180016086  cmp     rax, rdi
0x180016089  jz      loc_180016B0B
0x18001608f  mov     rax, 7FFFFFFFFFFFFFFEh
0x180016099  cmp     rsi, rax
0x18001609c  ja      loc_180016B2E
0x1800160a2  cmp     rdx, rsi
0x1800160a5  jb      loc_180016193
0x1800160ab  test    rsi, rsi
0x1800160ae  jz      loc_180016656
0x1800160b4  lea     r8, [rdi+8]
0x1800160b8  cmp     qword ptr [rdi+20h], 8
0x1800160bd  jb      short loc_1800160C2
0x1800160bf  mov     r8, [r8]; Source
0x1800160c2  lea     rcx, [rbp+2A0h+var_318]
0x1800160c6  cmp     rdx, 8
0x1800160ca  cmovnb  rcx, [rbp+2A0h+var_318]; Destination
0x1800160cf  lea     rdi, [rsi+rsi]
0x1800160d3  add     rdx, rdx; DestinationSize
0x1800160d6  mov     r9, rdi; SourceSize
0x1800160d9  call    cs:__imp_memcpy_s
0x1800160df  lea     rcx, [rbp+2A0h+var_318]
0x1800160e3  cmp     [rbp+2A0h+var_300], 8
0x1800160e8  cmovnb  rcx, [rbp+2A0h+var_318]
0x1800160ed  mov     [rbp+2A0h+var_308], rsi
0x1800160f1  xor     eax, eax
0x1800160f3  mov     [rdi+rcx], ax
0x1800160f7  jmp     loc_1800161AC
0x1800160fc  mov     rax, [rax+10h]
0x180016100  jmp     loc_180015FC2
0x180016105  mov     rcx, [r14+40h]; this
0x180016109  call    ?TestClose@MetroConsumptionState@consumption@win_musl@@QEAAXXZ; win_musl::consumption::MetroConsumptionState::TestClose(void)
0x18001610e  nop
0x18001610f  mov     rcx, rbx; this
0x180016112  call    ?Leave@CriticalSection@win_musl@@QEAAXXZ; win_musl::CriticalSection::Leave(void)
0x180016117  nop
0x180016118  cmp     [r15], r13
0x18001611b  jz      loc_18001634B
0x180016121  cmp     [r15+8], r13
0x180016125  jz      loc_18001634B
0x18001612b  mov     rcx, r15
0x18001612e  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x180016133  mov     [r15], r13
0x180016136  mov     [r15+8], r13
0x18001613a  jmp     loc_18001634B
0x18001613f  lea     rcx, [r9+18h]
0x180016143  mov     r10, [rcx+18h]
0x180016147  call    ?_Myptr@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEBAPEB_WXZ; std::wstring::_Myptr(void)
0x18001614c  mov     r11, [rbp+2A0h+var_2C8]
0x180016150  mov     rcx, r10
0x180016153  cmp     r11, r10
0x180016156  cmovb   rcx, r11
0x18001615a  lea     rdx, [rbp+2A0h+Destination]
0x18001615e  cmp     [rbp+2A0h+var_2C0], 8
0x180016163  cmovnb  rdx, [rbp+2A0h+Destination]
0x180016168  test    rcx, rcx
0x18001616b  jz      loc_1800163C0
0x180016171  movzx   r8d, word ptr [rdx]
0x180016175  cmp     r8w, [rax]
0x180016179  jnz     short loc_180016188
0x18001617b  add     rdx, 2
0x18001617f  add     rax, 2
0x180016183  dec     rcx
0x180016186  jmp     short loc_180016168
0x180016188  jb      loc_180015FD5
0x18001618e  jmp     loc_1800163C9
0x180016193  mov     rdx, rsi
0x180016196  lea     rcx, [rbp+2A0h+var_320]
0x18001619a  call    ?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18001619f  mov     rdx, [rbp+2A0h+var_300]
0x1800161a3  test    rsi, rsi
0x1800161a6  jnz     loc_1800160B4
0x1800161ac  xorps   xmm0, xmm0
0x1800161af  movdqu  [rbp+2A0h+var_2B8], xmm0
0x1800161b4  mov     rcx, [r14+38h]
0x1800161b8  test    rcx, rcx
0x1800161bb  jz      short loc_1800161DE
0x1800161bd  mov     rdx, [r14+40h]
0x1800161c1  mov     eax, 1
0x1800161c6  lock xadd [rcx+8], eax
0x1800161cb  inc     eax
0x1800161cd  cmp     eax, 1
0x1800161d0  jz      loc_1800163B7
0x1800161d6  mov     qword ptr [rbp+2A0h+var_2B8], rcx
0x1800161da  mov     qword ptr [rbp+2A0h+var_2B8+8], rdx
0x1800161de  mov     qword ptr [rsp+3A0h+var_380], r12
0x1800161e3  mov     r9d, r13d
0x1800161e6  lea     r8, [rbp+2A0h+var_320]
0x1800161ea  lea     rdx, [rbp+2A0h+var_2B8]
0x1800161ee  lea     rcx, [rsp+3A0h+var_358]
0x1800161f3  call    ??$CreateInstance@V?$scope@PEAVMetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@W4__MIDL___MIDL_itf_opc2Eio_0000_0000_0002@@VByteCollection@win_dox@@@?$UnknownOnly@VContainerPartSender@consumption@win_musl@@Vnull_type@win_mp_lib@@V45@@win_musl@@SA?AV?$scope@PEAV?$UnknownOnly@VContainerPartSender@consumption@win_musl@@Vnull_type@win_mp_lib@@V45@@win_musl@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVMetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@3@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@W4__MIDL___MIDL_itf_opc2Eio_0000_0000_0002@@VByteCollection@win_dox@@@Z; win_musl::UnknownOnly<win_musl::consumption::ContainerPartSender,win_mp_lib::null_type,win_mp_lib::null_type>::CreateInstance<win_scope::scope<win_musl::consumption::MetroConsumptionState *,win_scope::const_policies<win_scope::shared_policies>>,std::wstring,__MIDL___MIDL_itf_opc2Eio_0000_0000_0002,win_dox::ByteCollection>(win_scope::scope<win_musl::consumption::MetroConsumptionState *,win_scope::const_policies<win_scope::shared_policies>>,std::wstring,__MIDL___MIDL_itf_opc2Eio_0000_0000_0002,win_dox::ByteCollection)
0x1800161f8  nop
0x1800161f9  mov     r12, [rax]
0x1800161fc  test    r12, r12
0x1800161ff  jz      short loc_180016211
0x180016201  mov     rax, [r12]
0x180016205  mov     rcx, r12
0x180016208  mov     rax, [rax+8]
0x18001620c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016211  mov     [rsp+3A0h+var_330], r12
0x180016216  mov     rcx, [rsp+3A0h+var_358]
0x18001621b  test    rcx, rcx
0x18001621e  jz      short loc_180016235
0x180016220  mov     rax, [rcx]
0x180016223  mov     rax, [rax+10h]
0x180016227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001622c  mov     [rsp+3A0h+var_358], 0
0x180016235  mov     rcx, [r14+40h]
0x180016239  call    ?GetContainerPartReceiver@MetroConsumptionState@consumption@win_musl@@QEAAAEAV?$scope@PEAVOpcPackageReceiver@win_dox@@U?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@XZ; win_musl::consumption::MetroConsumptionState::GetContainerPartReceiver(void)
0x18001623e  mov     r14, [rax+8]
0x180016242  mov     rax, [r14]
0x180016245  mov     rsi, [rax+8]
0x180016249  mov     rdi, [r15+8]
0x18001624d  add     rdi, 68h ; 'h'
0x180016251  mov     [rsp+3A0h+var_360], 0
0x18001625a  mov     rdx, r12
0x18001625d  lea     rcx, [rsp+3A0h+var_360]
0x180016262  call    ?reset@?$scope_helper@PEAV?$ByteReceiverUnique@VZipLocalConsumer@consumption@win_musl@@$00UIUnknown@@@win_musl@@U?$const_policies@U?$types_6@Uclose_com@win_scope@@Uconvert_normal@2@Uacquire_com@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Usafe_types_com@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAV?$ByteReceiverUnique@VZipLocalConsumer@consumption@win_musl@@$00UIUnknown@@@win_musl@@U?$const_policies@U?$types_6@Uclose_com@win_scope@@Uconvert_normal@2@Uacquire_com@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Usafe_types_com@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@3@PEAV?$ByteReceiverUnique@VZipLocalConsumer@consumption@win_musl@@$00UIUnknown@@@win_musl@@@Z; win_scope::detail::scope_helper<win_musl::ByteReceiverUnique<win_musl::consumption::ZipLocalConsumer,1,IUnknown> *,win_scope::const_policies<win_scope::types_6<win_scope::close_com,win_scope::convert_normal,win_scope::acquire_com,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_com>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::reset(win_scope::scope<win_musl::ByteReceiverUnique<win_musl::consumption::ZipLocalConsumer,1,IUnknown> *,win_scope::const_policies<win_scope::types_6<win_scope::close_com,win_scope::convert_normal,win_scope::acquire_com,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_com>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> &,win_musl::ByteReceiverUnique<win_musl::consumption::ZipLocalConsumer,1,IUnknown> *)
0x180016267  mov     r9, [r15+8]
0x18001626b  mov     qword ptr [rsp+3A0h+var_378], rdi
0x180016270  lea     rax, [rsp+3A0h+var_360]
0x180016275  mov     qword ptr [rsp+3A0h+var_380], rax
0x18001627a  mov     r9d, [r9+50h]
0x18001627e  lea     r8, [rbp+2A0h+var_268]
0x180016282  lea     rdx, [rsp+3A0h+var_348]
0x180016287  mov     rcx, r14
0x18001628a  mov     rax, rsi
  ... truncated ...
```
