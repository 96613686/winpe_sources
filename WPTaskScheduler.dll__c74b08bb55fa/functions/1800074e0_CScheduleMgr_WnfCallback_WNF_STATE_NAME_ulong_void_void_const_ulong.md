# CScheduleMgr::WnfCallback(_WNF_STATE_NAME *,ulong,void *,void * const,ulong)

- ea: `0x1800074e0`
- end: `0x180007ddd`
- name: `?WnfCallback@CScheduleMgr@@QEAAXPEAU_WNF_STATE_NAME@@KPEAXQEAXK@Z`
- size: `2301`
- prototype: `void __fastcall(CScheduleMgr *__hidden this, struct _WNF_STATE_NAME *, unsigned int, void *, void *const, unsigned int)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180007410`

## callees

- `0x1800074e0`
- `0x180008bf8`
- `0x18000e9c8`
- `0x18000ea40`
- `0x18000eef0`
- `0x18000f0c0`
- `0x18000f760`
- `0x18000f7cc`
- `0x180017370`
- `0x180019c80`
- `0x18001f65c`
- `0x18001f87c`
- `0x18001fbac`
- `0x18001fbe0`
- `0x18001fd14`
- `0x180020c30`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180007dd2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180007dd2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800079f4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800079f4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180007dc9`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180007dc9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000755d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800078fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800079cb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000755d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800078fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800079cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800077f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007967`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007a0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800077f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007967`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007a0d`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800075e0`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180007646`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800075e0`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180007646`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x18000767d`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x18000767d`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180007624`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180007624`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800075c1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800075c1`

## pseudocode

```c
void __fastcall CScheduleMgr::WnfCallback(
        CScheduleMgr *this,
        struct _WNF_STATE_NAME *a2,
        __int64 a3,
        void *a4,
        void *const a5,
        unsigned int a6)
{
  int v6; // r13d
  struct _WNF_STATE_NAME *v7; // rbx
  char v8; // r12
  __int64 v9; // rcx
  DWORD v10; // eax
  void **v11; // rax
  void **v12; // r9
  __int64 v13; // r10
  struct _WNF_STATE_NAME v14; // r11
  __int64 v15; // rcx
  char v16; // si
  unsigned __int64 v17; // rdx
  void **i; // rcx
  __int64 v19; // r8
  void **v20; // rdx
  __int64 v21; // rbx
  __int64 v22; // r14
  __int64 j; // rbx
  __int64 *k; // rsi
  bool v25; // zf
  int v26; // eax
  int v27; // edi
  __int64 *v28; // rcx
  struct CSchedule *m; // rdx
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v31; // rbx
  unsigned __int64 *v32; // rax
  void (__fastcall ***v33)(_QWORD, SYSTEMTIME *); // rcx
  __int64 v34; // rax
  __int64 *v35; // rax
  __int64 *v36; // rcx
  __int64 v37; // rax
  _QWORD *v38; // rax
  __int64 v39; // rcx
  struct CSchedule *v40; // rax
  char v41; // [rsp+68h] [rbp-A0h]
  _QWORD v42[2]; // [rsp+70h] [rbp-98h] BYREF
  struct _WNF_STATE_NAME *v43; // [rsp+80h] [rbp-88h]
  void *v44; // [rsp+88h] [rbp-80h]
  char v45[48]; // [rsp+90h] [rbp-78h] BYREF
  SYSTEMTIME v46; // [rsp+C0h] [rbp-48h] BYREF
  struct _FILETIME v47; // [rsp+D0h] [rbp-38h]
  struct _FILETIME v48; // [rsp+D8h] [rbp-30h]
  int v49; // [rsp+E0h] [rbp-28h]
  int v50; // [rsp+E4h] [rbp-24h]
  int v51; // [rsp+E8h] [rbp-20h]
  struct _SYSTEMTIME SystemTime; // [rsp+F0h] [rbp-18h] BYREF
  struct _TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+108h] [rbp+0h] BYREF
  DWORD v54; // [rsp+1B4h] [rbp+ACh]
  SYSTEMTIME v55; // [rsp+1B8h] [rbp+B0h] BYREF
  struct _FILETIME v56; // [rsp+1C8h] [rbp+C0h] BYREF
  struct _FILETIME v57; // [rsp+1D0h] [rbp+C8h]
  __int64 v58; // [rsp+1D8h] [rbp+D0h]
  int v59; // [rsp+1E0h] [rbp+D8h]
  SYSTEMTIME v60; // [rsp+1E8h] [rbp+E0h] BYREF
  struct _FILETIME FileTime; // [rsp+1F8h] [rbp+F0h] BYREF
  struct _FILETIME v62; // [rsp+200h] [rbp+F8h]
  __int64 v63; // [rsp+208h] [rbp+100h]
  int v64; // [rsp+210h] [rbp+108h]
  struct _SYSTEMTIME v65; // [rsp+218h] [rbp+110h] BYREF

  v6 = a3;
  v44 = a5;
  v42[1] = v42;
  v42[0] = v42;
  v7 = a2;
  v43 = a2;
  if ( !a2 )
  {
    if ( (byte_180030D04 & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(this, ErrorNullPointer, a3, 1, &v65);
    return;
  }
  v8 = 0;
  v41 = 0;
  EnterCriticalSection(&CriticalSection);
  if ( (byte_180030D01 & 0x40) != 0 )
    McTemplateU0qq_EventWriteTransfer(v9, WNFEventProcessingStart, v7->Data[0], v7->Data[1]);
  v58 = 0;
  v56 = 0;
  v57 = 0;
  v55 = 0;
  FileTime = 0;
  v60 = 0;
  v62 = 0;
  SystemTime = 0;
  v59 = 0;
  v63 = 0;
  v64 = 0;
  GetSystemTime(&SystemTime);
  v60 = SystemTime;
  if ( SystemTimeToFileTime(&v60, &FileTime) )
  {
    v62 = FileTime;
    v63 = 0;
    v64 = 1;
  }
  v65 = 0;
  GetLocalTime(&v65);
  v55 = v65;
  if ( SystemTimeToFileTime(&v55, &v56) )
  {
    v57 = v56;
    v58 = 0;
    v59 = 1;
  }
  v10 = GetTimeZoneInformation(&TimeZoneInformation);
  v54 = v10;
  if ( (byte_180030D02 & 1) != 0 )
  {
    McTemplateU0hhhhhhhqt_EventWriteTransfer(
      *(_QWORD *)&v55.wHour >> 16,
      (unsigned int)TimeDateLocal,
      v55.wYear,
      *(_QWORD *)&v55.wYear >> 16,
      v55.wDay,
      v55.wHour,
      v55.wMinute,
      v55.wSecond,
      v55.wMilliseconds,
      v10,
      v10 == 2);
    v7 = v43;
    if ( (byte_180030D02 & 1) != 0 )
      McTemplateU0hhhhhhhqt_EventWriteTransfer(
        HIWORD(*(_QWORD *)&v60.wYear),
        (unsigned int)TimeDateUTC,
        v60.wYear,
        *(_QWORD *)&v60.wYear >> 16,
        v60.wDay,
        v60.wHour,
        v60.wMinute,
        v60.wSecond,
        v60.wMilliseconds,
        0,
        0);
  }
  v11 = (void **)xmmword_180030BE0;
  v12 = (void **)xmmword_180030BE0;
  v13 = *(_QWORD *)(xmmword_180030BE0 + 8);
  v14 = *v7;
  v15 = v13;
  v16 = *(_BYTE *)(v13 + 25);
  if ( !v16 )
  {
    do
    {
      v17 = *(_QWORD *)(v15 + 32);
      if ( v17 < *(_QWORD *)&v14 )
      {
        v15 = *(_QWORD *)(v15 + 16);
      }
      else
      {
        if ( *((_BYTE *)v12 + 25) && *(_QWORD *)&v14 < v17 )
          v12 = (void **)v15;
        v11 = (void **)v15;
        v15 = *(_QWORD *)v15;
      }
    }
    while ( !*(_BYTE *)(v15 + 25) );
  }
  if ( *((_BYTE *)v12 + 25) )
    i = *(void ***)(xmmword_180030BE0 + 8);
  else
    i = (void **)*v12;
  while ( !*((_BYTE *)i + 25) )
  {
    if ( *(_QWORD *)&v14 < (unsigned __int64)i[4] )
    {
      v12 = i;
      i = (void **)*i;
    }
    else
    {
      i = (void **)i[2];
    }
  }
  v19 = 0;
  while ( v11 != v12 )
  {
    ++v19;
    if ( !*((_BYTE *)v11 + 25) )
    {
      i = (void **)v11[2];
      if ( *((_BYTE *)i + 25) )
      {
        for ( i = (void **)v11[1]; !*((_BYTE *)i + 25); i = (void **)i[1] )
        {
          if ( v11 != i[2] )
            break;
          v11 = i;
        }
LABEL_48:
        v11 = i;
      }
      else
      {
        v20 = (void **)*i;
        if ( *((_BYTE *)*i + 25) )
          goto LABEL_48;
        do
        {
          i = (void **)*v20;
          v11 = v20;
          v20 = i;
        }
        while ( !*((_BYTE *)i + 25) );
      }
    }
  }
  if ( v19 )
  {
    v21 = xmmword_180030BE0;
    if ( !v16 )
    {
      do
      {
        if ( *(_QWORD *)(v13 + 32) < *(unsigned __int64 *)&v14 )
        {
          v13 = *(_QWORD *)(v13 + 16);
        }
        else
        {
          v21 = v13;
          v13 = *(_QWORD *)v13;
        }
      }
      while ( !*(_BYTE *)(v13 + 25) );
    }
    if ( v21 == (_QWORD)xmmword_180030BE0 || *(unsigned __int64 *)&v14 < *(_QWORD *)(v21 + 32) )
    {
      *(struct _WNF_STATE_NAME *)&v65.wYear = v14;
      *(_QWORD *)&v65.wHour = 0;
      v32 = (unsigned __int64 *)std::_Tree_buy<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>>::_Buynode<std::pair<unsigned __int64,_EVENT_SUBSCRIPTION *>>(
                                  &xmmword_180030BE0,
                                  &v65);
      std::_Tree<std::_Tmap_traits<unsigned __int64,_EVENT_SUBSCRIPTION *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>>,0>>::_Insert_hint<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *> &,std::_Tree_node<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>,void *> *>(
        (__int64)&xmmword_180030BE0,
        &SystemTime,
        v21,
        v32 + 4,
        v32);
      v21 = *(_QWORD *)&SystemTime.wYear;
    }
    v22 = *(_QWORD *)(v21 + 40);
    i = (void **)&g_ScheduleMgr;
    for ( j = *(_QWORD *)(v22 + 8); j != *(_QWORD *)(v22 + 16); j += 16 )
    {
      if ( v6 != *(_DWORD *)(j + 8) && *(_QWORD *)j )
      {
        for ( k = (__int64 *)g_ScheduleMgr; ; k = (__int64 *)*k )
        {
          if ( k == (__int64 *)&g_ScheduleMgr )
            goto LABEL_39;
          if ( *(__int64 **)j == k )
            break;
        }
        *(_DWORD *)(j + 8) = v6;
        if ( k[25] && k[27] )
        {
          v25 = (*((_BYTE *)k + 44) & 8) == 0;
          v51 = 1;
          if ( v25 )
          {
            v46 = v55;
            v47 = v56;
            v48 = v57;
            v49 = v58;
            v26 = HIDWORD(v58);
          }
          else
          {
            v46 = v60;
            v47 = FileTime;
            v48 = v62;
            v49 = v63;
            v26 = HIDWORD(v63);
          }
          v50 = v26;
          EnterCriticalSection((LPCRITICAL_SECTION)(k + 28));
          v27 = (*(__int64 (__fastcall **)(__int64, SYSTEMTIME *, struct _WNF_STATE_NAME *, void *, unsigned int))(*(_QWORD *)k[25] + 128LL))(
                  k[25],
                  &v46,
                  v43,
                  v44,
                  a6);
          if ( (*((_BYTE *)k + 44) & 2) == 0 && !*((_DWORD *)k + 66) )
          {
            v28 = k + 12;
            if ( !*((_DWORD *)k + 34) || (v34 = TimeValue::AtLimitTime(v28, v45), (unsigned int)operator<=(&v46, v34)) )
            {
              if ( (!*((_DWORD *)k + 22) || (unsigned int)operator>=(&v46, k + 6)) && v27 )
              {
                if ( byte_180030D04 < 0 )
                  McTemplateU0j_EventWriteTransfer(v28, TriggeredInWnfHandler, k + 2);
                v33 = (void (__fastcall ***)(_QWORD, SYSTEMTIME *))k[27];
                ++*((_DWORD *)k + 36);
                (**v33)(v33, &v46);
                (*(void (__fastcall **)(__int64, SYSTEMTIME *))(*(_QWORD *)k[25] + 72LL))(k[25], &v46);
                (*(void (__fastcall **)(__int64, SYSTEMTIME *, __int64))(*(_QWORD *)k[25] + 96LL))(k[25], &v46, 1);
                if ( (*((_BYTE *)k + 44) & 1) != 0 )
                {
                  TaskStore::PersistStatistics(qword_180030AC8, (const struct _GUID *)k + 1);
                  TaskStore::PersistRuntimeData(qword_180030AC8, (const struct _GUID *)k + 1, 1);
                }
                if ( !*((_DWORD *)k + 66) )
                  CSchedule::UpdateState((CSchedule *)k, (const struct TimeInfo *)&TimeZoneInformation);
              }
            }
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)(k + 28));
LABEL_64:
          i = (void **)&g_ScheduleMgr;
        }
        else if ( (byte_180030D04 & 1) != 0 )
        {
          McGenEventWrite_EventWriteTransfer(&g_ScheduleMgr, ErrorNullPointer, v19, 1, &v65);
          goto LABEL_64;
        }
        if ( k && *((_DWORD *)k + 66) && (*((_BYTE *)k + 44) & 4) != 0 )
        {
          v35 = (__int64 *)k[1];
          v36 = (__int64 *)*k;
          *v35 = *k;
          v36[1] = (__int64)v35;
          v37 = v42[0];
          *k = v42[0];
          k[1] = (__int64)v42;
          *(_QWORD *)(v37 + 8) = k;
          v42[0] = k;
          if ( (*((_BYTE *)k + 44) & 1) != 0 )
            TaskStore::Delete((TaskStore *)v42, (struct _GUID *)k + 1);
          i = (void **)&g_ScheduleMgr;
        }
        ++v41;
        continue;
      }
LABEL_39:
      ;
    }
    v7 = v43;
    v8 = v41;
  }
  else if ( (byte_180030D07 & 0x10) != 0 )
  {
    McTemplateU0qq_EventWriteTransfer(i, ErrorWNFNotSubscribedEvent, v7->Data[0], v7->Data[1]);
  }
  if ( (byte_180030D01 & 0x40) != 0 )
    McTemplateU0qqq_EventWriteTransfer(
      (_DWORD)i,
      (unsigned int)WNFEventProcessingCompleted,
      v7->Data[0],
      v7->Data[1],
      v8);
  LeaveCriticalSection(&CriticalSection);
  if ( (_QWORD *)v42[0] != v42 )
  {
    EnterCriticalSection(&CScheduleMgr::CritLockExpired);
    for ( m = (struct CSchedule *)v42[0]; (_QWORD *)v42[0] != v42; m = (struct CSchedule *)v42[0] )
    {
      v38 = (_QWORD *)*((_QWORD *)m + 1);
      v39 = *(_QWORD *)m;
      *v38 = *(_QWORD *)m;
      *(_QWORD *)(v39 + 8) = v38;
      v40 = CScheduleMgr::ExpiredScheduleList;
      *(_QWORD *)m = CScheduleMgr::ExpiredScheduleList;
      *((_QWORD *)m + 1) = &CScheduleMgr::ExpiredScheduleList;
      *((_QWORD *)v40 + 1) = m;
      CScheduleMgr::ExpiredScheduleList = m;
    }
    ThreadpoolWork = CreateThreadpoolWork(CScheduleMgr::DeleteExpiredWorker, 0, &ThreadpoolCallBackEnvironment);
    v31 = ThreadpoolWork;
    if ( ThreadpoolWork )
    {
      SubmitThreadpoolWork(ThreadpoolWork);
      CloseThreadpoolWork(v31);
    }
    LeaveCriticalSection(&CScheduleMgr::CritLockExpired);
  }
}

```

## disassembly

```asm
0x1800074e0  mov     r11, rsp
0x1800074e3  push    rbp
0x1800074e4  push    rbx
0x1800074e5  push    r13
0x1800074e7  lea     rbp, [r11-158h]
0x1800074ee  sub     rsp, 240h
0x1800074f5  mov     rax, cs:__security_cookie
0x1800074fc  xor     rax, rsp
0x1800074ff  mov     [rbp+150h+var_30], rax
0x180007506  mov     rax, [rbp+150h+arg_20]
0x18000750d  mov     r13d, r8d
0x180007510  mov     [rbp+150h+var_1D0], rax
0x180007514  lea     rax, [rsp+250h+var_1E8]
0x180007519  mov     [rsp+250h+var_1E0], rax
0x18000751e  lea     rax, [rsp+250h+var_1E8]
0x180007523  mov     [rsp+250h+var_1E8], rax
0x180007528  mov     rbx, rdx
0x18000752b  mov     [rsp+250h+var_1D8], rdx
0x180007530  test    rdx, rdx
0x180007533  jz      loc_180007B29
0x180007539  mov     [r11+8], rsi
0x18000753d  lea     rcx, CriticalSection; lpCriticalSection
0x180007544  mov     [r11+18h], rdi
0x180007548  xor     edi, edi
0x18000754a  mov     [r11+20h], r12
0x18000754e  mov     r12d, edi
0x180007551  mov     [r11-20h], r14
0x180007555  mov     [r11-28h], r15
0x180007559  mov     dword ptr [rsp+250h+var_1F0], edi
0x18000755d  call    cs:__imp_EnterCriticalSection
0x180007563  test    cs:byte_180030D01, 40h
0x18000756a  jnz     loc_180007B59
0x180007570  xor     eax, eax
0x180007572  mov     [rbp+150h+var_80], rdi
0x180007579  xorps   xmm0, xmm0
0x18000757c  mov     qword ptr [rbp+150h+var_90.dwLowDateTime], rax
0x180007583  lea     rcx, [rbp+150h+SystemTime]; lpSystemTime
0x180007587  mov     [rbp+150h+var_88], rax
0x18000758e  movups  xmmword ptr [rbp+150h+var_A0.wYear], xmm0
0x180007595  mov     qword ptr [rbp+150h+FileTime.dwLowDateTime], rax
0x18000759c  movups  xmmword ptr [rbp+150h+var_70.wYear], xmm0
0x1800075a3  mov     [rbp+150h+var_58], rax
0x1800075aa  movups  xmmword ptr [rbp+150h+SystemTime.wYear], xmm0
0x1800075ae  mov     [rbp+150h+var_78], edi
0x1800075b4  mov     [rbp+150h+var_50], rdi
0x1800075bb  mov     [rbp+150h+var_48], edi
0x1800075c1  call    cs:__imp_GetSystemTime
0x1800075c7  movups  xmm0, xmmword ptr [rbp+150h+SystemTime.wYear]
0x1800075cb  lea     rdx, [rbp+150h+FileTime]; lpFileTime
0x1800075d2  lea     rcx, [rbp+150h+var_70]; lpSystemTime
0x1800075d9  movaps  xmmword ptr [rbp+150h+var_70.wYear], xmm0
0x1800075e0  call    cs:__imp_SystemTimeToFileTime
0x1800075e6  test    eax, eax
0x1800075e8  jz      short loc_180007613
0x1800075ea  mov     eax, [rbp+150h+FileTime.dwHighDateTime]
0x1800075f0  mov     dword ptr [rbp+150h+var_58+4], eax
0x1800075f6  mov     eax, [rbp+150h+FileTime.dwLowDateTime]
0x1800075fc  mov     dword ptr [rbp+150h+var_58], eax
0x180007602  mov     [rbp+150h+var_50], rdi
0x180007609  mov     [rbp+150h+var_48], 1
0x180007613  xorps   xmm0, xmm0
0x180007616  lea     rcx, [rbp+150h+var_40]; lpSystemTime
0x18000761d  movups  xmmword ptr [rbp+150h+var_40.wYear], xmm0
0x180007624  call    cs:__imp_GetLocalTime
0x18000762a  movups  xmm0, xmmword ptr [rbp+150h+var_40.wYear]
0x180007631  lea     rdx, [rbp+150h+var_90]; lpFileTime
0x180007638  lea     rcx, [rbp+150h+var_A0]; lpSystemTime
0x18000763f  movaps  xmmword ptr [rbp+150h+var_A0.wYear], xmm0
0x180007646  call    cs:__imp_SystemTimeToFileTime
0x18000764c  test    eax, eax
0x18000764e  jz      short loc_180007679
0x180007650  mov     eax, [rbp+150h+var_90.dwHighDateTime]
0x180007656  mov     dword ptr [rbp+150h+var_88+4], eax
0x18000765c  mov     eax, [rbp+150h+var_90.dwLowDateTime]
0x180007662  mov     dword ptr [rbp+150h+var_88], eax
0x180007668  mov     [rbp+150h+var_80], rdi
0x18000766f  mov     [rbp+150h+var_78], 1
0x180007679  lea     rcx, [rbp+150h+TimeZoneInformation]; lpTimeZoneInformation
0x18000767d  call    cs:__imp_GetTimeZoneInformation
0x180007683  movzx   ecx, cs:byte_180030D02
0x18000768a  mov     [rbp+150h+var_A4], eax
0x180007690  test    cl, 1
0x180007693  jnz     loc_180007B71
0x180007699  mov     rdi, qword ptr cs:xmmword_180030BE0
0x1800076a0  mov     r14d, [rbx+4]
0x1800076a4  mov     rax, rdi
0x1800076a7  mov     r15d, [rbx]
0x1800076aa  mov     r11d, r14d
0x1800076ad  shl     r11, 20h
0x1800076b1  mov     r9, rdi
0x1800076b4  mov     r10, [rdi+8]
0x1800076b8  or      r11, r15
0x1800076bb  mov     rcx, r10
0x1800076be  movzx   esi, byte ptr [r10+19h]
0x1800076c3  test    sil, sil
0x1800076c6  jnz     short loc_1800076EE
0x1800076c8  mov     rdx, [rcx+20h]
0x1800076cc  cmp     rdx, r11
0x1800076cf  jb      loc_18000798F
0x1800076d5  cmp     [r9+19h], r12b
0x1800076d9  jz      short loc_1800076E2
0x1800076db  cmp     r11, rdx
0x1800076de  cmovb   r9, rcx
0x1800076e2  mov     rax, rcx
0x1800076e5  mov     rcx, [rcx]
0x1800076e8  cmp     [rcx+19h], r12b
0x1800076ec  jz      short loc_1800076C8
0x1800076ee  cmp     [r9+19h], r12b
0x1800076f2  jz      loc_180007998
0x1800076f8  mov     rcx, r10
0x1800076fb  cmp     [rcx+19h], r12b
0x1800076ff  jnz     short loc_180007715
0x180007701  cmp     r11, [rcx+20h]
0x180007705  jb      loc_180007A18
0x18000770b  mov     rcx, [rcx+10h]
0x18000770f  cmp     [rcx+19h], r12b
0x180007713  jz      short loc_180007701
0x180007715  xor     r8d, r8d
0x180007718  cmp     rax, r9
0x18000771b  jz      short loc_180007752
0x18000771d  inc     r8
0x180007720  cmp     [rax+19h], r12b
0x180007724  jnz     short loc_180007718
0x180007726  mov     rcx, [rax+10h]
0x18000772a  cmp     [rcx+19h], r12b
0x18000772e  jnz     loc_18000782F
0x180007734  mov     rdx, [rcx]
0x180007737  cmp     [rdx+19h], r12b
0x18000773b  jnz     loc_180007853
0x180007741  mov     rcx, [rdx]
0x180007744  mov     rax, rdx
0x180007747  mov     rdx, rcx
0x18000774a  cmp     [rcx+19h], r12b
0x18000774e  jnz     short loc_180007718
0x180007750  jmp     short loc_180007741
0x180007752  test    r8, r8
0x180007755  jz      loc_1800079A0
0x18000775b  mov     rbx, rdi
0x18000775e  test    sil, sil
0x180007761  jnz     short loc_180007779
0x180007763  cmp     [r10+20h], r11
0x180007767  jb      loc_18000785B
0x18000776d  mov     rbx, r10
0x180007770  mov     r10, [r10]
0x180007773  cmp     [r10+19h], r12b
0x180007777  jz      short loc_180007763
0x180007779  cmp     rbx, rdi
0x18000777c  jz      loc_180007A5B
0x180007782  cmp     r11, [rbx+20h]
0x180007786  jb      loc_180007A5B
0x18000778c  mov     r14, [rbx+28h]
0x180007790  lea     rcx, ?g_ScheduleMgr@@3VCScheduleMgr@@A; CScheduleMgr g_ScheduleMgr
0x180007797  mov     r12d, [rbp+150h+arg_28]
0x18000779e  mov     rbx, [r14+8]
0x1800077a2  cmp     rbx, [r14+10h]
0x1800077a6  jz      short loc_1800077B8
0x1800077a8  cmp     r13d, [rbx+8]
0x1800077ac  jnz     loc_180007864
0x1800077b2  add     rbx, 10h
0x1800077b6  jmp     short loc_1800077A2
0x1800077b8  mov     rbx, [rsp+250h+var_1D8]
0x1800077bd  mov     r12d, dword ptr [rsp+250h+var_1F0]
0x1800077c2  test    cs:byte_180030D01, 40h
0x1800077c9  mov     r15, [rsp+250h+var_20]
0x1800077d1  mov     r14, [rsp+238h]
0x1800077d9  mov     rdi, [rsp+250h+arg_10]
0x1800077e1  mov     rsi, [rsp+250h+arg_0]
0x1800077e9  jnz     loc_180007D67
0x1800077ef  lea     rcx, CriticalSection; lpCriticalSection
0x1800077f6  call    cs:__imp_LeaveCriticalSection
0x1800077fc  mov     r12, [rsp+250h+arg_18]
0x180007804  lea     rax, [rsp+250h+var_1E8]
0x180007809  cmp     [rsp+250h+var_1E8], rax
0x18000780e  jnz     loc_1800079C4
0x180007814  mov     rcx, [rbp+150h+var_30]
0x18000781b  xor     rcx, rsp; StackCookie
0x18000781e  call    __security_check_cookie
0x180007823  add     rsp, 240h
0x18000782a  pop     r13
0x18000782c  pop     rbx
0x18000782d  pop     rbp
0x18000782e  retn
0x18000782f  mov     rcx, [rax+8]
0x180007833  cmp     [rcx+19h], r12b
0x180007837  jnz     short loc_180007853
0x180007839  nop     dword ptr [rax+00000000h]
0x180007840  cmp     rax, [rcx+10h]
0x180007844  jnz     short loc_180007853
0x180007846  mov     rax, rcx
0x180007849  mov     rcx, [rcx+8]
0x18000784d  cmp     [rcx+19h], r12b
0x180007851  jz      short loc_180007840
0x180007853  mov     rax, rcx
0x180007856  jmp     loc_180007718
0x18000785b  mov     r10, [r10+10h]
0x18000785f  jmp     loc_180007773
0x180007864  cmp     qword ptr [rbx], 0
0x180007868  jz      loc_1800077B2
0x18000786e  mov     rsi, cs:?g_ScheduleMgr@@3VCScheduleMgr@@A; CScheduleMgr g_ScheduleMgr
0x180007875  cmp     rsi, rcx
0x180007878  jz      loc_1800077B2
0x18000787e  cmp     [rbx], rsi
0x180007881  jnz     loc_180007A23
0x180007887  mov     [rbx+8], r13d
0x18000788b  cmp     qword ptr [rsi+0C8h], 0
0x180007893  jz      loc_180007A2B
0x180007899  cmp     qword ptr [rsi+0D8h], 0
0x1800078a1  jz      loc_180007A2B
0x1800078a7  test    byte ptr [rsi+2Ch], 8
0x1800078ab  mov     [rbp+150h+var_170], 1
0x1800078b2  jnz     loc_180007C65
0x1800078b8  mov     rax, qword ptr [rbp+150h+var_A0.wYear]
0x1800078bf  mov     [rbp+150h+var_198], rax
0x1800078c3  mov     rax, qword ptr [rbp+150h+var_A0.wHour]
0x1800078ca  mov     [rbp+150h+var_190], rax
0x1800078ce  mov     rax, qword ptr [rbp+150h+var_90.dwLowDateTime]
0x1800078d5  mov     [rbp+150h+var_188], rax
0x1800078d9  mov     rax, [rbp+150h+var_88]
0x1800078e0  mov     [rbp+150h+var_180], rax
0x1800078e4  mov     eax, dword ptr [rbp+150h+var_80]
0x1800078ea  mov     [rbp+150h+var_178], eax
0x1800078ed  mov     eax, dword ptr [rbp+150h+var_80+4]
0x1800078f3  lea     rcx, [rsi+0E0h]; lpCriticalSection
0x1800078fa  mov     [rbp+150h+var_174], eax
0x1800078fd  call    cs:__imp_EnterCriticalSection
0x180007903  mov     rcx, [rsi+0C8h]
0x18000790a  lea     rdx, [rbp+150h+var_198]
0x18000790e  mov     r9, [rbp+150h+var_1D0]
0x180007912  mov     r8, [rsp+250h+var_1D8]
0x180007917  mov     dword ptr [rsp+250h+var_230], r12d
0x18000791c  mov     rax, [rcx]
0x18000791f  mov     rax, [rax+80h]
0x180007926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000792b  test    byte ptr [rsi+2Ch], 2
0x18000792f  mov     edi, eax
0x180007931  jnz     short loc_180007960
0x180007933  cmp     dword ptr [rsi+108h], 0
0x18000793a  jnz     short loc_180007960
0x18000793c  lea     rcx, [rsi+60h]
0x180007940  cmp     dword ptr [rcx+28h], 0
0x180007944  jnz     loc_180007CA5
0x18000794a  cmp     dword ptr [rsi+58h], 0
0x18000794e  lea     rdx, [rsi+30h]
0x180007952  jnz     loc_180007CC7
0x180007958  test    edi, edi
0x18000795a  jnz     loc_180007AA1
0x180007960  lea     rcx, [rsi+0E0h]; lpCriticalSection
0x180007967  call    cs:__imp_LeaveCriticalSection
0x18000796d  lea     rcx, ?g_ScheduleMgr@@3VCScheduleMgr@@A; CScheduleMgr g_ScheduleMgr
0x180007974  test    rsi, rsi
0x180007977  jz      short loc_180007986
0x180007979  cmp     dword ptr [rsi+108h], 0
0x180007980  jnz     loc_180007D1A
0x180007986  inc     dword ptr [rsp+250h+var_1F0]
0x18000798a  jmp     loc_1800077B2
0x18000798f  mov     rcx, [rcx+10h]
0x180007993  jmp     loc_1800076E8
0x180007998  mov     rcx, [r9]
0x18000799b  jmp     loc_1800076FB
0x1800079a0  test    cs:byte_180030D07, 10h
0x1800079a7  jz      loc_1800077C2
0x1800079ad  mov     r9d, r14d
0x1800079b0  lea     rdx, ErrorWNFNotSubscribedEvent
0x1800079b7  mov     r8d, r15d
0x1800079ba  call    McTemplateU0qq_EventWriteTransfer
0x1800079bf  jmp     loc_1800077C2
0x1800079c4  lea     rcx, ?CritLockExpired@CScheduleMgr@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800079cb  call    cs:__imp_EnterCriticalSection
0x1800079d1  mov     rdx, [rsp+250h+var_1E8]
0x1800079d6  lea     rax, [rsp+250h+var_1E8]
0x1800079db  cmp     rdx, rax
0x1800079de  jnz     loc_180007D84
0x1800079e4  lea     r8, ?ThreadpoolCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x1800079eb  xor     edx, edx; pv
0x1800079ed  lea     rcx, ?DeleteExpiredWorker@CScheduleMgr@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800079f4  call    cs:__imp_CreateThreadpoolWork
0x1800079fa  mov     rbx, rax
0x1800079fd  test    rax, rax
0x180007a00  jnz     loc_180007DC6
0x180007a06  lea     rcx, ?CritLockExpired@CScheduleMgr@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180007a0d  call    cs:__imp_LeaveCriticalSection
0x180007a13  jmp     loc_180007814
0x180007a18  mov     r9, rcx
0x180007a1b  mov     rcx, [rcx]
0x180007a1e  jmp     loc_18000770F
0x180007a23  mov     rsi, [rsi]
0x180007a26  jmp     loc_180007875
0x180007a2b  test    cs:byte_180030D04, 1
0x180007a32  jz      loc_180007974
0x180007a38  lea     rax, [rbp+150h+var_40]
0x180007a3f  mov     r9d, 1
0x180007a45  lea     rdx, ErrorNullPointer
0x180007a4c  mov     qword ptr [rsp+250h+var_230], rax
0x180007a51  call    McGenEventWrite_EventWriteTransfer
0x180007a56  jmp     loc_18000796D
0x180007a5b  lea     rdx, [rbp+150h+var_40]
0x180007a62  mov     qword ptr [rbp+150h+var_40.wYear], r11
0x180007a69  lea     rcx, xmmword_180030BE0
0x180007a70  mov     qword ptr [rbp+150h+var_40.wHour], r12
0x180007a77  call    ??$_Buynode@U?$pair@_KPEAU_EVENT_SUBSCRIPTION@@@std@@@?$_Tree_buy@U?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@std@@V?$allocator@U?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@std@@PEAX@1@$$QEAU?$pair@_KPEAU_EVENT_SUBSCRIPTION@@@1@@Z; std::_Tree_buy<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>>::_Buynode<std::pair<unsigned __int64,_EVENT_SUBSCRIPTION *>>(std::pair<unsigned __int64,_EVENT_SUBSCRIPTION *> &&)
  ... truncated ...
```
