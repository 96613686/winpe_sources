# WinREAgent::Executor::InternalLoad(PushButtonReset::SerializeNode *)

- ea: `0x18000a26c`
- end: `0x18000ace3`
- name: `?InternalLoad@Executor@WinREAgent@@AEAAJPEAVSerializeNode@PushButtonReset@@@Z`
- size: `2679`
- prototype: `int(WinREAgent::Executor *__hidden this, struct PushButtonReset::SerializeNode *)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000b75c`

## callees

- `0x180003c94`
- `0x1800049a4`
- `0x180004af8`
- `0x180005c00`
- `0x180005cc0`
- `0x1800064a0`
- `0x1800074b8`
- `0x18000a26c`
- `0x18000d5a0`
- `0x18000d620`
- `0x18000d800`
- `0x18000d860`
- `0x18000d92c`
- `0x180011ef4`
- `0x18001eb5c`
- `0x18001f228`
- `0x180029320`
- `0x1800314cc`
- `0x180037344`
- `0x1800517d8`
- `0x1800520a4`
- `0x180052194`
- `0x1800521f8`
- `0x1800528fc`
- `0x180052a7c`
- `0x18006f010`

## string_xrefs

- `0x18000a2d5`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000a579`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000a5c3`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000a61d`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000a696`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000a6f9`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000a818`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000a872`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000a8cb`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000a9e6`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000aa3b`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000aa94`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000aaf5`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000ab48`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000aba3`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000ab34`: `Failed to get WinREAgent root directory`
- `0x18000a2dc`: `WinREAgent::Executor::InternalLoad`
- `0x18000a580`: `WinREAgent::Executor::InternalLoad`
- `0x18000a5ca`: `WinREAgent::Executor::InternalLoad`
- `0x18000a624`: `WinREAgent::Executor::InternalLoad`
- `0x18000a69d`: `WinREAgent::Executor::InternalLoad`
- `0x18000a700`: `WinREAgent::Executor::InternalLoad`
- `0x18000a81f`: `WinREAgent::Executor::InternalLoad`
- `0x18000a879`: `WinREAgent::Executor::InternalLoad`
- `0x18000a8d2`: `WinREAgent::Executor::InternalLoad`
- `0x18000a9ed`: `WinREAgent::Executor::InternalLoad`
- `0x18000aa42`: `WinREAgent::Executor::InternalLoad`
- `0x18000aa9b`: `WinREAgent::Executor::InternalLoad`
- `0x18000aafc`: `WinREAgent::Executor::InternalLoad`
- `0x18000ab4f`: `WinREAgent::Executor::InternalLoad`
- `0x18000abaa`: `WinREAgent::Executor::InternalLoad`
- `0x18000a38b`: `PackagePath`
- `0x18000a668`: `Failed to load PackagePath of entry node [%u]`
- `0x18000a423`: `InstallSize`
- `0x18000a5af`: `Failed to load InstallSize of entry node [%u]`
- `0x18000a8a2`: `CommitOperation`
- `0x18000a9d2`: `Failed to load commit operation from operation node [%u]`
- `0x18000ab8f`: `Failed to load Rollback Helper`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall WinREAgent::Executor::InternalLoad(
        WinREAgent::Executor *this,
        struct PushButtonReset::SerializeNode *a2)
{
  struct PushButtonReset::SerializeNodeList **v4; // rax
  int Node; // ebx
  unsigned int i; // edi
  PushButtonReset::SerializeNodeList *v7; // rbx
  struct PushButtonReset::SerializeNode **v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rbx
  __int64 v11; // rbx
  _QWORD *v12; // rax
  _QWORD *v13; // r12
  ATL::CStringData *v14; // r15
  int *v15; // r14
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rax
  _QWORD *v19; // rax
  struct PushButtonReset::SerializeNodeList **v20; // rax
  unsigned int j; // edi
  PushButtonReset::SerializeNodeList *v22; // rbx
  struct PushButtonReset::SerializeNode **v23; // rax
  struct WinREAgent::Operation **v24; // rbx
  struct PushButtonReset::SerializeNode *v25; // rax
  __int64 v26; // rax
  struct PushButtonReset::SerializeNodeList **v27; // rax
  unsigned int k; // edi
  PushButtonReset::SerializeNodeList *v29; // rbx
  struct PushButtonReset::SerializeNode **v30; // rax
  struct WinREAgent::Operation **v31; // rbx
  struct PushButtonReset::SerializeNode *v32; // rax
  __int64 v33; // rax
  _QWORD *v34; // rcx
  struct PushButtonReset::SerializeNode **v35; // rax
  struct PushButtonReset::SerializeNode *v36; // rax
  __int64 v37; // rax
  int v38; // edi
  unsigned int v40; // [rsp+30h] [rbp-99h]
  unsigned int v41; // [rsp+30h] [rbp-99h]
  unsigned int v42; // [rsp+30h] [rbp-99h]
  unsigned int v43; // [rsp+30h] [rbp-99h]
  unsigned int v44; // [rsp+30h] [rbp-99h]
  unsigned int v45; // [rsp+30h] [rbp-99h]
  unsigned int v46; // [rsp+30h] [rbp-99h]
  unsigned int v47; // [rsp+30h] [rbp-99h]
  _QWORD v48[2]; // [rsp+40h] [rbp-89h] BYREF
  _QWORD v49[2]; // [rsp+50h] [rbp-79h] BYREF
  _QWORD v50[2]; // [rsp+60h] [rbp-69h] BYREF
  _QWORD v51[2]; // [rsp+70h] [rbp-59h] BYREF
  _QWORD v52[2]; // [rsp+80h] [rbp-49h] BYREF
  _QWORD *v53; // [rsp+90h] [rbp-39h] BYREF
  _QWORD v54[2]; // [rsp+98h] [rbp-31h] BYREF
  _QWORD v55[2]; // [rsp+A8h] [rbp-21h] BYREF
  void **v56; // [rsp+B8h] [rbp-11h] BYREF
  _QWORD *v57; // [rsp+C0h] [rbp-9h]
  void **v58; // [rsp+C8h] [rbp-1h] BYREF
  __int64 v59; // [rsp+D0h] [rbp+7h]
  void **v60; // [rsp+D8h] [rbp+Fh] BYREF
  __int64 v61; // [rsp+E0h] [rbp+17h]
  __int64 v62; // [rsp+140h] [rbp+77h] BYREF
  __int64 v63; // [rsp+148h] [rbp+7Fh] BYREF

  v52[1] = 0;
  v52[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::`vftable';
  v4 = (struct PushButtonReset::SerializeNodeList **)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v52);
  Node = PushButtonReset::SerializeNode::SelectChildren(a2, v4, L"Package/Entry");
  if ( Node >= 0 )
  {
    for ( i = 0; i < *(_DWORD *)(*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD *))(v52[0] + 24LL))(v52) + 8LL); ++i )
    {
      v50[1] = 0;
      v50[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
      v7 = (PushButtonReset::SerializeNodeList *)(*(__int64 (__fastcall **)(_QWORD *))(v52[0] + 24LL))(v52);
      v8 = (struct PushButtonReset::SerializeNode **)(*(__int64 (__fastcall **)(_QWORD *))(v50[0] + 8LL))(v50);
      Node = PushButtonReset::SerializeNodeList::GetNode(v7, i, v8);
      if ( Node < 0 )
      {
        v43 = i;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Node,
          "WinREAgent::Executor::InternalLoad",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          2252,
          L"Failed to retrieve Packages entry node [%u]",
          v43);
        goto LABEL_21;
      }
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v62);
      v55[0] = 0;
      v53 = 0;
      v9 = (*(__int64 (__fastcall **)(_QWORD *))(v50[0] + 24LL))(v50);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v63,
        (__int64)L"PackagePath");
      Node = PushButtonReset::SerializeNode::GetProperty(v9, &v63, &v62);
      ATL::CStringData::Release((ATL::CStringData *)(v63 - 24));
      if ( Node < 0 )
      {
        v42 = i;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Node,
          "WinREAgent::Executor::InternalLoad",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          2259,
          L"Failed to load PackagePath of entry node [%u]",
          v42);
LABEL_20:
        ATL::CStringData::Release((ATL::CStringData *)(v62 - 24));
LABEL_21:
        v50[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
        RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v50);
        v52[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::`vftable';
        goto LABEL_63;
      }
      v10 = (*(__int64 (__fastcall **)(_QWORD *))(v50[0] + 24LL))(v50);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v58,
        (__int64)L"PackageSize");
      Node = PushButtonReset::SerializeNode::GetProperty(v10, &v58, v55);
      ATL::CStringData::Release((ATL::CStringData *)(v58 - 3));
      if ( Node < 0 )
      {
        v41 = i;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Node,
          "WinREAgent::Executor::InternalLoad",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          2262,
          L"Failed to load PackageSize of entry node [%u]",
          v41);
        goto LABEL_20;
      }
      v11 = (*(__int64 (__fastcall **)(_QWORD *))(v50[0] + 24LL))(v50);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)v54,
        (__int64)L"InstallSize");
      Node = PushButtonReset::SerializeNode::GetProperty(v11, v54, &v53);
      ATL::CStringData::Release((ATL::CStringData *)(v54[0] - 24LL));
      if ( Node < 0 )
      {
        v40 = i;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Node,
          "WinREAgent::Executor::InternalLoad",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          2265,
          L"Failed to load InstallSize of entry node [%u]",
          v40);
        goto LABEL_18;
      }
      v57 = PbrNew<WinREAgent::PACKAGE_INFO,>();
      v56 = &RAII::CAutoPbrDelete<WinREAgent::PACKAGE_INFO *>::`vftable';
      if ( (unsigned __int8)RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!((__int64 *)&v56) )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          2147942414LL,
          "WinREAgent::Executor::InternalLoad",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          2268,
          L"Failed to allocate package");
        v56 = &RAII::CAutoPbrDelete<WinREAgent::PACKAGE_INFO *>::`vftable';
        RAII::CAutoPbrDelete<WinREAgent::PACKAGE_INFO *>::Release(&v56);
        Node = -2147024882;
LABEL_18:
        ATL::CStringData::Release((ATL::CStringData *)(v62 - 24));
        v50[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
        RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v50);
        goto LABEL_62;
      }
      v12 = (_QWORD *)((__int64 (__fastcall *)(void ***))v56[3])(&v56);
      v13 = v12;
      v14 = (ATL::CStringData *)(v62 - 24);
      v15 = (int *)(*v12 - 24LL);
      if ( (int *)(v62 - 24) != v15 )
      {
        if ( v15[4] >= 0 && *(_QWORD *)v14 == *(_QWORD *)v15 )
        {
          v16 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v62 - 24);
          ATL::CStringData::Release((ATL::CStringData *)v15);
          *v13 = v16 + 24;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(v12, v62, *(unsigned int *)(v62 - 16));
        }
      }
      v17 = ((__int64 (__fastcall *)(void ***))v56[3])(&v56);
      *(_QWORD *)(v17 + 8) = v55[0];
      v18 = ((__int64 (__fastcall *)(void ***))v56[3])(&v56);
      *(_QWORD *)(v18 + 16) = v53;
      v19 = v57;
      v57 = 0;
      v53 = v19;
      ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(
        (_QWORD *)this + 12,
        &v53);
      v56 = &RAII::CAutoPbrDelete<WinREAgent::PACKAGE_INFO *>::`vftable';
      RAII::CAutoPbrDelete<WinREAgent::PACKAGE_INFO *>::Release(&v56);
      ATL::CStringData::Release(v14);
      v50[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
      RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v50);
    }
    v48[1] = 0;
    v48[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::`vftable';
    v20 = (struct PushButtonReset::SerializeNodeList **)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v48);
    Node = PushButtonReset::SerializeNode::SelectChildren(a2, v20, L"StageOperation");
    if ( Node >= 0 )
    {
      for ( j = 0; j < *(_DWORD *)(*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD *))(v48[0] + 24LL))(v48) + 8LL); ++j )
      {
        v55[1] = 0;
        v55[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
        v22 = (PushButtonReset::SerializeNodeList *)(*(__int64 (__fastcall **)(_QWORD *))(v48[0] + 24LL))(v48);
        v23 = (struct PushButtonReset::SerializeNode **)(*(__int64 (__fastcall **)(_QWORD *))(v55[0] + 8LL))(v55);
        Node = PushButtonReset::SerializeNodeList::GetNode(v22, j, v23);
        if ( Node < 0 )
        {
          v45 = j;
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)Node,
            "WinREAgent::Executor::InternalLoad",
            "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
            2286,
            L"Failed to retrieve operation node [%u]",
            v45);
          goto LABEL_32;
        }
        v59 = 0;
        v58 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
        v24 = (struct WinREAgent::Operation **)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v58);
        v25 = (struct PushButtonReset::SerializeNode *)(*(__int64 (__fastcall **)(_QWORD *))(v55[0] + 32LL))(v55);
        Node = WinREAgent::Operation::Load(v25, v24);
        if ( Node < 0 )
        {
          v44 = j;
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)Node,
            "WinREAgent::Executor::InternalLoad",
            "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
            2290,
            L"Failed to load stage operation from operation node [%u]",
            v44);
          v58 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
          RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(&v58);
LABEL_32:
          v55[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
          RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v55);
          goto LABEL_61;
        }
        v26 = v59;
        v59 = 0;
        v62 = v26;
        ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(
          (_QWORD *)this + 4,
          &v62);
        v58 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
        RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(&v58);
        v55[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
        RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v55);
      }
      v49[1] = 0;
      v49[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::`vftable';
      v27 = (struct PushButtonReset::SerializeNodeList **)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v49);
      Node = PushButtonReset::SerializeNode::SelectChildren(a2, v27, L"CommitOperation");
      if ( Node >= 0 )
      {
        for ( k = 0; k < *(_DWORD *)(*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD *))(v49[0] + 24LL))(v49) + 8LL); ++k )
        {
          v54[1] = 0;
          v54[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
          v29 = (PushButtonReset::SerializeNodeList *)(*(__int64 (__fastcall **)(_QWORD *))(v49[0] + 24LL))(v49);
          v30 = (struct PushButtonReset::SerializeNode **)(*(__int64 (__fastcall **)(_QWORD *))(v54[0] + 8LL))(v54);
          Node = PushButtonReset::SerializeNodeList::GetNode(v29, k, v30);
          if ( Node < 0 )
          {
            v47 = k;
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)Node,
              "WinREAgent::Executor::InternalLoad",
              "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
              2303,
              L"Failed to retrieve operation node [%u]",
              v47);
            goto LABEL_42;
          }
          v61 = 0;
          v60 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
          v31 = (struct WinREAgent::Operation **)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v60);
          v32 = (struct PushButtonReset::SerializeNode *)(*(__int64 (__fastcall **)(_QWORD *))(v54[0] + 32LL))(v54);
          Node = WinREAgent::Operation::Load(v32, v31);
          if ( Node < 0 )
          {
            v46 = k;
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)Node,
              "WinREAgent::Executor::InternalLoad",
              "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
              2307,
              L"Failed to load commit operation from operation node [%u]",
              v46);
            v60 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
            RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(&v60);
LABEL_42:
            v54[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
            v34 = v54;
            goto LABEL_59;
          }
          v33 = v61;
          v61 = 0;
          v62 = v33;
          ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(
            (_QWORD *)this + 8,
            &v62);
          v60 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
          RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(&v60);
          v54[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
          RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v54);
        }
        v51[1] = 0;
        v51[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
        v35 = (struct PushButtonReset::SerializeNode **)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v51);
        Node = PushButtonReset::SerializeNode::SelectChild(a2, v35, L"ExecutionContext");
        if ( Node >= 0 )
        {
          v36 = (struct PushButtonReset::SerializeNode *)(*(__int64 (__fastcall **)(_QWORD *))(v51[0] + 32LL))(v51);
          Node = WinREAgent::ExecutionContext::Load(v36, (struct WinREAgent::ExecutionContext **)this + 51);
          if ( Node >= 0 )
          {
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v63);
            Node = WinREAgent::WorkDir::GetRootDir((__int64)this + 368, (__int64)&v63);
            if ( Node >= 0 )
            {
              v37 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 52) + 8LL))((char *)this + 416);
              v38 = WinREAgent::RollbackHelper::LoadRollbackHelper(&v63, v37);
              if ( v38 < 0 )
              {
                PushButtonReset::Logging::TraceErr(
                  2,
                  (unsigned int)v38,
                  "WinREAgent::Executor::InternalLoad",
                  "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
                  2326,
                  L"Failed to load Rollback Helper");
                ATL::CStringData::Release((ATL::CStringData *)(v63 - 24));
                v51[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
                RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v51);
                v49[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::`vftable';
                RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::Release(v49);
                v48[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::`vftable';
                RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::Release(v48);
                Node = v38;
                goto LABEL_62;
              }
              *(_QWORD *)(*((_QWORD *)this + 51) + 448LL) = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 52)
                                                                                              + 32LL))((char *)this + 416);
              LODWORD(v62) = 0;
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                (__int64)&v53,
                (__int64)L"ScenarioType");
              Node = PushButtonReset::SerializeNode::GetProperty(a2, &v53, &v62);
              ATL::CStringData::Release((ATL::CStringData *)(v53 - 3));
              if ( Node >= 0 )
                *((_DWORD *)this + 108) = v62;
              else
                PushButtonReset::Logging::TraceErr(
                  2,
                  (unsigned int)Node,
                  "WinREAgent::Executor::InternalLoad",
                  "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
                  2333,
                  L"Failed to load ScenarioType");
            }
            else
            {
              PushButtonReset::Logging::TraceErr(
                2,
                (unsigned int)Node,
                "WinREAgent::Executor::InternalLoad",
                "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
                2323,
                L"Failed to get WinREAgent root directory");
            }
            ATL::CStringData::Release((ATL::CStringData *)(v63 - 24));
          }
          else
          {
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)Node,
              "WinREAgent::Executor::InternalLoad",
              "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
              2318,
              L"Failed to load ExecutionContext");
          }
          v51[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
        }
        else
        {
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)Node,
            "WinREAgent::Executor::InternalLoad",
            "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
            2315,
            L"Failed to select Execution context node");
          v51[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
        }
        v34 = v51;
LABEL_59:
        RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v34);
      }
      else
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Node,
          "WinREAgent::Executor::InternalLoad",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          2297,
          L"Failed to enumerate Operation subnodes");
      }
      v49[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::`vftable';
      RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::Release(v49);
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Node,
        "WinREAgent::Executor::InternalLoad",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        2280,
        L"Failed to enumerate Operation subnodes");
    }
LABEL_61:
    v48[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::`vftable';
    RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::Release(v48);
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Node,
      "WinREAgent::Executor::InternalLoad",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      2246,
      L"Failed to look up Packages entries");
  }
LABEL_62:
  v52[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::`vftable';
LABEL_63:
  RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::Release(v52);
  return (unsigned int)Node;
}

```

## disassembly

```asm
0x18000a26c  mov     [rsp-8+arg_0], rbx
0x18000a271  push    rbp
0x18000a272  push    rsi
0x18000a273  push    rdi
0x18000a274  push    r12
0x18000a276  push    r13
0x18000a278  push    r14
0x18000a27a  push    r15
0x18000a27c  lea     rbp, [rsp-27h]
0x18000a281  sub     rsp, 0F0h
0x18000a288  mov     r13, rdx
0x18000a28b  mov     rsi, rcx
0x18000a28e  xor     r15d, r15d
0x18000a291  mov     [rbp+57h+var_98], r15
0x18000a295  lea     r12, ??_7?$CAutoPbrDelete@PEAVSerializeNodeList@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::`vftable'
0x18000a29c  mov     [rbp+57h+var_A0], r12
0x18000a2a0  lea     rcx, [rbp+57h+var_A0]
0x18000a2a4  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18000a2a9  mov     rdx, rax; struct PushButtonReset::SerializeNodeList **
0x18000a2ac  lea     r8, aPackageEntry; "Package/Entry"
0x18000a2b3  mov     rcx, r13; this
0x18000a2b6  call    ?SelectChildren@SerializeNode@PushButtonReset@@QEAAJPEAPEAVSerializeNodeList@2@PEBGZZ; PushButtonReset::SerializeNode::SelectChildren(PushButtonReset::SerializeNodeList * *,ushort const *,...)
0x18000a2bb  mov     ebx, eax
0x18000a2bd  test    eax, eax
0x18000a2bf  jns     short loc_18000A2F3
0x18000a2c1  lea     rax, aFailedToLookUp_1; "Failed to look up Packages entries"
0x18000a2c8  mov     [rsp+120h+var_F8], rax
0x18000a2cd  mov     [rsp+120h+var_100], 8C6h
0x18000a2d5  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000a2dc  lea     r8, aWinreagentExec_9; "WinREAgent::Executor::InternalLoad"
0x18000a2e3  mov     edx, ebx
0x18000a2e5  lea     ecx, [r15+2]
0x18000a2e9  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000a2ee  jmp     loc_18000ACB9
0x18000a2f3  mov     edi, r15d
0x18000a2f6  lea     r14, ??_7?$CAutoPbrDelete@PEAVSerializeNode@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable'
0x18000a2fd  lea     r12, ??_7?$CAutoPbrDelete@PEAUPACKAGE_INFO@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::PACKAGE_INFO *>::`vftable'
0x18000a304  mov     rax, [rbp+57h+var_A0]
0x18000a308  lea     rcx, [rbp+57h+var_A0]
0x18000a30c  mov     rax, [rax+18h]
0x18000a310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a315  mov     rcx, [rax]
0x18000a318  cmp     edi, [rcx+8]
0x18000a31b  jnb     loc_18000A6B2
0x18000a321  mov     [rbp+57h+var_B8], r15
0x18000a325  mov     [rbp+57h+var_C0], r14
0x18000a329  mov     rax, [rbp+57h+var_A0]
0x18000a32d  lea     rcx, [rbp+57h+var_A0]
0x18000a331  mov     rax, [rax+18h]
0x18000a335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a33a  mov     rbx, rax
0x18000a33d  mov     rcx, [rbp+57h+var_C0]
0x18000a341  mov     rax, [rcx+8]
0x18000a345  lea     rcx, [rbp+57h+var_C0]
0x18000a349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a34e  mov     r8, rax; struct PushButtonReset::SerializeNode **
0x18000a351  mov     edx, edi; unsigned int
0x18000a353  mov     rcx, rbx; this
0x18000a356  call    ?GetNode@SerializeNodeList@PushButtonReset@@QEAAJKPEAPEAVSerializeNode@2@@Z; PushButtonReset::SerializeNodeList::GetNode(ulong,PushButtonReset::SerializeNode * *)
0x18000a35b  mov     ebx, eax
0x18000a35d  test    eax, eax
0x18000a35f  js      loc_18000A67E
0x18000a365  lea     rcx, [rbp+57h+arg_10]
0x18000a369  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000a36e  nop
0x18000a36f  mov     [rbp+57h+var_78], r15
0x18000a373  mov     [rbp+57h+var_90], r15
0x18000a377  mov     rax, [rbp+57h+var_C0]
0x18000a37b  lea     rcx, [rbp+57h+var_C0]
0x18000a37f  mov     rax, [rax+18h]
0x18000a383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a388  mov     rbx, rax
0x18000a38b  lea     rdx, aPackagepath; "PackagePath"
0x18000a392  lea     rcx, [rbp+57h+arg_18]
0x18000a396  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18000a39b  nop
0x18000a39c  lea     r8, [rbp+57h+arg_10]
0x18000a3a0  lea     rdx, [rbp+57h+arg_18]
0x18000a3a4  mov     rcx, rbx
0x18000a3a7  call    ?GetProperty@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::SerializeNode::GetProperty(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18000a3ac  mov     ebx, eax
0x18000a3ae  mov     rcx, [rbp+57h+arg_18]
0x18000a3b2  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000a3b6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000a3bb  test    ebx, ebx
0x18000a3bd  js      loc_18000A664
0x18000a3c3  mov     rax, [rbp+57h+var_C0]
0x18000a3c7  lea     rcx, [rbp+57h+var_C0]
0x18000a3cb  mov     rax, [rax+18h]
0x18000a3cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3d4  mov     rbx, rax
0x18000a3d7  lea     rdx, aPackagesize; "PackageSize"
0x18000a3de  lea     rcx, [rbp+57h+var_58]
0x18000a3e2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18000a3e7  nop
0x18000a3e8  lea     r8, [rbp+57h+var_78]
0x18000a3ec  lea     rdx, [rbp+57h+var_58]
0x18000a3f0  mov     rcx, rbx
0x18000a3f3  call    ?GetProperty@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEA_K@Z; PushButtonReset::SerializeNode::GetProperty(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,unsigned __int64 *)
0x18000a3f8  mov     ebx, eax
0x18000a3fa  mov     rcx, [rbp+57h+var_58]
0x18000a3fe  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000a402  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000a407  test    ebx, ebx
0x18000a409  js      loc_18000A605
0x18000a40f  mov     rax, [rbp+57h+var_C0]
0x18000a413  lea     rcx, [rbp+57h+var_C0]
0x18000a417  mov     rax, [rax+18h]
0x18000a41b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a420  mov     rbx, rax
0x18000a423  lea     rdx, aInstallsize; "InstallSize"
0x18000a42a  lea     rcx, [rbp+57h+var_88]
0x18000a42e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18000a433  nop
0x18000a434  lea     r8, [rbp+57h+var_90]
0x18000a438  lea     rdx, [rbp+57h+var_88]
0x18000a43c  mov     rcx, rbx
0x18000a43f  call    ?GetProperty@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEA_K@Z; PushButtonReset::SerializeNode::GetProperty(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,unsigned __int64 *)
0x18000a444  mov     ebx, eax
0x18000a446  mov     rcx, [rbp+57h+var_88]
0x18000a44a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000a44e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000a453  test    ebx, ebx
0x18000a455  js      loc_18000A5AB
0x18000a45b  call    ??$PbrNew@UPACKAGE_INFO@WinREAgent@@$$V@@YAPEAUPACKAGE_INFO@WinREAgent@@XZ; PbrNew<WinREAgent::PACKAGE_INFO,>(void)
0x18000a460  mov     [rbp+57h+var_60], rax
0x18000a464  mov     [rbp+57h+var_68], r12
0x18000a468  lea     rcx, [rbp+57h+var_68]
0x18000a46c  call    ??7?$CAutoCleanupBase@PEAUISetupOneSettings@@@RAII@@UEBA_NXZ; RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(void)
0x18000a471  test    al, al
0x18000a473  jnz     loc_18000A565
0x18000a479  mov     rax, [rbp+57h+var_68]
0x18000a47d  lea     rcx, [rbp+57h+var_68]
0x18000a481  mov     rax, [rax+18h]
0x18000a485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a48a  mov     r12, rax
0x18000a48d  mov     rdx, [rbp+57h+arg_10]
0x18000a491  lea     r15, [rdx-18h]
0x18000a495  mov     r14, [rax]
0x18000a498  add     r14, 0FFFFFFFFFFFFFFE8h
0x18000a49c  cmp     r15, r14
0x18000a49f  jz      short loc_18000A4D9
0x18000a4a1  cmp     dword ptr [r14+10h], 0
0x18000a4a6  jl      short loc_18000A4CD
0x18000a4a8  mov     r8, [r14]
0x18000a4ab  cmp     [r15], r8
0x18000a4ae  jnz     short loc_18000A4CD
0x18000a4b0  mov     rcx, r15
0x18000a4b3  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18000a4b8  mov     rbx, rax
0x18000a4bb  mov     rcx, r14; this
0x18000a4be  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000a4c3  lea     rax, [rbx+18h]
0x18000a4c7  mov     [r12], rax
0x18000a4cb  jmp     short loc_18000A4D9
0x18000a4cd  mov     r8d, [rdx-10h]
0x18000a4d1  mov     rcx, r12
0x18000a4d4  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000a4d9  mov     rax, [rbp+57h+var_68]
0x18000a4dd  lea     rcx, [rbp+57h+var_68]
0x18000a4e1  mov     rax, [rax+18h]
0x18000a4e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4ea  mov     rcx, [rbp+57h+var_78]
0x18000a4ee  mov     [rax+8], rcx
0x18000a4f2  mov     rax, [rbp+57h+var_68]
0x18000a4f6  lea     rcx, [rbp+57h+var_68]
0x18000a4fa  mov     rax, [rax+18h]
0x18000a4fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a503  mov     rdx, [rbp+57h+var_90]
0x18000a507  mov     [rax+10h], rdx
0x18000a50b  mov     rax, [rbp+57h+var_60]
0x18000a50f  mov     [rbp+57h+var_60], 0
0x18000a517  mov     [rbp+57h+var_90], rax
0x18000a51b  lea     rcx, [rsi+60h]
0x18000a51f  lea     rdx, [rbp+57h+var_90]
0x18000a523  call    ?Add@?$CAtlArray@PEAUPACKAGE_INFO@WinREAgent@@V?$CElementTraits@PEAUPACKAGE_INFO@WinREAgent@@@ATL@@@ATL@@QEAA_KAEBQEAUPACKAGE_INFO@WinREAgent@@@Z; ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(WinREAgent::PACKAGE_INFO * const &)
0x18000a528  nop
0x18000a529  lea     r12, ??_7?$CAutoPbrDelete@PEAUPACKAGE_INFO@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::PACKAGE_INFO *>::`vftable'
0x18000a530  mov     [rbp+57h+var_68], r12
0x18000a534  lea     rcx, [rbp+57h+var_68]
0x18000a538  call    ?Release@?$CAutoPbrDelete@PEAUPACKAGE_INFO@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::PACKAGE_INFO *>::Release(void)
0x18000a53d  nop
0x18000a53e  mov     rcx, r15; this
0x18000a541  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000a546  nop
0x18000a547  lea     r14, ??_7?$CAutoPbrDelete@PEAVSerializeNode@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable'
0x18000a54e  mov     [rbp+57h+var_C0], r14
0x18000a552  lea     rcx, [rbp+57h+var_C0]
0x18000a556  call    ?Release@?$CAutoPbrDelete@PEAVSerializeNode@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(void)
0x18000a55b  inc     edi
0x18000a55d  xor     r15d, r15d
0x18000a560  jmp     loc_18000A304
0x18000a565  lea     rax, aFailedToAlloca_23; "Failed to allocate package"
0x18000a56c  mov     [rsp+120h+var_F8], rax
0x18000a571  mov     [rsp+120h+var_100], 8DCh
0x18000a579  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000a580  lea     r8, aWinreagentExec_9; "WinREAgent::Executor::InternalLoad"
0x18000a587  mov     edx, 8007000Eh
0x18000a58c  mov     ecx, 2
0x18000a591  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000a596  nop
0x18000a597  mov     [rbp+57h+var_68], r12
0x18000a59b  lea     rcx, [rbp+57h+var_68]
0x18000a59f  call    ?Release@?$CAutoPbrDelete@PEAUPACKAGE_INFO@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::PACKAGE_INFO *>::Release(void)
0x18000a5a4  mov     ebx, 8007000Eh
0x18000a5a9  jmp     short loc_18000A5DE
0x18000a5ab  mov     [rsp+120h+var_F0], edi
0x18000a5af  lea     rax, aFailedToLoadIn; "Failed to load InstallSize of entry nod"...
0x18000a5b6  mov     [rsp+120h+var_F8], rax
0x18000a5bb  mov     [rsp+120h+var_100], 8D9h
0x18000a5c3  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000a5ca  lea     r8, aWinreagentExec_9; "WinREAgent::Executor::InternalLoad"
0x18000a5d1  mov     edx, ebx
0x18000a5d3  mov     ecx, 2
0x18000a5d8  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000a5dd  nop
0x18000a5de  mov     rcx, [rbp+57h+arg_10]
0x18000a5e2  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000a5e6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000a5eb  nop
0x18000a5ec  mov     [rbp+57h+var_C0], r14
0x18000a5f0  lea     rcx, [rbp+57h+var_C0]
0x18000a5f4  call    ?Release@?$CAutoPbrDelete@PEAVSerializeNode@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(void)
0x18000a5f9  lea     r12, ??_7?$CAutoPbrDelete@PEAVSerializeNodeList@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::`vftable'
0x18000a600  jmp     loc_18000ACB9
0x18000a605  mov     [rsp+120h+var_F0], edi
0x18000a609  lea     rax, aFailedToLoadPa; "Failed to load PackageSize of entry nod"...
0x18000a610  mov     [rsp+120h+var_F8], rax
0x18000a615  mov     [rsp+120h+var_100], 8D6h
0x18000a61d  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000a624  lea     r8, aWinreagentExec_9; "WinREAgent::Executor::InternalLoad"
0x18000a62b  mov     edx, ebx
0x18000a62d  mov     ecx, 2
0x18000a632  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000a637  nop
0x18000a638  mov     rcx, [rbp+57h+arg_10]
0x18000a63c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000a640  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000a645  nop
0x18000a646  mov     [rbp+57h+var_C0], r14
0x18000a64a  lea     rcx, [rbp+57h+var_C0]
0x18000a64e  call    ?Release@?$CAutoPbrDelete@PEAVSerializeNode@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(void)
0x18000a653  nop
0x18000a654  lea     rax, ??_7?$CAutoPbrDelete@PEAVSerializeNodeList@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::`vftable'
0x18000a65b  mov     [rbp+57h+var_A0], rax
0x18000a65f  jmp     loc_18000ACBD
0x18000a664  mov     [rsp+120h+var_F0], edi
0x18000a668  lea     rax, aFailedToLoadPa_0; "Failed to load PackagePath of entry nod"...
0x18000a66f  mov     [rsp+120h+var_F8], rax
0x18000a674  mov     [rsp+120h+var_100], 8D3h
0x18000a67c  jmp     short loc_18000A61D
0x18000a67e  mov     [rsp+120h+var_F0], edi
0x18000a682  lea     rax, aFailedToRetrie; "Failed to retrieve Packages entry node "...
0x18000a689  mov     [rsp+120h+var_F8], rax
0x18000a68e  mov     [rsp+120h+var_100], 8CCh
0x18000a696  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000a69d  lea     r8, aWinreagentExec_9; "WinREAgent::Executor::InternalLoad"
0x18000a6a4  mov     edx, ebx
0x18000a6a6  mov     ecx, 2
0x18000a6ab  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000a6b0  jmp     short loc_18000A646
0x18000a6b2  mov     [rsp+120h+var_D8], r15
0x18000a6b7  lea     r12, ??_7?$CAutoPbrDelete@PEAVSerializeNodeList@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::`vftable'
0x18000a6be  mov     [rsp+120h+var_E0], r12
0x18000a6c3  lea     rcx, [rsp+120h+var_E0]
0x18000a6c8  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18000a6cd  mov     rdx, rax; struct PushButtonReset::SerializeNodeList **
0x18000a6d0  lea     r8, aStageoperation; "StageOperation"
0x18000a6d7  mov     rcx, r13; this
0x18000a6da  call    ?SelectChildren@SerializeNode@PushButtonReset@@QEAAJPEAPEAVSerializeNodeList@2@PEBGZZ; PushButtonReset::SerializeNode::SelectChildren(PushButtonReset::SerializeNodeList * *,ushort const *,...)
0x18000a6df  mov     ebx, eax
0x18000a6e1  test    eax, eax
0x18000a6e3  jns     short loc_18000A718
0x18000a6e5  lea     rax, aFailedToEnumer_7; "Failed to enumerate Operation subnodes"
0x18000a6ec  mov     [rsp+120h+var_F8], rax
0x18000a6f1  mov     [rsp+120h+var_100], 8E8h
0x18000a6f9  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000a700  lea     r8, aWinreagentExec_9; "WinREAgent::Executor::InternalLoad"
0x18000a707  mov     edx, ebx
0x18000a709  mov     ecx, 2
0x18000a70e  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000a713  jmp     loc_18000ACA9
0x18000a718  mov     edi, r15d
0x18000a71b  mov     rax, [rsp+120h+var_E0]
0x18000a720  lea     rcx, [rsp+120h+var_E0]
0x18000a725  mov     rax, [rax+18h]
0x18000a729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a72e  mov     rcx, [rax]
0x18000a731  cmp     edi, [rcx+8]
0x18000a734  jnb     loc_18000A88E
0x18000a73a  mov     [rbp+57h+var_70], r15
0x18000a73e  mov     [rbp+57h+var_78], r14
0x18000a742  mov     rax, [rsp+120h+var_E0]
0x18000a747  lea     rcx, [rsp+120h+var_E0]
0x18000a74c  mov     rax, [rax+18h]
0x18000a750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a755  mov     rbx, rax
0x18000a758  mov     rcx, [rbp+57h+var_78]
0x18000a75c  mov     rax, [rcx+8]
0x18000a760  lea     rcx, [rbp+57h+var_78]
  ... truncated ...
```
