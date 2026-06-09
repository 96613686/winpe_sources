# CSMBHelperClass::CSMBHelperClass(void)

- ea: `0x180002974`
- end: `0x18000359a`
- name: `??0CSMBHelperClass@@QEAA@XZ`
- size: `3110`
- prototype: `CSMBHelperClass *__fastcall(CSMBHelperClass *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180004a88`

## callees

- `0x18000123c`
- `0x1800015b8`
- `0x180002974`
- `0x180004ee0`
- `0x180005f64`
- `0x18000a320`
- `0x18000cb80`
- `0x18000cc24`
- `0x18000d374`
- `0x18000e010`
- `0x18000e10c`
- `0x18000eddc`
- `0x18000f494`
- `0x18000f520`
- `0x18000f624`
- `0x18000f684`
- `0x18000f7dc`
- `0x18000f970`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002a58`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003091`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002a58`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003091`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180003066`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180003066`

## string_xrefs

- `0x180002b37`: `UNCPath`
- `0x180002afd`: `HelpLinkURL`
- `0x18000325b`: `HelpLinkURL`
- `0x180003334`: `HelpLinkURL`
- `0x180002b0c`: `ImpersonationRequired`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
CSMBHelperClass *__fastcall CSMBHelperClass::CSMBHelperClass(CSMBHelperClass *this)
{
  CSMBHelperClass *v1; // rdi
  RootCauseList *v2; // rsi
  _QWORD *v3; // r15
  __int64 v4; // rcx
  __int64 v5; // rcx
  _BYTE *v6; // rax
  Repair *v7; // rax
  Repair *v8; // rbx
  __int64 v9; // r14
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rax
  unsigned __int16 **v13; // rax
  struct RootCause *v14; // rax
  unsigned __int16 **v15; // rax
  struct RootCause *v16; // rax
  unsigned __int16 **v17; // rax
  struct RootCause *v18; // rax
  RootCause *RootCause; // rax
  unsigned __int16 **v20; // rax
  struct RootCause *v21; // rax
  RootCause *v22; // r14
  Repair *v23; // rax
  Repair *v24; // rbx
  unsigned __int16 **v25; // rax
  struct RootCause *v26; // rax
  RootCause *v27; // r14
  Repair *v28; // rax
  Repair *v29; // rbx
  unsigned __int16 **v30; // rax
  struct RootCause *v31; // rax
  RootCause *v32; // r14
  Repair *v33; // rax
  Repair *v34; // rbx
  unsigned __int16 **v35; // rax
  struct RootCause *v36; // rax
  RootCause *v37; // r14
  Repair *v38; // rax
  Repair *v39; // rbx
  unsigned __int16 **v40; // rax
  struct RootCause *v41; // rax
  RootCause *v42; // rsi
  Repair *v43; // rax
  Repair *v44; // rbx
  int v45; // ebx
  int i; // eax
  unsigned __int16 **v47; // rax
  struct RootCause *v48; // rax
  RootCause *v49; // r14
  Repair *v50; // rax
  Repair *v51; // rbx
  struct RootCause *v52; // rax
  Repair *v53; // rax
  unsigned __int16 **v54; // rax
  struct RootCause *v55; // rax
  RootCause *v56; // r14
  Repair *v57; // rax
  struct Repair *v58; // rbx
  unsigned __int16 **v59; // rax
  struct RootCause *v60; // rax
  RootCause *v61; // rsi
  Repair *v62; // rax
  Repair *v63; // rbx
  __int64 v64; // rbx
  __int64 v66; // rbx
  __int64 v67; // rbx
  __int64 v68; // [rsp+30h] [rbp-58h] BYREF
  struct _GUID ppv; // [rsp+40h] [rbp-48h] BYREF
  __int64 v71; // [rsp+98h] [rbp+10h] BYREF
  int v72; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v73; // [rsp+A8h] [rbp+20h] BYREF

  v1 = this;
  *((_DWORD *)this + 16) = 0;
  *(_OWORD *)((char *)this + 72) = 0;
  *(_OWORD *)((char *)this + 88) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_BYTE *)this + 112) = 0;
  *(_QWORD *)this = &CNetDiagHelperImpl::`vftable'{for `INetDiagHelper'};
  *((_QWORD *)this + 1) = &CNetDiagHelperImpl::`vftable'{for `INetDiagHelperInfo'};
  *(_QWORD *)((char *)this + 20) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 4) = 0;
  *((_QWORD *)this + 7) = &CNetDiagHelperExImpl::`vftable';
  v2 = (CSMBHelperClass *)((char *)this + 184);
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 23) = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<unsigned long const,RootCause *>>>::_Buyheadnode();
  *((_QWORD *)v2 + 2) = 0;
  AttributeList::AttributeList((CSMBHelperClass *)((char *)v1 + 208));
  v3 = (_QWORD *)((char *)v1 + 232);
  *((_QWORD *)v1 + 29) = 0;
  *((_QWORD *)v1 + 30) = 0;
  *((_QWORD *)v1 + 29) = std::_List_alloc<0,std::_List_base_types<AttributeDescriptor>>::_Buynode0(v4, 0, 0);
  *((_QWORD *)v1 + 31) = 0;
  *((_QWORD *)v1 + 32) = 0;
  *((_QWORD *)v1 + 33) = 0;
  *((_QWORD *)v1 + 37) = 0;
  if ( CoCreateInstance(&CLSID_NDFEtw, 0, 1u, &IID_INDFEtw, (LPVOID *)v1 + 22) )
    *((_QWORD *)v1 + 22) = 0;
  *((_QWORD *)v1 + 35) = 0;
  *((_DWORD *)v1 + 72) = 0;
  *((_QWORD *)v1 + 15) = 0;
  *((_QWORD *)v1 + 16) = 0;
  v5 = 16;
  v6 = (char *)v1 + 156;
  do
  {
    *v6++ = 0;
    --v5;
  }
  while ( v5 );
  try
  {
    v7 = (Repair *)operator new(0x38u);
    v8 = v7;
    v71 = (__int64)v7;
    if ( v7 )
    {
      ppv = (struct _GUID)SMBHC_GUID_REPAIR_CHECKFILEPERMISSIONS;
      Repair::Repair(v7, (unsigned __int16 *)0x7D, &ppv);
      *(_QWORD *)v8 = &FilePermissionRepair::`vftable';
      AttributeList::setDWordAttribute((Repair *)((char *)v8 + 8), L"ContactAdmin", 1u);
    }
    else
    {
      v8 = 0;
    }
    AttributeList::setStringAttribute(
      (Repair *)((char *)v8 + 8),
      L"HelpLinkURL",
      L"mshelp://Windows/?id=089a542f-c717-442e-8840-5935a8f52b0e");
    AttributeList::setDWordAttribute((CSMBHelperClass *)((char *)v1 + 208), L"ImpersonationRequired", 1u);
    ppv = 0;
    *(_QWORD *)&ppv.Data1 = AllocateTestMemory(0x10u);
    *(_DWORD *)ppv.Data4 = 1;
    StringCchCopyW(*(unsigned __int16 **)&ppv.Data1, 8u, L"UNCPath");
    v9 = *v3;
    v11 = std::_List_buy<AttributeDescriptor>::_Buynode<AttributeDescriptor const &>(
            v10,
            *v3,
            *(_QWORD *)(*v3 + 8LL),
            &ppv);
    v12 = *((_QWORD *)v1 + 30);
    if ( 0x7FFFFFFFFFFFFFELL == v12 )
      std::_Xlength_error("list<T> too long");
    *((_QWORD *)v1 + 30) = v12 + 1;
    *(_QWORD *)(v9 + 8) = v11;
    **(_QWORD **)(v11 + 8) = v11;
    v13 = (unsigned __int16 **)operator new(0x28u);
    v71 = (__int64)v13;
    if ( v13 )
    {
      ppv = (struct _GUID)SMBHC_GUID_RC_CONNECTIVITY_FAILURE;
      v14 = RootCause::RootCause(v13, (unsigned __int16 *)0x72, &ppv);
    }
    else
    {
      v14 = 0;
    }
    RootCauseList::addRootCause(v2, 0, v14);
    v15 = (unsigned __int16 **)operator new(0x28u);
    v71 = (__int64)v15;
    if ( v15 )
    {
      ppv = (struct _GUID)SMBHC_GUID_RC_SERVER_FAILURE;
      v16 = RootCause::RootCause(v15, (unsigned __int16 *)0x72, &ppv);
    }
    else
    {
      v16 = 0;
    }
    RootCauseList::addRootCause(v2, 4u, v16);
    v17 = (unsigned __int16 **)operator new(0x28u);
    v71 = (__int64)v17;
    if ( v17 )
    {
      ppv = (struct _GUID)SMBHC_GUID_RC_FILE_PERMISSION_FAILURE;
      v18 = RootCause::RootCause(v17, (unsigned __int16 *)0x78, &ppv);
    }
    else
    {
      v18 = 0;
    }
    RootCauseList::addRootCause(v2, 7u, v18);
    RootCause = RootCauseList::getRootCause(v2, 7u);
    RootCause::addRepair(RootCause, v8);
    v20 = (unsigned __int16 **)operator new(0x28u);
    v71 = (__int64)v20;
    if ( v20 )
    {
      ppv = (struct _GUID)SMBHC_GUID_RC_FILE_CONNECT_FAILURE;
      v21 = RootCause::RootCause(v20, (unsigned __int16 *)0x77, &ppv);
    }
    else
    {
      v21 = 0;
    }
    RootCauseList::addRootCause(v2, 8u, v21);
    v22 = RootCauseList::getRootCause(v2, 8u);
    v23 = (Repair *)operator new(0x38u);
    v24 = v23;
    v71 = (__int64)v23;
    if ( v23 )
    {
      ppv = (struct _GUID)SMBHC_GUID_REPAIR_CHECKFILEPATH;
      Repair::Repair(v23, (unsigned __int16 *)0x7C, &ppv);
      *(_QWORD *)v24 = &CheckPathRepair::`vftable';
      AttributeList::setDWordAttribute((Repair *)((char *)v24 + 8), L"Informational", 1u);
    }
    else
    {
      v24 = 0;
    }
    RootCause::addRepair(v22, v24);
    v25 = (unsigned __int16 **)operator new(0x28u);
    v71 = (__int64)v25;
    if ( v25 )
    {
      ppv = (struct _GUID)SMBHC_GUID_RC_SHARE_CONNECT_FAILURE;
      v26 = RootCause::RootCause(v25, (unsigned __int16 *)0x74, &ppv);
    }
    else
    {
      v26 = 0;
    }
    RootCauseList::addRootCause(v2, 6u, v26);
    v27 = RootCauseList::getRootCause(v2, 6u);
    v28 = (Repair *)operator new(0x38u);
    v29 = v28;
    v71 = (__int64)v28;
    if ( v28 )
    {
      ppv = (struct _GUID)SMBHC_GUID_REPAIR_CHECKSHARE;
      Repair::Repair(v28, (unsigned __int16 *)0x7A, &ppv);
      *(_QWORD *)v29 = &CheckShareRepair::`vftable';
      AttributeList::setDWordAttribute((Repair *)((char *)v29 + 8), L"Informational", 1u);
    }
    else
    {
      v29 = 0;
    }
    RootCause::addRepair(v27, v29);
    v30 = (unsigned __int16 **)operator new(0x28u);
    v71 = (__int64)v30;
    if ( v30 )
    {
      ppv = (struct _GUID)SMBHC_GUID_RC_SHAREMAXCONNECTIONS_FAILURE;
      v31 = RootCause::RootCause(v30, (unsigned __int16 *)0x80, &ppv);
    }
    else
    {
      v31 = 0;
    }
    RootCauseList::addRootCause(v2, 0xBu, v31);
    v32 = RootCauseList::getRootCause(v2, 0xBu);
    v33 = (Repair *)operator new(0x38u);
    v34 = v33;
    v71 = (__int64)v33;
    if ( v33 )
    {
      ppv = (struct _GUID)SMBHC_GUID_REPAIR_MAXCONNECTIONREACHED;
      Repair::Repair(v33, (unsigned __int16 *)0x81, &ppv);
      *(_QWORD *)v34 = &MaxConnectionsRepair::`vftable';
      AttributeList::setDWordAttribute((Repair *)((char *)v34 + 8), L"ContactAdmin", 1u);
    }
    else
    {
      v34 = 0;
    }
    RootCause::addRepair(v32, v34);
    v35 = (unsigned __int16 **)operator new(0x28u);
    v71 = (__int64)v35;
    if ( v35 )
    {
      ppv = (struct _GUID)SMBHC_GUID_RC_DUPLICATENAME_FAILURE;
      v36 = RootCause::RootCause(v35, (unsigned __int16 *)0x82, &ppv);
    }
    else
    {
      v36 = 0;
    }
    RootCauseList::addRootCause(v2, 0xEu, v36);
    v37 = RootCauseList::getRootCause(v2, 0xEu);
    v38 = (Repair *)operator new(0x38u);
    v39 = v38;
    v71 = (__int64)v38;
    if ( v38 )
    {
      ppv = (struct _GUID)SMBHC_GUID_REPAIR_DUPLICATENAME;
      Repair::Repair(v38, (unsigned __int16 *)0x83, &ppv);
      *(_QWORD *)v39 = &DuplicateNameRepair::`vftable';
      AttributeList::setDWordAttribute((Repair *)((char *)v39 + 8), L"ContactAdmin", 1u);
    }
    else
    {
      v39 = 0;
    }
    RootCause::addRepair(v37, v39);
    v40 = (unsigned __int16 **)operator new(0x28u);
    v71 = (__int64)v40;
    if ( v40 )
    {
      ppv = (struct _GUID)SMBHC_GUID_RC_INVALIDNETWORKRESPONSE_FAILURE;
      v41 = RootCause::RootCause(v40, (unsigned __int16 *)0x84, &ppv);
    }
    else
    {
      v41 = 0;
    }
    RootCauseList::addRootCause(v2, 0xDu, v41);
    v42 = RootCauseList::getRootCause(v2, 0xDu);
    v43 = (Repair *)operator new(0x38u);
    v44 = v43;
    v71 = (__int64)v43;
    if ( v43 )
    {
      ppv = (struct _GUID)SMBHC_GUID_REPAIR_INVALIDNETWORKRESPONSE;
      Repair::Repair(v43, (unsigned __int16 *)0x85, &ppv);
      *(_QWORD *)v44 = &InvalidNetworkResponseRepair::`vftable';
      AttributeList::setDWordAttribute((Repair *)((char *)v44 + 8), L"Informational", 1u);
    }
    else
    {
      v44 = 0;
    }
    RootCause::addRepair(v42, v44);
    v45 = 0;
    *(_QWORD *)&ppv.Data1 = 0;
    v68 = 0;
    v73 = 0;
    v72 = 0;
    LODWORD(v71) = 0;
    if ( CoInitializeEx(0, 0) >= 0
      && CoCreateInstance(&CLSID_NetworkListManager, 0, 1u, &IID_INetworkListManager, (LPVOID *)&ppv) >= 0
      && (*(int (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)&ppv.Data1 + 72LL))(*(_QWORD *)&ppv.Data1, &v68) >= 0 )
    {
      for ( i = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v68 + 64LL))(
                  v68,
                  1,
                  &v73,
                  &v72);
            !i && !(*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v73 + 104LL))(v73, &v71);
            i = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v68 + 64LL))(
                  v68,
                  1,
                  &v73,
                  &v72) )
      {
        if ( !(_DWORD)v71 )
        {
          v45 = 1;
          break;
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
        v73 = 0;
      }
    }
    if ( *(_QWORD *)&ppv.Data1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&ppv.Data1 + 16LL))(*(_QWORD *)&ppv.Data1);
    if ( v68 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
    if ( v73 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
    v47 = (unsigned __int16 **)operator new(0x28u);
    if ( v45 )
    {
      v71 = (__int64)v47;
      if ( v47 )
      {
        ppv = (struct _GUID)SMBHC_GUID_RC_SHARE_PERMISSION_FAILURE;
        v48 = RootCause::RootCause(v47, (unsigned __int16 *)0x86, &ppv);
      }
      else
      {
        v48 = 0;
      }
      RootCauseList::addRootCause((CSMBHelperClass *)((char *)v1 + 184), 5u, v48);
      v49 = RootCauseList::getRootCause((CSMBHelperClass *)((char *)v1 + 184), 5u);
      v50 = (Repair *)operator new(0x38u);
      v51 = v50;
      v71 = (__int64)v50;
      if ( v50 )
      {
        ppv = (struct _GUID)SMBHC_GUID_REPAIR_CHECKSHAREPERMISSIONS_HOME;
        Repair::Repair(v50, (unsigned __int16 *)0x87, &ppv);
        *(_QWORD *)v51 = &CheckLoginRepairHome::`vftable';
        AttributeList::setDWordAttribute((Repair *)((char *)v51 + 8), L"RequiresUserAction", 1u);
        AttributeList::setStringAttribute(
          (Repair *)((char *)v51 + 8),
          L"HelpLinkURL",
          L"mshelp://Windows/?id=089a542f-c717-442e-8840-5935a8f52b0e");
      }
      else
      {
        v51 = 0;
      }
    }
    else
    {
      v71 = (__int64)v47;
      if ( v47 )
      {
        ppv = (struct _GUID)SMBHC_GUID_RC_SHARE_PERMISSION_FAILURE;
        v52 = RootCause::RootCause(v47, (unsigned __int16 *)0x73, &ppv);
      }
      else
      {
        v52 = 0;
      }
      RootCauseList::addRootCause((CSMBHelperClass *)((char *)v1 + 184), 5u, v52);
      v49 = RootCauseList::getRootCause((CSMBHelperClass *)((char *)v1 + 184), 5u);
      v53 = (Repair *)operator new(0x38u);
      v51 = v53;
      v71 = (__int64)v53;
      if ( v53 )
      {
        ppv = (struct _GUID)SMBHC_GUID_REPAIR_CHECKSHAREPERMISSIONS;
        Repair::Repair(v53, (unsigned __int16 *)0x79, &ppv);
        *(_QWORD *)v51 = &CheckLoginRepairHome::`vftable';
        AttributeList::setDWordAttribute((Repair *)((char *)v51 + 8), L"RequiresUserAction", 1u);
        AttributeList::setStringAttribute(
          (Repair *)((char *)v51 + 8),
          L"HelpLinkURL",
          L"mshelp://Windows/?id=089a542f-c717-442e-8840-5935a8f52b0e");
      }
      else
      {
        v51 = 0;
      }
    }
    RootCause::addRepair(v49, v51);
    v54 = (unsigned __int16 **)operator new(0x28u);
    v71 = (__int64)v54;
    if ( v54 )
    {
      ppv = (struct _GUID)SMBHC_GUID_RC_TOOMANYCREDENTIALS;
      v55 = RootCause::RootCause(v54, (unsigned __int16 *)0x76, &ppv);
    }
    else
    {
      v55 = 0;
    }
    RootCauseList::addRootCause((CSMBHelperClass *)((char *)v1 + 184), 0xAu, v55);
    v56 = RootCauseList::getRootCause((CSMBHelperClass *)((char *)v1 + 184), 0xAu);
    v57 = (Repair *)operator new(0x38u);
    v58 = v57;
    v71 = (__int64)v57;
    if ( v57 )
    {
      ppv = (struct _GUID)SMBHC_ID_REPAIR_CLOSECONNECTIONS;
      Repair::Repair(v57, (unsigned __int16 *)0x7E, &ppv);
      *(_QWORD *)v58 = &CloseConnectionsRepair::`vftable';
    }
    else
    {
      v58 = 0;
    }
    RootCause::addRepair(v56, v58);
    v59 = (unsigned __int16 **)operator new(0x28u);
    v71 = (__int64)v59;
    if ( v59 )
    {
      ppv = (struct _GUID)SMBHC_GUID_RC_GENERICFAILUREME;
      v60 = RootCause::RootCause(v59, (unsigned __int16 *)0x75, &ppv);
    }
    else
    {
      v60 = 0;
    }
    RootCauseList::addRootCause((CSMBHelperClass *)((char *)v1 + 184), 2u, v60);
    v61 = RootCauseList::getRootCause((CSMBHelperClass *)((char *)v1 + 184), 2u);
    v62 = (Repair *)operator new(0x38u);
    v63 = v62;
    v71 = (__int64)v62;
    if ( v62 )
    {
      ppv = (struct _GUID)SMBHC_GUID_REPAIR_GENERICFAILUREME;
      Repair::Repair(v62, (unsigned __int16 *)0x7B, &ppv);
      *(_QWORD *)v63 = &GenericFailureRepair::`vftable';
      AttributeList::setDWordAttribute((Repair *)((char *)v63 + 8), L"Informational", 1u);
    }
    else
    {
      v63 = 0;
    }
    RootCause::addRepair(v61, v63);
    if ( (int)CSMBHelperClass::InitializeMap_SMBHC_RC_EventMap(v1) < 0 )
    {
      if ( *((_QWORD *)v1 + 22) )
      {
        v71 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &v71,
          L"CSMBHelperClass::CSMBHelperClass Failed");
        v64 = v71;
        (*(void (__fastcall **)(_QWORD, __int64, _QWORD, const unsigned __int16 *, __int64))(**((_QWORD **)v1 + 22)
                                                                                           + 24LL))(
          *((_QWORD *)v1 + 22),
          2,
          0,
          L"SMBHelperClass",
          v71);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v64 - 24 + 16), 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v64 - 24) + 8LL))(*(_QWORD *)(v64 - 24));
      }
      *((_DWORD *)v1 + 70) = 1;
    }
  }
  catch ( enum TestException )
  {
    if ( *((_QWORD *)this + 22) )
    {
      v71 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &v71,
        L"CSMBHelperClass::CSMBHelperClass Failed");
      v66 = v71;
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD, const unsigned __int16 *, __int64))(**((_QWORD **)this + 22)
                                                                                         + 24LL))(
        *((_QWORD *)this + 22),
        2,
        0,
        L"SMBHelperClass",
        v71);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v66 - 8), 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v66 - 24) + 8LL))(*(_QWORD *)(v66 - 24), v66 - 24);
    }
    *((_DWORD *)this + 70) = 1;
    return this;
  }
  catch ( exception )
  {
    if ( *((_QWORD *)this + 22) )
    {
      v71 = guard_dispatch_icall_thunk_10345483385596137414(&ATL::g_strmgr) + 24;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &v71,
        L"CSMBHelperClass::CSMBHelperClass Failed");
      v67 = v71;
      guard_dispatch_icall_thunk_10345483385596137414(*((_QWORD *)this + 22));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v67 - 8), 0xFFFFFFFF) <= 1 )
        guard_dispatch_icall_thunk_10345483385596137414(*(_QWORD *)(v67 - 24));
    }
    *((_DWORD *)this + 70) = 1;
    return this;
  }
  return v1;
}

```

## disassembly

```asm
0x180002974  mov     [rsp+arg_0], rcx
0x180002979  push    rbx
0x18000297a  push    rsi
0x18000297b  push    rdi
0x18000297c  push    r12
0x18000297e  push    r13
0x180002980  push    r14
0x180002982  push    r15
0x180002984  sub     rsp, 50h
0x180002988  mov     rdi, rcx
0x18000298b  xor     r12d, r12d
0x18000298e  mov     [rcx+40h], r12d
0x180002992  xorps   xmm0, xmm0
0x180002995  xor     eax, eax
0x180002997  movups  xmmword ptr [rcx+48h], xmm0
0x18000299b  movups  xmmword ptr [rcx+58h], xmm0
0x18000299f  mov     [rcx+68h], rax
0x1800029a3  mov     [rcx+70h], r12b
0x1800029a7  lea     rax, ??_7CNetDiagHelperImpl@@6BINetDiagHelper@@@; const CNetDiagHelperImpl::`vftable'{for `INetDiagHelper'}
0x1800029ae  mov     [rcx], rax
0x1800029b1  lea     rax, ??_7CNetDiagHelperImpl@@6BINetDiagHelperInfo@@@; const CNetDiagHelperImpl::`vftable'{for `INetDiagHelperInfo'}
0x1800029b8  mov     [rcx+8], rax
0x1800029bc  mov     [rcx+14h], r12
0x1800029c0  mov     [rcx+20h], r12
0x1800029c4  mov     [rcx+10h], r12d
0x1800029c8  lea     rax, ??_7CNetDiagHelperExImpl@@6B@; const CNetDiagHelperExImpl::`vftable'
0x1800029cf  mov     [rcx+38h], rax
0x1800029d3  lea     rsi, [rcx+0B8h]
0x1800029da  mov     [rsi], r12
0x1800029dd  mov     [rsi+8], r12
0x1800029e1  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBKPEAVRootCause@@@std@@V?$allocator@U?$pair@$$CBKPEAVRootCause@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKPEAVRootCause@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<ulong const,RootCause *>>>::_Buyheadnode(void)
0x1800029e6  mov     [rsi], rax
0x1800029e9  mov     [rsi+10h], r12
0x1800029ed  lea     r14, [rdi+0D0h]
0x1800029f4  mov     rcx, r14; this
0x1800029f7  call    ??0AttributeList@@QEAA@XZ; AttributeList::AttributeList(void)
0x1800029fc  nop
0x1800029fd  lea     r15, [rdi+0E8h]
0x180002a04  mov     [r15], r12
0x180002a07  mov     [r15+8], r12
0x180002a0b  xor     r8d, r8d
0x180002a0e  xor     edx, edx
0x180002a10  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UAttributeDescriptor@@V?$allocator@UAttributeDescriptor@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UAttributeDescriptor@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<AttributeDescriptor>>::_Buynode0(std::_List_node<AttributeDescriptor,void *> *,std::_List_node<AttributeDescriptor,void *> *)
0x180002a15  mov     [r15], rax
0x180002a18  mov     [rdi+0F8h], r12
0x180002a1f  mov     [rdi+100h], r12
0x180002a26  mov     [rdi+108h], r12
0x180002a2d  mov     [rdi+128h], r12
0x180002a34  lea     rbx, [rdi+0B0h]
0x180002a3b  mov     [rsp+88h+ppv], rbx; ppv
0x180002a40  lea     r9, IID_INDFEtw; riid
0x180002a47  lea     r13d, [r12+1]
0x180002a4c  mov     r8d, r13d; dwClsContext
0x180002a4f  xor     edx, edx; pUnkOuter
0x180002a51  lea     rcx, CLSID_NDFEtw; rclsid
0x180002a58  call    cs:__imp_CoCreateInstance
0x180002a5e  test    eax, eax
0x180002a60  jz      short loc_180002A65
0x180002a62  mov     [rbx], r12
0x180002a65  mov     [rdi+118h], r12
0x180002a6c  mov     [rdi+120h], r12d
0x180002a73  mov     [rdi+78h], r12
0x180002a77  mov     [rdi+80h], r12
0x180002a7e  mov     ecx, 10h
0x180002a83  lea     rax, [rdi+9Ch]
0x180002a8a  mov     [rax], r12b
0x180002a8d  add     rax, r13
0x180002a90  sub     rcx, r13
0x180002a93  jnz     short loc_180002A8A
0x180002a95  mov     ecx, 38h ; '8'; Size
0x180002a9a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002a9f  mov     rbx, rax
0x180002aa2  mov     [rsp+88h+arg_8], rax
0x180002aaa  test    rax, rax
0x180002aad  jz      short loc_180002AEF
0x180002aaf  movups  xmm0, cs:SMBHC_GUID_REPAIR_CHECKFILEPERMISSIONS
0x180002ab6  movdqu  xmmword ptr [rsp+88h+var_48.Data1], xmm0
0x180002abc  lea     r8, [rsp+88h+var_48]; struct _GUID
0x180002ac1  mov     edx, 7Dh ; '}'; unsigned __int16 *
0x180002ac6  mov     rcx, rax; this
0x180002ac9  call    ??0Repair@@QEAA@PEAGU_GUID@@@Z; Repair::Repair(ushort *,_GUID)
0x180002ace  nop
0x180002acf  lea     rax, ??_7FilePermissionRepair@@6B@; const FilePermissionRepair::`vftable'
0x180002ad6  mov     [rbx], rax
0x180002ad9  lea     rcx, [rbx+8]; this
0x180002add  mov     r8d, r13d; unsigned int
0x180002ae0  lea     rdx, aContactadmin; "ContactAdmin"
0x180002ae7  call    ?setDWordAttribute@AttributeList@@QEAAXPEAGK@Z; AttributeList::setDWordAttribute(ushort *,ulong)
0x180002aec  nop
0x180002aed  jmp     short loc_180002AF2
0x180002aef  mov     rbx, r12
0x180002af2  lea     rcx, [rbx+8]; this
0x180002af6  lea     r8, aMshelpWindowsI; "mshelp://Windows/?id=089a542f-c717-442e"...
0x180002afd  lea     rdx, aHelplinkurl; "HelpLinkURL"
0x180002b04  call    ?setStringAttribute@AttributeList@@QEAAXPEAG0@Z; AttributeList::setStringAttribute(ushort *,ushort *)
0x180002b09  mov     r8d, r13d; unsigned int
0x180002b0c  lea     rdx, aImpersonationr; "ImpersonationRequired"
0x180002b13  mov     rcx, r14; this
0x180002b16  call    ?setDWordAttribute@AttributeList@@QEAAXPEAGK@Z; AttributeList::setDWordAttribute(ushort *,ulong)
0x180002b1b  xorps   xmm0, xmm0
0x180002b1e  movups  xmmword ptr [rsp+88h+var_48.Data1], xmm0
0x180002b23  mov     ecx, 10h; unsigned __int64
0x180002b28  call    ?AllocateTestMemory@@YAPEAX_K@Z; AllocateTestMemory(unsigned __int64)
0x180002b2d  mov     qword ptr [rsp+88h+var_48.Data1], rax
0x180002b32  mov     dword ptr [rsp+88h+var_48.Data4], r13d
0x180002b37  lea     r8, aUncpath; "UNCPath"
0x180002b3e  mov     edx, 8; unsigned __int64
0x180002b43  mov     rcx, rax; unsigned __int16 *
0x180002b46  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180002b4b  mov     r14, [r15]
0x180002b4e  lea     r9, [rsp+88h+var_48]
0x180002b53  mov     r8, [r14+8]
0x180002b57  mov     rdx, r14
0x180002b5a  call    ??$_Buynode@AEBUAttributeDescriptor@@@?$_List_buy@UAttributeDescriptor@@V?$allocator@UAttributeDescriptor@@@std@@@std@@QEAAPEAU?$_List_node@UAttributeDescriptor@@PEAX@1@PEAU21@0AEBUAttributeDescriptor@@@Z; std::_List_buy<AttributeDescriptor>::_Buynode<AttributeDescriptor const &>(std::_List_node<AttributeDescriptor,void *> *,std::_List_node<AttributeDescriptor,void *> *,AttributeDescriptor const &)
0x180002b5f  mov     rdx, rax
0x180002b62  mov     rax, [r15+8]
0x180002b66  mov     rcx, 7FFFFFFFFFFFFFEh
0x180002b70  sub     rcx, rax
0x180002b73  cmp     rcx, r13
0x180002b76  jb      loc_18000358C
0x180002b7c  inc     rax
0x180002b7f  mov     [r15+8], rax
0x180002b83  mov     [r14+8], rdx
0x180002b87  mov     rax, [rdx+8]
0x180002b8b  mov     [rax], rdx
0x180002b8e  mov     r15d, 28h ; '('
0x180002b94  mov     ecx, r15d; Size
0x180002b97  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002b9c  mov     [rsp+88h+arg_8], rax
0x180002ba4  test    rax, rax
0x180002ba7  jz      short loc_180002BC9
0x180002ba9  movups  xmm0, cs:SMBHC_GUID_RC_CONNECTIVITY_FAILURE
0x180002bb0  movdqu  xmmword ptr [rsp+88h+var_48.Data1], xmm0
0x180002bb6  lea     r8, [rsp+88h+var_48]; struct _GUID
0x180002bbb  lea     edx, [r15+4Ah]; unsigned __int16 *
0x180002bbf  mov     rcx, rax; this
0x180002bc2  call    ??0RootCause@@QEAA@PEAGU_GUID@@@Z; RootCause::RootCause(ushort *,_GUID)
0x180002bc7  jmp     short loc_180002BCC
0x180002bc9  mov     rax, r12
0x180002bcc  mov     r8, rax; struct RootCause *
0x180002bcf  xor     edx, edx; unsigned int
0x180002bd1  mov     rcx, rsi; this
0x180002bd4  call    ?addRootCause@RootCauseList@@QEAAXKPEAVRootCause@@@Z; RootCauseList::addRootCause(ulong,RootCause *)
0x180002bd9  mov     rcx, r15; Size
0x180002bdc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002be1  mov     [rsp+88h+arg_8], rax
0x180002be9  test    rax, rax
0x180002bec  jz      short loc_180002C0F
0x180002bee  movups  xmm0, cs:SMBHC_GUID_RC_SERVER_FAILURE
0x180002bf5  movdqu  xmmword ptr [rsp+88h+var_48.Data1], xmm0
0x180002bfb  lea     r8, [rsp+88h+var_48]; struct _GUID
0x180002c00  mov     edx, 72h ; 'r'; unsigned __int16 *
0x180002c05  mov     rcx, rax; this
0x180002c08  call    ??0RootCause@@QEAA@PEAGU_GUID@@@Z; RootCause::RootCause(ushort *,_GUID)
0x180002c0d  jmp     short loc_180002C12
0x180002c0f  mov     rax, r12
0x180002c12  mov     r8, rax; struct RootCause *
0x180002c15  mov     edx, 4; unsigned int
0x180002c1a  mov     rcx, rsi; this
0x180002c1d  call    ?addRootCause@RootCauseList@@QEAAXKPEAVRootCause@@@Z; RootCauseList::addRootCause(ulong,RootCause *)
0x180002c22  mov     rcx, r15; Size
0x180002c25  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002c2a  mov     [rsp+88h+arg_8], rax
0x180002c32  test    rax, rax
0x180002c35  jz      short loc_180002C58
0x180002c37  movups  xmm0, cs:SMBHC_GUID_RC_FILE_PERMISSION_FAILURE
0x180002c3e  movdqu  xmmword ptr [rsp+88h+var_48.Data1], xmm0
0x180002c44  lea     r8, [rsp+88h+var_48]; struct _GUID
0x180002c49  mov     edx, 78h ; 'x'; unsigned __int16 *
0x180002c4e  mov     rcx, rax; this
0x180002c51  call    ??0RootCause@@QEAA@PEAGU_GUID@@@Z; RootCause::RootCause(ushort *,_GUID)
0x180002c56  jmp     short loc_180002C5B
0x180002c58  mov     rax, r12
0x180002c5b  mov     r8, rax; struct RootCause *
0x180002c5e  mov     r14d, 7
0x180002c64  mov     edx, r14d; unsigned int
0x180002c67  mov     rcx, rsi; this
0x180002c6a  call    ?addRootCause@RootCauseList@@QEAAXKPEAVRootCause@@@Z; RootCauseList::addRootCause(ulong,RootCause *)
0x180002c6f  mov     edx, r14d; unsigned int
0x180002c72  mov     rcx, rsi; this
0x180002c75  call    ?getRootCause@RootCauseList@@QEAAPEAVRootCause@@K@Z; RootCauseList::getRootCause(ulong)
0x180002c7a  mov     rdx, rbx; struct Repair *
0x180002c7d  mov     rcx, rax; this
0x180002c80  call    ?addRepair@RootCause@@QEAAXPEAVRepair@@@Z; RootCause::addRepair(Repair *)
0x180002c85  mov     rcx, r15; Size
0x180002c88  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002c8d  mov     [rsp+88h+arg_8], rax
0x180002c95  test    rax, rax
0x180002c98  jz      short loc_180002CBA
0x180002c9a  movups  xmm0, cs:SMBHC_GUID_RC_FILE_CONNECT_FAILURE
0x180002ca1  movdqu  xmmword ptr [rsp+88h+var_48.Data1], xmm0
0x180002ca7  lea     r8, [rsp+88h+var_48]; struct _GUID
0x180002cac  lea     edx, [r14+70h]; unsigned __int16 *
0x180002cb0  mov     rcx, rax; this
0x180002cb3  call    ??0RootCause@@QEAA@PEAGU_GUID@@@Z; RootCause::RootCause(ushort *,_GUID)
0x180002cb8  jmp     short loc_180002CBD
0x180002cba  mov     rax, r12
0x180002cbd  mov     r8, rax; struct RootCause *
0x180002cc0  mov     edx, 8; unsigned int
0x180002cc5  mov     rcx, rsi; this
0x180002cc8  call    ?addRootCause@RootCauseList@@QEAAXKPEAVRootCause@@@Z; RootCauseList::addRootCause(ulong,RootCause *)
0x180002ccd  mov     edx, 8; unsigned int
0x180002cd2  mov     rcx, rsi; this
0x180002cd5  call    ?getRootCause@RootCauseList@@QEAAPEAVRootCause@@K@Z; RootCauseList::getRootCause(ulong)
0x180002cda  mov     r14, rax
0x180002cdd  mov     ecx, 38h ; '8'; Size
0x180002ce2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002ce7  mov     rbx, rax
0x180002cea  mov     [rsp+88h+arg_8], rax
0x180002cf2  test    rax, rax
0x180002cf5  jz      short loc_180002D37
0x180002cf7  movups  xmm0, cs:SMBHC_GUID_REPAIR_CHECKFILEPATH
0x180002cfe  movdqu  xmmword ptr [rsp+88h+var_48.Data1], xmm0
0x180002d04  lea     r8, [rsp+88h+var_48]; struct _GUID
0x180002d09  mov     edx, 7Ch ; '|'; unsigned __int16 *
0x180002d0e  mov     rcx, rax; this
0x180002d11  call    ??0Repair@@QEAA@PEAGU_GUID@@@Z; Repair::Repair(ushort *,_GUID)
0x180002d16  nop
0x180002d17  lea     rax, ??_7CheckPathRepair@@6B@; const CheckPathRepair::`vftable'
0x180002d1e  mov     [rbx], rax
0x180002d21  lea     rcx, [rbx+8]; this
0x180002d25  mov     r8d, r13d; unsigned int
0x180002d28  lea     rdx, aInformational; "Informational"
0x180002d2f  call    ?setDWordAttribute@AttributeList@@QEAAXPEAGK@Z; AttributeList::setDWordAttribute(ushort *,ulong)
0x180002d34  nop
0x180002d35  jmp     short loc_180002D3A
0x180002d37  mov     rbx, r12
0x180002d3a  mov     rdx, rbx; struct Repair *
0x180002d3d  mov     rcx, r14; this
0x180002d40  call    ?addRepair@RootCause@@QEAAXPEAVRepair@@@Z; RootCause::addRepair(Repair *)
0x180002d45  mov     rcx, r15; Size
0x180002d48  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002d4d  mov     [rsp+88h+arg_8], rax
0x180002d55  test    rax, rax
0x180002d58  jz      short loc_180002D7B
0x180002d5a  movups  xmm0, cs:SMBHC_GUID_RC_SHARE_CONNECT_FAILURE
0x180002d61  movdqu  xmmword ptr [rsp+88h+var_48.Data1], xmm0
0x180002d67  lea     r8, [rsp+88h+var_48]; struct _GUID
0x180002d6c  mov     edx, 74h ; 't'; unsigned __int16 *
0x180002d71  mov     rcx, rax; this
0x180002d74  call    ??0RootCause@@QEAA@PEAGU_GUID@@@Z; RootCause::RootCause(ushort *,_GUID)
0x180002d79  jmp     short loc_180002D7E
0x180002d7b  mov     rax, r12
0x180002d7e  mov     r8, rax; struct RootCause *
0x180002d81  mov     ebx, 6
0x180002d86  mov     edx, ebx; unsigned int
0x180002d88  mov     rcx, rsi; this
0x180002d8b  call    ?addRootCause@RootCauseList@@QEAAXKPEAVRootCause@@@Z; RootCauseList::addRootCause(ulong,RootCause *)
0x180002d90  mov     edx, ebx; unsigned int
0x180002d92  mov     rcx, rsi; this
0x180002d95  call    ?getRootCause@RootCauseList@@QEAAPEAVRootCause@@K@Z; RootCauseList::getRootCause(ulong)
0x180002d9a  mov     r14, rax
0x180002d9d  lea     ecx, [rbx+32h]; Size
0x180002da0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002da5  mov     rbx, rax
0x180002da8  mov     [rsp+88h+arg_8], rax
0x180002db0  test    rax, rax
0x180002db3  jz      short loc_180002DF5
0x180002db5  movups  xmm0, cs:SMBHC_GUID_REPAIR_CHECKSHARE
0x180002dbc  movdqu  xmmword ptr [rsp+88h+var_48.Data1], xmm0
0x180002dc2  lea     r8, [rsp+88h+var_48]; struct _GUID
0x180002dc7  mov     edx, 7Ah ; 'z'; unsigned __int16 *
0x180002dcc  mov     rcx, rax; this
0x180002dcf  call    ??0Repair@@QEAA@PEAGU_GUID@@@Z; Repair::Repair(ushort *,_GUID)
0x180002dd4  nop
0x180002dd5  lea     rax, ??_7CheckShareRepair@@6B@; const CheckShareRepair::`vftable'
0x180002ddc  mov     [rbx], rax
0x180002ddf  lea     rcx, [rbx+8]; this
0x180002de3  mov     r8d, r13d; unsigned int
0x180002de6  lea     rdx, aInformational; "Informational"
0x180002ded  call    ?setDWordAttribute@AttributeList@@QEAAXPEAGK@Z; AttributeList::setDWordAttribute(ushort *,ulong)
0x180002df2  nop
0x180002df3  jmp     short loc_180002DF8
0x180002df5  mov     rbx, r12
0x180002df8  mov     rdx, rbx; struct Repair *
0x180002dfb  mov     rcx, r14; this
0x180002dfe  call    ?addRepair@RootCause@@QEAAXPEAVRepair@@@Z; RootCause::addRepair(Repair *)
0x180002e03  mov     rcx, r15; Size
0x180002e06  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002e0b  mov     [rsp+88h+arg_8], rax
0x180002e13  test    rax, rax
0x180002e16  jz      short loc_180002E39
0x180002e18  movups  xmm0, cs:SMBHC_GUID_RC_SHAREMAXCONNECTIONS_FAILURE
0x180002e1f  movdqu  xmmword ptr [rsp+88h+var_48.Data1], xmm0
0x180002e25  lea     r8, [rsp+88h+var_48]; struct _GUID
0x180002e2a  mov     edx, 80h; unsigned __int16 *
0x180002e2f  mov     rcx, rax; this
0x180002e32  call    ??0RootCause@@QEAA@PEAGU_GUID@@@Z; RootCause::RootCause(ushort *,_GUID)
0x180002e37  jmp     short loc_180002E3C
0x180002e39  mov     rax, r12
0x180002e3c  mov     r8, rax; struct RootCause *
0x180002e3f  mov     ebx, 0Bh
0x180002e44  mov     edx, ebx; unsigned int
0x180002e46  mov     rcx, rsi; this
0x180002e49  call    ?addRootCause@RootCauseList@@QEAAXKPEAVRootCause@@@Z; RootCauseList::addRootCause(ulong,RootCause *)
0x180002e4e  mov     edx, ebx; unsigned int
0x180002e50  mov     rcx, rsi; this
0x180002e53  call    ?getRootCause@RootCauseList@@QEAAPEAVRootCause@@K@Z; RootCauseList::getRootCause(ulong)
0x180002e58  mov     r14, rax
0x180002e5b  lea     ecx, [rbx+2Dh]; Size
  ... truncated ...
```
