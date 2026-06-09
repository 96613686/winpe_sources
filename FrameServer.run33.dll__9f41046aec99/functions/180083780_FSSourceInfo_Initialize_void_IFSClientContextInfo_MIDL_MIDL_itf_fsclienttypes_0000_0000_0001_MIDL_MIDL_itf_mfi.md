# FSSourceInfo::Initialize(void *,IFSClientContextInfo *,__MIDL___MIDL_itf_fsclienttypes_0000_0000_0001,__MIDL___MIDL_itf_mfidl_0000_0114_0001 *,ulong,ulong,uchar *,ulong,uchar *,IMFAttributes *,ulong *,CTUnkArray<FSPinInfo> &,ulong *)

- ea: `0x180083780`
- end: `0x18008490d`
- name: `?Initialize@FSSourceInfo@@QEAAJPEAXPEAUIFSClientContextInfo@@W4__MIDL___MIDL_itf_fsclienttypes_0000_0000_0001@@PEAU__MIDL___MIDL_itf_mfidl_0000_0114_0001@@KKPEAEK4PEAUIMFAttributes@@PEAKAEAV?$CTUnkArray@VFSPinInfo@@@@6@Z`
- size: `4493`
- prototype: `void __fastcall __noreturn(__int64, void *, __int64, int, struct _GUID *, int, UINT cbBufSize, UINT8 *, unsigned int, FSPinInfo *, struct IMFAttributes *, unsigned int *, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `36`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180067bd0`

## callees

- `0x1800039f0`
- `0x180003e20`
- `0x18000478c`
- `0x180008cf0`
- `0x180009494`
- `0x1800095c8`
- `0x180009608`
- `0x180009658`
- `0x1800096f4`
- `0x180009b5c`
- `0x18000a4a8`
- `0x18000a880`
- `0x18000ad10`
- `0x180018998`
- `0x180024200`
- `0x18004d714`
- `0x18004d748`
- `0x18004da70`
- `0x18004f37c`
- `0x18006425c`
- `0x1800766d0`
- `0x1800826f0`
- `0x1800833f8`
- `0x180083780`
- `0x180085254`
- `0x1800852c4`
- `0x1800859d8`
- `0x18008792c`
- `0x180087c14`
- `0x180087e40`
- `0x180088444`
- `0x180088590`
- `0x180088a2c`
- `0x1800896e0`
- `0x18008a734`
- `0x1800ea010`

## import_xrefs

- `MFSENSORGROUP!MFCreateSensorGroupIdManager` at `0x180083de2`
- `MFSENSORGROUP!MFCreateSensorGroupIdManager` at `0x180083de2`
- `MFSENSORGROUP!MFCreateSensorProfileWithFlags` at `0x180083b8e`
- `MFSENSORGROUP!MFCreateSensorProfileWithFlags` at `0x180083b8e`
- `MFSENSORGROUP!MFCreateSensorGroupWithOptions` at `0x180083ac1`
- `MFSENSORGROUP!MFCreateSensorGroupWithOptions` at `0x180083ac1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800848db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800848db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180083813`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180083813`
- `MFPlat!MFCreateAttributes` at `0x1800842c8`
- `MFPlat!MFCreateAttributes` at `0x1800842c8`
- `MFPlat!MFInitAttributesFromBlob` at `0x1800842f4`
- `MFPlat!MFInitAttributesFromBlob` at `0x1800842f4`

## pseudocode

```c
void __fastcall __noreturn FSSourceInfo::Initialize(
        __int64 a1,
        void *a2,
        __int64 a3,
        int a4,
        struct _GUID *a5,
        int a6,
        UINT cbBufSize,
        UINT8 *a8,
        int a9,
        FSPinInfo *a10,
        struct IMFAttributes *a11,
        unsigned int *a12,
        __int64 a13,
        _DWORD *a14)
{
  char v17; // r15
  __int64 (__fastcall *v18)(_QWORD, GUID *, __int64); // rsi
  __int64 v19; // rdx
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rdx
  __int64 (__fastcall *v23)(__int64 (__fastcall *)(_QWORD, GUID *, __int64), __int64); // rbx
  __int64 (__fastcall ***v24)(_QWORD, GUID *, __int64); // r14
  __int64 v25; // rax
  unsigned int Data1; // r14d
  __int64 v27; // rsi
  GuidTrace *v28; // rax
  const char *String; // rbx
  FSString *v30; // rax
  const char *v31; // rax
  _QWORD *v32; // r14
  __int64 v33; // rcx
  __int64 v34; // rax
  int (__fastcall ***v35)(_QWORD, _QWORD, _QWORD); // rsi
  int (__fastcall *v36)(_QWORD, GUID *, _OWORD *); // rbx
  __int64 v37; // rax
  FSPinInfo *v38; // rsi
  void (__fastcall *v39)(FSPinInfo *, struct _GUID *, struct IFSClientContextInfo **); // rbx
  struct IFSClientContextInfo *v40; // rbx
  int v41; // eax
  __int64 v42; // rdx
  __int64 (__fastcall *v43)(struct IFSClientContextInfo *, GUID *, __int64); // r14
  __int64 v44; // rdx
  char *v45; // rsi
  char v46; // bl
  char v47; // al
  const char *v48; // rcx
  struct IMFAttributes *v49; // r12
  _QWORD *v50; // rcx
  _QWORD *v51; // rcx
  _QWORD *v52; // rbx
  __int64 v53; // rax
  __int64 (__fastcall *v54)(_QWORD, _QWORD, _QWORD); // rcx
  _QWORD *v55; // rbx
  __int64 (__fastcall **v56)(_QWORD, GUID *, __int64); // rax
  __int64 (__fastcall *v57)(__int64 (__fastcall *)(_QWORD, GUID *, __int64), __int64); // rbx
  __int64 v58; // rax
  _QWORD *v59; // r14
  int v60; // eax
  __int64 v61; // rsi
  int (__fastcall *v62)(__int64, int (__fastcall ****)(_QWORD, GUID *, _OWORD *)); // rbx
  int v63; // eax
  const char *v64; // rcx
  struct IMFAttributesVtbl *lpVtbl; // rax
  __int64 (__fastcall *v66)(__int64 (__fastcall *)(_QWORD, GUID *, __int64), struct IFSClientContextInfo **); // rbx
  int v67; // eax
  struct IFSClientContextInfo *v68; // rdx
  struct IFSClientContextInfo *v69; // rsi
  int v70; // ebx
  FSString *v71; // rax
  const char *v72; // rax
  FSString *v73; // rax
  const char *v74; // rax
  UINT8 *v75; // r15
  __int64 *v76; // rsi
  __int64 v77; // rcx
  __int64 v78; // rax
  void (__fastcall *v79)(__int64 *, __int64); // r14
  int v80; // eax
  bool v81; // zf
  unsigned int v82; // r14d
  __int64 v83; // r12
  __int64 v84; // rcx
  __int64 v85; // rcx
  __int64 v86; // rcx
  int v87; // eax
  __int64 v88; // rdx
  FSPinInfo *v89; // rax
  struct IMFSensorProfileInternal *v90; // r14
  struct IMFSensorProfile *v91; // r15
  struct IMFAttributes *v92; // rbx
  unsigned int v93; // esi
  unsigned int v94; // r12d
  unsigned __int64 v95; // rax
  FSPinInfo *v96; // rbx
  __int64 v97; // rbx
  unsigned int v98; // r14d
  FSSourceInfo *v99; // rcx
  __int64 v100; // rdx
  unsigned int *v101; // r15
  __int64 (__fastcall *v102)(__int64 (__fastcall *)(_QWORD, GUID *, __int64), bool); // rbx
  bool IsTorchControlSharingEnabled; // al
  __int64 v104; // rcx
  const wchar_t *v105; // rax
  __int64 v106; // rax
  int v107; // edx
  int v108; // r8d
  __int64 v109; // [rsp+38h] [rbp-C8h]
  char v110; // [rsp+70h] [rbp-90h]
  bool v111; // [rsp+71h] [rbp-8Fh] BYREF
  struct IFSClientContextInfo *v112; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v113; // [rsp+80h] [rbp-80h] BYREF
  FSPinInfo *v114; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v115; // [rsp+90h] [rbp-70h] BYREF
  int (__fastcall ***v116)(_QWORD, GUID *, _OWORD *); // [rsp+98h] [rbp-68h] BYREF
  __int64 (__fastcall *v117)(_QWORD, _QWORD, _QWORD); // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v118; // [rsp+A8h] [rbp-58h]
  unsigned int v119; // [rsp+ACh] [rbp-54h]
  _QWORD *v120; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD *v121; // [rsp+B8h] [rbp-48h] BYREF
  _DWORD *v122; // [rsp+C0h] [rbp-40h]
  FSPinInfo *v123; // [rsp+C8h] [rbp-38h]
  struct IMFAttributes *v124; // [rsp+D0h] [rbp-30h]
  unsigned int *v125; // [rsp+D8h] [rbp-28h]
  __int64 v126; // [rsp+E0h] [rbp-20h] BYREF
  int v127; // [rsp+E8h] [rbp-18h]
  __int64 v128; // [rsp+ECh] [rbp-14h]
  UINT8 *pBuf; // [rsp+F8h] [rbp-8h]
  void *v130; // [rsp+100h] [rbp+0h]
  __int64 v131; // [rsp+108h] [rbp+8h]
  _BYTE v132[32]; // [rsp+110h] [rbp+10h] BYREF
  _OWORD v133[2]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v134[66]; // [rsp+150h] [rbp+50h] BYREF

  pBuf = a8;
  v17 = 0;
  v124 = a11;
  v125 = a12;
  v131 = a13;
  v123 = a10;
  v122 = a14;
  v130 = a2;
  LODWORD(v112) = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  v121 = 0;
  v118 = 0;
  v115 = 0;
  v119 = 0;
  v113 = 0;
  v120 = 0;
  v117 = 0;
  memset_0(v134, 0, 0x208u);
  v126 = 0;
  v128 = 0;
  v127 = 0;
  if ( !a5 )
  {
    LOBYTE(v18) = 87;
    if ( !g_wppLevels )
      goto LABEL_197;
    v19 = 24;
LABEL_4:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v19,
      &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids,
      a1,
      -2147024809);
    goto LABEL_197;
  }
  if ( !a3 )
  {
    LOBYTE(v18) = 87;
    if ( !g_wppLevels )
      goto LABEL_197;
    v19 = 25;
    goto LABEL_4;
  }
  LODWORD(v18) = 1;
  if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a3 + 208LL))(a3, 0) )
    LODWORD(v18) = a4;
  v20 = *(_QWORD *)(a1 + 168);
  *(_QWORD *)(a1 + 168) = 0;
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  v21 = FSClientContextInfo::CloneFSClientContextInfo(
          a3,
          (unsigned int)v18,
          *(unsigned int *)(a1 + 56),
          0,
          0,
          &GUID_c948ed26_2196_401e_ab0c_84cc1b3067bc,
          a1 + 168);
  LOBYTE(v18) = v21;
  if ( v21 < 0 )
  {
    if ( g_wppLevels )
    {
      v22 = 26;
      goto LABEL_15;
    }
    goto LABEL_197;
  }
  v18 = *(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(a1 + 96);
  v23 = *(__int64 (__fastcall **)(__int64 (__fastcall *)(_QWORD, GUID *, __int64), __int64))(*(_QWORD *)v18 + 48LL);
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(a1 + 104);
  v21 = v23(v18, a1 + 104);
  LOBYTE(v18) = v21;
  if ( v21 < 0 )
  {
    if ( g_wppLevels )
    {
      v22 = 27;
      goto LABEL_15;
    }
    goto LABEL_197;
  }
  v24 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64))(a1 + 96);
  v18 = **v24;
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(a1 + 112);
  v21 = v18(v24, &GUID_7eec0fa2_0911_4614_be40_60253271e04d, a1 + 112);
  LOBYTE(v18) = v21;
  if ( v21 < 0 )
  {
    if ( g_wppLevels )
    {
      v22 = 28;
      goto LABEL_15;
    }
    goto LABEL_197;
  }
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v25 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 104) + 32LL))(*(_QWORD *)(a1 + 104));
    Data1 = a5[1].Data1;
    v27 = v25;
    v28 = GuidTrace::GuidTrace((GuidTrace *)v132, a5);
    String = GuidTrace::GetString(v28);
    v30 = ClientContextInfoTrace::ClientContextInfoTrace(
            (ClientContextInfoTrace *)v133,
            *(struct IFSClientContextInfo **)(a1 + 168));
    v31 = FSString::GetString(v30);
    WPP_SF_qssddS(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)v31, (__int64)String, Data1, a6, v27);
    v17 = 3;
  }
  if ( (v17 & 2) != 0 )
  {
    v17 &= ~2u;
    FSString::~FSString((FSString *)v133);
  }
  if ( (v17 & 1) != 0 )
  {
    v17 &= ~1u;
    FSString::~FSString((FSString *)v132);
  }
  v32 = (_QWORD *)(a1 + 104);
  if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 104) + 24LL))(*(_QWORD *)(a1 + 104)) == 4
    && (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v32 + 48LL))(*v32) )
  {
    v33 = *v32;
    *(_QWORD *)&v133[0] = 0;
    v114 = 0;
    v112 = 0;
    v116 = 0;
    v34 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v33 + 56LL))(v33, 0);
    if ( (int)MFCreateSensorGroupWithOptions(v34, 0, &v116) >= 0 )
    {
      v35 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v116;
      v36 = **v116;
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(v133);
      if ( v36(v35, &GUID_fa993888_4383_415a_a930_dd472a8cf6f7, v133) >= 0 )
      {
        v37 = **(_QWORD **)&v133[0];
        v114 = 0;
        if ( (*(int (__fastcall **)(_QWORD, GUID *, GUID *, FSPinInfo **))(v37 + 24))(
               *(_QWORD *)&v133[0],
               &GUID_00000000_0000_0000_0000_000000000000,
               &GUID_c95ea55b_0187_48be_9353_8d2507662351,
               &v114) >= 0 )
        {
          v38 = v114;
          v39 = *(void (__fastcall **)(FSPinInfo *, struct _GUID *, struct IFSClientContextInfo **))(*(_QWORD *)v114 + 48LL);
          wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v112);
          v39(v38, a5, &v112);
        }
      }
    }
    v40 = v112;
    if ( !v112 )
    {
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v112);
      v41 = MFCreateSensorProfileWithFlags(a5, 0x40000000, &v112);
      LOBYTE(v18) = v41;
      if ( v41 < 0 )
      {
        if ( !g_wppLevels )
        {
LABEL_39:
          wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v112);
          wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v114);
          wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(v133);
          wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v116);
          goto LABEL_197;
        }
        v42 = 30;
LABEL_38:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v42, &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids, a1, v41);
        goto LABEL_39;
      }
      v40 = v112;
    }
    v43 = **(__int64 (__fastcall ***)(struct IFSClientContextInfo *, GUID *, __int64))v40;
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(a1 + 264);
    v41 = v43(v40, &GUID_b35b06ef_9123_4604_a586_9750cdd2c67d, a1 + 264);
    LOBYTE(v18) = v41;
    if ( v41 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_39;
      v42 = 31;
      goto LABEL_38;
    }
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v112);
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v114);
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(v133);
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v116);
    v32 = (_QWORD *)(a1 + 104);
  }
  if ( !*(_QWORD *)(a1 + 96) )
  {
    LODWORD(v18) = -2147418113;
    if ( !g_wppLevels )
      goto LABEL_197;
    v44 = 32;
    goto LABEL_196;
  }
  if ( !v125 )
  {
    LOBYTE(v18) = 87;
    if ( !g_wppLevels )
      goto LABEL_197;
    v19 = 33;
    goto LABEL_4;
  }
  if ( !v122 )
  {
    LOBYTE(v18) = 87;
    if ( !g_wppLevels )
      goto LABEL_197;
    v19 = 34;
    goto LABEL_4;
  }
  if ( *(_QWORD *)(a1 + 160) )
  {
    LODWORD(v18) = -1072875854;
    if ( !g_wppLevels )
      goto LABEL_197;
    v44 = 35;
    goto LABEL_196;
  }
  v110 = 0;
  v45 = (char *)(a1 + 288);
  if ( (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v32 + 32LL))(*v32) )
  {
    if ( a1 != -288 )
    {
      v46 = 0;
      v47 = 0;
      goto LABEL_63;
    }
    v46 = 3;
  }
  else
  {
    v46 = 87;
  }
  v47 = 1;
LABEL_63:
  *v45 = v47;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v109 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v32 + 32LL))(*v32);
    v48 = "true";
    if ( !*v45 )
      v48 = "false";
    WPP_SF_qDSsS(*((_QWORD *)WPP_GLOBAL_Control + 27), v46, (__int64)v134, (__int64)v48, v109);
  }
  if ( !*(_DWORD *)(a1 + 56) )
  {
    v49 = v124;
    v21 = FSSourceInfo::ConfigureProfile((FSSourceInfo *)a1, v124, (struct __MIDL___MIDL_itf_mfidl_0000_0114_0001 *)a5);
    LOBYTE(v18) = v21;
    if ( v21 < 0 )
    {
      if ( g_wppLevels )
      {
        v22 = 37;
        goto LABEL_15;
      }
      goto LABEL_197;
    }
    v50 = v121;
    v121 = 0;
    if ( v50 )
      (*(void (__fastcall **)(_QWORD *))(*v50 + 16LL))(v50);
    v21 = MFCreateSensorGroupIdManager(&v121);
    LOBYTE(v18) = v21;
    if ( v21 < 0 )
    {
      if ( g_wppLevels )
      {
        v22 = 38;
        goto LABEL_15;
      }
      goto LABEL_197;
    }
    v51 = v120;
    v52 = v121;
    v53 = *v121;
    v120 = 0;
    v18 = *(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v53 + 32);
    if ( v51 )
      (*(void (__fastcall **)(_QWORD *))(*v51 + 16LL))(v51);
    v21 = ((__int64 (__fastcall *)(_QWORD *, _QWORD, _QWORD, _QWORD **))v18)(v52, 0, 0, &v120);
    LOBYTE(v18) = v21;
    if ( v21 < 0 )
    {
      if ( g_wppLevels )
      {
        v22 = 39;
        goto LABEL_15;
      }
      goto LABEL_197;
    }
    v54 = v117;
    v55 = v120;
    v56 = (__int64 (__fastcall **)(_QWORD, GUID *, __int64))*v120;
    v117 = 0;
    v18 = *v56;
    if ( v54 )
      (*(void (__fastcall **)(__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD)))(*(_QWORD *)v54 + 16LL))(v54);
    v21 = v18(v55, &GUID_1725de0f_cf7a_4075_9365_d8c5d1eea8d7, (__int64)&v117);
    LOBYTE(v18) = v21;
    if ( v21 < 0 )
    {
      if ( g_wppLevels )
      {
        v22 = 40;
        goto LABEL_15;
      }
      goto LABEL_197;
    }
    v18 = (__int64 (__fastcall *)(_QWORD, GUID *, __int64))v117;
    v57 = *(__int64 (__fastcall **)(__int64 (__fastcall *)(_QWORD, GUID *, __int64), __int64))(*(_QWORD *)v117 + 64LL);
    v58 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v32 + 32LL))(*v32);
    v21 = v57(v18, v58);
    LOBYTE(v18) = v21;
    if ( v21 < 0 )
    {
      if ( g_wppLevels )
      {
        v22 = 41;
        goto LABEL_15;
      }
      goto LABEL_197;
    }
    v21 = (*(__int64 (__fastcall **)(__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD), _QWORD))(*(_QWORD *)v117 + 72LL))(
            v117,
            0);
    LOBYTE(v18) = v21;
    if ( v21 < 0 )
    {
      if ( g_wppLevels )
      {
        v22 = 42;
        goto LABEL_15;
      }
      goto LABEL_197;
    }
    *(_QWORD *)(a1 + 280) = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v32 + 192LL))(*v32);
    v59 = (_QWORD *)(a1 + 168);
    v60 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 168) + 40LL))(*(_QWORD *)(a1 + 168));
    FSSourceInfo::GetQuota(a1, v60 != 0, &v113, &v115);
    v61 = *(_QWORD *)(a1 + 96);
    v116 = 0;
    v62 = *(int (__fastcall **)(__int64, int (__fastcall ****)(_QWORD, GUID *, _OWORD *)))(*(_QWORD *)v61 + 288LL);
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v116);
    if ( v62(v61, &v116) >= 0 )
    {
      v63 = MFGetAttributeUINT32(v116, &MF_DEVPROXY_COMPRESSED_MEDIATYPE_PASSTHROUGH_MODE, 0);
      *(_BYTE *)(a1 + 208) = v63 != 0;
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
      {
        v64 = "enabled";
        if ( !v63 )
          v64 = "disabled";
        WPP_SF_qs(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          43,
          (unsigned int)&WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids,
          a1,
          (__int64)v64);
      }
    }
    if ( *(_BYTE *)(a1 + 208)
      && v49
      && (lpVtbl = v49->lpVtbl,
          v133[0] = GUID_00000000_0000_0000_0000_000000000000,
          ((int (__fastcall *)(struct IMFAttributes *, const IID *, _OWORD *))lpVtbl->GetGUID)(
            v49,
            &MF_CAPTURE_ENGINE_SELECTEDCAMERAPROFILE,
            v133) >= 0)
      && !(*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v59 + 32LL))(*v59) )
    {
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 44, &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids, a1);
      v110 = 1;
    }
    else
    {
      v110 = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v59 + 104LL))(*v59) != 0;
    }
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v116);
    if ( *(_BYTE *)(a1 + 208)
      && (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v59 + 40LL))(*v59)
      && !(*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v59 + 32LL))(*v59)
      && !(*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v59 + 80LL))(*v59) )
    {
      v18 = *(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(a1 + 96);
      v112 = 0;
      v66 = *(__int64 (__fastcall **)(__int64 (__fastcall *)(_QWORD, GUID *, __int64), struct IFSClientContextInfo **))(*(_QWORD *)v18 + 272LL);
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v112);
      v67 = v66(v18, &v112);
      LOBYTE(v18) = v67;
      if ( v67 < 0 )
      {
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids, a1, v67);
LABEL_121:
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v112);
        goto LABEL_197;
      }
      v68 = v112;
      if ( v112 )
      {
        if ( !(*(unsigned int (__fastcall **)(struct IFSClientContextInfo *))(*(_QWORD *)v112 + 40LL))(v112) )
        {
          v69 = v112;
          v70 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v59 + 136LL))(*v59);
          if ( (*(unsigned int (__fastcall **)(struct IFSClientContextInfo *))(*(_QWORD *)v69 + 136LL))(v69) != v70 )
          {
            if ( byte_18010EC4D )
            {
              v17 |= 4u;
              v71 = ClientContextInfoTrace::ClientContextInfoTrace((ClientContextInfoTrace *)v133, v112);
              v72 = FSString::GetString(v71);
              WPP_SF_qs(
                *((_QWORD *)WPP_GLOBAL_Control + 27),
                46,
                (unsigned int)&WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids,
                a1,
                (__int64)v72);
            }
            if ( (v17 & 4) != 0 )
              FSString::~FSString((FSString *)v133);
            LOBYTE(v18) = 32;
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                47,
                &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids,
                a1,
                -2147024864);
            goto LABEL_121;
          }
        }
        v68 = v112;
      }
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
      {
        v17 |= 8u;
        v73 = ClientContextInfoTrace::ClientContextInfoTrace((ClientContextInfoTrace *)v133, v68);
        v74 = FSString::GetString(v73);
        WPP_SF_qs(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          48,
          (unsigned int)&WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids,
          a1,
          (__int64)v74);
      }
      if ( (v17 & 8) != 0 )
        FSString::~FSString((FSString *)v133);
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v112);
    }
    v75 = pBuf;
    if ( pBuf && cbBufSize )
    {
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(a1 + 216);
      v21 = MFCreateAttributes((IMFAttributes **)(a1 + 216), 1u);
      LOBYTE(v18) = v21;
      if ( v21 < 0 )
      {
        if ( g_wppLevels )
        {
          v22 = 49;
          goto LABEL_15;
        }
        goto LABEL_197;
      }
      v21 = MFInitAttributesFromBlob(*(IMFAttributes **)(a1 + 216), v75, cbBufSize);
      LOBYTE(v18) = v21;
      if ( v21 < 0 )
      {
        if ( g_wppLevels )
        {
          v22 = 50;
          goto LABEL_15;
        }
        goto LABEL_197;
      }
    }
    if ( v123 )
    {
      if ( a9 )
      {
        v21 = FSDeserializeAttributeArray((unsigned int *)v123, a9, (__int64)&v126);
        LOBYTE(v18) = v21;
        if ( v21 < 0 )
        {
          if ( g_wppLevels )
          {
            v22 = 51;
            goto LABEL_15;
          }
          goto LABEL_197;
        }
      }
    }
    v118 = v115;
    v119 = v113;
  }
  v76 = *(__int64 **)(a1 + 96);
  v77 = *(_QWORD *)(a1 + 120);
  v78 = *v76;
  *(_QWORD *)(a1 + 120) = 0;
  v79 = *(void (__fastcall **)(__int64 *, __int64))(v78 + 192);
  if ( v77 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
  v79(v76, a1 + 120);
  if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 104) + 24LL))(*(_QWORD *)(a1 + 104)) == 4 )
    v80 = FSSourceInfo::MergePinAttributes_MEPProfileExEnabled(a1, &v126);
  else
    v80 = FSSourceInfo::MergePinAttributes_MEPProfileExDisabled(a1, &v126);
  LODWORD(v18) = v80;
  if ( v80 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_197;
    v44 = 52;
    goto LABEL_196;
  }
  v81 = *(_DWORD *)(a1 + 56) == 0;
  v82 = *(_DWORD *)(a1 + 232);
  LODWORD(v112) = v82;
  if ( !v81 )
    goto LABEL_172;
  v83 = 0;
  v115 = 0;
  if ( !v82 )
    goto LABEL_172;
  while ( 1 )
  {
    v84 = *(_QWORD *)(a1 + 168);
    v113 = 0;
    v114 = 0;
    v111 = 0;
    if ( (*(unsigned int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v84 + 208LL))(v84, 0) )
    {
      if ( *(_DWORD *)(a1 + 136) )
        break;
    }
    v85 = *(_QWORD *)(*(_QWORD *)(a1 + 224) + 8 * v83);
    if ( (*(int (__fastcall **)(__int64, const IID *, unsigned int *))(*(_QWORD *)v85 + 56LL))(
           v85,
           &MF_DEVICESTREAM_TRANSFORM_STREAM_ID,
           &v113) < 0 )
    {
      v86 = *(_QWORD *)(*(_QWORD *)(a1 + 224) + 8 * v83);
      v87 = (*(__int64 (__fastcall **)(__int64, const IID *, unsigned int *))(*(_QWORD *)v86 + 56LL))(
              v86,
              &MF_DEVICESTREAM_STREAM_ID,
              &v113);
      LOBYTE(v18) = v87;
      if ( v87 < 0 )
      {
        if ( g_wppLevels )
        {
          v100 = 54;
          goto LABEL_189;
        }
        goto LABEL_190;
      }
    }
    if ( FSSourceInfo::ShouldAddPin(
           (FSSourceInfo *)a1,
           v130,
           v83,
           *(struct IMFAttributes **)(*(_QWORD *)(a1 + 224) + 8 * v83)) )
    {
      v89 = (FSPinInfo *)operator new(0x1F0u);
      v123 = v89;
      if ( v89 )
      {
        v90 = *(struct IMFSensorProfileInternal **)(a1 + 264);
        v91 = *(struct IMFSensorProfile **)(a1 + 248);
        v92 = *(struct IMFAttributes **)(*(_QWORD *)(a1 + 224) + 8 * v83);
        v93 = v83 + *v122;
        v94 = v113;
        v95 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 536LL))(*(_QWORD *)(a1 + 96));
        v89 = FSPinInfo::FSPinInfo(
                v123,
                (struct FSSourceInfo *)a1,
                *(struct FSClientContext **)(a1 + 152),
                *(struct IFSCCInfoConfiguration **)(a1 + 168),
                v95,
                v119,
                v118,
                v94,
                v115,
                v93,
                v91,
                v90,
                v110,
                v92);
        LODWORD(v83) = v115;
        v82 = (unsigned int)v112;
      }
      wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=(&v114, v89);
      v96 = v114;
      if ( !v114 )
      {
        v87 = -2147024882;
        LOBYTE(v18) = 14;
        if ( g_wppLevels )
        {
          v100 = 56;
LABEL_189:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v100,
            &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids,
            a1,
            v87);
        }
LABEL_190:
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v114);
        goto LABEL_197;
      }
      v87 = FSPinInfo::CheckMediaTypesAgainstProfile(v114, *(struct IFSSource **)(a1 + 96), v124, &v111);
      LOBYTE(v18) = v87;
      if ( v87 < 0 )
      {
        if ( g_wppLevels )
        {
          v100 = 57;
          goto LABEL_189;
        }
        goto LABEL_190;
      }
      if ( v111 )
      {
        FSPinInfo::ClosePin(v96, 1);
        if ( (unsigned __int8)byte_18010EC4D >= 8u )
        {
          v88 = 60;
          goto LABEL_170;
        }
      }
      else
      {
        if ( !(unsigned int)CTUnkArray<IMFMediaType>::Add(a1 + 128, v96)
          || !(unsigned int)CTUnkArray<IMFMediaType>::Add(v131, v96) )
        {
          v87 = -2147024882;
          LOBYTE(v18) = 14;
          if ( g_wppLevels )
          {
            v100 = 58;
            goto LABEL_189;
          }
          goto LABEL_190;
        }
        if ( (unsigned __int8)byte_18010EC4D >= 8u )
        {
          v88 = 59;
          goto LABEL_170;
        }
      }
    }
    else if ( (unsigned __int8)byte_18010EC4D >= 8u )
    {
      v88 = 55;
LABEL_170:
      WPP_SF_qDD(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        v88,
        &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids,
        a1,
        v83,
        v113);
    }
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v114);
    v83 = (unsigned int)(v83 + 1);
    v115 = v83;
    if ( (unsigned int)v83 >= v82 )
      goto LABEL_172;
  }
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_qDD(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      53,
      &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids,
      a1,
      v83,
      v113);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v114);
LABEL_172:
  v97 = 0;
  *v122 += v82;
  v98 = *(_DWORD *)(a1 + 136);
  if ( v98 )
  {
    while ( 1 )
    {
      v21 = FSPinInfo::Initialize(
              *(FSPinInfo **)(*(_QWORD *)(a1 + 128) + 8 * v97),
              *(struct IFSSource **)(a1 + 96),
              (int)v97 + a6,
              *(struct IDeviceAccessHandler **)(a1 + 200));
      LOBYTE(v18) = v21;
      if ( v21 < 0 )
        break;
      v97 = (unsigned int)(v97 + 1);
      if ( (unsigned int)v97 >= v98 )
        goto LABEL_175;
    }
    if ( g_wppLevels )
    {
      v22 = 61;
LABEL_15:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v22, &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids, a1, v21);
    }
    goto LABEL_197;
  }
LABEL_175:
  v21 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(**(_QWORD **)(a1 + 96) + 104LL))(
          *(_QWORD *)(a1 + 96),
          a1,
          *(_QWORD *)(a1 + 168),
          a1 + 160);
  LOBYTE(v18) = v21;
  if ( v21 >= 0 )
  {
    v101 = v125;
    *v125 = v98;
    v18 = *(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(a1 + 96);
    v102 = *(__int64 (__fastcall **)(__int64 (__fastcall *)(_QWORD, GUID *, __int64), bool))(*(_QWORD *)v18 + 376LL);
    IsTorchControlSharingEnabled = FSSourceInfo::IsTorchControlSharingEnabled(v99);
    LODWORD(v18) = v102(v18, IsTorchControlSharingEnabled);
    if ( (int)v18 >= 0 )
    {
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
      {
        v106 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 104) + 32LL))(*(_QWORD *)(a1 + 104));
        WPP_SF_qDqdiS(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          v107,
          v108,
          a1,
          (char)v18,
          *(_QWORD *)(a1 + 152),
          *v101,
          *(_QWORD *)(a1 + 160),
          v106);
      }
      goto LABEL_204;
    }
    if ( !g_wppLevels )
      goto LABEL_197;
    v44 = 63;
LABEL_196:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v44,
      &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids,
      a1,
      (_DWORD)v18);
    goto LABEL_197;
  }
  if ( g_wppLevels )
  {
    v22 = 62;
    goto LABEL_15;
  }
LABEL_197:
  if ( byte_18010EC4D )
  {
    v104 = *(_QWORD *)(a1 + 104);
    if ( v104 )
      v105 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v104 + 32LL))(v104);
    else
      v105 = L"<unknown>";
    WPP_SF_qDS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      64,
      (unsigned int)&WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids,
      a1,
      (char)v18,
      (__int64)v105);
  }
LABEL_204:
  CTUnkArray<IFSProcessActivity>::~CTUnkArray<IFSProcessActivity>(&v126);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v117);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v120);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v121);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
}

```

## disassembly

```asm
0x180083780  mov     [rsp-8+arg_18], rbx
0x180083785  push    rbp
0x180083786  push    rsi
0x180083787  push    rdi
0x180083788  push    r12
0x18008378a  push    r13
0x18008378c  push    r14
0x18008378e  push    r15
0x180083790  lea     rbp, [rsp-270h]
0x180083798  sub     rsp, 370h
0x18008379f  mov     rax, cs:__security_cookie
0x1800837a6  xor     rax, rsp
0x1800837a9  mov     [rbp+2A0h+var_40], rax
0x1800837b0  mov     rax, [rbp+2A0h+arg_38]
0x1800837b7  mov     r13, rcx
0x1800837ba  mov     rcx, [rbp+2A0h+arg_48]
0x1800837c1  xor     esi, esi
0x1800837c3  mov     r12, [rbp+2A0h+arg_20]
0x1800837ca  mov     r14d, r9d
0x1800837cd  mov     [rbp+2A0h+pBuf], rax
0x1800837d1  mov     rbx, r8
0x1800837d4  mov     rax, [rbp+2A0h+arg_50]
0x1800837db  mov     r15d, esi
0x1800837de  mov     [rbp+2A0h+var_2D0], rax
0x1800837e2  mov     rax, [rbp+2A0h+arg_58]
0x1800837e9  mov     [rbp+2A0h+var_2C8], rax
0x1800837ed  mov     rax, [rbp+2A0h+arg_60]
0x1800837f4  mov     [rbp+2A0h+var_298], rax
0x1800837f8  mov     rax, [rbp+2A0h+arg_68]
0x1800837ff  mov     [rbp+2A0h+var_2D8], rcx
0x180083803  lea     rcx, [r13+10h]; lpCriticalSection
0x180083807  mov     [rbp+2A0h+var_2E0], rax
0x18008380b  mov     [rbp+2A0h+var_2A0], rdx
0x18008380f  mov     dword ptr [rsp+3A0h+var_328], esi
0x180083813  call    cs:__imp_EnterCriticalSection
0x180083819  mov     eax, esi
0x18008381b  mov     [rbp+2A0h+var_2E8], rsi
0x18008381f  xor     edx, edx; Val
0x180083821  mov     [rbp+2A0h+var_2F8], eax
0x180083824  mov     r8d, 208h; Size
0x18008382a  mov     [rbp+2A0h+var_310], eax
0x18008382d  lea     rcx, [rbp+2A0h+var_250]; void *
0x180083831  mov     [rbp+2A0h+var_2F4], eax
0x180083834  mov     [rbp+2A0h+var_320], eax
0x180083837  mov     [rbp+2A0h+var_2F0], rsi
0x18008383b  mov     [rbp+2A0h+var_300], rsi
0x18008383f  call    memset_0
0x180083844  mov     [rbp+2A0h+var_2C0], rsi
0x180083848  mov     [rbp+2A0h+var_2B4], rsi
0x18008384c  mov     [rbp+2A0h+var_2B8], esi
0x18008384f  test    r12, r12
0x180083852  jnz     short loc_180083876
0x180083854  mov     ebx, 80070057h
0x180083859  mov     esi, ebx
0x18008385b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1
0x180083862  jb      loc_180084804
0x180083868  lea     edx, [r12+18h]
0x18008386d  mov     dword ptr [rsp+3A0h+var_380], ebx
0x180083871  jmp     loc_1800847EA
0x180083876  test    rbx, rbx
0x180083879  jnz     short loc_180083896
0x18008387b  mov     ebx, 80070057h
0x180083880  mov     esi, ebx
0x180083882  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1
0x180083889  jb      loc_180084804
0x18008388f  mov     edx, 19h
0x180083894  jmp     short loc_18008386D
0x180083896  mov     rax, [rbx]
0x180083899  xor     edx, edx
0x18008389b  mov     rcx, rbx
0x18008389e  mov     rax, [rax+0D0h]
0x1800838a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800838aa  test    eax, eax
0x1800838ac  mov     esi, 1
0x1800838b1  cmovz   esi, r14d
0x1800838b5  lea     r14, [r13+0A8h]
0x1800838bc  mov     rcx, [r14]
0x1800838bf  mov     [r14], r15
0x1800838c2  test    rcx, rcx
0x1800838c5  jz      short loc_1800838D3
0x1800838c7  mov     rax, [rcx]
0x1800838ca  mov     rax, [rax+10h]
0x1800838ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800838d3  mov     r8d, [r13+38h]
0x1800838d7  lea     rax, _GUID_c948ed26_2196_401e_ab0c_84cc1b3067bc
0x1800838de  mov     qword ptr [rsp+3A0h+var_370], r14
0x1800838e3  xor     r9d, r9d
0x1800838e6  mov     qword ptr [rsp+3A0h+var_378], rax
0x1800838eb  mov     edx, esi
0x1800838ed  mov     rcx, rbx
0x1800838f0  mov     [rsp+3A0h+var_380], r15b
0x1800838f5  call    ?CloneFSClientContextInfo@FSClientContextInfo@@SAJPEAUIFSClientContextInfo@@W4__MIDL___MIDL_itf_fsclienttypes_0000_0000_0001@@W4__MIDL___MIDL_itf_fsclienttypes_0000_0000_0018@@_N3AEBU_GUID@@PEAPEAX@Z
0x1800838fa  mov     esi, eax
0x1800838fc  test    eax, eax
0x1800838fe  jns     short loc_18008391B
0x180083900  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1
0x180083907  jb      loc_180084804
0x18008390d  mov     edx, 1Ah
0x180083912  mov     dword ptr [rsp+3A0h+var_380], eax
0x180083916  jmp     loc_1800847EA
0x18008391b  mov     rsi, [r13+60h]
0x18008391f  lea     rcx, [r13+68h]
0x180083923  mov     rax, [rsi]
0x180083926  mov     rbx, [rax+30h]
0x18008392a  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ
0x18008392f  lea     rdx, [r13+68h]
0x180083933  mov     rcx, rsi
0x180083936  mov     rax, rbx
0x180083939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008393e  mov     esi, eax
0x180083940  test    eax, eax
0x180083942  jns     short loc_180083958
0x180083944  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1
0x18008394b  jb      loc_180084804
0x180083951  mov     edx, 1Bh
0x180083956  jmp     short loc_180083912
0x180083958  mov     r14, [r13+60h]
0x18008395c  lea     rcx, [r13+70h]
0x180083960  mov     rax, [r14]
0x180083963  mov     rsi, [rax]
0x180083966  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ
0x18008396b  lea     r8, [r13+70h]
0x18008396f  mov     rcx, r14
0x180083972  lea     rdx, _GUID_7eec0fa2_0911_4614_be40_60253271e04d
0x180083979  mov     rax, rsi
0x18008397c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083981  mov     esi, eax
0x180083983  test    eax, eax
0x180083985  jns     short loc_18008399E
0x180083987  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1
0x18008398e  jb      loc_180084804
0x180083994  mov     edx, 1Ch
0x180083999  jmp     loc_180083912
0x18008399e  cmp     cs:byte_18010EC4D, 8
0x1800839a5  jb      loc_180083A2C
0x1800839ab  mov     rcx, [r13+68h]
0x1800839af  mov     rax, [rcx]
0x1800839b2  mov     rax, [rax+20h]
0x1800839b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800839bb  mov     r14d, [r12+10h]
0x1800839c0  lea     rcx, [rbp+2A0h+var_290]; this
0x1800839c4  mov     rdx, r12; struct _GUID *
0x1800839c7  mov     rsi, rax
0x1800839ca  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z
0x1800839cf  mov     rcx, rax; this
0x1800839d2  call    ?GetString@GuidTrace@@QEBAPEBDXZ
0x1800839d7  mov     rdx, [r13+0A8h]; struct IFSClientContextInfo *
0x1800839de  lea     rcx, [rbp+2A0h+var_270]; this
0x1800839e2  mov     rbx, rax
0x1800839e5  call    ??0ClientContextInfoTrace@@QEAA@PEAUIFSClientContextInfo@@@Z
0x1800839ea  mov     rcx, rax; this
0x1800839ed  call    ?GetString@FSString@@QEBAPEBDXZ
0x1800839f2  mov     ecx, dword ptr [rbp+2A0h+arg_28]
0x1800839f8  mov     r9, r13
0x1800839fb  mov     qword ptr [rsp+3A0h+var_360], rsi; __int64
0x180083a00  mov     dword ptr [rsp+3A0h+var_368], ecx; char
0x180083a04  mov     rcx, cs:WPP_GLOBAL_Control
0x180083a0b  mov     dword ptr [rsp+3A0h+var_370], r14d; char
0x180083a10  mov     qword ptr [rsp+3A0h+var_378], rbx; __int64
0x180083a15  mov     qword ptr [rsp+3A0h+var_380], rax; __int64
0x180083a1a  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180083a21  call    WPP_SF_qssddS
0x180083a26  mov     r15d, 3
0x180083a2c  test    r15b, 2
0x180083a30  jz      short loc_180083A3F
0x180083a32  and     r15d, 0FFFFFFFDh
0x180083a36  lea     rcx, [rbp+2A0h+var_270]; this
0x180083a3a  call    ??1FSString@@QEAA@XZ
0x180083a3f  test    r15b, 1
0x180083a43  jz      short loc_180083A52
0x180083a45  and     r15d, 0FFFFFFFEh
0x180083a49  lea     rcx, [rbp+2A0h+var_290]; this
0x180083a4d  call    ??1FSString@@QEAA@XZ
0x180083a52  lea     r14, [r13+68h]
0x180083a56  mov     rcx, [r14]
0x180083a59  mov     rax, [rcx]
0x180083a5c  mov     rax, [rax+18h]
0x180083a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083a65  cmp     eax, 4
0x180083a68  jnz     loc_180083C5F
0x180083a6e  mov     rcx, [r14]
0x180083a71  mov     rax, [rcx]
0x180083a74  mov     rax, [rax+30h]
0x180083a78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083a7d  cmp     eax, 1
0x180083a80  jb      loc_180083C5F
0x180083a86  mov     rcx, [r14]
0x180083a89  xor     edx, edx
0x180083a8b  mov     qword ptr [rbp+2A0h+var_270], 0
0x180083a93  mov     [rbp+2A0h+var_318], 0
0x180083a9b  mov     [rsp+3A0h+var_328], 0
0x180083aa4  mov     [rbp+2A0h+var_308], 0
0x180083aac  mov     rax, [rcx]
0x180083aaf  mov     rax, [rax+38h]
0x180083ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083ab8  lea     r8, [rbp+2A0h+var_308]
0x180083abc  xor     edx, edx
0x180083abe  mov     rcx, rax
0x180083ac1  call    cs:__imp_MFCreateSensorGroupWithOptions
0x180083ac7  test    eax, eax
0x180083ac9  js      loc_180083B6D
0x180083acf  mov     rsi, [rbp+2A0h+var_308]
0x180083ad3  lea     rcx, [rbp+2A0h+var_270]
0x180083ad7  mov     rax, [rsi]
0x180083ada  mov     rbx, [rax]
0x180083add  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ
0x180083ae2  lea     r8, [rbp+2A0h+var_270]
0x180083ae6  mov     rcx, rsi
0x180083ae9  lea     rdx, _GUID_fa993888_4383_415a_a930_dd472a8cf6f7
0x180083af0  mov     rax, rbx
0x180083af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083af8  test    eax, eax
0x180083afa  js      short loc_180083B6D
0x180083afc  mov     rcx, [rbp+2A0h+var_318]
0x180083b00  mov     rbx, qword ptr [rbp+2A0h+var_270]
0x180083b04  mov     rax, [rbx]
0x180083b07  mov     [rbp+2A0h+var_318], 0
0x180083b0f  mov     rsi, [rax+18h]
0x180083b13  test    rcx, rcx
0x180083b16  jz      short loc_180083B24
0x180083b18  mov     rdx, [rcx]
0x180083b1b  mov     rax, [rdx+10h]
0x180083b1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083b24  lea     r9, [rbp+2A0h+var_318]
0x180083b28  mov     rcx, rbx
0x180083b2b  lea     r8, _GUID_c95ea55b_0187_48be_9353_8d2507662351
0x180083b32  mov     rax, rsi
0x180083b35  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000
0x180083b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083b41  test    eax, eax
0x180083b43  js      short loc_180083B6D
0x180083b45  mov     rsi, [rbp+2A0h+var_318]
0x180083b49  lea     rcx, [rsp+3A0h+var_328]
0x180083b4e  mov     rax, [rsi]
0x180083b51  mov     rbx, [rax+30h]
0x180083b55  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ
0x180083b5a  lea     r8, [rsp+3A0h+var_328]
0x180083b5f  mov     rdx, r12
0x180083b62  mov     rcx, rsi
0x180083b65  mov     rax, rbx
0x180083b68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083b6d  mov     rbx, [rsp+3A0h+var_328]
0x180083b72  test    rbx, rbx
0x180083b75  jnz     short loc_180083BF3
0x180083b77  lea     rcx, [rsp+3A0h+var_328]
0x180083b7c  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ
0x180083b81  lea     r8, [rsp+3A0h+var_328]
0x180083b86  mov     edx, 40000000h
0x180083b8b  mov     rcx, r12
0x180083b8e  call    cs:__imp_MFCreateSensorProfileWithFlags
0x180083b94  mov     esi, eax
0x180083b96  test    eax, eax
0x180083b98  jns     short loc_180083BEE
0x180083b9a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1
0x180083ba1  jb      short loc_180083BC4
0x180083ba3  lea     edx, [rbx+1Eh]
0x180083ba6  mov     rcx, cs:WPP_GLOBAL_Control
0x180083bad  lea     r8, WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids
0x180083bb4  mov     r9, r13
0x180083bb7  mov     dword ptr [rsp+3A0h+var_380], eax
0x180083bbb  mov     rcx, [rcx+10h]
0x180083bbf  call    WPP_SF_qD
0x180083bc4  lea     rcx, [rsp+3A0h+var_328]; void *
0x180083bc9  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ
0x180083bce  lea     rcx, [rbp+2A0h+var_318]; void *
0x180083bd2  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ
0x180083bd7  lea     rcx, [rbp+2A0h+var_270]; void *
0x180083bdb  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ
0x180083be0  lea     rcx, [rbp+2A0h+var_308]; void *
0x180083be4  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ
0x180083be9  jmp     loc_180084804
0x180083bee  mov     rbx, [rsp+3A0h+var_328]
0x180083bf3  mov     rax, [rbx]
0x180083bf6  lea     rsi, [r13+108h]
0x180083bfd  mov     rcx, rsi
0x180083c00  mov     r14, [rax]
0x180083c03  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ
0x180083c08  mov     r8, rsi
0x180083c0b  lea     rdx, _GUID_b35b06ef_9123_4604_a586_9750cdd2c67d
0x180083c12  mov     rcx, rbx
0x180083c15  mov     rax, r14
0x180083c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083c1d  mov     esi, eax
0x180083c1f  test    eax, eax
0x180083c21  jns     short loc_180083C36
0x180083c23  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1
0x180083c2a  jb      short loc_180083BC4
0x180083c2c  mov     edx, 1Fh
0x180083c31  jmp     loc_180083BA6
0x180083c36  lea     rcx, [rsp+3A0h+var_328]; void *
0x180083c3b  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ
0x180083c40  lea     rcx, [rbp+2A0h+var_318]; void *
0x180083c44  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ
0x180083c49  lea     rcx, [rbp+2A0h+var_270]; void *
0x180083c4d  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ
0x180083c52  lea     rcx, [rbp+2A0h+var_308]; void *
0x180083c56  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ
0x180083c5b  lea     r14, [r13+68h]
0x180083c5f  cmp     qword ptr [r13+60h], 0
0x180083c64  jnz     short loc_180083C82
  ... truncated ...
```
