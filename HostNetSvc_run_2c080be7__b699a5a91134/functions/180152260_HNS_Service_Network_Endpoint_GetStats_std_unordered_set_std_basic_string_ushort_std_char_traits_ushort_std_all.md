# HNS::Service::Network::Endpoint::GetStats(std::unordered_set<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &,wil::com_ptr_t<HNSObject,wil::err_exception_policy> &)

- ea: `0x180152260`
- end: `0x1801548ef`
- name: `?GetStats@Endpoint@Network@Service@HNS@@QEAAXAEBV?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAV?$com_ptr_t@VHNSObject@@Uerr_exception_policy@wil@@@wil@@@Z`
- size: `9871`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800c7cf4`

## callees

- `0x18005f0c0`
- `0x18005ffa0`
- `0x18005ffc4`
- `0x1800666b4`
- `0x180067c00`
- `0x18006c530`
- `0x1800759d8`
- `0x180075aac`
- `0x18007f05c`
- `0x18007f21c`
- `0x1800a29f4`
- `0x1800b5c7c`
- `0x1800d4834`
- `0x1800d4ae8`
- `0x180114da8`
- `0x180119848`
- `0x180151ac0`
- `0x180152260`
- `0x18015cd44`
- `0x18019c4d4`
- `0x18019dcb8`
- `0x1801cf0d4`
- `0x1802447fc`
- `0x18028aad0`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1801522d8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1801522d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180154898`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180154898`
- `NetMgmtIF!NetMgmtGetNicStats` at `0x180152400`
- `NetMgmtIF!NetMgmtGetNicStats` at `0x180152400`
- `RPCRT4!UuidCreate` at `0x1801524f6`
- `RPCRT4!UuidCreate` at `0x1801524f6`

## string_xrefs

- `0x1801522c0`: `HNS::Service::Network::Endpoint::GetStats`
- `0x1801548a3`: `HNS::Service::Network::Endpoint::GetStats`
- `0x1801528b2`: `DroppedPacketsIncoming`
- `0x18015320a`: `TcpHalfOpenTimeoutsIn`
- `0x18015408e`: `TcpHalfOpenTimeoutsIn`
- `0x18015332d`: `DropAclIn`
- `0x180154198`: `DropAclIn`
- `0x180153907`: `TcpHalfOpenTimeoutsOut`
- `0x1801546bf`: `TcpHalfOpenTimeoutsOut`
- `0x180153a2a`: `DropAclOut`
- `0x1801547c5`: `DropAclOut`
- `0x1801548dd`: `onecore\vm\dv\net\hns\service\common\helperlib\src\switchhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=61
void __fastcall HNS::Service::Network::Endpoint::GetStats(VfpPort *a1, __int64 a2, __int64 *a3)
{
  __int64 *v3; // rsi
  RTL_SRWLOCK *v4; // rdi
  char v5; // r13
  volatile signed __int32 *Ptr; // rax
  struct _GUID *EndpointNicGuid; // rax
  __int64 v8; // rax
  __int128 *v9; // rbx
  int NicStats; // eax
  _QWORD *v11; // rcx
  volatile signed __int32 *v12; // rax
  volatile signed __int32 *v13; // rbx
  __int64 v14; // rbx
  __int64 v15; // rbx
  _QWORD *v16; // rax
  __int64 v17; // rbx
  char v18; // bl
  __int64 v19; // rbx
  __int64 v20; // rbx
  __int64 v21; // rbx
  __int64 v22; // rbx
  VfpPort *v23; // rbx
  __int64 v24; // rdi
  VfpPort *v25; // rbx
  __int64 v26; // rdi
  _QWORD *PortResource; // rax
  volatile signed __int32 *v28; // rbx
  __int64 v29; // rbx
  __int64 v30; // rbx
  __int64 v31; // rbx
  __int64 v32; // rbx
  __int64 v33; // rbx
  __int64 v34; // rbx
  volatile signed __int32 *v35; // rbx
  _QWORD *v36; // rax
  volatile signed __int32 *v37; // rbx
  __int64 v38; // rbx
  __int64 v39; // rbx
  __int64 v40; // rbx
  __int64 v41; // rbx
  __int64 v42; // rbx
  __int64 v43; // rbx
  __int64 v44; // rbx
  __int64 v45; // rbx
  __int64 v46; // rbx
  __int64 v47; // rbx
  __int64 v48; // rbx
  __int64 v49; // rbx
  __int64 v50; // rdi
  __int64 v51; // rdi
  __int64 v52; // rdi
  __int64 v53; // rdi
  __int64 v54; // rbx
  __int64 v55; // rbx
  __int64 v56; // rbx
  __int64 v57; // rbx
  __int64 v58; // rbx
  __int64 v59; // rbx
  __int64 v60; // rbx
  __int64 v61; // rbx
  volatile signed __int32 *v62; // rbx
  HNSObject *v63; // rbx
  int v64; // [rsp+20h] [rbp-1108h]
  bool VfpPortCounters; // [rsp+30h] [rbp-10F8h] BYREF
  __int64 *v66; // [rsp+38h] [rbp-10F0h] BYREF
  __int64 v67; // [rsp+40h] [rbp-10E8h]
  HNSObject *v68; // [rsp+48h] [rbp-10E0h]
  HNSObject *v69; // [rsp+50h] [rbp-10D8h]
  VfpPort *v70; // [rsp+58h] [rbp-10D0h] BYREF
  volatile signed __int32 *v71; // [rsp+60h] [rbp-10C8h]
  PSRWLOCK SRWLock; // [rsp+68h] [rbp-10C0h]
  RTL_SRWLOCK *v73; // [rsp+70h] [rbp-10B8h]
  volatile signed __int32 *v74; // [rsp+78h] [rbp-10B0h]
  _BYTE v75[24]; // [rsp+80h] [rbp-10A8h] BYREF
  __int64 *v76; // [rsp+98h] [rbp-1090h]
  __int64 *v77; // [rsp+A0h] [rbp-1088h]
  __int64 *v78; // [rsp+138h] [rbp-FF0h]
  __int64 *v79; // [rsp+190h] [rbp-F98h]
  __int64 *v80; // [rsp+198h] [rbp-F90h]
  __int64 *v81; // [rsp+1A0h] [rbp-F88h]
  __int64 *v82; // [rsp+1A8h] [rbp-F80h]
  __int64 *v83; // [rsp+1B0h] [rbp-F78h]
  __int64 *v84; // [rsp+1B8h] [rbp-F70h]
  __int64 *v85; // [rsp+1C0h] [rbp-F68h]
  __int64 *v86; // [rsp+1C8h] [rbp-F60h]
  __int64 *v87; // [rsp+1D0h] [rbp-F58h]
  _BYTE v88[24]; // [rsp+6A0h] [rbp-A88h] BYREF
  __int64 *v89; // [rsp+6B8h] [rbp-A70h]
  __int64 *v90; // [rsp+6C0h] [rbp-A68h]
  __int64 *v91; // [rsp+758h] [rbp-9D0h]
  __int64 *v92; // [rsp+7B0h] [rbp-978h]
  __int64 *v93; // [rsp+7B8h] [rbp-970h]
  __int64 *v94; // [rsp+7C0h] [rbp-968h]
  __int64 *v95; // [rsp+7C8h] [rbp-960h]
  __int64 *v96; // [rsp+7D0h] [rbp-958h]
  __int64 *v97; // [rsp+7D8h] [rbp-950h]
  __int64 *v98; // [rsp+7E0h] [rbp-948h]
  __int64 *v99; // [rsp+7E8h] [rbp-940h]
  __int64 *v100; // [rsp+7F0h] [rbp-938h]
  _OWORD v101[2]; // [rsp+CC0h] [rbp-468h] BYREF
  VfpPort *v102[2]; // [rsp+CE0h] [rbp-448h] BYREF
  struct _GUID v103; // [rsp+CF0h] [rbp-438h] BYREF
  __int128 v104; // [rsp+D00h] [rbp-428h] BYREF
  __int128 v105; // [rsp+D10h] [rbp-418h] BYREF
  __int128 v106; // [rsp+D20h] [rbp-408h]
  _OWORD v107[2]; // [rsp+D30h] [rbp-3F8h] BYREF
  __int128 v108; // [rsp+D50h] [rbp-3D8h] BYREF
  __int128 v109; // [rsp+D60h] [rbp-3C8h]
  __int128 v110; // [rsp+D70h] [rbp-3B8h] BYREF
  __int64 v111; // [rsp+D80h] [rbp-3A8h]
  unsigned __int64 v112; // [rsp+D88h] [rbp-3A0h]
  __int128 v113; // [rsp+D90h] [rbp-398h] BYREF
  __int128 v114; // [rsp+DA0h] [rbp-388h]
  __int128 v115; // [rsp+DB0h] [rbp-378h] BYREF
  __int128 v116; // [rsp+DC0h] [rbp-368h]
  __int128 v117; // [rsp+DD0h] [rbp-358h] BYREF
  __int128 v118; // [rsp+DE0h] [rbp-348h]
  __int128 v119; // [rsp+DF0h] [rbp-338h] BYREF
  __int128 v120; // [rsp+E00h] [rbp-328h]
  __int128 v121; // [rsp+E10h] [rbp-318h] BYREF
  __int128 v122; // [rsp+E20h] [rbp-308h]
  __int128 v123; // [rsp+E30h] [rbp-2F8h] BYREF
  __int128 v124; // [rsp+E40h] [rbp-2E8h]
  __int128 v125; // [rsp+E50h] [rbp-2D8h] BYREF
  __int128 v126; // [rsp+E60h] [rbp-2C8h]
  __int128 v127; // [rsp+E70h] [rbp-2B8h] BYREF
  __int128 v128; // [rsp+E80h] [rbp-2A8h]
  __int128 v129; // [rsp+E90h] [rbp-298h] BYREF
  __int128 v130; // [rsp+EA0h] [rbp-288h]
  __int128 v131; // [rsp+EB0h] [rbp-278h] BYREF
  __int128 v132; // [rsp+EC0h] [rbp-268h]
  __int128 v133; // [rsp+ED0h] [rbp-258h] BYREF
  __int128 v134; // [rsp+EE0h] [rbp-248h]
  __int128 v135; // [rsp+EF0h] [rbp-238h] BYREF
  __int128 v136; // [rsp+F00h] [rbp-228h]
  __int128 v137; // [rsp+F10h] [rbp-218h] BYREF
  __int128 v138; // [rsp+F20h] [rbp-208h]
  __int128 v139; // [rsp+F30h] [rbp-1F8h] BYREF
  __int128 v140; // [rsp+F40h] [rbp-1E8h]
  __int128 v141; // [rsp+F50h] [rbp-1D8h] BYREF
  __int128 v142; // [rsp+F60h] [rbp-1C8h]
  __int128 v143; // [rsp+F70h] [rbp-1B8h] BYREF
  __int128 v144; // [rsp+F80h] [rbp-1A8h]
  __int128 v145; // [rsp+F90h] [rbp-198h] BYREF
  __int128 v146; // [rsp+FA0h] [rbp-188h]
  __int128 v147; // [rsp+FB0h] [rbp-178h] BYREF
  __int128 v148; // [rsp+FC0h] [rbp-168h]
  __int128 v149; // [rsp+FD0h] [rbp-158h] BYREF
  __int128 v150; // [rsp+FE0h] [rbp-148h]
  __int128 v151; // [rsp+FF0h] [rbp-138h] BYREF
  __int128 v152; // [rsp+1000h] [rbp-128h]
  __int128 v153; // [rsp+1010h] [rbp-118h] BYREF
  __int128 v154; // [rsp+1020h] [rbp-108h]
  _QWORD v155[14]; // [rsp+1030h] [rbp-F8h] BYREF
  UUID Uuid; // [rsp+10A0h] [rbp-88h] BYREF
  __int128 v157; // [rsp+10B0h] [rbp-78h]
  bool *p_VfpPortCounters; // [rsp+10C0h] [rbp-68h]
  __int64 v159; // [rsp+10C8h] [rbp-60h]
  wil::details::in1diag3 *retaddr; // [rsp+1128h] [rbp+0h]

  v3 = a3;
  v67 = a2;
  v4 = (RTL_SRWLOCK *)a1;
  *(_QWORD *)&v101[0] = a1;
  v70 = a1;
  v66 = a3;
  v5 = 0;
  LODWORD(v68) = 0;
  HNSTraceProvider::TraceEnter("HNS::Service::Network::Endpoint::GetStats", 0x9F7u);
  SRWLock = v4 + 5;
  AcquireSRWLockShared(v4 + 5);
  v73 = v4 + 5;
  HNS::Service::Interface::IEntity::ValidateAndThrow((HNS::Service::Interface::IEntity *)v4);
  memset_0(v155, 0, sizeof(v155));
  Ptr = (volatile signed __int32 *)v4[1].Ptr;
  v68 = (HNSObject *)Ptr;
  v69 = (HNSObject *)Ptr;
  v74 = Ptr;
  if ( Ptr )
    _InterlockedAdd(Ptr + 4, 1u);
  v110 = 0;
  v111 = 0;
  v112 = 7;
  LOWORD(v110) = 0;
  EndpointNicGuid = HNS::Service::Network::Endpoint::GetEndpointNicGuid((HNS::Service::Network::Endpoint *)v4, &v103);
  if ( !memcmp_0(EndpointNicGuid, &GUID_NULL, 0x10u) )
  {
    v11 = v4[233].Ptr;
    if ( v11 )
    {
      v12 = (volatile signed __int32 *)v4[234].Ptr;
      if ( v12 )
        _InterlockedAdd(v12 + 2, 1u);
      v13 = (volatile signed __int32 *)v4[234].Ptr;
      HNSObject::Get<std::wstring>(v11[287], &v108, v11 + 280);
      v5 = 4;
      std::wstring::operator=(&v110, &v108);
      std::wstring::~wstring(&v108);
      if ( v13 )
      {
        if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
          if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
        }
      }
    }
  }
  else
  {
    HNS::Service::Network::Endpoint::GetEndpointNicGuid((HNS::Service::Network::Endpoint *)v4, &Uuid);
    v8 = GuidToString(&v108, &Uuid, 0);
    std::wstring::operator=(&v110, v8);
    std::wstring::~wstring(&v108);
  }
  if ( v111 )
  {
    v9 = &v110;
    if ( v112 > 7 )
      v9 = (__int128 *)v110;
    HNSTraceProvider::TraceEnter("HNS::GetNicStats", 0x424u);
    NicStats = NetMgmtGetNicStats(v9, v155);
    if ( NicStats < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x428,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\switchhelper.cpp",
        (const char *)(unsigned int)NicStats,
        v64);
    HNSTraceProvider::TraceSuccess("HNS::GetNicStats", 0x42Au);
  }
  Uuid = 0;
  UuidCreate(&Uuid);
  *(UUID *)v102 = Uuid;
  v14 = *v3;
  v103 = 0;
  v104 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v103, L"InstanceId");
  Uuid = GUID_NULL;
  HNSObject::Set<_GUID>(v14, &v103, v102, 18);
  std::wstring::~wstring(&v103);
  Uuid = 0;
  v157 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&Uuid, L"ID");
  *(_OWORD *)v102 = *(_OWORD *)HNSObject::GetGuid(v68, &v103, &Uuid);
  std::wstring::~wstring(&Uuid);
  v15 = *v3;
  v103 = 0;
  v104 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v103, L"EndpointId");
  Uuid = GUID_NULL;
  HNSObject::Set<_GUID>(v15, &v103, v102, 18);
  std::wstring::~wstring(&v103);
  v103 = 0;
  v104 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v103, L"/all");
  v16 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<HNS::Service::Resource::IpsetData>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<HNS::Service::Resource::IpsetData>>>,0>>::find(
                    v67,
                    v102,
                    &v103);
  *(_QWORD *)&Uuid.Data1 = *(_QWORD *)(v67 + 8);
  v17 = *(_QWORD *)&Uuid.Data1;
  *(_QWORD *)&v107[0] = *v16;
  std::wstring::~wstring(&v103);
  if ( *(_QWORD *)&v107[0] == v17 )
  {
    v103 = 0;
    v104 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v103, L"/hns");
    v18 = 1;
    v5 |= 1u;
    if ( *(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<HNS::Service::Resource::IpsetData>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<HNS::Service::Resource::IpsetData>>>,0>>::find(
                      v67,
                      v102,
                      &v103) == *(_QWORD *)(v67 + 8) )
    {
      VfpPortCounters = 0;
      goto LABEL_22;
    }
  }
  else
  {
    v18 = 1;
  }
  VfpPortCounters = 1;
LABEL_22:
  if ( (v5 & 1) != 0 )
  {
    v5 &= ~1u;
    std::wstring::~wstring(&v103);
  }
  if ( VfpPortCounters )
  {
    v19 = *v3;
    v105 = 0;
    v106 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v105, L"BytesReceived");
    v102[0] = (VfpPort *)v155[0];
    v103 = GUID_NULL;
    HNSObject::Set<unsigned __int64>(v19, &v105, v102, 18);
    std::wstring::~wstring(&v105);
    v20 = *v3;
    v105 = 0;
    v106 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v105, L"BytesSent");
    v102[0] = (VfpPort *)v155[1];
    v103 = GUID_NULL;
    HNSObject::Set<unsigned __int64>(v20, &v105, v102, 18);
    std::wstring::~wstring(&v105);
    v21 = *v3;
    v105 = 0;
    v106 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v105, L"DroppedPacketsIncoming");
    v102[0] = (VfpPort *)v155[10];
    v103 = GUID_NULL;
    HNSObject::Set<unsigned __int64>(v21, &v105, v102, 18);
    std::wstring::~wstring(&v105);
    v22 = *v3;
    v105 = 0;
    v106 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v105, L"DroppedPacketsOutgoing");
    v102[0] = (VfpPort *)v155[11];
    v103 = GUID_NULL;
    HNSObject::Set<unsigned __int64>(v22, &v105, v102, 18);
    std::wstring::~wstring(&v105);
    *(_QWORD *)&v103.Data1 = v155[2];
    *(_QWORD *)v103.Data4 = v155[4];
    *(_QWORD *)&v104 = v155[6];
    v102[0] = (VfpPort *)&v103;
    v102[1] = (VfpPort *)((char *)&v104 + 8);
    v23 = (VfpPort *)MathHelper::SafeAdd(v102);
    v24 = *v3;
    v105 = 0;
    v106 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v105, L"PacketsReceived");
    v102[0] = v23;
    v103 = GUID_NULL;
    HNSObject::Set<unsigned __int64>(v24, &v105, v102, 18);
    std::wstring::~wstring(&v105);
    *(_QWORD *)&v103.Data1 = v155[3];
    *(_QWORD *)v103.Data4 = v155[5];
    *(_QWORD *)&v104 = v155[7];
    v102[0] = (VfpPort *)&v103;
    v102[1] = (VfpPort *)((char *)&v104 + 8);
    v25 = (VfpPort *)MathHelper::SafeAdd(v102);
    v26 = *v3;
    v105 = 0;
    v106 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v105, L"PacketsSent");
    v102[0] = v25;
    v103 = GUID_NULL;
    HNSObject::Set<unsigned __int64>(v26, &v105, v102, 18);
    std::wstring::~wstring(&v105);
    v4 = *(RTL_SRWLOCK **)&v101[0];
    v18 = 1;
  }
  if ( *(_QWORD *)&v107[0] == *(_QWORD *)&Uuid.Data1 )
  {
    v105 = 0;
    v106 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v105, L"/vfp");
    v5 |= 2u;
    if ( *(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<HNS::Service::Resource::IpsetData>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<HNS::Service::Resource::IpsetData>>>,0>>::find(
                      v67,
                      &Uuid,
                      &v105) == *(_QWORD *)(v67 + 8) )
      v18 = 0;
  }
  if ( (v5 & 2) != 0 )
    std::wstring::~wstring(&v105);
  if ( v18 )
  {
    VfpPortCounters = 0;
    try
    {
      PortResource = (_QWORD *)HNS::Service::Network::Endpoint::GetPortResource(v4, &v103);
      HNS::Service::Resource::PortResource::GetVFPPort(*PortResource, v102);
      v28 = *(volatile signed __int32 **)v103.Data4;
      if ( *(_QWORD *)v103.Data4 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)v103.Data4 + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
          if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
        }
      }
      memset_0(v75, -1, 0x620u);
      memset_0(v88, -1, 0x620u);
      if ( v102[0] )
      {
        VfpPortCounters = VfpPort::GetVfpPortCounters(
                            v102[0],
                            (struct _VFX_PORT_COUNTER_EX4 *)v75,
                            (struct _VFX_PORT_COUNTER_EX4 *)v88);
        if ( VfpPortCounters )
        {
          v29 = *v3;
          v105 = 0;
          v106 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v105, L"SynPacketsIn");
          *(_QWORD *)&Uuid.Data1 = v76;
          v101[0] = GUID_NULL;
          HNSObject::Set<unsigned __int64>(v29, &v105, &Uuid, 18);
          std::wstring::~wstring(&v105);
          v30 = *v3;
          v113 = 0;
          v114 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v113, L"SynAckPacketsIn");
          *(_QWORD *)&Uuid.Data1 = v77;
          v101[0] = GUID_NULL;
          HNSObject::Set<unsigned __int64>(v30, &v113, &Uuid, 18);
          std::wstring::~wstring(&v113);
          v31 = *v3;
          v115 = 0;
          v116 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v115, L"FinPacketsIn");
          *(_QWORD *)&Uuid.Data1 = v83;
          v101[0] = GUID_NULL;
          HNSObject::Set<unsigned __int64>(v31, &v115, &Uuid, 18);
          std::wstring::~wstring(&v115);
          v32 = *v3;
          v117 = 0;
          v118 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v117, L"RstPacketsIn");
          *(_QWORD *)&Uuid.Data1 = v82;
          v101[0] = GUID_NULL;
          HNSObject::Set<unsigned __int64>(v32, &v117, &Uuid, 18);
          std::wstring::~wstring(&v117);
          *(_QWORD *)&v101[0] = *v3;
          v119 = 0;
          v120 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v119, L"TcpConnectionsVerifiedIn");
          *(_QWORD *)&Uuid.Data1 = v79;
          v107[0] = GUID_NULL;
          HNSObject::Set<unsigned __int64>(*(_QWORD *)&v101[0], &v119, &Uuid, 18);
          std::wstring::~wstring(&v119);
          *(_QWORD *)&v101[0] = *v3;
          v153 = 0;
          v154 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v153, L"TcpConnectionsTimedOutIn");
          *(_QWORD *)&Uuid.Data1 = v85;
          v107[0] = GUID_NULL;
          HNSObject::Set<unsigned __int64>(*(_QWORD *)&v101[0], &v153, &Uuid, 18);
          std::wstring::~wstring(&v153);
          *(_QWORD *)&v101[0] = *v3;
          v151 = 0;
          v152 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v151, L"TcpConnectionsResetIn");
          *(_QWORD *)&Uuid.Data1 = v81;
          v107[0] = GUID_NULL;
          HNSObject::Set<unsigned __int64>(*(_QWORD *)&v101[0], &v151, &Uuid, 18);
          std::wstring::~wstring(&v151);
          *(_QWORD *)&v101[0] = *v3;
          v121 = 0;
          v122 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v121, L"TcpConnectionsResetBySynIn");
          *(_QWORD *)&Uuid.Data1 = v84;
          v107[0] = GUID_NULL;
          HNSObject::Set<unsigned __int64>(*(_QWORD *)&v101[0], &v121, &Uuid, 18);
          std::wstring::~wstring(&v121);
          *(_QWORD *)&v101[0] = *v3;
          v123 = 0;
          v124 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v123, L"TcpConnectionsClosedByFinIn");
          *(_QWORD *)&Uuid.Data1 = v86;
          v107[0] = GUID_NULL;
          HNSObject::Set<unsigned __int64>(*(_QWORD *)&v101[0], &v123, &Uuid, 18);
          std::wstring::~wstring(&v123);
          *(_QWORD *)&v101[0] = *v3;
          v125 = 0;
          v126 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v125, L"TcpHalfOpenTimeoutsIn");
          *(_QWORD *)&Uuid.Data1 = v80;
          v107[0] = GUID_NULL;
          HNSObject::Set<unsigned __int64>(*(_QWORD *)&v101[0], &v125, &Uuid, 18);
          std::wstring::~wstring(&v125);
          *(_QWORD *)&v101[0] = *v3;
          v127 = 0;
          v128 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v127, L"TcpConnectionsTimeWaitIn");
          *(_QWORD *)&Uuid.Data1 = v87;
          v107[0] = GUID_NULL;
          HNSObject::Set<unsigned __int64>(*(_QWORD *)&v101[0], &v127, &Uuid, 18);
          std::wstring::~wstring(&v127);
          v33 = *v3;
          v129 = 0;
          v130 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v129, L"DropAclIn");
          *(_QWORD *)&Uuid.Data1 = v78;
          v101[0] = GUID_NULL;
          HNSObject::Set<unsigned __int64>(v33, &v129, &Uuid, 18);
          std::wstring::~wstring(&v129);
          *(_QWORD *)&v101[0] = *v3;
          v131 = 0;
          v132 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v131, L"SynPacketsOut");
          *(_QWORD *)&Uuid.Data1 = v89;
          v107[0] = GUID_NULL;
          HNSObject::Set<unsigned __int64>(*(_QWORD *)&v101[0], &v131, &Uuid, 18);
          std::wstring::~wstring(&v131);
          *(_QWORD *)&v101[0] = *v3;
          v133 = 0;
          v134 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v133, L"SynAckPacketsOut");
          *(_QWORD *)&Uuid.Data1 = v90;
          v107[0] = GUID_NULL;
          HNSObject::Set<unsigned __int64>(*(_QWORD *)&v101[0], &v133, &Uuid, 18);
          std::wstring::~wstring(&v133);
          *(_QWORD *)&v101[0] = *v3;
          v135 = 0;
          v136 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v135, L"FinPacketsOut");
          *(_QWORD *)&Uuid.Data1 = v96;
          v107[0] = GUID_NULL;
          HNSObject::Set<unsigned __int64>(*(_QWORD *)&v101[0], &v135, &Uuid, 18);
          std::wstring::~wstring(&v135);
          *(_QWORD *)&v101[0] = *v3;
          v137 = 0;
          v138 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v137, L"RstPacketsOut");
          *(_QWORD *)&Uuid.Data1 = v95;
          v107[0] = GUID_NULL;
          HNSObject::Set<unsigned __int64>(*(_QWORD *)&v101[0], &v137, &Uuid, 18);
          std::wstring::~wstring(&v137);
          *(_QWORD *)&v101[0] = *v3;
          v139 = 0;
          v140 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v139, L"TcpConnectionsVerifiedOut");
          *(_QWORD *)&Uuid.Data1 = v92;
          v107[0] = GUID_NULL;
          HNSObject::Set<unsigned __int64>(*(_QWORD *)&v101[0], &v139, &Uuid, 18);
          std::wstring::~wstring(&v139);
          *(_QWORD *)&v101[0] = *v3;
          v141 = 0;
          v142 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v141, L"TcpConnectionsTimedOutOut");
          *(_QWORD *)&Uuid.Data1 = v98;
          v107[0] = GUID_NULL;
          HNSObject::Set<unsigned __int64>(*(_QWORD *)&v101[0], &v141, &Uuid, 18);
          std::wstring::~wstring(&v141);
          *(_QWORD *)&v101[0] = *v3;
          v143 = 0;
          v144 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v143, L"TcpConnectionsResetOut");
          *(_QWORD *)&Uuid.Data1 = v94;
          v107[0] = GUID_NULL;
          HNSObject::Set<unsigned __int64>(*(_QWORD *)&v101[0], &v143, &Uuid, 18);
          std::wstring::~wstring(&v143);
          *(_QWORD *)&v101[0] = *v3;
          v145 = 0;
          v146 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v145, L"TcpConnectionsResetBySynOut");
          *(_QWORD *)&Uuid.Data1 = v97;
          v107[0] = GUID_NULL;
          HNSObject::Set<unsigned __int64>(*(_QWORD *)&v101[0], &v145, &Uuid, 18);
          std::wstring::~wstring(&v145);
          *(_QWORD *)&v101[0] = *v3;
          v147 = 0;
          v148 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v147, L"TcpConnectionsClosedByFinOut");
          *(_QWORD *)&Uuid.Data1 = v99;
          v107[0] = GUID_NULL;
          HNSObject::Set<unsigned __int64>(*(_QWORD *)&v101[0], &v147, &Uuid, 18);
          std::wstring::~wstring(&v147);
          *(_QWORD *)&v101[0] = *v3;
          v149 = 0;
          v150 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v149, L"TcpHalfOpenTimeoutsOut");
          *(_QWORD *)&Uuid.Data1 = v93;
          v107[0] = GUID_NULL;
          HNSObject::Set<unsigned __int64>(*(_QWORD *)&v101[0], &v149, &Uuid, 18);
          std::wstring::~wstring(&v149);
          *(_QWORD *)&v101[0] = *v3;
          v108 = 0;
          v109 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v108, L"TcpConnectionsTimeWaitOut");
          *(_QWORD *)&Uuid.Data1 = v100;
          v107[0] = GUID_NULL;
          HNSObject::Set<unsigned __int64>(*(_QWORD *)&v101[0], &v108, &Uuid, 18);
          std::wstring::~wstring(&v108);
          v34 = *v3;
          memset(v107, 0, sizeof(v107));
          std::wstring::_Construct<1,unsigned short const *>(v107, L"DropAclOut");
          *(_QWORD *)&Uuid.Data1 = v91;
          v101[0] = GUID_NULL;
          HNSObject::Set<unsigned __int64>(v34, v107, &Uuid, 18);
          std::wstring::~wstring(v107);
        }
      }
      v35 = (volatile signed __int32 *)v102[1];
      if ( v102[1] )
      {
        if ( !_InterlockedDecrement((volatile signed __int32 *)v102[1] + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v35)(v35);
          if ( !_InterlockedDecrement(v35 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v35 + 8LL))(v35);
        }
      }
    }
    catch ( ... )
    {
      if ( *(_DWORD *)qword_18039AA48 > 3u )
      {
        p_VfpPortCounters = &VfpPortCounters;
        v159 = 1;
        tlgWriteTransfer_EventWriteTransfer(qword_18039AA48, byte_18033B7DD, 0, 0, 3, &Uuid);
      }
      v4 = (RTL_SRWLOCK *)v70;
      v3 = v66;
      v68 = v69;
    }
  }
  try
  {
    VfpPortCounters = 0;
    v36 = (_QWORD *)HNS::Service::Network::Endpoint::GetPortResource(v4, &v103);
    HNS::Service::Resource::PortResource::GetVFPPort(*v36, &v70);
    v37 = *(volatile signed __int32 **)v103.Data4;
    if ( *(_QWORD *)v103.Data4 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)v103.Data4 + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v37)(v37);
        if ( _InterlockedExchangeAdd(v37 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v37 + 8LL))(v37);
      }
    }
    memset_0(v88, 0, 0x620u);
    memset_0(v75, 0, 0x620u);
    if ( v70 )
    {
      VfpPortCounters = VfpPort::GetVfpPortCounters(
                          v70,
                          (struct _VFX_PORT_COUNTER_EX4 *)v88,
                          (struct _VFX_PORT_COUNTER_EX4 *)v75);
      if ( VfpPortCounters )
      {
        v38 = *v3;
        v108 = 0;
        v109 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v108, L"SynPacketsIn");
        v66 = v89;
        Uuid = GUID_NULL;
        HNSObject::Set<unsigned __int64>(v38, &v108, &v66, 18);
        std::wstring::~wstring(&v108);
        v39 = *v3;
        v149 = 0;
        v150 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v149, L"SynAckPacketsIn");
        v66 = v90;
        Uuid = GUID_NULL;
        HNSObject::Set<unsigned __int64>(v39, &v149, &v66, 18);
        std::wstring::~wstring(&v149);
        v40 = *v3;
        v147 = 0;
        v148 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v147, L"FinPacketsIn");
        v66 = v96;
        Uuid = GUID_NULL;
        HNSObject::Set<unsigned __int64>(v40, &v147, &v66, 18);
        std::wstring::~wstring(&v147);
        v41 = *v3;
        v145 = 0;
        v146 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v145, L"RstPacketsIn");
        v66 = v95;
        Uuid = GUID_NULL;
        HNSObject::Set<unsigned __int64>(v41, &v145, &v66, 18);
        std::wstring::~wstring(&v145);
        v42 = *v3;
        v143 = 0;
        v144 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v143, L"TcpConnectionsVerifiedIn");
        v66 = v92;
        Uuid = GUID_NULL;
        HNSObject::Set<unsigned __int64>(v42, &v143, &v66, 18);
        std::wstring::~wstring(&v143);
        v43 = *v3;
        v141 = 0;
        v142 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v141, L"TcpConnectionsTimedOutIn");
        v66 = v98;
        Uuid = GUID_NULL;
        HNSObject::Set<unsigned __int64>(v43, &v141, &v66, 18);
        std::wstring::~wstring(&v141);
        v44 = *v3;
        v139 = 0;
        v140 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v139, L"TcpConnectionsResetIn");
        v66 = v94;
        Uuid = GUID_NULL;
        HNSObject::Set<unsigned __int64>(v44, &v139, &v66, 18);
        std::wstring::~wstring(&v139);
        v45 = *v3;
        v137 = 0;
        v138 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v137, L"TcpConnectionsResetBySynIn");
        v66 = v97;
        Uuid = GUID_NULL;
        HNSObject::Set<unsigned __int64>(v45, &v137, &v66, 18);
        std::wstring::~wstring(&v137);
        v46 = *v3;
        v135 = 0;
        v136 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v135, L"TcpConnectionsClosedByFinIn");
        v66 = v99;
        Uuid = GUID_NULL;
        HNSObject::Set<unsigned __int64>(v46, &v135, &v66, 18);
        std::wstring::~wstring(&v135);
        v47 = *v3;
        v133 = 0;
        v134 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v133, L"TcpHalfOpenTimeoutsIn");
        v66 = v93;
        Uuid = GUID_NULL;
        HNSObject::Set<unsigned __int64>(v47, &v133, &v66, 18);
        std::wstring::~wstring(&v133);
        v48 = *v3;
        v131 = 0;
        v132 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v131, L"TcpConnectionsTimeWaitIn");
        v66 = v100;
        Uuid = GUID_NULL;
        HNSObject::Set<unsigned __int64>(v48, &v131, &v66, 18);
        std::wstring::~wstring(&v131);
        v49 = *v3;
        v129 = 0;
        v130 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v129, L"DropAclIn");
        v66 = v91;
        Uuid = GUID_NULL;
        HNSObject::Set<unsigned __int64>(v49, &v129, &v66, 18);
        std::wstring::~wstring(&v129);
        v50 = *v3;
        v127 = 0;
        v128 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v127, L"SynPacketsOut");
        v66 = v76;
        Uuid = GUID_NULL;
        HNSObject::Set<unsigned __int64>(v50, &v127, &v66, 18);
        std::wstring::~wstring(&v127);
        v51 = *v3;
        v125 = 0;
        v126 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v125, L"SynAckPacketsOut");
        v66 = v77;
        Uuid = GUID_NULL;
        HNSObject::Set<unsigned __int64>(v51, &v125, &v66, 18);
        std::wstring::~wstring(&v125);
        v52 = *v3;
        v123 = 0;
        v124 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v123, L"FinPacketsOut");
        v66 = v83;
        Uuid = GUID_NULL;
        HNSObject::Set<unsigned __int64>(v52, &v123, &v66, 18);
        std::wstring::~wstring(&v123);
        v53 = *v3;
        v121 = 0;
        v122 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v121, L"RstPacketsOut");
        v66 = v82;
        Uuid = GUID_NULL;
        HNSObject::Set<unsigned __int64>(v53, &v121, &v66, 18);
        std::wstring::~wstring(&v121);
        v54 = *v3;
        v151 = 0;
        v152 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v151, L"TcpConnectionsVerifiedOut");
        v66 = v79;
        Uuid = GUID_NULL;
        HNSObject::Set<unsigned __int64>(v54, &v151, &v66, 18);
        std::wstring::~wstring(&v151);
        v55 = *v3;
        v153 = 0;
        v154 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v153, L"TcpConnectionsTimedOutOut");
        v66 = v85;
        Uuid = GUID_NULL;
        HNSObject::Set<unsigned __int64>(v55, &v153, &v66, 18);
        std::wstring::~wstring(&v153);
        v56 = *v3;
        v119 = 0;
        v120 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v119, L"TcpConnectionsResetOut");
        v66 = v81;
        Uuid = GUID_NULL;
        HNSObject::Set<unsigned __int64>(v56, &v119, &v66, 18);
        std::wstring::~wstring(&v119);
        v57 = *v3;
        v117 = 0;
        v118 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v117, L"TcpConnectionsResetBySynOut");
        v66 = v84;
        Uuid = GUID_NULL;
        HNSObject::Set<unsigned __int64>(v57, &v117, &v66, 18);
        std::wstring::~wstring(&v117);
        v58 = *v3;
        v115 = 0;
        v116 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v115, L"TcpConnectionsClosedByFinOut");
        v66 = v86;
        Uuid = GUID_NULL;
        HNSObject::Set<unsigned __int64>(v58, &v115, &v66, 18);
        std::wstring::~wstring(&v115);
        v59 = *v3;
        v113 = 0;
        v114 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v113, L"TcpHalfOpenTimeoutsOut");
        v66 = v80;
        Uuid = GUID_NULL;
        HNSObject::Set<unsigned __int64>(v59, &v113, &v66, 18);
        std::wstring::~wstring(&v113);
        v60 = *v3;
        v105 = 0;
        v106 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v105, L"TcpConnectionsTimeWaitOut");
        v66 = v87;
        Uuid = GUID_NULL;
        HNSObject::Set<unsigned __int64>(v60, &v105, &v66, 18);
        std::wstring::~wstring(&v105);
        v61 = *v3;
        memset(v101, 0, sizeof(v101));
        std::wstring::_Construct<1,unsigned short const *>(v101, L"DropAclOut");
        v66 = v78;
        Uuid = GUID_NULL;
        HNSObject::Set<unsigned __int64>(v61, v101, &v66, 18);
        std::wstring::~wstring(v101);
      }
    }
    v62 = v71;
    if ( v71 )
    {
      if ( _InterlockedExchangeAdd(v71 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v62)(v62);
        if ( _InterlockedExchangeAdd(v62 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v62 + 8LL))(v62);
      }
    }
    v63 = v68;
  }
  catch ( ... )
  {
    if ( *(_DWORD *)qword_18039AA48 > 3u )
    {
      p_VfpPortCounters = &VfpPortCounters;
      v159 = 1;
      tlgWriteTransfer_EventWriteTransfer(qword_18039AA48, byte_18033BB39, 0, 0, 3, &Uuid);
    }
    v63 = v69;
  }
  std::wstring::~wstring(&v110);
  if ( v63 )
    HNSObject::Release(v63);
  if ( SRWLock )
    ReleaseSRWLockShared(SRWLock);
  HNSTraceProvider::TraceSuccess("HNS::Service::Network::Endpoint::GetStats", 0xA97u);
}

```

## disassembly

```asm
0x180152260  push    rbx
0x180152262  push    rsi
0x180152263  push    rdi
0x180152264  push    r12
0x180152266  push    r13
0x180152268  push    r14
0x18015226a  push    r15
0x18015226c  mov     eax, 10F0h
0x180152271  call    _alloca_probe
0x180152276  sub     rsp, rax
0x180152279  movaps  [rsp+1128h+var_48], xmm6
0x180152281  mov     rax, cs:__security_cookie
0x180152288  xor     rax, rsp
0x18015228b  mov     [rsp+1128h+var_58], rax
0x180152293  mov     rsi, r8
0x180152296  mov     [rsp+1128h+var_10E8], rdx
0x18015229b  mov     rdi, rcx
0x18015229e  mov     qword ptr [rsp+1128h+var_468], rcx
0x1801522a6  mov     [rsp+1128h+var_10D0], rcx
0x1801522ab  mov     [rsp+1128h+var_10F0], r8
0x1801522b0  xor     r15d, r15d
0x1801522b3  mov     r13d, r15d
0x1801522b6  mov     dword ptr [rsp+1128h+var_10E0], r15d
0x1801522bb  mov     edx, 9F7h; unsigned int
0x1801522c0  lea     rcx, aHnsServiceNetw_134; "HNS::Service::Network::Endpoint::GetSta"...
0x1801522c7  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x1801522cc  lea     rbx, [rdi+28h]
0x1801522d0  mov     [rsp+1128h+SRWLock], rbx
0x1801522d5  mov     rcx, rbx; SRWLock
0x1801522d8  call    cs:__imp_AcquireSRWLockShared
0x1801522de  mov     [rsp+1128h+var_10B8], rbx
0x1801522e3  mov     rcx, rdi; this
0x1801522e6  call    ?ValidateAndThrow@IEntity@Interface@Service@HNS@@QEAAXXZ; HNS::Service::Interface::IEntity::ValidateAndThrow(void)
0x1801522eb  xor     edx, edx; Val
0x1801522ed  lea     r8d, [r15+70h]; Size
0x1801522f1  lea     rcx, [rsp+1128h+var_F8]; void *
0x1801522f9  call    memset_0
0x1801522fe  mov     rax, [rdi+8]
0x180152302  mov     [rsp+1128h+var_10E0], rax
0x180152307  mov     [rsp+1128h+var_10D8], rax
0x18015230c  mov     [rsp+1128h+var_10B0], rax
0x180152311  lea     ebx, [r15+1]
0x180152315  test    rax, rax
0x180152318  jz      short loc_18015231E
0x18015231a  lock add [rax+10h], ebx
0x18015231e  xorps   xmm0, xmm0
0x180152321  movups  [rsp+1128h+var_3B8], xmm0
0x180152329  mov     [rsp+1128h+var_3A8], r15
0x180152331  mov     [rsp+1128h+var_3A0], 7
0x18015233d  mov     word ptr [rsp+1128h+var_3B8], r15w
0x180152346  lea     rdx, [rsp+1128h+var_438]; retstr
0x18015234e  mov     rcx, rdi; this
0x180152351  call    ?GetEndpointNicGuid@Endpoint@Network@Service@HNS@@QEBA?AU_GUID@@XZ; HNS::Service::Network::Endpoint::GetEndpointNicGuid(void)
0x180152356  mov     r8d, 10h; Size
0x18015235c  lea     rdx, GUID_NULL; Buf2
0x180152363  mov     rcx, rax; Buf1
0x180152366  call    memcmp_0
0x18015236b  test    eax, eax
0x18015236d  jz      loc_18015241B
0x180152373  lea     rdx, [rsp+1128h+Uuid]; retstr
0x18015237b  mov     rcx, rdi; this
0x18015237e  call    ?GetEndpointNicGuid@Endpoint@Network@Service@HNS@@QEBA?AU_GUID@@XZ; HNS::Service::Network::Endpoint::GetEndpointNicGuid(void)
0x180152383  xor     r8d, r8d
0x180152386  lea     rdx, [rsp+1128h+Uuid]
0x18015238e  lea     rcx, [rsp+1128h+var_3D8]
0x180152396  call    ?GuidToString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; GuidToString(_GUID const &,bool)
0x18015239b  mov     rdx, rax
0x18015239e  lea     rcx, [rsp+1128h+var_3B8]
0x1801523a6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1801523ab  lea     rcx, [rsp+1128h+var_3D8]; void *
0x1801523b3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801523b8  or      r12d, 0FFFFFFFFh
0x1801523bc  cmp     [rsp+1128h+var_3A8], r15
0x1801523c4  jz      loc_1801524E3
0x1801523ca  lea     rbx, [rsp+1128h+var_3B8]
0x1801523d2  cmp     [rsp+1128h+var_3A0], 7
0x1801523db  cmova   rbx, qword ptr [rsp+1128h+var_3B8]
0x1801523e4  mov     edx, 424h; unsigned int
0x1801523e9  lea     rcx, aHnsGetnicstats; "HNS::GetNicStats"
0x1801523f0  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x1801523f5  lea     rdx, [rsp+1128h+var_F8]
0x1801523fd  mov     rcx, rbx
0x180152400  call    cs:__imp_NetMgmtGetNicStats
0x180152406  mov     rcx, [rsp+1128h]; this
0x18015240e  test    eax, eax
0x180152410  js      loc_1801548DA
0x180152416  jmp     loc_1801524D2
0x18015241b  mov     rcx, [rdi+748h]
0x180152422  test    rcx, rcx
0x180152425  jz      short loc_1801523B8
0x180152427  mov     rax, [rdi+750h]
0x18015242e  test    rax, rax
0x180152431  jz      short loc_180152437
0x180152433  lock add [rax+8], ebx
0x180152437  mov     rbx, [rdi+750h]
0x18015243e  lea     r8, [rcx+8C0h]
0x180152445  lea     rdx, [rsp+1128h+var_3D8]
0x18015244d  mov     rcx, [rcx+8F8h]
0x180152454  call    ??$Get@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@HNSObject@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z; HNSObject::Get<std::wstring>(std::wstring const &)
0x180152459  mov     r13d, 4
0x18015245f  lea     rdx, [rsp+1128h+var_3D8]
0x180152467  lea     rcx, [rsp+1128h+var_3B8]
0x18015246f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180152474  lea     rcx, [rsp+1128h+var_3D8]; void *
0x18015247c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180152481  or      r12d, 0FFFFFFFFh
0x180152485  test    rbx, rbx
0x180152488  jz      loc_1801523BC
0x18015248e  mov     eax, r12d
0x180152491  lock xadd [rbx+8], eax
0x180152496  add     eax, r12d
0x180152499  jnz     loc_1801523BC
0x18015249f  mov     rax, [rbx]
0x1801524a2  mov     rcx, rbx
0x1801524a5  mov     rax, [rax]
0x1801524a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801524ad  mov     eax, r12d
0x1801524b0  lock xadd [rbx+0Ch], eax
0x1801524b5  add     eax, r12d
0x1801524b8  jnz     loc_1801523BC
0x1801524be  mov     rax, [rbx]
0x1801524c1  mov     rcx, rbx
0x1801524c4  mov     rax, [rax+8]
0x1801524c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801524cd  jmp     loc_1801523BC
0x1801524d2  mov     edx, 42Ah; unsigned int
0x1801524d7  lea     rcx, aHnsGetnicstats; "HNS::GetNicStats"
0x1801524de  call    ?TraceSuccess@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceSuccess(char const *,uint)
0x1801524e3  xorps   xmm0, xmm0
0x1801524e6  movups  xmmword ptr [rsp+1128h+Uuid.Data1], xmm0
0x1801524ee  lea     rcx, [rsp+1128h+Uuid]; Uuid
0x1801524f6  call    cs:__imp_UuidCreate
0x1801524fc  movaps  xmm0, xmmword ptr [rsp+1128h+Uuid.Data1]
0x180152504  movdqa  xmmword ptr [rsp+1128h+var_448], xmm0
0x18015250d  mov     rbx, [rsi]
0x180152510  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x180152517  xorps   xmm0, xmm0
0x18015251a  movups  xmmword ptr [rsp+1128h+var_438.Data1], xmm0
0x180152522  xorps   xmm1, xmm1
0x180152525  movdqu  [rsp+1128h+var_428], xmm1
0x18015252e  mov     r8d, 0Ah
0x180152534  lea     rdx, aInstanceid; "InstanceId"
0x18015253b  lea     rcx, [rsp+1128h+var_438]
0x180152543  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180152548  nop
0x180152549  movdqu  xmmword ptr [rsp+1128h+Uuid.Data1], xmm6
0x180152552  lea     rax, [rsp+1128h+Uuid]
0x18015255a  mov     qword ptr [rsp+1128h+var_1108], rax
0x18015255f  mov     r14d, 12h
0x180152565  mov     r9d, r14d
0x180152568  lea     r8, [rsp+1128h+var_448]
0x180152570  lea     rdx, [rsp+1128h+var_438]
0x180152578  mov     rcx, rbx
0x18015257b  call    ??$Set@U_GUID@@@HNSObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@KU3@@Z; HNSObject::Set<_GUID>(std::wstring const &,_GUID const &,ulong,_GUID)
0x180152580  nop
0x180152581  lea     rcx, [rsp+1128h+var_438]; void *
0x180152589  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18015258e  xorps   xmm0, xmm0
0x180152591  movups  xmmword ptr [rsp+1128h+Uuid.Data1], xmm0
0x180152599  xorps   xmm1, xmm1
0x18015259c  movdqu  [rsp+1128h+var_78], xmm1
0x1801525a5  lea     r8d, [r14-10h]
0x1801525a9  lea     rdx, aId_0; "ID"
0x1801525b0  lea     rcx, [rsp+1128h+Uuid]
0x1801525b8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1801525bd  nop
0x1801525be  lea     r8, [rsp+1128h+Uuid]
0x1801525c6  lea     rdx, [rsp+1128h+var_438]
0x1801525ce  mov     rcx, [rsp+1128h+var_10E0]
0x1801525d3  call    ?GetGuid@HNSObject@@QEBA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::GetGuid(std::wstring const &)
0x1801525d8  movups  xmm0, xmmword ptr [rax]
0x1801525db  movdqu  xmmword ptr [rsp+1128h+var_448], xmm0
0x1801525e4  lea     rcx, [rsp+1128h+Uuid]; void *
0x1801525ec  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801525f1  mov     rbx, [rsi]
0x1801525f4  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x1801525fb  xorps   xmm0, xmm0
0x1801525fe  movups  xmmword ptr [rsp+1128h+var_438.Data1], xmm0
0x180152606  xorps   xmm1, xmm1
0x180152609  movdqu  [rsp+1128h+var_428], xmm1
0x180152612  lea     r8d, [r14-8]
0x180152616  lea     rdx, aEndpointid; "EndpointId"
0x18015261d  lea     rcx, [rsp+1128h+var_438]
0x180152625  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18015262a  nop
0x18015262b  movdqu  xmmword ptr [rsp+1128h+Uuid.Data1], xmm6
0x180152634  lea     rax, [rsp+1128h+Uuid]
0x18015263c  mov     qword ptr [rsp+1128h+var_1108], rax
0x180152641  mov     r9d, r14d
0x180152644  lea     r8, [rsp+1128h+var_448]
0x18015264c  lea     rdx, [rsp+1128h+var_438]
0x180152654  mov     rcx, rbx
0x180152657  call    ??$Set@U_GUID@@@HNSObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@KU3@@Z; HNSObject::Set<_GUID>(std::wstring const &,_GUID const &,ulong,_GUID)
0x18015265c  nop
0x18015265d  lea     rcx, [rsp+1128h+var_438]; void *
0x180152665  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18015266a  xorps   xmm0, xmm0
0x18015266d  movups  xmmword ptr [rsp+1128h+var_438.Data1], xmm0
0x180152675  xorps   xmm1, xmm1
0x180152678  movdqu  [rsp+1128h+var_428], xmm1
0x180152681  lea     r8d, [r14-0Eh]
0x180152685  lea     rdx, aAll_1; "/all"
0x18015268c  lea     rcx, [rsp+1128h+var_438]
0x180152694  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180152699  lea     r8, [rsp+1128h+var_438]
0x1801526a1  lea     rdx, [rsp+1128h+var_448]
0x1801526a9  mov     rbx, [rsp+1128h+var_10E8]
0x1801526ae  mov     rcx, rbx
0x1801526b1  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UIpsetData@Resource@Service@HNS@@U?$default_delete@UIpsetData@Resource@Service@HNS@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UIpsetData@Resource@Service@HNS@@U?$default_delete@UIpsetData@Resource@Service@HNS@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UIpsetData@Resource@Service@HNS@@U?$default_delete@UIpsetData@Resource@Service@HNS@@@std@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<HNS::Service::Resource::IpsetData>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<HNS::Service::Resource::IpsetData>>>,0>>::find(std::wstring const &)
0x1801526b6  mov     rbx, [rbx+8]
0x1801526ba  mov     qword ptr [rsp+1128h+Uuid.Data1], rbx
0x1801526c2  mov     rax, [rax]
0x1801526c5  mov     qword ptr [rsp+1128h+var_3F8], rax
0x1801526cd  lea     rcx, [rsp+1128h+var_438]; void *
0x1801526d5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801526da  cmp     qword ptr [rsp+1128h+var_3F8], rbx
0x1801526e2  jnz     short loc_180152749
0x1801526e4  xorps   xmm0, xmm0
0x1801526e7  movups  xmmword ptr [rsp+1128h+var_438.Data1], xmm0
0x1801526ef  xorps   xmm1, xmm1
0x1801526f2  movdqu  [rsp+1128h+var_428], xmm1
0x1801526fb  lea     r8d, [r14-0Eh]
0x1801526ff  lea     rdx, aHns_0; "/hns"
0x180152706  lea     rcx, [rsp+1128h+var_438]
0x18015270e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180152713  lea     ebx, [r14-11h]
0x180152717  or      r13d, ebx
0x18015271a  lea     r8, [rsp+1128h+var_438]
0x180152722  lea     rdx, [rsp+1128h+var_448]
0x18015272a  mov     rcx, [rsp+1128h+var_10E8]
0x18015272f  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UIpsetData@Resource@Service@HNS@@U?$default_delete@UIpsetData@Resource@Service@HNS@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UIpsetData@Resource@Service@HNS@@U?$default_delete@UIpsetData@Resource@Service@HNS@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UIpsetData@Resource@Service@HNS@@U?$default_delete@UIpsetData@Resource@Service@HNS@@@std@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<HNS::Service::Resource::IpsetData>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<HNS::Service::Resource::IpsetData>>>,0>>::find(std::wstring const &)
0x180152734  mov     rcx, [rsp+1128h+var_10E8]
0x180152739  mov     rcx, [rcx+8]
0x18015273d  cmp     [rax], rcx
0x180152740  jnz     short loc_18015274E
0x180152742  mov     [rsp+1128h+var_10F8], r15b
0x180152747  jmp     short loc_180152752
0x180152749  mov     ebx, 1
0x18015274e  mov     [rsp+1128h+var_10F8], bl
0x180152752  test    bl, r13b
0x180152755  jz      short loc_180152768
0x180152757  and     r13d, 0FFFFFFFEh
0x18015275b  lea     rcx, [rsp+1128h+var_438]; void *
0x180152763  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180152768  cmp     [rsp+1128h+var_10F8], r15b
0x18015276d  jz      loc_180152B71
0x180152773  mov     rbx, [rsi]
0x180152776  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x18015277d  xorps   xmm0, xmm0
0x180152780  movups  [rsp+1128h+var_418], xmm0
0x180152788  xorps   xmm1, xmm1
0x18015278b  movdqu  [rsp+1128h+var_408], xmm1
0x180152794  mov     r8d, 0Dh
0x18015279a  lea     rdx, aBytesreceived; "BytesReceived"
0x1801527a1  lea     rcx, [rsp+1128h+var_418]
0x1801527a9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1801527ae  nop
0x1801527af  mov     rax, [rsp+1128h+var_F8]
0x1801527b7  mov     [rsp+1128h+var_448], rax
0x1801527bf  movdqu  xmmword ptr [rsp+1128h+var_438.Data1], xmm6
0x1801527c8  lea     rax, [rsp+1128h+var_438]
0x1801527d0  mov     qword ptr [rsp+1128h+var_1108], rax
0x1801527d5  mov     r9d, r14d
0x1801527d8  lea     r8, [rsp+1128h+var_448]
0x1801527e0  lea     rdx, [rsp+1128h+var_418]
0x1801527e8  mov     rcx, rbx
0x1801527eb  call    ??$Set@_K@HNSObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEB_KKU_GUID@@@Z; HNSObject::Set<unsigned __int64>(std::wstring const &,unsigned __int64 const &,ulong,_GUID)
0x1801527f0  nop
0x1801527f1  lea     rcx, [rsp+1128h+var_418]; void *
0x1801527f9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801527fe  mov     rbx, [rsi]
0x180152801  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x180152808  xorps   xmm0, xmm0
0x18015280b  movups  [rsp+1128h+var_418], xmm0
0x180152813  xorps   xmm1, xmm1
0x180152816  movdqu  [rsp+1128h+var_408], xmm1
0x18015281f  mov     r8d, 9
0x180152825  lea     rdx, aBytessent; "BytesSent"
0x18015282c  lea     rcx, [rsp+1128h+var_418]
0x180152834  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180152839  nop
0x18015283a  mov     rax, [rsp+1128h+var_F0]
0x180152842  mov     [rsp+1128h+var_448], rax
0x18015284a  movdqu  xmmword ptr [rsp+1128h+var_438.Data1], xmm6
0x180152853  lea     rax, [rsp+1128h+var_438]
0x18015285b  mov     qword ptr [rsp+1128h+var_1108], rax
0x180152860  mov     r9d, r14d
0x180152863  lea     r8, [rsp+1128h+var_448]
0x18015286b  lea     rdx, [rsp+1128h+var_418]
0x180152873  mov     rcx, rbx
0x180152876  call    ??$Set@_K@HNSObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEB_KKU_GUID@@@Z; HNSObject::Set<unsigned __int64>(std::wstring const &,unsigned __int64 const &,ulong,_GUID)
0x18015287b  nop
0x18015287c  lea     rcx, [rsp+1128h+var_418]; void *
0x180152884  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180152889  mov     rbx, [rsi]
0x18015288c  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x180152893  xorps   xmm0, xmm0
0x180152896  movups  [rsp+1128h+var_418], xmm0
0x18015289e  xorps   xmm1, xmm1
0x1801528a1  movdqu  [rsp+1128h+var_408], xmm1
  ... truncated ...
```
