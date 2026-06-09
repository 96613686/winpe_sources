# TieringHeatSession::SetCurrentLocation(TE_FILE_ID_128 const *,__int64,uchar,ushort)

- ea: `0x140024b60`
- end: `0x140025869`
- name: `?SetCurrentLocation@TieringHeatSession@@QEAAJPEBUTE_FILE_ID_128@@_JEG@Z`
- size: `3337`
- prototype: `__int64 __fastcall(TieringHeatSession *this, const struct TE_FILE_ID_128 *, __int64, unsigned __int8, unsigned __int16)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14003eba8`

## callees

- `0x140002db0`
- `0x140004a68`
- `0x1400185a0`
- `0x140021018`
- `0x140024b60`
- `0x140025f78`
- `0x1400260cc`
- `0x140026290`
- `0x140026434`
- `0x140026514`
- `0x14002660c`
- `0x14002866c`
- `0x140029dec`
- `0x14003fbb0`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x140024bb9`
- `ntdll!RtlCompareMemory` at `0x140025334`
- `ntdll!RtlCompareMemory` at `0x140024bb9`
- `ntdll!RtlCompareMemory` at `0x140025334`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14002505a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14002505a`
- `ESENT!JetPrepareUpdate` at `0x140024dc6`
- `ESENT!JetPrepareUpdate` at `0x140024de0`
- `ESENT!JetPrepareUpdate` at `0x140024df1`
- `ESENT!JetPrepareUpdate` at `0x140024f76`
- `ESENT!JetPrepareUpdate` at `0x140025043`
- `ESENT!JetPrepareUpdate` at `0x14002512d`
- `ESENT!JetPrepareUpdate` at `0x140025147`
- `ESENT!JetPrepareUpdate` at `0x14002515b`
- `ESENT!JetPrepareUpdate` at `0x1400256d2`
- `ESENT!JetPrepareUpdate` at `0x140025841`
- `ESENT!JetPrepareUpdate` at `0x140024dc6`
- `ESENT!JetPrepareUpdate` at `0x140024de0`
- `ESENT!JetPrepareUpdate` at `0x140024df1`
- `ESENT!JetPrepareUpdate` at `0x140024f76`
- `ESENT!JetPrepareUpdate` at `0x140025043`
- `ESENT!JetPrepareUpdate` at `0x14002512d`
- `ESENT!JetPrepareUpdate` at `0x140025147`
- `ESENT!JetPrepareUpdate` at `0x14002515b`
- `ESENT!JetPrepareUpdate` at `0x1400256d2`
- `ESENT!JetPrepareUpdate` at `0x140025841`
- `ESENT!JetUpdate` at `0x140024f98`
- `ESENT!JetUpdate` at `0x14002553b`
- `ESENT!JetUpdate` at `0x140024f98`
- `ESENT!JetUpdate` at `0x14002553b`
- `ESENT!JetMakeKey` at `0x140024c39`
- `ESENT!JetMakeKey` at `0x140024cd3`
- `ESENT!JetMakeKey` at `0x140024c39`
- `ESENT!JetMakeKey` at `0x140024cd3`
- `ESENT!JetSeek` at `0x140024d95`
- `ESENT!JetSeek` at `0x140024d95`

## pseudocode

```c
__int64 __fastcall TieringHeatSession::SetCurrentLocation(
        TieringHeatSession *this,
        const struct TE_FILE_ID_128 *a2,
        __int64 a3,
        unsigned __int8 a4,
        unsigned __int16 a5)
{
  unsigned __int8 v6; // bl
  unsigned int v8; // edi
  JET_ERR Key; // eax
  JET_ERR v11; // edi
  unsigned int v12; // ebx
  int v13; // eax
  _QWORD *v14; // rcx
  int v15; // edx
  JET_ERR v16; // eax
  int v17; // eax
  JET_ERR v18; // eax
  JET_TABLEID v19; // rdx
  JET_SESID v20; // rcx
  int v21; // eax
  unsigned __int16 *v22; // rdi
  __int64 i; // rcx
  JET_ERR v24; // eax
  int v25; // eax
  JET_ERR v26; // eax
  JET_ERR v27; // edi
  int v28; // eax
  int v29; // eax
  int v30; // eax
  JET_ERR CurrentHeatRecord; // eax
  int v32; // eax
  char v33; // r13
  char v34; // r12
  unsigned __int16 v35; // r15
  int v36; // r8d
  char v37; // r8
  unsigned __int16 v38; // di
  unsigned __int8 v39; // cl
  _QWORD *v40; // r10
  char v41; // r9
  char v42; // dl
  unsigned __int8 v43; // dl
  JET_ERR v44; // eax
  int v45; // eax
  JET_ERR v46; // eax
  int v47; // edx
  int v48; // r8d
  int v49; // eax
  unsigned __int8 v50; // [rsp+70h] [rbp-31h] BYREF
  unsigned __int8 v51; // [rsp+71h] [rbp-30h] BYREF
  unsigned __int8 v52; // [rsp+72h] [rbp-2Fh]
  unsigned __int16 v53[2]; // [rsp+74h] [rbp-2Dh] BYREF
  __int64 pvData; // [rsp+78h] [rbp-29h] BYREF
  __int64 v55; // [rsp+80h] [rbp-21h] BYREF
  __int128 Source1; // [rsp+88h] [rbp-19h] BYREF
  unsigned __int16 v57[4]; // [rsp+98h] [rbp-9h] BYREF
  int v58; // [rsp+A0h] [rbp-1h]
  __int16 v59; // [rsp+A4h] [rbp+3h]

  pvData = a3;
  v53[0] = 0;
  v6 = a4;
  *(_QWORD *)v57 = 0;
  v52 = a4;
  v50 = a4;
  v58 = 0;
  v59 = 0;
  if ( RtlCompareMemory(a2, &NullGuid, 0x10u) == 16 )
  {
    v8 = ATL::AtlHresultFromWin32(123);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids, v8);
    }
    return v8;
  }
  while ( 1 )
  {
    Key = JetMakeKey(*((_QWORD *)this + 1), *((_QWORD *)this + 3), a2, 0x10u, 1u);
    v11 = Key;
    if ( Key )
    {
      if ( Key == -529 || Key == -1092 || Key == -1808 )
      {
        v12 = ATL::AtlHresultFromWin32(112);
      }
      else if ( Key == -1011 )
      {
        v12 = -2147024882;
      }
      else
      {
        v13 = -Key;
        if ( v13 < 0 )
          LOWORD(v13) = v11;
        v12 = v11 & 0x8E5E0000 | (unsigned __int16)v13 | 0xE5E0000;
      }
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_36;
      }
      v15 = 47;
      goto LABEL_35;
    }
    v16 = JetMakeKey(*((_QWORD *)this + 1), *((_QWORD *)this + 3), &pvData, 8u, 0);
    v11 = v16;
    if ( v16 )
    {
      if ( v16 == -529 || v16 == -1092 || v16 == -1808 )
      {
        v12 = ATL::AtlHresultFromWin32(112);
      }
      else if ( v16 == -1011 )
      {
        v12 = -2147024882;
      }
      else
      {
        v17 = -v16;
        if ( v17 < 0 )
          LOWORD(v17) = v11;
        v12 = v11 & 0x8E5E0000 | (unsigned __int16)v17 | 0xE5E0000;
      }
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_36;
      }
      v15 = 48;
      goto LABEL_35;
    }
    v18 = JetSeek(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 1u);
    v11 = v18;
    if ( (v6 & 0x20) != 0 || v18 != -1601 && v18 != 1039 )
      break;
    v19 = *((_QWORD *)this + 3);
    v20 = *((_QWORD *)this + 1);
    v50 = v6;
    v11 = JetPrepareUpdate(v20, v19, 0);
    if ( v11 == -1607 )
    {
      JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 3u);
      v11 = JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 0);
    }
    if ( v11 )
    {
      if ( v11 == -529 || v11 == -1092 || v11 == -1808 )
      {
        v12 = ATL::AtlHresultFromWin32(112);
      }
      else if ( v11 == -1011 )
      {
        v12 = -2147024882;
      }
      else
      {
        v21 = -v11;
        if ( v11 > 0 )
          LOWORD(v21) = v11;
        v12 = v11 & 0x8E5E0000 | (unsigned __int16)v21 | 0xE5E0000;
      }
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_36;
      }
      v15 = 49;
LABEL_35:
      WPP_SF_iiSd(
        v14[2],
        v15,
        (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
        *((_QWORD *)a2 + 1),
        *(_QWORD *)a2,
        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
        v11);
      goto LABEL_36;
    }
    v22 = &v57[1];
    for ( i = 6; i; --i )
      *v22++ = -1;
    v57[0] = 0;
    v24 = TieringHeatSession::SetCurrentHeatRecord(
            this,
            a2,
            &pvData,
            &v50,
            0,
            (unsigned __int8 *)(**((_QWORD **)this + 5) + 328LL),
            &a5,
            v57);
    v11 = v24;
    if ( v24 )
    {
      if ( v24 == -529 || v24 == -1092 || v24 == -1808 )
      {
        v12 = ATL::AtlHresultFromWin32(112);
      }
      else if ( v24 == -1011 )
      {
        v12 = -2147024882;
      }
      else
      {
        v25 = -v24;
        if ( v25 < 0 )
          LOWORD(v25) = v11;
        v12 = v11 & 0x8E5E0000 | (unsigned __int16)v25 | 0xE5E0000;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_iiSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          50,
          (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
          *((_QWORD *)a2 + 1),
          *(_QWORD *)a2,
          *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
          v11);
      }
LABEL_74:
      JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 3u);
      goto LABEL_36;
    }
    v26 = JetUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 0, 0, 0);
    v27 = v26;
    switch ( v26 )
    {
      case 0:
        v12 = 0;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_iiiDDZ(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            53,
            (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
            *((_QWORD *)a2 + 1),
            *(_QWORD *)a2,
            pvData,
            v52,
            v50,
            **((_QWORD **)this + 5) + 672LL);
        }
        return v12;
      case -529:
      case -1092:
      case -1808:
        v12 = ATL::AtlHresultFromWin32(112);
        break;
      case -1011:
        v12 = -2147024882;
        break;
      default:
        v28 = -v26;
        if ( v28 < 0 )
          LOWORD(v28) = v27;
        v12 = v27 & 0x8E5E0000 | (unsigned __int16)v28 | 0xE5E0000;
        break;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_iiSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52,
        (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
        *((_QWORD *)a2 + 1),
        *(_QWORD *)a2,
        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
        v27);
    }
LABEL_89:
    JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 3u);
    if ( v27 != -1102 )
      return v12;
    Sleep(0x64u);
LABEL_37:
    v6 = v52;
  }
  if ( v18 )
  {
    if ( v18 == -529 || v18 == -1092 || v18 == -1808 )
    {
      v12 = ATL::AtlHresultFromWin32(112);
    }
    else if ( v18 == -1011 )
    {
      v12 = -2147024882;
    }
    else
    {
      v29 = -v18;
      if ( v29 < 0 )
        LOWORD(v29) = v11;
      v12 = v11 & 0x8E5E0000 | (unsigned __int16)v29 | 0xE5E0000;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_iiiZL(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        54,
        (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
        *((_QWORD *)a2 + 1),
        *(_QWORD *)a2,
        pvData,
        **((_QWORD **)this + 5) + 672LL,
        v11);
    }
    goto LABEL_36;
  }
  v11 = JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 2u);
  if ( v11 == -1607 )
  {
    JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 3u);
    v11 = JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 2u);
  }
  if ( v11 )
  {
    if ( v11 == -529 || v11 == -1092 || v11 == -1808 )
    {
      v12 = ATL::AtlHresultFromWin32(112);
    }
    else if ( v11 == -1011 )
    {
      v12 = -2147024882;
    }
    else
    {
      v30 = -v11;
      if ( v11 > 0 )
        LOWORD(v30) = v11;
      v12 = v11 & 0x8E5E0000 | (unsigned __int16)v30 | 0xE5E0000;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_iiZd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        55,
        (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
        *((_QWORD *)a2 + 1),
        *(_QWORD *)a2,
        **((_QWORD **)this + 5) + 672LL,
        v11);
    }
LABEL_36:
    if ( v11 != -1102 )
      return v12;
    goto LABEL_37;
  }
  v55 = 0;
  v51 = 0;
  Source1 = 0;
  CurrentHeatRecord = TieringHeatSession::GetCurrentHeatRecord(
                        this,
                        1u,
                        (struct TE_FILE_ID_128 *)&Source1,
                        &v55,
                        &v50,
                        &v51,
                        0,
                        v53,
                        0);
  v11 = CurrentHeatRecord;
  if ( CurrentHeatRecord )
  {
    if ( CurrentHeatRecord == -529 || CurrentHeatRecord == -1092 || CurrentHeatRecord == -1808 )
    {
      v12 = ATL::AtlHresultFromWin32(112);
    }
    else if ( CurrentHeatRecord == -1011 )
    {
      v12 = -2147024882;
    }
    else
    {
      v32 = -CurrentHeatRecord;
      if ( v32 < 0 )
        LOWORD(v32) = v11;
      v12 = v11 & 0x8E5E0000 | (unsigned __int16)v32 | 0xE5E0000;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_iiZd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        56,
        (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
        *((_QWORD *)a2 + 1),
        *(_QWORD *)a2,
        **((_QWORD **)this + 5) + 672LL,
        v11);
    }
    goto LABEL_74;
  }
  v33 = v50;
  v34 = v51;
  v35 = v53[0];
  if ( RtlCompareMemory(&Source1, a2, 0x10u) != 16 )
  {
    v12 = -2147220986;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_iiiiZL(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        *(_QWORD *)a2,
        v36,
        *((_QWORD *)a2 + 1),
        *(_QWORD *)a2,
        SBYTE8(Source1),
        Source1,
        **((_QWORD **)this + 5) + 672LL,
        0);
    }
    goto LABEL_201;
  }
  v37 = pvData;
  if ( v55 != pvData )
  {
    v12 = -2147220986;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_iiiiZd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        **((_DWORD **)this + 5) + 672,
        pvData,
        *((_QWORD *)a2 + 1),
        *(_QWORD *)a2,
        pvData,
        v55,
        **((_QWORD **)this + 5) + 672LL);
    }
LABEL_201:
    JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 3u);
    return v12;
  }
  v38 = v53[0];
  v39 = v50;
  if ( v53[0] == a5 )
  {
    v42 = v51;
    v40 = WPP_GLOBAL_Control;
    v39 = v6 | v50 & 0xF;
    v41 = v52;
LABEL_146:
    v50 = v39;
    goto LABEL_147;
  }
  if ( v50 != v6 )
  {
    v40 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_iiiDZ(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
        *((_QWORD *)a2 + 1),
        *(_QWORD *)a2,
        pvData,
        a5,
        **((_QWORD **)this + 5) + 672LL);
      v39 = v50;
      v40 = WPP_GLOBAL_Control;
      v37 = pvData;
      v38 = v53[0];
    }
    v41 = v52;
    v42 = v51 & 0xDF;
    v39 = v52 | v39 & 0xF;
    goto LABEL_146;
  }
  v42 = v51;
  v40 = WPP_GLOBAL_Control;
  v41 = v52;
LABEL_147:
  v43 = v42 & 0xFE;
  v51 = v43;
  if ( v39 != v33 || v43 != v34 || v38 != v35 )
  {
    v12 = 0;
    v44 = TieringHeatSession::SetCurrentHeatRecord(this, 0, 0, &v50, &v51, 0, v53, 0);
    v11 = v44;
    if ( v44 )
    {
      if ( v44 == -529 || v44 == -1092 || v44 == -1808 )
      {
        v12 = ATL::AtlHresultFromWin32(112);
      }
      else if ( v44 == -1011 )
      {
        v12 = -2147024882;
      }
      else
      {
        v45 = -v44;
        if ( v45 < 0 )
          LOWORD(v45) = v11;
        v12 = v11 & 0x8E5E0000 | (unsigned __int16)v45 | 0xE5E0000;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_iiZd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          60,
          (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
          *((_QWORD *)a2 + 1),
          *(_QWORD *)a2,
          **((_QWORD **)this + 5) + 672LL,
          v11);
      }
      goto LABEL_74;
    }
    v46 = JetUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 0, 0, 0);
    v27 = v46;
    switch ( v46 )
    {
      case 0:
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_iiiDDDDDDZ(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v47,
            v48,
            *((_QWORD *)a2 + 1),
            *(_QWORD *)a2,
            pvData,
            v33,
            v50,
            v34,
            v51,
            v35,
            v53[0],
            **((_QWORD **)this + 5) + 672LL);
        }
        return v12;
      case -529:
      case -1092:
      case -1808:
        v12 = ATL::AtlHresultFromWin32(112);
        break;
      case -1011:
        v12 = -2147024882;
        break;
      default:
        v49 = -v46;
        if ( v49 < 0 )
          LOWORD(v49) = v27;
        v12 = v27 & 0x8E5E0000 | (unsigned __int16)v49 | 0xE5E0000;
        break;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_iiZd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        61,
        (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
        *((_QWORD *)a2 + 1),
        *(_QWORD *)a2,
        **((_QWORD **)this + 5) + 672LL,
        v27);
    }
    goto LABEL_89;
  }
  if ( v40 != &WPP_GLOBAL_Control && (*((_BYTE *)v40 + 28) & 1) != 0 && *((_BYTE *)v40 + 25) >= 5u )
    WPP_SF_iiiDZ(
      v40[2],
      63,
      (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
      *((_QWORD *)a2 + 1),
      *(_QWORD *)a2,
      v37,
      v41,
      **((_QWORD **)this + 5) + 672LL);
  JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 3u);
  return 0;
}

```

## disassembly

```asm
0x140024b60  push    rbp
0x140024b62  push    rbx
0x140024b63  push    rsi
0x140024b64  push    rdi
0x140024b65  push    r12
0x140024b67  push    r13
0x140024b69  push    r14
0x140024b6b  push    r15
0x140024b6d  lea     rbp, [rsp-17h]
0x140024b72  sub     rsp, 0B8h
0x140024b79  mov     rax, cs:__security_cookie
0x140024b80  xor     rax, rsp
0x140024b83  mov     [rbp+4Fh+var_48], rax
0x140024b87  xor     eax, eax
0x140024b89  mov     [rbp+4Fh+pvData], r8
0x140024b8d  mov     r14, rdx
0x140024b90  mov     [rbp+4Fh+var_7C], ax
0x140024b94  mov     bl, r9b
0x140024b97  mov     qword ptr [rbp+4Fh+var_58], rax
0x140024b9b  mov     rsi, rcx
0x140024b9e  mov     [rbp+4Fh+var_7E], bl
0x140024ba1  lea     r8d, [rax+10h]; Length
0x140024ba5  mov     [rbp+4Fh+var_80], bl
0x140024ba8  lea     rdx, ?NullGuid@@3U_GUID@@A; Source2
0x140024baf  mov     [rbp+4Fh+var_50], eax
0x140024bb2  mov     rcx, r14; Source1
0x140024bb5  mov     [rbp+4Fh+var_4C], ax
0x140024bb9  call    cs:__imp_RtlCompareMemory
0x140024bbf  cmp     rax, 10h
0x140024bc3  jnz     short loc_140024C0D
0x140024bc5  lea     ecx, [rax+6Bh]; unsigned int
0x140024bc8  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140024bcd  mov     edi, eax
0x140024bcf  mov     rcx, cs:WPP_GLOBAL_Control
0x140024bd6  lea     rax, WPP_GLOBAL_Control
0x140024bdd  cmp     rcx, rax
0x140024be0  jz      short loc_140024C06
0x140024be2  test    byte ptr [rcx+1Ch], 1
0x140024be6  jz      short loc_140024C06
0x140024be8  cmp     byte ptr [rcx+19h], 2
0x140024bec  jb      short loc_140024C06
0x140024bee  mov     rcx, [rcx+10h]
0x140024bf2  lea     r8, WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids
0x140024bf9  mov     edx, 2Eh ; '.'
0x140024bfe  mov     r9d, edi
0x140024c01  call    WPP_SF_d
0x140024c06  mov     eax, edi
0x140024c08  jmp     loc_140025849
0x140024c0d  lea     r15, WPP_GLOBAL_Control
0x140024c14  mov     r13d, 0FFFFFDEFh
0x140024c1a  mov     r12d, 3
0x140024c20  mov     rdx, [rsi+18h]; tableid
0x140024c24  mov     r9d, 10h; cbData
0x140024c2a  mov     rcx, [rsi+8]; sesid
0x140024c2e  mov     r8, r14; pvData
0x140024c31  mov     [rsp+0F0h+grbit], 1; grbit
0x140024c39  call    cs:__imp_JetMakeKey
0x140024c3f  mov     edi, eax
0x140024c41  test    eax, eax
0x140024c43  jz      short loc_140024CB9
0x140024c45  cmp     eax, r13d
0x140024c48  jz      short loc_140024C7F
0x140024c4a  cmp     eax, 0FFFFFBBCh
0x140024c4f  jz      short loc_140024C7F
0x140024c51  cmp     eax, 0FFFFF8F0h
0x140024c56  jz      short loc_140024C7F
0x140024c58  cmp     eax, 0FFFFFC0Dh
0x140024c5d  jnz     short loc_140024C66
0x140024c5f  mov     ebx, 8007000Eh
0x140024c64  jmp     short loc_140024C8B
0x140024c66  neg     eax
0x140024c68  cmovs   eax, edi
0x140024c6b  movzx   ebx, ax
0x140024c6e  mov     eax, edi
0x140024c70  and     eax, 8E5E0000h
0x140024c75  or      ebx, eax
0x140024c77  or      ebx, 0E5E0000h
0x140024c7d  jmp     short loc_140024C8B
0x140024c7f  mov     ecx, 70h ; 'p'; unsigned int
0x140024c84  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140024c89  mov     ebx, eax
0x140024c8b  mov     rcx, cs:WPP_GLOBAL_Control
0x140024c92  cmp     rcx, r15
0x140024c95  jz      loc_140024D73
0x140024c9b  test    byte ptr [rcx+1Ch], 1
0x140024c9f  jz      loc_140024D73
0x140024ca5  cmp     byte ptr [rcx+19h], 2
0x140024ca9  jb      loc_140024D73
0x140024caf  mov     edx, 2Fh ; '/'
0x140024cb4  jmp     loc_140024D46
0x140024cb9  mov     rdx, [rsi+18h]; tableid
0x140024cbd  lea     r8, [rbp+4Fh+pvData]; pvData
0x140024cc1  mov     rcx, [rsi+8]; sesid
0x140024cc5  mov     r9d, 8; cbData
0x140024ccb  mov     [rsp+0F0h+grbit], 0; grbit
0x140024cd3  call    cs:__imp_JetMakeKey
0x140024cd9  mov     edi, eax
0x140024cdb  test    eax, eax
0x140024cdd  jz      loc_140024D87
0x140024ce3  cmp     eax, r13d
0x140024ce6  jz      short loc_140024D1D
0x140024ce8  cmp     eax, 0FFFFFBBCh
0x140024ced  jz      short loc_140024D1D
0x140024cef  cmp     eax, 0FFFFF8F0h
0x140024cf4  jz      short loc_140024D1D
0x140024cf6  cmp     eax, 0FFFFFC0Dh
0x140024cfb  jnz     short loc_140024D04
0x140024cfd  mov     ebx, 8007000Eh
0x140024d02  jmp     short loc_140024D29
0x140024d04  neg     eax
0x140024d06  cmovs   eax, edi
0x140024d09  movzx   ebx, ax
0x140024d0c  mov     eax, edi
0x140024d0e  and     eax, 8E5E0000h
0x140024d13  or      ebx, eax
0x140024d15  or      ebx, 0E5E0000h
0x140024d1b  jmp     short loc_140024D29
0x140024d1d  mov     ecx, 70h ; 'p'; unsigned int
0x140024d22  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140024d27  mov     ebx, eax
0x140024d29  mov     rcx, cs:WPP_GLOBAL_Control
0x140024d30  cmp     rcx, r15
0x140024d33  jz      short loc_140024D73
0x140024d35  test    byte ptr [rcx+1Ch], 1
0x140024d39  jz      short loc_140024D73
0x140024d3b  cmp     byte ptr [rcx+19h], 2
0x140024d3f  jb      short loc_140024D73
0x140024d41  mov     edx, 30h ; '0'
0x140024d46  mov     rax, [rsi+28h]
0x140024d4a  lea     r8, WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids
0x140024d51  mov     r9, [r14+8]
0x140024d55  mov     rcx, [rcx+10h]
0x140024d59  mov     dword ptr [rsp+0F0h+var_C0], edi
0x140024d5d  mov     rax, [rax+70h]
0x140024d61  mov     [rsp+0F0h+var_C8], rax
0x140024d66  mov     rax, [r14]
0x140024d69  mov     qword ptr [rsp+0F0h+grbit], rax
0x140024d6e  call    WPP_SF_iiSd
0x140024d73  cmp     edi, 0FFFFFBB2h
0x140024d79  jnz     loc_140025847
0x140024d7f  mov     bl, [rbp+4Fh+var_7E]
0x140024d82  jmp     loc_140024C20
0x140024d87  mov     rdx, [rsi+18h]; tableid
0x140024d8b  mov     r8d, 1; grbit
0x140024d91  mov     rcx, [rsi+8]; sesid
0x140024d95  call    cs:__imp_JetSeek
0x140024d9b  mov     edi, eax
0x140024d9d  test    bl, 20h
0x140024da0  jnz     loc_140025065
0x140024da6  cmp     eax, 0FFFFF9BFh
0x140024dab  jz      short loc_140024DB8
0x140024dad  cmp     eax, 40Fh
0x140024db2  jnz     loc_140025065
0x140024db8  mov     rdx, [rsi+18h]; tableid
0x140024dbc  xor     r8d, r8d; prep
0x140024dbf  mov     rcx, [rsi+8]; sesid
0x140024dc3  mov     [rbp+4Fh+var_80], bl
0x140024dc6  call    cs:__imp_JetPrepareUpdate
0x140024dcc  mov     edi, eax
0x140024dce  cmp     eax, 0FFFFF9B9h
0x140024dd3  jnz     short loc_140024DF9
0x140024dd5  mov     rdx, [rsi+18h]; tableid
0x140024dd9  mov     r8d, r12d; prep
0x140024ddc  mov     rcx, [rsi+8]; sesid
0x140024de0  call    cs:__imp_JetPrepareUpdate
0x140024de6  mov     rdx, [rsi+18h]; tableid
0x140024dea  xor     r8d, r8d; prep
0x140024ded  mov     rcx, [rsi+8]; sesid
0x140024df1  call    cs:__imp_JetPrepareUpdate
0x140024df7  mov     edi, eax
0x140024df9  test    edi, edi
0x140024dfb  jz      short loc_140024E76
0x140024dfd  cmp     edi, r13d
0x140024e00  jz      short loc_140024E3C
0x140024e02  cmp     edi, 0FFFFFBBCh
0x140024e08  jz      short loc_140024E3C
0x140024e0a  cmp     edi, 0FFFFF8F0h
0x140024e10  jz      short loc_140024E3C
0x140024e12  cmp     edi, 0FFFFFC0Dh
0x140024e18  jnz     short loc_140024E21
0x140024e1a  mov     ebx, 8007000Eh
0x140024e1f  jmp     short loc_140024E48
0x140024e21  mov     eax, edi
0x140024e23  neg     eax
0x140024e25  cmovs   eax, edi
0x140024e28  movzx   ebx, ax
0x140024e2b  mov     eax, edi
0x140024e2d  and     eax, 8E5E0000h
0x140024e32  or      ebx, eax
0x140024e34  or      ebx, 0E5E0000h
0x140024e3a  jmp     short loc_140024E48
0x140024e3c  mov     ecx, 70h ; 'p'; unsigned int
0x140024e41  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140024e46  mov     ebx, eax
0x140024e48  mov     rcx, cs:WPP_GLOBAL_Control
0x140024e4f  cmp     rcx, r15
0x140024e52  jz      loc_140024D73
0x140024e58  test    byte ptr [rcx+1Ch], 1
0x140024e5c  jz      loc_140024D73
0x140024e62  cmp     byte ptr [rcx+19h], 2
0x140024e66  jb      loc_140024D73
0x140024e6c  mov     edx, 31h ; '1'
0x140024e71  jmp     loc_140024D46
0x140024e76  mov     eax, 0FFFFh
0x140024e7b  lea     rdi, [rbp+4Fh+var_58+2]
0x140024e7f  movzx   eax, ax
0x140024e82  lea     r9, [rbp+4Fh+var_80]; unsigned __int8 *
0x140024e86  mov     ecx, 6
0x140024e8b  lea     r8, [rbp+4Fh+pvData]; __int64 *
0x140024e8f  rep stosw
0x140024e92  xor     eax, eax
0x140024e94  mov     rdx, r14; struct TE_FILE_ID_128 *
0x140024e97  mov     [rbp+4Fh+var_58], ax
0x140024e9b  mov     rax, [rsi+28h]
0x140024e9f  mov     rcx, [rax]
0x140024ea2  lea     rax, [rbp+4Fh+var_58]
0x140024ea6  mov     [rsp+0F0h+var_B8], rax; unsigned __int16 *
0x140024eab  add     rcx, 148h
0x140024eb2  lea     rax, [rbp+4Fh+arg_20]
0x140024eb6  mov     [rsp+0F0h+var_C0], rax; unsigned __int16 *
0x140024ebb  mov     [rsp+0F0h+var_C8], rcx; unsigned __int8 *
0x140024ec0  mov     rcx, rsi; this
0x140024ec3  mov     qword ptr [rsp+0F0h+grbit], 0; unsigned __int8 *
0x140024ecc  call    ?SetCurrentHeatRecord@TieringHeatSession@@QEAAJPEAUTE_FILE_ID_128@@PEA_JPEAE22PEAG3@Z; TieringHeatSession::SetCurrentHeatRecord(TE_FILE_ID_128 *,__int64 *,uchar *,uchar *,uchar *,ushort *,ushort *)
0x140024ed1  mov     edi, eax
0x140024ed3  test    eax, eax
0x140024ed5  jz      loc_140024F81
0x140024edb  cmp     eax, r13d
0x140024ede  jz      short loc_140024F15
0x140024ee0  cmp     eax, 0FFFFFBBCh
0x140024ee5  jz      short loc_140024F15
0x140024ee7  cmp     eax, 0FFFFF8F0h
0x140024eec  jz      short loc_140024F15
0x140024eee  cmp     eax, 0FFFFFC0Dh
0x140024ef3  jnz     short loc_140024EFC
0x140024ef5  mov     ebx, 8007000Eh
0x140024efa  jmp     short loc_140024F21
0x140024efc  neg     eax
0x140024efe  cmovs   eax, edi
0x140024f01  movzx   ebx, ax
0x140024f04  mov     eax, edi
0x140024f06  and     eax, 8E5E0000h
0x140024f0b  or      ebx, eax
0x140024f0d  or      ebx, 0E5E0000h
0x140024f13  jmp     short loc_140024F21
0x140024f15  mov     ecx, 70h ; 'p'; unsigned int
0x140024f1a  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140024f1f  mov     ebx, eax
0x140024f21  mov     rcx, cs:WPP_GLOBAL_Control
0x140024f28  cmp     rcx, r15
0x140024f2b  jz      short loc_140024F6B
0x140024f2d  test    byte ptr [rcx+1Ch], 1
0x140024f31  jz      short loc_140024F6B
0x140024f33  cmp     byte ptr [rcx+19h], 2
0x140024f37  jb      short loc_140024F6B
0x140024f39  mov     rax, [rsi+28h]
0x140024f3d  lea     r8, WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids
0x140024f44  mov     r9, [r14+8]
0x140024f48  mov     edx, 32h ; '2'
0x140024f4d  mov     rcx, [rcx+10h]
0x140024f51  mov     dword ptr [rsp+0F0h+var_C0], edi
0x140024f55  mov     rax, [rax+70h]
0x140024f59  mov     [rsp+0F0h+var_C8], rax
0x140024f5e  mov     rax, [r14]
0x140024f61  mov     qword ptr [rsp+0F0h+grbit], rax
0x140024f66  call    WPP_SF_iiSd
0x140024f6b  mov     rdx, [rsi+18h]; tableid
0x140024f6f  mov     r8d, r12d; prep
0x140024f72  mov     rcx, [rsi+8]; sesid
0x140024f76  call    cs:__imp_JetPrepareUpdate
0x140024f7c  jmp     loc_140024D73
0x140024f81  mov     rdx, [rsi+18h]; tableid
0x140024f85  xor     r9d, r9d; cbBookmark
0x140024f88  mov     rcx, [rsi+8]; sesid
0x140024f8c  xor     r8d, r8d; pvBookmark
0x140024f8f  mov     qword ptr [rsp+0F0h+grbit], 0; pcbActual
0x140024f98  call    cs:__imp_JetUpdate
0x140024f9e  mov     edi, eax
0x140024fa0  test    eax, eax
0x140024fa2  jz      loc_1400255F8
0x140024fa8  cmp     eax, r13d
0x140024fab  jz      short loc_140024FE2
0x140024fad  cmp     eax, 0FFFFFBBCh
0x140024fb2  jz      short loc_140024FE2
0x140024fb4  cmp     eax, 0FFFFF8F0h
0x140024fb9  jz      short loc_140024FE2
0x140024fbb  cmp     eax, 0FFFFFC0Dh
0x140024fc0  jnz     short loc_140024FC9
0x140024fc2  mov     ebx, 8007000Eh
0x140024fc7  jmp     short loc_140024FEE
0x140024fc9  neg     eax
0x140024fcb  cmovs   eax, edi
0x140024fce  movzx   ebx, ax
0x140024fd1  mov     eax, edi
0x140024fd3  and     eax, 8E5E0000h
0x140024fd8  or      ebx, eax
0x140024fda  or      ebx, 0E5E0000h
0x140024fe0  jmp     short loc_140024FEE
0x140024fe2  mov     ecx, 70h ; 'p'; unsigned int
0x140024fe7  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
  ... truncated ...
```
