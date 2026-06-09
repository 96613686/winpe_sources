# CTieredVolume::OnDumpTableToDatabase(void)

- ea: `0x140010d1c`
- end: `0x140011b68`
- name: `?OnDumpTableToDatabase@CTieredVolume@@AEAAXXZ`
- size: `3660`
- prototype: `void __fastcall(CTieredVolume *__hidden this)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14000d5e0`

## callees

- `0x140004a68`
- `0x140004aa8`
- `0x140004ef0`
- `0x140005420`
- `0x14000b7f8`
- `0x14000c354`
- `0x14000ccc0`
- `0x140010d1c`
- `0x1400127dc`
- `0x140016470`
- `0x140017760`
- `0x140017930`
- `0x140017c8c`
- `0x140017e78`
- `0x1400188b8`
- `0x1400197b0`
- `0x14001a1d4`
- `0x14001b328`
- `0x14001effc`
- `0x140026e90`
- `0x1400280bc`
- `0x14002beec`
- `0x14002c60c`
- `0x14002eef0`

## import_xrefs

- `msvcrt!free` at `0x140011548`
- `msvcrt!free` at `0x140011548`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140010ff4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140011010`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14001140d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140011427`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14001165d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14001171b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140011735`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140010ff4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140011010`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14001140d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140011427`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14001165d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14001171b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140011735`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140010edd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140010f58`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140011835`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140011a80`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140010edd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140010f58`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140011835`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140011a80`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140010e80`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140010ef1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001174b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400119f7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140010e80`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140010ef1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001174b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400119f7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400110c9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400110c9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140011138`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400114a7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400114b4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140011586`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140011138`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400114a7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400114b4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140011586`

## pseudocode

```c
void __fastcall CTieredVolume::OnDumpTableToDatabase(CTieredVolume *this)
{
  char dwLowDateTime; // r15
  _QWORD *v3; // rcx
  char v4; // bl
  __int64 *v5; // r14
  void **v6; // r13
  RTL_SRWLOCK *v7; // rdi
  RTL_SRWLOCK *v8; // r14
  __int64 v9; // rax
  int v10; // eax
  _QWORD *v11; // rcx
  struct _FILETIME v12; // rbx
  int VolumeInfoFromReservedRecord; // eax
  int v14; // edx
  __int64 v15; // rdx
  __int64 v16; // r8
  int v17; // r15d
  int v18; // r13d
  __int64 v19; // r14
  __int64 v20; // r10
  __int64 *v21; // r11
  __int64 v22; // rcx
  int v23; // eax
  void *v24; // rcx
  void **v25; // r8
  char *v26; // r14
  void **v27; // rdi
  char *v28; // r15
  int v29; // eax
  DWORD v30; // eax
  int v31; // edx
  int v32; // r8d
  int v33; // eax
  char v34; // bl
  _QWORD *v35; // rcx
  int v36; // eax
  int v37; // eax
  int v38; // eax
  char v39[8]; // [rsp+40h] [rbp-C0h] BYREF
  int v40; // [rsp+48h] [rbp-B8h]
  void **v41; // [rsp+50h] [rbp-B0h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v43[32]; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v44; // [rsp+80h] [rbp-80h]
  char v45; // [rsp+82h] [rbp-7Eh]
  __int64 v46; // [rsp+88h] [rbp-78h]
  char v47; // [rsp+90h] [rbp-70h]
  JET_SESID v48[4]; // [rsp+A0h] [rbp-60h] BYREF
  __int16 v49; // [rsp+C0h] [rbp-40h]
  char v50; // [rsp+C2h] [rbp-3Eh]
  __int64 v51; // [rsp+C8h] [rbp-38h]
  char v52; // [rsp+D0h] [rbp-30h]
  struct _FILETIME pftDueTime; // [rsp+150h] [rbp+50h] BYREF
  bool v54; // [rsp+158h] [rbp+58h] BYREF
  int v55; // [rsp+160h] [rbp+60h]
  __int64 *v56; // [rsp+168h] [rbp+68h]

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "CTieredVolume::OnDumpTableToDatabase";
  CHResultImp::CHResultImp((CHResultImp *)v39);
  dwLowDateTime = 0;
  v54 = 0;
  SystemTimeAsFileTime = 0;
  pftDueTime = 0;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      205,
      &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
      *((unsigned int *)this + 32));
    v3 = WPP_GLOBAL_Control;
  }
  LOBYTE(v48[0]) = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v43[0] = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  if ( *((_BYTE *)this + 165) )
  {
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 1) != 0 && *((_BYTE *)v3 + 25) >= 5u )
    {
      WPP_SF_d(v3[2], 206, &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids, *((unsigned int *)this + 32));
      v3 = WPP_GLOBAL_Control;
    }
    if ( *((_DWORD *)this + 46) != 1 )
    {
      if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 1) != 0 && *((_BYTE *)v3 + 25) >= 4u )
        WPP_SF_Z(v3[2], 207, &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids, (char *)this + 672);
      *((_DWORD *)this + 46) = 1;
    }
    goto LABEL_228;
  }
  v4 = 0;
  v5 = 0;
  v56 = 0;
  v6 = 0;
  v41 = 0;
  v7 = (RTL_SRWLOCK *)((char *)this + 24);
  AcquireSRWLockExclusive((PSRWLOCK)this + 3);
  if ( !*((_BYTE *)this + 724) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        208,
        &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
        *((unsigned int *)this + 32));
    }
    v4 = 1;
    *((_BYTE *)this + 724) = 1;
  }
  if ( this != (CTieredVolume *)-24LL )
    ReleaseSRWLockExclusive((PSRWLOCK)this + 3);
  if ( v4 )
  {
    v8 = (RTL_SRWLOCK *)*((_QWORD *)this + 94);
    AcquireSRWLockExclusive(v8);
    v56 = (__int64 *)*((_QWORD *)this + 140);
    v6 = (void **)*((_QWORD *)this + 141);
    v41 = v6;
    *((_DWORD *)this + 419) = 0;
    v9 = ((unsigned __int8)*((_DWORD *)this + 250) - 1) & 1;
    *((_DWORD *)this + 250) = v9;
    *((_QWORD *)this + 140) = (char *)this + 48 * v9 + 1008;
    *((_QWORD *)this + 141) = (char *)this + 8 * v9 + 1104;
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
    v5 = v56;
  }
  v10 = CTieredVolume::ReferenceVolume(this, 1);
  if ( v10 >= 0 )
  {
    LOBYTE(pftDueTime.dwLowDateTime) = 0;
    v54 = 1;
    if ( !v4 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      {
        goto LABEL_34;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        210,
        &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
        *((unsigned int *)this + 32));
LABEL_55:
      v11 = WPP_GLOBAL_Control;
      goto LABEL_34;
    }
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v12 = SystemTimeAsFileTime;
    if ( *((_QWORD *)this + 12) < 2u )
    {
      *((_DWORD *)this + 419) = *(_DWORD *)(*((_QWORD *)this + 2) + 144LL);
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          211,
          &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
          *((unsigned int *)this + 32),
          *((_DWORD *)this + 24));
      }
      goto LABEL_88;
    }
    VolumeInfoFromReservedRecord = TieringJetSession::Initialize((TieringJetSession *)v48, (RTL_SRWLOCK **)this + 148);
    v40 = VolumeInfoFromReservedRecord;
    if ( VolumeInfoFromReservedRecord < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_88;
      }
      v14 = 212;
LABEL_87:
      WPP_SF_Zd(
        v11[2],
        v14,
        (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
        (_DWORD)this + 672,
        VolumeInfoFromReservedRecord);
LABEL_88:
      dwLowDateTime = 1;
LABEL_89:
      CTieredVolume::CleanUpInMemoryTree((__int64)v11, v5, v6);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          229,
          &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
          *((unsigned int *)this + 32));
      }
      *((_BYTE *)this + 724) = 0;
      goto LABEL_55;
    }
    VolumeInfoFromReservedRecord = TieringJetSession::OpenJetTable((TieringJetSession *)v48, 0);
    v40 = VolumeInfoFromReservedRecord;
    if ( VolumeInfoFromReservedRecord < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_88;
      }
      v14 = 213;
      goto LABEL_87;
    }
    if ( !*((_BYTE *)this + 729) )
    {
      VolumeInfoFromReservedRecord = TieringJetSession::Initialize((TieringJetSession *)v43, (RTL_SRWLOCK **)this + 168);
      v40 = VolumeInfoFromReservedRecord;
      if ( VolumeInfoFromReservedRecord < 0 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_88;
        }
        v14 = 214;
        goto LABEL_87;
      }
      VolumeInfoFromReservedRecord = TieringJetSession::OpenJetTable((TieringJetSession *)v43, 0);
      v40 = VolumeInfoFromReservedRecord;
      if ( VolumeInfoFromReservedRecord < 0 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_88;
        }
        v14 = 215;
        goto LABEL_87;
      }
    }
    VolumeInfoFromReservedRecord = TieringHeatSession::GetVolumeInfoFromReservedRecord(
                                     (TieringHeatSession *)v48,
                                     *((_BYTE *)this + 720) == 0);
    v40 = VolumeInfoFromReservedRecord;
    if ( VolumeInfoFromReservedRecord < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_88;
      }
      v14 = 216;
      goto LABEL_87;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_P(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, v16, v5[1]);
    }
    v17 = 0;
    v55 = 0;
    v18 = 0;
    v19 = *v5;
    if ( v19 && v19 != v56[5] )
    {
      while ( *(_QWORD *)(v19 + 40) != v56[5] )
        v19 = *(_QWORD *)(v19 + 40);
      while ( v19 )
      {
        if ( *((_BYTE *)this + 165)
          || *((_BYTE *)this + 166)
          || WaitForSingleObject(*((HANDLE *)this + 96), 0) != 258
          || WaitForSingleObject(*((HANDLE *)this + 95), 0) != 258 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_Z(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              252,
              &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
              (char *)this + 672);
          }
          break;
        }
        if ( *(_BYTE *)(v51 + 77) && *(_BYTE *)(v51 + 76) )
          break;
        v19 = ATL::CRBTree<_FILE_EXTENT_IDENTIFIER,_FILE_EXTENT_DATA *,ATL::CElementTraits<_FILE_EXTENT_IDENTIFIER>,ATL::CElementTraits<_FILE_EXTENT_DATA *>>::Successor(
                v56,
                v19);
        v22 = *(_QWORD *)(v20 + 24);
        v55 = ++v17;
        if ( (*(_BYTE *)v22 & 1) != 0 )
          ++*((_DWORD *)this + 81);
        TieringHeatSession::AddOrUpdateHeatRecord(
          (TieringHeatSession *)v48,
          (const struct TE_FILE_ID_128 *)(v20 + 8),
          *v21,
          *(unsigned __int16 *)(v22 + 2),
          *(_BYTE *)v22 & 1);
      }
    }
    GetSystemTimeAsFileTime((LPFILETIME)this + 21);
    GetSystemTimeAsFileTime((LPFILETIME)this + 22);
    v23 = TieringHeatSession::SetVolumeInfoOnReservedRecord((TieringHeatSession *)v48, 1, 0);
    v40 = v23;
    if ( v23 < 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Zd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          218,
          (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
          (_DWORD)this + 672,
          v23);
      }
    }
    v25 = v41;
    v26 = (char *)*v41;
    if ( *v41 )
    {
      v27 = v41;
      do
      {
        v28 = *(char **)v26;
        ++v18;
        TieringHeatSession::DeleteRecordsWithGivenFileId(v48, (const struct TE_FILE_ID_128 *)(v26 + 8), 0);
        if ( !*((_BYTE *)this + 729) )
          TieringPinnedSession::ClearPinnedRecordGivenFileId(
            (TieringPinnedSession *)v43,
            (const struct TE_FILE_ID_128 *)(v26 + 8));
        free(v26);
        *v27 = v28;
        v26 = v28;
      }
      while ( v28 );
      v7 = (RTL_SRWLOCK *)((char *)this + 24);
      v17 = v55;
      v25 = v41;
    }
    if ( (unsigned int)(v17 + v18) > *((_DWORD *)this + 140) )
      *((_DWORD *)this + 140) = v17 + v18;
    CTieredVolume::CleanUpInMemoryTree((__int64)v24, v56, v25);
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    *((_DWORD *)this + 139) += (*(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&v12) / 0x23C34600uLL;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        219,
        &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
        *((unsigned int *)this + 32));
    }
    *((_BYTE *)this + 724) = 0;
    v29 = TieringJetSession::CloseJetTable((TieringJetSession *)v48, 1);
    v40 = v29;
    if ( v29 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_139;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_135:
        if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 && *((_BYTE *)v11 + 25) >= 4u )
        {
          v30 = WaitForSingleObject(*((HANDLE *)this + 96), 0);
          WPP_SF_DDDZ(*((_QWORD *)WPP_GLOBAL_Control + 2), v31, v32, v17, v18, v30 == 258, (__int64)this + 672);
          v11 = WPP_GLOBAL_Control;
        }
LABEL_139:
        if ( !*((_BYTE *)this + 729) )
        {
          v33 = TieringJetSession::CloseJetTable((TieringJetSession *)v43, 1);
          v40 = v33;
          if ( v33 >= 0 )
          {
LABEL_145:
            v11 = WPP_GLOBAL_Control;
            goto LABEL_146;
          }
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_Zd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              222,
              (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
              (_DWORD)this + 672,
              v33);
            goto LABEL_145;
          }
        }
LABEL_146:
        if ( !*((_BYTE *)this + 165) && !*((_BYTE *)this + 166) )
        {
          if ( WaitForSingleObject(*((HANDLE *)this + 96), 0) == 258
            && WaitForSingleObject(*((HANDLE *)this + 95), 0) == 258 )
          {
            v34 = 1;
            AcquireSRWLockExclusive(v7);
            if ( *((_DWORD *)this + 46) == 7 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                WPP_SF_dZ(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  223,
                  (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
                  *((_DWORD *)this + 179),
                  (__int64)this + 672);
              }
              if ( (int)--*((_DWORD *)this + 179) <= 0 )
              {
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                {
                  WPP_SF_Z(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    224,
                    &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
                    (char *)this + 672);
                }
                *((_DWORD *)this + 46) = 1;
              }
            }
            if ( !*((_BYTE *)this + 725) )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_Z(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  225,
                  &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
                  (char *)this + 672);
              }
              *((_BYTE *)this + 725) = 1;
              v34 = 0;
            }
            if ( v7 )
              ReleaseSRWLockExclusive(v7);
            if ( v34 )
              goto LABEL_187;
            if ( *((_DWORD *)this + 46) != 7 )
            {
              v35 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_dZ(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  226,
                  (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
                  *((unsigned __int8 *)this + 720),
                  (__int64)this + 672);
                v35 = WPP_GLOBAL_Control;
              }
              if ( !*((_BYTE *)this + 720) )
                goto LABEL_182;
              *((_BYTE *)this + 720) = 0;
              v36 = CTieredVolume::ProcessVolumeTables(this, &v54);
              if ( v36 < 0 )
              {
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                {
LABEL_186:
                  *((_BYTE *)this + 725) = 0;
                  goto LABEL_187;
                }
                if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
LABEL_182:
                  if ( v35 != &WPP_GLOBAL_Control && (*((_BYTE *)v35 + 28) & 1) != 0 && *((_BYTE *)v35 + 25) >= 5u )
                    WPP_SF_Z(v35[2], 228, &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids, (char *)this + 672);
                  goto LABEL_186;
                }
                WPP_SF_Zd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  227,
                  (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
                  (_DWORD)this + 672,
                  v36);
              }
            }
            v35 = WPP_GLOBAL_Control;
            goto LABEL_182;
          }
          v11 = WPP_GLOBAL_Control;
        }
        if ( v11 == &WPP_GLOBAL_Control || (*((_BYTE *)v11 + 28) & 1) == 0 || *((_BYTE *)v11 + 25) < 5u )
          goto LABEL_188;
        WPP_SF_Z(v11[2], 252, &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids, (char *)this + 672);
LABEL_187:
        v11 = WPP_GLOBAL_Control;
LABEL_188:
        dwLowDateTime = pftDueTime.dwLowDateTime;
        goto LABEL_34;
      }
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        220,
        (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
        (_DWORD)this + 672,
        v29);
    }
    v11 = WPP_GLOBAL_Control;
    goto LABEL_135;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      209,
      &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
      *((unsigned int *)this + 32),
      v10);
    v11 = WPP_GLOBAL_Control;
  }
  LOBYTE(pftDueTime.dwLowDateTime) = 1;
  dwLowDateTime = 1;
  if ( v4 )
    goto LABEL_89;
LABEL_34:
  if ( *((_BYTE *)this + 165) || *((_BYTE *)this + 166) )
    goto LABEL_199;
  if ( WaitForSingleObject(*((HANDLE *)this + 96), 0) != 258 || WaitForSingleObject(*((HANDLE *)this + 95), 0) != 258 )
  {
    v11 = WPP_GLOBAL_Control;
LABEL_199:
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 && *((_BYTE *)v11 + 25) >= 5u )
      WPP_SF_Z(v11[2], 252, &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids, (char *)this + 672);
    AcquireSRWLockExclusive(v7);
    if ( *((_DWORD *)this + 46) != 1 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Z(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          232,
          &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
          (char *)this + 672);
      }
      *((_DWORD *)this + 46) = 1;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Z(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        233,
        &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
        (char *)this + 672);
    }
    if ( v7 )
      ReleaseSRWLockExclusive(v7);
    goto LABEL_215;
  }
  if ( dwLowDateTime && *((_DWORD *)this + 46) != 1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Z(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        230,
        &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
        (char *)this + 672);
    }
    *((_DWORD *)this + 46) = 1;
  }
  pftDueTime.dwLowDateTime = -1640261632;
  pftDueTime.dwHighDateTime = -9;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_dZ(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      231,
      (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
      3600,
      (__int64)this + 672);
  }
  SetThreadpoolTimer(*((PTP_TIMER *)this + 114), &pftDueTime, 0, 0x186A0u);
LABEL_215:
  v37 = TieringJetSession::CloseJetTable((TieringJetSession *)v48, 1);
  v40 = v37;
  if ( v37 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Zd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      234,
      (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
      (_DWORD)this + 672,
      v37);
  }
  if ( !*((_BYTE *)this + 729) )
  {
    v38 = TieringJetSession::CloseJetTable((TieringJetSession *)v43, 1);
    v40 = v38;
    if ( v38 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        235,
        (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
        (_DWORD)this + 672,
        v38);
    }
  }
  if ( v54 )
    CTieredVolume::DereferenceVolume((RTL_SRWLOCK *)this);
LABEL_228:
  TieringJetSession::~TieringJetSession((TieringJetSession *)v43);
  TieringJetSession::~TieringJetSession((TieringJetSession *)v48);
  CHResultImp::~CHResultImp((CHResultImp *)v39);
}

```

## disassembly

```asm
0x140010d1c  push    rbp
0x140010d1e  push    rbx
0x140010d1f  push    rsi
0x140010d20  push    rdi
0x140010d21  push    r12
0x140010d23  push    r13
0x140010d25  push    r14
0x140010d27  push    r15
0x140010d29  lea     rbp, [rsp-8]
0x140010d2e  sub     rsp, 108h
0x140010d35  mov     rsi, rcx
0x140010d38  mov     ecx, 8
0x140010d3d  mov     rax, gs:58h
0x140010d46  mov     rdx, [rax]
0x140010d49  lea     rax, aCtieredvolumeO_0; "CTieredVolume::OnDumpTableToDatabase"
0x140010d50  mov     [rcx+rdx], rax
0x140010d54  lea     rcx, [rsp+140h+var_100]; this
0x140010d59  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x140010d5e  nop
0x140010d5f  xor     r15d, r15d
0x140010d62  mov     [rbp+40h+arg_8], r15b
0x140010d66  mov     qword ptr [rsp+140h+SystemTimeAsFileTime.dwLowDateTime], r15
0x140010d6b  mov     qword ptr [rbp+40h+pftDueTime.dwLowDateTime], r15
0x140010d6f  lea     rax, WPP_GLOBAL_Control
0x140010d76  lea     rdi, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x140010d7d  lea     ebx, [r15+1]
0x140010d81  mov     rcx, cs:WPP_GLOBAL_Control
0x140010d88  cmp     rcx, rax
0x140010d8b  jz      short loc_140010DBE
0x140010d8d  test    [rcx+1Ch], bl
0x140010d90  jz      short loc_140010DBE
0x140010d92  cmp     byte ptr [rcx+19h], 4
0x140010d96  jb      short loc_140010DBE
0x140010d98  mov     edx, 0CDh
0x140010d9d  mov     r9d, [rsi+80h]
0x140010da4  mov     r8, rdi
0x140010da7  mov     rcx, [rcx+10h]
0x140010dab  call    WPP_SF_d
0x140010db0  mov     rcx, cs:WPP_GLOBAL_Control
0x140010db7  lea     rax, WPP_GLOBAL_Control
0x140010dbe  mov     byte ptr [rbp+40h+var_A0], r15b
0x140010dc2  mov     [rbp+40h+var_80], r15w
0x140010dc7  mov     [rbp+40h+var_7E], r15b
0x140010dcb  mov     [rbp+40h+var_78], r15
0x140010dcf  mov     [rbp+40h+var_70], r15b
0x140010dd3  mov     [rsp+140h+var_E0], r15b
0x140010dd8  mov     [rbp+40h+var_C0], r15w
0x140010ddd  mov     [rbp+40h+var_BE], r15b
0x140010de1  mov     [rbp+40h+var_B8], r15
0x140010de5  mov     [rbp+40h+var_B0], r15b
0x140010de9  cmp     [rsi+0A5h], r15b
0x140010df0  jz      short loc_140010E67
0x140010df2  cmp     rcx, rax
0x140010df5  jz      short loc_140010E28
0x140010df7  test    [rcx+1Ch], bl
0x140010dfa  jz      short loc_140010E28
0x140010dfc  cmp     byte ptr [rcx+19h], 5
0x140010e00  jb      short loc_140010E28
0x140010e02  mov     edx, 0CEh
0x140010e07  mov     r9d, [rsi+80h]
0x140010e0e  mov     r8, rdi
0x140010e11  mov     rcx, [rcx+10h]
0x140010e15  call    WPP_SF_d
0x140010e1a  mov     rcx, cs:WPP_GLOBAL_Control
0x140010e21  lea     rax, WPP_GLOBAL_Control
0x140010e28  cmp     [rsi+0B8h], ebx
0x140010e2e  jz      loc_140011B35
0x140010e34  cmp     rcx, rax
0x140010e37  jz      short loc_140010E5C
0x140010e39  test    [rcx+1Ch], bl
0x140010e3c  jz      short loc_140010E5C
0x140010e3e  cmp     byte ptr [rcx+19h], 4
0x140010e42  jb      short loc_140010E5C
0x140010e44  lea     r9, [rsi+2A0h]
0x140010e4b  mov     edx, 0CFh
0x140010e50  mov     r8, rdi
0x140010e53  mov     rcx, [rcx+10h]
0x140010e57  call    WPP_SF_Z
0x140010e5c  mov     [rsi+0B8h], ebx
0x140010e62  jmp     loc_140011B35
0x140010e67  mov     bl, r15b
0x140010e6a  mov     r14, r15
0x140010e6d  mov     [rbp+40h+arg_18], r15
0x140010e71  mov     r13, r15
0x140010e74  mov     [rsp+140h+var_F0], r15
0x140010e79  lea     rdi, [rsi+18h]
0x140010e7d  mov     rcx, rdi; SRWLock
0x140010e80  call    cs:__imp_AcquireSRWLockExclusive
0x140010e86  mov     r12b, 5
0x140010e89  cmp     [rsi+2D4h], r15b
0x140010e90  jnz     short loc_140010ED5
0x140010e92  mov     rcx, cs:WPP_GLOBAL_Control
0x140010e99  lea     rax, WPP_GLOBAL_Control
0x140010ea0  cmp     rcx, rax
0x140010ea3  jz      short loc_140010ECD
0x140010ea5  test    byte ptr [rcx+1Ch], 1
0x140010ea9  jz      short loc_140010ECD
0x140010eab  cmp     [rcx+19h], r12b
0x140010eaf  jb      short loc_140010ECD
0x140010eb1  mov     edx, 0D0h
0x140010eb6  mov     r9d, [rsi+80h]
0x140010ebd  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x140010ec4  mov     rcx, [rcx+10h]
0x140010ec8  call    WPP_SF_d
0x140010ecd  mov     bl, 1
0x140010ecf  mov     [rsi+2D4h], bl
0x140010ed5  test    rdi, rdi
0x140010ed8  jz      short loc_140010EE3
0x140010eda  mov     rcx, rdi; SRWLock
0x140010edd  call    cs:__imp_ReleaseSRWLockExclusive
0x140010ee3  test    bl, bl
0x140010ee5  jz      short loc_140010F62
0x140010ee7  mov     r14, [rsi+2F0h]
0x140010eee  mov     rcx, r14; SRWLock
0x140010ef1  call    cs:__imp_AcquireSRWLockExclusive
0x140010ef7  mov     rax, [rsi+460h]
0x140010efe  mov     [rbp+40h+arg_18], rax
0x140010f02  mov     r13, [rsi+468h]
0x140010f09  mov     [rsp+140h+var_F0], r13
0x140010f0e  mov     [rsi+68Ch], r15d
0x140010f15  mov     eax, [rsi+3E8h]
0x140010f1b  dec     eax
0x140010f1d  and     eax, 1
0x140010f20  mov     edx, eax
0x140010f22  mov     [rsi+3E8h], edx
0x140010f28  add     rax, 15h
0x140010f2c  lea     rax, [rax+rax*2]
0x140010f30  shl     rax, 4
0x140010f34  add     rax, rsi
0x140010f37  mov     [rsi+460h], rax
0x140010f3e  lea     rax, [rsi+450h]
0x140010f45  lea     rax, [rax+rdx*8]
0x140010f49  mov     [rsi+468h], rax
0x140010f50  test    r14, r14
0x140010f53  jz      short loc_140010F5E
0x140010f55  mov     rcx, r14; SRWLock
0x140010f58  call    cs:__imp_ReleaseSRWLockExclusive
0x140010f5e  mov     r14, [rbp+40h+arg_18]
0x140010f62  mov     dl, 1; bool
0x140010f64  mov     rcx, rsi; this
0x140010f67  call    ?ReferenceVolume@CTieredVolume@@QEAAJ_N@Z; CTieredVolume::ReferenceVolume(bool)
0x140010f6c  test    eax, eax
0x140010f6e  jns     loc_1400110D4
0x140010f74  mov     rcx, cs:WPP_GLOBAL_Control
0x140010f7b  lea     rdx, WPP_GLOBAL_Control
0x140010f82  cmp     rcx, rdx
0x140010f85  jz      short loc_140010FBA
0x140010f87  test    byte ptr [rcx+1Ch], 1
0x140010f8b  jz      short loc_140010FBA
0x140010f8d  cmp     byte ptr [rcx+19h], 2
0x140010f91  jb      short loc_140010FBA
0x140010f93  mov     edx, 0D1h
0x140010f98  mov     dword ptr [rsp+140h+var_120], eax
0x140010f9c  mov     r9d, [rsi+80h]
0x140010fa3  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x140010faa  mov     rcx, [rcx+10h]
0x140010fae  call    WPP_SF_Dd
0x140010fb3  mov     rcx, cs:WPP_GLOBAL_Control
0x140010fba  mov     byte ptr [rbp+40h+pftDueTime.dwLowDateTime], 1
0x140010fbe  mov     r15b, byte ptr [rbp+40h+pftDueTime.dwLowDateTime]
0x140010fc2  test    bl, bl
0x140010fc4  jnz     loc_140011335
0x140010fca  lea     r14, WPP_GLOBAL_Control
0x140010fd1  cmp     byte ptr [rsi+0A5h], 0
0x140010fd8  jnz     loc_1400119C7
0x140010fde  cmp     byte ptr [rsi+0A6h], 0
0x140010fe5  jnz     loc_1400119C7
0x140010feb  xor     edx, edx; dwMilliseconds
0x140010fed  mov     rcx, [rsi+300h]; hHandle
0x140010ff4  call    cs:__imp_WaitForSingleObject
0x140010ffa  mov     ebx, 102h
0x140010fff  cmp     eax, ebx
0x140011001  jnz     loc_1400119C0
0x140011007  xor     edx, edx; dwMilliseconds
0x140011009  mov     rcx, [rsi+2F8h]; hHandle
0x140011010  call    cs:__imp_WaitForSingleObject
0x140011016  cmp     eax, ebx
0x140011018  jnz     loc_1400119C0
0x14001101e  test    r15b, r15b
0x140011021  jz      short loc_140011068
0x140011023  cmp     dword ptr [rsi+0B8h], 1
0x14001102a  jz      short loc_140011068
0x14001102c  mov     rcx, cs:WPP_GLOBAL_Control
0x140011033  cmp     rcx, r14
0x140011036  jz      short loc_14001105E
0x140011038  test    byte ptr [rcx+1Ch], 1
0x14001103c  jz      short loc_14001105E
0x14001103e  cmp     byte ptr [rcx+19h], 4
0x140011042  jb      short loc_14001105E
0x140011044  lea     r9, [rsi+2A0h]
0x14001104b  lea     edx, [rbx-1Ch]
0x14001104e  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x140011055  mov     rcx, [rcx+10h]
0x140011059  call    WPP_SF_Z
0x14001105e  mov     dword ptr [rsi+0B8h], 1
0x140011068  mov     [rbp+40h+pftDueTime.dwLowDateTime], 9E3B9800h
0x14001106f  mov     [rbp+40h+pftDueTime.dwHighDateTime], 0FFFFFFF7h
0x140011076  mov     rcx, cs:WPP_GLOBAL_Control
0x14001107d  cmp     rcx, r14
0x140011080  jz      short loc_1400110B5
0x140011082  test    byte ptr [rcx+1Ch], 1
0x140011086  jz      short loc_1400110B5
0x140011088  cmp     byte ptr [rcx+19h], 4
0x14001108c  jb      short loc_1400110B5
0x14001108e  lea     rax, [rsi+2A0h]
0x140011095  mov     edx, 0E7h
0x14001109a  mov     qword ptr [rsp+140h+var_120], rax
0x14001109f  mov     r9d, 0E10h
0x1400110a5  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x1400110ac  mov     rcx, [rcx+10h]
0x1400110b0  call    WPP_SF_dZ
0x1400110b5  mov     r9d, 186A0h; msWindowLength
0x1400110bb  xor     r8d, r8d; msPeriod
0x1400110be  lea     rdx, [rbp+40h+pftDueTime]; pftDueTime
0x1400110c2  mov     rcx, [rsi+390h]; pti
0x1400110c9  call    cs:__imp_SetThreadpoolTimer
0x1400110cf  jmp     loc_140011A86
0x1400110d4  mov     byte ptr [rbp+40h+pftDueTime.dwLowDateTime], r15b
0x1400110d8  mov     [rbp+40h+arg_8], 1
0x1400110dc  test    bl, bl
0x1400110de  jnz     short loc_140011133
0x1400110e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400110e7  lea     r14, WPP_GLOBAL_Control
0x1400110ee  cmp     rcx, r14
0x1400110f1  jz      loc_140010FD1
0x1400110f7  test    byte ptr [rcx+1Ch], 1
0x1400110fb  jz      loc_140010FD1
0x140011101  cmp     byte ptr [rcx+19h], 3
0x140011105  jb      loc_140010FD1
0x14001110b  mov     edx, 0D2h
0x140011110  mov     r9d, [rsi+80h]
0x140011117  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x14001111e  mov     rcx, [rcx+10h]
0x140011122  call    WPP_SF_d
0x140011127  mov     rcx, cs:WPP_GLOBAL_Control
0x14001112e  jmp     loc_140010FD1
0x140011133  lea     rcx, [rsp+140h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140011138  call    cs:__imp_GetSystemTimeAsFileTime
0x14001113e  mov     rbx, qword ptr [rsp+140h+SystemTimeAsFileTime.dwLowDateTime]
0x140011143  cmp     qword ptr [rsi+60h], 2
0x140011148  jnb     short loc_1400111AD
0x14001114a  mov     rax, [rsi+10h]
0x14001114e  mov     ecx, [rax+90h]
0x140011154  mov     [rsi+68Ch], ecx
0x14001115a  mov     rcx, cs:WPP_GLOBAL_Control
0x140011161  lea     rax, WPP_GLOBAL_Control
0x140011168  cmp     rcx, rax
0x14001116b  jz      loc_140011332
0x140011171  test    byte ptr [rcx+1Ch], 1
0x140011175  jz      loc_140011332
0x14001117b  cmp     [rcx+19h], r12b
0x14001117f  jb      loc_140011332
0x140011185  mov     edx, 0D3h
0x14001118a  mov     eax, [rsi+60h]
0x14001118d  mov     dword ptr [rsp+140h+var_120], eax
0x140011191  mov     r9d, [rsi+80h]
0x140011198  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x14001119f  mov     rcx, [rcx+10h]
0x1400111a3  call    WPP_SF_Dd
0x1400111a8  jmp     loc_140011332
0x1400111ad  lea     rdx, [rsi+4A0h]; struct TieringJetDatabase *
0x1400111b4  lea     rcx, [rbp+40h+var_A0]; this
0x1400111b8  call    ?Initialize@TieringJetSession@@QEAAJPEAVTieringJetDatabase@@@Z; TieringJetSession::Initialize(TieringJetDatabase *)
0x1400111bd  mov     [rsp+140h+var_F8], eax
0x1400111c1  test    eax, eax
0x1400111c3  jns     short loc_1400111FA
0x1400111c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400111cc  lea     rdx, WPP_GLOBAL_Control
0x1400111d3  cmp     rcx, rdx
0x1400111d6  jz      loc_140011332
0x1400111dc  test    byte ptr [rcx+1Ch], 1
0x1400111e0  jz      loc_140011332
0x1400111e6  cmp     byte ptr [rcx+19h], 2
0x1400111ea  jb      loc_140011332
0x1400111f0  mov     edx, 0D4h
0x1400111f5  jmp     loc_140011317
0x1400111fa  xor     edx, edx; bool
0x1400111fc  lea     rcx, [rbp+40h+var_A0]; this
0x140011200  call    ?OpenJetTable@TieringJetSession@@QEAAJ_N@Z; TieringJetSession::OpenJetTable(bool)
0x140011205  mov     [rsp+140h+var_F8], eax
0x140011209  test    eax, eax
0x14001120b  jns     short loc_140011242
0x14001120d  mov     rcx, cs:WPP_GLOBAL_Control
0x140011214  lea     rdx, WPP_GLOBAL_Control
0x14001121b  cmp     rcx, rdx
0x14001121e  jz      loc_140011332
0x140011224  test    byte ptr [rcx+1Ch], 1
0x140011228  jz      loc_140011332
0x14001122e  cmp     byte ptr [rcx+19h], 2
0x140011232  jb      loc_140011332
0x140011238  mov     edx, 0D5h
0x14001123d  jmp     loc_140011317
0x140011242  cmp     byte ptr [rsi+2D9h], 0
0x140011249  jnz     loc_1400112D4
0x14001124f  lea     rdx, [rsi+540h]; struct TieringJetDatabase *
0x140011256  lea     rcx, [rsp+140h+var_E0]; this
0x14001125b  call    ?Initialize@TieringJetSession@@QEAAJPEAVTieringJetDatabase@@@Z; TieringJetSession::Initialize(TieringJetDatabase *)
0x140011260  mov     [rsp+140h+var_F8], eax
0x140011264  test    eax, eax
0x140011266  jns     short loc_14001129A
  ... truncated ...
```
