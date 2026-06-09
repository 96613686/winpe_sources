# TieringJetSession::OpenJetTable(bool)

- ea: `0x14001b328`
- end: `0x14001c08b`
- name: `?OpenJetTable@TieringJetSession@@QEAAJ_N@Z`
- size: `3427`
- prototype: `__int64 __fastcall(TieringJetSession *__hidden this, bool)`
- caller_count: `18`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14000c444`
- `0x14000c648`
- `0x14000d5f0`
- `0x14000ef74`
- `0x14000f108`
- `0x1400108e0`
- `0x140010d1c`
- `0x1400122fc`
- `0x140017120`
- `0x1400211a4`
- `0x14002eef0`
- `0x14003cfb4`
- `0x14003d800`
- `0x14003db78`
- `0x14003ddd4`
- `0x14003e49c`
- `0x14003eba8`
- `0x14003f4d8`

## callees

- `0x140002db0`
- `0x140004ef0`
- `0x140005420`
- `0x140009904`
- `0x140009a04`
- `0x140009c08`
- `0x140017708`
- `0x14001b328`
- `0x14001c094`
- `0x14001cce8`
- `0x14001cd80`
- `0x14003695c`
- `0x1400370f8`
- `0x14003fbb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001b401`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001b41f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001b51f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001bbcd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001beb6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001b401`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001b41f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001b51f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001bbcd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001beb6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001b39e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001b5f3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001b39e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001b5f3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14001b920`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14001b920`
- `ESENT!JetSetCurrentIndexW` at `0x14001bedc`
- `ESENT!JetSetCurrentIndexW` at `0x14001bef4`
- `ESENT!JetSetCurrentIndexW` at `0x14001bedc`
- `ESENT!JetSetCurrentIndexW` at `0x14001bef4`
- `ESENT!JetCreateDatabase2W` at `0x14001ba2f`
- `ESENT!JetCreateDatabase2W` at `0x14001bdba`
- `ESENT!JetCreateDatabase2W` at `0x14001ba2f`
- `ESENT!JetCreateDatabase2W` at `0x14001bdba`
- `ESENT!JetOpenDatabaseW` at `0x14001b98b`
- `ESENT!JetOpenDatabaseW` at `0x14001bc04`
- `ESENT!JetOpenDatabaseW` at `0x14001b98b`
- `ESENT!JetOpenDatabaseW` at `0x14001bc04`
- `ESENT!JetAttachDatabase2W` at `0x14001b66b`
- `ESENT!JetAttachDatabase2W` at `0x14001b8d6`
- `ESENT!JetAttachDatabase2W` at `0x14001b92b`
- `ESENT!JetAttachDatabase2W` at `0x14001b66b`
- `ESENT!JetAttachDatabase2W` at `0x14001b8d6`
- `ESENT!JetAttachDatabase2W` at `0x14001b92b`
- `ESENT!JetBeginSessionW` at `0x14001b43d`
- `ESENT!JetBeginSessionW` at `0x14001b43d`
- `ESENT!JetEndSession` at `0x14001c080`
- `ESENT!JetEndSession` at `0x14001c080`
- `ESENT!JetCloseDatabase` at `0x14001c039`
- `ESENT!JetCloseDatabase` at `0x14001c039`
- `ESENT!JetCloseTable` at `0x14001bff3`
- `ESENT!JetCloseTable` at `0x14001bff3`

## string_xrefs

- `0x14001b36c`: `TieringJetSession::OpenJetTable`

## pseudocode

```c
__int64 __fastcall TieringJetSession::OpenJetTable(TieringJetSession *this, bool a2)
{
  PVOID ThreadLocalStoragePointer; // rax
  RTL_SRWLOCK *v5; // rbx
  __int64 v6; // rax
  unsigned int v7; // edi
  JET_SESID *v8; // r14
  JET_ERR v9; // eax
  JET_ERR v10; // r8d
  __int64 v11; // r9
  __int64 v12; // rax
  int v14; // eax
  RTL_SRWLOCK **v15; // rax
  RTL_SRWLOCK *v16; // rbx
  __int64 v17; // rax
  JET_ERR v18; // eax
  unsigned int v19; // r8d
  JET_ERR Database2W; // r14d
  __int64 v21; // rax
  char v22; // cl
  _QWORD *v23; // r10
  const WCHAR *v24; // rdx
  JET_SESID v25; // rcx
  JET_ERR v26; // eax
  JET_ERR v27; // eax
  __int64 v28; // rdx
  JET_DBID *v29; // r9
  JET_SESID v30; // rcx
  int v31; // eax
  const WCHAR *v32; // rdx
  __int64 v33; // r8
  __int64 *v34; // rax
  __int64 v35; // rax
  __int64 v36; // rdx
  int v37; // r9d
  char v38; // al
  int v39; // eax
  int v40; // edx
  __int64 v41; // r9
  char v42; // bl
  char v43; // r14
  JET_ERR v44; // eax
  JET_ERR v45; // r8d
  int v46; // eax
  _QWORD *v47; // rcx
  __int64 v48; // rdx
  bool v49; // r13
  int v50; // eax
  int v51; // eax
  JET_TABLEID v52; // rdx
  JET_SESID v53; // rcx
  bool v54; // bl
  const WCHAR *v55; // r8
  JET_ERR v56; // eax
  int v57; // r8d
  int v58; // eax
  _WORD v59[4]; // [rsp+30h] [rbp-39h] BYREF
  bool v60; // [rsp+39h] [rbp-30h]
  bool v61; // [rsp+3Ah] [rbp-2Fh] BYREF
  unsigned int v62; // [rsp+3Ch] [rbp-2Dh]
  _BYTE v63[8]; // [rsp+40h] [rbp-29h] BYREF
  int v64; // [rsp+48h] [rbp-21h]
  PSRWLOCK SRWLock; // [rsp+50h] [rbp-19h]
  _BYTE v66[16]; // [rsp+58h] [rbp-11h] BYREF
  _WORD *v67; // [rsp+68h] [rbp-1h]
  __int64 v68; // [rsp+70h] [rbp+7h]
  __int64 v69; // [rsp+78h] [rbp+Fh]
  int v70; // [rsp+80h] [rbp+17h]
  int v71; // [rsp+84h] [rbp+1Bh]

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v60 = a2;
  *(_QWORD *)(*(_QWORD *)ThreadLocalStoragePointer + 8LL) = "TieringJetSession::OpenJetTable";
  CHResultImp::CHResultImp((CHResultImp *)v63);
  v61 = 0;
  if ( *(_BYTE *)this )
    goto LABEL_29;
  v5 = (RTL_SRWLOCK *)(**((_QWORD **)this + 5) + 24LL);
  AcquireSRWLockExclusive(v5);
  v6 = *((_QWORD *)this + 5);
  if ( !*(_BYTE *)(v6 + 77) )
  {
    if ( a2 )
    {
      if ( !*(_BYTE *)(v6 + 40) )
        goto LABEL_11;
    }
    else if ( !*(_BYTE *)(v6 + 8) )
    {
LABEL_11:
      if ( v5 )
        ReleaseSRWLockExclusive(v5);
      v8 = (JET_SESID *)((char *)this + 8);
      v9 = JetBeginSessionW(**(_QWORD **)(*((_QWORD *)this + 5) + 104LL), (JET_SESID *)this + 1, 0, 0);
      v10 = v9;
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
          v14 = -v9;
          if ( v14 < 0 )
            LOWORD(v14) = v10;
          v7 = v10 & 0x8E5E0000 | (unsigned __int16)v14 | 0xE5E0000;
        }
        v64 = v7;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            82,
            (unsigned int)&WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
            *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
            v10);
        }
        goto LABEL_38;
      }
      v15 = (RTL_SRWLOCK **)*((_QWORD *)this + 5);
      LOBYTE(v59[0]) = 0;
      v16 = *v15 + 3;
      SRWLock = v16;
      AcquireSRWLockExclusive(v16);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          83,
          &WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
          *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
      }
      v17 = *((_QWORD *)this + 5);
      if ( *(_DWORD *)(v17 + 96) == 1 )
      {
        v62 = 0;
        while ( 1 )
        {
          v18 = JetAttachDatabase2W(*v8, *(JET_PCWSTR *)(*((_QWORD *)this + 5) + 112LL), 0, 0x10u);
          v19 = v62;
          Database2W = v18;
          if ( v62 >= 2 )
            break;
          switch ( v18 )
          {
            case 0:
              goto LABEL_79;
            case -529:
            case -1092:
            case -1808:
              goto LABEL_67;
            case 1007:
              goto LABEL_79;
            case -1008:
            case -505:
            case -1202:
              goto LABEL_67;
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_DSd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              84,
              (unsigned int)&WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
              v62,
              *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
              v18);
            v19 = v62;
          }
          v21 = *((_QWORD *)this + 5);
          v62 = v19 + 1;
          *(_BYTE *)(*(_QWORD *)v21 + 163LL) = 1;
          v22 = TieringJetDatabase::RestoreHeatBackupFileByNumber(*((TieringJetDatabase **)this + 5), v19 + 1);
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            WPP_SF_DDS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              85,
              (unsigned int)&WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
              v62,
              v22,
              *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
            v23 = WPP_GLOBAL_Control;
          }
          if ( v62 > 2 )
            goto LABEL_80;
          v8 = (JET_SESID *)((char *)this + 8);
        }
        if ( !v18 || v18 == 1007 )
        {
LABEL_71:
          v23 = WPP_GLOBAL_Control;
          goto LABEL_72;
        }
LABEL_67:
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            86,
            (unsigned int)&WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
            *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
            v18);
          v19 = v62;
          goto LABEL_71;
        }
LABEL_72:
        if ( v19 != 2 )
        {
LABEL_80:
          if ( Database2W != -1811 && Database2W != -1203 )
          {
            if ( Database2W && Database2W != -550 && Database2W != 1007 )
            {
              if ( Database2W == -529 || Database2W == -1092 || Database2W == -1808 )
              {
                v7 = ATL::AtlHresultFromWin32(0x70u);
              }
              else if ( Database2W == -1011 )
              {
                v7 = -2147024882;
              }
              else
              {
                v39 = -Database2W;
                if ( Database2W > 0 )
                  LOWORD(v39) = Database2W;
                v7 = Database2W & 0x8E5E0000 | (unsigned __int16)v39 | 0xE5E0000;
              }
              v64 = v7;
              if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 1) != 0 && *((_BYTE *)v23 + 25) >= 2u )
              {
                v40 = 97;
LABEL_137:
                v41 = *((_QWORD *)this + 5);
LABEL_138:
                WPP_SF_Sd(
                  v23[2],
                  v40,
                  (unsigned int)&WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
                  *(_QWORD *)(v41 + 112),
                  Database2W);
LABEL_139:
                v23 = WPP_GLOBAL_Control;
                goto LABEL_140;
              }
              goto LABEL_140;
            }
            v38 = v59[0];
            goto LABEL_144;
          }
          goto LABEL_108;
        }
        if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 1) != 0 && *((_BYTE *)v23 + 25) >= 2u )
          WPP_SF_S(
            v23[2],
            87,
            &WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
            *(_QWORD *)(**((_QWORD **)this + 5) + 600LL));
        CTieredVolume::TryDeleteMoveCopyFilesForRecoveryOrBackup(
          **((_QWORD **)this + 5),
          *(_QWORD *)(**((_QWORD **)this + 5) + 600LL),
          0,
          0,
          L"*.*");
        goto LABEL_78;
      }
      v24 = *(const WCHAR **)(v17 + 112);
      v25 = *v8;
      if ( *(_DWORD *)(v17 + 96) == 3 )
      {
        Database2W = JetAttachDatabase2W(v25, v24, 0, 0x10u);
        if ( Database2W >= 0 )
          goto LABEL_79;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            88,
            &WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
            *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
        }
        DeleteFileW(*(LPCWSTR *)(*((_QWORD *)this + 5) + 112LL));
LABEL_78:
        Database2W = -1811;
LABEL_79:
        v23 = WPP_GLOBAL_Control;
        goto LABEL_80;
      }
      v26 = JetAttachDatabase2W(v25, v24, 0, 0x10u);
      Database2W = v26;
      if ( v26 == -550 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            89,
            &WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
            *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
        }
        v27 = JetOpenDatabaseW(
                *((_QWORD *)this + 1),
                *(JET_PCWSTR *)(*((_QWORD *)this + 5) + 112LL),
                0,
                (JET_DBID *)this + 4,
                0);
        Database2W = v27;
        if ( v27 != -1203 )
        {
          if ( !v27 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                91,
                &WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
                *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
            }
            v38 = 1;
            LOBYTE(v59[0]) = 1;
LABEL_144:
            if ( v38 )
            {
LABEL_175:
              v49 = v60;
              do
              {
                TieringJetSession::OpenJetTableInternal(
                  this,
                  &v61,
                  v49,
                  *((_DWORD *)this + 4),
                  *((_QWORD *)this + 1),
                  (unsigned __int64 *)this + 3);
                v41 = *((_QWORD *)this + 5);
              }
              while ( *(_BYTE *)(v41 + 148) );
              v16 = SRWLock;
              switch ( Database2W )
              {
                case 0:
                  if ( SRWLock )
                    ReleaseSRWLockExclusive(SRWLock);
                  v52 = *((_QWORD *)this + 3);
                  v53 = *((_QWORD *)this + 1);
                  if ( (unsigned int)(*(_DWORD *)(*((_QWORD *)this + 5) + 96LL) - 2) <= 1 )
                  {
                    v56 = JetSetCurrentIndexW(v53, v52, L"ByFileId");
                    v54 = v60;
                  }
                  else
                  {
                    v54 = v60;
                    if ( v60 )
                      v55 = 0;
                    else
                      v55 = L"ByFileIdOffset";
                    v56 = JetSetCurrentIndexW(v53, v52, v55);
                  }
                  v57 = v56;
                  switch ( v56 )
                  {
                    case 0:
                      v7 = 0;
                      *((_BYTE *)this + 33) = v54;
                      v43 = 0;
                      v64 = 0;
                      v42 = 0;
                      *(_BYTE *)this = 1;
                      v61 = 0;
                      *((_BYTE *)this + 32) = 0;
                      goto LABEL_229;
                    case -529:
                    case -1092:
                    case -1808:
                      v7 = ATL::AtlHresultFromWin32(0x70u);
                      break;
                    case -1011:
                      v7 = -2147024882;
                      break;
                    default:
                      v58 = -v56;
                      if ( v57 > 0 )
                        LOWORD(v58) = v57;
                      v7 = v57 & 0x8E5E0000 | (unsigned __int16)v58 | 0xE5E0000;
                      break;
                  }
                  v64 = v7;
                  v23 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_Sd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      101,
                      (unsigned int)&WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
                      *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
                      v57);
                    goto LABEL_142;
                  }
LABEL_227:
                  v42 = v59[0];
                  v43 = 1;
LABEL_230:
                  if ( v61 )
                  {
                    if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 1) != 0 && *((_BYTE *)v23 + 25) >= 4u )
                      WPP_SF_S(
                        v23[2],
                        102,
                        &WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
                        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
                    JetCloseTable(*((_QWORD *)this + 1), *((_QWORD *)this + 3));
                    v23 = WPP_GLOBAL_Control;
                  }
                  if ( v42 )
                  {
                    if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 1) != 0 && *((_BYTE *)v23 + 25) >= 4u )
                      WPP_SF_S(
                        v23[2],
                        103,
                        &WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
                        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
                    JetCloseDatabase(*((_QWORD *)this + 1), *((_DWORD *)this + 4), 0);
                    v23 = WPP_GLOBAL_Control;
                  }
                  if ( v43 )
                  {
                    if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 1) != 0 && *((_BYTE *)v23 + 25) >= 4u )
                      WPP_SF_S(
                        v23[2],
                        104,
                        &WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
                        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
                    JetEndSession(*((_QWORD *)this + 1), 0);
                  }
                  goto LABEL_38;
                case -529:
                case -1092:
                case -1808:
                  v7 = ATL::AtlHresultFromWin32(0x70u);
                  break;
                case -1011:
                  v7 = -2147024882;
                  break;
                default:
                  v51 = -Database2W;
                  if ( Database2W > 0 )
                    LOWORD(v51) = Database2W;
                  v7 = Database2W & 0x8E5E0000 | (unsigned __int16)v51 | 0xE5E0000;
                  break;
              }
              v64 = v7;
              v23 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v40 = 100;
                goto LABEL_138;
              }
              goto LABEL_140;
            }
            v44 = JetOpenDatabaseW(
                    *((_QWORD *)this + 1),
                    *(JET_PCWSTR *)(*((_QWORD *)this + 5) + 112LL),
                    0,
                    (JET_DBID *)this + 4,
                    0);
            v45 = v44;
            if ( v44 )
            {
              if ( v44 == -529 || v44 == -1092 || v44 == -1808 )
              {
                v7 = ATL::AtlHresultFromWin32(0x70u);
              }
              else if ( v44 == -1011 )
              {
                v7 = -2147024882;
              }
              else
              {
                v46 = -v44;
                if ( v46 < 0 )
                  LOWORD(v46) = v45;
                v7 = v45 & 0x8E5E0000 | (unsigned __int16)v46 | 0xE5E0000;
              }
              v64 = v7;
              v23 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  98,
                  (unsigned int)&WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
                  *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
                  v45);
                goto LABEL_139;
              }
              goto LABEL_140;
            }
            v47 = WPP_GLOBAL_Control;
            Database2W = 0;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
            {
LABEL_174:
              LOBYTE(v59[0]) = 1;
              goto LABEL_175;
            }
            v48 = 99;
LABEL_173:
            WPP_SF_S(
              v47[2],
              v48,
              &WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
              *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
            goto LABEL_174;
          }
          goto LABEL_79;
        }
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_112;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
LABEL_108:
          if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 1) != 0 && *((_BYTE *)v23 + 25) >= 5u )
            WPP_SF_S(
              v23[2],
              93,
              &WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
              *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
LABEL_112:
          v28 = *((_QWORD *)this + 5);
          v29 = (JET_DBID *)((char *)this + 16);
          v30 = *((_QWORD *)this + 1);
          v31 = *(_DWORD *)(v28 + 96);
          v32 = *(const WCHAR **)(v28 + 112);
          if ( ((v31 - 1) & 0xFFFFFFFD) != 0 )
          {
            Database2W = JetCreateDatabase2W(v30, v32, 0, v29, 0x200u);
            if ( !Database2W )
            {
              v34 = (__int64 *)*((_QWORD *)this + 5);
              if ( *((_DWORD *)v34 + 24) == 2 )
              {
                if ( (Microsoft_Windows_Storage_TieringEnableBits & 2) != 0 )
                {
                  v35 = *v34;
                  v68 = 2;
                  v71 = 0;
                  v36 = *(_QWORD *)(v35 + 704);
                  LODWORD(v35) = *(_WORD *)(v35 + 696) >> 1;
                  v59[0] = v35;
                  v70 = 2 * v35;
                  v69 = v36;
                  v67 = v59;
                  v37 = McGenEventWrite_EventWriteTransfer(v59, TIERENGINE_EVENT_PINNED_DB_CREATED, v33, 3, v66);
                }
                else
                {
                  v37 = 0;
                }
                v47 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                  goto LABEL_174;
                if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
                  goto LABEL_169;
                WPP_SF_DS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  94,
                  (unsigned int)&WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
                  v37,
                  *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
              }
LABEL_168:
              v47 = WPP_GLOBAL_Control;
LABEL_169:
              if ( v47 == &WPP_GLOBAL_Control || (*((_BYTE *)v47 + 28) & 1) == 0 || *((_BYTE *)v47 + 25) < 4u )
                goto LABEL_174;
              v48 = 96;
              goto LABEL_173;
            }
          }
          else
          {
            Database2W = JetCreateDatabase2W(v30, v32, 0, v29, 0x208u);
            if ( !Database2W )
              goto LABEL_168;
          }
          if ( Database2W == -529 || Database2W == -1092 || Database2W == -1808 )
          {
            v7 = ATL::AtlHresultFromWin32(0x70u);
          }
          else if ( Database2W == -1011 )
          {
            v7 = -2147024882;
          }
          else
          {
            v50 = -Database2W;
            if ( Database2W > 0 )
              LOWORD(v50) = Database2W;
            v7 = Database2W & 0x8E5E0000 | (unsigned __int16)v50 | 0xE5E0000;
          }
          v64 = v7;
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v40 = 95;
            goto LABEL_137;
          }
LABEL_140:
          if ( v16 )
          {
            ReleaseSRWLockExclusive(v16);
LABEL_142:
            v42 = v59[0];
            v43 = 1;
LABEL_229:
            v23 = WPP_GLOBAL_Control;
            goto LABEL_230;
          }
          goto LABEL_227;
        }
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          90,
          &WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
          *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
      }
      else
      {
        if ( v26 != -1206 )
          goto LABEL_79;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            92,
            &WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
            *(_QWORD *)(**((_QWORD **)this + 5) + 624LL));
        }
        CTieredVolume::TryDeleteMoveCopyFilesForRecoveryOrBackup(
          **((_QWORD **)this + 5),
          *(_QWORD *)(**((_QWORD **)this + 5) + 624LL),
          0,
          0,
          L"*.*");
      }
      v23 = WPP_GLOBAL_Control;
      goto LABEL_108;
    }
    if ( a2 )
    {
      *(_BYTE *)(v6 + 40) = 0;
      v11 = *((_QWORD *)this + 5);
      *((_QWORD *)this + 1) = *(_QWORD *)(v11 + 48);
      *((_DWORD *)this + 4) = *(_DWORD *)(v11 + 56);
      v12 = *(_QWORD *)(v11 + 64);
    }
    else
    {
      *(_BYTE *)(v6 + 8) = 0;
      v11 = *((_QWORD *)this + 5);
      *((_QWORD *)this + 1) = *(_QWORD *)(v11 + 16);
      *((_DWORD *)this + 4) = *(_DWORD *)(v11 + 24);
      v12 = *(_QWORD *)(v11 + 32);
    }
    *((_QWORD *)this + 3) = v12;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        81,
        &WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
        *(_QWORD *)(v11 + 112));
    }
    *(_BYTE *)this = 1;
    *((_BYTE *)this + 33) = a2;
    *((_BYTE *)this + 32) = 1;
    v64 = 0;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
LABEL_29:
    CHResultImp::~CHResultImp((CHResultImp *)v63);
    return 0;
  }
  v7 = -2147220993;
  v64 = -2147220993;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      80,
      (unsigned int)&WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
      *(_QWORD *)(v6 + 112),
      255);
  }
  if ( v5 )
    ReleaseSRWLockExclusive(v5);
LABEL_38:
  CHResultImp::~CHResultImp((CHResultImp *)v63);
  return v7;
}

```

## disassembly

```asm
0x14001b328  mov     [rsp-8+arg_10], rbx
0x14001b32d  push    rbp
0x14001b32e  push    rsi
0x14001b32f  push    rdi
0x14001b330  push    r12
0x14001b332  push    r13
0x14001b334  push    r14
0x14001b336  push    r15
0x14001b338  lea     rbp, [rsp-27h]
0x14001b33d  sub     rsp, 90h
0x14001b344  mov     rax, cs:__security_cookie
0x14001b34b  xor     rax, rsp
0x14001b34e  mov     [rbp+57h+var_38], rax
0x14001b352  mov     rax, gs:58h
0x14001b35b  mov     rsi, rcx
0x14001b35e  mov     dil, dl
0x14001b361  mov     [rbp+57h+var_87], dl
0x14001b364  mov     edx, 8
0x14001b369  mov     rcx, [rax]
0x14001b36c  lea     rax, aTieringjetsess; "TieringJetSession::OpenJetTable"
0x14001b373  mov     [rdx+rcx], rax
0x14001b377  lea     rcx, [rbp+57h+var_80]; this
0x14001b37b  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14001b380  xor     r14d, r14d
0x14001b383  mov     [rbp+57h+var_86], r14b
0x14001b387  cmp     [rsi], r14b
0x14001b38a  jnz     loc_14001B525
0x14001b390  mov     rax, [rsi+28h]
0x14001b394  mov     rbx, [rax]
0x14001b397  add     rbx, 18h
0x14001b39b  mov     rcx, rbx; SRWLock
0x14001b39e  call    cs:__imp_AcquireSRWLockExclusive
0x14001b3a4  mov     rax, [rsi+28h]
0x14001b3a8  cmp     [rax+4Dh], r14b
0x14001b3ac  jz      short loc_14001B40C
0x14001b3ae  mov     edi, 800401FFh
0x14001b3b3  mov     [rbp+57h+var_78], edi
0x14001b3b6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b3bd  lea     r12, WPP_GLOBAL_Control
0x14001b3c4  cmp     rcx, r12
0x14001b3c7  jz      short loc_14001B3F5
0x14001b3c9  lea     r15d, [r14+1]
0x14001b3cd  test    [rcx+1Ch], r15b
0x14001b3d1  jz      short loc_14001B3F5
0x14001b3d3  cmp     byte ptr [rcx+19h], 2
0x14001b3d7  jb      short loc_14001B3F5
0x14001b3d9  mov     r9, [rax+70h]
0x14001b3dd  lea     edx, [r14+50h]
0x14001b3e1  mov     rcx, [rcx+10h]
0x14001b3e5  lea     r8, WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids
0x14001b3ec  mov     [rsp+0C0h+grbit], edi
0x14001b3f0  call    WPP_SF_Sd
0x14001b3f5  test    rbx, rbx
0x14001b3f8  jz      loc_14001B5C7
0x14001b3fe  mov     rcx, rbx; SRWLock
0x14001b401  call    cs:__imp_ReleaseSRWLockExclusive
0x14001b407  jmp     loc_14001B5C7
0x14001b40c  test    dil, dil
0x14001b40f  jz      short loc_14001B484
0x14001b411  cmp     [rax+28h], r14b
0x14001b415  jnz     short loc_14001B48A
0x14001b417  test    rbx, rbx
0x14001b41a  jz      short loc_14001B425
0x14001b41c  mov     rcx, rbx; SRWLock
0x14001b41f  call    cs:__imp_ReleaseSRWLockExclusive
0x14001b425  mov     rax, [rsi+28h]
0x14001b429  lea     r14, [rsi+8]
0x14001b42d  xor     r9d, r9d; szPassword
0x14001b430  xor     r8d, r8d; szUserName
0x14001b433  mov     rdx, r14; psesid
0x14001b436  mov     rcx, [rax+68h]
0x14001b43a  mov     rcx, [rcx]; instance
0x14001b43d  call    cs:__imp_JetBeginSessionW
0x14001b443  mov     r8d, eax
0x14001b446  test    eax, eax
0x14001b448  jz      loc_14001B5D7
0x14001b44e  cmp     eax, 0FFFFFDEFh
0x14001b453  jz      loc_14001B572
0x14001b459  cmp     eax, 0FFFFFBBCh
0x14001b45e  jz      loc_14001B572
0x14001b464  cmp     eax, 0FFFFF8F0h
0x14001b469  jz      loc_14001B572
0x14001b46f  cmp     eax, 0FFFFFC0Dh
0x14001b474  jnz     loc_14001B557
0x14001b47a  mov     edi, 8007000Eh
0x14001b47f  jmp     loc_14001B57E
0x14001b484  cmp     [rax+8], r14b
0x14001b488  jz      short loc_14001B417
0x14001b48a  test    dil, dil
0x14001b48d  jz      short loc_14001B4AC
0x14001b48f  mov     [rax+28h], r14b
0x14001b493  mov     r9, [rsi+28h]
0x14001b497  mov     rax, [r9+30h]
0x14001b49b  mov     [rsi+8], rax
0x14001b49f  mov     eax, [r9+38h]
0x14001b4a3  mov     [rsi+10h], eax
0x14001b4a6  mov     rax, [r9+40h]
0x14001b4aa  jmp     short loc_14001B4C7
0x14001b4ac  mov     [rax+8], r14b
0x14001b4b0  mov     r9, [rsi+28h]
0x14001b4b4  mov     rax, [r9+10h]
0x14001b4b8  mov     [rsi+8], rax
0x14001b4bc  mov     eax, [r9+18h]
0x14001b4c0  mov     [rsi+10h], eax
0x14001b4c3  mov     rax, [r9+20h]
0x14001b4c7  mov     [rsi+18h], rax
0x14001b4cb  lea     r12, WPP_GLOBAL_Control
0x14001b4d2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b4d9  mov     r15d, 1
0x14001b4df  cmp     rcx, r12
0x14001b4e2  jz      short loc_14001B508
0x14001b4e4  test    [rcx+1Ch], r15b
0x14001b4e8  jz      short loc_14001B508
0x14001b4ea  cmp     byte ptr [rcx+19h], 4
0x14001b4ee  jb      short loc_14001B508
0x14001b4f0  mov     r9, [r9+70h]
0x14001b4f4  lea     edx, [r15+50h]
0x14001b4f8  mov     rcx, [rcx+10h]
0x14001b4fc  lea     r8, WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids
0x14001b503  call    WPP_SF_S
0x14001b508  mov     [rsi], r15b
0x14001b50b  mov     [rsi+21h], dil
0x14001b50f  mov     [rsi+20h], r15b
0x14001b513  mov     [rbp+57h+var_78], r14d
0x14001b517  test    rbx, rbx
0x14001b51a  jz      short loc_14001B525
0x14001b51c  mov     rcx, rbx; SRWLock
0x14001b51f  call    cs:__imp_ReleaseSRWLockExclusive
0x14001b525  lea     rcx, [rbp+57h+var_80]; this
0x14001b529  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x14001b52e  xor     eax, eax
0x14001b530  mov     rcx, [rbp+57h+var_38]
0x14001b534  xor     rcx, rsp; StackCookie
0x14001b537  call    __security_check_cookie
0x14001b53c  mov     rbx, [rsp+0C0h+arg_10]
0x14001b544  add     rsp, 90h
0x14001b54b  pop     r15
0x14001b54d  pop     r14
0x14001b54f  pop     r13
0x14001b551  pop     r12
0x14001b553  pop     rdi
0x14001b554  pop     rsi
0x14001b555  pop     rbp
0x14001b556  retn
0x14001b557  neg     eax
0x14001b559  cmovs   eax, r8d
0x14001b55d  movzx   edi, ax
0x14001b560  mov     eax, r8d
0x14001b563  and     eax, 8E5E0000h
0x14001b568  or      edi, eax
0x14001b56a  or      edi, 0E5E0000h
0x14001b570  jmp     short loc_14001B57E
0x14001b572  mov     ecx, 70h ; 'p'; unsigned int
0x14001b577  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14001b57c  mov     edi, eax
0x14001b57e  mov     [rbp+57h+var_78], edi
0x14001b581  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b588  lea     r12, WPP_GLOBAL_Control
0x14001b58f  cmp     rcx, r12
0x14001b592  jz      short loc_14001B5C7
0x14001b594  mov     r15d, 1
0x14001b59a  test    [rcx+1Ch], r15b
0x14001b59e  jz      short loc_14001B5C7
0x14001b5a0  cmp     byte ptr [rcx+19h], 2
0x14001b5a4  jb      short loc_14001B5C7
0x14001b5a6  mov     r9, [rsi+28h]
0x14001b5aa  lea     edx, [r15+51h]
0x14001b5ae  mov     rcx, [rcx+10h]
0x14001b5b2  mov     [rsp+0C0h+grbit], r8d
0x14001b5b7  lea     r8, WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids
0x14001b5be  mov     r9, [r9+70h]
0x14001b5c2  call    WPP_SF_Sd
0x14001b5c7  lea     rcx, [rbp+57h+var_80]; this
0x14001b5cb  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x14001b5d0  mov     eax, edi
0x14001b5d2  jmp     loc_14001B530
0x14001b5d7  mov     rax, [rsi+28h]
0x14001b5db  mov     r15d, 1
0x14001b5e1  mov     byte ptr [rbp+57h+var_90], 0
0x14001b5e5  mov     rbx, [rax]
0x14001b5e8  add     rbx, 18h
0x14001b5ec  mov     rcx, rbx; SRWLock
0x14001b5ef  mov     [rbp+57h+SRWLock], rbx
0x14001b5f3  call    cs:__imp_AcquireSRWLockExclusive
0x14001b5f9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b600  lea     r12, WPP_GLOBAL_Control
0x14001b607  lea     r13, WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids
0x14001b60e  cmp     rcx, r12
0x14001b611  jz      short loc_14001B637
0x14001b613  test    [rcx+1Ch], r15b
0x14001b617  jz      short loc_14001B637
0x14001b619  cmp     byte ptr [rcx+19h], 5
0x14001b61d  jb      short loc_14001B637
0x14001b61f  mov     r9, [rsi+28h]
0x14001b623  lea     edx, [r15+52h]
0x14001b627  mov     rcx, [rcx+10h]
0x14001b62b  mov     r8, r13
0x14001b62e  mov     r9, [r9+70h]
0x14001b632  call    WPP_SF_S
0x14001b637  mov     rax, [rsi+28h]
0x14001b63b  mov     edi, 2
0x14001b640  cmp     [rax+60h], r15d
0x14001b644  jnz     loc_14001B8C0
0x14001b64a  mov     [rbp+57h+var_84], 0
0x14001b651  jmp     short loc_14001B657
0x14001b653  lea     r14, [rsi+8]
0x14001b657  mov     rdx, [rsi+28h]
0x14001b65b  mov     r9d, 10h; grbit
0x14001b661  mov     rcx, [r14]; sesid
0x14001b664  xor     r8d, r8d; cpgDatabaseSizeMax
0x14001b667  mov     rdx, [rdx+70h]; szFilename
0x14001b66b  call    cs:__imp_JetAttachDatabase2W
0x14001b671  mov     r8d, [rbp+57h+var_84]
0x14001b675  mov     r14d, eax
0x14001b678  cmp     r8d, edi
0x14001b67b  jnb     loc_14001B78F
0x14001b681  test    eax, eax
0x14001b683  jz      loc_14001B83E
0x14001b689  cmp     eax, 0FFFFFDEFh
0x14001b68e  jz      loc_14001B79D
0x14001b694  cmp     eax, 0FFFFFBBCh
0x14001b699  jz      loc_14001B79D
0x14001b69f  cmp     eax, 0FFFFF8F0h
0x14001b6a4  jz      loc_14001B79D
0x14001b6aa  cmp     eax, 3EFh
0x14001b6af  jz      loc_14001B83E
0x14001b6b5  cmp     eax, 0FFFFFC10h
0x14001b6ba  jz      loc_14001B79D
0x14001b6c0  cmp     eax, 0FFFFFE07h
0x14001b6c5  jz      loc_14001B79D
0x14001b6cb  cmp     eax, 0FFFFFB4Eh
0x14001b6d0  jz      loc_14001B79D
0x14001b6d6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b6dd  cmp     rcx, r12
0x14001b6e0  jz      short loc_14001B718
0x14001b6e2  test    [rcx+1Ch], r15b
0x14001b6e6  jz      short loc_14001B718
0x14001b6e8  cmp     [rcx+19h], dil
0x14001b6ec  jb      short loc_14001B718
0x14001b6ee  mov     rax, [rsi+28h]
0x14001b6f2  mov     r9d, r8d
0x14001b6f5  mov     rcx, [rcx+10h]
0x14001b6f9  mov     edx, 54h ; 'T'
0x14001b6fe  mov     dword ptr [rsp+0C0h+var_98], r14d
0x14001b703  mov     r8, r13
0x14001b706  mov     rax, [rax+70h]
0x14001b70a  mov     qword ptr [rsp+0C0h+grbit], rax
0x14001b70f  call    WPP_SF_DSd
0x14001b714  mov     r8d, [rbp+57h+var_84]
0x14001b718  mov     rax, [rsi+28h]
0x14001b71c  add     r8d, r15d
0x14001b71f  mov     edx, r8d; unsigned int
0x14001b722  mov     [rbp+57h+var_84], r8d
0x14001b726  mov     rcx, [rax]
0x14001b729  mov     [rcx+0A3h], r15b
0x14001b730  mov     rcx, [rsi+28h]; this
0x14001b734  call    ?RestoreHeatBackupFileByNumber@TieringJetDatabase@@QEAAJK@Z; TieringJetDatabase::RestoreHeatBackupFileByNumber(ulong)
0x14001b739  mov     ecx, eax
0x14001b73b  mov     r10, cs:WPP_GLOBAL_Control
0x14001b742  cmp     r10, r12
0x14001b745  jz      short loc_14001B781
0x14001b747  test    [r10+1Ch], r15b
0x14001b74b  jz      short loc_14001B781
0x14001b74d  cmp     byte ptr [r10+19h], 3
0x14001b752  jb      short loc_14001B781
0x14001b754  mov     rax, [rsi+28h]
0x14001b758  mov     edx, 55h ; 'U'
0x14001b75d  mov     r9d, [rbp+57h+var_84]
0x14001b761  mov     r8, r13
0x14001b764  mov     rax, [rax+70h]
0x14001b768  mov     [rsp+0C0h+var_98], rax
0x14001b76d  mov     [rsp+0C0h+grbit], ecx
0x14001b771  mov     rcx, [r10+10h]
0x14001b775  call    WPP_SF_DDS
0x14001b77a  mov     r10, cs:WPP_GLOBAL_Control
0x14001b781  cmp     [rbp+57h+var_84], edi
0x14001b784  jbe     loc_14001B653
0x14001b78a  jmp     loc_14001B845
0x14001b78f  test    r14d, r14d
0x14001b792  jz      short loc_14001B7D7
0x14001b794  cmp     r14d, 3EFh
0x14001b79b  jz      short loc_14001B7D7
0x14001b79d  mov     r10, cs:WPP_GLOBAL_Control
0x14001b7a4  cmp     r10, r12
0x14001b7a7  jz      short loc_14001B7DE
0x14001b7a9  test    [r10+1Ch], r15b
0x14001b7ad  jz      short loc_14001B7DE
0x14001b7af  cmp     [r10+19h], dil
0x14001b7b3  jb      short loc_14001B7DE
0x14001b7b5  mov     r9, [rsi+28h]
0x14001b7b9  mov     edx, 56h ; 'V'
0x14001b7be  mov     rcx, [r10+10h]
0x14001b7c2  mov     r8, r13
0x14001b7c5  mov     [rsp+0C0h+grbit], r14d
0x14001b7ca  mov     r9, [r9+70h]
0x14001b7ce  call    WPP_SF_Sd
0x14001b7d3  mov     r8d, [rbp+57h+var_84]
0x14001b7d7  mov     r10, cs:WPP_GLOBAL_Control
0x14001b7de  cmp     r8d, edi
0x14001b7e1  jnz     short loc_14001B845
  ... truncated ...
```
