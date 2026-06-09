# TieringHeatSession::GetMovementsListForDiskOptimizer(_STORAGE_TIER_CLASS,ulong,TieringMovementSession *,_TE_ENUM_INTERNAL_RESUME_KEY *,int *,long *,__MIDL___MIDL_itf_tieringengine_0000_0000_0005 * *)

- ea: `0x140021a28`
- end: `0x140022872`
- name: `?GetMovementsListForDiskOptimizer@TieringHeatSession@@QEAAJW4_STORAGE_TIER_CLASS@@KPEAVTieringMovementSession@@PEAU_TE_ENUM_INTERNAL_RESUME_KEY@@PEAHPEAJPEAPEAU__MIDL___MIDL_itf_tieringengine_0000_0000_0005@@@Z`
- size: `3658`
- prototype: `__int64 __fastcall(TieringHeatSession *this, enum _STORAGE_TIER_CLASS, unsigned int, struct TieringMovementSession *, struct _TE_ENUM_INTERNAL_RESUME_KEY *, int *, int *, struct __MIDL___MIDL_itf_tieringengine_0000_0000_0005 **)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14003ddd4`

## callees

- `0x14000148c`
- `0x140002323`
- `0x140002db0`
- `0x140004ef0`
- `0x140005420`
- `0x140009a04`
- `0x140009c08`
- `0x14000b7f8`
- `0x140017e78`
- `0x14001cd80`
- `0x14001d534`
- `0x14001d960`
- `0x140020e1c`
- `0x140021a28`
- `0x1400259f4`
- `0x140025bc0`
- `0x1400261c8`
- `0x140028e7c`
- `0x14003fb76`
- `0x14003fbb0`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x1400223bc`
- `ntdll!RtlCompareMemory` at `0x1400223bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140021ec9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140021ec9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140021ae8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140021b06`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400220f3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14002210d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140021ae8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140021b06`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400220f3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14002210d`
- `ESENT!JetMove` at `0x140021c41`
- `ESENT!JetMove` at `0x140021f61`
- `ESENT!JetMove` at `0x140021c41`
- `ESENT!JetMove` at `0x140021f61`

## string_xrefs

- `0x140021a8f`: `TieringHeatSession::GetMovementsListForDiskOptimizer`

## pseudocode

```c
__int64 __fastcall TieringHeatSession::GetMovementsListForDiskOptimizer(
        TieringHeatSession *this,
        enum _STORAGE_TIER_CLASS a2,
        unsigned int a3,
        struct TieringMovementSession *a4,
        struct _TE_ENUM_INTERNAL_RESUME_KEY *a5,
        int *a6,
        int *a7,
        struct __MIDL___MIDL_itf_tieringengine_0000_0000_0005 **a8)
{
  __int64 *ThreadLocalStoragePointer; // rax
  __int64 v11; // rcx
  unsigned int v12; // r14d
  __int64 *v13; // rax
  __int64 v14; // rbx
  int v15; // r9d
  JET_SESID *v16; // rbx
  JET_TABLEID *v17; // rax
  unsigned int v18; // ebx
  JET_ERR v19; // r8d
  int v20; // eax
  _QWORD *v21; // rcx
  JET_ERR CurrentMovementRecord; // eax
  __int64 *v24; // rdx
  __int64 v25; // rbx
  __int64 v26; // r9
  unsigned int v27; // eax
  unsigned int v28; // eax
  SIZE_T v29; // rbx
  void *v30; // rax
  unsigned int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // r9
  __int64 v34; // r8
  unsigned int v35; // eax
  int v36; // eax
  _QWORD *v37; // r10
  __int64 *v38; // rax
  __int64 v39; // r15
  __int64 v40; // rax
  unsigned int HeatRecord; // eax
  int v42; // eax
  int v43; // edx
  _QWORD *v44; // rcx
  int v45; // edx
  unsigned int v46; // r8d
  _OWORD *v47; // r15
  SIZE_T v48; // rax
  __int64 v49; // rcx
  __int128 v50; // xmm0
  __int64 *v51; // rcx
  __int128 v52; // xmm0
  int v53; // eax
  int *v54; // rdi
  void *v55; // r12
  unsigned int v56; // r15d
  enum _STORAGE_TIER_CLASS v57; // esi
  unsigned int v58; // ebx
  _QWORD *v59; // rcx
  unsigned __int16 *v60; // rax
  unsigned int v61; // eax
  __int64 v62; // r8
  int v63; // r9d
  unsigned int v64; // eax
  __int64 v65; // r10
  char v66; // [rsp+70h] [rbp-90h]
  unsigned __int8 v67[3]; // [rsp+71h] [rbp-8Fh] BYREF
  unsigned __int16 v68; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned __int8 v69[4]; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v70; // [rsp+7Ch] [rbp-84h]
  enum _STORAGE_TIER_CLASS v71; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v72; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v73; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int8 v74[4]; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned int v75; // [rsp+90h] [rbp-70h] BYREF
  __int64 v76; // [rsp+98h] [rbp-68h] BYREF
  void *Source1; // [rsp+A0h] [rbp-60h] BYREF
  char v78[8]; // [rsp+A8h] [rbp-58h] BYREF
  int v79; // [rsp+B0h] [rbp-50h]
  int *v80; // [rsp+B8h] [rbp-48h]
  __int64 v81; // [rsp+C0h] [rbp-40h] BYREF
  JET_TABLEID tableid; // [rsp+C8h] [rbp-38h]
  TieringMovementSession *v83; // [rsp+D0h] [rbp-30h]
  __int64 v84; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int16 *v85; // [rsp+E0h] [rbp-20h] BYREF
  int *v86; // [rsp+E8h] [rbp-18h] BYREF
  __int64 *v87; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int v88; // [rsp+F8h] [rbp-8h]
  int v89; // [rsp+FCh] [rbp-4h]
  _QWORD Buf1[4]; // [rsp+100h] [rbp+0h] BYREF
  __int128 Source2; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v92[4]; // [rsp+130h] [rbp+30h] BYREF
  int v93; // [rsp+138h] [rbp+38h]
  __int16 v94; // [rsp+13Ch] [rbp+3Ch]

  v76 = (__int64)a8;
  ThreadLocalStoragePointer = (__int64 *)NtCurrentTeb()->ThreadLocalStoragePointer;
  v71 = a2;
  v83 = a4;
  v11 = *ThreadLocalStoragePointer;
  v72 = a3;
  v87 = (__int64 *)a5;
  v85 = (unsigned __int16 *)a6;
  *(_QWORD *)(v11 + 8) = "TieringHeatSession::GetMovementsListForDiskOptimizer";
  v86 = a7;
  CHResultImp::CHResultImp((CHResultImp *)v78);
  *a7 = 0;
  v12 = 0;
  *a6 = 0;
  v13 = (__int64 *)*((_QWORD *)this + 5);
  v79 = 0;
  v14 = *v13;
  if ( *(_WORD *)(*v13 + 165)
    || WaitForSingleObject(*(HANDLE *)(v14 + 768), 0) != 258
    || WaitForSingleObject(*(HANDLE *)(v14 + 760), 0) != 258 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 252, &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids, v14 + 672);
    }
    v64 = ATL::AtlHresultFromWin32(87);
    v18 = v64;
    v79 = v64;
    if ( (_UNKNOWN **)v65 != &WPP_GLOBAL_Control && (*(_BYTE *)(v65 + 28) & 1) != 0 && *(_BYTE *)(v65 + 25) >= 2u )
      WPP_SF_Sd(
        *(_QWORD *)(v65 + 16),
        27,
        (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
        v64);
    goto LABEL_201;
  }
  v15 = *(_DWORD *)(**((_QWORD **)this + 5) + 184LL);
  if ( ((v15 - 1) & 0xFFFFFFFA) != 0 || v15 == 5 )
  {
    v61 = ATL::AtlHresultFromWin32(1003);
    v18 = v61;
    v79 = v61;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_DSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
        v63,
        *(_QWORD *)(v62 + 112),
        v61);
    }
    goto LABEL_201;
  }
  v16 = (JET_SESID *)v83;
  v75 = *(_DWORD *)a5;
  v88 = v75;
  v89 = *((_DWORD *)a5 + 1);
  v81 = *((_QWORD *)a5 + 1);
  Buf1[0] = v81;
  v84 = *((_QWORD *)a5 + 2);
  Buf1[1] = v84;
  v80 = (int *)*((_QWORD *)a5 + 3);
  Buf1[2] = v80;
  Buf1[3] = *((_QWORD *)a5 + 4);
  v17 = (JET_TABLEID *)((char *)v83 + 24);
  if ( a2 != StorageTierClassPerformance )
    v17 = (JET_TABLEID *)((char *)v83 + 16);
  tableid = *v17;
  if ( !memcmp_0(Buf1, &NullGuid, 0x10u) && !v80 )
  {
    if ( !TieringMovementSession::AreMovementTablesPresent((TieringMovementSession *)v16) )
    {
      v18 = -2147019873;
      v79 = -2147019873;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Zd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
          **((_DWORD **)this + 5) + 696,
          159);
      }
LABEL_201:
      CHResultImp::~CHResultImp((CHResultImp *)v78);
      return v18;
    }
    v19 = JetMove(v16[1], tableid, 0x80000000, 0);
    if ( ((v19 + 1603) & 0xFFFFFFFD) == 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Z(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          &WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
          **((_QWORD **)this + 5) + 696LL);
      }
      CHResultImp::~CHResultImp((CHResultImp *)v78);
      return 0;
    }
    v66 = 0;
    if ( v19 )
    {
      if ( v19 == -529 || v19 == -1092 || v19 == -1808 )
      {
        v18 = ATL::AtlHresultFromWin32(112);
      }
      else if ( v19 == -1011 )
      {
        v18 = -2147024882;
      }
      else
      {
        v20 = -v19;
        if ( v19 > 0 )
          LOWORD(v20) = v19;
        v18 = v19 & 0x8E5E0000 | (unsigned __int16)v20 | 0xE5E0000;
      }
      v79 = v18;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Zd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          33,
          (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
          **((_DWORD **)this + 5) + 696,
          v19);
      }
      goto LABEL_201;
    }
    v21 = WPP_GLOBAL_Control;
    goto LABEL_52;
  }
  v21 = WPP_GLOBAL_Control;
  v73 = 0;
  Source2 = 0;
  Source1 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentMovementRecord = TieringMovementSession::GetCurrentMovementRecord(
                              (TieringMovementSession *)v16,
                              tableid,
                              &v73,
                              (struct TE_FILE_ID_128 *)&Source2,
                              (__int64 *)&Source1);
    if ( CurrentMovementRecord )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_51;
      }
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
        CurrentMovementRecord);
    }
    else if ( v73 != v75 || memcmp_0(&Source2, Buf1, 0x10u) || Source1 != v80 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_51;
      }
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        &WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
    }
    v21 = WPP_GLOBAL_Control;
  }
LABEL_51:
  v66 = 1;
LABEL_52:
  v24 = (__int64 *)*((_QWORD *)this + 5);
  v25 = 10000;
  if ( v72 < 0x2710 )
    v25 = v72;
  v26 = *v24;
  v27 = *(_DWORD *)(*v24 + 208);
  if ( v27 < 0x3E8 )
    v27 = 1000;
  v28 = v27 + 1;
  if ( (unsigned int)v25 >= v28 )
    v25 = v28;
  v73 = v25;
  if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 1) != 0 && *((_BYTE *)v21 + 25) >= 5u )
    WPP_SF_IIS(v21[2], (_DWORD)v24, 1000, *(_QWORD *)(v26 + 200), *(_QWORD *)(v26 + 192), v24[14]);
  v29 = 40 * v25;
  v30 = CoTaskMemAlloc(v29);
  *(_QWORD *)v76 = v30;
  if ( !v30 )
  {
    v18 = -2147024882;
    v79 = -2147024882;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_DSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
        v73,
        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
        14);
    }
    goto LABEL_201;
  }
  v70 = 0;
  memset_0(v30, 0, v29);
  Source1 = *(void **)v76;
  while ( 1 )
  {
    if ( v66 )
    {
      v31 = JetMove(*((_QWORD *)v83 + 1), tableid, 1, 0);
      v34 = v31;
      if ( ((v31 + 1603) & 0xFFFFFFFD) == 0 )
      {
        v37 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Z(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            36,
            &WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
            **((_QWORD **)this + 5) + 696LL);
          v37 = WPP_GLOBAL_Control;
        }
        v12 = 0;
        v79 = 0;
LABEL_171:
        if ( v70 >= v73 )
        {
LABEL_172:
          v12 = 0;
          v79 = 0;
          *(_DWORD *)v85 = 1;
          goto LABEL_173;
        }
        goto LABEL_174;
      }
      if ( v31 )
      {
        if ( v31 == -529 || v31 == -1092 || v31 == -1808 )
        {
          v12 = ATL::AtlHresultFromWin32(112);
        }
        else if ( v31 == -1011 )
        {
          v12 = -2147024882;
        }
        else
        {
          v53 = -v31;
          if ( (int)v34 > 0 )
            LOWORD(v53) = v34;
          v12 = v34 & 0x8E5E0000 | (unsigned __int16)v53 | 0xE5E0000;
        }
        v79 = v12;
        v37 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Zd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            37,
            (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
            **((_DWORD **)this + 5) + 696,
            v34);
          v37 = WPP_GLOBAL_Control;
        }
        goto LABEL_171;
      }
    }
    else
    {
      v66 = 1;
    }
    v76 = 0;
    *(_QWORD *)v92 = 0;
    v93 = 0;
    v94 = 0;
    v67[0] = 0;
    v69[0] = 0;
    v74[0] = 0;
    v68 = 0;
    v72 = 0;
    Source2 = 0;
    v35 = TieringMovementSession::GetCurrentMovementRecord(v83, tableid, &v72, (struct TE_FILE_ID_128 *)&Source2, &v76);
    v33 = 0;
    v34 = v35;
    if ( v35 )
    {
      if ( v35 == -529 || v35 == -1092 || v35 == -1808 )
      {
        v12 = ATL::AtlHresultFromWin32(112);
      }
      else if ( v35 == -1011 )
      {
        v12 = -2147024882;
      }
      else
      {
        v36 = -v35;
        if ( v36 < 0 )
          LOWORD(v36) = v34;
        v12 = v34 & 0x8E5E0000 | (unsigned __int16)v36 | 0xE5E0000;
      }
      v79 = v12;
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Zd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          38,
          (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
          **((_DWORD **)this + 5) + 696,
          v34);
        goto LABEL_91;
      }
    }
    else
    {
      HeatRecord = TieringHeatSession::GetHeatRecord(
                     this,
                     (struct TE_FILE_ID_128 *)&Source2,
                     v76,
                     v67,
                     v69,
                     v74,
                     &v68,
                     v92);
      v34 = HeatRecord;
      if ( HeatRecord == -1017 )
      {
        v12 = -1906441223;
        v79 = -1906441223;
        v37 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_92;
        }
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          39,
          (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
          *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
          7);
LABEL_91:
        v37 = WPP_GLOBAL_Control;
LABEL_92:
        v33 = 0;
        goto LABEL_93;
      }
      v33 = 0;
      switch ( HeatRecord )
      {
        case 0u:
          if ( (v69[0] & 0xC) != 0 )
          {
            v37 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
            {
              goto LABEL_93;
            }
            v43 = 41;
            goto LABEL_126;
          }
          if ( !v68 )
          {
            v37 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
            {
              goto LABEL_93;
            }
            v43 = 42;
LABEL_126:
            WPP_SF_iiDS(
              v37[2],
              v43,
              (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
              DWORD2(Source2),
              Source2,
              v76,
              *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
            goto LABEL_91;
          }
          if ( v71 == StorageTierClassPerformance )
          {
            if ( (v67[0] & 0x90) == 0 )
            {
              v44 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                v45 = 43;
                goto LABEL_143;
              }
              goto LABEL_144;
            }
          }
          else if ( (v67[0] & 0xA0) == 0 )
          {
            v44 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              v45 = 44;
LABEL_143:
              WPP_SF_iiiDS(
                v44[2],
                v45,
                (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
                DWORD2(Source2),
                Source2,
                v76,
                v72,
                *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
              v33 = 0;
            }
LABEL_144:
            v46 = v70;
            v47 = Source1;
            if ( v70 )
            {
              v48 = RtlCompareMemory(Source1, &Source2, 0x10u);
              v32 = v76;
              if ( v48 == 16 )
              {
                v34 = *((_QWORD *)v47 + 3);
                if ( v34 + *((_QWORD *)v47 + 2) == v76 )
                {
                  *((_QWORD *)v47 + 3) = v34 + 0x100000;
                  *((_WORD *)v47 + 16) |= 0x80u;
                  v49 = **((_QWORD **)this + 5);
                  if ( v71 == StorageTierClassPerformance )
                    *(_QWORD *)(v49 + 264) += v68;
                  else
                    *(_QWORD *)(v49 + 272) += v68;
                  v33 = 0;
                  goto LABEL_157;
                }
              }
              v46 = v70;
              v47 = (_OWORD *)((char *)v47 + 40);
              Source1 = v47;
              v33 = 0;
            }
            else
            {
              v32 = v76;
            }
            v50 = Source2;
            v34 = v46 + 1;
            *((_QWORD *)v47 + 2) = v32;
            v70 = v34;
            *v47 = v50;
            *((_QWORD *)v47 + 3) = 0x100000;
            *((_WORD *)v47 + 16) = 128;
            if ( v71 == StorageTierClassPerformance )
            {
              *((_DWORD *)v47 + 9) = 2;
              *(_QWORD *)(**((_QWORD **)this + 5) + 264LL) += v68;
            }
            else
            {
              *((_DWORD *)v47 + 9) = 1;
              *(_QWORD *)(**((_QWORD **)this + 5) + 272LL) += v68;
            }
            *v86 = v34;
          }
LABEL_157:
          v51 = v87;
          v52 = Source2;
          *(_DWORD *)v87 = v72;
          v51[3] = v76;
          *(_OWORD *)(v51 + 1) = v52;
          *((_DWORD *)v51 + 8) = 0;
          v37 = WPP_GLOBAL_Control;
          goto LABEL_93;
        case 0xFFFFFDEF:
        case 0xFFFFFBBC:
        case 0xFFFFF8F0:
          v12 = ATL::AtlHresultFromWin32(112);
          break;
        case 0xFFFFFC0D:
          v12 = -2147024882;
          break;
        default:
          v42 = -HeatRecord;
          if ( v42 < 0 )
            LOWORD(v42) = v34;
          v12 = v34 & 0x8E5E0000 | (unsigned __int16)v42 | 0xE5E0000;
          break;
      }
      v79 = v12;
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          40,
          (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
          *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
          v34);
        goto LABEL_91;
      }
    }
LABEL_93:
    if ( v70 >= v73 )
      goto LABEL_172;
    v38 = (__int64 *)*((_QWORD *)this + 5);
    v39 = *v38;
    if ( *(_DWORD *)(*v38 + 184) != 2 )
      goto LABEL_174;
    if ( *(_BYTE *)(v39 + 165) != (_BYTE)v33 || *(_BYTE *)(v39 + 166) != (_BYTE)v33 )
      goto LABEL_179;
    if ( WaitForSingleObject(*(HANDLE *)(v39 + 768), 0) != 258 || WaitForSingleObject(*(HANDLE *)(v39 + 760), 0) != 258 )
      break;
    v40 = *((_QWORD *)this + 5);
    if ( *(_BYTE *)(v40 + 77) && *(_BYTE *)(v40 + 76) )
      goto LABEL_173;
  }
  v37 = WPP_GLOBAL_Control;
LABEL_179:
  if ( v37 == &WPP_GLOBAL_Control )
    goto LABEL_183;
  if ( (*((_BYTE *)v37 + 28) & 1) != 0 && *((_BYTE *)v37 + 25) >= 5u )
  {
    WPP_SF_Z(v37[2], 252, &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids, v39 + 672);
LABEL_173:
    v37 = WPP_GLOBAL_Control;
  }
LABEL_174:
  if ( v37 == &WPP_GLOBAL_Control || (*((_BYTE *)v37 + 28) & 1) == 0 )
  {
LABEL_183:
    v55 = (void *)v81;
    v56 = v75;
    v57 = v71;
    v54 = v80;
    v58 = v70;
    goto LABEL_184;
  }
  v54 = v80;
  v55 = (void *)v81;
  v56 = v75;
  v57 = v71;
  v58 = v70;
  if ( *((_BYTE *)v37 + 25) >= 4u )
    WPP_SF_DLLiiiS(v37[2], v32, v34, v70, v71, v75, v84, v81, (char)v80, *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
LABEL_184:
  if ( (unsigned int)dword_14004C098 > 4
    && (qword_14004C0A8 & 0x200000000000LL) != 0
    && (qword_14004C0B0 & 0x200000000000LL) == qword_14004C0B0 )
  {
    v59 = (_QWORD *)*((_QWORD *)this + 5);
    v87 = (__int64 *)v59[14];
    v86 = v54;
    Source1 = v55;
    v73 = v56;
    v72 = *(_DWORD *)v85;
    v75 = v58;
    v71 = v57;
    v60 = (unsigned __int16 *)(*v59 + 696LL);
    v81 = 0x1000000;
    v85 = v60;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (__int64)v59,
      (__int64)byte_14004638B,
      v34,
      v33,
      (__int64)&v81,
      &v85,
      (__int64)&v71,
      (__int64)&v75,
      (__int64)&v72,
      (__int64)&v73,
      (__int64)&v84,
      (__int64)&Source1,
      (__int64)&v86,
      &v87);
  }
  CHResultImp::~CHResultImp((CHResultImp *)v78);
  return v12;
}

```

## disassembly

```asm
0x140021a28  mov     [rsp-8+arg_8], rbx
0x140021a2d  push    rbp
0x140021a2e  push    rsi
0x140021a2f  push    rdi
0x140021a30  push    r12
0x140021a32  push    r13
0x140021a34  push    r14
0x140021a36  push    r15
0x140021a38  lea     rbp, [rsp-50h]
0x140021a3d  sub     rsp, 150h
0x140021a44  mov     rax, cs:__security_cookie
0x140021a4b  xor     rax, rsp
0x140021a4e  mov     [rbp+80h+var_40], rax
0x140021a52  mov     rax, [rbp+80h+arg_38]
0x140021a59  mov     r13, rcx
0x140021a5c  mov     rdi, [rbp+80h+arg_20]
0x140021a63  mov     esi, edx
0x140021a65  mov     r15, [rbp+80h+arg_28]
0x140021a6c  mov     rbx, [rbp+80h+arg_30]
0x140021a73  mov     [rbp+80h+var_E8], rax
0x140021a77  mov     rax, gs:58h
0x140021a80  mov     [rbp+80h+var_100], edx
0x140021a83  mov     edx, 8
0x140021a88  mov     [rbp+80h+var_B0], r9
0x140021a8c  mov     rcx, [rax]
0x140021a8f  lea     rax, aTieringheatses_10; "TieringHeatSession::GetMovementsListFor"...
0x140021a96  mov     [rbp+80h+var_FC], r8d
0x140021a9a  mov     [rbp+80h+var_90], rdi
0x140021a9e  mov     [rbp+80h+var_A0], r15
0x140021aa2  mov     [rdx+rcx], rax
0x140021aa6  lea     rcx, [rbp+80h+var_D8]; this
0x140021aaa  mov     [rbp+80h+var_98], rbx
0x140021aae  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x140021ab3  xor     ecx, ecx
0x140021ab5  mov     [rbx], ecx
0x140021ab7  mov     r14d, ecx
0x140021aba  mov     [r15], ecx
0x140021abd  mov     rax, [r13+28h]
0x140021ac1  mov     [rbp+80h+var_D0], ecx
0x140021ac4  mov     rbx, [rax]
0x140021ac7  cmp     [rbx+0A5h], cl
0x140021acd  jnz     loc_1400227B1
0x140021ad3  cmp     [rbx+0A6h], cl
0x140021ad9  jnz     loc_1400227B1
0x140021adf  mov     rcx, [rbx+300h]; hHandle
0x140021ae6  xor     edx, edx; dwMilliseconds
0x140021ae8  call    cs:__imp_WaitForSingleObject
0x140021aee  mov     r15d, 102h
0x140021af4  cmp     eax, r15d
0x140021af7  jnz     loc_1400227B1
0x140021afd  mov     rcx, [rbx+2F8h]; hHandle
0x140021b04  xor     edx, edx; dwMilliseconds
0x140021b06  call    cs:__imp_WaitForSingleObject
0x140021b0c  cmp     eax, r15d
0x140021b0f  jnz     loc_1400227B1
0x140021b15  mov     r8, [r13+28h]
0x140021b19  mov     rax, [r8]
0x140021b1c  mov     r9d, [rax+0B8h]
0x140021b23  lea     eax, [r9-1]
0x140021b27  test    eax, 0FFFFFFFAh
0x140021b2c  jnz     loc_140022749
0x140021b32  cmp     r9d, 5
0x140021b36  jz      loc_140022749
0x140021b3c  mov     eax, [rdi]
0x140021b3e  mov     r12d, 2
0x140021b44  mov     rbx, [rbp+80h+var_B0]
0x140021b48  mov     [rbp+80h+var_F0], eax
0x140021b4b  mov     [rbp+80h+var_88], eax
0x140021b4e  mov     eax, [rdi+4]
0x140021b51  mov     [rbp+80h+var_84], eax
0x140021b54  mov     rax, [rdi+8]
0x140021b58  mov     [rbp+80h+var_C0], rax
0x140021b5c  mov     [rbp+80h+Buf1], rax
0x140021b60  mov     rax, [rdi+10h]
0x140021b64  mov     [rbp+80h+var_A8], rax
0x140021b68  mov     [rbp+80h+var_78], rax
0x140021b6c  mov     rax, [rdi+18h]
0x140021b70  mov     [rbp+80h+var_C8], rax
0x140021b74  mov     [rbp+80h+var_70], rax
0x140021b78  mov     rax, [rdi+20h]
0x140021b7c  mov     [rbp+80h+var_68], rax
0x140021b80  lea     rax, [rbx+18h]
0x140021b84  cmp     esi, r12d
0x140021b87  jz      short loc_140021B8D
0x140021b89  lea     rax, [rbx+10h]
0x140021b8d  mov     rax, [rax]
0x140021b90  lea     rdx, ?NullGuid@@3U_GUID@@A; Buf2
0x140021b97  mov     r8d, 10h; Size
0x140021b9d  mov     [rbp+80h+tableid], rax
0x140021ba1  lea     rcx, [rbp+80h+Buf1]; Buf1
0x140021ba5  call    memcmp_0
0x140021baa  xor     r10d, r10d
0x140021bad  lea     rsi, WPP_GLOBAL_Control
0x140021bb4  lea     r15, WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids
0x140021bbb  mov     edi, 1
0x140021bc0  test    eax, eax
0x140021bc2  jnz     loc_140021D63
0x140021bc8  cmp     [rbp+80h+var_C8], r10
0x140021bcc  jnz     loc_140021D63
0x140021bd2  mov     rcx, rbx; this
0x140021bd5  call    ?AreMovementTablesPresent@TieringMovementSession@@QEAA_NXZ; TieringMovementSession::AreMovementTablesPresent(void)
0x140021bda  test    al, al
0x140021bdc  jnz     short loc_140021C30
0x140021bde  mov     ebx, 8007139Fh
0x140021be3  mov     [rbp+80h+var_D0], ebx
0x140021be6  mov     rcx, cs:WPP_GLOBAL_Control
0x140021bed  cmp     rcx, rsi
0x140021bf0  jz      loc_140022840
0x140021bf6  test    [rcx+1Ch], dil
0x140021bfa  jz      loc_140022840
0x140021c00  cmp     [rcx+19h], r12b
0x140021c04  jb      loc_140022840
0x140021c0a  mov     rax, [r13+28h]
0x140021c0e  lea     edx, [rdi+1Eh]
0x140021c11  mov     rcx, [rcx+10h]
0x140021c15  mov     r8, r15
0x140021c18  mov     dword ptr [rsp+180h+var_160], ebx
0x140021c1c  mov     r9, [rax]
0x140021c1f  add     r9, 2B8h
0x140021c26  call    WPP_SF_Zd
0x140021c2b  jmp     loc_140022840
0x140021c30  mov     rdx, [rbp+80h+tableid]; tableid
0x140021c34  xor     r9d, r9d; grbit
0x140021c37  mov     rcx, [rbx+8]; sesid
0x140021c3b  mov     r8d, 80000000h; cRow
0x140021c41  call    cs:__imp_JetMove
0x140021c47  mov     r8d, eax
0x140021c4a  add     eax, 643h
0x140021c4f  test    eax, 0FFFFFFFDh
0x140021c54  jz      loc_140021D1C
0x140021c5a  xor     r10d, r10d
0x140021c5d  mov     [rsp+180h+var_110], r10b
0x140021c62  test    r8d, r8d
0x140021c65  jz      loc_140021D10
0x140021c6b  cmp     r8d, 0FFFFFDEFh
0x140021c72  jz      short loc_140021CB4
0x140021c74  cmp     r8d, 0FFFFFBBCh
0x140021c7b  jz      short loc_140021CB4
0x140021c7d  cmp     r8d, 0FFFFF8F0h
0x140021c84  jz      short loc_140021CB4
0x140021c86  cmp     r8d, 0FFFFFC0Dh
0x140021c8d  jnz     short loc_140021C96
0x140021c8f  mov     ebx, 8007000Eh
0x140021c94  jmp     short loc_140021CC0
0x140021c96  mov     eax, r8d
0x140021c99  neg     eax
0x140021c9b  cmovs   eax, r8d
0x140021c9f  movzx   ebx, ax
0x140021ca2  mov     eax, r8d
0x140021ca5  and     eax, 8E5E0000h
0x140021caa  or      ebx, eax
0x140021cac  or      ebx, 0E5E0000h
0x140021cb2  jmp     short loc_140021CC0
0x140021cb4  mov     ecx, 70h ; 'p'; unsigned int
0x140021cb9  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140021cbe  mov     ebx, eax
0x140021cc0  mov     [rbp+80h+var_D0], ebx
0x140021cc3  mov     rcx, cs:WPP_GLOBAL_Control
0x140021cca  cmp     rcx, rsi
0x140021ccd  jz      loc_140022840
0x140021cd3  test    [rcx+1Ch], dil
0x140021cd7  jz      loc_140022840
0x140021cdd  cmp     [rcx+19h], r12b
0x140021ce1  jb      loc_140022840
0x140021ce7  mov     rax, [r13+28h]
0x140021ceb  mov     edx, 21h ; '!'
0x140021cf0  mov     rcx, [rcx+10h]
0x140021cf4  mov     dword ptr [rsp+180h+var_160], r8d
0x140021cf9  mov     r8, r15
0x140021cfc  mov     r9, [rax]
0x140021cff  add     r9, 2B8h
0x140021d06  call    WPP_SF_Zd
0x140021d0b  jmp     loc_140022840
0x140021d10  mov     rcx, cs:WPP_GLOBAL_Control
0x140021d17  jmp     loc_140021E57
0x140021d1c  mov     rcx, cs:WPP_GLOBAL_Control
0x140021d23  cmp     rcx, rsi
0x140021d26  jz      short loc_140021D53
0x140021d28  test    [rcx+1Ch], dil
0x140021d2c  jz      short loc_140021D53
0x140021d2e  cmp     byte ptr [rcx+19h], 4
0x140021d32  jb      short loc_140021D53
0x140021d34  mov     rax, [r13+28h]
0x140021d38  mov     edx, 20h ; ' '
0x140021d3d  mov     rcx, [rcx+10h]
0x140021d41  mov     r8, r15
0x140021d44  mov     r9, [rax]
0x140021d47  add     r9, 2B8h
0x140021d4e  call    WPP_SF_Z
0x140021d53  lea     rcx, [rbp+80h+var_D8]; this
0x140021d57  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x140021d5c  xor     eax, eax
0x140021d5e  jmp     loc_14002284B
0x140021d63  mov     rcx, cs:WPP_GLOBAL_Control
0x140021d6a  xorps   xmm0, xmm0
0x140021d6d  mov     [rbp+80h+var_F8], r10d
0x140021d71  movups  [rbp+80h+Source2], xmm0
0x140021d75  mov     [rbp+80h+Source1], r10
0x140021d79  test    [rcx+1Ch], dil
0x140021d7d  jz      loc_140021E52
0x140021d83  cmp     byte ptr [rcx+19h], 4
0x140021d87  jb      loc_140021E52
0x140021d8d  mov     rdx, [rbp+80h+tableid]; unsigned __int64
0x140021d91  lea     rax, [rbp+80h+Source1]
0x140021d95  lea     r9, [rbp+80h+Source2]; struct TE_FILE_ID_128 *
0x140021d99  mov     [rsp+180h+var_160], rax; __int64 *
0x140021d9e  lea     r8, [rbp+80h+var_F8]; unsigned int *
0x140021da2  mov     rcx, rbx; this
0x140021da5  call    ?GetCurrentMovementRecord@TieringMovementSession@@QEAAJ_KPEAKPEAUTE_FILE_ID_128@@PEA_J@Z; TieringMovementSession::GetCurrentMovementRecord(unsigned __int64,ulong *,TE_FILE_ID_128 *,__int64 *)
0x140021daa  test    eax, eax
0x140021dac  jz      short loc_140021DF1
0x140021dae  mov     rcx, cs:WPP_GLOBAL_Control
0x140021db5  cmp     rcx, rsi
0x140021db8  jz      loc_140021E52
0x140021dbe  test    [rcx+1Ch], dil
0x140021dc2  jz      loc_140021E52
0x140021dc8  cmp     [rcx+19h], r12b
0x140021dcc  jb      loc_140021E52
0x140021dd2  mov     r9, [r13+28h]
0x140021dd6  mov     edx, 1Dh
0x140021ddb  mov     rcx, [rcx+10h]
0x140021ddf  mov     r8, r15
0x140021de2  mov     dword ptr [rsp+180h+var_160], eax
0x140021de6  mov     r9, [r9+70h]
0x140021dea  call    WPP_SF_Sd
0x140021def  jmp     short loc_140021E4B
0x140021df1  mov     eax, [rbp+80h+var_F0]
0x140021df4  cmp     [rbp+80h+var_F8], eax
0x140021df7  jnz     short loc_140021E1A
0x140021df9  mov     r8d, 10h; Size
0x140021dff  lea     rdx, [rbp+80h+Buf1]; Buf2
0x140021e03  lea     rcx, [rbp+80h+Source2]; Buf1
0x140021e07  call    memcmp_0
0x140021e0c  test    eax, eax
0x140021e0e  jnz     short loc_140021E1A
0x140021e10  mov     rax, [rbp+80h+var_C8]
0x140021e14  cmp     [rbp+80h+Source1], rax
0x140021e18  jz      short loc_140021E4B
0x140021e1a  mov     rcx, cs:WPP_GLOBAL_Control
0x140021e21  cmp     rcx, rsi
0x140021e24  jz      short loc_140021E52
0x140021e26  test    [rcx+1Ch], dil
0x140021e2a  jz      short loc_140021E52
0x140021e2c  cmp     byte ptr [rcx+19h], 4
0x140021e30  jb      short loc_140021E52
0x140021e32  mov     r9, [r13+28h]
0x140021e36  mov     edx, 1Eh
0x140021e3b  mov     rcx, [rcx+10h]
0x140021e3f  mov     r8, r15
0x140021e42  mov     r9, [r9+70h]
0x140021e46  call    WPP_SF_S
0x140021e4b  mov     rcx, cs:WPP_GLOBAL_Control
0x140021e52  mov     [rsp+180h+var_110], dil
0x140021e57  mov     rdx, [r13+28h]
0x140021e5b  mov     ebx, 2710h
0x140021e60  cmp     [rbp+80h+var_FC], ebx
0x140021e63  mov     r8d, 3E8h
0x140021e69  cmovb   ebx, [rbp+80h+var_FC]
0x140021e6d  mov     r9, [rdx]
0x140021e70  mov     eax, [r9+0D0h]
0x140021e77  cmp     eax, r8d
0x140021e7a  cmovb   eax, r8d
0x140021e7e  inc     eax
0x140021e80  cmp     ebx, eax
0x140021e82  cmovnb  ebx, eax
0x140021e85  mov     [rbp+80h+var_F8], ebx
0x140021e88  cmp     rcx, rsi
0x140021e8b  jz      short loc_140021EBE
0x140021e8d  test    [rcx+1Ch], dil
0x140021e91  jz      short loc_140021EBE
0x140021e93  cmp     byte ptr [rcx+19h], 5
0x140021e97  jb      short loc_140021EBE
0x140021e99  mov     rax, [rdx+70h]
0x140021e9d  mov     rcx, [rcx+10h]
0x140021ea1  mov     [rsp+180h+var_158], rax
0x140021ea6  mov     rax, [r9+0C0h]
0x140021ead  mov     r9, [r9+0C8h]
0x140021eb4  mov     [rsp+180h+var_160], rax
0x140021eb9  call    WPP_SF_IIS
0x140021ebe  lea     rbx, [rbx+rbx*4]
0x140021ec2  shl     rbx, 3
0x140021ec6  mov     rcx, rbx; cb
0x140021ec9  call    cs:__imp_CoTaskMemAlloc
0x140021ecf  mov     rcx, [rbp+80h+var_E8]
0x140021ed3  mov     [rcx], rax
0x140021ed6  xor     ecx, ecx
0x140021ed8  test    rax, rax
0x140021edb  jnz     short loc_140021F26
0x140021edd  mov     ebx, 8007000Eh
0x140021ee2  mov     [rbp+80h+var_D0], ebx
0x140021ee5  mov     rcx, cs:WPP_GLOBAL_Control
0x140021eec  cmp     rcx, rsi
0x140021eef  jz      loc_140022840
0x140021ef5  test    [rcx+1Ch], dil
0x140021ef9  jz      loc_140022840
0x140021eff  cmp     [rcx+19h], r12b
0x140021f03  jb      loc_140022840
0x140021f09  mov     rax, [r13+28h]
0x140021f0d  mov     edx, 23h ; '#'
0x140021f12  mov     r9d, [rbp+80h+var_F8]
  ... truncated ...
```
