# Broker::TimeBroker::ValidateCreationParameters(_TbiTimeEventCreationParameters const &,bool,bool)

- ea: `0x180002500`
- end: `0x1800036f9`
- name: `?ValidateCreationParameters@TimeBroker@Broker@@AEAAXAEBU_TbiTimeEventCreationParameters@@_N1@Z`
- size: `4601`
- prototype: `void __fastcall(Broker::TimeBroker *this, const struct _TbiTimeEventCreationParameters *, char, char)`
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000215c`
- `0x180003868`
- `0x18000ef50`

## callees

- `0x180002000`
- `0x180002500`
- `0x180003800`
- `0x180003840`
- `0x180009fc0`
- `0x180012dd0`
- `0x180013978`
- `0x180016210`
- `0x18001682c`
- `0x180016880`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000281c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002b3b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002c50`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000281c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002b3b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002c50`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180002616`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180002616`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180002654`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000276d`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800028c5`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180002654`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000276d`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800028c5`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180002664`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000277d`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800028d5`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180002664`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000277d`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800028d5`

## pseudocode

```c
void __fastcall Broker::TimeBroker::ValidateCreationParameters(
        Broker::TimeBroker *this,
        const struct _TbiTimeEventCreationParameters *a2,
        char a3,
        char a4)
{
  __int64 v7; // r9
  Broker::TimeBroker *v8; // rcx
  __int64 v9; // r9
  unsigned int v10; // ecx
  __int64 v11; // r9
  unsigned int v12; // ecx
  __int64 v13; // r9
  __int128 v14; // xmm0
  BOOL v15; // edi
  BOOL v16; // eax
  bool v17; // dl
  bool v18; // r8
  _BOOL8 v19; // rcx
  __int64 v20; // r9
  __int64 v21; // r9
  __int64 v22; // r9
  __int128 v23; // xmm0
  BOOL v24; // edi
  BOOL v25; // r8d
  bool v26; // dl
  bool v27; // al
  __int64 v28; // rax
  __int64 v29; // rdi
  __int64 v30; // r9
  __int64 v31; // r9
  __int128 v32; // xmm0
  BOOL v33; // edi
  BOOL v34; // r8d
  bool v35; // dl
  bool v36; // al
  __int64 v37; // rax
  __int64 v38; // r9
  __int64 v39; // r9
  const struct _SYSTEMTIME *v40; // rdx
  __int64 v41; // r9
  __int64 v42; // r9
  __int64 v43; // rax
  __int64 v44; // rbx
  __int64 v45; // rbx
  __int64 v46; // rdi
  __int64 v47; // r9
  unsigned int v48; // r8d
  unsigned int v49; // eax
  unsigned int v50; // eax
  void **v51; // [rsp+50h] [rbp-39h] BYREF
  __int128 v52; // [rsp+58h] [rbp-31h]
  int v53; // [rsp+68h] [rbp-21h]
  struct _FILETIME FileTime; // [rsp+70h] [rbp-19h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+80h] [rbp-9h] BYREF
  int v56; // [rsp+98h] [rbp+Fh]
  _BYTE SystemTime[24]; // [rsp+A0h] [rbp+17h] BYREF
  int v58; // [rsp+B8h] [rbp+2Fh]

  if ( (unsigned int)(*((_DWORD *)a2 + 14) - 1) <= 0xE )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids);
    v58 = 4;
    *(_QWORD *)SystemTime = &Broker::InvalidParameter::`vftable';
    *(_OWORD *)&SystemTime[8] = 0;
    throw (Broker::InvalidParameter *)SystemTime;
  }
  if ( *((_DWORD *)a2 + 22) && (*(_DWORD *)a2 & 0xFFFFFFFB) != 0 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids);
    v58 = 5;
    *(_QWORD *)SystemTime = &Broker::AccessDenied::`vftable';
    *(_OWORD *)&SystemTime[8] = 0;
    throw (Broker::AccessDenied *)SystemTime;
  }
  v7 = *(unsigned int *)a2;
  if ( (_DWORD)v7 == 4 )
  {
    *(_OWORD *)SystemTime = 0;
    GetSystemTime((LPSYSTEMTIME)SystemTime);
    if ( a3 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids);
      v53 = 5;
      v51 = &Broker::AccessDenied::`vftable';
      v52 = 0;
      throw (Broker::AccessDenied *)&v51;
    }
    v12 = *((_DWORD *)a2 + 7);
    if ( !v12 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, 0);
      v53 = 4;
      v51 = &Broker::InvalidParameter::`vftable';
      v52 = 0;
      throw (Broker::InvalidParameter *)&v51;
    }
    v13 = *((unsigned int *)a2 + 6);
    if ( (_DWORD)v13 )
    {
      if ( (unsigned int)(v13 - 5) > 0x1E1337B )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v13);
        v53 = 4;
        v51 = &Broker::InvalidParameter::`vftable';
        v52 = 0;
        throw (Broker::InvalidParameter *)&v51;
      }
      if ( (unsigned int)v13 <= v12 )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2));
        v53 = 4;
        v51 = &Broker::InvalidParameter::`vftable';
        v52 = 0;
        throw (Broker::InvalidParameter *)&v51;
      }
    }
    v14 = *(_OWORD *)((char *)a2 + 8);
    FileTime = 0;
    *(_OWORD *)pExceptionObject = v14;
    v15 = SystemTimeToFileTime((const SYSTEMTIME *)pExceptionObject, &FileTime);
    v16 = FileTimeToSystemTime(&FileTime, (LPSYSTEMTIME)pExceptionObject);
    v17 = 0;
    v18 = 0;
    if ( v15 )
      v17 = *((_WORD *)a2 + 4) == *(_WORD *)pExceptionObject;
    v19 = *((_WORD *)a2 + 5) == *(_WORD *)&pExceptionObject[2];
    if ( v16 )
      v18 = *((_WORD *)a2 + 5) == *(_WORD *)&pExceptionObject[2];
    if ( *((_WORD *)a2 + 8) != *(_WORD *)&pExceptionObject[8]
      || *((_WORD *)a2 + 7) != *(_WORD *)&pExceptionObject[6]
      || !v17
      || !v18
      || *((_WORD *)a2 + 9) != *(_WORD *)&pExceptionObject[10] )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_ddddddd(*((_QWORD *)WPP_GLOBAL_Control + 2));
      v53 = 4;
      v51 = &Broker::InvalidParameter::`vftable';
      v52 = 0;
      throw (Broker::InvalidParameter *)&v51;
    }
    if ( *((_DWORD *)a2 + 18) )
    {
      *(_OWORD *)pExceptionObject = *(_OWORD *)((char *)a2 + 72);
      Broker::TimeBroker::ValidateIrregularSchedule(v19, pExceptionObject);
    }
    if ( *((_QWORD *)a2 + 8) )
    {
      v50 = *((_DWORD *)a2 + 14);
      if ( !v50 )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids);
        v53 = 4;
        v51 = &Broker::InvalidParameter::`vftable';
        v52 = 0;
        throw (Broker::InvalidParameter *)&v51;
      }
      if ( v50 > 0xFF8 )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids);
        v53 = 4;
        v51 = &Broker::InvalidParameter::`vftable';
        v52 = 0;
        throw (Broker::InvalidParameter *)&v51;
      }
    }
  }
  else if ( (_DWORD)v7 )
  {
    v8 = (Broker::TimeBroker *)(unsigned int)(v7 - 1);
    switch ( (_DWORD)v7 )
    {
      case 1:
        if ( a3 )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids);
          v53 = 5;
          v51 = &Broker::AccessDenied::`vftable';
          v52 = 0;
          throw (Broker::AccessDenied *)&v51;
        }
        v39 = *((unsigned int *)a2 + 7);
        v40 = (const struct _SYSTEMTIME *)((char *)a2 + 8);
        if ( !(_DWORD)v39 )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, 0);
          v53 = 4;
          v51 = &Broker::InvalidParameter::`vftable';
          v52 = 0;
          throw (Broker::InvalidParameter *)&v51;
        }
        if ( (unsigned int)v39 > 0x708 )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v39);
          v53 = 4;
          v51 = &Broker::InvalidParameter::`vftable';
          v52 = 0;
          throw (Broker::InvalidParameter *)&v51;
        }
        v41 = *((unsigned int *)a2 + 6);
        if ( (unsigned int)v41 > 0x8D27 )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v41);
          v53 = 4;
          v51 = &Broker::InvalidParameter::`vftable';
          v52 = 0;
          throw (Broker::InvalidParameter *)&v51;
        }
        v42 = *((unsigned int *)a2 + 8);
        if ( (unsigned int)v42 > 0x80520 )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v42);
          v53 = 4;
          v51 = &Broker::InvalidParameter::`vftable';
          v52 = 0;
          throw (Broker::InvalidParameter *)&v51;
        }
        v43 = Broker::TimeBroker::ValidateSystemTime(v8, v40);
        if ( !*((_DWORD *)a2 + 6) )
        {
          v44 = 5000000LL * *((unsigned int *)a2 + 7);
          FileTime = 0;
          v45 = v43 + v44;
          GetSystemTimeAsFileTime(&FileTime);
          if ( v45 < *(_QWORD *)&FileTime )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              WPP_SF_i(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v45);
            v53 = 4;
            v51 = &Broker::InvalidParameter::`vftable';
            v52 = 0;
            throw (Broker::InvalidParameter *)&v51;
          }
        }
        break;
      case 2:
        if ( a3 && (*((_BYTE *)a2 + 32) & 4) != 0 )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids);
          v56 = 5;
          *(_QWORD *)pExceptionObject = &Broker::AccessDenied::`vftable';
          *(_OWORD *)&pExceptionObject[8] = 0;
          throw (Broker::AccessDenied *)pExceptionObject;
        }
        v30 = *((unsigned int *)a2 + 6);
        if ( (unsigned int)(v30 - 15) > 0xA8B1 )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v30);
          v53 = 4;
          v51 = &Broker::InvalidParameter::`vftable';
          v52 = 0;
          throw (Broker::InvalidParameter *)&v51;
        }
        v31 = *((unsigned int *)a2 + 7);
        if ( (unsigned int)v31 > 0xA8C0 )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v31);
          v56 = 4;
          *(_QWORD *)pExceptionObject = &Broker::InvalidParameter::`vftable';
          *(_OWORD *)&pExceptionObject[8] = 0;
          throw (Broker::InvalidParameter *)pExceptionObject;
        }
        v32 = *(_OWORD *)((char *)a2 + 8);
        FileTime = 0;
        *(_OWORD *)pExceptionObject = v32;
        v33 = SystemTimeToFileTime((const SYSTEMTIME *)pExceptionObject, &FileTime);
        v34 = FileTimeToSystemTime(&FileTime, (LPSYSTEMTIME)pExceptionObject);
        v35 = 0;
        v36 = 0;
        if ( v33 )
          v35 = *((_WORD *)a2 + 4) == *(_WORD *)pExceptionObject;
        if ( v34 )
          v36 = *((_WORD *)a2 + 5) == *(_WORD *)&pExceptionObject[2];
        if ( !v35
          || !v36
          || *((_WORD *)a2 + 7) != *(_WORD *)&pExceptionObject[6]
          || *((_WORD *)a2 + 8) != *(_WORD *)&pExceptionObject[8]
          || *((_WORD *)a2 + 9) != *(_WORD *)&pExceptionObject[10] )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_ddddddd(*((_QWORD *)WPP_GLOBAL_Control + 2));
          v53 = 4;
          v51 = &Broker::InvalidParameter::`vftable';
          v52 = 0;
          throw (Broker::InvalidParameter *)&v51;
        }
        v37 = *((unsigned int *)a2 + 7);
        if ( (unsigned int)v37 < 0xF )
          v37 = 15;
        if ( (*((_BYTE *)a2 + 32) & 1) != 0 )
        {
          v46 = *(_QWORD *)&FileTime + 600000000 * v37;
          FileTime = 0;
          GetSystemTimeAsFileTime(&FileTime);
          if ( v46 < *(_QWORD *)&FileTime )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              WPP_SF_i(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v46);
            v53 = 4;
            v51 = &Broker::InvalidParameter::`vftable';
            v52 = 0;
            throw (Broker::InvalidParameter *)&v51;
          }
        }
        v38 = *((unsigned int *)a2 + 8);
        if ( (v38 & 8) != 0 )
        {
          v49 = *((_DWORD *)a2 + 6);
          if ( v49 < 0x168 )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v49);
            v53 = 4;
            v51 = &Broker::InvalidParameter::`vftable';
            v52 = 0;
            throw (Broker::InvalidParameter *)&v51;
          }
          if ( (_DWORD)v38 != 8 )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v38);
            v53 = 4;
            v51 = &Broker::InvalidParameter::`vftable';
            v52 = 0;
            throw (Broker::InvalidParameter *)&v51;
          }
        }
        else if ( (v38 & 0xFFFFFFF0) != 0 )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v38);
          v53 = 4;
          v51 = &Broker::InvalidParameter::`vftable';
          v52 = 0;
          throw (Broker::InvalidParameter *)&v51;
        }
        break;
      case 3:
        v9 = *((unsigned int *)a2 + 3);
        if ( !(_DWORD)v9 )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, 0);
          v56 = 4;
          *(_QWORD *)pExceptionObject = &Broker::InvalidParameter::`vftable';
          *(_OWORD *)&pExceptionObject[8] = 0;
          throw (Broker::InvalidParameter *)pExceptionObject;
        }
        v10 = *((_DWORD *)a2 + 2);
        if ( (unsigned int)v9 > v10 )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v9);
          v56 = 4;
          *(_QWORD *)pExceptionObject = &Broker::InvalidParameter::`vftable';
          *(_OWORD *)&pExceptionObject[8] = 0;
          throw (Broker::InvalidParameter *)pExceptionObject;
        }
        if ( v10 - 60 > 0x15143 )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v10);
          v56 = 4;
          *(_QWORD *)pExceptionObject = &Broker::InvalidParameter::`vftable';
          *(_OWORD *)&pExceptionObject[8] = 0;
          throw (Broker::InvalidParameter *)pExceptionObject;
        }
        v11 = *((unsigned int *)a2 + 4);
        if ( (unsigned int)v11 > 0x278D00 )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v11);
          v56 = 4;
          *(_QWORD *)pExceptionObject = &Broker::InvalidParameter::`vftable';
          *(_OWORD *)&pExceptionObject[8] = 0;
          throw (Broker::InvalidParameter *)pExceptionObject;
        }
        break;
      case 5:
        if ( a3 )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids);
          v56 = 5;
          *(_QWORD *)pExceptionObject = &Broker::AccessDenied::`vftable';
          *(_OWORD *)&pExceptionObject[8] = 0;
          throw (Broker::AccessDenied *)pExceptionObject;
        }
        v47 = *((unsigned int *)a2 + 7);
        if ( !(_DWORD)v47 )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v47);
          v56 = 4;
          *(_QWORD *)pExceptionObject = &Broker::InvalidParameter::`vftable';
          *(_OWORD *)&pExceptionObject[8] = 0;
          throw (Broker::InvalidParameter *)pExceptionObject;
        }
        v48 = *((_DWORD *)a2 + 6);
        if ( (unsigned int)v47 >= v48 )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v47);
          v56 = 4;
          *(_QWORD *)pExceptionObject = &Broker::InvalidParameter::`vftable';
          *(_OWORD *)&pExceptionObject[8] = 0;
          throw (Broker::InvalidParameter *)pExceptionObject;
        }
        if ( v48 - 5 > 0x1E1337A )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v48);
          v56 = 4;
          *(_QWORD *)pExceptionObject = &Broker::InvalidParameter::`vftable';
          *(_OWORD *)&pExceptionObject[8] = 0;
          throw (Broker::InvalidParameter *)pExceptionObject;
        }
        break;
      default:
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v7);
        v56 = 4;
        *(_QWORD *)pExceptionObject = &Broker::InvalidParameter::`vftable';
        *(_OWORD *)&pExceptionObject[8] = 0;
        throw (Broker::InvalidParameter *)pExceptionObject;
    }
  }
  else
  {
    v20 = *((unsigned int *)a2 + 7);
    if ( !(_DWORD)v20 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, 0);
      v53 = 4;
      v51 = &Broker::InvalidParameter::`vftable';
      v52 = 0;
      throw (Broker::InvalidParameter *)&v51;
    }
    if ( (unsigned int)v20 > 0x3C )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v20);
      v53 = 4;
      v51 = &Broker::InvalidParameter::`vftable';
      v52 = 0;
      throw (Broker::InvalidParameter *)&v51;
    }
    v21 = *((unsigned int *)a2 + 6);
    if ( (unsigned int)v21 >= 0x15181 || (unsigned int)(v21 - 1) <= 0x3A )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v21);
      v53 = 4;
      v51 = &Broker::InvalidParameter::`vftable';
      v52 = 0;
      throw (Broker::InvalidParameter *)&v51;
    }
    v22 = *((unsigned int *)a2 + 8);
    if ( (unsigned int)v22 > 0xA8C0 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v22);
      v53 = 4;
      v51 = &Broker::InvalidParameter::`vftable';
      v52 = 0;
      throw (Broker::InvalidParameter *)&v51;
    }
    v23 = *(_OWORD *)((char *)a2 + 8);
    FileTime = 0;
    *(_OWORD *)pExceptionObject = v23;
    v24 = SystemTimeToFileTime((const SYSTEMTIME *)pExceptionObject, &FileTime);
    v25 = FileTimeToSystemTime(&FileTime, (LPSYSTEMTIME)pExceptionObject);
    v26 = 0;
    v27 = 0;
    if ( v24 )
      v26 = *((_WORD *)a2 + 4) == *(_WORD *)pExceptionObject;
    if ( v25 )
      v27 = *((_WORD *)a2 + 5) == *(_WORD *)&pExceptionObject[2];
    if ( !v26
      || !v27
      || *((_WORD *)a2 + 7) != *(_WORD *)&pExceptionObject[6]
      || *((_WORD *)a2 + 8) != *(_WORD *)&pExceptionObject[8]
      || *((_WORD *)a2 + 9) != *(_WORD *)&pExceptionObject[10] )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_ddddddd(*((_QWORD *)WPP_GLOBAL_Control + 2));
      v53 = 4;
      v51 = &Broker::InvalidParameter::`vftable';
      v52 = 0;
      throw (Broker::InvalidParameter *)&v51;
    }
    v28 = *((unsigned int *)a2 + 7);
    if ( a4 )
      v29 = *(_QWORD *)&FileTime + 5000000 * v28 + 600000000LL * *((unsigned int *)a2 + 8);
    else
      v29 = *(_QWORD *)&FileTime + 5000000 * v28;
    if ( !*((_DWORD *)a2 + 6) )
    {
      FileTime = 0;
      GetSystemTimeAsFileTime(&FileTime);
      if ( v29 < *(_QWORD *)&FileTime )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_i(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v29);
        v53 = 4;
        v51 = &Broker::InvalidParameter::`vftable';
        v52 = 0;
        throw (Broker::InvalidParameter *)&v51;
      }
    }
  }
}

```

## disassembly

```asm
0x180002500  mov     [rsp-8+arg_10], rbx
0x180002505  push    rbp
0x180002506  push    rsi
0x180002507  push    rdi
0x180002508  lea     rbp, [rsp-47h]
0x18000250d  sub     rsp, 0D0h
0x180002514  mov     rax, cs:__security_cookie
0x18000251b  xor     rax, rsp
0x18000251e  mov     [rbp+57h+var_20], rax
0x180002522  mov     eax, [rdx+38h]
0x180002525  movzx   esi, r9b
0x180002529  dec     eax
0x18000252b  movzx   edi, r8b
0x18000252f  mov     rbx, rdx
0x180002532  cmp     eax, 0Eh
0x180002535  jbe     loc_180002CFB
0x18000253b  cmp     dword ptr [rdx+58h], 0
0x18000253f  jnz     loc_180002D4D
0x180002545  mov     r9d, [rdx]
0x180002548  mov     [rsp+0E0h+arg_0], r14
0x180002550  cmp     r9d, 4
0x180002554  jz      loc_18000260B
0x18000255a  mov     ecx, r9d
0x18000255d  test    r9d, r9d
0x180002560  jz      loc_180002710
0x180002566  sub     ecx, 1; this
0x180002569  jz      loc_180002ACB
0x18000256f  sub     ecx, 1
0x180002572  jz      loc_180002881
0x180002578  sub     ecx, 1
0x18000257b  jnz     loc_1800029B5
0x180002581  mov     r9d, [rdx+0Ch]
0x180002585  test    r9d, r9d
0x180002588  jz      loc_180002F40
0x18000258e  mov     ecx, [rdx+8]
0x180002591  cmp     r9d, ecx
0x180002594  ja      loc_180002F95
0x18000259a  lea     eax, [rcx-3Ch]
0x18000259d  cmp     eax, 15143h
0x1800025a2  ja      loc_180002FE7
0x1800025a8  mov     r9d, [rdx+10h]
0x1800025ac  cmp     r9d, 278D00h
0x1800025b3  jbe     loc_1800026E9
0x1800025b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800025c0  test    byte ptr [rcx+1Ch], 20h
0x1800025c4  jz      short loc_1800025E1
0x1800025c6  cmp     byte ptr [rcx+19h], 2
0x1800025ca  jb      short loc_1800025E1
0x1800025cc  mov     rcx, [rcx+10h]
0x1800025d0  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x1800025d7  mov     edx, 4Dh ; 'M'
0x1800025dc  call    WPP_SF_d
0x1800025e1  xorps   xmm0, xmm0
0x1800025e4  mov     [rbp+57h+var_48], 4
0x1800025eb  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x1800025f2  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x1800025f9  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x1800025fd  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180002601  movups  xmmword ptr [rbp+57h+pExceptionObject+8], xmm0
0x180002605  call    _CxxThrowException_0
0x18000260b  xorps   xmm0, xmm0
0x18000260e  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180002612  movups  xmmword ptr [rbp+57h+SystemTime], xmm0
0x180002616  call    cs:__imp_GetSystemTime
0x18000261c  test    dil, dil
0x18000261f  jnz     loc_18000352F
0x180002625  mov     ecx, [rbx+1Ch]
0x180002628  test    ecx, ecx
0x18000262a  jz      loc_180003581
0x180002630  mov     r9d, [rbx+18h]
0x180002634  test    r9d, r9d
0x180002637  jnz     loc_180002BDB
0x18000263d  movups  xmm0, xmmword ptr [rbx+8]
0x180002641  xor     r14d, r14d
0x180002644  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x180002648  lea     rcx, [rbp+57h+pExceptionObject]; lpSystemTime
0x18000264c  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], r14
0x180002650  movups  xmmword ptr [rbp+57h+pExceptionObject], xmm0
0x180002654  call    cs:__imp_SystemTimeToFileTime
0x18000265a  lea     rdx, [rbp+57h+pExceptionObject]; lpSystemTime
0x18000265e  mov     edi, eax
0x180002660  lea     rcx, [rbp+57h+FileTime]; lpFileTime
0x180002664  call    cs:__imp_FileTimeToSystemTime
0x18000266a  movzx   r9d, word ptr [rbx+8]
0x18000266f  mov     ecx, r14d
0x180002672  cmp     r9w, word ptr [rbp+57h+pExceptionObject]
0x180002677  mov     edx, r14d
0x18000267a  movzx   r11d, word ptr [rbx+0Eh]
0x18000267f  mov     r8d, r14d
0x180002682  movzx   r10d, word ptr [rbx+10h]
0x180002687  setz    cl
0x18000268a  movzx   esi, word ptr [rbx+12h]
0x18000268e  test    edi, edi
0x180002690  movzx   edi, word ptr [rbx+0Ah]
0x180002694  cmovnz  edx, ecx
0x180002697  cmp     di, word ptr [rbp+57h+pExceptionObject+2]
0x18000269b  mov     ecx, r14d
0x18000269e  setz    cl
0x1800026a1  test    eax, eax
0x1800026a3  mov     eax, r14d
0x1800026a6  cmovnz  r8d, ecx
0x1800026aa  and     r8d, edx
0x1800026ad  cmp     r11w, word ptr [rbp+57h+pExceptionObject+6]
0x1800026b2  setz    al
0x1800026b5  and     r8d, eax
0x1800026b8  cmp     r10w, word ptr [rbp+57h+pExceptionObject+8]
0x1800026bd  setz    r14b
0x1800026c1  and     r8d, r14d
0x1800026c4  cmp     si, word ptr [rbp+57h+pExceptionObject+0Ah]
0x1800026c8  setz    al
0x1800026cb  test    al, r8b
0x1800026ce  jz      loc_1800029F9
0x1800026d4  cmp     dword ptr [rbx+48h], 0
0x1800026d8  jnz     loc_180003662
0x1800026de  cmp     qword ptr [rbx+40h], 0
0x1800026e3  jnz     loc_180003678
0x1800026e9  mov     r14, [rsp+0E0h+arg_0]
0x1800026f1  mov     rcx, [rbp+57h+var_20]
0x1800026f5  xor     rcx, rsp; StackCookie
0x1800026f8  call    __security_check_cookie
0x1800026fd  mov     rbx, [rsp+0E0h+arg_10]
0x180002705  add     rsp, 0D0h
0x18000270c  pop     rdi
0x18000270d  pop     rsi
0x18000270e  pop     rbp
0x18000270f  retn
0x180002710  mov     r9d, [rdx+1Ch]
0x180002714  test    r9d, r9d
0x180002717  jz      loc_180003397
0x18000271d  cmp     r9d, 3Ch ; '<'
0x180002721  ja      loc_1800033EC
0x180002727  mov     r9d, [rdx+18h]
0x18000272b  cmp     r9d, 15181h
0x180002732  jnb     loc_1800034DD
0x180002738  lea     eax, [r9-1]
0x18000273c  cmp     eax, 3Ah ; ':'
0x18000273f  jbe     loc_1800034DD
0x180002745  mov     r9d, [rdx+20h]
0x180002749  cmp     r9d, 0A8C0h
0x180002750  ja      loc_18000343E
0x180002756  movups  xmm0, xmmword ptr [rdx+8]
0x18000275a  xor     r14d, r14d
0x18000275d  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x180002761  lea     rcx, [rbp+57h+pExceptionObject]; lpSystemTime
0x180002765  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], r14
0x180002769  movups  xmmword ptr [rbp+57h+pExceptionObject], xmm0
0x18000276d  call    cs:__imp_SystemTimeToFileTime
0x180002773  lea     rdx, [rbp+57h+pExceptionObject]; lpSystemTime
0x180002777  mov     edi, eax
0x180002779  lea     rcx, [rbp+57h+FileTime]; lpFileTime
0x18000277d  call    cs:__imp_FileTimeToSystemTime
0x180002783  movzx   r9d, word ptr [rbx+8]
0x180002788  mov     ecx, r14d
0x18000278b  cmp     r9w, word ptr [rbp+57h+pExceptionObject]
0x180002790  mov     r8d, eax
0x180002793  movzx   r11d, word ptr [rbx+0Eh]
0x180002798  mov     edx, r14d
0x18000279b  movzx   r10d, word ptr [rbx+10h]
0x1800027a0  setz    cl
0x1800027a3  test    edi, edi
0x1800027a5  mov     eax, r14d
0x1800027a8  movzx   edi, word ptr [rbx+0Ah]
0x1800027ac  cmovnz  edx, ecx
0x1800027af  cmp     di, word ptr [rbp+57h+pExceptionObject+2]
0x1800027b3  mov     ecx, r14d
0x1800027b6  setz    cl
0x1800027b9  test    r8d, r8d
0x1800027bc  movzx   r8d, word ptr [rbx+12h]
0x1800027c1  cmovnz  eax, ecx
0x1800027c4  mov     ecx, r14d
0x1800027c7  and     eax, edx
0x1800027c9  mov     edx, r14d
0x1800027cc  cmp     r11w, word ptr [rbp+57h+pExceptionObject+6]
0x1800027d1  setz    dl
0x1800027d4  and     edx, eax
0x1800027d6  cmp     r10w, word ptr [rbp+57h+pExceptionObject+8]
0x1800027db  setz    cl
0x1800027de  and     ecx, edx
0x1800027e0  cmp     r8w, word ptr [rbp+57h+pExceptionObject+0Ah]
0x1800027e5  setz    al
0x1800027e8  test    al, cl
0x1800027ea  jz      loc_180002A90
0x1800027f0  mov     eax, [rbx+1Ch]
0x1800027f3  imul    rdx, rax, 4C4B40h
0x1800027fa  add     rdx, qword ptr [rbp+57h+FileTime.dwLowDateTime]
0x1800027fe  test    sil, sil
0x180002801  jnz     loc_1800034CB
0x180002807  mov     rdi, rdx
0x18000280a  cmp     [rbx+18h], r14d
0x18000280e  jnz     loc_1800026E9
0x180002814  lea     rcx, [rbp+57h+FileTime]; lpSystemTimeAsFileTime
0x180002818  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], r14
0x18000281c  call    cs:__imp_GetSystemTimeAsFileTime
0x180002822  cmp     rdi, qword ptr [rbp+57h+FileTime.dwLowDateTime]
0x180002826  jge     loc_1800026E9
0x18000282c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002833  test    byte ptr [rcx+1Ch], 20h
0x180002837  jz      short loc_180002857
0x180002839  cmp     byte ptr [rcx+19h], 2
0x18000283d  jb      short loc_180002857
0x18000283f  mov     rcx, [rcx+10h]
0x180002843  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x18000284a  mov     edx, 43h ; 'C'
0x18000284f  mov     r9, rdi
0x180002852  call    WPP_SF_i
0x180002857  xorps   xmm0, xmm0
0x18000285a  mov     [rbp+57h+var_78], 4
0x180002861  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x180002868  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x18000286f  mov     [rbp+57h+var_90], rax
0x180002873  lea     rcx, [rbp+57h+var_90]; pExceptionObject
0x180002877  movups  [rbp+57h+var_88], xmm0
0x18000287b  call    _CxxThrowException_0
0x180002881  test    dil, dil
0x180002884  jnz     loc_180002A34
0x18000288a  mov     r9d, [rdx+18h]
0x18000288e  lea     eax, [r9-0Fh]
0x180002892  cmp     eax, 0A8B1h
0x180002897  ja      loc_1800031A8
0x18000289d  mov     r9d, [rdx+1Ch]
0x1800028a1  cmp     r9d, 0A8C0h
0x1800028a8  ja      loc_18000303C
0x1800028ae  movups  xmm0, xmmword ptr [rdx+8]
0x1800028b2  xor     r14d, r14d
0x1800028b5  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x1800028b9  lea     rcx, [rbp+57h+pExceptionObject]; lpSystemTime
0x1800028bd  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], r14
0x1800028c1  movups  xmmword ptr [rbp+57h+pExceptionObject], xmm0
0x1800028c5  call    cs:__imp_SystemTimeToFileTime
0x1800028cb  lea     rdx, [rbp+57h+pExceptionObject]; lpSystemTime
0x1800028cf  mov     edi, eax
0x1800028d1  lea     rcx, [rbp+57h+FileTime]; lpFileTime
0x1800028d5  call    cs:__imp_FileTimeToSystemTime
0x1800028db  movzx   r9d, word ptr [rbx+8]
0x1800028e0  mov     ecx, r14d
0x1800028e3  cmp     r9w, word ptr [rbp+57h+pExceptionObject]
0x1800028e8  mov     r8d, eax
0x1800028eb  movzx   r11d, word ptr [rbx+0Eh]
0x1800028f0  mov     edx, r14d
0x1800028f3  movzx   r10d, word ptr [rbx+10h]
0x1800028f8  setz    cl
0x1800028fb  test    edi, edi
0x1800028fd  mov     eax, r14d
0x180002900  movzx   edi, word ptr [rbx+0Ah]
0x180002904  cmovnz  edx, ecx
0x180002907  cmp     di, word ptr [rbp+57h+pExceptionObject+2]
0x18000290b  mov     ecx, r14d
0x18000290e  setz    cl
0x180002911  test    r8d, r8d
0x180002914  movzx   r8d, word ptr [rbx+12h]
0x180002919  cmovnz  eax, ecx
0x18000291c  mov     ecx, r14d
0x18000291f  and     eax, edx
0x180002921  mov     edx, r14d
0x180002924  cmp     r11w, word ptr [rbp+57h+pExceptionObject+6]
0x180002929  setz    dl
0x18000292c  and     edx, eax
0x18000292e  cmp     r10w, word ptr [rbp+57h+pExceptionObject+8]
0x180002933  setz    cl
0x180002936  and     ecx, edx
0x180002938  cmp     r8w, word ptr [rbp+57h+pExceptionObject+0Ah]
0x18000293d  setz    al
0x180002940  test    al, cl
0x180002942  jz      loc_180002BA0
0x180002948  mov     eax, [rbx+1Ch]
0x18000294b  mov     ecx, 0Fh
0x180002950  cmp     eax, ecx
0x180002952  cmovb   eax, ecx
0x180002955  test    byte ptr [rbx+20h], 1
0x180002959  jnz     loc_180002C3D
0x18000295f  mov     r9d, [rbx+20h]
0x180002963  test    r9b, 8
0x180002967  jnz     loc_1800030C9
0x18000296d  test    r9d, 0FFFFFFF0h
0x180002974  jz      loc_1800026E9
0x18000297a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002981  test    byte ptr [rcx+1Ch], 20h
0x180002985  jnz     loc_180003184
0x18000298b  xorps   xmm0, xmm0
0x18000298e  mov     [rbp+57h+var_78], 4
0x180002995  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x18000299c  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x1800029a3  mov     [rbp+57h+var_90], rax
0x1800029a7  lea     rcx, [rbp+57h+var_90]; pExceptionObject
0x1800029ab  movups  [rbp+57h+var_88], xmm0
0x1800029af  call    _CxxThrowException_0
0x1800029b5  cmp     ecx, 2
0x1800029b8  jz      loc_180002DCF
0x1800029be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800029c5  test    byte ptr [rcx+1Ch], 20h
0x1800029c9  jnz     loc_180002DAB
0x1800029cf  xorps   xmm0, xmm0
0x1800029d2  mov     [rbp+57h+var_48], 4
0x1800029d9  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x1800029e0  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x1800029e7  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x1800029eb  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800029ef  movups  xmmword ptr [rbp+57h+pExceptionObject+8], xmm0
0x1800029f3  call    _CxxThrowException_0
0x1800029f9  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
