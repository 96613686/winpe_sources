# Microsoft::DiagnosticsHub::StandardCollector::AgentController::AddAgentInstance(IUnknown *,_GUID const &,ushort const *)

- ea: `0x18000dd60`
- end: `0x18000f1b0`
- name: `?AddAgentInstance@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@IEAAJPEAUIUnknown@@AEBU_GUID@@PEBG@Z`
- size: `5200`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::AgentController *this, struct IUnknown *, const struct _GUID *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000a8b0`
- `0x18000a910`
- `0x18001d2d0`

## callees

- `0x18000a17c`
- `0x18000dd60`
- `0x1800102ec`
- `0x180010540`
- `0x180010674`
- `0x1800107c0`
- `0x18003d864`
- `0x180040d8c`
- `0x180041834`
- `0x180041968`
- `0x180041a18`
- `0x180041a48`
- `0x180049b50`
- `0x18004ad58`
- `0x18004b640`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000e70a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000eb3b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000e70a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000eb3b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000e680`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000eb0c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000e680`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000eb0c`
- `KERNEL32!LeaveCriticalSection` at `0x18000df20`
- `KERNEL32!LeaveCriticalSection` at `0x18000dfc8`
- `KERNEL32!LeaveCriticalSection` at `0x18000e46f`
- `KERNEL32!LeaveCriticalSection` at `0x18000e504`
- `KERNEL32!LeaveCriticalSection` at `0x18000e59b`
- `KERNEL32!LeaveCriticalSection` at `0x18000e655`
- `KERNEL32!LeaveCriticalSection` at `0x18000e7c4`
- `KERNEL32!LeaveCriticalSection` at `0x18000e87e`
- `KERNEL32!LeaveCriticalSection` at `0x18000e938`
- `KERNEL32!LeaveCriticalSection` at `0x18000ea4b`
- `KERNEL32!LeaveCriticalSection` at `0x18000ea7a`
- `KERNEL32!LeaveCriticalSection` at `0x18000eaa9`
- `KERNEL32!LeaveCriticalSection` at `0x18000eaf2`
- `KERNEL32!LeaveCriticalSection` at `0x18000eb84`
- `KERNEL32!LeaveCriticalSection` at `0x18000ebd0`
- `KERNEL32!LeaveCriticalSection` at `0x18000ec24`
- `KERNEL32!LeaveCriticalSection` at `0x18000ed3b`
- `KERNEL32!LeaveCriticalSection` at `0x18000ee6e`
- `KERNEL32!LeaveCriticalSection` at `0x18000ef97`
- `KERNEL32!LeaveCriticalSection` at `0x18000f14f`
- `KERNEL32!LeaveCriticalSection` at `0x18000df20`
- `KERNEL32!LeaveCriticalSection` at `0x18000dfc8`
- `KERNEL32!LeaveCriticalSection` at `0x18000e46f`
- `KERNEL32!LeaveCriticalSection` at `0x18000e504`
- `KERNEL32!LeaveCriticalSection` at `0x18000e59b`
- `KERNEL32!LeaveCriticalSection` at `0x18000e655`
- `KERNEL32!LeaveCriticalSection` at `0x18000e7c4`
- `KERNEL32!LeaveCriticalSection` at `0x18000e87e`
- `KERNEL32!LeaveCriticalSection` at `0x18000e938`
- `KERNEL32!LeaveCriticalSection` at `0x18000ea4b`
- `KERNEL32!LeaveCriticalSection` at `0x18000ea7a`
- `KERNEL32!LeaveCriticalSection` at `0x18000eaa9`
- `KERNEL32!LeaveCriticalSection` at `0x18000eaf2`
- `KERNEL32!LeaveCriticalSection` at `0x18000eb84`
- `KERNEL32!LeaveCriticalSection` at `0x18000ebd0`
- `KERNEL32!LeaveCriticalSection` at `0x18000ec24`
- `KERNEL32!LeaveCriticalSection` at `0x18000ed3b`
- `KERNEL32!LeaveCriticalSection` at `0x18000ee6e`
- `KERNEL32!LeaveCriticalSection` at `0x18000ef97`
- `KERNEL32!LeaveCriticalSection` at `0x18000f14f`
- `KERNEL32!EnterCriticalSection` at `0x18000de69`
- `KERNEL32!EnterCriticalSection` at `0x18000e3d8`
- `KERNEL32!EnterCriticalSection` at `0x18000e492`
- `KERNEL32!EnterCriticalSection` at `0x18000e52e`
- `KERNEL32!EnterCriticalSection` at `0x18000e5be`
- `KERNEL32!EnterCriticalSection` at `0x18000e72d`
- `KERNEL32!EnterCriticalSection` at `0x18000e7e7`
- `KERNEL32!EnterCriticalSection` at `0x18000e8a1`
- `KERNEL32!EnterCriticalSection` at `0x18000ea1b`
- `KERNEL32!EnterCriticalSection` at `0x18000ea65`
- `KERNEL32!EnterCriticalSection` at `0x18000ea94`
- `KERNEL32!EnterCriticalSection` at `0x18000eac3`
- `KERNEL32!EnterCriticalSection` at `0x18000eb55`
- `KERNEL32!EnterCriticalSection` at `0x18000eba1`
- `KERNEL32!EnterCriticalSection` at `0x18000ebf5`
- `KERNEL32!EnterCriticalSection` at `0x18000edef`
- `KERNEL32!EnterCriticalSection` at `0x18000de69`
- `KERNEL32!EnterCriticalSection` at `0x18000e3d8`
- `KERNEL32!EnterCriticalSection` at `0x18000e492`
- `KERNEL32!EnterCriticalSection` at `0x18000e52e`
- `KERNEL32!EnterCriticalSection` at `0x18000e5be`
- `KERNEL32!EnterCriticalSection` at `0x18000e72d`
- `KERNEL32!EnterCriticalSection` at `0x18000e7e7`
- `KERNEL32!EnterCriticalSection` at `0x18000e8a1`
- `KERNEL32!EnterCriticalSection` at `0x18000ea1b`
- `KERNEL32!EnterCriticalSection` at `0x18000ea65`
- `KERNEL32!EnterCriticalSection` at `0x18000ea94`
- `KERNEL32!EnterCriticalSection` at `0x18000eac3`
- `KERNEL32!EnterCriticalSection` at `0x18000eb55`
- `KERNEL32!EnterCriticalSection` at `0x18000eba1`
- `KERNEL32!EnterCriticalSection` at `0x18000ebf5`
- `KERNEL32!EnterCriticalSection` at `0x18000edef`
- `ole32!StringFromGUID2` at `0x18000de3f`
- `ole32!StringFromGUID2` at `0x18000de3f`

## string_xrefs

- `0x18000e971`: `Configuring agent (%s) with [%s]`
- `0x18000e978`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\AgentController.cpp`
- `0x18000ea01`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\AgentController.cpp`
- `0x18000ee94`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\AgentController.cpp`
- `0x18000ee8d`: `Loaded agent (%s)`
- `0x18000e9fa`: `Failed to load agent (%s) (HRESULT: %#08x)`

## pseudocode

```c
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::AgentController::AddAgentInstance(
        Microsoft::DiagnosticsHub::StandardCollector::AgentController *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        const unsigned __int16 *a4)
{
  Microsoft::DiagnosticsHub::StandardCollector::AgentController *v6; // r15
  Microsoft::DiagnosticsHub::StandardCollector::AgentController *v7; // r14
  unsigned __int16 *v9; // rax
  struct _RTL_CRITICAL_SECTION *v10; // rdi
  __int64 v11; // rax
  int ModulePath; // ebx
  const unsigned __int16 *v13; // r8
  const struct _GUID *v14; // rdx
  struct IUnknown *v15; // rbx
  struct IUnknown *v16; // rbx
  struct IUnknown *v17; // rbx
  struct IUnknown *v18; // rbx
  struct IUnknown *v19; // rbx
  struct IUnknown *v20; // rbx
  struct IUnknown *v21; // rbx
  struct IUnknown *v22; // rbx
  struct IUnknown *v23; // rcx
  __int64 v24; // rax
  unsigned __int16 *v25; // rdx
  const struct _GUID *v26; // r13
  struct IUnknown *v27; // rdx
  __int64 v28; // rax
  unsigned __int16 *v29; // rcx
  struct IUnknown *v30; // r13
  __int64 v31; // rdx
  unsigned __int16 *v32; // rcx
  struct IUnknown *v33; // rdx
  __int64 v34; // rax
  unsigned __int16 *v35; // rcx
  struct IUnknown *v36; // rdx
  __int64 v37; // rax
  unsigned __int16 *v38; // rcx
  struct IUnknown *v39; // rdx
  __int64 v40; // rax
  unsigned __int16 *v41; // rcx
  int v42; // r12d
  const struct _GUID *v43; // r13
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  struct IUnknown *v48; // rcx
  __int64 v49; // rcx
  struct IUnknown *v50; // rax
  __int64 v51; // rcx
  struct _RTL_CRITICAL_SECTION *v52; // rbx
  unsigned __int16 *v53; // r15
  __int64 v54; // rdx
  unsigned __int16 *v55; // rcx
  const unsigned __int16 *v56; // r8
  const struct _GUID *v57; // rdx
  __int64 v58; // [rsp+20h] [rbp-228h]
  struct _GUID *v60[2]; // [rsp+38h] [rbp-210h] BYREF
  int pExceptionObject; // [rsp+48h] [rbp-200h] BYREF
  struct _GUID *v62[2]; // [rsp+50h] [rbp-1F8h] BYREF
  struct _RTL_CRITICAL_SECTION *v63; // [rsp+60h] [rbp-1E8h]
  Microsoft::DiagnosticsHub::StandardCollector::AgentController *v64; // [rsp+68h] [rbp-1E0h]
  const struct _GUID *v65; // [rsp+78h] [rbp-1D0h]
  const unsigned __int16 *v66; // [rsp+80h] [rbp-1C8h]
  _BYTE v67[8]; // [rsp+88h] [rbp-1C0h] BYREF
  unsigned __int16 *v68[2]; // [rsp+90h] [rbp-1B8h] BYREF
  __int64 v69; // [rsp+A0h] [rbp-1A8h]
  _QWORD v70[2]; // [rsp+A8h] [rbp-1A0h] BYREF
  struct IUnknown *v71; // [rsp+B8h] [rbp-190h] BYREF
  unsigned __int16 *v72; // [rsp+C0h] [rbp-188h] BYREF
  struct IUnknown *v73; // [rsp+C8h] [rbp-180h] BYREF
  struct IUnknown *v74; // [rsp+D0h] [rbp-178h] BYREF
  struct IUnknown *v75; // [rsp+D8h] [rbp-170h] BYREF
  struct IUnknown *v76; // [rsp+E0h] [rbp-168h] BYREF
  struct IUnknown *v77; // [rsp+E8h] [rbp-160h] BYREF
  struct IUnknown *v78; // [rsp+F0h] [rbp-158h] BYREF
  struct IUnknown *v79; // [rsp+F8h] [rbp-150h] BYREF
  __int64 v80; // [rsp+100h] [rbp-148h] BYREF
  OLECHAR sz[112]; // [rsp+110h] [rbp-138h] BYREF
  void *v82[2]; // [rsp+1F0h] [rbp-58h] BYREF

  v66 = a4;
  v6 = this;
  v7 = this;
  v64 = this;
  v65 = a3;
  if ( *((_BYTE *)this + 689) )
    return 3775987731LL;
  if ( !a2 )
    return 2147500035LL;
  if ( !*((_QWORD *)this + 85) )
    return 2147947423LL;
  v72 = 0;
  if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, unsigned __int16 **))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_bb4a877f_85a4_4891_b7fe_6b28d1c1b059,
         &v72) >= 0 )
  {
    v9 = v72;
  }
  else
  {
    v9 = 0;
    v72 = 0;
  }
  if ( !v9 )
    return 2147942487LL;
  if ( !StringFromGUID2(a3, sz, 39) )
  {
    pExceptionObject = -2147024882;
    throw (long *)&pExceptionObject;
  }
  sz[39] = 0;
  sz[78] = 0;
  v10 = (struct _RTL_CRITICAL_SECTION *)((char *)v6 + 8);
  v63 = (struct _RTL_CRITICAL_SECTION *)((char *)v6 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 8));
  v80 = 0;
  if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_7903a98d_7a1d_475f_a5f2_18b5d1a53787,
         &v80) >= 0 )
  {
    v11 = v80;
  }
  else
  {
    v11 = 0;
    v80 = 0;
  }
  if ( v11 && !*((_BYTE *)v6 + 688) )
  {
    *(_OWORD *)v68 = 0;
    v69 = 0;
    ModulePath = DiagHubCommon::ModulePath::GetModulePath(0);
    if ( ModulePath >= 0 )
    {
      *(_OWORD *)v60 = 0;
      DiagHubCommon::HResultFormatter::HResultFormatter(
        (DiagHubCommon::HResultFormatter *)v60,
        -518979497,
        v68[0],
        *((_WORD *)v6 + 336));
      v14 = (const struct _GUID *)L"<unknown error>";
      if ( v60[0] )
        v14 = v60[0];
      DiagHubCommon::SetErrorInfo((DiagHubCommon *)&IID_ICollectionSession, v14, v13);
      ModulePath = (int)v60[1];
      DiagHubCommon::HResultFormatter::~HResultFormatter((DiagHubCommon::HResultFormatter *)v60);
      std::vector<unsigned short>::~vector<unsigned short>(v68);
      if ( v80 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 8));
      if ( v72 )
        (*(void (__fastcall **)(unsigned __int16 *, _QWORD))(*(_QWORD *)v72 + 16LL))(v72, *(_QWORD *)v72);
    }
    else
    {
      _mm_lfence();
      std::vector<unsigned short>::~vector<unsigned short>(v68);
      if ( v80 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 8));
      if ( v72 )
        (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v72 + 16LL))(v72);
    }
    return (unsigned int)ModulePath;
  }
  v79 = 0;
  if ( *(_QWORD *)std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::find(
                    (char *)v6 + 696,
                    v70) != *((_QWORD *)v6 + 88) )
  {
    v15 = v79;
    if ( v79 != a2 )
    {
      if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))a2->lpVtbl->QueryInterface)(
             a2,
             &GUID_5793882a_6078_47c4_8197_c970a79c5121,
             &v79) < 0 )
        v79 = 0;
      if ( v15 )
        ((void (__fastcall *)(struct IUnknown *))v15->lpVtbl->Release)(v15);
    }
  }
  v78 = 0;
  if ( *(_QWORD *)std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::find(
                    (char *)v6 + 696,
                    v70) != *((_QWORD *)v6 + 88) )
  {
    v16 = v78;
    if ( v78 != a2 )
    {
      if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))a2->lpVtbl->QueryInterface)(
             a2,
             &GUID_fda07c49_142b_4f04_ac7b_7c77fc86fd94,
             &v78) < 0 )
        v78 = 0;
      if ( v16 )
        ((void (__fastcall *)(struct IUnknown *))v16->lpVtbl->Release)(v16);
    }
  }
  v77 = 0;
  if ( *(_QWORD *)std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::find(
                    (char *)v6 + 696,
                    v70) != *((_QWORD *)v6 + 88) )
  {
    v17 = v77;
    if ( v77 != a2 )
    {
      if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))a2->lpVtbl->QueryInterface)(
             a2,
             &GUID_c1392ad2_d0cb_4daa_84a2_1eb740c8f322,
             &v77) < 0 )
        v77 = 0;
      if ( v17 )
        ((void (__fastcall *)(struct IUnknown *))v17->lpVtbl->Release)(v17);
    }
  }
  v76 = 0;
  if ( *(_QWORD *)std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::find(
                    (char *)v6 + 696,
                    v70) != *((_QWORD *)v6 + 88) )
  {
    v18 = v76;
    if ( v76 != a2 )
    {
      if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))a2->lpVtbl->QueryInterface)(
             a2,
             &GUID_971bfd3c_85ad_483f_891c_01ef37ba361a,
             &v76) < 0 )
        v76 = 0;
      if ( v18 )
        ((void (__fastcall *)(struct IUnknown *))v18->lpVtbl->Release)(v18);
    }
  }
  v75 = 0;
  if ( *(_QWORD *)std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::find(
                    (char *)v6 + 696,
                    v70) != *((_QWORD *)v6 + 88) )
  {
    v19 = v75;
    if ( v75 != a2 )
    {
      if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))a2->lpVtbl->QueryInterface)(
             a2,
             &GUID_42e43569_8c6d_44a5_9fa6_ec7db18033eb,
             &v75) < 0 )
        v75 = 0;
      if ( v19 )
        ((void (__fastcall *)(struct IUnknown *))v19->lpVtbl->Release)(v19);
    }
  }
  v74 = 0;
  if ( *(_QWORD *)std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::find(
                    (char *)v6 + 696,
                    v70) != *((_QWORD *)v6 + 88) )
  {
    v20 = v74;
    if ( v74 != a2 )
    {
      if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))a2->lpVtbl->QueryInterface)(
             a2,
             &GUID_03428aab_4138_4dcf_872e_61801b6a3e2f,
             &v74) < 0 )
        v74 = 0;
      if ( v20 )
        ((void (__fastcall *)(struct IUnknown *))v20->lpVtbl->Release)(v20);
    }
  }
  v71 = 0;
  if ( *(_QWORD *)std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::find(
                    (char *)v6 + 696,
                    v70) != *((_QWORD *)v6 + 88) )
  {
    v21 = v71;
    if ( v71 != a2 )
    {
      if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))a2->lpVtbl->QueryInterface)(
             a2,
             &GUID_c511b1c5_6aa1_4e84_a6f8_17c7f344eafe,
             &v71) < 0 )
        v71 = 0;
      if ( v21 )
        ((void (__fastcall *)(struct IUnknown *))v21->lpVtbl->Release)(v21);
    }
  }
  v73 = 0;
  if ( *(_QWORD *)std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::find(
                    (char *)v6 + 696,
                    v67) != *((_QWORD *)v6 + 88) )
  {
    v22 = v73;
    if ( v73 != a2 )
    {
      if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))a2->lpVtbl->QueryInterface)(
             a2,
             &GUID_dcf46f4d_76aa_4883_8a48_e3af8cbd15aa,
             &v73) < 0 )
        v73 = 0;
      if ( v22 )
        ((void (__fastcall *)(struct IUnknown *))v22->lpVtbl->Release)(v22);
    }
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    if ( v79 )
    {
      v60[0] = (struct _GUID *)((char *)v6 + 112);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 112));
      v23 = v79;
      v70[0] = v79;
      v68[0] = (unsigned __int16 *)v79;
      if ( v79 )
      {
        ((void (__fastcall *)(struct IUnknown *))v79->lpVtbl->AddRef)(v79);
        v23 = (struct IUnknown *)v70[0];
      }
      LOBYTE(v68[1]) = 0;
      v24 = *((_QWORD *)v6 + 20);
      if ( v24 == *((_QWORD *)v6 + 21) )
      {
        std::vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorEtwAgent>>::_Emplace_reallocate<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorEtwAgent>>(
          (char *)v6 + 152,
          *((_QWORD *)v6 + 20),
          v68);
        v25 = v68[0];
      }
      else
      {
        v25 = 0;
        *(_QWORD *)v24 = v23;
        *(_BYTE *)(v24 + 8) = 0;
        *((_QWORD *)v6 + 20) += 16LL;
      }
      if ( v25 )
        (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v25 + 16LL))(v25);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 112));
    }
    if ( v78 )
    {
      v60[0] = (struct _GUID *)((char *)v6 + 176);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 176));
      v68[0] = (unsigned __int16 *)v78;
      if ( v78 )
        ((void (__fastcall *)(struct IUnknown *))v78->lpVtbl->AddRef)(v78);
      LOBYTE(v68[1]) = 0;
      v26 = a3;
      std::_Hash<std::_Umap_traits<_GUID,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>,0>>::emplace<_GUID const &,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>(
        (char *)v6 + 216,
        v70,
        a3,
        v68);
      if ( v68[0] )
        (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v68[0] + 16LL))(v68[0]);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 176));
    }
    else
    {
      v26 = a3;
    }
    if ( v77 )
    {
      v60[0] = (struct _GUID *)((char *)v6 + 280);
      EnterCriticalSection((LPCRITICAL_SECTION)v6 + 7);
      v68[0] = (unsigned __int16 *)v77;
      if ( v77 )
        ((void (__fastcall *)(struct IUnknown *))v77->lpVtbl->AddRef)(v77);
      LOBYTE(v68[1]) = 0;
      std::_Hash<std::_Umap_traits<_GUID,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>,0>>::emplace<_GUID const &,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>(
        (char *)v6 + 320,
        v70,
        v26,
        v68);
      if ( v68[0] )
        (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v68[0] + 16LL))(v68[0]);
      LeaveCriticalSection((LPCRITICAL_SECTION)v6 + 7);
    }
    if ( v76 )
    {
      v60[0] = (struct _GUID *)((char *)v6 + 384);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 384));
      v27 = v76;
      v70[0] = v76;
      v68[0] = (unsigned __int16 *)v76;
      if ( v76 )
      {
        ((void (__fastcall *)(struct IUnknown *))v76->lpVtbl->AddRef)(v76);
        v27 = (struct IUnknown *)v70[0];
      }
      LOBYTE(v68[1]) = 0;
      v28 = *((_QWORD *)v6 + 54);
      if ( v28 == *((_QWORD *)v6 + 55) )
      {
        std::vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorEtwAgent>>::_Emplace_reallocate<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorEtwAgent>>(
          (char *)v6 + 424,
          *((_QWORD *)v6 + 54),
          v68);
        v29 = v68[0];
      }
      else
      {
        v29 = 0;
        *(_QWORD *)v28 = v27;
        *(_BYTE *)(v28 + 8) = 0;
        *((_QWORD *)v6 + 54) += 16LL;
      }
      if ( v29 )
        (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v29 + 16LL))(v29);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 384));
    }
    if ( v75 )
    {
      v60[0] = (struct _GUID *)((char *)v6 + 512);
      LODWORD(v60[1]) = 1;
      AcquireSRWLockExclusive((PSRWLOCK)v6 + 64);
      v30 = v75;
      v68[0] = (unsigned __int16 *)v75;
      if ( v75 )
        ((void (__fastcall *)(struct IUnknown *))v75->lpVtbl->AddRef)(v75);
      LOBYTE(v68[1]) = 0;
      v31 = *((_QWORD *)v6 + 66);
      if ( v31 == *((_QWORD *)v6 + 67) )
      {
        std::vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorEtwAgent>>::_Emplace_reallocate<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorEtwAgent>>(
          (char *)v6 + 520,
          v31,
          v68);
        v32 = v68[0];
      }
      else
      {
        v32 = 0;
        *(_QWORD *)v31 = v30;
        *(_BYTE *)(v31 + 8) = 0;
        *((_QWORD *)v6 + 66) += 16LL;
      }
      if ( v32 )
        (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v32 + 16LL))(v32);
      ReleaseSRWLockExclusive((PSRWLOCK)v6 + 64);
    }
    if ( v74 )
    {
      v60[0] = (struct _GUID *)((char *)v6 + 448);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 448));
      v33 = v74;
      v70[0] = v74;
      v68[0] = (unsigned __int16 *)v74;
      if ( v74 )
      {
        ((void (__fastcall *)(struct IUnknown *))v74->lpVtbl->AddRef)(v74);
        v33 = (struct IUnknown *)v70[0];
      }
      LOBYTE(v68[1]) = 0;
      v34 = *((_QWORD *)v6 + 62);
      if ( v34 == *((_QWORD *)v6 + 63) )
      {
        std::vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorEtwAgent>>::_Emplace_reallocate<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorEtwAgent>>(
          (char *)v6 + 488,
          *((_QWORD *)v6 + 62),
          v68);
        v35 = v68[0];
      }
      else
      {
        v35 = 0;
        *(_QWORD *)v34 = v33;
        *(_BYTE *)(v34 + 8) = 0;
        *((_QWORD *)v6 + 62) += 16LL;
      }
      if ( v35 )
        (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v35 + 16LL))(v35);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 448));
    }
    if ( v71 )
    {
      v60[0] = (struct _GUID *)((char *)v6 + 544);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 544));
      v36 = v71;
      v70[0] = v71;
      v68[0] = (unsigned __int16 *)v71;
      if ( v71 )
      {
        ((void (__fastcall *)(struct IUnknown *))v71->lpVtbl->AddRef)(v71);
        v36 = (struct IUnknown *)v70[0];
      }
      LOBYTE(v68[1]) = 0;
      v37 = *((_QWORD *)v6 + 74);
      if ( v37 == *((_QWORD *)v6 + 75) )
      {
        std::vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorEtwAgent>>::_Emplace_reallocate<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorEtwAgent>>(
          (char *)v6 + 584,
          *((_QWORD *)v6 + 74),
          v68);
        v38 = v68[0];
      }
      else
      {
        v38 = 0;
        *(_QWORD *)v37 = v36;
        *(_BYTE *)(v37 + 8) = 0;
        *((_QWORD *)v6 + 74) += 16LL;
      }
      if ( v38 )
        (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v38 + 16LL))(v38);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 544));
    }
    if ( v73 )
    {
      v60[0] = (struct _GUID *)((char *)v6 + 608);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 608));
      v39 = v73;
      v70[0] = v73;
      v68[0] = (unsigned __int16 *)v73;
      if ( v73 )
      {
        ((void (__fastcall *)(struct IUnknown *))v73->lpVtbl->AddRef)(v73);
        v39 = (struct IUnknown *)v70[0];
      }
      LOBYTE(v68[1]) = 0;
      v40 = *((_QWORD *)v6 + 82);
      if ( v40 == *((_QWORD *)v6 + 83) )
      {
        std::vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorEtwAgent>>::_Emplace_reallocate<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorEtwAgent>>(
          (char *)v6 + 648,
          *((_QWORD *)v6 + 82),
          v68);
        v41 = v68[0];
      }
      else
      {
        v41 = 0;
        *(_QWORD *)v40 = v39;
        *(_BYTE *)(v40 + 8) = 0;
        *((_QWORD *)v6 + 82) += 16LL;
      }
      if ( v41 )
        (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v41 + 16LL))(v41);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 608));
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      v10 = v63;
      v42 = -2147024882;
      v7 = v64;
      v6 = v64;
      v43 = v65;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18000EFC0);
      goto LABEL_153;
    }
  }
  if ( v66 )
  {
    if ( *((_QWORD *)_logger + 7) != *((_QWORD *)_logger + 8) )
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 56),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\AgentController.cpp",
        L"Configuring agent (%s) with [%s]",
        sz,
        v66);
    v70[0] = 0;
    v42 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, _QWORD *))a2->lpVtbl->QueryInterface)(
            a2,
            &GUID_f19420fa_4409_4127_bb8f_72cf164e9009,
            v70);
    if ( v42 < 0 )
    {
      if ( v70[0] )
        (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v70[0] + 16LL))(v70[0], *(_QWORD *)v70[0]);
      goto LABEL_152;
    }
    v42 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *))(*(_QWORD *)v70[0] + 24LL))(v70[0], v66);
    if ( v42 < 0 )
    {
      if ( v70[0] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v70[0] + 16LL))(v70[0]);
      goto LABEL_152;
    }
    if ( v70[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v70[0] + 16LL))(v70[0]);
  }
  v42 = (*(__int64 (__fastcall **)(unsigned __int16 *, _QWORD))(*(_QWORD *)v72 + 24LL))(v72, *((_QWORD *)v6 + 85));
  if ( v42 < 0 )
  {
LABEL_152:
    v43 = a3;
LABEL_153:
    if ( *((_QWORD *)_logger + 21) != *((_QWORD *)_logger + 22) )
    {
      LODWORD(v58) = v42;
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 168),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\AgentController.cpp",
        L"Failed to load agent (%s) (HRESULT: %#08x)",
        sz,
        v58);
    }
    if ( v79 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 112));
      v44 = *(_QWORD *)(*((_QWORD *)v7 + 20) - 16LL);
      if ( v44 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
      *((_QWORD *)v7 + 20) -= 16LL;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 112));
    }
    if ( v78 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 176));
      std::_Hash<std::_Umap_traits<_GUID,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>,0>>::erase(
        (char *)v6 + 216,
        v43);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 176));
    }
    if ( v77 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)v6 + 7);
      std::_Hash<std::_Umap_traits<_GUID,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>,0>>::erase(
        (char *)v6 + 320,
        v43);
      LeaveCriticalSection((LPCRITICAL_SECTION)v6 + 7);
    }
    if ( v76 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 384));
      v45 = *(_QWORD *)(*((_QWORD *)v7 + 54) - 16LL);
      if ( v45 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
      *((_QWORD *)v7 + 54) -= 16LL;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 384));
    }
    if ( v75 )
    {
      AcquireSRWLockExclusive((PSRWLOCK)v6 + 64);
      v46 = *(_QWORD *)(*((_QWORD *)v7 + 66) - 16LL);
      if ( v46 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
      *((_QWORD *)v7 + 66) -= 16LL;
      ReleaseSRWLockExclusive((PSRWLOCK)v6 + 64);
    }
    if ( v74 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 448));
      v47 = *(_QWORD *)(*((_QWORD *)v7 + 62) - 16LL);
      if ( v47 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
      *((_QWORD *)v7 + 62) -= 16LL;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 448));
    }
    v48 = v71;
    if ( v71 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 544));
      v49 = *(_QWORD *)(*((_QWORD *)v7 + 74) - 16LL);
      if ( v49 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
      *((_QWORD *)v7 + 74) -= 16LL;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 544));
      v48 = v71;
    }
    v50 = v73;
    if ( v73 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 608));
      v51 = *(_QWORD *)(*((_QWORD *)v7 + 82) - 16LL);
      if ( v51 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
      *((_QWORD *)v7 + 82) -= 16LL;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 608));
      v48 = v71;
      v50 = v73;
    }
    ModulePath = -518979515;
    if ( v42 == -518979515 )
    {
      if ( v50 )
      {
        ((void (__fastcall *)(struct IUnknown *))v50->lpVtbl->Release)(v50);
        v48 = v71;
      }
      if ( v48 )
        ((void (__fastcall *)(struct IUnknown *))v48->lpVtbl->Release)(v48);
      if ( v74 )
        ((void (__fastcall *)(struct IUnknown *))v74->lpVtbl->Release)(v74);
      if ( v75 )
        ((void (__fastcall *)(struct IUnknown *))v75->lpVtbl->Release)(v75);
      if ( v76 )
        ((void (__fastcall *)(struct IUnknown *))v76->lpVtbl->Release)(v76);
      if ( v77 )
        ((void (__fastcall *)(struct IUnknown *))v77->lpVtbl->Release)(v77);
      if ( v78 )
        ((void (__fastcall *)(struct IUnknown *))v78->lpVtbl->Release)(v78);
      if ( v79 )
        ((void (__fastcall *)(struct IUnknown *))v79->lpVtbl->Release)(v79);
      if ( v80 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
      LeaveCriticalSection(v10);
      if ( v72 )
        (*(void (__fastcall **)(unsigned __int16 *, _QWORD))(*(_QWORD *)v72 + 16LL))(v72, *(_QWORD *)v72);
    }
    else
    {
      v82[0] = sz;
      v82[1] = (void *)v42;
      v62[0] = 0;
      v62[1] = (struct _GUID *)3775987785LL;
      DiagHubCommon::HResultFormatter::Init(
        (DiagHubCommon::HResultFormatter *)v62,
        *((_WORD *)v6 + 336),
        -518979511,
        (const void **const)v82);
      v57 = (const struct _GUID *)L"<unknown error>";
      if ( v62[0] )
        v57 = v62[0];
      DiagHubCommon::SetErrorInfo((DiagHubCommon *)&IID_ICollectionSession, v57, v56);
      ModulePath = (int)v62[1];
      DiagHubCommon::HResultFormatter::~HResultFormatter((DiagHubCommon::HResultFormatter *)v62);
      if ( v73 )
        ((void (__fastcall *)(struct IUnknown *))v73->lpVtbl->Release)(v73);
      if ( v71 )
        ((void (__fastcall *)(struct IUnknown *))v71->lpVtbl->Release)(v71);
      if ( v74 )
        ((void (__fastcall *)(struct IUnknown *))v74->lpVtbl->Release)(v74);
      if ( v75 )
        ((void (__fastcall *)(struct IUnknown *))v75->lpVtbl->Release)(v75);
      if ( v76 )
        ((void (__fastcall *)(struct IUnknown *))v76->lpVtbl->Release)(v76);
      if ( v77 )
        ((void (__fastcall *)(struct IUnknown *))v77->lpVtbl->Release)(v77);
      if ( v78 )
        ((void (__fastcall *)(struct IUnknown *))v78->lpVtbl->Release)(v78);
      if ( v79 )
        ((void (__fastcall *)(struct IUnknown *))v79->lpVtbl->Release)(v79);
      if ( v80 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
      LeaveCriticalSection(v10);
      if ( v72 )
        (*(void (__fastcall **)(unsigned __int16 *, _QWORD))(*(_QWORD *)v72 + 16LL))(v72, *(_QWORD *)v72);
    }
    return (unsigned int)ModulePath;
  }
  if ( __eh34_try(-1, 2) )
  {
    __eh34_scope_strut(2);
    v52 = (struct _RTL_CRITICAL_SECTION *)((char *)v6 + 48);
    v60[0] = (struct _GUID *)((char *)v6 + 48);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 48));
    v53 = v72;
    v68[0] = v72;
    if ( v72 )
      (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v72 + 8LL))(v72);
    LOBYTE(v68[1]) = 0;
    v54 = *((_QWORD *)v7 + 12);
    if ( v54 == *((_QWORD *)v7 + 13) )
    {
      std::vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorEtwAgent>>::_Emplace_reallocate<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorEtwAgent>>(
        (char *)v7 + 88,
        v54,
        v68);
      v55 = v68[0];
    }
    else
    {
      v55 = 0;
      *(_QWORD *)v54 = v53;
      *(_BYTE *)(v54 + 8) = 0;
      *((_QWORD *)v7 + 12) += 16LL;
    }
    if ( v55 )
      (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v55 + 16LL))(v55);
    LeaveCriticalSection(v52);
  }
  if ( __eh34_catch(2) )
  {
    if ( __eh34_catch_type(2, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      v10 = v63;
      v42 = -2147024882;
      v7 = v64;
      v6 = v64;
      v43 = v65;
      __eh34_try_continuation(2, &std::bad_alloc `RTTI Type Descriptor', &loc_18000EFC0);
      goto LABEL_153;
    }
  }
  if ( *(_QWORD *)_logger != *((_QWORD *)_logger + 1) )
    DiagHubCommon::LogStream::Write(
      _logger,
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\AgentController.cpp",
      L"Loaded agent (%s)",
      sz);
  if ( v73 )
    ((void (__fastcall *)(struct IUnknown *))v73->lpVtbl->Release)(v73);
  if ( v71 )
    ((void (__fastcall *)(struct IUnknown *))v71->lpVtbl->Release)(v71);
  if ( v74 )
    ((void (__fastcall *)(struct IUnknown *))v74->lpVtbl->Release)(v74);
  if ( v75 )
    ((void (__fastcall *)(struct IUnknown *))v75->lpVtbl->Release)(v75);
  if ( v76 )
    ((void (__fastcall *)(struct IUnknown *))v76->lpVtbl->Release)(v76);
  if ( v77 )
    ((void (__fastcall *)(struct IUnknown *))v77->lpVtbl->Release)(v77);
  if ( v78 )
    ((void (__fastcall *)(struct IUnknown *))v78->lpVtbl->Release)(v78);
  if ( v79 )
    ((void (__fastcall *)(struct IUnknown *))v79->lpVtbl->Release)(v79);
  if ( v80 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
  LeaveCriticalSection(v10);
  if ( v72 )
    (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v72 + 16LL))(v72);
  return 0;
}

```

## disassembly

```asm
0x18000dd60  push    rbx
0x18000dd62  push    rsi
0x18000dd63  push    rdi
0x18000dd64  push    r12
0x18000dd66  push    r13
0x18000dd68  push    r14
0x18000dd6a  push    r15
0x18000dd6c  sub     rsp, 210h
0x18000dd73  mov     rax, cs:__security_cookie
0x18000dd7a  xor     rax, rsp
0x18000dd7d  mov     [rsp+248h+var_48], rax
0x18000dd85  mov     [rsp+248h+var_1C8], r9
0x18000dd8d  mov     rbx, r8
0x18000dd90  mov     [rsp+248h+var_218], rbx
0x18000dd95  mov     r12, rdx
0x18000dd98  mov     r15, rcx
0x18000dd9b  mov     r14, rcx
0x18000dd9e  mov     [rsp+248h+var_1E0], rcx
0x18000dda3  mov     [rsp+248h+var_1D0], rbx
0x18000dda8  mov     al, [rcx+2B1h]
0x18000ddae  xor     esi, esi
0x18000ddb0  test    al, al
0x18000ddb2  jz      short loc_18000DDBE
0x18000ddb4  mov     eax, 0E1110013h
0x18000ddb9  jmp     loc_18000F173
0x18000ddbe  test    r12, r12
0x18000ddc1  jnz     short loc_18000DDCD
0x18000ddc3  mov     eax, 80004003h
0x18000ddc8  jmp     loc_18000F173
0x18000ddcd  cmp     [rcx+2A8h], rsi
0x18000ddd4  jnz     short loc_18000DDE0
0x18000ddd6  mov     eax, 8007139Fh
0x18000dddb  jmp     loc_18000F173
0x18000dde0  mov     [rsp+248h+var_188], rsi
0x18000dde8  mov     rax, [rdx]
0x18000ddeb  lea     r8, [rsp+248h+var_188]
0x18000ddf3  lea     rdx, _GUID_bb4a877f_85a4_4891_b7fe_6b28d1c1b059
0x18000ddfa  mov     rcx, r12
0x18000ddfd  mov     rax, [rax]
0x18000de00  call    cs:__guard_dispatch_icall_fptr
0x18000de06  test    eax, eax
0x18000de08  jns     short loc_18000DE17
0x18000de0a  mov     rax, rsi
0x18000de0d  mov     [rsp+248h+var_188], rax
0x18000de15  jmp     short loc_18000DE1F
0x18000de17  mov     rax, [rsp+248h+var_188]
0x18000de1f  test    rax, rax
0x18000de22  jnz     short loc_18000DE2E
0x18000de24  mov     eax, 80070057h
0x18000de29  jmp     loc_18000F173
0x18000de2e  mov     r8d, 27h ; '''; cchMax
0x18000de34  lea     rdx, [rsp+248h+sz]; lpsz
0x18000de3c  mov     rcx, rbx; rguid
0x18000de3f  call    cs:__imp_StringFromGUID2
0x18000de45  test    eax, eax
0x18000de47  jz      loc_18000F196
0x18000de4d  mov     [rsp+248h+var_EA], si
0x18000de55  mov     [rsp+248h+var_9C], si
0x18000de5d  lea     rdi, [r15+8]
0x18000de61  mov     [rsp+248h+var_1E8], rdi
0x18000de66  mov     rcx, rdi; lpCriticalSection
0x18000de69  call    cs:__imp_EnterCriticalSection
0x18000de6f  nop
0x18000de70  mov     [rsp+248h+var_148], rsi
0x18000de78  mov     rax, [r12]
0x18000de7c  lea     r8, [rsp+248h+var_148]
0x18000de84  lea     rdx, _GUID_7903a98d_7a1d_475f_a5f2_18b5d1a53787
0x18000de8b  mov     rcx, r12
0x18000de8e  mov     rax, [rax]
0x18000de91  call    cs:__guard_dispatch_icall_fptr
0x18000de97  test    eax, eax
0x18000de99  jns     short loc_18000DEA8
0x18000de9b  mov     rax, rsi
0x18000de9e  mov     [rsp+248h+var_148], rax
0x18000dea6  jmp     short loc_18000DEB0
0x18000dea8  mov     rax, [rsp+248h+var_148]
0x18000deb0  test    rax, rax
0x18000deb3  jz      loc_18000DFEF
0x18000deb9  mov     al, [r15+2B0h]
0x18000dec0  test    al, al
0x18000dec2  jnz     loc_18000DFEF
0x18000dec8  xorps   xmm1, xmm1
0x18000decb  movdqu  xmmword ptr [rsp+248h+var_1B8], xmm1
0x18000ded4  mov     [rsp+248h+var_1A8], rsi
0x18000dedc  lea     rdx, [rsp+248h+var_1B8]
0x18000dee4  xor     ecx, ecx; hModule
0x18000dee6  call    ?GetModulePath@ModulePath@DiagHubCommon@@SAJPEAUHINSTANCE__@@AEAV?$vector@GV?$allocator@G@std@@@std@@@Z; DiagHubCommon::ModulePath::GetModulePath(HINSTANCE__ *,std::vector<ushort> &)
0x18000deeb  mov     ebx, eax
0x18000deed  test    eax, eax
0x18000deef  jns     short loc_18000DF47
0x18000def1  lfence
0x18000def4  lea     rcx, [rsp+248h+var_1B8]
0x18000defc  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18000df01  nop
0x18000df02  mov     rcx, [rsp+248h+var_148]
0x18000df0a  test    rcx, rcx
0x18000df0d  jz      short loc_18000DF1D
0x18000df0f  mov     rax, [rcx]
0x18000df12  mov     rax, [rax+10h]
0x18000df16  call    cs:__guard_dispatch_icall_fptr
0x18000df1c  nop
0x18000df1d  mov     rcx, rdi; lpCriticalSection
0x18000df20  call    cs:__imp_LeaveCriticalSection
0x18000df26  nop
0x18000df27  mov     rcx, [rsp+248h+var_188]
0x18000df2f  test    rcx, rcx
0x18000df32  jz      short loc_18000DF42
0x18000df34  mov     rax, [rcx]
0x18000df37  mov     rax, [rax+10h]
0x18000df3b  call    cs:__guard_dispatch_icall_fptr
0x18000df41  nop
0x18000df42  jmp     loc_18000F171
0x18000df47  xorps   xmm0, xmm0
0x18000df4a  movups  xmmword ptr [rsp+248h+var_210], xmm0
0x18000df4f  movzx   r9d, word ptr [r15+2A0h]; unsigned __int16
0x18000df57  mov     r8, [rsp+248h+var_1B8]; unsigned __int16 *
0x18000df5f  mov     edx, 0E1110057h; int
0x18000df64  lea     rcx, [rsp+248h+var_210]; this
0x18000df69  call    ??0HResultFormatter@DiagHubCommon@@QEAA@JPEBGG@Z; DiagHubCommon::HResultFormatter::HResultFormatter(long,ushort const *,ushort)
0x18000df6e  nop
0x18000df6f  lea     rdx, aUnknownError; "<unknown error>"
0x18000df76  cmp     [rsp+248h+var_210], rsi
0x18000df7b  cmovnz  rdx, [rsp+248h+var_210]; struct _GUID *
0x18000df81  lea     rcx, IID_ICollectionSession; this
0x18000df88  call    ?SetErrorInfo@DiagHubCommon@@YAXAEBU_GUID@@PEBG@Z; DiagHubCommon::SetErrorInfo(_GUID const &,ushort const *)
0x18000df8d  mov     ebx, dword ptr [rsp+248h+var_210+8]
0x18000df91  lea     rcx, [rsp+248h+var_210]; this
0x18000df96  call    ??1HResultFormatter@DiagHubCommon@@QEAA@XZ; DiagHubCommon::HResultFormatter::~HResultFormatter(void)
0x18000df9b  nop
0x18000df9c  lea     rcx, [rsp+248h+var_1B8]
0x18000dfa4  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18000dfa9  nop
0x18000dfaa  mov     rcx, [rsp+248h+var_148]
0x18000dfb2  test    rcx, rcx
0x18000dfb5  jz      short loc_18000DFC5
0x18000dfb7  mov     rax, [rcx]
0x18000dfba  mov     rax, [rax+10h]
0x18000dfbe  call    cs:__guard_dispatch_icall_fptr
0x18000dfc4  nop
0x18000dfc5  mov     rcx, rdi; lpCriticalSection
0x18000dfc8  call    cs:__imp_LeaveCriticalSection
0x18000dfce  nop
0x18000dfcf  mov     rcx, [rsp+248h+var_188]
0x18000dfd7  test    rcx, rcx
0x18000dfda  jz      short loc_18000DFEA
0x18000dfdc  mov     rdx, [rcx]
0x18000dfdf  mov     rax, [rdx+10h]
0x18000dfe3  call    cs:__guard_dispatch_icall_fptr
0x18000dfe9  nop
0x18000dfea  jmp     loc_18000F171
0x18000dfef  mov     [rsp+248h+var_150], rsi
0x18000dff7  lea     r13, [r15+2B8h]
0x18000dffe  lea     r8, _GUID_5793882a_6078_47c4_8197_c970a79c5121
0x18000e005  lea     rdx, [rsp+248h+var_1A0]
0x18000e00d  mov     rcx, r13
0x18000e010  call    ?find@?$_Hash@V?$_Umap_traits@U_GUID@@HV?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@H@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::find(_GUID const &)
0x18000e015  mov     rcx, [r15+2C0h]
0x18000e01c  cmp     [rax], rcx
0x18000e01f  jz      short loc_18000E06F
0x18000e021  mov     rbx, [rsp+248h+var_150]
0x18000e029  cmp     rbx, r12
0x18000e02c  jz      short loc_18000E06F
0x18000e02e  mov     rax, [r12]
0x18000e032  lea     r8, [rsp+248h+var_150]
0x18000e03a  lea     rdx, _GUID_5793882a_6078_47c4_8197_c970a79c5121
0x18000e041  mov     rcx, r12
0x18000e044  mov     rax, [rax]
0x18000e047  call    cs:__guard_dispatch_icall_fptr
0x18000e04d  test    eax, eax
0x18000e04f  jns     short loc_18000E059
0x18000e051  mov     [rsp+248h+var_150], rsi
0x18000e059  test    rbx, rbx
0x18000e05c  jz      short loc_18000E06F
0x18000e05e  mov     rax, [rbx]
0x18000e061  mov     rcx, rbx
0x18000e064  mov     rax, [rax+10h]
0x18000e068  call    cs:__guard_dispatch_icall_fptr
0x18000e06e  nop
0x18000e06f  mov     [rsp+248h+var_158], rsi
0x18000e077  lea     r8, _GUID_fda07c49_142b_4f04_ac7b_7c77fc86fd94
0x18000e07e  lea     rdx, [rsp+248h+var_1A0]
0x18000e086  mov     rcx, r13
0x18000e089  call    ?find@?$_Hash@V?$_Umap_traits@U_GUID@@HV?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@H@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::find(_GUID const &)
0x18000e08e  mov     rcx, [r15+2C0h]
0x18000e095  cmp     [rax], rcx
0x18000e098  jz      short loc_18000E0E8
0x18000e09a  mov     rbx, [rsp+248h+var_158]
0x18000e0a2  cmp     rbx, r12
0x18000e0a5  jz      short loc_18000E0E8
0x18000e0a7  mov     rax, [r12]
0x18000e0ab  lea     r8, [rsp+248h+var_158]
0x18000e0b3  lea     rdx, _GUID_fda07c49_142b_4f04_ac7b_7c77fc86fd94
0x18000e0ba  mov     rcx, r12
0x18000e0bd  mov     rax, [rax]
0x18000e0c0  call    cs:__guard_dispatch_icall_fptr
0x18000e0c6  test    eax, eax
0x18000e0c8  jns     short loc_18000E0D2
0x18000e0ca  mov     [rsp+248h+var_158], rsi
0x18000e0d2  test    rbx, rbx
0x18000e0d5  jz      short loc_18000E0E8
0x18000e0d7  mov     rax, [rbx]
0x18000e0da  mov     rcx, rbx
0x18000e0dd  mov     rax, [rax+10h]
0x18000e0e1  call    cs:__guard_dispatch_icall_fptr
0x18000e0e7  nop
0x18000e0e8  mov     [rsp+248h+var_160], rsi
0x18000e0f0  lea     r8, _GUID_c1392ad2_d0cb_4daa_84a2_1eb740c8f322
0x18000e0f7  lea     rdx, [rsp+248h+var_1A0]
0x18000e0ff  mov     rcx, r13
0x18000e102  call    ?find@?$_Hash@V?$_Umap_traits@U_GUID@@HV?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@H@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::find(_GUID const &)
0x18000e107  mov     rcx, [r15+2C0h]
0x18000e10e  cmp     [rax], rcx
0x18000e111  jz      short loc_18000E161
0x18000e113  mov     rbx, [rsp+248h+var_160]
0x18000e11b  cmp     rbx, r12
0x18000e11e  jz      short loc_18000E161
0x18000e120  mov     rax, [r12]
0x18000e124  lea     r8, [rsp+248h+var_160]
0x18000e12c  lea     rdx, _GUID_c1392ad2_d0cb_4daa_84a2_1eb740c8f322
0x18000e133  mov     rcx, r12
0x18000e136  mov     rax, [rax]
0x18000e139  call    cs:__guard_dispatch_icall_fptr
0x18000e13f  test    eax, eax
0x18000e141  jns     short loc_18000E14B
0x18000e143  mov     [rsp+248h+var_160], rsi
0x18000e14b  test    rbx, rbx
0x18000e14e  jz      short loc_18000E161
0x18000e150  mov     rax, [rbx]
0x18000e153  mov     rcx, rbx
0x18000e156  mov     rax, [rax+10h]
0x18000e15a  call    cs:__guard_dispatch_icall_fptr
0x18000e160  nop
0x18000e161  mov     [rsp+248h+var_168], rsi
0x18000e169  lea     r8, _GUID_971bfd3c_85ad_483f_891c_01ef37ba361a
0x18000e170  lea     rdx, [rsp+248h+var_1A0]
0x18000e178  mov     rcx, r13
0x18000e17b  call    ?find@?$_Hash@V?$_Umap_traits@U_GUID@@HV?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@H@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::find(_GUID const &)
0x18000e180  mov     rcx, [r15+2C0h]
0x18000e187  cmp     [rax], rcx
0x18000e18a  jz      short loc_18000E1DA
0x18000e18c  mov     rbx, [rsp+248h+var_168]
0x18000e194  cmp     rbx, r12
0x18000e197  jz      short loc_18000E1DA
0x18000e199  mov     rax, [r12]
0x18000e19d  lea     r8, [rsp+248h+var_168]
0x18000e1a5  lea     rdx, _GUID_971bfd3c_85ad_483f_891c_01ef37ba361a
0x18000e1ac  mov     rcx, r12
0x18000e1af  mov     rax, [rax]
0x18000e1b2  call    cs:__guard_dispatch_icall_fptr
0x18000e1b8  test    eax, eax
0x18000e1ba  jns     short loc_18000E1C4
0x18000e1bc  mov     [rsp+248h+var_168], rsi
0x18000e1c4  test    rbx, rbx
0x18000e1c7  jz      short loc_18000E1DA
0x18000e1c9  mov     rax, [rbx]
0x18000e1cc  mov     rcx, rbx
0x18000e1cf  mov     rax, [rax+10h]
0x18000e1d3  call    cs:__guard_dispatch_icall_fptr
0x18000e1d9  nop
0x18000e1da  mov     [rsp+248h+var_170], rsi
0x18000e1e2  lea     r8, _GUID_42e43569_8c6d_44a5_9fa6_ec7db18033eb
0x18000e1e9  lea     rdx, [rsp+248h+var_1A0]
0x18000e1f1  mov     rcx, r13
0x18000e1f4  call    ?find@?$_Hash@V?$_Umap_traits@U_GUID@@HV?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@H@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::find(_GUID const &)
0x18000e1f9  mov     rcx, [r15+2C0h]
0x18000e200  cmp     [rax], rcx
0x18000e203  jz      short loc_18000E253
0x18000e205  mov     rbx, [rsp+248h+var_170]
0x18000e20d  cmp     rbx, r12
0x18000e210  jz      short loc_18000E253
0x18000e212  mov     rax, [r12]
0x18000e216  lea     r8, [rsp+248h+var_170]
0x18000e21e  lea     rdx, _GUID_42e43569_8c6d_44a5_9fa6_ec7db18033eb
0x18000e225  mov     rcx, r12
0x18000e228  mov     rax, [rax]
0x18000e22b  call    cs:__guard_dispatch_icall_fptr
0x18000e231  test    eax, eax
0x18000e233  jns     short loc_18000E23D
0x18000e235  mov     [rsp+248h+var_170], rsi
0x18000e23d  test    rbx, rbx
0x18000e240  jz      short loc_18000E253
0x18000e242  mov     rax, [rbx]
0x18000e245  mov     rcx, rbx
0x18000e248  mov     rax, [rax+10h]
0x18000e24c  call    cs:__guard_dispatch_icall_fptr
0x18000e252  nop
0x18000e253  mov     [rsp+248h+var_178], rsi
0x18000e25b  lea     r8, _GUID_03428aab_4138_4dcf_872e_61801b6a3e2f
0x18000e262  lea     rdx, [rsp+248h+var_1A0]
0x18000e26a  mov     rcx, r13
0x18000e26d  call    ?find@?$_Hash@V?$_Umap_traits@U_GUID@@HV?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@H@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::find(_GUID const &)
0x18000e272  mov     rcx, [r15+2C0h]
0x18000e279  cmp     [rax], rcx
0x18000e27c  jz      short loc_18000E2CC
0x18000e27e  mov     rbx, [rsp+248h+var_178]
0x18000e286  cmp     rbx, r12
0x18000e289  jz      short loc_18000E2CC
0x18000e28b  mov     rax, [r12]
0x18000e28f  lea     r8, [rsp+248h+var_178]
0x18000e297  lea     rdx, _GUID_03428aab_4138_4dcf_872e_61801b6a3e2f
  ... truncated ...
```
