# CTieredVolume::Processing_Pass2(void *,TieringHeatSession *)

- ea: `0x140030e10`
- end: `0x140031dfd`
- name: `?Processing_Pass2@CTieredVolume@@AEAAJPEAXPEAVTieringHeatSession@@@Z`
- size: `4077`
- prototype: `__int64 __fastcall(CTieredVolume *__hidden this, void *, struct TieringHeatSession *)`
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
- `0x14000b7f8`
- `0x140017824`
- `0x140017e78`
- `0x1400185a0`
- `0x1400260cc`
- `0x140026434`
- `0x14002670c`
- `0x14002866c`
- `0x140029dec`
- `0x14002a8e4`
- `0x14002d960`
- `0x14002dba8`
- `0x140030e10`
- `0x140035c8c`
- `0x140035d68`
- `0x140035e9c`
- `0x14003fbb0`

## import_xrefs

- `msvcrt!free` at `0x14003114c`
- `msvcrt!free` at `0x140031d58`
- `msvcrt!free` at `0x14003114c`
- `msvcrt!free` at `0x140031d58`
- `ntdll!NtClose` at `0x140031162`
- `ntdll!NtClose` at `0x140031438`
- `ntdll!NtClose` at `0x140031d67`
- `ntdll!NtClose` at `0x140031162`
- `ntdll!NtClose` at `0x140031438`
- `ntdll!NtClose` at `0x140031d67`
- `ntdll!RtlCompareMemory` at `0x140031114`
- `ntdll!RtlCompareMemory` at `0x140031132`
- `ntdll!RtlCompareMemory` at `0x140031114`
- `ntdll!RtlCompareMemory` at `0x140031132`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140030f12`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140030f2c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140030ff1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003100d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140030f12`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140030f2c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140030ff1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003100d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140031b06`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140031b06`
- `ESENT!JetDelete` at `0x1400314bd`
- `ESENT!JetDelete` at `0x140031b5e`
- `ESENT!JetDelete` at `0x1400314bd`
- `ESENT!JetDelete` at `0x140031b5e`
- `ESENT!JetPrepareUpdate` at `0x140031817`
- `ESENT!JetPrepareUpdate` at `0x140031834`
- `ESENT!JetPrepareUpdate` at `0x140031848`
- `ESENT!JetPrepareUpdate` at `0x14003196a`
- `ESENT!JetPrepareUpdate` at `0x140031a0b`
- `ESENT!JetPrepareUpdate` at `0x140031aef`
- `ESENT!JetPrepareUpdate` at `0x140031817`
- `ESENT!JetPrepareUpdate` at `0x140031834`
- `ESENT!JetPrepareUpdate` at `0x140031848`
- `ESENT!JetPrepareUpdate` at `0x14003196a`
- `ESENT!JetPrepareUpdate` at `0x140031a0b`
- `ESENT!JetPrepareUpdate` at `0x140031aef`
- `ESENT!JetUpdate` at `0x140031a31`
- `ESENT!JetUpdate` at `0x140031a31`
- `ESENT!JetMove` at `0x140030f73`
- `ESENT!JetMove` at `0x140030f73`

## pseudocode

```c
__int64 __fastcall CTieredVolume::Processing_Pass2(CTieredVolume *this, void *a2, struct TieringHeatSession *a3)
{
  PVOID ThreadLocalStoragePointer; // rax
  int v6; // r12d
  int v7; // edi
  __int64 v8; // r15
  struct _FILE_PLACEMENT *v9; // r13
  int v10; // ebx
  _QWORD *v11; // r10
  __int64 v12; // rax
  JET_TABLEID v13; // rdx
  unsigned int v14; // eax
  __int64 v15; // rax
  JET_ERR CurrentHeatRecord; // eax
  JET_ERR updated; // ebx
  int v18; // edi
  int v19; // eax
  __int64 v20; // rdx
  int v21; // edx
  int v22; // r8d
  int FileSummaryByFileId; // eax
  _QWORD *v24; // r10
  __int64 v25; // rcx
  __int64 v26; // r11
  unsigned __int8 v27; // cl
  char v28; // r8
  char v29; // al
  int FileExtentsForHandle; // eax
  bool v31; // zf
  char v32; // r9
  char v33; // dl
  JET_ERR v34; // eax
  int v35; // eax
  unsigned int v36; // eax
  unsigned int v37; // eax
  int v38; // eax
  JET_ERR v39; // eax
  JET_TABLEID v40; // rdx
  JET_SESID v41; // rcx
  int v42; // edi
  int v43; // eax
  JET_ERR v44; // eax
  int v45; // edi
  int v46; // eax
  _QWORD *v47; // rcx
  __int64 v48; // rdx
  unsigned int v49; // r9d
  unsigned int v50; // ebx
  unsigned int v51; // r8d
  char v53; // [rsp+40h] [rbp-C0h]
  unsigned __int8 v54; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int8 v55; // [rsp+61h] [rbp-9Fh] BYREF
  char v56; // [rsp+62h] [rbp-9Eh] BYREF
  char v57; // [rsp+63h] [rbp-9Dh] BYREF
  unsigned __int8 v58[4]; // [rsp+64h] [rbp-9Ch] BYREF
  int v59; // [rsp+68h] [rbp-98h]
  unsigned __int16 v60[2]; // [rsp+6Ch] [rbp-94h] BYREF
  int v61; // [rsp+70h] [rbp-90h] BYREF
  int v62; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v63; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v64; // [rsp+80h] [rbp-80h] BYREF
  int v65; // [rsp+84h] [rbp-7Ch]
  unsigned int v66; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v67; // [rsp+8Ch] [rbp-74h] BYREF
  int v68; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v69; // [rsp+94h] [rbp-6Ch]
  unsigned int v70; // [rsp+98h] [rbp-68h]
  unsigned __int64 v71; // [rsp+A0h] [rbp-60h] BYREF
  void *v72; // [rsp+A8h] [rbp-58h] BYREF
  struct _FILE_PLACEMENT *v73; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v74; // [rsp+B8h] [rbp-48h] BYREF
  void *v75; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v76; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int64 v77; // [rsp+D0h] [rbp-30h] BYREF
  char v78[8]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int v79; // [rsp+E0h] [rbp-20h]
  __int128 Source2; // [rsp+F0h] [rbp-10h] BYREF
  GUID Source1; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v82[8]; // [rsp+110h] [rbp+10h] BYREF

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v75 = a2;
  *(_QWORD *)(*(_QWORD *)ThreadLocalStoragePointer + 8LL) = "CTieredVolume::Processing_Pass2";
  CHResultImp::CHResultImp((CHResultImp *)v78);
  v6 = 0;
  v7 = 0;
  v64 = 0;
  v66 = 0;
  v8 = -1;
  v71 = 0;
  v9 = 0;
  v72 = (void *)-1LL;
  v73 = 0;
  Source2 = 0;
  v76 = 0;
  v77 = 0;
  v10 = 0x80000000;
  v62 = 0;
  Source1 = NullGuid;
  v61 = 0;
  v65 = 0;
  v63 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v60[0] = 0;
  v69 = 0;
  v70 = 0;
  v68 = 0;
  do
  {
LABEL_2:
    v11 = WPP_GLOBAL_Control;
LABEL_3:
    if ( *((_BYTE *)this + 165) || *((_BYTE *)this + 166) )
      goto LABEL_210;
    if ( WaitForSingleObject(*((HANDLE *)this + 96), 0) != 258 || WaitForSingleObject(*((HANDLE *)this + 95), 0) != 258 )
    {
      v11 = WPP_GLOBAL_Control;
LABEL_210:
      if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 && *((_BYTE *)v11 + 25) >= 5u )
        WPP_SF_Z(v11[2], 252, &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids, (char *)this + 672);
      goto LABEL_214;
    }
    if ( *((_DWORD *)this + 46) != 4 )
      goto LABEL_214;
    v12 = *((_QWORD *)a3 + 5);
    if ( *(_BYTE *)(v12 + 77) )
    {
      if ( *(_BYTE *)(v12 + 76) )
        goto LABEL_214;
    }
    v13 = *((_QWORD *)a3 + 3);
    v54 = 0;
    v68 = 0;
    v14 = JetMove(*((_QWORD *)a3 + 1), v13, v10, 0);
    if ( v14 == -1601 || v14 == 1039 || v14 == -1603 )
    {
      v47 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v48 = 69;
LABEL_204:
        WPP_SF_d(v47[2], v48, &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids, v14);
      }
      goto LABEL_214;
    }
    v10 = 1;
    v59 = 1;
  }
  while ( v14 == -1017 );
  if ( !v14 )
  {
    v11 = WPP_GLOBAL_Control;
    while ( 1 )
    {
      v10 = v59;
      if ( *((_DWORD *)this + 46) != 4 )
        goto LABEL_3;
      if ( *((_BYTE *)this + 165) || *((_BYTE *)this + 166) )
        goto LABEL_196;
      if ( WaitForSingleObject(*((HANDLE *)this + 96), 0) != 258
        || WaitForSingleObject(*((HANDLE *)this + 95), 0) != 258 )
      {
        v11 = WPP_GLOBAL_Control;
LABEL_196:
        v10 = v59;
        if ( v11 != &WPP_GLOBAL_Control
          && ((unsigned __int8)v59 & *((_BYTE *)v11 + 28)) != 0
          && *((_BYTE *)v11 + 25) >= 5u )
        {
          WPP_SF_Z(v11[2], 252, &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids, (char *)this + 672);
          goto LABEL_2;
        }
        goto LABEL_3;
      }
      v15 = *((_QWORD *)a3 + 5);
      if ( *(_BYTE *)(v15 + 77) && *(_BYTE *)(v15 + 76) )
      {
LABEL_190:
        v10 = v59;
        goto LABEL_2;
      }
      CurrentHeatRecord = TieringHeatSession::GetCurrentHeatRecord(
                            a3,
                            0,
                            (struct TE_FILE_ID_128 *)&Source2,
                            &v63,
                            &v55,
                            (unsigned __int8 *)&v56,
                            (unsigned __int8 *)&v57,
                            v60,
                            v82);
      updated = CurrentHeatRecord;
      if ( CurrentHeatRecord == -1017 )
        goto LABEL_89;
      if ( CurrentHeatRecord )
      {
        if ( CurrentHeatRecord == -529 || CurrentHeatRecord == -1092 || CurrentHeatRecord == -1808 )
        {
          v18 = ATL::AtlHresultFromWin32(112);
        }
        else if ( CurrentHeatRecord == -1011 )
        {
          v18 = -2147024882;
        }
        else
        {
          v19 = -CurrentHeatRecord;
          if ( v19 < 0 )
            LOWORD(v19) = updated;
          v18 = updated & 0x8E5E0000 | (unsigned __int16)v19 | 0xE5E0000;
        }
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v20 = 71;
          goto LABEL_113;
        }
        goto LABEL_145;
      }
      if ( RtlCompareMemory(&NullGuid, &Source2, 0x10u) == 16 )
        goto LABEL_190;
      if ( RtlCompareMemory(&Source1, &Source2, 0x10u) != 16 )
      {
        if ( v9 )
        {
          free(v9);
          v9 = 0;
          v73 = 0;
        }
        if ( v8 != -1 )
        {
          NtClose((HANDLE)v8);
          v72 = (void *)-1LL;
        }
        v65 = 0;
        Source1 = (GUID)Source2;
        v66 = 0;
        v61 = 0;
        v62 = 0;
        LODWORD(v71) = 0;
        v74 = 0;
        FileSummaryByFileId = CTieredVolume::GetFileSummaryByFileId(
                                this,
                                v75,
                                (const struct TE_FILE_ID_128 *)&Source1,
                                (int *)&v71,
                                &v61,
                                &v62,
                                &v74,
                                &v72);
        v7 = v61;
        if ( FileSummaryByFileId < 0 && !v61 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_iiZ(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v61 + 72,
              (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
              *(_DWORD *)Source1.Data4,
              Source1.Data1,
              (__int64)this + 672);
          }
          ++*((_DWORD *)this + 78);
          v7 = 1;
          v61 = 1;
        }
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
        {
          v8 = (__int64)v72;
          v71 = v74;
          goto LABEL_56;
        }
        v25 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v53 = v71;
        v71 = v74;
        WPP_SF_iiiDDDDZ(v25, v21, v22, DWORD2(Source2), Source2, v74, v62, v7, v53, 0, (__int64)this + 672);
        v8 = (__int64)v72;
      }
      v24 = WPP_GLOBAL_Control;
LABEL_56:
      v26 = v63;
      if ( v63 >= v71 || v7 )
      {
        if ( v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 1) != 0 && *((_BYTE *)v24 + 25) >= 5u )
          WPP_SF_iiDiZ(v24[2], v21, v22, DWORD2(Source2), Source2, v7, v63, (__int64)this + 672);
        updated = JetDelete(*((_QWORD *)a3 + 1), *((_QWORD *)a3 + 3));
        if ( !updated )
          goto LABEL_89;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_iiiZL(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            75,
            (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
            *(_DWORD *)Source1.Data4,
            Source1.Data1,
            v63,
            (__int64)this + 672,
            updated);
          goto LABEL_89;
        }
        goto LABEL_90;
      }
      if ( v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 1) != 0 && *((_BYTE *)v24 + 25) >= 5u )
      {
        WPP_SF_iiiDDZ(
          v24[2],
          76,
          (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
          DWORD2(Source2),
          Source2,
          v63,
          v55,
          v56,
          (__int64)this + 672);
        v26 = v63;
      }
      v27 = v56;
      v28 = v57;
      v29 = v56;
      v54 = v56;
      if ( (v56 & 0xC) != 0 && v57 != *((_BYTE *)this + 328) )
      {
        v27 = v56 & 0xF3;
        v54 = v56 & 0xF3;
        v29 = v56 & 0xF3;
      }
      v58[0] = v55;
      if ( (v29 & 0xC) != 0
        || (v29 & 0x20) != 0
        && (v29 & 0x10) == 0
        && !v62
        && (v55 & 0xF0) != 0
        && ((v55 & 0x80u) == 0 || v57 == *((_BYTE *)this + 328)) )
      {
        goto LABEL_121;
      }
      if ( !v65 )
      {
        v65 = 1;
        FileExtentsForHandle = CTieredVolume::GetFileExtentsForHandle(
                                 this,
                                 (HANDLE)v8,
                                 (const struct TE_FILE_ID_128 *)&Source1,
                                 &v77,
                                 &v76,
                                 &v66,
                                 &v73);
        if ( FileExtentsForHandle < 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_iiZd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              77,
              (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
              *(_DWORD *)Source1.Data4,
              Source1.Data1,
              (__int64)this + 672,
              FileExtentsForHandle);
          }
          ++*((_DWORD *)this + 78);
        }
        if ( v8 != -1 )
        {
          NtClose((HANDLE)v8);
          v8 = -1;
          v72 = (void *)-1LL;
        }
        v27 = v54;
        v26 = v63;
        v9 = v73;
      }
      updated = TieringHeatSession::UpdateCurrentRecordGivenPlacementList(
                  a3,
                  (const struct TE_FILE_ID_128 *)&Source2,
                  v26,
                  v66,
                  v9,
                  v71,
                  0,
                  0,
                  0,
                  v27,
                  v60[0]);
      if ( updated )
      {
        v28 = v57;
        if ( v57 != *((_BYTE *)this + 328) && (v55 & 0x80u) != 0 )
        {
          updated = JetDelete(*((_QWORD *)a3 + 1), *((_QWORD *)a3 + 3));
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_iiiZL(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              78,
              (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
              DWORD2(Source2),
              Source2,
              v63,
              (__int64)this + 672,
              updated);
LABEL_89:
            v11 = WPP_GLOBAL_Control;
            goto LABEL_90;
          }
          goto LABEL_90;
        }
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_iiiZL(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            79,
            (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
            DWORD2(Source2),
            Source2,
            v63,
            (__int64)this + 672,
            updated);
          v28 = v57;
          v11 = WPP_GLOBAL_Control;
        }
        v32 = v56;
        v33 = v58[0] & 0xF | 0x80;
        v27 = v54 | 0x20;
        v60[0] = 0;
      }
      else
      {
        v34 = TieringHeatSession::GetCurrentHeatRecord(
                a3,
                0,
                (struct TE_FILE_ID_128 *)&Source2,
                &v63,
                &v55,
                (unsigned __int8 *)&v56,
                (unsigned __int8 *)&v57,
                v60,
                v82);
        updated = v34;
        if ( v34 == -1017 )
          goto LABEL_89;
        if ( v34 )
        {
          if ( v34 == -529 || v34 == -1092 || v34 == -1808 )
          {
            v18 = ATL::AtlHresultFromWin32(112);
          }
          else if ( v34 == -1011 )
          {
            v18 = -2147024882;
          }
          else
          {
            v35 = -v34;
            if ( v35 < 0 )
              LOWORD(v35) = updated;
            v18 = updated & 0x8E5E0000 | (unsigned __int16)v35 | 0xE5E0000;
          }
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v20 = 80;
LABEL_113:
            WPP_SF_d(v11[2], v20, &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids, (unsigned int)updated);
LABEL_144:
            v11 = WPP_GLOBAL_Control;
          }
LABEL_145:
          if ( v6 >= 0 )
            v6 = v18;
          goto LABEL_90;
        }
        v32 = v56;
        v33 = v55;
        v27 = v56;
        v28 = v57;
        v11 = WPP_GLOBAL_Control;
      }
      v54 = v27;
      v58[0] = v33;
      if ( (v33 & 0xF0) != 0 )
      {
        v26 = v63;
LABEL_121:
        v64 = 0;
        v67 = 0;
        TieringHeatSession::AddCurrentCountAndAgeHistory(
          a3,
          (const struct TE_FILE_ID_128 *)&Source2,
          v26,
          0,
          v28,
          v60[0],
          v27,
          v82,
          &v68,
          &v64,
          &v67);
        v36 = v69;
        if ( v64 > v69 )
          v36 = v64;
        v69 = v36;
        v37 = v70;
        if ( v67 > v70 )
          v37 = v67;
        v70 = v37;
        if ( v58[0] == v55 && !v68 && v56 == v54 )
          goto LABEL_89;
        updated = JetPrepareUpdate(*((_QWORD *)a3 + 1), *((_QWORD *)a3 + 3), 2u);
        if ( updated == -1607 )
        {
          JetPrepareUpdate(*((_QWORD *)a3 + 1), *((_QWORD *)a3 + 3), 3u);
          updated = JetPrepareUpdate(*((_QWORD *)a3 + 1), *((_QWORD *)a3 + 3), 2u);
        }
        switch ( updated )
        {
          case 0:
            v39 = TieringHeatSession::SetCurrentHeatRecord(a3, 0, 0, v58, &v54, (unsigned __int8 *)this + 328, 0, v82);
            v40 = *((_QWORD *)a3 + 3);
            updated = v39;
            v41 = *((_QWORD *)a3 + 1);
            if ( v39 )
            {
              JetPrepareUpdate(v41, v40, 3u);
              if ( updated == -529 || updated == -1092 || updated == -1808 )
              {
                v42 = ATL::AtlHresultFromWin32(112);
              }
              else if ( updated == -1011 )
              {
                v42 = -2147024882;
              }
              else
              {
                v43 = -updated;
                if ( updated > 0 )
                  LOWORD(v43) = updated;
                v42 = updated & 0x8E5E0000 | (unsigned __int16)v43 | 0xE5E0000;
              }
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_Zd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  83,
                  (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
                  (_DWORD)this + 672,
                  updated);
              }
              JetPrepareUpdate(*((_QWORD *)a3 + 1), *((_QWORD *)a3 + 3), 3u);
              if ( v6 >= 0 )
                v6 = v42;
            }
            else
            {
              v44 = JetUpdate(v41, v40, 0, 0, 0);
              updated = v44;
              switch ( v44 )
              {
                case 0:
                  v11 = WPP_GLOBAL_Control;
                  v10 = v59;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && ((unsigned __int8)v59 & *((_BYTE *)WPP_GLOBAL_Control + 28)) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                  {
                    WPP_SF_iiiDDZ(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      85,
                      (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
                      DWORD2(Source2),
                      Source2,
                      v63,
                      v58[0],
                      v54,
                      (__int64)this + 672);
                    goto LABEL_2;
                  }
                  goto LABEL_3;
                case -529:
                case -1092:
                case -1808:
                  v45 = ATL::AtlHresultFromWin32(112);
                  break;
                case -1011:
                  v45 = -2147024882;
                  break;
                default:
                  v46 = -v44;
                  if ( v46 < 0 )
                    LOWORD(v46) = updated;
                  v45 = updated & 0x8E5E0000 | (unsigned __int16)v46 | 0xE5E0000;
                  break;
              }
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_iiZd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  84,
                  (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
                  DWORD2(Source2),
                  Source2,
                  (__int64)this + 672,
                  updated);
              }
              if ( v6 >= 0 )
                v6 = v45;
              JetPrepareUpdate(*((_QWORD *)a3 + 1), *((_QWORD *)a3 + 3), 3u);
              if ( updated == -1102 )
              {
                Sleep(0x64u);
                v11 = WPP_GLOBAL_Control;
                goto LABEL_91;
              }
            }
            goto LABEL_89;
          case -529:
          case -1092:
          case -1808:
            v18 = ATL::AtlHresultFromWin32(112);
            break;
          case -1011:
            v18 = -2147024882;
            break;
          default:
            v38 = -updated;
            if ( updated > 0 )
              LOWORD(v38) = updated;
            v18 = updated & 0x8E5E0000 | (unsigned __int16)v38 | 0xE5E0000;
            break;
        }
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_iiZd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            82,
            (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
            DWORD2(Source2),
            Source2,
            (__int64)this + 672,
            updated);
          goto LABEL_144;
        }
        goto LABEL_145;
      }
      if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 && *((_BYTE *)v11 + 25) >= 5u )
      {
        WPP_SF_iiiDDZ(
          v11[2],
          81,
          (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
          DWORD2(Source2),
          Source2,
          v63,
          v33,
          v32,
          (__int64)this + 672);
        goto LABEL_89;
      }
LABEL_90:
      v7 = v61;
      v31 = updated == -1102;
      v10 = v59;
      if ( !v31 )
        goto LABEL_3;
LABEL_91:
      v7 = v61;
    }
  }
  v47 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v48 = 70;
    goto LABEL_204;
  }
LABEL_214:
  if ( v9 )
    free(v9);
  if ( v8 != -1 )
    NtClose((HANDLE)v8);
  v49 = v69;
  v50 = 0;
  v51 = v70;
  *((_DWORD *)this + 54) = v69;
  *((_DWORD *)this + 55) = v51;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DDZ(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      86,
      (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
      v49,
      v51,
      (__int64)this + 672);
  }
  if ( v6 < 0 )
    v50 = v6;
  v79 = v50;
  CHResultImp::~CHResultImp((CHResultImp *)v78);
  return v50;
}

```

## disassembly

```asm
0x140030e10  mov     [rsp-8+arg_18], rbx
0x140030e15  push    rbp
0x140030e16  push    rsi
0x140030e17  push    rdi
0x140030e18  push    r12
0x140030e1a  push    r13
0x140030e1c  push    r14
0x140030e1e  push    r15
0x140030e20  lea     rbp, [rsp-30h]
0x140030e25  sub     rsp, 130h
0x140030e2c  mov     rax, cs:__security_cookie
0x140030e33  xor     rax, rsp
0x140030e36  mov     [rbp+60h+var_40], rax
0x140030e3a  mov     rax, gs:58h
0x140030e43  mov     rsi, rcx
0x140030e46  mov     ecx, 8
0x140030e4b  mov     r14, r8
0x140030e4e  mov     [rbp+60h+var_A0], rdx
0x140030e52  mov     r9, [rax]
0x140030e55  lea     rax, aCtieredvolumeP_4; "CTieredVolume::Processing_Pass2"
0x140030e5c  mov     [rcx+r9], rax
0x140030e60  lea     rcx, [rbp+60h+var_88]; this
0x140030e64  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x140030e69  xor     r12d, r12d
0x140030e6c  xor     edi, edi
0x140030e6e  xor     eax, eax
0x140030e70  mov     [rbp+60h+var_E0], r12d
0x140030e74  xorps   xmm0, xmm0
0x140030e77  mov     [rbp+60h+var_D8], r12d
0x140030e7b  or      r15, 0FFFFFFFFFFFFFFFFh
0x140030e7f  mov     [rbp+60h+var_C0], r12
0x140030e83  xor     r13d, r13d
0x140030e86  mov     [rbp+60h+var_B8], r15
0x140030e8a  xor     r9d, r9d
0x140030e8d  mov     [rbp+60h+var_B0], r13
0x140030e91  movups  [rbp+60h+Source2], xmm0
0x140030e95  xor     r8d, r8d
0x140030e98  mov     [rbp+60h+var_98], r12
0x140030e9c  movups  xmm0, xmmword ptr cs:?NullGuid@@3U_GUID@@A.Data1; _GUID NullGuid ...
0x140030ea3  mov     [rbp+60h+var_90], r12
0x140030ea7  mov     ebx, 80000000h
0x140030eac  mov     [rsp+160h+var_EC], r12d
0x140030eb1  movdqu  [rbp+60h+Source1], xmm0
0x140030eb6  mov     [rsp+160h+var_F0], edi
0x140030eba  mov     [rbp+60h+var_DC], edi
0x140030ebd  mov     [rsp+160h+var_E8], rdi
0x140030ec2  mov     [rsp+160h+var_FF], dil
0x140030ec7  mov     [rsp+160h+var_FE], dil
0x140030ecc  mov     [rsp+160h+var_FD], dil
0x140030ed1  mov     [rsp+160h+var_F4], ax
0x140030ed6  mov     [rbp+60h+var_CC], r9d
0x140030eda  mov     [rbp+60h+var_C8], r8d
0x140030ede  mov     [rbp+60h+var_D0], eax
0x140030ee1  mov     r10, cs:WPP_GLOBAL_Control
0x140030ee8  lea     rax, WPP_GLOBAL_Control
0x140030eef  cmp     byte ptr [rsi+0A5h], 0
0x140030ef6  jnz     loc_140031D1A
0x140030efc  cmp     byte ptr [rsi+0A6h], 0
0x140030f03  jnz     loc_140031D1A
0x140030f09  mov     rcx, [rsi+300h]; hHandle
0x140030f10  xor     edx, edx; dwMilliseconds
0x140030f12  call    cs:__imp_WaitForSingleObject
0x140030f18  cmp     eax, 102h
0x140030f1d  jnz     loc_140031D0C
0x140030f23  mov     rcx, [rsi+2F8h]; hHandle
0x140030f2a  xor     edx, edx; dwMilliseconds
0x140030f2c  call    cs:__imp_WaitForSingleObject
0x140030f32  cmp     eax, 102h
0x140030f37  jnz     loc_140031D0C
0x140030f3d  cmp     dword ptr [rsi+0B8h], 4
0x140030f44  jnz     loc_140031D49
0x140030f4a  mov     rax, [r14+28h]
0x140030f4e  xor     ecx, ecx
0x140030f50  cmp     [rax+4Dh], cl
0x140030f53  jz      short loc_140030F5E
0x140030f55  cmp     [rax+4Ch], cl
0x140030f58  jnz     loc_140031D49
0x140030f5e  mov     rdx, [r14+18h]; tableid
0x140030f62  xor     r9d, r9d; grbit
0x140030f65  mov     [rsp+160h+var_100], cl
0x140030f69  mov     r8d, ebx; cRow
0x140030f6c  mov     [rbp+60h+var_D0], ecx
0x140030f6f  mov     rcx, [r14+8]; sesid
0x140030f73  call    cs:__imp_JetMove
0x140030f79  cmp     eax, 0FFFFF9BFh
0x140030f7e  jz      loc_140031CE6
0x140030f84  cmp     eax, 40Fh
0x140030f89  jz      loc_140031CE6
0x140030f8f  cmp     eax, 0FFFFF9BDh
0x140030f94  jz      loc_140031CE6
0x140030f9a  mov     ebx, 1
0x140030f9f  mov     [rsp+160h+var_F8], ebx
0x140030fa3  cmp     eax, 0FFFFFC07h
0x140030fa8  jz      loc_140030EE1
0x140030fae  test    eax, eax
0x140030fb0  jnz     loc_140031CA2
0x140030fb6  mov     r10, cs:WPP_GLOBAL_Control
0x140030fbd  cmp     dword ptr [rsi+0B8h], 4
0x140030fc4  mov     ebx, [rsp+160h+var_F8]
0x140030fc8  jnz     loc_140030EE8
0x140030fce  cmp     byte ptr [rsi+0A5h], 0
0x140030fd5  jnz     loc_140031C58
0x140030fdb  cmp     byte ptr [rsi+0A6h], 0
0x140030fe2  jnz     loc_140031C58
0x140030fe8  mov     rcx, [rsi+300h]; hHandle
0x140030fef  xor     edx, edx; dwMilliseconds
0x140030ff1  call    cs:__imp_WaitForSingleObject
0x140030ff7  mov     ebx, 102h
0x140030ffc  cmp     eax, ebx
0x140030ffe  jnz     loc_140031C51
0x140031004  mov     rcx, [rsi+2F8h]; hHandle
0x14003100b  xor     edx, edx; dwMilliseconds
0x14003100d  call    cs:__imp_WaitForSingleObject
0x140031013  cmp     eax, ebx
0x140031015  jnz     loc_140031C51
0x14003101b  mov     rax, [r14+28h]
0x14003101f  cmp     byte ptr [rax+4Dh], 0
0x140031023  jz      short loc_14003102F
0x140031025  cmp     byte ptr [rax+4Ch], 0
0x140031029  jnz     loc_140031BC7
0x14003102f  lea     rax, [rbp+60h+var_50]
0x140031033  xor     edx, edx; bool
0x140031035  mov     [rsp+160h+var_120], rax; unsigned __int16 *
0x14003103a  lea     r9, [rsp+160h+var_E8]; __int64 *
0x14003103f  lea     rax, [rsp+160h+var_F4]
0x140031044  mov     rcx, r14; this
0x140031047  mov     [rsp+160h+var_128], rax; unsigned __int16 *
0x14003104c  lea     r8, [rbp+60h+Source2]; struct TE_FILE_ID_128 *
0x140031050  lea     rax, [rsp+160h+var_FD]
0x140031055  mov     [rsp+160h+var_130], rax; unsigned __int8 *
0x14003105a  lea     rax, [rsp+160h+var_FE]
0x14003105f  mov     [rsp+160h+var_138], rax; unsigned __int8 *
0x140031064  lea     rax, [rsp+160h+var_FF]
0x140031069  mov     [rsp+160h+pcbActual], rax; unsigned __int8 *
0x14003106e  call    ?GetCurrentHeatRecord@TieringHeatSession@@QEAAJ_NPEAUTE_FILE_ID_128@@PEA_JPEAE33PEAG4@Z; TieringHeatSession::GetCurrentHeatRecord(bool,TE_FILE_ID_128 *,__int64 *,uchar *,uchar *,uchar *,ushort *,ushort *)
0x140031073  mov     ebx, eax
0x140031075  cmp     eax, 0FFFFFC07h
0x14003107a  jz      loc_140031522
0x140031080  test    eax, eax
0x140031082  jz      short loc_140031103
0x140031084  cmp     eax, 0FFFFFDEFh
0x140031089  jz      short loc_1400310C0
0x14003108b  cmp     eax, 0FFFFFBBCh
0x140031090  jz      short loc_1400310C0
0x140031092  cmp     eax, 0FFFFF8F0h
0x140031097  jz      short loc_1400310C0
0x140031099  cmp     eax, 0FFFFFC0Dh
0x14003109e  jnz     short loc_1400310A7
0x1400310a0  mov     edi, 8007000Eh
0x1400310a5  jmp     short loc_1400310CC
0x1400310a7  neg     eax
0x1400310a9  cmovs   eax, ebx
0x1400310ac  movzx   edi, ax
0x1400310af  mov     eax, ebx
0x1400310b1  and     eax, 8E5E0000h
0x1400310b6  or      edi, eax
0x1400310b8  or      edi, 0E5E0000h
0x1400310be  jmp     short loc_1400310CC
0x1400310c0  mov     ecx, 70h ; 'p'; unsigned int
0x1400310c5  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1400310ca  mov     edi, eax
0x1400310cc  mov     r10, cs:WPP_GLOBAL_Control
0x1400310d3  lea     rax, WPP_GLOBAL_Control
0x1400310da  cmp     r10, rax
0x1400310dd  jz      loc_140031900
0x1400310e3  test    byte ptr [r10+1Ch], 1
0x1400310e8  jz      loc_140031900
0x1400310ee  cmp     byte ptr [r10+19h], 2
0x1400310f3  jb      loc_140031900
0x1400310f9  mov     edx, 47h ; 'G'
0x1400310fe  jmp     loc_1400316C4
0x140031103  mov     r8d, 10h; Length
0x140031109  lea     rdx, [rbp+60h+Source2]; Source2
0x14003110d  lea     rcx, ?NullGuid@@3U_GUID@@A; Source1
0x140031114  call    cs:__imp_RtlCompareMemory
0x14003111a  cmp     rax, 10h
0x14003111e  jz      loc_140031BC7
0x140031124  mov     r8d, 10h; Length
0x14003112a  lea     rdx, [rbp+60h+Source2]; Source2
0x14003112e  lea     rcx, [rbp+60h+Source1]; Source1
0x140031132  call    cs:__imp_RtlCompareMemory
0x140031138  cmp     rax, 10h
0x14003113c  jz      loc_1400312B1
0x140031142  xor     edi, edi
0x140031144  test    r13, r13
0x140031147  jz      short loc_140031159
0x140031149  mov     rcx, r13; Block
0x14003114c  call    cs:__imp_free
0x140031152  mov     r13d, edi
0x140031155  mov     [rbp+60h+var_B0], rdi
0x140031159  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x14003115d  jz      short loc_140031170
0x14003115f  mov     rcx, r15; Handle
0x140031162  call    cs:__imp_NtClose
0x140031168  mov     [rbp+60h+var_B8], 0FFFFFFFFFFFFFFFFh
0x140031170  movaps  xmm0, [rbp+60h+Source2]
0x140031174  lea     rax, [rbp+60h+var_B8]
0x140031178  mov     rdx, [rbp+60h+var_A0]; void *
0x14003117c  lea     r9, [rbp+60h+var_C0]; int *
0x140031180  mov     [rsp+160h+var_128], rax; void **
0x140031185  lea     r8, [rbp+60h+Source1]; struct TE_FILE_ID_128 *
0x140031189  lea     rax, [rbp+60h+var_A8]
0x14003118d  mov     [rbp+60h+var_DC], edi
0x140031190  mov     [rsp+160h+var_130], rax; unsigned __int64 *
0x140031195  mov     rcx, rsi; this
0x140031198  lea     rax, [rsp+160h+var_EC]
0x14003119d  movdqa  [rbp+60h+Source1], xmm0
0x1400311a2  mov     [rsp+160h+var_138], rax; int *
0x1400311a7  lea     rax, [rsp+160h+var_F0]
0x1400311ac  mov     [rsp+160h+pcbActual], rax; int *
0x1400311b1  mov     [rbp+60h+var_D8], edi
0x1400311b4  mov     [rsp+160h+var_F0], edi
0x1400311b8  mov     [rsp+160h+var_EC], edi
0x1400311bc  mov     dword ptr [rbp+60h+var_C0], edi
0x1400311bf  mov     [rbp+60h+var_A8], rdi
0x1400311c3  call    ?GetFileSummaryByFileId@CTieredVolume@@QEAAJPEAXPEBUTE_FILE_ID_128@@PEAH22PEA_KPEAPEAX@Z; CTieredVolume::GetFileSummaryByFileId(void *,TE_FILE_ID_128 const *,int *,int *,int *,unsigned __int64 *,void * *)
0x1400311c8  mov     edi, [rsp+160h+var_F0]
0x1400311cc  mov     [rsp+160h+var_F0], edi
0x1400311d0  test    eax, eax
0x1400311d2  jns     short loc_140031232
0x1400311d4  test    edi, edi
0x1400311d6  jnz     short loc_140031232
0x1400311d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400311df  lea     rax, WPP_GLOBAL_Control
0x1400311e6  cmp     rcx, rax
0x1400311e9  jz      short loc_140031223
0x1400311eb  test    byte ptr [rcx+1Ch], 1
0x1400311ef  jz      short loc_140031223
0x1400311f1  cmp     byte ptr [rcx+19h], 2
0x1400311f5  jb      short loc_140031223
0x1400311f7  mov     r9, qword ptr [rbp+60h+Source1+8]
0x1400311fb  lea     rax, [rsi+2A0h]
0x140031202  mov     rcx, [rcx+10h]
0x140031206  lea     edx, [rdi+48h]
0x140031209  mov     [rsp+160h+var_138], rax
0x14003120e  lea     r8, WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids
0x140031215  mov     rax, qword ptr [rbp+60h+Source1]
0x140031219  mov     [rsp+160h+pcbActual], rax
0x14003121e  call    WPP_SF_iiZ
0x140031223  inc     dword ptr [rsi+138h]
0x140031229  mov     edi, 1
0x14003122e  mov     [rsp+160h+var_F0], edi
0x140031232  mov     r10, cs:WPP_GLOBAL_Control
0x140031239  lea     rcx, WPP_GLOBAL_Control
0x140031240  cmp     r10, rcx
0x140031243  jz      loc_14003154D
0x140031249  test    byte ptr [r10+1Ch], 1
0x14003124e  jz      loc_14003154D
0x140031254  cmp     byte ptr [r10+19h], 5
0x140031259  jb      loc_14003154D
0x14003125f  mov     r9, qword ptr [rbp+60h+Source2+8]
0x140031263  lea     rax, [rsi+2A0h]
0x14003126a  mov     rcx, [r10+10h]
0x14003126e  mov     [rsp+160h+var_110], rax
0x140031273  mov     eax, dword ptr [rbp+60h+var_C0]
0x140031276  mov     dword ptr [rsp+160h+var_118], 0
0x14003127e  mov     dword ptr [rsp+160h+var_120], eax
0x140031282  mov     eax, [rsp+160h+var_EC]
0x140031286  mov     dword ptr [rsp+160h+var_128], edi
0x14003128a  mov     dword ptr [rsp+160h+var_130], eax
0x14003128e  mov     [rsp+160h+var_EC], eax
0x140031292  mov     rax, [rbp+60h+var_A8]
0x140031296  mov     [rsp+160h+var_138], rax
0x14003129b  mov     [rbp+60h+var_C0], rax
0x14003129f  mov     rax, qword ptr [rbp+60h+Source2]
0x1400312a3  mov     [rsp+160h+pcbActual], rax
0x1400312a8  call    WPP_SF_iiiDDDDZ
0x1400312ad  mov     r15, [rbp+60h+var_B8]
0x1400312b1  mov     r10, cs:WPP_GLOBAL_Control
0x1400312b8  lea     rcx, WPP_GLOBAL_Control
0x1400312bf  mov     r11, [rsp+160h+var_E8]
0x1400312c4  cmp     r11, [rbp+60h+var_C0]
0x1400312c8  jnb     loc_140031B18
0x1400312ce  test    edi, edi
0x1400312d0  jnz     loc_140031B18
0x1400312d6  cmp     r10, rcx
0x1400312d9  jz      short loc_140031333
0x1400312db  test    byte ptr [r10+1Ch], 1
0x1400312e0  jz      short loc_140031333
0x1400312e2  cmp     byte ptr [r10+19h], 5
0x1400312e7  jb      short loc_140031333
0x1400312e9  movzx   ecx, [rsp+160h+var_FE]
0x1400312ee  lea     rax, [rsi+2A0h]
0x1400312f5  movzx   r8d, [rsp+160h+var_FF]
0x1400312fb  lea     edx, [rdi+4Ch]
0x1400312fe  mov     r9, qword ptr [rbp+60h+Source2+8]
0x140031302  mov     [rsp+160h+var_120], rax
0x140031307  mov     rax, qword ptr [rbp+60h+Source2]
0x14003130b  mov     dword ptr [rsp+160h+var_128], ecx
0x14003130f  mov     rcx, [r10+10h]
0x140031313  mov     dword ptr [rsp+160h+var_130], r8d
0x140031318  lea     r8, WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids
0x14003131f  mov     [rsp+160h+var_138], r11
0x140031324  mov     [rsp+160h+pcbActual], rax
0x140031329  call    WPP_SF_iiiDDZ
0x14003132e  mov     r11, [rsp+160h+var_E8]
0x140031333  mov     cl, [rsp+160h+var_FE]
0x140031337  mov     r8b, [rsp+160h+var_FD]
0x14003133c  mov     al, cl
0x14003133e  mov     [rsp+160h+var_100], cl
  ... truncated ...
```
