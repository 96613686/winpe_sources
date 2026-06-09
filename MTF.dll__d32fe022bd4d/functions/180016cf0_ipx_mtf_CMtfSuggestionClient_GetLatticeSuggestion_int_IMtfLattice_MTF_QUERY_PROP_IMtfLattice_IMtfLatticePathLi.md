# ipx::mtf::CMtfSuggestionClient::GetLatticeSuggestion(int,IMtfLattice *,_MTF_QUERY_PROP *,IMtfLattice * *,IMtfLatticePathList * *)

- ea: `0x180016cf0`
- end: `0x180017a2d`
- name: `?GetLatticeSuggestion@CMtfSuggestionClient@mtf@ipx@@UEAAJHPEAUIMtfLattice@@PEAU_MTF_QUERY_PROP@@PEAPEAU4@PEAPEAUIMtfLatticePathList@@@Z`
- size: `3389`
- prototype: `int(ipx::mtf::CMtfSuggestionClient *__hidden this, int, struct IMtfLattice *, struct _MTF_QUERY_PROP *, struct IMtfLattice **, struct IMtfLatticePathList **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180006074`
- `0x180016cf0`
- `0x180019b00`
- `0x18001d1f4`
- `0x18001dbb4`
- `0x18002bc62`
- `0x18002bca0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016d54`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016d71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016e2b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016ed5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016f77`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017037`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017152`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017222`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800172e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800173d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800174b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800175a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017668`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017764`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017855`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017961`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800179fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016d54`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016d71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016e2b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016ed5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016f77`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017037`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017152`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017222`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800172e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800173d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800174b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800175a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017668`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017764`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017855`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017961`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800179fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016d37`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016d37`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
__int64 __fastcall ipx::mtf::CMtfSuggestionClient::GetLatticeSuggestion(
        ipx::mtf::CMtfSuggestionClient *this,
        int a2,
        struct IMtfLattice *a3,
        struct _MTF_QUERY_PROP *a4,
        struct IMtfLattice **a5,
        struct IMtfLatticePathList **a6)
{
  struct IMtfSuggestionInputQuery *v10; // rbx
  int v12; // eax
  unsigned int v13; // edi
  struct IMtfSuggestionInputQuery *v14; // rdi
  int v15; // eax
  unsigned int v16; // esi
  struct IMtfPropertyBag *v17; // rcx
  int v18; // eax
  unsigned int v19; // esi
  struct IMtfPropertyBag *v20; // rcx
  int v21; // eax
  unsigned int v22; // esi
  __int64 v23; // rcx
  struct IMtfPropertyBag *v24; // rcx
  __int64 v25; // r8
  int v26; // eax
  unsigned int v27; // esi
  __int64 (__fastcall ***v28)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v29; // rcx
  struct IMtfPropertyBag *v30; // rcx
  __int64 v31; // rcx
  int v32; // eax
  unsigned int v33; // esi
  __int64 (__fastcall ***v34)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v35; // rcx
  struct IMtfPropertyBag *v36; // rcx
  int v37; // eax
  unsigned int v38; // esi
  __int64 (__fastcall ***v39)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v40; // rcx
  struct IMtfPropertyBag *v41; // rcx
  __int64 (__fastcall ***v42)(_QWORD, GUID *, _QWORD *); // rcx
  int v43; // eax
  unsigned int v44; // esi
  __int64 (__fastcall ***v45)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v46; // rcx
  struct IMtfPropertyBag *v47; // rcx
  int v48; // eax
  unsigned int v49; // esi
  __int64 v50; // rcx
  __int64 (__fastcall ***v51)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v52; // rcx
  struct IMtfPropertyBag *v53; // rcx
  int v54; // eax
  unsigned int v55; // esi
  __int64 v56; // rcx
  __int64 (__fastcall ***v57)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v58; // rcx
  struct IMtfPropertyBag *v59; // rcx
  __int64 v60; // rcx
  __int64 (__fastcall ***v61)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v62; // rcx
  struct IMtfPropertyBag *v63; // rcx
  int v64; // eax
  unsigned int v65; // esi
  __int64 v66; // rcx
  __int64 (__fastcall ***v67)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v68; // rcx
  struct IMtfPropertyBag *v69; // rcx
  int v70; // eax
  unsigned int v71; // esi
  __int64 v72; // rcx
  __int64 (__fastcall ***v73)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v74; // rcx
  struct IMtfPropertyBag *v75; // rcx
  int v76; // eax
  unsigned int v77; // esi
  __int64 v78; // rcx
  __int64 (__fastcall ***v79)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v80; // rcx
  struct IMtfPropertyBag *v81; // rcx
  __int64 v82; // rcx
  __int64 (__fastcall ***v83)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v84; // rcx
  struct IMtfPropertyBag *v85; // rcx
  int v86; // [rsp+20h] [rbp-128h]
  int v87; // [rsp+20h] [rbp-128h]
  unsigned int v88; // [rsp+20h] [rbp-128h]
  struct IMtfPropertyBag *v89; // [rsp+50h] [rbp-F8h] BYREF
  __int64 v90; // [rsp+58h] [rbp-F0h] BYREF
  __int64 (__fastcall ***v91)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-E8h]
  __int64 v92; // [rsp+68h] [rbp-E0h] BYREF
  unsigned int v93; // [rsp+70h] [rbp-D8h] BYREF
  unsigned int v94; // [rsp+74h] [rbp-D4h]
  int v95; // [rsp+78h] [rbp-D0h] BYREF
  struct IMtfSuggestionInputQuery *v96[2]; // [rsp+80h] [rbp-C8h] BYREF
  int v97; // [rsp+90h] [rbp-B8h] BYREF
  _BYTE v98[40]; // [rsp+94h] [rbp-B4h] BYREF
  unsigned int v99; // [rsp+BCh] [rbp-8Ch]
  __int128 v100; // [rsp+F0h] [rbp-58h] BYREF
  __int64 v101; // [rsp+100h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v10 = (ipx::mtf::CMtfSuggestionClient *)((char *)this + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v96[1] = v10;
  if ( !a5 )
  {
    if ( v10 )
      LeaveCriticalSection((LPCRITICAL_SECTION)v10);
    return 2147942487LL;
  }
  if ( !a6 )
  {
    if ( v10 )
      LeaveCriticalSection((LPCRITICAL_SECTION)v10);
    return 2147942487LL;
  }
  *a5 = 0;
  *a6 = 0;
  if ( (*(_DWORD *)a4 & 0x40) == 0 || !*((_DWORD *)a4 + 4) )
  {
    *(_DWORD *)a4 |= 0x40u;
    *((_DWORD *)a4 + 4) = 3000;
  }
  v93 = 13;
  v96[0] = 0;
  v12 = ipx::mtf::CMtfSuggestionClient::_CreateSuggestionInputQuery(0, a2 != 0, a4, 0, 0, a3, 0, v96, &v93);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C6,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      (const char *)(unsigned int)v12,
      v86);
    if ( v96[0] )
      (*(void (__fastcall **)(struct IMtfSuggestionInputQuery *))(*(_QWORD *)v96[0] + 16LL))(v96[0]);
    if ( v10 )
      LeaveCriticalSection((LPCRITICAL_SECTION)v10);
    return v13;
  }
  v89 = 0;
  v14 = v96[0];
  v15 = ipx::mtf::CMtfSuggestionClient::_CreateRequestBag(
          (ipx::mtf::CMtfSuggestionClient *)((char *)this - 16),
          v93,
          0,
          0,
          0,
          0,
          0,
          v96[0],
          &v89);
  v16 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5CF,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      (const char *)(unsigned int)v15,
      v87);
    v17 = v89;
    if ( v89 )
    {
      v89 = 0;
      (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v17 + 16LL))(v17);
    }
    if ( v14 )
      (*(void (__fastcall **)(struct IMtfSuggestionInputQuery *))(*(_QWORD *)v14 + 16LL))(v14);
    if ( v10 )
      LeaveCriticalSection((LPCRITICAL_SECTION)v10);
    return v16;
  }
  memset_0(v98, 0, 0x5Cu);
  v97 = 64;
  v18 = (*(__int64 (__fastcall **)(struct IMtfSuggestionInputQuery *, int *))(*(_QWORD *)v14 + 24LL))(v14, &v97);
  v19 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D4,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      (const char *)(unsigned int)v18,
      v87);
    v20 = v89;
    if ( v89 )
    {
      v89 = 0;
      (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v20 + 16LL))(v20);
    }
    if ( v14 )
      (*(void (__fastcall **)(struct IMtfSuggestionInputQuery *))(*(_QWORD *)v14 + 16LL))(v14);
    if ( v10 )
      LeaveCriticalSection((LPCRITICAL_SECTION)v10);
    return v19;
  }
  v93 = v99;
  v90 = 0;
  v21 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 12))(
          *((_QWORD *)this + 12),
          &GUID_9d889366_53d0_49ef_b7e6_af4db30fc482,
          &v90);
  v22 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D9,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      (const char *)(unsigned int)v21,
      v87);
    v23 = v90;
    v90 = 0;
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v24 = v89;
    if ( v89 )
    {
      v89 = 0;
      (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v24 + 16LL))(v24);
    }
    if ( v14 )
      (*(void (__fastcall **)(struct IMtfSuggestionInputQuery *))(*(_QWORD *)v14 + 16LL))(v14);
    if ( v10 )
      LeaveCriticalSection((LPCRITICAL_SECTION)v10);
    return v22;
  }
  v25 = *((unsigned __int16 *)this + 94);
  v94 = *((unsigned __int16 *)this + 94);
  v91 = 0;
  v88 = v93;
  v26 = (*(__int64 (__fastcall **)(__int64, char *, __int64, struct IMtfPropertyBag *))(*(_QWORD *)v90 + 24LL))(
          v90,
          (char *)this + 32,
          v25,
          v89);
  v27 = v26;
  if ( v26 < 0 )
  {
    if ( (v26 & 0x1FFF0000) == 0x7B20000 && v26 != -2143288316 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5E8,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
        (const char *)(unsigned int)v26,
        v88);
      v28 = v91;
      v91 = 0;
      if ( v28 )
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v28)[2])(v28);
      v29 = v90;
      v90 = 0;
      if ( v29 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      v30 = v89;
      if ( v89 )
      {
        v89 = 0;
        (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v30 + 16LL))(v30);
      }
      if ( v14 )
        (*(void (__fastcall **)(struct IMtfSuggestionInputQuery *))(*(_QWORD *)v14 + 16LL))(v14);
      if ( v10 )
        LeaveCriticalSection((LPCRITICAL_SECTION)v10);
      return v27;
    }
    v31 = v90;
    v90 = 0;
    if ( v31 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v32 = ipx::mtf::CMtfSuggestionClient::RepairServerConnection((ipx::mtf::CMtfSuggestionClient *)((char *)this - 16));
    v33 = v32;
    if ( v32 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5EE,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
        (const char *)(unsigned int)v32,
        v88);
      v34 = v91;
      v91 = 0;
      if ( v34 )
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v34)[2])(v34);
      v35 = v90;
      v90 = 0;
      if ( v35 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      v36 = v89;
      if ( v89 )
      {
        v89 = 0;
        (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v36 + 16LL))(v36);
      }
      if ( v14 )
        (*(void (__fastcall **)(struct IMtfSuggestionInputQuery *))(*(_QWORD *)v14 + 16LL))(v14);
      if ( v10 )
        LeaveCriticalSection((LPCRITICAL_SECTION)v10);
      return v33;
    }
    v37 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 12))(
            *((_QWORD *)this + 12),
            &GUID_9d889366_53d0_49ef_b7e6_af4db30fc482,
            &v90);
    v38 = v37;
    if ( v37 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5F0,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
        (const char *)(unsigned int)v37,
        v88);
      v39 = v91;
      v91 = 0;
      if ( v39 )
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v39)[2])(v39);
      v40 = v90;
      v90 = 0;
      if ( v40 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
      v41 = v89;
      if ( v89 )
      {
        v89 = 0;
        (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v41 + 16LL))(v41);
      }
      if ( v14 )
        (*(void (__fastcall **)(struct IMtfSuggestionInputQuery *))(*(_QWORD *)v14 + 16LL))(v14);
      if ( v10 )
        LeaveCriticalSection((LPCRITICAL_SECTION)v10);
      return v38;
    }
    v42 = v91;
    v91 = 0;
    if ( v42 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v42)[2])(v42);
    v88 = v93;
    v43 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, struct IMtfPropertyBag *))(*(_QWORD *)v90 + 24LL))(
            v90,
            (char *)this + 32,
            v94,
            v89);
    v44 = v43;
    if ( v43 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5F8,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
        (const char *)(unsigned int)v43,
        v88);
      v45 = v91;
      v91 = 0;
      if ( v45 )
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v45)[2])(v45);
      v46 = v90;
      v90 = 0;
      if ( v46 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
      v47 = v89;
      if ( v89 )
      {
        v89 = 0;
        (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v47 + 16LL))(v47);
      }
      if ( v14 )
        (*(void (__fastcall **)(struct IMtfSuggestionInputQuery *))(*(_QWORD *)v14 + 16LL))(v14);
      if ( v10 )
        LeaveCriticalSection((LPCRITICAL_SECTION)v10);
      return v44;
    }
  }
  v92 = 0;
  v48 = (**v91)(v91, &GUID_47445657_8d68_4b3b_b716_b0debdd9b3f5, &v92);
  v49 = v48;
  if ( v48 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x601,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      (const char *)(unsigned int)v48,
      v88);
    v50 = v92;
    if ( v92 )
    {
      v92 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    }
    v51 = v91;
    v91 = 0;
    if ( v51 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v51)[2])(v51);
    v52 = v90;
    v90 = 0;
    if ( v52 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    v53 = v89;
    if ( v89 )
    {
      v89 = 0;
      (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v53 + 16LL))(v53);
    }
    if ( v14 )
      (*(void (__fastcall **)(struct IMtfSuggestionInputQuery *))(*(_QWORD *)v14 + 16LL))(v14);
    if ( v10 )
      LeaveCriticalSection((LPCRITICAL_SECTION)v10);
    return v49;
  }
  v95 = 0;
  v54 = (*(__int64 (__fastcall **)(__int64, GUID *, int *, __int64))(*(_QWORD *)v92 + 40LL))(
          v92,
          &GUID_MTFCORE_VERB,
          &v95,
          4);
  v55 = v54;
  if ( v54 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x604,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      (const char *)(unsigned int)v54,
      v88);
    v56 = v92;
    if ( v92 )
    {
      v92 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    }
    v57 = v91;
    v91 = 0;
    if ( v57 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v57)[2])(v57);
    v58 = v90;
    v90 = 0;
    if ( v58 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
    v59 = v89;
    if ( v89 )
    {
      v89 = 0;
      (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v59 + 16LL))(v59);
    }
    if ( v14 )
      (*(void (__fastcall **)(struct IMtfSuggestionInputQuery *))(*(_QWORD *)v14 + 16LL))(v14);
    if ( v10 )
      LeaveCriticalSection((LPCRITICAL_SECTION)v10);
    return v55;
  }
  if ( v95 != 21 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x606,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      (const char *)0x8000FFFFLL,
      v88);
    v60 = v92;
    if ( v92 )
    {
      v92 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
    }
    v61 = v91;
    v91 = 0;
    if ( v61 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v61)[2])(v61);
    v62 = v90;
    v90 = 0;
    if ( v62 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
    v63 = v89;
    if ( v89 )
    {
      v89 = 0;
      (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v63 + 16LL))(v63);
    }
    if ( v14 )
      (*(void (__fastcall **)(struct IMtfSuggestionInputQuery *))(*(_QWORD *)v14 + 16LL))(v14);
    if ( v10 )
      LeaveCriticalSection((LPCRITICAL_SECTION)v10);
    return 2147549183LL;
  }
  v100 = 0;
  v101 = 0;
  v64 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *, __int64))(*(_QWORD *)v92 + 40LL))(
          v92,
          &GUID_MTFCORE_RESULT,
          &v100,
          24);
  v65 = v64;
  if ( v64 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x609,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      (const char *)(unsigned int)v64,
      v88);
    v66 = v92;
    if ( v92 )
    {
      v92 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
    }
    v67 = v91;
    v91 = 0;
    if ( v67 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v67)[2])(v67);
    v68 = v90;
    v90 = 0;
    if ( v68 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
    v69 = v89;
    if ( v89 )
    {
      v89 = 0;
      (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v69 + 16LL))(v69);
    }
    if ( v14 )
      (*(void (__fastcall **)(struct IMtfSuggestionInputQuery *))(*(_QWORD *)v14 + 16LL))(v14);
    if ( v10 )
      LeaveCriticalSection((LPCRITICAL_SECTION)v10);
    return v65;
  }
  if ( !BYTE2(v101) )
    goto LABEL_185;
  v70 = (*(__int64 (__fastcall **)(__int64, GUID *, GUID *, struct IMtfLatticePathList **))(*(_QWORD *)v92 + 56LL))(
          v92,
          &GUID_MTFCORE_SUGGESTIONLIST,
          &GUID_bf445657_712d_488f_b37f_2e303c7420d3,
          a6);
  v71 = v70;
  if ( v70 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x60D,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      (const char *)(unsigned int)v70,
      v88);
    v72 = v92;
    if ( v92 )
    {
      v92 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
    }
    v73 = v91;
    v91 = 0;
    if ( v73 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v73)[2])(v73);
    v74 = v90;
    v90 = 0;
    if ( v74 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
    v75 = v89;
    if ( v89 )
    {
      v89 = 0;
      (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v75 + 16LL))(v75);
    }
    if ( v14 )
      (*(void (__fastcall **)(struct IMtfSuggestionInputQuery *))(*(_QWORD *)v14 + 16LL))(v14);
    if ( v10 )
      LeaveCriticalSection((LPCRITICAL_SECTION)v10);
    return v71;
  }
  if ( (**(int (__fastcall ***)(_QWORD, GUID *, struct IMtfLattice **))*a6)(
         *a6,
         &GUID_ee445657_a83d_450f_871b_8e404574e6ec,
         a5) >= 0
    && *a5
    || (v76 = ((__int64 (__fastcall *)(GUID *, _QWORD, __int64, GUID *))Hooked_CoCreateInstance)(
                &CLSID_MtfLattice,
                0,
                1,
                &GUID_ee445657_a83d_450f_871b_8e404574e6ec),
        v77 = v76,
        v76 >= 0) )
  {
LABEL_185:
    v82 = v92;
    if ( v92 )
    {
      v92 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
    }
    v83 = v91;
    v91 = 0;
    if ( v83 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v83)[2])(v83);
    v84 = v90;
    v90 = 0;
    if ( v84 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
    v85 = v89;
    if ( v89 )
    {
      v89 = 0;
      (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v85 + 16LL))(v85);
    }
    if ( v14 )
      (*(void (__fastcall **)(struct IMtfSuggestionInputQuery *))(*(_QWORD *)v14 + 16LL))(v14);
    if ( v10 )
      LeaveCriticalSection((LPCRITICAL_SECTION)v10);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x617,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      (const char *)(unsigned int)v76,
      (int)a5);
    v78 = v92;
    if ( v92 )
    {
      v92 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
    }
    v79 = v91;
    v91 = 0;
    if ( v79 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v79)[2])(v79);
    v80 = v90;
    v90 = 0;
    if ( v80 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
    v81 = v89;
    if ( v89 )
    {
      v89 = 0;
      (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v81 + 16LL))(v81);
    }
    if ( v14 )
      (*(void (__fastcall **)(struct IMtfSuggestionInputQuery *))(*(_QWORD *)v14 + 16LL))(v14);
    if ( v10 )
      LeaveCriticalSection((LPCRITICAL_SECTION)v10);
    return v77;
  }
}

```

## disassembly

```asm
0x180016cf0  push    rbx
0x180016cf2  push    rsi
0x180016cf3  push    rdi
0x180016cf4  push    r12
0x180016cf6  push    r13
0x180016cf8  push    r14
0x180016cfa  push    r15
0x180016cfc  sub     rsp, 110h
0x180016d03  mov     rax, cs:__security_cookie
0x180016d0a  xor     rax, rsp
0x180016d0d  mov     [rsp+148h+var_40], rax
0x180016d15  mov     rdi, r9
0x180016d18  mov     r12, r8
0x180016d1b  mov     esi, edx
0x180016d1d  mov     r14, rcx
0x180016d20  mov     r15, [rsp+148h+arg_20]
0x180016d28  mov     r13, [rsp+148h+arg_28]
0x180016d30  lea     rbx, [rcx+30h]
0x180016d34  mov     rcx, rbx; lpCriticalSection
0x180016d37  call    cs:__imp_EnterCriticalSection
0x180016d3d  mov     [rsp+148h+var_C0], rbx
0x180016d45  xor     ecx, ecx; this
0x180016d47  test    r15, r15
0x180016d4a  jnz     short loc_180016D64
0x180016d4c  test    rbx, rbx
0x180016d4f  jz      short loc_180016D5A
0x180016d51  mov     rcx, rbx; lpCriticalSection
0x180016d54  call    cs:__imp_LeaveCriticalSection
0x180016d5a  mov     eax, 80070057h
0x180016d5f  jmp     loc_180017A09
0x180016d64  test    r13, r13
0x180016d67  jnz     short loc_180016D81
0x180016d69  test    rbx, rbx
0x180016d6c  jz      short loc_180016D77
0x180016d6e  mov     rcx, rbx; lpCriticalSection
0x180016d71  call    cs:__imp_LeaveCriticalSection
0x180016d77  mov     eax, 80070057h
0x180016d7c  jmp     loc_180017A09
0x180016d81  mov     [r15], rcx
0x180016d84  mov     [r13+0], rcx
0x180016d88  mov     eax, [rdi]
0x180016d8a  test    al, 40h
0x180016d8c  jz      short loc_180016D93
0x180016d8e  cmp     [rdi+10h], ecx
0x180016d91  jnz     short loc_180016D9F
0x180016d93  or      eax, 40h
0x180016d96  mov     [rdi], eax
0x180016d98  mov     dword ptr [rdi+10h], 0BB8h
0x180016d9f  mov     [rsp+148h+var_D8], 0Dh
0x180016da7  mov     [rsp+148h+var_C8], rcx
0x180016daf  test    esi, esi
0x180016db1  setnz   dl; bool
0x180016db4  lea     rax, [rsp+148h+var_D8]
0x180016db9  mov     [rsp+148h+var_108], rax; unsigned int *
0x180016dbe  lea     rax, [rsp+148h+var_C8]
0x180016dc6  mov     [rsp+148h+var_110], rax; struct IMtfSuggestionInputQuery **
0x180016dcb  mov     [rsp+148h+var_118], rcx; struct IMtfPropertyBag *
0x180016dd0  mov     [rsp+148h+var_120], r12; struct IMtfLattice *
0x180016dd5  mov     [rsp+148h+var_128], ecx; int
0x180016dd9  xor     r9d, r9d; unsigned __int8 *
0x180016ddc  mov     r8, rdi; struct _MTF_QUERY_PROP *
0x180016ddf  call    ?_CreateSuggestionInputQuery@CMtfSuggestionClient@mtf@ipx@@IEAAJ_NPEBU_MTF_QUERY_PROP@@PEAEKPEAUIMtfLattice@@PEAUIMtfPropertyBag@@PEAPEAUIMtfSuggestionInputQuery@@PEAK@Z; ipx::mtf::CMtfSuggestionClient::_CreateSuggestionInputQuery(bool,_MTF_QUERY_PROP const *,uchar *,ulong,IMtfLattice *,IMtfPropertyBag *,IMtfSuggestionInputQuery * *,ulong *)
0x180016de4  mov     edi, eax
0x180016de6  xor     esi, esi
0x180016de8  test    eax, eax
0x180016dea  jns     short loc_180016E38
0x180016dec  mov     rcx, [rsp+148h]; this
0x180016df4  mov     r9d, eax; char *
0x180016df7  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x180016dfe  mov     edx, 5C6h; void *
0x180016e03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016e08  nop
0x180016e09  mov     rcx, [rsp+148h+var_C8]
0x180016e11  test    rcx, rcx
0x180016e14  jz      short loc_180016E23
0x180016e16  mov     rax, [rcx]
0x180016e19  mov     rax, [rax+10h]
0x180016e1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e22  nop
0x180016e23  test    rbx, rbx
0x180016e26  jz      short loc_180016E31
0x180016e28  mov     rcx, rbx; lpCriticalSection
0x180016e2b  call    cs:__imp_LeaveCriticalSection
0x180016e31  mov     eax, edi
0x180016e33  jmp     loc_180017A09
0x180016e38  mov     [rsp+148h+var_F8], rsi
0x180016e3d  lea     rax, [rsp+148h+var_F8]
0x180016e42  mov     [rsp+148h+var_108], rax; struct IMtfPropertyBag **
0x180016e47  mov     rdi, [rsp+148h+var_C8]
0x180016e4f  mov     [rsp+148h+var_110], rdi; struct IMtfSuggestionInputQuery *
0x180016e54  mov     [rsp+148h+var_118], rsi; struct IMtfSuggestionContextProperty *
0x180016e59  mov     [rsp+148h+var_120], rsi; struct IMtfSuggestionCandidatePrimitive *
0x180016e5e  mov     [rsp+148h+var_128], esi; int
0x180016e62  xor     r9d, r9d; unsigned __int8 *
0x180016e65  xor     r8d, r8d; struct MTFCORE_SIMPLEPARAM *
0x180016e68  mov     edx, [rsp+148h+var_D8]; unsigned int
0x180016e6c  lea     rcx, [r14-10h]; this
0x180016e70  call    ?_CreateRequestBag@CMtfSuggestionClient@mtf@ipx@@IEAAJKPEBUMTFCORE_SIMPLEPARAM@@PEBEKPEAUIMtfSuggestionCandidatePrimitive@@PEAUIMtfSuggestionContextProperty@@PEAUIMtfSuggestionInputQuery@@PEAPEAUIMtfPropertyBag@@@Z; ipx::mtf::CMtfSuggestionClient::_CreateRequestBag(ulong,MTFCORE_SIMPLEPARAM const *,uchar const *,ulong,IMtfSuggestionCandidatePrimitive *,IMtfSuggestionContextProperty *,IMtfSuggestionInputQuery *,IMtfPropertyBag * *)
0x180016e75  mov     esi, eax
0x180016e77  test    eax, eax
0x180016e79  jns     short loc_180016EE2
0x180016e7b  mov     rcx, [rsp+148h]; this
0x180016e83  mov     r9d, eax; char *
0x180016e86  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x180016e8d  mov     edx, 5CFh; void *
0x180016e92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016e97  nop
0x180016e98  mov     rcx, [rsp+148h+var_F8]
0x180016e9d  test    rcx, rcx
0x180016ea0  jz      short loc_180016EB8
0x180016ea2  mov     [rsp+148h+var_F8], 0
0x180016eab  mov     rax, [rcx]
0x180016eae  mov     rax, [rax+10h]
0x180016eb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016eb7  nop
0x180016eb8  test    rdi, rdi
0x180016ebb  jz      short loc_180016ECD
0x180016ebd  mov     rax, [rdi]
0x180016ec0  mov     rcx, rdi
0x180016ec3  mov     rax, [rax+10h]
0x180016ec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ecc  nop
0x180016ecd  test    rbx, rbx
0x180016ed0  jz      short loc_180016EDB
0x180016ed2  mov     rcx, rbx; lpCriticalSection
0x180016ed5  call    cs:__imp_LeaveCriticalSection
0x180016edb  mov     eax, esi
0x180016edd  jmp     loc_180017A09
0x180016ee2  xor     edx, edx; Val
0x180016ee4  lea     r8d, [rdx+5Ch]; Size
0x180016ee8  lea     rcx, [rsp+148h+var_B4]; void *
0x180016ef0  call    memset_0
0x180016ef5  mov     [rsp+148h+var_B8], 40h ; '@'
0x180016f00  mov     rax, [rdi]
0x180016f03  lea     rdx, [rsp+148h+var_B8]
0x180016f0b  mov     rcx, rdi
0x180016f0e  mov     rax, [rax+18h]
0x180016f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f17  mov     esi, eax
0x180016f19  test    eax, eax
0x180016f1b  jns     short loc_180016F84
0x180016f1d  mov     rcx, [rsp+148h]; this
0x180016f25  mov     r9d, eax; char *
0x180016f28  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x180016f2f  mov     edx, 5D4h; void *
0x180016f34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016f39  nop
0x180016f3a  mov     rcx, [rsp+148h+var_F8]
0x180016f3f  test    rcx, rcx
0x180016f42  jz      short loc_180016F5A
0x180016f44  mov     [rsp+148h+var_F8], 0
0x180016f4d  mov     rax, [rcx]
0x180016f50  mov     rax, [rax+10h]
0x180016f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f59  nop
0x180016f5a  test    rdi, rdi
0x180016f5d  jz      short loc_180016F6F
0x180016f5f  mov     rax, [rdi]
0x180016f62  mov     rcx, rdi
0x180016f65  mov     rax, [rax+10h]
0x180016f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f6e  nop
0x180016f6f  test    rbx, rbx
0x180016f72  jz      short loc_180016F7D
0x180016f74  mov     rcx, rbx; lpCriticalSection
0x180016f77  call    cs:__imp_LeaveCriticalSection
0x180016f7d  mov     eax, esi
0x180016f7f  jmp     loc_180017A09
0x180016f84  mov     eax, [rsp+148h+var_8C]
0x180016f8b  mov     [rsp+148h+var_D8], eax
0x180016f8f  mov     [rsp+148h+var_F0], 0
0x180016f98  mov     rcx, [r14+60h]
0x180016f9c  mov     rax, [rcx]
0x180016f9f  lea     r8, [rsp+148h+var_F0]
0x180016fa4  lea     rdx, _GUID_9d889366_53d0_49ef_b7e6_af4db30fc482
0x180016fab  mov     rax, [rax]
0x180016fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fb3  mov     esi, eax
0x180016fb5  test    eax, eax
0x180016fb7  jns     loc_180017044
0x180016fbd  mov     rcx, [rsp+148h]; this
0x180016fc5  mov     r9d, eax; char *
0x180016fc8  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x180016fcf  mov     edx, 5D9h; void *
0x180016fd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016fd9  nop
0x180016fda  mov     rcx, [rsp+148h+var_F0]
0x180016fdf  mov     [rsp+148h+var_F0], 0
0x180016fe8  test    rcx, rcx
0x180016feb  jz      short loc_180016FFA
0x180016fed  mov     rax, [rcx]
0x180016ff0  mov     rax, [rax+10h]
0x180016ff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ff9  nop
0x180016ffa  mov     rcx, [rsp+148h+var_F8]
0x180016fff  test    rcx, rcx
0x180017002  jz      short loc_18001701A
0x180017004  mov     [rsp+148h+var_F8], 0
0x18001700d  mov     rax, [rcx]
0x180017010  mov     rax, [rax+10h]
0x180017014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017019  nop
0x18001701a  test    rdi, rdi
0x18001701d  jz      short loc_18001702F
0x18001701f  mov     rax, [rdi]
0x180017022  mov     rcx, rdi
0x180017025  mov     rax, [rax+10h]
0x180017029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001702e  nop
0x18001702f  test    rbx, rbx
0x180017032  jz      short loc_18001703D
0x180017034  mov     rcx, rbx; lpCriticalSection
0x180017037  call    cs:__imp_LeaveCriticalSection
0x18001703d  mov     eax, esi
0x18001703f  jmp     loc_180017A09
0x180017044  movzx   r8d, word ptr [r14+0BCh]
0x18001704c  mov     [rsp+148h+var_D4], r8d
0x180017051  mov     [rsp+148h+var_E8], 0
0x18001705a  mov     rcx, [rsp+148h+var_F0]
0x18001705f  mov     rax, [rcx]
0x180017062  lea     rdx, [rsp+148h+var_E8]
0x180017067  mov     [rsp+148h+var_120], rdx
0x18001706c  mov     edx, [rsp+148h+var_D8]
0x180017070  mov     [rsp+148h+var_128], edx; int
0x180017074  mov     r9, [rsp+148h+var_F8]
0x180017079  lea     rdx, [r14+20h]
0x18001707d  mov     rax, [rax+18h]
0x180017081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017086  mov     esi, eax
0x180017088  test    eax, eax
0x18001708a  jns     loc_1800173E0
0x180017090  mov     ecx, eax
0x180017092  mov     eax, 1FFF0000h
0x180017097  and     ecx, eax
0x180017099  cmp     ecx, 10000h
0x18001709f  jz      loc_18001715F
0x1800170a5  mov     ecx, esi
0x1800170a7  and     ecx, eax
0x1800170a9  cmp     ecx, 7B20000h
0x1800170af  jnz     loc_18001715F
0x1800170b5  cmp     esi, 80400404h
0x1800170bb  jz      loc_18001715F
0x1800170c1  mov     rcx, [rsp+148h]; this
0x1800170c9  mov     r9d, esi; char *
0x1800170cc  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x1800170d3  mov     edx, 5E8h; void *
0x1800170d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800170dd  nop
0x1800170de  mov     rcx, [rsp+148h+var_E8]
0x1800170e3  xor     r14d, r14d
0x1800170e6  mov     [rsp+148h+var_E8], r14
0x1800170eb  test    rcx, rcx
0x1800170ee  jz      short loc_1800170FD
0x1800170f0  mov     rax, [rcx]
0x1800170f3  mov     rax, [rax+10h]
0x1800170f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170fc  nop
0x1800170fd  mov     rcx, [rsp+148h+var_F0]
0x180017102  mov     [rsp+148h+var_F0], r14
0x180017107  test    rcx, rcx
0x18001710a  jz      short loc_180017119
0x18001710c  mov     rax, [rcx]
0x18001710f  mov     rax, [rax+10h]
0x180017113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017118  nop
0x180017119  mov     rcx, [rsp+148h+var_F8]
0x18001711e  test    rcx, rcx
0x180017121  jz      short loc_180017135
0x180017123  mov     [rsp+148h+var_F8], r14
0x180017128  mov     rax, [rcx]
0x18001712b  mov     rax, [rax+10h]
0x18001712f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017134  nop
0x180017135  test    rdi, rdi
0x180017138  jz      short loc_18001714A
0x18001713a  mov     rax, [rdi]
0x18001713d  mov     rcx, rdi
0x180017140  mov     rax, [rax+10h]
0x180017144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017149  nop
0x18001714a  test    rbx, rbx
0x18001714d  jz      short loc_180017158
0x18001714f  mov     rcx, rbx; lpCriticalSection
0x180017152  call    cs:__imp_LeaveCriticalSection
0x180017158  mov     eax, esi
0x18001715a  jmp     loc_180017A09
0x18001715f  mov     rcx, [rsp+148h+var_F0]
0x180017164  mov     [rsp+148h+var_F0], 0
0x18001716d  test    rcx, rcx
0x180017170  jz      short loc_18001717E
0x180017172  mov     rax, [rcx]
0x180017175  mov     rax, [rax+10h]
0x180017179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001717e  lea     rcx, [r14-10h]; this
0x180017182  call    ?RepairServerConnection@CMtfSuggestionClient@mtf@ipx@@IEAAJXZ; ipx::mtf::CMtfSuggestionClient::RepairServerConnection(void)
0x180017187  mov     esi, eax
0x180017189  xor     r12d, r12d
0x18001718c  test    eax, eax
0x18001718e  jns     loc_18001722F
0x180017194  mov     rcx, [rsp+148h]; this
  ... truncated ...
```
