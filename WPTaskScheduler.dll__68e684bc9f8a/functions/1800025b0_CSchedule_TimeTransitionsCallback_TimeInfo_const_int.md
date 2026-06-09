# CSchedule::TimeTransitionsCallback(TimeInfo const &,int *)

- ea: `0x1800025b0`
- end: `0x180002bfc`
- name: `?TimeTransitionsCallback@CSchedule@@QEAAJAEBVTimeInfo@@PEAH@Z`
- size: `1612`
- prototype: `__int64 __fastcall(CSchedule *__hidden this, const struct TimeInfo *, int *)`
- caller_count: `3`
- callee_count: `14`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x180002150`
- `0x180003fa0`
- `0x180005440`

## callees

- `0x180001cd0`
- `0x1800025b0`
- `0x180004b30`
- `0x180005c30`
- `0x18000e634`
- `0x18000ea40`
- `0x18000f760`
- `0x180017370`
- `0x180018560`
- `0x18001f65c`
- `0x18001f87c`
- `0x18001fadc`
- `0x180020c30`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180002783`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180002783`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800027e2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002981`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800027e2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002981`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000279e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000279e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180002881`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180002914`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180002881`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180002914`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000272b`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000272b`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x180002853`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x180002853`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x1800028ea`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x1800028ea`

## pseudocode

```c
__int64 __fastcall CSchedule::TimeTransitionsCallback(CSchedule *this, const struct TimeInfo *a2, int *a3)
{
  bool v3; // zf
  unsigned int v5; // r11d
  unsigned int v7; // r14d
  __int128 v9; // xmm0
  int v10; // eax
  __int64 v11; // rcx
  struct _SYSTEMTIME v12; // xmm0
  __int64 v13; // xmm6_8
  struct _TP_TIMER *v14; // rcx
  __int64 result; // rax
  struct _TP_TIMER *v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  DWORD v19; // eax
  SYSTEMTIME v20; // xmm0
  __int64 v21; // rcx
  unsigned int v22; // r10d
  void (__fastcall ***v23)(_QWORD, __int128 *); // rcx
  SYSTEMTIME v24; // [rsp+30h] [rbp-D0h] BYREF
  FILETIME v25; // [rsp+40h] [rbp-C0h]
  FILETIME v26; // [rsp+48h] [rbp-B8h]
  int v27; // [rsp+50h] [rbp-B0h]
  int v28; // [rsp+54h] [rbp-ACh]
  int v29; // [rsp+58h] [rbp-A8h]
  struct _FILETIME pftDueTime; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v31; // [rsp+68h] [rbp-98h] BYREF
  __int64 v32; // [rsp+78h] [rbp-88h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  int v34; // [rsp+88h] [rbp-78h]
  int v35; // [rsp+8Ch] [rbp-74h]
  int v36; // [rsp+90h] [rbp-70h]
  struct _SYSTEMTIME SystemTime; // [rsp+98h] [rbp-68h] BYREF
  FILETIME FileTime; // [rsp+A8h] [rbp-58h] BYREF
  FILETIME v39; // [rsp+B0h] [rbp-50h]
  int v40; // [rsp+B8h] [rbp-48h]
  int v41; // [rsp+BCh] [rbp-44h]
  int v42; // [rsp+C0h] [rbp-40h]
  struct _SYSTEMTIME UniversalTime; // [rsp+C8h] [rbp-38h] BYREF
  struct _TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+E0h] [rbp-20h] BYREF
  DWORD v45; // [rsp+18Ch] [rbp+8Ch]
  SYSTEMTIME v46; // [rsp+190h] [rbp+90h] BYREF
  struct _FILETIME v47; // [rsp+1A0h] [rbp+A0h] BYREF
  struct _FILETIME v48; // [rsp+1A8h] [rbp+A8h]
  __int64 v49; // [rsp+1B0h] [rbp+B0h]
  int v50; // [rsp+1B8h] [rbp+B8h]
  SYSTEMTIME v51; // [rsp+1C0h] [rbp+C0h] BYREF
  struct _FILETIME v52; // [rsp+1D0h] [rbp+D0h] BYREF
  struct _FILETIME v53; // [rsp+1D8h] [rbp+D8h]
  __int64 v54; // [rsp+1E0h] [rbp+E0h]
  int v55; // [rsp+1E8h] [rbp+E8h]
  SYSTEMTIME LocalTime; // [rsp+1F0h] [rbp+F0h] BYREF

  v3 = (*((_BYTE *)this + 44) & 8) == 0;
  v5 = *((_DWORD *)this + 10);
  v7 = v5;
  v36 = 1;
  if ( v3 )
  {
    v9 = *((_OWORD *)a2 + 11);
    v32 = *((_QWORD *)a2 + 24);
    v33 = *((_QWORD *)a2 + 25);
    v34 = *((_DWORD *)a2 + 52);
    v10 = *((_DWORD *)a2 + 53);
  }
  else
  {
    v9 = *((_OWORD *)a2 + 14);
    v32 = *((_QWORD *)a2 + 30);
    v33 = *((_QWORD *)a2 + 31);
    v34 = *((_DWORD *)a2 + 64);
    v10 = *((_DWORD *)a2 + 65);
  }
  v35 = v10;
  v31 = v9;
  switch ( v5 )
  {
    case 2u:
      if ( !*((_DWORD *)this + 22) || !(unsigned int)operator<(&v31, (char *)this + 48) )
      {
LABEL_6:
        if ( *((_DWORD *)this + 34) && !(unsigned int)operator<(&v31, (char *)this + 96) )
        {
          v7 = 5;
          break;
        }
LABEL_7:
        v7 = 4;
      }
      break;
    case 3u:
      if ( *((_DWORD *)this + 22) && (unsigned int)operator<(&v31, (char *)this + 48) )
      {
        v7 = 2;
        break;
      }
      goto LABEL_6;
    case 4u:
      if ( *((_DWORD *)this + 22) && (unsigned int)operator<(&v31, (char *)this + 48) )
      {
        v7 = 2;
      }
      else if ( *((_DWORD *)this + 34) && !(unsigned int)operator<(&v31, (char *)this + 96) )
      {
        v7 = 5;
      }
      break;
    case 5u:
      if ( *((_DWORD *)this + 22) && (unsigned int)operator<(&v31, (char *)this + 48) )
      {
        v7 = 2;
      }
      else if ( !*((_DWORD *)this + 34) || (unsigned int)operator<(&v31, (char *)this + 96) )
      {
        goto LABEL_7;
      }
      break;
    default:
      return 2147500037LL;
  }
  v11 = 0;
  if ( a3 )
    *a3 = v7 != v5;
  if ( v7 == v5 )
    return 0;
  if ( byte_180030D06 < 0 )
    McTemplateU0jqq_EventWriteTransfer(
      0,
      (unsigned int)ScheduleStateChange,
      (_DWORD)this + 16,
      *((_DWORD *)this + 10),
      v7);
  if ( *((_QWORD *)this + 25) && *((_QWORD *)this + 27) )
  {
    switch ( v7 )
    {
      case 2u:
        v20 = (SYSTEMTIME)*((_OWORD *)this + 3);
        v25 = (FILETIME)*((_QWORD *)this + 8);
        v26 = (FILETIME)*((_QWORD *)this + 9);
        v27 = *((_DWORD *)this + 20);
        v28 = *((_DWORD *)this + 21);
        v24 = v20;
        v29 = 1;
        CSchedule::SetNextTransitionTimer((__int64)this, (__int64 *)&v24);
        break;
      case 4u:
        v12 = (struct _SYSTEMTIME)*((_OWORD *)this + 6);
        v40 = *((_DWORD *)this + 32);
        v41 = *((_DWORD *)this + 33);
        v39 = (FILETIME)(*((_QWORD *)this + 15) + 7500000LL);
        FileTime = v39;
        SystemTime = v12;
        v42 = 1;
        FileTimeToSystemTime(&FileTime, &SystemTime);
        v13 = *(_QWORD *)&SystemTime.wYear;
        v14 = (struct _TP_TIMER *)*((_QWORD *)this + 37);
        v25 = FileTime;
        v26 = v39;
        v27 = v40;
        v28 = v41;
        v29 = 1;
        v24 = SystemTime;
        if ( v14 )
          SetThreadpoolTimer(v14, 0, 0, 0);
        else
          *((_QWORD *)this + 37) = CreateThreadpoolTimer(
                                     CScheduleMgr::BaseTimeTransitionsCallback,
                                     this,
                                     &ThreadpoolCallBackEnvironment);
        if ( *((_QWORD *)this + 37) )
        {
          TimeInfo::TimeInfo(&TimeZoneInformation);
          if ( (*((_BYTE *)this + 44) & 8) != 0 )
          {
            TimeInfo::SetUTC(&TimeZoneInformation, &v24);
          }
          else
          {
            v19 = GetTimeZoneInformation(&TimeZoneInformation);
            *(_QWORD *)&v46.wYear = v13;
            v45 = v19;
            *(_QWORD *)&v46.wHour = *(_QWORD *)&v24.wHour;
            if ( SystemTimeToFileTime(&v46, &v47) )
            {
              v48 = v47;
              v49 = 0;
              v50 = 1;
            }
            LocalTime = v46;
            UniversalTime = 0;
            TzSpecificLocalTimeToSystemTime(&TimeZoneInformation, &LocalTime, &UniversalTime);
            v51 = UniversalTime;
            if ( SystemTimeToFileTime(&v51, &v52) )
            {
              v53 = v52;
              v54 = 0;
              v55 = 1;
            }
          }
          v16 = (struct _TP_TIMER *)*((_QWORD *)this + 37);
          pftDueTime = v52;
          SetThreadpoolTimer(v16, &pftDueTime, 0, 0);
        }
        else
        {
          GetLastError();
        }
        break;
      case 5u:
        break;
      default:
        return 2147500037LL;
    }
    result = (*(__int64 (__fastcall **)(_QWORD, const struct TimeInfo *, _QWORD, _QWORD))(**((_QWORD **)this + 25)
                                                                                        + 112LL))(
               *((_QWORD *)this + 25),
               a2,
               v7,
               *((unsigned int *)this + 10));
    *((_DWORD *)this + 10) = v7;
    if ( (_DWORD)result == 47120640 )
    {
      if ( (unsigned int)operator==((char *)this + 48, (char *)this + 96, v17, v18) || v7 == 4 )
      {
        if ( (byte_180030D09 & 8) != 0 )
          McTemplateU0j_EventWriteTransfer(v21, TriggeredInTransitionHandler, (char *)this + 16);
        v23 = (void (__fastcall ***)(_QWORD, __int128 *))*((_QWORD *)this + 27);
        ++*((_DWORD *)this + 36);
        (**v23)(v23, &v31);
        (*(void (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)this + 25) + 72LL))(*((_QWORD *)this + 25), &v31);
        (*(void (__fastcall **)(_QWORD, __int128 *, __int64, _QWORD))(**((_QWORD **)this + 25) + 96LL))(
          *((_QWORD *)this + 25),
          &v31,
          1,
          0);
        if ( (*((_BYTE *)this + 44) & 1) != 0 )
        {
          TaskStore::PersistStatistics((CScheduleMgr **)qword_180030AC8, (struct _GUID *)this + 1);
          TaskStore::PersistRuntimeData((CScheduleMgr **)qword_180030AC8, (struct _GUID *)this + 1, 0);
        }
        if ( !*((_DWORD *)this + 66) )
          CSchedule::UpdateState(this, a2);
        return 0;
      }
      else
      {
        return v22;
      }
    }
    return result;
  }
  if ( (byte_180030D04 & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v11, ErrorNullPointer, a3, 1, &LocalTime);
  return 2147500035LL;
}

```

## disassembly

```asm
0x1800025b0  push    rbp
0x1800025b2  push    rbx
0x1800025b3  push    rsi
0x1800025b4  push    rdi
0x1800025b5  push    r14
0x1800025b7  lea     rbp, [rsp-120h]
0x1800025bf  sub     rsp, 220h
0x1800025c6  mov     rax, cs:__security_cookie
0x1800025cd  xor     rax, rsp
0x1800025d0  mov     [rbp+140h+var_40], rax
0x1800025d7  test    byte ptr [rcx+2Ch], 8
0x1800025db  mov     rdi, r8
0x1800025de  mov     r11d, [rcx+28h]
0x1800025e2  mov     rsi, rdx
0x1800025e5  mov     r14d, r11d
0x1800025e8  mov     [rbp+140h+var_1B0], 1
0x1800025ef  mov     rbx, rcx
0x1800025f2  jnz     loc_18000298C
0x1800025f8  mov     rax, [rdx+0C0h]
0x1800025ff  movups  xmm0, xmmword ptr [rdx+0B0h]
0x180002606  mov     [rsp+240h+var_1C8], rax
0x18000260b  mov     rax, [rdx+0C8h]
0x180002612  mov     [rbp+140h+var_1C0], rax
0x180002616  mov     eax, [rdx+0D0h]
0x18000261c  mov     [rbp+140h+var_1B8], eax
0x18000261f  mov     eax, [rdx+0D4h]
0x180002625  mov     [rbp+140h+var_1B4], eax
0x180002628  movups  [rsp+240h+var_1D8], xmm0
0x18000262d  cmp     r11d, 2
0x180002631  jz      loc_180002954
0x180002637  cmp     r11d, 3
0x18000263b  jnz     short loc_180002661
0x18000263d  cmp     dword ptr [rcx+58h], 0
0x180002641  lea     rdx, [rcx+30h]
0x180002645  jnz     loc_1800029DB
0x18000264b  lea     rdx, [rbx+60h]
0x18000264f  cmp     dword ptr [rdx+28h], 0
0x180002653  jnz     loc_1800029BE
0x180002659  mov     r14d, 4
0x18000265f  jmp     short loc_180002687
0x180002661  cmp     r11d, 4
0x180002665  jnz     loc_180002A32
0x18000266b  cmp     dword ptr [rcx+58h], 0
0x18000266f  lea     rdx, [rcx+30h]
0x180002673  jnz     loc_1800029F8
0x180002679  lea     rdx, [rbx+60h]
0x18000267d  cmp     dword ptr [rdx+28h], 0
0x180002681  jnz     loc_180002A15
0x180002687  xor     eax, eax
0x180002689  xor     ecx, ecx
0x18000268b  cmp     r14d, r11d
0x18000268e  setnz   al
0x180002691  test    rdi, rdi
0x180002694  jnz     loc_180002A84
0x18000269a  cmp     r14d, r11d
0x18000269d  jz      loc_180002BF5
0x1800026a3  cmp     cs:byte_180030D06, cl
0x1800026a9  jl      loc_180002A8B
0x1800026af  cmp     qword ptr [rbx+0C8h], 0
0x1800026b7  jz      loc_1800027A6
0x1800026bd  cmp     qword ptr [rbx+0D8h], 0
0x1800026c5  jz      loc_1800027A6
0x1800026cb  cmp     r14d, 2
0x1800026cf  jz      loc_180002AA9
0x1800026d5  cmp     r14d, 4
0x1800026d9  jnz     loc_180002AEC
0x1800026df  mov     eax, [rbx+80h]
0x1800026e5  lea     rdx, [rbp+140h+SystemTime]; lpSystemTime
0x1800026e9  movups  xmm0, xmmword ptr [rbx+60h]
0x1800026ed  mov     [rbp+140h+var_188], eax
0x1800026f0  lea     rcx, [rbp+140h+FileTime]; lpFileTime
0x1800026f4  mov     eax, [rbx+84h]
0x1800026fa  mov     [rbp+140h+var_184], eax
0x1800026fd  mov     rax, [rbx+78h]
0x180002701  add     rax, 7270E0h
0x180002707  movaps  [rsp+240h+var_30], xmm6
0x18000270f  mov     [rbp+140h+var_190], rax
0x180002713  shr     rax, 20h
0x180002717  mov     [rbp+140h+FileTime.dwHighDateTime], eax
0x18000271a  mov     eax, dword ptr [rbp+140h+var_190]
0x18000271d  mov     [rbp+140h+FileTime.dwLowDateTime], eax
0x180002720  movups  xmmword ptr [rbp+140h+SystemTime.wYear], xmm0
0x180002724  mov     [rbp+140h+var_180], 1
0x18000272b  call    cs:__imp_FileTimeToSystemTime
0x180002731  mov     rax, qword ptr [rbp+140h+FileTime.dwLowDateTime]
0x180002735  movups  xmm6, xmmword ptr [rbp+140h+SystemTime.wYear]
0x180002739  mov     rcx, [rbx+128h]; pti
0x180002740  mov     [rsp+240h+var_200], rax
0x180002745  mov     rax, [rbp+140h+var_190]
0x180002749  mov     [rsp+240h+var_1F8], rax
0x18000274e  mov     eax, [rbp+140h+var_188]
0x180002751  mov     [rsp+240h+var_1F0], eax
0x180002755  mov     eax, [rbp+140h+var_184]
0x180002758  mov     [rsp+240h+var_1EC], eax
0x18000275c  mov     [rsp+240h+var_1E8], 1
0x180002764  movups  [rsp+240h+var_210], xmm6
0x180002769  test    rcx, rcx
0x18000276c  jnz     loc_180002979
0x180002772  lea     r8, ?ThreadpoolCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x180002779  mov     rdx, rbx; pv
0x18000277c  lea     rcx, ?BaseTimeTransitionsCallback@CScheduleMgr@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180002783  call    cs:__imp_CreateThreadpoolTimer
0x180002789  mov     [rbx+128h], rax
0x180002790  cmp     qword ptr [rbx+128h], 0
0x180002798  jnz     loc_18000283C
0x18000279e  call    cs:__imp_GetLastError
0x1800027a4  jmp     short loc_1800027E8
0x1800027a6  test    cs:byte_180030D04, 1
0x1800027ad  jnz     loc_180002BD2
0x1800027b3  mov     eax, 80004003h
0x1800027b8  jmp     short loc_18000281F
0x1800027ba  lea     rdx, [rsp+240h+var_210]; struct TimeValue *
0x1800027bf  call    ?SetUTC@TimeInfo@@QEAAXAEBVTimeValue@@@Z; TimeInfo::SetUTC(TimeValue const &)
0x1800027c4  mov     rax, qword ptr [rbp+140h+var_70.dwLowDateTime]
0x1800027cb  lea     rdx, [rsp+240h+pftDueTime]; pftDueTime
0x1800027d0  mov     rcx, [rbx+128h]; pti
0x1800027d7  xor     r9d, r9d; msWindowLength
0x1800027da  xor     r8d, r8d; msPeriod
0x1800027dd  mov     qword ptr [rsp+240h+pftDueTime.dwLowDateTime], rax
0x1800027e2  call    cs:__imp_SetThreadpoolTimer
0x1800027e8  movaps  xmm6, [rsp+240h+var_30]
0x1800027f0  mov     rcx, [rbx+0C8h]
0x1800027f7  mov     r8d, r14d
0x1800027fa  mov     r9d, [rbx+28h]
0x1800027fe  mov     rdx, rsi
0x180002801  mov     rax, [rcx]
0x180002804  mov     rax, [rax+70h]
0x180002808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000280d  mov     [rbx+28h], r14d
0x180002811  mov     r10d, eax
0x180002814  cmp     eax, 2CF0100h
0x180002819  jz      loc_180002B00
0x18000281f  mov     rcx, [rbp+140h+var_40]
0x180002826  xor     rcx, rsp; StackCookie
0x180002829  call    __security_check_cookie
0x18000282e  add     rsp, 220h
0x180002835  pop     r14
0x180002837  pop     rdi
0x180002838  pop     rsi
0x180002839  pop     rbx
0x18000283a  pop     rbp
0x18000283b  retn
0x18000283c  lea     rcx, [rbp+140h+TimeZoneInformation]; lpTimeZoneInformation
0x180002840  call    ??0TimeInfo@@QEAA@XZ; TimeInfo::TimeInfo(void)
0x180002845  test    byte ptr [rbx+2Ch], 8
0x180002849  lea     rcx, [rbp+140h+TimeZoneInformation]; lpTimeZoneInformation
0x18000284d  jnz     loc_1800027BA
0x180002853  call    cs:__imp_GetTimeZoneInformation
0x180002859  lea     rdx, [rbp+140h+var_A0]; lpFileTime
0x180002860  movsd   qword ptr [rbp+140h+var_B0.wYear], xmm6
0x180002868  mov     [rbp+140h+var_B4], eax
0x18000286e  lea     rcx, [rbp+140h+var_B0]; lpSystemTime
0x180002875  mov     rax, qword ptr [rsp+240h+var_210+8]
0x18000287a  mov     qword ptr [rbp+140h+var_B0.wHour], rax
0x180002881  call    cs:__imp_SystemTimeToFileTime
0x180002887  test    eax, eax
0x180002889  jz      short loc_1800028B8
0x18000288b  mov     eax, [rbp+140h+var_A0.dwHighDateTime]
0x180002891  mov     dword ptr [rbp+140h+var_98+4], eax
0x180002897  mov     eax, [rbp+140h+var_A0.dwLowDateTime]
0x18000289d  mov     dword ptr [rbp+140h+var_98], eax
0x1800028a3  mov     [rbp+140h+var_90], 0
0x1800028ae  mov     [rbp+140h+var_88], 1
0x1800028b8  mov     rax, qword ptr [rbp+140h+var_B0.wYear]
0x1800028bf  lea     r8, [rbp+140h+UniversalTime]; lpUniversalTime
0x1800028c3  mov     qword ptr [rbp+140h+LocalTime.wYear], rax
0x1800028ca  lea     rdx, [rbp+140h+LocalTime]; lpLocalTime
0x1800028d1  mov     rax, qword ptr [rbp+140h+var_B0.wHour]
0x1800028d8  lea     rcx, [rbp+140h+TimeZoneInformation]; lpTimeZoneInformation
0x1800028dc  xorps   xmm0, xmm0
0x1800028df  mov     qword ptr [rbp+140h+LocalTime.wHour], rax
0x1800028e6  movups  xmmword ptr [rbp+140h+UniversalTime.wYear], xmm0
0x1800028ea  call    cs:__imp_TzSpecificLocalTimeToSystemTime
0x1800028f0  mov     rax, qword ptr [rbp+140h+UniversalTime.wYear]
0x1800028f4  lea     rdx, [rbp+140h+var_70]; lpFileTime
0x1800028fb  mov     qword ptr [rbp+140h+var_80.wYear], rax
0x180002902  lea     rcx, [rbp+140h+var_80]; lpSystemTime
0x180002909  mov     rax, qword ptr [rbp+140h+UniversalTime.wHour]
0x18000290d  mov     qword ptr [rbp+140h+var_80.wHour], rax
0x180002914  call    cs:__imp_SystemTimeToFileTime
0x18000291a  test    eax, eax
0x18000291c  jz      loc_1800027C4
0x180002922  mov     eax, [rbp+140h+var_70.dwHighDateTime]
0x180002928  mov     dword ptr [rbp+140h+var_68+4], eax
0x18000292e  mov     eax, [rbp+140h+var_70.dwLowDateTime]
0x180002934  mov     dword ptr [rbp+140h+var_68], eax
0x18000293a  mov     [rbp+140h+var_60], 0
0x180002945  mov     [rbp+140h+var_58], 1
0x18000294f  jmp     loc_1800027C4
0x180002954  cmp     dword ptr [rcx+58h], 0
0x180002958  lea     rdx, [rcx+30h]
0x18000295c  jz      loc_18000264B
0x180002962  lea     rcx, [rsp+240h+var_1D8]
0x180002967  call    ??M@YAHAEBVTimeValue@@0@Z; operator<(TimeValue const &,TimeValue const &)
0x18000296c  test    eax, eax
0x18000296e  jnz     loc_180002687
0x180002974  jmp     loc_18000264B
0x180002979  xor     r9d, r9d; msWindowLength
0x18000297c  xor     r8d, r8d; msPeriod
0x18000297f  xor     edx, edx; pftDueTime
0x180002981  call    cs:__imp_SetThreadpoolTimer
0x180002987  jmp     loc_180002790
0x18000298c  mov     rax, [rdx+0F0h]
0x180002993  movups  xmm0, xmmword ptr [rdx+0E0h]
0x18000299a  mov     [rsp+240h+var_1C8], rax
0x18000299f  mov     rax, [rdx+0F8h]
0x1800029a6  mov     [rbp+140h+var_1C0], rax
0x1800029aa  mov     eax, [rdx+100h]
0x1800029b0  mov     [rbp+140h+var_1B8], eax
0x1800029b3  mov     eax, [rdx+104h]
0x1800029b9  jmp     loc_180002625
0x1800029be  lea     rcx, [rsp+240h+var_1D8]
0x1800029c3  call    ??M@YAHAEBVTimeValue@@0@Z; operator<(TimeValue const &,TimeValue const &)
0x1800029c8  test    eax, eax
0x1800029ca  jnz     loc_180002659
0x1800029d0  mov     r14d, 5
0x1800029d6  jmp     loc_180002687
0x1800029db  lea     rcx, [rsp+240h+var_1D8]
0x1800029e0  call    ??M@YAHAEBVTimeValue@@0@Z; operator<(TimeValue const &,TimeValue const &)
0x1800029e5  test    eax, eax
0x1800029e7  jz      loc_18000264B
0x1800029ed  mov     r14d, 2
0x1800029f3  jmp     loc_180002687
0x1800029f8  lea     rcx, [rsp+240h+var_1D8]
0x1800029fd  call    ??M@YAHAEBVTimeValue@@0@Z; operator<(TimeValue const &,TimeValue const &)
0x180002a02  test    eax, eax
0x180002a04  jz      loc_180002679
0x180002a0a  mov     r14d, 2
0x180002a10  jmp     loc_180002687
0x180002a15  lea     rcx, [rsp+240h+var_1D8]
0x180002a1a  call    ??M@YAHAEBVTimeValue@@0@Z; operator<(TimeValue const &,TimeValue const &)
0x180002a1f  test    eax, eax
0x180002a21  jnz     loc_180002687
0x180002a27  mov     r14d, 5
0x180002a2d  jmp     loc_180002687
0x180002a32  cmp     r11d, 5
0x180002a36  jnz     loc_180002AF6
0x180002a3c  cmp     dword ptr [rcx+58h], 0
0x180002a40  lea     rdx, [rcx+30h]
0x180002a44  jz      short loc_180002A5F
0x180002a46  lea     rcx, [rsp+240h+var_1D8]
0x180002a4b  call    ??M@YAHAEBVTimeValue@@0@Z; operator<(TimeValue const &,TimeValue const &)
0x180002a50  test    eax, eax
0x180002a52  jz      short loc_180002A5F
0x180002a54  mov     r14d, 2
0x180002a5a  jmp     loc_180002687
0x180002a5f  lea     rdx, [rbx+60h]
0x180002a63  cmp     dword ptr [rdx+28h], 0
0x180002a67  jz      loc_180002659
0x180002a6d  lea     rcx, [rsp+240h+var_1D8]
0x180002a72  call    ??M@YAHAEBVTimeValue@@0@Z; operator<(TimeValue const &,TimeValue const &)
0x180002a77  test    eax, eax
0x180002a79  jz      loc_180002687
0x180002a7f  jmp     loc_180002659
0x180002a84  mov     [rdi], eax
0x180002a86  jmp     loc_18000269A
0x180002a8b  mov     r9d, [rbx+28h]
0x180002a8f  lea     r8, [rbx+10h]
0x180002a93  lea     rdx, ScheduleStateChange
0x180002a9a  mov     dword ptr [rsp+240h+var_220], r14d
0x180002a9f  call    McTemplateU0jqq_EventWriteTransfer
0x180002aa4  jmp     loc_1800026AF
0x180002aa9  mov     rax, [rbx+40h]
0x180002aad  lea     rdx, [rsp+240h+var_210]
0x180002ab2  movups  xmm0, xmmword ptr [rbx+30h]
0x180002ab6  mov     [rsp+240h+var_200], rax
0x180002abb  mov     rcx, rbx
0x180002abe  mov     rax, [rbx+48h]
0x180002ac2  mov     [rsp+240h+var_1F8], rax
0x180002ac7  mov     eax, [rbx+50h]
0x180002aca  mov     [rsp+240h+var_1F0], eax
0x180002ace  mov     eax, [rbx+54h]
0x180002ad1  mov     [rsp+240h+var_1EC], eax
0x180002ad5  movups  [rsp+240h+var_210], xmm0
0x180002ada  mov     [rsp+240h+var_1E8], 1
0x180002ae2  call    ?SetNextTransitionTimer@CSchedule@@AEAAJVTimeValue@@@Z; CSchedule::SetNextTransitionTimer(TimeValue)
0x180002ae7  jmp     loc_1800027F0
0x180002aec  cmp     r14d, 5
0x180002af0  jz      loc_1800027F0
0x180002af6  mov     eax, 80004005h
0x180002afb  jmp     loc_18000281F
0x180002b00  lea     rdx, [rbx+60h]
0x180002b04  lea     rcx, [rbx+30h]
0x180002b08  call    ??8@YAHAEBVTimeValue@@0@Z; operator==(TimeValue const &,TimeValue const &)
0x180002b0d  test    eax, eax
0x180002b0f  jnz     short loc_180002B1F
0x180002b11  cmp     r14d, 4
0x180002b15  jz      short loc_180002B1F
0x180002b17  mov     eax, r10d
0x180002b1a  jmp     loc_18000281F
0x180002b1f  test    cs:byte_180030D09, 8
0x180002b26  jz      short loc_180002B38
0x180002b28  lea     r8, [rbx+10h]
0x180002b2c  lea     rdx, TriggeredInTransitionHandler
0x180002b33  call    McTemplateU0j_EventWriteTransfer
0x180002b38  mov     rcx, [rbx+0D8h]
0x180002b3f  lea     rdx, [rsp+240h+var_1D8]
0x180002b44  inc     dword ptr [rbx+90h]
0x180002b4a  mov     rax, [rcx]
0x180002b4d  mov     rax, [rax]
  ... truncated ...
```
