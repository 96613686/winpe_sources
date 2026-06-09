# CTieredVolume::Processing_Pass1(void *,TieringPinnedSession *,TieringHeatSession *,unsigned __int64,unsigned __int64 *,unsigned __int64 *)

- ea: `0x14002fd94`
- end: `0x140030e08`
- name: `?Processing_Pass1@CTieredVolume@@AEAAJPEAXPEAVTieringPinnedSession@@PEAVTieringHeatSession@@_KPEA_K4@Z`
- size: `4212`
- prototype: `__int64 __fastcall(CTieredVolume *this, void *, struct TieringPinnedSession *, struct TieringHeatSession *, unsigned __int64, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14002eef0`

## callees

- `0x140002db0`
- `0x140004a68`
- `0x140004ef0`
- `0x140005420`
- `0x140009a04`
- `0x140009c08`
- `0x140017e78`
- `0x1400185a0`
- `0x14001cd80`
- `0x14001f744`
- `0x140020c6c`
- `0x140020ecc`
- `0x140021018`
- `0x1400280bc`
- `0x14002b15c`
- `0x14002d844`
- `0x14002fd94`
- `0x14003506c`
- `0x140035d68`
- `0x140036288`
- `0x14003fbb0`

## import_xrefs

- `msvcrt!free` at `0x14002fec5`
- `msvcrt!free` at `0x140030d71`
- `msvcrt!free` at `0x14002fec5`
- `msvcrt!free` at `0x140030d71`
- `ntdll!RtlCompareMemory` at `0x14003017d`
- `ntdll!RtlCompareMemory` at `0x14003017d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14002fe64`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14002fe7e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14002fe64`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14002fe7e`
- `ESENT!JetRollback` at `0x14003005a`
- `ESENT!JetRollback` at `0x14003015c`
- `ESENT!JetRollback` at `0x140030351`
- `ESENT!JetRollback` at `0x140030427`
- `ESENT!JetRollback` at `0x1400308ad`
- `ESENT!JetRollback` at `0x140030bd9`
- `ESENT!JetRollback` at `0x14003005a`
- `ESENT!JetRollback` at `0x14003015c`
- `ESENT!JetRollback` at `0x140030351`
- `ESENT!JetRollback` at `0x140030427`
- `ESENT!JetRollback` at `0x1400308ad`
- `ESENT!JetRollback` at `0x140030bd9`
- `ESENT!JetBeginTransaction` at `0x14002ff43`
- `ESENT!JetBeginTransaction` at `0x14002ff43`
- `ESENT!JetCommitTransaction` at `0x14003048f`
- `ESENT!JetCommitTransaction` at `0x140030adb`
- `ESENT!JetCommitTransaction` at `0x14003048f`
- `ESENT!JetCommitTransaction` at `0x140030adb`
- `ESENT!JetDelete` at `0x140030378`
- `ESENT!JetDelete` at `0x140030378`
- `ESENT!JetPrepareUpdate` at `0x14003077a`
- `ESENT!JetPrepareUpdate` at `0x140030798`
- `ESENT!JetPrepareUpdate` at `0x1400307ac`
- `ESENT!JetPrepareUpdate` at `0x14003098b`
- `ESENT!JetPrepareUpdate` at `0x140030a9e`
- `ESENT!JetPrepareUpdate` at `0x140030ba3`
- `ESENT!JetPrepareUpdate` at `0x14003077a`
- `ESENT!JetPrepareUpdate` at `0x140030798`
- `ESENT!JetPrepareUpdate` at `0x1400307ac`
- `ESENT!JetPrepareUpdate` at `0x14003098b`
- `ESENT!JetPrepareUpdate` at `0x140030a9e`
- `ESENT!JetPrepareUpdate` at `0x140030ba3`
- `ESENT!JetUpdate` at `0x1400309d6`
- `ESENT!JetUpdate` at `0x1400309d6`
- `ESENT!JetMove` at `0x14002fee0`
- `ESENT!JetMove` at `0x14002fee0`

## pseudocode

```c
__int64 __fastcall CTieredVolume::Processing_Pass1(
        CTieredVolume *this,
        void *a2,
        struct TieringPinnedSession *a3,
        struct TieringHeatSession *a4,
        unsigned __int64 a5,
        unsigned __int64 *a6,
        unsigned __int64 *a7)
{
  PVOID ThreadLocalStoragePointer; // rax
  struct _FILE_PLACEMENT *v10; // rsi
  int v11; // edi
  int v12; // r12d
  int updated; // ebx
  int v14; // r14d
  _QWORD *v15; // r10
  __int64 v16; // rax
  unsigned int v17; // eax
  __int64 v18; // r9
  JET_SESID v19; // rcx
  JET_ERR v20; // eax
  JET_ERR v21; // r8d
  int v22; // eax
  int v23; // eax
  JET_ERR CurrentPinnedRecord; // eax
  JET_ERR v25; // r8d
  int v26; // r12d
  int v27; // eax
  _BYTE *v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rdx
  int FileExtentsByFileId; // esi
  __int64 v32; // r8
  unsigned __int64 v33; // r14
  unsigned __int64 v34; // rbx
  unsigned __int8 v35; // dl
  _QWORD *v36; // rcx
  __int64 v37; // rdx
  JET_ERR v38; // eax
  int v39; // esi
  int v40; // eax
  JET_ERR v41; // eax
  JET_ERR v42; // r8d
  int v43; // eax
  int v44; // eax
  int v45; // eax
  unsigned __int64 v46; // rcx
  unsigned __int64 v47; // rcx
  int v48; // r10d
  char v49; // dl
  unsigned int v50; // ebx
  struct _FILE_PLACEMENT *v51; // r9
  char v52; // cl
  unsigned __int8 v53; // al
  JET_SESID v54; // rcx
  JET_ERR v55; // r8d
  int v56; // eax
  _BYTE *v57; // rcx
  __int64 v58; // rdx
  int v59; // eax
  int v60; // r8d
  int v61; // eax
  JET_ERR v62; // eax
  JET_ERR v63; // r8d
  int v64; // eax
  JET_ERR v65; // eax
  JET_ERR v66; // r8d
  int v67; // eax
  int v68; // eax
  int v70; // [rsp+28h] [rbp-C9h]
  void **v71; // [rsp+58h] [rbp-99h]
  unsigned __int8 v72[4]; // [rsp+60h] [rbp-91h] BYREF
  int v73; // [rsp+64h] [rbp-8Dh]
  int v74; // [rsp+68h] [rbp-89h]
  unsigned __int8 v75; // [rsp+6Ch] [rbp-85h] BYREF
  unsigned __int8 v76[3]; // [rsp+6Dh] [rbp-84h] BYREF
  struct _FILE_PLACEMENT *v77; // [rsp+70h] [rbp-81h] BYREF
  _BYTE v78[8]; // [rsp+78h] [rbp-79h] BYREF
  int v79; // [rsp+80h] [rbp-71h]
  int v80; // [rsp+88h] [rbp-69h] BYREF
  unsigned int v81; // [rsp+8Ch] [rbp-65h] BYREF
  int v82; // [rsp+90h] [rbp-61h] BYREF
  int v83; // [rsp+94h] [rbp-5Dh] BYREF
  TieringHeatSession *v84; // [rsp+98h] [rbp-59h]
  unsigned __int64 v85; // [rsp+A0h] [rbp-51h] BYREF
  unsigned __int64 v86; // [rsp+A8h] [rbp-49h] BYREF
  unsigned __int64 v87; // [rsp+B0h] [rbp-41h] BYREF
  unsigned __int64 *v88; // [rsp+B8h] [rbp-39h]
  unsigned __int64 *v89; // [rsp+C0h] [rbp-31h]
  void *v90; // [rsp+C8h] [rbp-29h]
  __int128 Source1; // [rsp+D0h] [rbp-21h] BYREF

  v88 = a6;
  v89 = a7;
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v84 = a4;
  v90 = a2;
  *(_QWORD *)(*(_QWORD *)ThreadLocalStoragePointer + 8LL) = "CTieredVolume::Processing_Pass1";
  CHResultImp::CHResultImp((CHResultImp *)v78);
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v77 = 0;
  updated = 0;
  v14 = 0x80000000;
  v79 = 0;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 0;
LABEL_2:
  v15 = WPP_GLOBAL_Control;
  while ( 1 )
  {
    if ( *((_BYTE *)this + 165) || *((_BYTE *)this + 166) )
      goto LABEL_276;
    if ( WaitForSingleObject(*((HANDLE *)this + 96), 0) != 258 || WaitForSingleObject(*((HANDLE *)this + 95), 0) != 258 )
      break;
    if ( *((_DWORD *)this + 46) != 3 )
      goto LABEL_280;
    v16 = *((_QWORD *)a3 + 5);
    if ( *(_BYTE *)(v16 + 77) )
    {
      if ( *(_BYTE *)(v16 + 76) )
        goto LABEL_280;
    }
    v83 = 0;
    v80 = 0;
    v82 = 0;
    v81 = 0;
    if ( v10 )
    {
      free(v10);
      v10 = 0;
      v77 = 0;
    }
    v17 = JetMove(*((_QWORD *)a3 + 1), *((_QWORD *)a3 + 3), v14, 0);
    v18 = v17;
    if ( v17 == -1601 || v17 == 1039 || v17 == -1603 )
    {
      updated = 0;
      v79 = 0;
      goto LABEL_280;
    }
    v14 = 1;
    v74 = 1;
    if ( v17 == -1017 )
      goto LABEL_2;
    if ( v17 )
    {
      if ( v17 == -529 || v17 == -1092 || v17 == -1808 )
      {
        updated = ATL::AtlHresultFromWin32(112);
      }
      else if ( v17 == -1011 )
      {
        updated = -2147024882;
      }
      else
      {
        v68 = -v17;
        if ( v68 < 0 )
          LOWORD(v68) = v18;
        updated = v18 & 0x8E5E0000 | (unsigned __int16)v68 | 0xE5E0000;
      }
      v79 = updated;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids, v18);
        v15 = WPP_GLOBAL_Control;
      }
      goto LABEL_281;
    }
    v19 = *((_QWORD *)a3 + 1);
    ++v12;
    v72[0] = 0;
    v73 = v12;
    Source1 = 0;
    v75 = 0;
    v20 = JetBeginTransaction(v19);
    v21 = v20;
    if ( v20 )
    {
      if ( v20 == -529 || v20 == -1092 || v20 == -1808 )
      {
        updated = ATL::AtlHresultFromWin32(112);
      }
      else if ( v20 == -1011 )
      {
        updated = -2147024882;
      }
      else
      {
        v22 = -v20;
        if ( v22 < 0 )
          LOWORD(v22) = v21;
        updated = v21 & 0x8E5E0000 | (unsigned __int16)v22 | 0xE5E0000;
      }
      v79 = updated;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          44,
          (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
          *(_QWORD *)(*((_QWORD *)a3 + 5) + 112LL),
          v21);
        v15 = WPP_GLOBAL_Control;
      }
      v23 = updated;
      if ( v11 < 0 )
        v23 = v11;
      v11 = v23;
    }
    else
    {
      CurrentPinnedRecord = TieringPinnedSession::GetCurrentPinnedRecord(
                              a3,
                              (struct TE_FILE_ID_128 *)&Source1,
                              v72,
                              &v75);
      v25 = CurrentPinnedRecord;
      if ( CurrentPinnedRecord == -1017 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            45,
            &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
            *(_QWORD *)(*((_QWORD *)a3 + 5) + 112LL));
        }
        JetRollback(*((_QWORD *)a3 + 1), 0);
        goto LABEL_2;
      }
      v26 = v11;
      if ( CurrentPinnedRecord )
      {
        if ( CurrentPinnedRecord == -529 || CurrentPinnedRecord == -1092 || CurrentPinnedRecord == -1808 )
        {
          v11 = ATL::AtlHresultFromWin32(112);
        }
        else if ( CurrentPinnedRecord == -1011 )
        {
          v11 = -2147024882;
        }
        else
        {
          v27 = -CurrentPinnedRecord;
          if ( v27 < 0 )
            LOWORD(v27) = v25;
          v11 = v25 & 0x8E5E0000 | (unsigned __int16)v27 | 0xE5E0000;
        }
        updated = v11;
        v79 = v11;
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_DSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            46,
            (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
            v73,
            *(_QWORD *)(*((_QWORD *)a3 + 5) + 112LL),
            v25);
          v28 = WPP_GLOBAL_Control;
        }
        if ( v26 < 0 )
          v11 = v26;
        if ( v28 != (_BYTE *)&WPP_GLOBAL_Control && (v28[28] & 1) != 0 && v28[25] >= 5u )
        {
          v29 = 47;
          goto LABEL_60;
        }
        goto LABEL_61;
      }
      if ( RtlCompareMemory(&Source1, &NullGuid, 0x10u) == 16 )
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v29 = 48;
LABEL_60:
          WPP_SF_S(
            *((_QWORD *)v28 + 2),
            v29,
            &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
            *(_QWORD *)(*((_QWORD *)a3 + 5) + 112LL));
        }
LABEL_61:
        JetRollback(*((_QWORD *)a3 + 1), 0);
        goto LABEL_62;
      }
      v85 = 0;
      v87 = 0;
      v86 = 0;
      FileExtentsByFileId = CTieredVolume::GetFileExtentsByFileId(
                              this,
                              v90,
                              (const struct TE_FILE_ID_128 *)&Source1,
                              &v83,
                              &v80,
                              &v82,
                              &v85,
                              &v86,
                              &v87,
                              &v81,
                              &v77,
                              v71);
      v33 = v85;
      v34 = v86;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v70 = v85;
        WPP_SF_iiiii(*((_QWORD *)WPP_GLOBAL_Control + 2), v30, v32, *((_QWORD *)&Source1 + 1), (_QWORD)Source1);
      }
      if ( FileExtentsByFileId < 0 )
      {
        v35 = v72[0];
        if ( v72[0] == 1 )
          ++*((_DWORD *)this + 59);
        else
          ++*((_DWORD *)this + 61);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_iiZ(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51,
            (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
            DWORD2(Source1),
            Source1,
            (__int64)this + 672);
          v35 = v72[0];
        }
        if ( v11 >= 0 )
          v11 = FileExtentsByFileId;
        updated = TieringHeatSession::UpdateRecordsGivenPlacementList(
                    v84,
                    (const struct TE_FILE_ID_128 *)&Source1,
                    0,
                    0,
                    0,
                    v70,
                    v35 == 1,
                    1);
        v79 = updated;
        v36 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v37 = 52;
          goto LABEL_86;
        }
        goto LABEL_87;
      }
      if ( v80 )
      {
        v38 = JetDelete(*((_QWORD *)a3 + 1), *((_QWORD *)a3 + 3));
        v39 = v38;
        if ( v38 )
        {
          if ( v38 == -529 || v38 == -1092 || v38 == -1808 )
          {
            v11 = ATL::AtlHresultFromWin32(112);
          }
          else if ( v38 == -1011 )
          {
            v11 = -2147024882;
          }
          else
          {
            v40 = -v38;
            if ( v40 < 0 )
              LOWORD(v40) = v39;
            v11 = v39 & 0x8E5E0000 | (unsigned __int16)v40 | 0xE5E0000;
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_iiZd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              53,
              (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
              DWORD2(Source1),
              Source1,
              (__int64)this + 672,
              v39);
          }
          JetRollback(*((_QWORD *)a3 + 1), 0);
          if ( v26 < 0 )
            v11 = v26;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_iiZ(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              54,
              (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
              DWORD2(Source1),
              Source1,
              (__int64)this + 672);
          }
          v41 = JetCommitTransaction(*((_QWORD *)a3 + 1), 1u);
          v42 = v41;
          if ( v41 )
          {
            if ( v41 == -529 || v41 == -1092 || v41 == -1808 )
            {
              v11 = ATL::AtlHresultFromWin32(112);
            }
            else if ( v41 == -1011 )
            {
              v11 = -2147024882;
            }
            else
            {
              v43 = -v41;
              if ( v43 < 0 )
                LOWORD(v43) = v42;
              v11 = v42 & 0x8E5E0000 | (unsigned __int16)v43 | 0xE5E0000;
            }
            updated = v11;
            v79 = v11;
            v36 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_iiSd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                55,
                (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
                DWORD2(Source1),
                Source1,
                *(_QWORD *)(*((_QWORD *)a3 + 5) + 112LL),
                v42);
              v36 = WPP_GLOBAL_Control;
            }
            if ( v26 < 0 )
              v11 = v26;
            if ( v36 != &WPP_GLOBAL_Control && (*((_BYTE *)v36 + 28) & 1) != 0 && *((_BYTE *)v36 + 25) >= 5u )
            {
              v37 = 56;
LABEL_86:
              WPP_SF_S(
                v36[2],
                v37,
                &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
                *(_QWORD *)(*((_QWORD *)a3 + 5) + 112LL));
            }
LABEL_87:
            JetRollback(*((_QWORD *)a3 + 1), 0);
            goto LABEL_88;
          }
          v39 = 0;
        }
        v79 = TieringHeatSession::DeleteRecordsWithGivenFileId(
                (JET_SESID *)v84,
                (const struct TE_FILE_ID_128 *)&Source1,
                0);
        updated = v79;
        if ( v39 )
        {
          if ( v39 == -529 || v39 == -1092 || v39 == -1808 )
          {
            updated = ATL::AtlHresultFromWin32(112);
          }
          else if ( v39 == -1011 )
          {
            updated = -2147024882;
          }
          else
          {
            v44 = -v39;
            if ( v39 > 0 )
              LOWORD(v44) = v39;
            updated = v39 & 0x8E5E0000 | (unsigned __int16)v44 | 0xE5E0000;
          }
          v79 = updated;
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_iiZd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              57,
              (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
              DWORD2(Source1),
              Source1,
              (__int64)this + 672,
              v39);
            v15 = WPP_GLOBAL_Control;
          }
          v45 = updated;
          if ( v11 < 0 )
            v45 = v11;
          v11 = v45;
        }
        else
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_iiS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              58,
              (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
              DWORD2(Source1),
              Source1,
              *(_QWORD *)(*((_QWORD *)a3 + 5) + 112LL));
LABEL_88:
            v10 = v77;
            goto LABEL_89;
          }
        }
        v10 = v77;
        v14 = v74;
        v12 = v73;
      }
      else
      {
        if ( v72[0] == 1 )
        {
          *v88 += v33;
          *v89 += v34 / *((unsigned int *)this + 79);
          v46 = *((unsigned int *)this + 79);
          ++*((_DWORD *)this + 58);
          *((_QWORD *)this + 31) += v33 / v46;
        }
        else
        {
          v47 = *((unsigned int *)this + 79);
          ++*((_DWORD *)this + 60);
          *((_QWORD *)this + 32) += v33 / v47;
        }
        v48 = 0;
        v10 = v77;
        v49 = 1;
        v50 = v81;
        v51 = v77;
        v76[0] = v75;
        if ( v81 )
        {
          while ( v49 )
          {
            if ( v72[0] == 1 )
            {
              v52 = 0;
              if ( *((_BYTE *)v51 + 24) == 16 )
                v52 = v49;
              v49 = v52;
            }
            else if ( *((_BYTE *)v51 + 24) != 32 )
            {
              v49 = 0;
            }
            v51 = (struct _FILE_PLACEMENT *)((char *)v51 + 32);
            if ( ++v48 >= v81 )
            {
              if ( v49 )
                goto LABEL_169;
              break;
            }
          }
          v53 = v75 & 0xFE;
        }
        else
        {
LABEL_169:
          v53 = v75 | 1;
        }
        v54 = *((_QWORD *)a3 + 1);
        v76[0] = v53;
        if ( v53 == v75 )
        {
          JetRollback(v54, 0);
        }
        else
        {
          v55 = JetPrepareUpdate(v54, *((_QWORD *)a3 + 3), 4u);
          if ( v55 == -1607 )
          {
            JetPrepareUpdate(*((_QWORD *)a3 + 1), *((_QWORD *)a3 + 3), 3u);
            v55 = JetPrepareUpdate(*((_QWORD *)a3 + 1), *((_QWORD *)a3 + 3), 4u);
          }
          if ( v55 )
          {
            if ( v55 == -529 || v55 == -1092 || v55 == -1808 )
            {
              v11 = ATL::AtlHresultFromWin32(112);
            }
            else if ( v55 == -1011 )
            {
              v11 = -2147024882;
            }
            else
            {
              v56 = -v55;
              if ( v55 > 0 )
                LOWORD(v56) = v55;
              v11 = v55 & 0x8E5E0000 | (unsigned __int16)v56 | 0xE5E0000;
            }
            updated = v11;
            v79 = v11;
            v57 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_iiSd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                59,
                (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
                DWORD2(Source1),
                Source1,
                *(_QWORD *)(*((_QWORD *)a3 + 5) + 112LL),
                v55);
              v57 = WPP_GLOBAL_Control;
            }
            if ( v26 < 0 )
              v11 = v26;
            if ( v57 != (_BYTE *)&WPP_GLOBAL_Control && (v57[28] & 1) != 0 && v57[25] >= 5u )
            {
              v58 = 60;
              goto LABEL_193;
            }
LABEL_194:
            JetRollback(*((_QWORD *)a3 + 1), 0);
LABEL_89:
            v14 = v74;
LABEL_62:
            v12 = v73;
            goto LABEL_2;
          }
          v59 = TieringPinnedSession::SetCurrentPinnedRecord(a3, 0, 0, v76);
          v60 = v59;
          if ( v59 )
          {
            if ( v59 == -529 || v59 == -1092 || v59 == -1808 )
            {
              v11 = ATL::AtlHresultFromWin32(112);
            }
            else if ( v59 == -1011 )
            {
              v11 = -2147024882;
            }
            else
            {
              v61 = -v59;
              if ( v61 < 0 )
                LOWORD(v61) = v60;
              v11 = v60 & 0x8E5E0000 | (unsigned __int16)v61 | 0xE5E0000;
            }
            updated = v11;
            v79 = v11;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_iiZd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                61,
                (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
                DWORD2(Source1),
                Source1,
                (__int64)this + 672,
                v60);
            }
            if ( v26 < 0 )
              v11 = v26;
            JetPrepareUpdate(*((_QWORD *)a3 + 1), *((_QWORD *)a3 + 3), 3u);
            v57 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
            {
              goto LABEL_194;
            }
            v58 = 62;
            goto LABEL_193;
          }
          v62 = JetUpdate(*((_QWORD *)a3 + 1), *((_QWORD *)a3 + 3), 0, 0, 0);
          v63 = v62;
          if ( v62 )
          {
            if ( v62 == -529 || v62 == -1092 || v62 == -1808 )
            {
              v11 = ATL::AtlHresultFromWin32(112);
            }
            else if ( v62 == -1011 )
            {
              v11 = -2147024882;
            }
            else
            {
              v64 = -v62;
              if ( v64 < 0 )
                LOWORD(v64) = v63;
              v11 = v63 & 0x8E5E0000 | (unsigned __int16)v64 | 0xE5E0000;
            }
            updated = v11;
            v79 = v11;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_iiSd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                63,
                (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
                DWORD2(Source1),
                Source1,
                *(_QWORD *)(*((_QWORD *)a3 + 5) + 112LL),
                v63);
            }
            if ( v26 < 0 )
              v11 = v26;
            JetPrepareUpdate(*((_QWORD *)a3 + 1), *((_QWORD *)a3 + 3), 3u);
            v57 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
            {
              goto LABEL_194;
            }
            v58 = 64;
            goto LABEL_193;
          }
          v65 = JetCommitTransaction(*((_QWORD *)a3 + 1), 1u);
          v66 = v65;
          if ( v65 )
          {
            if ( v65 == -529 || v65 == -1092 || v65 == -1808 )
            {
              v11 = ATL::AtlHresultFromWin32(112);
            }
            else if ( v65 == -1011 )
            {
              v11 = -2147024882;
            }
            else
            {
              v67 = -v65;
              if ( v67 < 0 )
                LOWORD(v67) = v66;
              v11 = v66 & 0x8E5E0000 | (unsigned __int16)v67 | 0xE5E0000;
            }
            updated = v11;
            v79 = v11;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_iiSd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                65,
                (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
                DWORD2(Source1),
                Source1,
                *(_QWORD *)(*((_QWORD *)a3 + 5) + 112LL),
                v66);
            }
            if ( v26 < 0 )
              v11 = v26;
            JetPrepareUpdate(*((_QWORD *)a3 + 1), *((_QWORD *)a3 + 3), 3u);
            v57 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
            {
              goto LABEL_194;
            }
            v58 = 66;
LABEL_193:
            WPP_SF_S(
              *((_QWORD *)v57 + 2),
              v58,
              &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
              *(_QWORD *)(*((_QWORD *)a3 + 5) + 112LL));
            goto LABEL_194;
          }
        }
        v79 = TieringHeatSession::UpdateRecordsGivenPlacementList(
                v84,
                (const struct TE_FILE_ID_128 *)&Source1,
                v50,
                v10,
                v33,
                v70,
                v72[0] == 1,
                0);
        updated = v79;
        if ( v79 >= 0 )
          goto LABEL_89;
        v15 = WPP_GLOBAL_Control;
        v14 = v74;
        v12 = v73;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && ((unsigned __int8)v74 & *((_BYTE *)WPP_GLOBAL_Control + 28)) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_iiZ(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            67,
            (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
            DWORD2(Source1),
            Source1,
            (__int64)this + 672);
          goto LABEL_2;
        }
      }
    }
  }
  v15 = WPP_GLOBAL_Control;
LABEL_276:
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 && *((_BYTE *)v15 + 25) >= 5u )
  {
    WPP_SF_Z(v15[2], 252, &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids, (char *)this + 672);
LABEL_280:
    v15 = WPP_GLOBAL_Control;
  }
LABEL_281:
  if ( v10 )
  {
    free(v10);
    v15 = WPP_GLOBAL_Control;
  }
  if ( updated >= 0 )
  {
    if ( v11 < 0 )
      updated = v11;
    v79 = updated;
  }
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 && *((_BYTE *)v15 + 25) >= 5u )
    WPP_SF_DIIDZ(
      v15[2],
      *v88 % *((unsigned int *)this + 79),
      (_DWORD)this + 672,
      v12,
      *v88 / *((unsigned int *)this + 79),
      *v89,
      updated,
      (__int64)this + 672);
  CHResultImp::~CHResultImp((CHResultImp *)v78);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x14002fd94  push    rbp
0x14002fd96  push    rbx
0x14002fd97  push    rsi
0x14002fd98  push    rdi
0x14002fd99  push    r12
0x14002fd9b  push    r13
0x14002fd9d  push    r14
0x14002fd9f  push    r15
0x14002fda1  lea     rbp, [rsp-7]
0x14002fda6  sub     rsp, 0F8h
0x14002fdad  mov     rax, cs:__security_cookie
0x14002fdb4  xor     rax, rsp
0x14002fdb7  mov     [rbp+3Fh+var_50], rax
0x14002fdbb  mov     rax, [rbp+3Fh+arg_28]
0x14002fdbf  mov     r13, rcx
0x14002fdc2  mov     [rbp+3Fh+var_78], rax
0x14002fdc6  mov     r15, r8
0x14002fdc9  mov     rax, [rbp+3Fh+arg_30]
0x14002fdcd  mov     [rbp+3Fh+var_70], rax
0x14002fdd1  mov     rax, gs:58h
0x14002fdda  mov     ecx, 8
0x14002fddf  mov     [rbp+3Fh+var_98], r9
0x14002fde3  mov     [rbp+3Fh+var_68], rdx
0x14002fde7  mov     r8, [rax]
0x14002fdea  lea     rax, aCtieredvolumeP_1; "CTieredVolume::Processing_Pass1"
0x14002fdf1  mov     [rcx+r8], rax
0x14002fdf5  lea     rcx, [rbp+3Fh+var_B8]; this
0x14002fdf9  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14002fdfe  xor     esi, esi
0x14002fe00  xor     edi, edi
0x14002fe02  xor     r12d, r12d
0x14002fe05  mov     [rsp+130h+var_C0], rsi
0x14002fe0a  xor     ebx, ebx
0x14002fe0c  mov     r14d, 80000000h
0x14002fe12  mov     [rbp+3Fh+var_B0], ebx
0x14002fe15  mov     [r13+0E8h], rbx
0x14002fe1c  mov     [r13+0F0h], rbx
0x14002fe23  mov     [r13+0F8h], rbx
0x14002fe2a  mov     [r13+100h], rbx
0x14002fe31  mov     r10, cs:WPP_GLOBAL_Control
0x14002fe38  lea     rax, WPP_GLOBAL_Control
0x14002fe3f  cmp     byte ptr [r13+0A5h], 0
0x14002fe47  jnz     loc_140030D2C
0x14002fe4d  cmp     byte ptr [r13+0A6h], 0
0x14002fe55  jnz     loc_140030D2C
0x14002fe5b  mov     rcx, [r13+300h]; hHandle
0x14002fe62  xor     edx, edx; dwMilliseconds
0x14002fe64  call    cs:__imp_WaitForSingleObject
0x14002fe6a  cmp     eax, 102h
0x14002fe6f  jnz     loc_140030D1E
0x14002fe75  mov     rcx, [r13+2F8h]; hHandle
0x14002fe7c  xor     edx, edx; dwMilliseconds
0x14002fe7e  call    cs:__imp_WaitForSingleObject
0x14002fe84  cmp     eax, 102h
0x14002fe89  jnz     loc_140030D1E
0x14002fe8f  cmp     dword ptr [r13+0B8h], 3
0x14002fe97  jnz     loc_140030D5B
0x14002fe9d  mov     rax, [r15+28h]
0x14002fea1  xor     ecx, ecx
0x14002fea3  cmp     [rax+4Dh], cl
0x14002fea6  jz      short loc_14002FEB1
0x14002fea8  cmp     [rax+4Ch], cl
0x14002feab  jnz     loc_140030D5B
0x14002feb1  mov     [rbp+3Fh+var_9C], ecx
0x14002feb4  mov     [rbp+3Fh+var_A8], ecx
0x14002feb7  mov     [rbp+3Fh+var_A0], ecx
0x14002feba  mov     [rbp+3Fh+var_A4], ecx
0x14002febd  test    rsi, rsi
0x14002fec0  jz      short loc_14002FED2
0x14002fec2  mov     rcx, rsi; Block
0x14002fec5  call    cs:__imp_free
0x14002fecb  xor     esi, esi
0x14002fecd  mov     [rsp+130h+var_C0], rsi
0x14002fed2  mov     rdx, [r15+18h]; tableid
0x14002fed6  xor     r9d, r9d; grbit
0x14002fed9  mov     rcx, [r15+8]; sesid
0x14002fedd  mov     r8d, r14d; cRow
0x14002fee0  call    cs:__imp_JetMove
0x14002fee6  mov     r9d, eax
0x14002fee9  cmp     eax, 0FFFFF9BFh
0x14002feee  jz      loc_140030D17
0x14002fef4  cmp     eax, 40Fh
0x14002fef9  jz      loc_140030D17
0x14002feff  cmp     eax, 0FFFFF9BDh
0x14002ff04  jz      loc_140030D17
0x14002ff0a  mov     r14d, 1
0x14002ff10  mov     [rsp+130h+var_C8], r14d
0x14002ff15  cmp     eax, 0FFFFFC07h
0x14002ff1a  jz      loc_14002FE31
0x14002ff20  test    eax, eax
0x14002ff22  jnz     loc_140030C83
0x14002ff28  mov     rcx, [r15+8]; sesid
0x14002ff2c  xorps   xmm0, xmm0
0x14002ff2f  inc     r12d
0x14002ff32  mov     [rsp+130h+var_D0], al
0x14002ff36  mov     [rsp+130h+var_CC], r12d
0x14002ff3b  movups  [rbp+3Fh+Source1], xmm0
0x14002ff3f  mov     [rsp+130h+var_C4], al
0x14002ff43  call    cs:__imp_JetBeginTransaction
0x14002ff49  mov     r8d, eax
0x14002ff4c  test    eax, eax
0x14002ff4e  jz      loc_14002FFF8
0x14002ff54  cmp     eax, 0FFFFFDEFh
0x14002ff59  jz      short loc_14002FF92
0x14002ff5b  cmp     eax, 0FFFFFBBCh
0x14002ff60  jz      short loc_14002FF92
0x14002ff62  cmp     eax, 0FFFFF8F0h
0x14002ff67  jz      short loc_14002FF92
0x14002ff69  cmp     eax, 0FFFFFC0Dh
0x14002ff6e  jnz     short loc_14002FF77
0x14002ff70  mov     ebx, 8007000Eh
0x14002ff75  jmp     short loc_14002FF9E
0x14002ff77  neg     eax
0x14002ff79  cmovs   eax, r8d
0x14002ff7d  movzx   ebx, ax
0x14002ff80  mov     eax, r8d
0x14002ff83  and     eax, 8E5E0000h
0x14002ff88  or      ebx, eax
0x14002ff8a  or      ebx, 0E5E0000h
0x14002ff90  jmp     short loc_14002FF9E
0x14002ff92  mov     ecx, 70h ; 'p'; unsigned int
0x14002ff97  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14002ff9c  mov     ebx, eax
0x14002ff9e  mov     [rbp+3Fh+var_B0], ebx
0x14002ffa1  mov     r10, cs:WPP_GLOBAL_Control
0x14002ffa8  lea     rax, WPP_GLOBAL_Control
0x14002ffaf  cmp     r10, rax
0x14002ffb2  jz      short loc_14002FFEA
0x14002ffb4  test    [r10+1Ch], r14b
0x14002ffb8  jz      short loc_14002FFEA
0x14002ffba  cmp     byte ptr [r10+19h], 2
0x14002ffbf  jb      short loc_14002FFEA
0x14002ffc1  mov     r9, [r15+28h]
0x14002ffc5  mov     edx, 2Ch ; ','
0x14002ffca  mov     rcx, [r10+10h]
0x14002ffce  mov     dword ptr [rsp+130h+pcbActual], r8d
0x14002ffd3  lea     r8, WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids
0x14002ffda  mov     r9, [r9+70h]
0x14002ffde  call    WPP_SF_Sd
0x14002ffe3  mov     r10, cs:WPP_GLOBAL_Control
0x14002ffea  test    edi, edi
0x14002ffec  mov     eax, ebx
0x14002ffee  cmovs   eax, edi
0x14002fff1  mov     edi, eax
0x14002fff3  jmp     loc_14002FE38
0x14002fff8  lea     r9, [rsp+130h+var_C4]; unsigned __int8 *
0x14002fffd  mov     rcx, r15; this
0x140030000  lea     r8, [rsp+130h+var_D0]; unsigned __int8 *
0x140030005  lea     rdx, [rbp+3Fh+Source1]; struct TE_FILE_ID_128 *
0x140030009  call    ?GetCurrentPinnedRecord@TieringPinnedSession@@QEAAJPEAUTE_FILE_ID_128@@PEAE1@Z; TieringPinnedSession::GetCurrentPinnedRecord(TE_FILE_ID_128 *,uchar *,uchar *)
0x14003000e  mov     r8d, eax
0x140030011  cmp     eax, 0FFFFFC07h
0x140030016  jnz     short loc_140030065
0x140030018  mov     rcx, cs:WPP_GLOBAL_Control
0x14003001f  lea     rax, WPP_GLOBAL_Control
0x140030026  cmp     rcx, rax
0x140030029  jz      short loc_140030054
0x14003002b  test    [rcx+1Ch], r14b
0x14003002f  jz      short loc_140030054
0x140030031  cmp     byte ptr [rcx+19h], 5
0x140030035  jb      short loc_140030054
0x140030037  mov     r9, [r15+28h]
0x14003003b  lea     r8, WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids
0x140030042  mov     rcx, [rcx+10h]
0x140030046  mov     edx, 2Dh ; '-'
0x14003004b  mov     r9, [r9+70h]
0x14003004f  call    WPP_SF_S
0x140030054  mov     rcx, [r15+8]; sesid
0x140030058  xor     edx, edx; grbit
0x14003005a  call    cs:__imp_JetRollback
0x140030060  jmp     loc_14002FE31
0x140030065  mov     r12d, edi
0x140030068  test    r8d, r8d
0x14003006b  jz      loc_14003016C
0x140030071  cmp     r8d, 0FFFFFDEFh
0x140030078  jz      short loc_1400300B7
0x14003007a  cmp     r8d, 0FFFFFBBCh
0x140030081  jz      short loc_1400300B7
0x140030083  cmp     r8d, 0FFFFF8F0h
0x14003008a  jz      short loc_1400300B7
0x14003008c  cmp     r8d, 0FFFFFC0Dh
0x140030093  jnz     short loc_14003009C
0x140030095  mov     edi, 8007000Eh
0x14003009a  jmp     short loc_1400300C3
0x14003009c  neg     eax
0x14003009e  cmovs   eax, r8d
0x1400300a2  movzx   edi, ax
0x1400300a5  mov     eax, r8d
0x1400300a8  and     eax, 8E5E0000h
0x1400300ad  or      edi, eax
0x1400300af  or      edi, 0E5E0000h
0x1400300b5  jmp     short loc_1400300C3
0x1400300b7  mov     ecx, 70h ; 'p'; unsigned int
0x1400300bc  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1400300c1  mov     edi, eax
0x1400300c3  mov     ebx, edi
0x1400300c5  mov     [rbp+3Fh+var_B0], ebx
0x1400300c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400300cf  lea     rax, WPP_GLOBAL_Control
0x1400300d6  cmp     rcx, rax
0x1400300d9  jz      short loc_140030121
0x1400300db  test    [rcx+1Ch], r14b
0x1400300df  jz      short loc_140030121
0x1400300e1  cmp     byte ptr [rcx+19h], 2
0x1400300e5  jb      short loc_140030121
0x1400300e7  mov     rax, [r15+28h]
0x1400300eb  mov     edx, 2Eh ; '.'
0x1400300f0  mov     r9d, [rsp+130h+var_CC]
0x1400300f5  mov     rcx, [rcx+10h]
0x1400300f9  mov     dword ptr [rsp+130h+var_108], r8d
0x1400300fe  lea     r8, WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids
0x140030105  mov     rax, [rax+70h]
0x140030109  mov     [rsp+130h+pcbActual], rax
0x14003010e  call    WPP_SF_DSd
0x140030113  mov     rcx, cs:WPP_GLOBAL_Control
0x14003011a  lea     rax, WPP_GLOBAL_Control
0x140030121  test    r12d, r12d
0x140030124  cmovs   edi, r12d
0x140030128  cmp     rcx, rax
0x14003012b  jz      short loc_140030156
0x14003012d  test    [rcx+1Ch], r14b
0x140030131  jz      short loc_140030156
0x140030133  cmp     byte ptr [rcx+19h], 5
0x140030137  jb      short loc_140030156
0x140030139  mov     edx, 2Fh ; '/'
0x14003013e  mov     r9, [r15+28h]
0x140030142  lea     r8, WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids
0x140030149  mov     rcx, [rcx+10h]
0x14003014d  mov     r9, [r9+70h]
0x140030151  call    WPP_SF_S
0x140030156  mov     rcx, [r15+8]; sesid
0x14003015a  xor     edx, edx; grbit
0x14003015c  call    cs:__imp_JetRollback
0x140030162  mov     r12d, [rsp+130h+var_CC]
0x140030167  jmp     loc_14002FE31
0x14003016c  mov     r8d, 10h; Length
0x140030172  lea     rdx, ?NullGuid@@3U_GUID@@A; Source2
0x140030179  lea     rcx, [rbp+3Fh+Source1]; Source1
0x14003017d  call    cs:__imp_RtlCompareMemory
0x140030183  cmp     rax, 10h
0x140030187  jnz     short loc_1400301AF
0x140030189  mov     rcx, cs:WPP_GLOBAL_Control
0x140030190  lea     rax, WPP_GLOBAL_Control
0x140030197  cmp     rcx, rax
0x14003019a  jz      short loc_140030156
0x14003019c  test    [rcx+1Ch], r14b
0x1400301a0  jz      short loc_140030156
0x1400301a2  cmp     byte ptr [rcx+19h], 5
0x1400301a6  jb      short loc_140030156
0x1400301a8  mov     edx, 30h ; '0'
0x1400301ad  jmp     short loc_14003013E
0x1400301af  mov     rdx, [rbp+3Fh+var_68]; void *
0x1400301b3  lea     r9, [rbp+3Fh+var_9C]; int *
0x1400301b7  xor     eax, eax
0x1400301b9  lea     r8, [rbp+3Fh+Source1]; struct TE_FILE_ID_128 *
0x1400301bd  mov     [rbp+3Fh+var_90], rax
0x1400301c1  mov     rcx, r13; this
0x1400301c4  mov     [rbp+3Fh+var_80], rax
0x1400301c8  mov     [rbp+3Fh+var_88], rax
0x1400301cc  lea     rax, [rsp+130h+var_C0]
0x1400301d1  mov     [rsp+130h+var_E0], rax; struct _FILE_PLACEMENT **
0x1400301d6  lea     rax, [rbp+3Fh+var_A4]
0x1400301da  mov     [rsp+130h+var_E8], rax; unsigned int *
0x1400301df  lea     rax, [rbp+3Fh+var_80]
0x1400301e3  mov     [rsp+130h+var_F0], rax; unsigned __int64 *
0x1400301e8  lea     rax, [rbp+3Fh+var_88]
0x1400301ec  mov     [rsp+130h+var_F8], rax; unsigned __int64 *
0x1400301f1  lea     rax, [rbp+3Fh+var_90]
0x1400301f5  mov     [rsp+130h+var_100], rax; unsigned __int64 *
0x1400301fa  lea     rax, [rbp+3Fh+var_A0]
0x1400301fe  mov     [rsp+130h+var_108], rax; int *
0x140030203  lea     rax, [rbp+3Fh+var_A8]
0x140030207  mov     [rsp+130h+pcbActual], rax; int *
0x14003020c  call    ?GetFileExtentsByFileId@CTieredVolume@@QEAAJPEAXPEBUTE_FILE_ID_128@@PEAH22PEA_K33PEAKPEAPEAU_FILE_PLACEMENT@@PEAPEAX@Z; CTieredVolume::GetFileExtentsByFileId(void *,TE_FILE_ID_128 const *,int *,int *,int *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,ulong *,_FILE_PLACEMENT * *,void * *)
0x140030211  mov     esi, eax
0x140030213  mov     rcx, cs:WPP_GLOBAL_Control
0x14003021a  lea     rax, WPP_GLOBAL_Control
0x140030221  mov     r14, [rbp+3Fh+var_90]
0x140030225  mov     rbx, [rbp+3Fh+var_88]
0x140030229  cmp     rcx, rax
0x14003022c  jz      short loc_14003026A
0x14003022e  test    byte ptr [rcx+1Ch], 1
0x140030232  jz      short loc_14003026A
0x140030234  cmp     byte ptr [rcx+19h], 5
0x140030238  jb      short loc_14003026A
0x14003023a  mov     rax, [rbp+3Fh+var_80]
0x14003023e  mov     r9, qword ptr [rbp+3Fh+Source1+8]
0x140030242  mov     rcx, [rcx+10h]
0x140030246  mov     [rsp+130h+var_F8], rax
0x14003024b  mov     rax, qword ptr [rbp+3Fh+Source1]
0x14003024f  mov     [rsp+130h+var_100], rbx
0x140030254  mov     [rsp+130h+var_108], r14; int
0x140030259  mov     [rsp+130h+pcbActual], rax
0x14003025e  call    WPP_SF_iiiii
0x140030263  lea     rax, WPP_GLOBAL_Control
0x14003026a  test    esi, esi
0x14003026c  jns     loc_140030366
0x140030272  mov     dl, [rsp+130h+var_D0]
0x140030276  cmp     dl, 1
0x140030279  jnz     short loc_140030284
  ... truncated ...
```
