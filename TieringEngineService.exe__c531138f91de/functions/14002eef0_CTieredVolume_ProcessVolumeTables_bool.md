# CTieredVolume::ProcessVolumeTables(bool *)

- ea: `0x14002eef0`
- end: `0x14002fd8c`
- name: `?ProcessVolumeTables@CTieredVolume@@AEAAJPEA_N@Z`
- size: `3740`
- prototype: `__int64 __fastcall(CTieredVolume *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `21`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140010d1c`

## callees

- `0x140001714`
- `0x140004aa8`
- `0x140004ef0`
- `0x140005420`
- `0x14000b7f8`
- `0x1400127dc`
- `0x1400164c8`
- `0x140017e78`
- `0x1400188b8`
- `0x1400197b0`
- `0x14001a1d4`
- `0x14001b328`
- `0x14002dff4`
- `0x14002e86c`
- `0x14002eef0`
- `0x14002fd94`
- `0x140030e10`
- `0x140031e04`
- `0x1400351f8`
- `0x1400357f0`
- `0x140036390`

## import_xrefs

- `ntdll!NtOpenFile` at `0x14002f1f6`
- `ntdll!NtOpenFile` at `0x14002f1f6`
- `ntdll!RtlGetThreadErrorMode` at `0x14002f10b`
- `ntdll!RtlGetThreadErrorMode` at `0x14002f10b`
- `ntdll!RtlSetThreadErrorMode` at `0x14002f11b`
- `ntdll!RtlSetThreadErrorMode` at `0x14002fd22`
- `ntdll!RtlSetThreadErrorMode` at `0x14002f11b`
- `ntdll!RtlSetThreadErrorMode` at `0x14002fd22`
- `ntdll!NtClose` at `0x14002fd33`
- `ntdll!NtClose` at `0x14002fd33`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14002f19f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14002f207`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14002f7a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14002f19f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14002f207`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14002f7a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002fd0e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002fd0e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14002f136`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14002f774`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14002f136`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14002f774`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14002fc34`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14002fc34`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x14002f015`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x14002fbd2`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x14002f015`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x14002fbd2`

## pseudocode

```c
__int64 __fastcall CTieredVolume::ProcessVolumeTables(CTieredVolume *this, bool *a2)
{
  __int64 v4; // r8
  __int64 v5; // r9
  int v6; // ebx
  ULONG ThreadErrorMode; // eax
  NTSTATUS v8; // eax
  char v9; // cl
  NTSTATUS v10; // r14d
  int VolumeBitmapInfoByTier; // eax
  _QWORD *v12; // rcx
  int v13; // edx
  int v14; // eax
  int v15; // eax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  int v18; // eax
  _QWORD *v19; // rcx
  char *v20; // r9
  __int64 v21; // rdx
  int v22; // eax
  unsigned __int64 v23; // r14
  __int64 v24; // r8
  _QWORD *v25; // rdx
  int v26; // eax
  int v27; // ebx
  int v28; // r9d
  _BYTE *v29; // rcx
  int v30; // edx
  int v31; // eax
  int v32; // eax
  __int64 v33; // r8
  __int64 v34; // r9
  _BYTE v36[8]; // [rsp+40h] [rbp-C0h] BYREF
  int v37; // [rsp+48h] [rbp-B8h]
  ULONG OldMode; // [rsp+50h] [rbp-B0h] BYREF
  char v39; // [rsp+54h] [rbp-ACh]
  void *FileHandle; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v41; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v42; // [rsp+68h] [rbp-98h] BYREF
  __int64 v43; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v44; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v45; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v47; // [rsp+90h] [rbp-70h] BYREF
  __int64 v48; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v49[32]; // [rsp+A0h] [rbp-60h] BYREF
  __int16 v50; // [rsp+C0h] [rbp-40h]
  char v51; // [rsp+C2h] [rbp-3Eh]
  __int64 v52; // [rsp+C8h] [rbp-38h]
  char v53; // [rsp+D0h] [rbp-30h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v55[32]; // [rsp+110h] [rbp+10h] BYREF
  __int16 v56; // [rsp+130h] [rbp+30h]
  char v57; // [rsp+132h] [rbp+32h]
  TieringJetDatabase *v58; // [rsp+138h] [rbp+38h]
  char v59; // [rsp+140h] [rbp+40h]
  _BYTE v60[32]; // [rsp+170h] [rbp+70h] BYREF
  __int16 v61; // [rsp+190h] [rbp+90h]
  char v62; // [rsp+192h] [rbp+92h]
  __int64 v63; // [rsp+198h] [rbp+98h]
  char v64; // [rsp+1A0h] [rbp+A0h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v66[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int16 v67; // [rsp+200h] [rbp+100h]
  char v68; // [rsp+202h] [rbp+102h]
  __int64 v69; // [rsp+208h] [rbp+108h]
  char v70; // [rsp+210h] [rbp+110h]
  __int16 v71; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 *v72; // [rsp+290h] [rbp+190h] BYREF
  __int64 v73; // [rsp+298h] [rbp+198h] BYREF

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "CTieredVolume::ProcessVolumeTables";
  CHResultImp::CHResultImp((CHResultImp *)v36);
  LOBYTE(v71) = 0;
  LOBYTE(v72) = 0;
  v41 = 0;
  v44 = 0;
  v43 = 0;
  v42 = 0;
  v55[0] = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v66[0] = 0;
  v67 = 0;
  v68 = 0;
  v69 = 0;
  v70 = 0;
  v60[0] = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  v49[0] = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v45 = 0;
  UnbiasedTime = 0;
  *((_QWORD *)this + 66) = 0;
  *((_QWORD *)this + 67) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = 0;
  FileHandle = 0;
  v39 = 0;
  IoStatusBlock = 0;
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  v5 = *((unsigned int *)this + 46);
  if ( (_DWORD)v5 != 3 )
  {
    v6 = -2138898426;
    v37 = -2138898426;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_DZd(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, -2138898426, v5, (__int64)this + 144, 6);
    }
    goto LABEL_187;
  }
  if ( (unsigned int)dword_14004C098 > 4
    && (qword_14004C0A8 & 0x200000000000LL) != 0
    && (qword_14004C0B0 & 0x200000000000LL) == qword_14004C0B0 )
  {
    v47 = (unsigned __int16 *)((char *)this + 696);
    LOWORD(v73) = *((_WORD *)this + 92);
    v48 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapBuffer<_UNICODE_STRING>>(
      qword_14004C0B0,
      (__int64)&unk_1400468A8,
      v4,
      v5,
      (__int64)&v48,
      (__int64)&v73,
      &v47);
  }
  ThreadErrorMode = RtlGetThreadErrorMode();
  v8 = RtlSetThreadErrorMode(ThreadErrorMode | 0x10, &OldMode);
  v9 = v39;
  if ( v8 >= 0 )
    v9 = 1;
  v39 = v9;
  AcquireSRWLockShared((PSRWLOCK)this + 3);
  if ( !*((_BYTE *)this + 721) )
  {
    v6 = -2138898430;
    v37 = -2138898430;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
        *((unsigned int *)this + 32),
        -2138898430);
    }
    if ( this != (CTieredVolume *)-24LL )
      ReleaseSRWLockShared((PSRWLOCK)this + 3);
    goto LABEL_187;
  }
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)((char *)this + 144);
  *(_QWORD *)&ObjectAttributes.Attributes = 192;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v10 = NtOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x21u);
  if ( this != (CTieredVolume *)-24LL )
    ReleaseSRWLockShared((PSRWLOCK)this + 3);
  if ( v10 < 0 )
  {
    v6 = v10 | 0x10000000;
    v37 = v10 | 0x10000000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
        (_DWORD)this + 144,
        v10);
    }
    goto LABEL_187;
  }
  VolumeBitmapInfoByTier = TieringJetSession::Initialize((TieringJetSession *)v55, (RTL_SRWLOCK **)this + 148);
  v6 = VolumeBitmapInfoByTier;
  v37 = VolumeBitmapInfoByTier;
  if ( VolumeBitmapInfoByTier < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_187;
    }
    v13 = 13;
    goto LABEL_32;
  }
  v14 = TieringJetSession::OpenJetTable((TieringJetSession *)v55, 0);
  v6 = v14;
  v37 = v14;
  if ( v14 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
        (_DWORD)this + 672,
        v14);
    }
LABEL_38:
    TieringJetSession::CloseJetTable((TieringJetSession *)v55, 1);
    goto LABEL_187;
  }
  if ( !*((_QWORD *)this + 12) || !*((_QWORD *)this + 35) || !*((_QWORD *)this + 36) )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    {
      goto LABEL_186;
    }
    v21 = 15;
    v20 = (char *)this + 144;
    goto LABEL_185;
  }
  if ( !*((_BYTE *)this + 163) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Z(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
        (char *)this + 672);
    }
    v6 = CTieredVolume::TeardownMovementSession((JET_API_PTR)this, 0);
    v37 = v6;
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Z(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
          (char *)this + 672);
      }
      goto LABEL_187;
    }
    v15 = TieringJetDatabase::CloseSessionAndBackupJetDatabase(v58, (struct TieringJetSession *)v55, a2, (bool *)&v72);
    v37 = v15;
    if ( v15 >= 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = 19;
        goto LABEL_61;
      }
    }
    else
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = 18;
LABEL_61:
        WPP_SF_Dd(v16[2], v17, &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids, *((unsigned int *)this + 32), v15);
      }
    }
    if ( !*a2 )
    {
      v18 = CTieredVolume::ReferenceVolume(this, 1);
      v6 = v18;
      v37 = v18;
      if ( v18 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
            *((unsigned int *)this + 32),
            v18);
        }
        goto LABEL_38;
      }
      *a2 = 1;
    }
LABEL_74:
    if ( (_BYTE)v72 )
      goto LABEL_76;
    goto LABEL_75;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Z(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
      (char *)this + 672);
    goto LABEL_74;
  }
LABEL_75:
  TieringJetSession::CloseJetTable((TieringJetSession *)v55, 1);
LABEL_76:
  VolumeBitmapInfoByTier = TieringJetSession::Initialize((TieringJetSession *)v60, (RTL_SRWLOCK **)this + 148);
  v6 = VolumeBitmapInfoByTier;
  v37 = VolumeBitmapInfoByTier;
  if ( VolumeBitmapInfoByTier < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_187;
    }
    v13 = 22;
    goto LABEL_32;
  }
  v6 = TieringJetSession::OpenJetTable((TieringJetSession *)v60, 0);
  v37 = v6;
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
        (_DWORD)this + 672,
        v6);
    }
    goto LABEL_187;
  }
  *((_DWORD *)this + 78) = 0;
  if ( !*((_QWORD *)this + 35) && !*((_QWORD *)this + 36) )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    {
      goto LABEL_186;
    }
    v20 = (char *)this + 672;
    v21 = 24;
LABEL_185:
    WPP_SF_Z(v19[2], v21, &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids, v20);
LABEL_186:
    v6 = -2147220986;
    v37 = -2147220986;
    goto LABEL_187;
  }
  VolumeBitmapInfoByTier = TieringJetSession::Initialize(
                             (TieringJetSession *)v49,
                             (RTL_SRWLOCK **)((char *)this + (*((_BYTE *)this + 729) != 0 ? 1504LL : 1344LL)));
  v6 = VolumeBitmapInfoByTier;
  v37 = VolumeBitmapInfoByTier;
  if ( VolumeBitmapInfoByTier < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_187;
    }
    v13 = 25;
    goto LABEL_32;
  }
  VolumeBitmapInfoByTier = TieringJetSession::OpenJetTable((TieringJetSession *)v49, 0);
  v6 = VolumeBitmapInfoByTier;
  v37 = VolumeBitmapInfoByTier;
  if ( VolumeBitmapInfoByTier < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_187;
    }
    v13 = 26;
    goto LABEL_32;
  }
  if ( *((_BYTE *)this + 729) )
  {
    v22 = CTieredVolume::PopulatePinnedCacheFromQfl(this, (struct TieringPinnedSession *)v49);
    v37 = v22;
    if ( v22 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
        (_DWORD)this + 672,
        v22);
    }
  }
  VolumeBitmapInfoByTier = CTieredVolume::GetVolumeBitmapInfoByTier((RTL_SRWLOCK *)this, 1, &v43, &v42);
  v6 = VolumeBitmapInfoByTier;
  v37 = VolumeBitmapInfoByTier;
  if ( VolumeBitmapInfoByTier < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_187;
    }
    v13 = 28;
    goto LABEL_32;
  }
  v23 = 0;
  AcquireSRWLockShared((PSRWLOCK)this + 3);
  v25 = (_QWORD *)*((_QWORD *)this + 10);
  while ( v25 )
  {
    v24 = v25[2];
    v25 = (_QWORD *)*v25;
    if ( *(_BYTE *)(v24 + 36) )
      v23 += *(unsigned int *)(v24 + 32);
  }
  if ( this != (CTieredVolume *)-24LL )
    ReleaseSRWLockShared((PSRWLOCK)this + 3);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_IZ(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, v24, v23, (__int64)this + 672);
  }
  v26 = CTieredVolume::Processing_Pass1(
          this,
          FileHandle,
          (struct TieringPinnedSession *)v49,
          (struct TieringHeatSession *)v60,
          v23,
          &v44,
          &v41);
  v27 = v26;
  if ( v26 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
        (_DWORD)this + 672,
        v26);
    }
    LOBYTE(v71) = 1;
    *((_DWORD *)this + 136) = v27;
  }
  v28 = *((_DWORD *)this + 46);
  if ( v28 != 3 )
  {
    v6 = -2138898426;
    v37 = -2138898426;
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_187;
    }
    v30 = 31;
    goto LABEL_134;
  }
  VolumeBitmapInfoByTier = TieringJetSession::Initialize((TieringJetSession *)v66, (RTL_SRWLOCK **)this + 148);
  v6 = VolumeBitmapInfoByTier;
  v37 = VolumeBitmapInfoByTier;
  if ( VolumeBitmapInfoByTier < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_187;
    }
    v13 = 32;
    goto LABEL_32;
  }
  VolumeBitmapInfoByTier = TieringJetSession::OpenJetTable((TieringJetSession *)v66, 1);
  v6 = VolumeBitmapInfoByTier;
  v37 = VolumeBitmapInfoByTier;
  if ( VolumeBitmapInfoByTier < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_187;
    }
    v13 = 33;
LABEL_32:
    WPP_SF_Zd(
      v12[2],
      v13,
      (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
      (_DWORD)this + 672,
      VolumeBitmapInfoByTier);
    goto LABEL_187;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Z(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
      (char *)this + 672);
  }
  *((_DWORD *)this + 46) = 4;
  v31 = CTieredVolume::Processing_Pass2(this, FileHandle, (struct TieringHeatSession *)v60);
  v37 = v31;
  if ( v31 >= 0 )
    goto LABEL_154;
  LOBYTE(v71) = 1;
  *((_DWORD *)this + 136) = v31;
  v29 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Zd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      35,
      (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
      (_DWORD)this + 672,
      v31);
LABEL_154:
    v29 = WPP_GLOBAL_Control;
  }
  v28 = *((_DWORD *)this + 46);
  if ( v28 != 4 )
  {
    v6 = -2138898426;
    v37 = -2138898426;
    if ( v29 == (_BYTE *)&WPP_GLOBAL_Control || (v29[28] & 1) == 0 || v29[25] < 2u )
      goto LABEL_187;
    v30 = 36;
    goto LABEL_134;
  }
  if ( v29 != (_BYTE *)&WPP_GLOBAL_Control && (v29[28] & 1) != 0 && v29[25] >= 4u )
    WPP_SF_Z(*((_QWORD *)v29 + 2), 37, &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids, (char *)this + 672);
  *((_DWORD *)this + 46) = 5;
  v32 = CTieredVolume::Processing_Pass3(
          (JET_API_PTR)this,
          FileHandle,
          (struct TieringHeatSession *)v66,
          v23,
          v44,
          v43,
          v42,
          v41);
  v6 = v32;
  v37 = v32;
  if ( v32 >= 0 )
    goto LABEL_169;
  LOBYTE(v71) = 1;
  *((_DWORD *)this + 136) = v32;
  v29 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Zd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      38,
      (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
      (_DWORD)this + 672,
      v32);
LABEL_169:
    v29 = WPP_GLOBAL_Control;
  }
  v28 = *((_DWORD *)this + 46);
  if ( v28 != 5 )
  {
    v6 = -2138898426;
    v37 = -2138898426;
    if ( v29 == (_BYTE *)&WPP_GLOBAL_Control || (v29[28] & 1) == 0 || v29[25] < 2u )
      goto LABEL_187;
    v30 = 39;
LABEL_134:
    WPP_SF_DZd(*((_QWORD *)v29 + 2), v30, -2138898426, v28, (__int64)this + 144, 6);
    goto LABEL_187;
  }
  if ( *((_BYTE *)this + 163) )
  {
    if ( v29 != (_BYTE *)&WPP_GLOBAL_Control && (v29[28] & 1) != 0 && v29[25] >= 4u )
      WPP_SF_Z(*((_QWORD *)v29 + 2), 40, &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids, (char *)this + 672);
    *((_BYTE *)this + 163) = 0;
  }
LABEL_187:
  QueryUnbiasedInterruptTime(&v45);
  *((_DWORD *)this + 137) = (v45 - UnbiasedTime) / 0x23C34600;
  if ( !(_BYTE)v71 )
    *((_DWORD *)this + 136) = v6;
  TieringJetSession::CloseJetTable((TieringJetSession *)v49, 1);
  TieringJetSession::CloseJetTable((TieringJetSession *)v66, 1);
  TieringJetSession::CloseJetTable((TieringJetSession *)v60, 1);
  AcquireSRWLockExclusive((PSRWLOCK)this + 3);
  if ( (unsigned int)(*((_DWORD *)this + 46) - 3) <= 2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Z(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
        (char *)this + 672);
    }
    *((_DWORD *)this + 46) = 2;
  }
  if ( (unsigned int)dword_14004C098 > 4
    && (qword_14004C0A8 & 0x200000000000LL) != 0
    && (qword_14004C0B0 & 0x200000000000LL) == qword_14004C0B0 )
  {
    v72 = (unsigned __int16 *)((char *)this + 696);
    v71 = *((_WORD *)this + 92);
    v73 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapBuffer<_UNICODE_STRING>>(
      qword_14004C0B0,
      (__int64)&dword_140046844,
      v33,
      v34,
      (__int64)&v73,
      (__int64)&v71,
      &v72);
  }
  if ( this != (CTieredVolume *)-24LL )
    ReleaseSRWLockExclusive((PSRWLOCK)this + 3);
  if ( v39 )
    RtlSetThreadErrorMode(OldMode, 0);
  if ( FileHandle )
    NtClose(FileHandle);
  TieringJetSession::~TieringJetSession((TieringJetSession *)v49);
  TieringJetSession::~TieringJetSession((TieringJetSession *)v60);
  TieringJetSession::~TieringJetSession((TieringJetSession *)v66);
  TieringJetSession::~TieringJetSession((TieringJetSession *)v55);
  CHResultImp::~CHResultImp((CHResultImp *)v36);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14002eef0  mov     [rsp-8+arg_8], rbx
0x14002eef5  push    rbp
0x14002eef6  push    rsi
0x14002eef7  push    rdi
0x14002eef8  push    r12
0x14002eefa  push    r13
0x14002eefc  push    r14
0x14002eefe  push    r15
0x14002ef00  lea     rbp, [rsp-140h]
0x14002ef08  sub     rsp, 240h
0x14002ef0f  mov     r12, rdx
0x14002ef12  mov     rdi, rcx
0x14002ef15  mov     ecx, 8
0x14002ef1a  mov     rax, gs:58h
0x14002ef23  mov     r8, [rax]
0x14002ef26  lea     rax, aCtieredvolumeP_3; "CTieredVolume::ProcessVolumeTables"
0x14002ef2d  mov     [rcx+r8], rax
0x14002ef31  lea     rcx, [rsp+270h+var_230]; this
0x14002ef36  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14002ef3b  nop
0x14002ef3c  xor     esi, esi
0x14002ef3e  mov     byte ptr [rbp+170h+arg_0], sil
0x14002ef45  mov     byte ptr [rbp+170h+arg_10], sil
0x14002ef4c  mov     [rsp+270h+var_210], rsi
0x14002ef51  mov     [rsp+270h+var_1F8], rsi
0x14002ef56  mov     [rsp+270h+var_200], rsi
0x14002ef5b  mov     [rsp+270h+var_208], rsi
0x14002ef60  mov     [rbp+170h+var_160], sil
0x14002ef64  mov     [rbp+170h+var_140], si
0x14002ef68  mov     [rbp+170h+var_13E], sil
0x14002ef6c  mov     [rbp+170h+var_138], rsi
0x14002ef70  mov     [rbp+170h+var_130], sil
0x14002ef74  mov     [rbp+170h+var_90], sil
0x14002ef7b  mov     [rbp+170h+var_70], si
0x14002ef82  mov     [rbp+170h+var_6E], sil
0x14002ef89  mov     [rbp+170h+var_68], rsi
0x14002ef90  mov     [rbp+170h+var_60], sil
0x14002ef97  mov     [rbp+170h+var_100], sil
0x14002ef9b  mov     [rbp+170h+var_E0], si
0x14002efa2  mov     [rbp+170h+var_DE], sil
0x14002efa9  mov     [rbp+170h+var_D8], rsi
0x14002efb0  mov     [rbp+170h+var_D0], sil
0x14002efb7  mov     [rbp+170h+var_1D0], sil
0x14002efbb  mov     [rbp+170h+var_1B0], si
0x14002efbf  mov     [rbp+170h+var_1AE], sil
0x14002efc3  mov     [rbp+170h+var_1A8], rsi
0x14002efc7  mov     [rbp+170h+var_1A0], sil
0x14002efcb  mov     [rbp+170h+var_1F0], rsi
0x14002efcf  mov     [rbp+170h+UnbiasedTime], rsi
0x14002efd3  mov     [rdi+210h], rsi
0x14002efda  mov     [rdi+218h], rsi
0x14002efe1  mov     [rdi+108h], rsi
0x14002efe8  mov     [rdi+110h], rsi
0x14002efef  mov     [rdi+0C0h], rsi
0x14002eff6  mov     [rdi+0C8h], rsi
0x14002effd  mov     [rsp+270h+FileHandle], rsi
0x14002f002  mov     [rsp+270h+var_21C], sil
0x14002f007  xorps   xmm0, xmm0
0x14002f00a  movups  xmmword ptr [rbp+170h+IoStatusBlock], xmm0
0x14002f011  lea     rcx, [rbp+170h+UnbiasedTime]; UnbiasedTime
0x14002f015  call    cs:__imp_QueryUnbiasedInterruptTime
0x14002f01b  mov     r9d, [rdi+0B8h]
0x14002f022  lea     ebx, [rsi+1]
0x14002f025  mov     r15, 200000000000h
0x14002f02f  cmp     r9d, 3
0x14002f033  jz      short loc_14002F097
0x14002f035  mov     r8d, 80830006h
0x14002f03b  mov     ebx, r8d
0x14002f03e  mov     [rsp+270h+var_228], ebx
0x14002f042  lea     rsi, WPP_GLOBAL_Control
0x14002f049  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f050  mov     r12d, 1
0x14002f056  cmp     rcx, rsi
0x14002f059  jz      loc_14002FBCE
0x14002f05f  test    [rcx+1Ch], r12b
0x14002f063  jz      loc_14002FBCE
0x14002f069  cmp     byte ptr [rcx+19h], 2
0x14002f06d  jb      loc_14002FBCE
0x14002f073  lea     rax, [rdi+90h]
0x14002f07a  lea     edx, [r12+9]
0x14002f07f  mov     [rsp+270h+OpenOptions], r8d
0x14002f084  mov     qword ptr [rsp+270h+ShareAccess], rax
0x14002f089  mov     rcx, [rcx+10h]
0x14002f08d  call    WPP_SF_DZd
0x14002f092  jmp     loc_14002FBCE
0x14002f097  mov     eax, cs:dword_14004C098
0x14002f09d  cmp     eax, 4
0x14002f0a0  jbe     short loc_14002F10B
0x14002f0a2  mov     rcx, cs:qword_14004C0B0
0x14002f0a9  mov     rax, cs:qword_14004C0A8
0x14002f0b0  test    r15, rax
0x14002f0b3  jz      short loc_14002F10B
0x14002f0b5  mov     rax, rcx
0x14002f0b8  and     rax, r15
0x14002f0bb  cmp     rax, rcx
0x14002f0be  jnz     short loc_14002F10B
0x14002f0c0  lea     rax, [rdi+2B8h]
0x14002f0c7  mov     [rbp+170h+var_1E0], rax
0x14002f0cb  movzx   eax, word ptr [rdi+0B8h]
0x14002f0d2  mov     word ptr [rbp+170h+arg_18], ax
0x14002f0d9  mov     [rbp+170h+var_1D8], 1000000h
0x14002f0e1  lea     rax, [rbp+170h+var_1E0]
0x14002f0e5  mov     [rsp+270h+var_240], rax
0x14002f0ea  lea     rax, [rbp+170h+arg_18]
0x14002f0f1  mov     qword ptr [rsp+270h+OpenOptions], rax
0x14002f0f6  lea     rax, [rbp+170h+var_1D8]
0x14002f0fa  mov     qword ptr [rsp+270h+ShareAccess], rax
0x14002f0ff  lea     rdx, unk_1400468A8
0x14002f106  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapBuffer<_UNICODE_STRING>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<2> const &,_tlgWrapBuffer<_UNICODE_STRING> const &)
0x14002f10b  call    cs:__imp_RtlGetThreadErrorMode
0x14002f111  or      eax, 10h
0x14002f114  lea     rdx, [rsp+270h+OldMode]; OldMode
0x14002f119  mov     ecx, eax; NewMode
0x14002f11b  call    cs:__imp_RtlSetThreadErrorMode
0x14002f121  movzx   ecx, [rsp+270h+var_21C]
0x14002f126  test    eax, eax
0x14002f128  cmovns  ecx, ebx
0x14002f12b  mov     [rsp+270h+var_21C], cl
0x14002f12f  lea     r15, [rdi+18h]
0x14002f133  mov     rcx, r15; SRWLock
0x14002f136  call    cs:__imp_AcquireSRWLockShared
0x14002f13c  cmp     [rdi+2D1h], sil
0x14002f143  jnz     short loc_14002F1AA
0x14002f145  mov     ebx, 80830002h
0x14002f14a  mov     [rsp+270h+var_228], ebx
0x14002f14e  lea     rsi, WPP_GLOBAL_Control
0x14002f155  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f15c  mov     r12d, 1
0x14002f162  cmp     rcx, rsi
0x14002f165  jz      short loc_14002F193
0x14002f167  test    [rcx+1Ch], r12b
0x14002f16b  jz      short loc_14002F193
0x14002f16d  cmp     byte ptr [rcx+19h], 2
0x14002f171  jb      short loc_14002F193
0x14002f173  lea     edx, [r12+0Ah]
0x14002f178  mov     [rsp+270h+ShareAccess], ebx
0x14002f17c  mov     r9d, [rdi+80h]
0x14002f183  lea     r8, WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids
0x14002f18a  mov     rcx, [rcx+10h]
0x14002f18e  call    WPP_SF_Dd
0x14002f193  test    r15, r15
0x14002f196  jz      loc_14002FBC4
0x14002f19c  mov     rcx, r15; SRWLock
0x14002f19f  call    cs:__imp_ReleaseSRWLockShared
0x14002f1a5  jmp     loc_14002FBC4
0x14002f1aa  mov     qword ptr [rbp+170h+ObjectAttributes.Length], 30h ; '0'
0x14002f1b2  mov     [rbp+170h+ObjectAttributes.RootDirectory], rsi
0x14002f1b6  lea     r13, [rdi+90h]
0x14002f1bd  mov     [rbp+170h+ObjectAttributes.ObjectName], r13
0x14002f1c1  mov     qword ptr [rbp+170h+ObjectAttributes.Attributes], 0C0h
0x14002f1c9  xorps   xmm0, xmm0
0x14002f1cc  movdqu  xmmword ptr [rbp+170h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002f1d1  mov     [rsp+270h+OpenOptions], 21h ; '!'; OpenOptions
0x14002f1d9  mov     [rsp+270h+ShareAccess], 7; ShareAccess
0x14002f1e1  lea     r9, [rbp+170h+IoStatusBlock]; IoStatusBlock
0x14002f1e8  lea     r8, [rbp+170h+ObjectAttributes]; ObjectAttributes
0x14002f1ec  mov     edx, 100080h; DesiredAccess
0x14002f1f1  lea     rcx, [rsp+270h+FileHandle]; FileHandle
0x14002f1f6  call    cs:__imp_NtOpenFile
0x14002f1fc  mov     r14d, eax
0x14002f1ff  test    r15, r15
0x14002f202  jz      short loc_14002F20D
0x14002f204  mov     rcx, r15; SRWLock
0x14002f207  call    cs:__imp_ReleaseSRWLockShared
0x14002f20d  test    r14d, r14d
0x14002f210  jns     short loc_14002F270
0x14002f212  mov     ebx, r14d
0x14002f215  bts     ebx, 1Ch
0x14002f219  mov     [rsp+270h+var_228], ebx
0x14002f21d  lea     rsi, WPP_GLOBAL_Control
0x14002f224  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f22b  mov     r12d, 1
0x14002f231  cmp     rcx, rsi
0x14002f234  jz      loc_14002FBC4
0x14002f23a  test    [rcx+1Ch], r12b
0x14002f23e  jz      loc_14002FBC4
0x14002f244  cmp     byte ptr [rcx+19h], 2
0x14002f248  jb      loc_14002FBC4
0x14002f24e  lea     edx, [r12+0Bh]
0x14002f253  mov     [rsp+270h+ShareAccess], r14d
0x14002f258  mov     r9, r13
0x14002f25b  lea     r8, WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids
0x14002f262  mov     rcx, [rcx+10h]
0x14002f266  call    WPP_SF_Zd
0x14002f26b  jmp     loc_14002FBC4
0x14002f270  lea     r13, [rdi+4A0h]
0x14002f277  mov     rdx, r13; struct TieringJetDatabase *
0x14002f27a  lea     rcx, [rbp+170h+var_160]; this
0x14002f27e  call    ?Initialize@TieringJetSession@@QEAAJPEAVTieringJetDatabase@@@Z; TieringJetSession::Initialize(TieringJetDatabase *)
0x14002f283  mov     ebx, eax
0x14002f285  mov     [rsp+270h+var_228], eax
0x14002f289  test    eax, eax
0x14002f28b  jns     short loc_14002F2D0
0x14002f28d  lea     rsi, WPP_GLOBAL_Control
0x14002f294  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f29b  mov     r12d, 1
0x14002f2a1  cmp     rcx, rsi
0x14002f2a4  jz      loc_14002FBC4
0x14002f2aa  test    [rcx+1Ch], r12b
0x14002f2ae  jz      loc_14002FBC4
0x14002f2b4  cmp     byte ptr [rcx+19h], 2
0x14002f2b8  jb      loc_14002FBC4
0x14002f2be  lea     edx, [r12+0Ch]
0x14002f2c3  lea     r9, [rdi+2A0h]
0x14002f2ca  mov     [rsp+270h+ShareAccess], eax
0x14002f2ce  jmp     short loc_14002F25B
0x14002f2d0  xor     edx, edx; bool
0x14002f2d2  lea     rcx, [rbp+170h+var_160]; this
0x14002f2d6  call    ?OpenJetTable@TieringJetSession@@QEAAJ_N@Z; TieringJetSession::OpenJetTable(bool)
0x14002f2db  mov     ebx, eax
0x14002f2dd  mov     [rsp+270h+var_228], eax
0x14002f2e1  test    eax, eax
0x14002f2e3  jns     short loc_14002F33B
0x14002f2e5  lea     rsi, WPP_GLOBAL_Control
0x14002f2ec  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f2f3  mov     r12d, 1
0x14002f2f9  cmp     rcx, rsi
0x14002f2fc  jz      short loc_14002F32A
0x14002f2fe  test    [rcx+1Ch], r12b
0x14002f302  jz      short loc_14002F32A
0x14002f304  cmp     byte ptr [rcx+19h], 2
0x14002f308  jb      short loc_14002F32A
0x14002f30a  lea     r9, [rdi+2A0h]
0x14002f311  lea     edx, [r12+0Dh]
0x14002f316  mov     [rsp+270h+ShareAccess], eax
0x14002f31a  lea     r8, WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids
0x14002f321  mov     rcx, [rcx+10h]
0x14002f325  call    WPP_SF_Zd
0x14002f32a  mov     dl, r12b; bool
0x14002f32d  lea     rcx, [rbp+170h+var_160]; this
0x14002f331  call    ?CloseJetTable@TieringJetSession@@QEAAJ_N@Z; TieringJetSession::CloseJetTable(bool)
0x14002f336  jmp     loc_14002FBC4
0x14002f33b  cmp     [rdi+60h], rsi
0x14002f33f  jz      loc_14002FB7A
0x14002f345  cmp     [rdi+118h], rsi
0x14002f34c  jz      loc_14002FB7A
0x14002f352  cmp     [rdi+120h], rsi
0x14002f359  jz      loc_14002FB7A
0x14002f35f  cmp     [rdi+0A3h], sil
0x14002f366  jnz     loc_14002F4F8
0x14002f36c  lea     rsi, WPP_GLOBAL_Control
0x14002f373  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f37a  mov     r14d, 1
0x14002f380  cmp     rcx, rsi
0x14002f383  jz      short loc_14002F3AC
0x14002f385  test    [rcx+1Ch], r14b
0x14002f389  jz      short loc_14002F3AC
0x14002f38b  cmp     byte ptr [rcx+19h], 4
0x14002f38f  jb      short loc_14002F3AC
0x14002f391  lea     r9, [rdi+2A0h]
0x14002f398  lea     edx, [r14+0Fh]
0x14002f39c  lea     r8, WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids
0x14002f3a3  mov     rcx, [rcx+10h]
0x14002f3a7  call    WPP_SF_Z
0x14002f3ac  xor     edx, edx; bool
0x14002f3ae  mov     rcx, rdi; ulContext
0x14002f3b1  call    ?TeardownMovementSession@CTieredVolume@@AEAAJ_N@Z; CTieredVolume::TeardownMovementSession(bool)
0x14002f3b6  mov     ebx, eax
0x14002f3b8  mov     [rsp+270h+var_228], eax
0x14002f3bc  test    eax, eax
0x14002f3be  jns     short loc_14002F40B
0x14002f3c0  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f3c7  mov     r12d, 1
0x14002f3cd  cmp     rcx, rsi
0x14002f3d0  jz      loc_14002FBC4
0x14002f3d6  test    [rcx+1Ch], r12b
0x14002f3da  jz      loc_14002FBC4
0x14002f3e0  cmp     byte ptr [rcx+19h], 4
0x14002f3e4  jb      loc_14002FBC4
0x14002f3ea  lea     r9, [rdi+2A0h]
0x14002f3f1  lea     edx, [r12+10h]
0x14002f3f6  lea     r8, WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids
0x14002f3fd  mov     rcx, [rcx+10h]
0x14002f401  call    WPP_SF_Z
0x14002f406  jmp     loc_14002FBC4
0x14002f40b  lea     r9, [rbp+170h+arg_10]; bool *
0x14002f412  mov     r8, r12; bool *
0x14002f415  lea     rdx, [rbp+170h+var_160]; struct TieringJetSession *
0x14002f419  mov     rcx, [rbp+170h+var_138]; this
0x14002f41d  call    ?CloseSessionAndBackupJetDatabase@TieringJetDatabase@@QEAAJPEAVTieringJetSession@@PEA_N1@Z; TieringJetDatabase::CloseSessionAndBackupJetDatabase(TieringJetSession *,bool *,bool *)
0x14002f422  mov     [rsp+270h+var_228], eax
0x14002f426  test    eax, eax
0x14002f428  jns     short loc_14002F449
0x14002f42a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f431  cmp     rcx, rsi
0x14002f434  jz      short loc_14002F481
0x14002f436  test    [rcx+1Ch], r14b
0x14002f43a  jz      short loc_14002F481
0x14002f43c  cmp     byte ptr [rcx+19h], 2
0x14002f440  jb      short loc_14002F481
0x14002f442  mov     edx, 12h
0x14002f447  jmp     short loc_14002F466
0x14002f449  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f450  cmp     rcx, rsi
0x14002f453  jz      short loc_14002F481
0x14002f455  test    [rcx+1Ch], r14b
0x14002f459  jz      short loc_14002F481
0x14002f45b  cmp     byte ptr [rcx+19h], 2
0x14002f45f  jb      short loc_14002F481
0x14002f461  mov     edx, 13h
  ... truncated ...
```
