# TieringPinnedSession::AddOrUpdatePinnedRecord(TE_FILE_ID_128 const *,_STORAGE_TIER_CLASS)

- ea: `0x14001e2e0`
- end: `0x14001eff5`
- name: `?AddOrUpdatePinnedRecord@TieringPinnedSession@@QEAAJPEBUTE_FILE_ID_128@@W4_STORAGE_TIER_CLASS@@@Z`
- size: `3349`
- prototype: `__int64 __fastcall(TieringPinnedSession *__hidden this, const struct TE_FILE_ID_128 *, enum _STORAGE_TIER_CLASS)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400122fc`
- `0x14002e86c`

## callees

- `0x140002db0`
- `0x140004a68`
- `0x140004ef0`
- `0x140005420`
- `0x140009a04`
- `0x140009c08`
- `0x14001e2e0`
- `0x14001f744`
- `0x140020c6c`
- `0x140020ecc`
- `0x140021018`
- `0x1400210c8`
- `0x14003fbb0`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x14001e375`
- `ntdll!RtlCompareMemory` at `0x14001e8aa`
- `ntdll!RtlCompareMemory` at `0x14001e375`
- `ntdll!RtlCompareMemory` at `0x14001e8aa`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14001ee04`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14001ee04`
- `ESENT!JetRollback` at `0x14001e4fc`
- `ESENT!JetRollback` at `0x14001ede5`
- `ESENT!JetRollback` at `0x14001e4fc`
- `ESENT!JetRollback` at `0x14001ede5`
- `ESENT!JetBeginTransaction` at `0x14001e3fd`
- `ESENT!JetBeginTransaction` at `0x14001e3fd`
- `ESENT!JetCommitTransaction` at `0x14001ee1b`
- `ESENT!JetCommitTransaction` at `0x14001ee1b`
- `ESENT!JetPrepareUpdate` at `0x14001e65c`
- `ESENT!JetPrepareUpdate` at `0x14001e677`
- `ESENT!JetPrepareUpdate` at `0x14001e6ca`
- `ESENT!JetPrepareUpdate` at `0x14001e869`
- `ESENT!JetPrepareUpdate` at `0x14001e92e`
- `ESENT!JetPrepareUpdate` at `0x14001ea1e`
- `ESENT!JetPrepareUpdate` at `0x14001eaa1`
- `ESENT!JetPrepareUpdate` at `0x14001eabe`
- `ESENT!JetPrepareUpdate` at `0x14001eb13`
- `ESENT!JetPrepareUpdate` at `0x14001ecac`
- `ESENT!JetPrepareUpdate` at `0x14001eda8`
- `ESENT!JetPrepareUpdate` at `0x14001e65c`
- `ESENT!JetPrepareUpdate` at `0x14001e677`
- `ESENT!JetPrepareUpdate` at `0x14001e6ca`
- `ESENT!JetPrepareUpdate` at `0x14001e869`
- `ESENT!JetPrepareUpdate` at `0x14001e92e`
- `ESENT!JetPrepareUpdate` at `0x14001ea1e`
- `ESENT!JetPrepareUpdate` at `0x14001eaa1`
- `ESENT!JetPrepareUpdate` at `0x14001eabe`
- `ESENT!JetPrepareUpdate` at `0x14001eb13`
- `ESENT!JetPrepareUpdate` at `0x14001ecac`
- `ESENT!JetPrepareUpdate` at `0x14001eda8`
- `ESENT!JetUpdate` at `0x14001ecf7`
- `ESENT!JetUpdate` at `0x14001ecf7`
- `ESENT!JetMakeKey` at `0x14001e422`
- `ESENT!JetMakeKey` at `0x14001e422`
- `ESENT!JetSeek` at `0x14001e512`
- `ESENT!JetSeek` at `0x14001e512`

## string_xrefs

- `0x14001e322`: `TieringPinnedSession::AddOrUpdatePinnedRecord`

## pseudocode

```c
__int64 __fastcall TieringPinnedSession::AddOrUpdatePinnedRecord(
        TieringPinnedSession *this,
        const struct TE_FILE_ID_128 *a2,
        enum _STORAGE_TIER_CLASS a3)
{
  int v6; // ebx
  signed int v7; // ebx
  unsigned __int8 v8; // al
  JET_ERR v9; // edi
  JET_ERR v10; // eax
  JET_ERR v11; // r8d
  JET_ERR Key; // eax
  int v13; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  JET_ERR v16; // eax
  int v17; // eax
  int v18; // eax
  JET_ERR CurrentPinnedRecord; // eax
  int v20; // eax
  JET_ERR v21; // eax
  int v22; // eax
  int v23; // eax
  JET_ERR v24; // eax
  int v25; // eax
  JET_ERR v26; // eax
  int v27; // eax
  JET_SESID v28; // rcx
  JET_ERR v29; // eax
  int v30; // eax
  int v31; // eax
  _QWORD *v32; // rax
  unsigned __int8 v34; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int8 v35[7]; // [rsp+51h] [rbp-2Fh] BYREF
  _BYTE v36[8]; // [rsp+58h] [rbp-28h] BYREF
  int v37; // [rsp+60h] [rbp-20h]
  __int128 Source1; // [rsp+68h] [rbp-18h] BYREF

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "TieringPinnedSession::AddOrUpdatePinnedRecord";
  CHResultImp::CHResultImp((CHResultImp *)v36);
  v34 = 0;
  v35[0] = 0;
  v6 = a3 - 1;
  if ( v6 )
  {
    if ( v6 != 1 )
    {
      v7 = -2147024809;
      v37 = -2147024809;
      goto LABEL_233;
    }
    v8 = 1;
  }
  else
  {
    v8 = 2;
  }
  v34 = v8;
  if ( RtlCompareMemory(a2, &NullGuid, 0x10u) == 16 )
  {
    v7 = -2138898428;
    v37 = -2138898428;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids, 2156068868LL);
    }
    goto LABEL_233;
  }
  v7 = v37;
  v9 = -1102;
  while ( 1 )
  {
    if ( v9 != -1102 && v9 != -1605 )
      goto LABEL_227;
    v10 = JetBeginTransaction(*((_QWORD *)this + 1));
    v11 = v10;
    if ( v10 )
      break;
    Key = JetMakeKey(*((_QWORD *)this + 1), *((_QWORD *)this + 3), a2, 0x10u, 1u);
    v9 = Key;
    if ( Key )
    {
      if ( Key == -529 || Key == -1092 || Key == -1808 )
      {
        v7 = ATL::AtlHresultFromWin32(0x70u);
      }
      else if ( Key == -1011 )
      {
        v7 = -2147024882;
      }
      else
      {
        v13 = -Key;
        if ( v13 < 0 )
          LOWORD(v13) = v9;
        v7 = v9 & 0x8E5E0000 | (unsigned __int16)v13 | 0xE5E0000;
      }
      v37 = v7;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_iiSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            40,
            (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
            *((_QWORD *)a2 + 1),
            *(_QWORD *)a2,
            *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
            v9);
          v14 = WPP_GLOBAL_Control;
        }
        if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 5u )
        {
          v15 = 41;
LABEL_33:
          WPP_SF_S(
            v14[2],
            v15,
            &WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
            *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
          goto LABEL_34;
        }
      }
      goto LABEL_34;
    }
    v16 = JetSeek(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 1u);
    v9 = v16;
    if ( v16 == -1601 || v16 == 1039 || v16 == -1017 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_iiS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          42,
          (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
          *((_QWORD *)a2 + 1),
          *(_QWORD *)a2,
          *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
      }
      v9 = JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 0);
      if ( v9 == -1607 )
      {
        JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 3u);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_iiS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            43,
            (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
            *((_QWORD *)a2 + 1),
            *(_QWORD *)a2,
            *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
        }
        v9 = JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 0);
      }
      if ( v9 )
      {
        if ( v9 == -529 || v9 == -1092 || v9 == -1808 )
        {
          v7 = ATL::AtlHresultFromWin32(0x70u);
        }
        else if ( v9 == -1011 )
        {
          v7 = -2147024882;
        }
        else
        {
          v23 = -v9;
          if ( v9 > 0 )
            LOWORD(v23) = v9;
          v7 = v9 & 0x8E5E0000 | (unsigned __int16)v23 | 0xE5E0000;
        }
        v37 = v7;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_iiSd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              44,
              (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
              *((_QWORD *)a2 + 1),
              *(_QWORD *)a2,
              *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
              v9);
            v14 = WPP_GLOBAL_Control;
          }
          if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 5u )
          {
            v15 = 45;
            goto LABEL_33;
          }
        }
        goto LABEL_34;
      }
      v24 = TieringPinnedSession::SetCurrentPinnedRecord(this, a2, &v34, v35);
      v9 = v24;
      if ( v24 )
      {
        if ( v24 == -529 || v24 == -1092 || v24 == -1808 )
        {
          v7 = ATL::AtlHresultFromWin32(0x70u);
        }
        else if ( v24 == -1011 )
        {
          v7 = -2147024882;
        }
        else
        {
          v25 = -v24;
          if ( v25 < 0 )
            LOWORD(v25) = v9;
          v7 = v9 & 0x8E5E0000 | (unsigned __int16)v25 | 0xE5E0000;
        }
        v37 = v7;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_iiSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            46,
            (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
            *((_QWORD *)a2 + 1),
            *(_QWORD *)a2,
            *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
            v9);
        }
        JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 3u);
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v15 = 47;
          goto LABEL_33;
        }
        goto LABEL_34;
      }
      goto LABEL_175;
    }
    if ( v16 )
    {
      if ( v16 == -529 || v16 == -1092 || v16 == -1808 )
      {
        v7 = ATL::AtlHresultFromWin32(0x70u);
      }
      else if ( v16 == -1011 )
      {
        v7 = -2147024882;
      }
      else
      {
        v17 = -v16;
        if ( v17 < 0 )
          LOWORD(v17) = v9;
        v7 = v9 & 0x8E5E0000 | (unsigned __int16)v17 | 0xE5E0000;
      }
      v37 = v7;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_iiSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            48,
            (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
            *((_QWORD *)a2 + 1),
            *(_QWORD *)a2,
            *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
            v9);
          v14 = WPP_GLOBAL_Control;
        }
        if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 5u )
        {
          v15 = 49;
          goto LABEL_33;
        }
      }
LABEL_34:
      JetRollback(*((_QWORD *)this + 1), 0);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_iiS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          50,
          (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
          *((_QWORD *)a2 + 1),
          *(_QWORD *)a2,
          *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
      }
      v9 = JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 2u);
      if ( v9 == -1607 )
      {
        JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 3u);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_iiS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51,
            (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
            *((_QWORD *)a2 + 1),
            *(_QWORD *)a2,
            *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
        }
        v9 = JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 2u);
      }
      if ( v9 )
      {
        if ( v9 == -529 || v9 == -1092 || v9 == -1808 )
        {
          v7 = ATL::AtlHresultFromWin32(0x70u);
        }
        else if ( v9 == -1011 )
        {
          v7 = -2147024882;
        }
        else
        {
          v18 = -v9;
          if ( v9 > 0 )
            LOWORD(v18) = v9;
          v7 = v9 & 0x8E5E0000 | (unsigned __int16)v18 | 0xE5E0000;
        }
        v37 = v7;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_iiSd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              52,
              (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
              *((_QWORD *)a2 + 1),
              *(_QWORD *)a2,
              *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
              v9);
            v14 = WPP_GLOBAL_Control;
          }
          if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 5u )
          {
            v15 = 53;
            goto LABEL_33;
          }
        }
        goto LABEL_34;
      }
      Source1 = 0;
      CurrentPinnedRecord = TieringPinnedSession::GetCurrentPinnedRecord(this, (struct TE_FILE_ID_128 *)&Source1, 0, 0);
      v9 = CurrentPinnedRecord;
      if ( CurrentPinnedRecord )
      {
        if ( CurrentPinnedRecord == -529 || CurrentPinnedRecord == -1092 || CurrentPinnedRecord == -1808 )
        {
          v7 = ATL::AtlHresultFromWin32(0x70u);
        }
        else if ( CurrentPinnedRecord == -1011 )
        {
          v7 = -2147024882;
        }
        else
        {
          v20 = -CurrentPinnedRecord;
          if ( v20 < 0 )
            LOWORD(v20) = v9;
          v7 = v9 & 0x8E5E0000 | (unsigned __int16)v20 | 0xE5E0000;
        }
        v37 = v7;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_iiSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            54,
            (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
            *((_QWORD *)a2 + 1),
            *(_QWORD *)a2,
            *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
            v9);
        }
        JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 3u);
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v15 = 55;
          goto LABEL_33;
        }
        goto LABEL_34;
      }
      if ( RtlCompareMemory(&Source1, a2, 0x10u) != 16 )
      {
        v7 = -2147220986;
        v37 = -2147220986;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_iiiiSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            56,
            (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
            *((_QWORD *)a2 + 1),
            *(_QWORD *)a2,
            SBYTE8(Source1),
            Source1,
            *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
            0);
        }
        JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 3u);
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v15 = 57;
          goto LABEL_33;
        }
        goto LABEL_34;
      }
      v21 = TieringPinnedSession::SetCurrentPinnedRecord(this, 0, &v34, 0);
      v9 = v21;
      if ( v21 )
      {
        if ( v21 == -529 || v21 == -1092 || v21 == -1808 )
        {
          v7 = ATL::AtlHresultFromWin32(0x70u);
        }
        else if ( v21 == -1011 )
        {
          v7 = -2147024882;
        }
        else
        {
          v22 = -v21;
          if ( v22 < 0 )
            LOWORD(v22) = v9;
          v7 = v9 & 0x8E5E0000 | (unsigned __int16)v22 | 0xE5E0000;
        }
        v37 = v7;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_iiSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            58,
            (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
            *((_QWORD *)a2 + 1),
            *(_QWORD *)a2,
            *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
            v9);
        }
        JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 3u);
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v15 = 59;
          goto LABEL_33;
        }
        goto LABEL_34;
      }
LABEL_175:
      v26 = JetUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 0, 0, 0);
      v9 = v26;
      if ( v26 )
      {
        if ( v26 == -529 || v26 == -1092 || v26 == -1808 )
        {
          v7 = ATL::AtlHresultFromWin32(0x70u);
        }
        else if ( v26 == -1011 )
        {
          v7 = -2147024882;
        }
        else
        {
          v27 = -v26;
          if ( v27 < 0 )
            LOWORD(v27) = v9;
          v7 = v9 & 0x8E5E0000 | (unsigned __int16)v27 | 0xE5E0000;
        }
        v37 = v7;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_iiSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            60,
            (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
            *((_QWORD *)a2 + 1),
            *(_QWORD *)a2,
            *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
            v9);
        }
        JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 3u);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            61,
            &WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
            *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
        }
        JetRollback(*((_QWORD *)this + 1), 0);
        if ( v9 == -1102 || v9 == -1605 )
          Sleep(0x64u);
      }
      else
      {
        v28 = *((_QWORD *)this + 1);
        v7 = 0;
        v37 = 0;
        v29 = JetCommitTransaction(v28, 1u);
        v9 = v29;
        if ( v29 )
        {
          if ( v29 == -529 || v29 == -1092 || v29 == -1808 )
          {
            v7 = ATL::AtlHresultFromWin32(0x70u);
          }
          else if ( v29 == -1011 )
          {
            v7 = -2147024882;
          }
          else
          {
            v30 = -v29;
            if ( v30 < 0 )
              LOWORD(v30) = v9;
            v7 = v9 & 0x8E5E0000 | (unsigned __int16)v30 | 0xE5E0000;
          }
          v37 = v7;
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_iiSd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                62,
                (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
                *((_QWORD *)a2 + 1),
                *(_QWORD *)a2,
                *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
                v9);
              v14 = WPP_GLOBAL_Control;
            }
            if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 5u )
            {
              v15 = 63;
              goto LABEL_33;
            }
          }
          goto LABEL_34;
        }
      }
    }
  }
  if ( v10 == -529 || v10 == -1092 || v10 == -1808 )
  {
    v7 = ATL::AtlHresultFromWin32(0x70u);
  }
  else if ( v10 == -1011 )
  {
    v7 = -2147024882;
  }
  else
  {
    v31 = -v10;
    if ( v31 < 0 )
      LOWORD(v31) = v11;
    v7 = v11 & 0x8E5E0000 | (unsigned __int16)v31 | 0xE5E0000;
  }
  v37 = v7;
  v32 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
      *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
      v11);
LABEL_227:
    v32 = WPP_GLOBAL_Control;
  }
  if ( v7 >= 0 && v32 != &WPP_GLOBAL_Control && (*((_BYTE *)v32 + 28) & 1) != 0 && *((_BYTE *)v32 + 25) >= 5u )
    WPP_SF_iiS(
      v32[2],
      64,
      (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
      *((_QWORD *)a2 + 1),
      *(_QWORD *)a2,
      *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
LABEL_233:
  CHResultImp::~CHResultImp((CHResultImp *)v36);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14001e2e0  mov     [rsp-38h+arg_10], rbx
0x14001e2e5  push    rbp
0x14001e2e6  push    rsi
0x14001e2e7  push    rdi
0x14001e2e8  push    r12
0x14001e2ea  push    r13
0x14001e2ec  push    r14
0x14001e2ee  push    r15
0x14001e2f0  mov     rbp, rsp
0x14001e2f3  sub     rsp, 80h
0x14001e2fa  mov     rax, cs:__security_cookie
0x14001e301  xor     rax, rsp
0x14001e304  mov     [rbp+var_8], rax
0x14001e308  mov     rax, gs:58h
0x14001e311  mov     rsi, rcx
0x14001e314  mov     r12, rdx
0x14001e317  mov     ecx, 8
0x14001e31c  mov     ebx, r8d
0x14001e31f  mov     rdx, [rax]
0x14001e322  lea     rax, aTieringpinneds; "TieringPinnedSession::AddOrUpdatePinned"...
0x14001e329  mov     [rcx+rdx], rax
0x14001e32d  lea     rcx, [rbp+var_28]; this
0x14001e331  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14001e336  mov     r13d, 1
0x14001e33c  mov     [rbp+var_30], 0
0x14001e340  mov     [rbp+var_2F], 0
0x14001e344  sub     ebx, r13d
0x14001e347  jz      short loc_14001E360
0x14001e349  cmp     ebx, r13d
0x14001e34c  jz      short loc_14001E35B
0x14001e34e  mov     ebx, 80070057h
0x14001e353  mov     [rbp+var_20], ebx
0x14001e356  jmp     loc_14001EFC3
0x14001e35b  mov     al, r13b
0x14001e35e  jmp     short loc_14001E362
0x14001e360  mov     al, 2
0x14001e362  mov     r8d, 10h; Length
0x14001e368  mov     [rbp+var_30], al
0x14001e36b  lea     rdx, ?NullGuid@@3U_GUID@@A; Source2
0x14001e372  mov     rcx, r12; Source1
0x14001e375  call    cs:__imp_RtlCompareMemory
0x14001e37b  cmp     rax, 10h
0x14001e37f  jnz     short loc_14001E3CF
0x14001e381  mov     ebx, 80830004h
0x14001e386  mov     [rbp+var_20], ebx
0x14001e389  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e390  lea     r14, WPP_GLOBAL_Control
0x14001e397  cmp     rcx, r14
0x14001e39a  jz      loc_14001EFC3
0x14001e3a0  test    [rcx+1Ch], r13b
0x14001e3a4  jz      loc_14001EFC3
0x14001e3aa  cmp     byte ptr [rcx+19h], 2
0x14001e3ae  jb      loc_14001EFC3
0x14001e3b4  mov     rcx, [rcx+10h]
0x14001e3b8  lea     edx, [rax+16h]
0x14001e3bb  mov     r9d, ebx
0x14001e3be  lea     r8, WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids
0x14001e3c5  call    WPP_SF_d
0x14001e3ca  jmp     loc_14001EFC3
0x14001e3cf  mov     ebx, [rbp+var_20]
0x14001e3d2  lea     r14, WPP_GLOBAL_Control
0x14001e3d9  mov     edi, 0FFFFFBB2h
0x14001e3de  lea     r15, WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids
0x14001e3e5  cmp     edi, 0FFFFFBB2h
0x14001e3eb  jz      short loc_14001E3F9
0x14001e3ed  cmp     edi, 0FFFFF9BBh
0x14001e3f3  jnz     loc_14001EF7B
0x14001e3f9  mov     rcx, [rsi+8]; sesid
0x14001e3fd  call    cs:__imp_JetBeginTransaction
0x14001e403  mov     r8d, eax
0x14001e406  test    eax, eax
0x14001e408  jnz     loc_14001EEF0
0x14001e40e  mov     rdx, [rsi+18h]; tableid
0x14001e412  lea     r9d, [rax+10h]; cbData
0x14001e416  mov     rcx, [rsi+8]; sesid
0x14001e41a  mov     r8, r12; pvData
0x14001e41d  mov     [rsp+80h+grbit], r13d; grbit
0x14001e422  call    cs:__imp_JetMakeKey
0x14001e428  mov     edi, eax
0x14001e42a  test    eax, eax
0x14001e42c  jz      loc_14001E507
0x14001e432  cmp     eax, 0FFFFFDEFh
0x14001e437  jz      short loc_14001E46E
0x14001e439  cmp     eax, 0FFFFFBBCh
0x14001e43e  jz      short loc_14001E46E
0x14001e440  cmp     eax, 0FFFFF8F0h
0x14001e445  jz      short loc_14001E46E
0x14001e447  cmp     eax, 0FFFFFC0Dh
0x14001e44c  jnz     short loc_14001E455
0x14001e44e  mov     ebx, 8007000Eh
0x14001e453  jmp     short loc_14001E47A
0x14001e455  neg     eax
0x14001e457  cmovs   eax, edi
0x14001e45a  movzx   ebx, ax
0x14001e45d  mov     eax, edi
0x14001e45f  and     eax, 8E5E0000h
0x14001e464  or      ebx, eax
0x14001e466  or      ebx, 0E5E0000h
0x14001e46c  jmp     short loc_14001E47A
0x14001e46e  mov     ecx, 70h ; 'p'; unsigned int
0x14001e473  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14001e478  mov     ebx, eax
0x14001e47a  mov     [rbp+var_20], ebx
0x14001e47d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e484  cmp     rcx, r14
0x14001e487  jz      short loc_14001E4F6
0x14001e489  test    [rcx+1Ch], r13b
0x14001e48d  jz      short loc_14001E4CC
0x14001e48f  cmp     byte ptr [rcx+19h], 2
0x14001e493  jb      short loc_14001E4CC
0x14001e495  mov     rax, [rsi+28h]
0x14001e499  mov     edx, 28h ; '('
0x14001e49e  mov     r9, [r12+8]
0x14001e4a3  mov     r8, r15
0x14001e4a6  mov     rcx, [rcx+10h]
0x14001e4aa  mov     dword ptr [rsp+80h+var_50], edi
0x14001e4ae  mov     rax, [rax+70h]
0x14001e4b2  mov     [rsp+80h+var_58], rax
0x14001e4b7  mov     rax, [r12]
0x14001e4bb  mov     qword ptr [rsp+80h+grbit], rax
0x14001e4c0  call    WPP_SF_iiSd
0x14001e4c5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e4cc  cmp     rcx, r14
0x14001e4cf  jz      short loc_14001E4F6
0x14001e4d1  test    [rcx+1Ch], r13b
0x14001e4d5  jz      short loc_14001E4F6
0x14001e4d7  cmp     byte ptr [rcx+19h], 5
0x14001e4db  jb      short loc_14001E4F6
0x14001e4dd  mov     edx, 29h ; ')'
0x14001e4e2  mov     r9, [rsi+28h]
0x14001e4e6  mov     r8, r15
0x14001e4e9  mov     rcx, [rcx+10h]
0x14001e4ed  mov     r9, [r9+70h]
0x14001e4f1  call    WPP_SF_S
0x14001e4f6  mov     rcx, [rsi+8]; sesid
0x14001e4fa  xor     edx, edx; grbit
0x14001e4fc  call    cs:__imp_JetRollback
0x14001e502  jmp     loc_14001E3E5
0x14001e507  mov     rdx, [rsi+18h]; tableid
0x14001e50b  mov     r8d, r13d; grbit
0x14001e50e  mov     rcx, [rsi+8]; sesid
0x14001e512  call    cs:__imp_JetSeek
0x14001e518  mov     edi, eax
0x14001e51a  cmp     eax, 0FFFFF9BFh
0x14001e51f  jz      loc_14001EA52
0x14001e525  cmp     eax, 40Fh
0x14001e52a  jz      loc_14001EA52
0x14001e530  cmp     eax, 0FFFFFC07h
0x14001e535  jz      loc_14001EA52
0x14001e53b  test    eax, eax
0x14001e53d  jz      loc_14001E608
0x14001e543  cmp     eax, 0FFFFFDEFh
0x14001e548  jz      short loc_14001E57F
0x14001e54a  cmp     eax, 0FFFFFBBCh
0x14001e54f  jz      short loc_14001E57F
0x14001e551  cmp     eax, 0FFFFF8F0h
0x14001e556  jz      short loc_14001E57F
0x14001e558  cmp     eax, 0FFFFFC0Dh
0x14001e55d  jnz     short loc_14001E566
0x14001e55f  mov     ebx, 8007000Eh
0x14001e564  jmp     short loc_14001E58B
0x14001e566  neg     eax
0x14001e568  cmovs   eax, edi
0x14001e56b  movzx   ebx, ax
0x14001e56e  mov     eax, edi
0x14001e570  and     eax, 8E5E0000h
0x14001e575  or      ebx, eax
0x14001e577  or      ebx, 0E5E0000h
0x14001e57d  jmp     short loc_14001E58B
0x14001e57f  mov     ecx, 70h ; 'p'; unsigned int
0x14001e584  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14001e589  mov     ebx, eax
0x14001e58b  mov     [rbp+var_20], ebx
0x14001e58e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e595  cmp     rcx, r14
0x14001e598  jz      loc_14001E4F6
0x14001e59e  test    [rcx+1Ch], r13b
0x14001e5a2  jz      short loc_14001E5E1
0x14001e5a4  cmp     byte ptr [rcx+19h], 2
0x14001e5a8  jb      short loc_14001E5E1
0x14001e5aa  mov     rax, [rsi+28h]
0x14001e5ae  mov     edx, 30h ; '0'
0x14001e5b3  mov     r9, [r12+8]
0x14001e5b8  mov     r8, r15
0x14001e5bb  mov     rcx, [rcx+10h]
0x14001e5bf  mov     dword ptr [rsp+80h+var_50], edi
0x14001e5c3  mov     rax, [rax+70h]
0x14001e5c7  mov     [rsp+80h+var_58], rax
0x14001e5cc  mov     rax, [r12]
0x14001e5d0  mov     qword ptr [rsp+80h+grbit], rax
0x14001e5d5  call    WPP_SF_iiSd
0x14001e5da  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e5e1  cmp     rcx, r14
0x14001e5e4  jz      loc_14001E4F6
0x14001e5ea  test    [rcx+1Ch], r13b
0x14001e5ee  jz      loc_14001E4F6
0x14001e5f4  cmp     byte ptr [rcx+19h], 5
0x14001e5f8  jb      loc_14001E4F6
0x14001e5fe  mov     edx, 31h ; '1'
0x14001e603  jmp     loc_14001E4E2
0x14001e608  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e60f  cmp     rcx, r14
0x14001e612  jz      short loc_14001E64C
0x14001e614  test    [rcx+1Ch], r13b
0x14001e618  jz      short loc_14001E64C
0x14001e61a  cmp     byte ptr [rcx+19h], 5
0x14001e61e  jb      short loc_14001E64C
0x14001e620  mov     rax, [rsi+28h]
0x14001e624  mov     edx, 32h ; '2'
0x14001e629  mov     r9, [r12+8]
0x14001e62e  mov     r8, r15
0x14001e631  mov     rcx, [rcx+10h]
0x14001e635  mov     rax, [rax+70h]
0x14001e639  mov     [rsp+80h+var_58], rax
0x14001e63e  mov     rax, [r12]
0x14001e642  mov     qword ptr [rsp+80h+grbit], rax
0x14001e647  call    WPP_SF_iiS
0x14001e64c  mov     rdx, [rsi+18h]; tableid
0x14001e650  mov     ebx, 2
0x14001e655  mov     rcx, [rsi+8]; sesid
0x14001e659  mov     r8d, ebx; prep
0x14001e65c  call    cs:__imp_JetPrepareUpdate
0x14001e662  mov     edi, eax
0x14001e664  cmp     eax, 0FFFFF9B9h
0x14001e669  jnz     short loc_14001E6D2
0x14001e66b  mov     rdx, [rsi+18h]; tableid
0x14001e66f  lea     r8d, [rbx+1]; prep
0x14001e673  mov     rcx, [rsi+8]; sesid
0x14001e677  call    cs:__imp_JetPrepareUpdate
0x14001e67d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e684  cmp     rcx, r14
0x14001e687  jz      short loc_14001E6BF
0x14001e689  test    [rcx+1Ch], r13b
0x14001e68d  jz      short loc_14001E6BF
0x14001e68f  cmp     byte ptr [rcx+19h], 5
0x14001e693  jb      short loc_14001E6BF
0x14001e695  mov     rax, [rsi+28h]
0x14001e699  lea     edx, [rbx+31h]
0x14001e69c  mov     r9, [r12+8]
0x14001e6a1  mov     r8, r15
0x14001e6a4  mov     rcx, [rcx+10h]
0x14001e6a8  mov     rax, [rax+70h]
0x14001e6ac  mov     [rsp+80h+var_58], rax
0x14001e6b1  mov     rax, [r12]
0x14001e6b5  mov     qword ptr [rsp+80h+grbit], rax
0x14001e6ba  call    WPP_SF_iiS
0x14001e6bf  mov     rdx, [rsi+18h]; tableid
0x14001e6c3  mov     r8d, ebx; prep
0x14001e6c6  mov     rcx, [rsi+8]; sesid
0x14001e6ca  call    cs:__imp_JetPrepareUpdate
0x14001e6d0  mov     edi, eax
0x14001e6d2  test    edi, edi
0x14001e6d4  jz      loc_14001E7A5
0x14001e6da  cmp     edi, 0FFFFFDEFh
0x14001e6e0  jz      short loc_14001E71C
0x14001e6e2  cmp     edi, 0FFFFFBBCh
0x14001e6e8  jz      short loc_14001E71C
0x14001e6ea  cmp     edi, 0FFFFF8F0h
0x14001e6f0  jz      short loc_14001E71C
0x14001e6f2  cmp     edi, 0FFFFFC0Dh
0x14001e6f8  jnz     short loc_14001E701
0x14001e6fa  mov     ebx, 8007000Eh
0x14001e6ff  jmp     short loc_14001E728
0x14001e701  mov     eax, edi
0x14001e703  neg     eax
0x14001e705  cmovs   eax, edi
0x14001e708  movzx   ebx, ax
0x14001e70b  mov     eax, edi
0x14001e70d  and     eax, 8E5E0000h
0x14001e712  or      ebx, eax
0x14001e714  or      ebx, 0E5E0000h
0x14001e71a  jmp     short loc_14001E728
0x14001e71c  mov     ecx, 70h ; 'p'; unsigned int
0x14001e721  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14001e726  mov     ebx, eax
0x14001e728  mov     [rbp+var_20], ebx
0x14001e72b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e732  cmp     rcx, r14
0x14001e735  jz      loc_14001E4F6
0x14001e73b  test    [rcx+1Ch], r13b
0x14001e73f  jz      short loc_14001E77E
0x14001e741  cmp     byte ptr [rcx+19h], 2
0x14001e745  jb      short loc_14001E77E
0x14001e747  mov     rax, [rsi+28h]
0x14001e74b  mov     edx, 34h ; '4'
0x14001e750  mov     r9, [r12+8]
0x14001e755  mov     r8, r15
0x14001e758  mov     rcx, [rcx+10h]
0x14001e75c  mov     dword ptr [rsp+80h+var_50], edi
0x14001e760  mov     rax, [rax+70h]
0x14001e764  mov     [rsp+80h+var_58], rax
0x14001e769  mov     rax, [r12]
0x14001e76d  mov     qword ptr [rsp+80h+grbit], rax
0x14001e772  call    WPP_SF_iiSd
0x14001e777  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e77e  cmp     rcx, r14
0x14001e781  jz      loc_14001E4F6
0x14001e787  test    [rcx+1Ch], r13b
0x14001e78b  jz      loc_14001E4F6
0x14001e791  cmp     byte ptr [rcx+19h], 5
  ... truncated ...
```
