# CScheduleMgr::TimeTransitionsCallback(CSchedule *)

- ea: `0x180002150`
- end: `0x18000259f`
- name: `?TimeTransitionsCallback@CScheduleMgr@@QEAAXPEAVCSchedule@@@Z`
- size: `1103`
- prototype: `void __fastcall(CScheduleMgr *this, struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180002140`

## callees

- `0x180002150`
- `0x1800025b0`
- `0x18000ea40`
- `0x18000f7cc`
- `0x18001fd14`
- `0x180020bf6`
- `0x180020c30`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180002594`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180002594`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800023a2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800023a2`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000258b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000258b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002196`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800021b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002379`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002196`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800021b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002379`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002203`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002336`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800023bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800023ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002203`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002336`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800023bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800023ca`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180002273`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800022be`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180002273`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800022be`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x1800022e3`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x1800022e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800022a7`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800022a7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18000225a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18000225a`

## pseudocode

```c
void __fastcall CScheduleMgr::TimeTransitionsCallback(CScheduleMgr *this, struct _GUID *a2)
{
  void **i; // rbx
  __int64 v4; // rcx
  __int64 v5; // r8
  DWORD v6; // eax
  _QWORD *v7; // rcx
  __int64 v8; // r8
  struct CSchedule *j; // rdx
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v11; // rbx
  struct _RTL_CRITICAL_SECTION *v12; // rcx
  _QWORD *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rax
  bool v16; // zf
  _QWORD *v17; // rax
  __int64 v18; // rcx
  struct CSchedule *v19; // rax
  _QWORD v20[2]; // [rsp+60h] [rbp-A0h] BYREF
  SYSTEMTIME Buf2; // [rsp+70h] [rbp-90h] BYREF
  _TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+80h] [rbp-80h] BYREF
  DWORD v23; // [rsp+12Ch] [rbp+2Ch]
  SYSTEMTIME v24; // [rsp+130h] [rbp+30h] BYREF
  struct _FILETIME v25; // [rsp+140h] [rbp+40h] BYREF
  struct _FILETIME v26; // [rsp+148h] [rbp+48h]
  __int64 v27; // [rsp+150h] [rbp+50h]
  int v28; // [rsp+158h] [rbp+58h]
  SYSTEMTIME SystemTime; // [rsp+160h] [rbp+60h] BYREF
  struct _FILETIME FileTime; // [rsp+170h] [rbp+70h] BYREF
  struct _FILETIME v31; // [rsp+178h] [rbp+78h]
  __int64 v32; // [rsp+180h] [rbp+80h]
  int v33; // [rsp+188h] [rbp+88h]
  SYSTEMTIME Buf1; // [rsp+190h] [rbp+90h] BYREF

  v20[1] = v20;
  v20[0] = v20;
  EnterCriticalSection(&CriticalSection);
  *(_QWORD *)&Buf1.wYear = a2;
  if ( !a2 )
  {
LABEL_24:
    v12 = &CriticalSection;
LABEL_22:
    LeaveCriticalSection(v12);
    return;
  }
  EnterCriticalSection(&CriticalSection);
  for ( i = (void **)g_ScheduleMgr; ; i = (void **)*i )
  {
    if ( i == (void **)&g_ScheduleMgr )
    {
      LeaveCriticalSection(&CriticalSection);
      goto LABEL_24;
    }
    *(_QWORD *)&Buf2.wYear = i;
    if ( !memcmp_0(&Buf1, &Buf2, 8u) )
      break;
  }
  LeaveCriticalSection(&CriticalSection);
  if ( (byte_180030D06 & 0x40) != 0 )
    McGenEventWrite_EventWriteTransfer(v4, TimeTransitionProcessingStart, v5, 1, &Buf1);
  v25 = 0;
  v27 = 0;
  v28 = 0;
  v24 = 0;
  v26 = 0;
  v32 = 0;
  v33 = 0;
  SystemTime = 0;
  FileTime = 0;
  v31 = 0;
  Buf1 = 0;
  GetSystemTime(&Buf1);
  SystemTime = Buf1;
  if ( SystemTimeToFileTime(&SystemTime, &FileTime) )
  {
    v31 = FileTime;
    v32 = 0;
    v33 = 1;
  }
  Buf2 = 0;
  GetLocalTime(&Buf2);
  v24 = Buf2;
  if ( SystemTimeToFileTime(&v24, &v25) )
  {
    v26 = v25;
    v27 = 0;
    v28 = 1;
  }
  v6 = GetTimeZoneInformation(&TimeZoneInformation);
  v23 = v6;
  if ( (byte_180030D02 & 1) != 0 )
  {
    McTemplateU0hhhhhhhqt_EventWriteTransfer(
      *(_DWORD *)&v24.wSecond,
      (unsigned int)TimeDateLocal,
      v24.wYear,
      *(_QWORD *)&v24.wYear >> 16,
      v24.wDay,
      v24.wHour,
      v24.wMinute,
      v24.wSecond,
      v24.wMilliseconds,
      v6,
      v6 == 2);
    if ( (byte_180030D02 & 1) != 0 )
      McTemplateU0hhhhhhhqt_EventWriteTransfer(
        *(_DWORD *)&SystemTime.wSecond,
        (unsigned int)TimeDateUTC,
        SystemTime.wYear,
        *(_QWORD *)&SystemTime.wYear >> 16,
        SystemTime.wDay,
        SystemTime.wHour,
        SystemTime.wMinute,
        SystemTime.wSecond,
        SystemTime.wMilliseconds,
        0,
        0);
  }
  CSchedule::TimeTransitionsCallback((CSchedule *)a2, (const struct TimeInfo *)&TimeZoneInformation, 0);
  if ( *(_DWORD *)a2[16].Data4 )
  {
    if ( (a2[2].Data4[4] & 4) != 0 )
    {
      v13 = *(_QWORD **)a2->Data4;
      v14 = *(_QWORD *)&a2->Data1;
      *v13 = *(_QWORD *)&a2->Data1;
      *(_QWORD *)(v14 + 8) = v13;
      v7 = v20;
      v15 = v20[0];
      *(_QWORD *)&a2->Data1 = v20[0];
      *(_QWORD *)a2->Data4 = v20;
      *(_QWORD *)(v15 + 8) = a2;
      v16 = (a2[2].Data4[4] & 1) == 0;
      v20[0] = a2;
      if ( !v16 )
        TaskStore::Delete((TaskStore *)v20, a2 + 1);
    }
  }
  if ( (byte_180030D06 & 0x40) != 0 )
    McGenEventWrite_EventWriteTransfer(v7, TimeTransitionProcessingCompleted, v8, 1, &Buf1);
  LeaveCriticalSection(&CriticalSection);
  if ( (_QWORD *)v20[0] != v20 )
  {
    EnterCriticalSection(&CScheduleMgr::CritLockExpired);
    for ( j = (struct CSchedule *)v20[0]; (_QWORD *)v20[0] != v20; j = (struct CSchedule *)v20[0] )
    {
      v17 = (_QWORD *)*((_QWORD *)j + 1);
      v18 = *(_QWORD *)j;
      *v17 = *(_QWORD *)j;
      *(_QWORD *)(v18 + 8) = v17;
      v19 = CScheduleMgr::ExpiredScheduleList;
      *(_QWORD *)j = CScheduleMgr::ExpiredScheduleList;
      *((_QWORD *)j + 1) = &CScheduleMgr::ExpiredScheduleList;
      *((_QWORD *)v19 + 1) = j;
      CScheduleMgr::ExpiredScheduleList = j;
    }
    ThreadpoolWork = CreateThreadpoolWork(
                       (PTP_WORK_CALLBACK)CScheduleMgr::DeleteExpiredWorker,
                       0,
                       &ThreadpoolCallBackEnvironment);
    v11 = ThreadpoolWork;
    if ( ThreadpoolWork )
    {
      SubmitThreadpoolWork(ThreadpoolWork);
      CloseThreadpoolWork(v11);
    }
    v12 = &CScheduleMgr::CritLockExpired;
    goto LABEL_22;
  }
}

```

## disassembly

```asm
0x180002150  mov     [rsp-8+arg_10], rbx
0x180002155  push    rbp
0x180002156  push    rsi
0x180002157  push    rdi
0x180002158  lea     rbp, [rsp-0B0h]
0x180002160  sub     rsp, 1B0h
0x180002167  mov     rax, cs:__security_cookie
0x18000216e  xor     rax, rsp
0x180002171  mov     [rbp+0C0h+var_20], rax
0x180002178  lea     rax, [rsp+1C0h+var_160]
0x18000217d  mov     rdi, rdx
0x180002180  mov     [rsp+1C0h+var_158], rax
0x180002185  lea     rcx, CriticalSection; lpCriticalSection
0x18000218c  lea     rax, [rsp+1C0h+var_160]
0x180002191  mov     [rsp+1C0h+var_160], rax
0x180002196  call    cs:__imp_EnterCriticalSection
0x18000219c  mov     qword ptr [rbp+0C0h+Buf1], rdi
0x1800021a3  test    rdi, rdi
0x1800021a6  jz      loc_1800023D0
0x1800021ac  lea     rcx, CriticalSection; lpCriticalSection
0x1800021b3  call    cs:__imp_EnterCriticalSection
0x1800021b9  mov     rbx, cs:?g_ScheduleMgr@@3VCScheduleMgr@@A; CScheduleMgr g_ScheduleMgr
0x1800021c0  lea     rsi, ?g_ScheduleMgr@@3VCScheduleMgr@@A; CScheduleMgr g_ScheduleMgr
0x1800021c7  cmp     rbx, rsi
0x1800021ca  jz      loc_1800023C3
0x1800021d0  mov     r8d, 8; Size
0x1800021d6  mov     qword ptr [rsp+1C0h+Buf2], rbx
0x1800021db  lea     rdx, [rsp+1C0h+Buf2]; Buf2
0x1800021e0  lea     rcx, [rbp+0C0h+Buf1]; Buf1
0x1800021e7  call    memcmp_0
0x1800021ec  test    eax, eax
0x1800021ee  jnz     loc_18000236A
0x1800021f4  lea     rcx, CriticalSection; lpCriticalSection
0x1800021fb  mov     [rsp+1C0h+arg_0], r14
0x180002203  call    cs:__imp_LeaveCriticalSection
0x180002209  test    cs:byte_180030D06, 40h
0x180002210  jnz     loc_1800023D9
0x180002216  xor     eax, eax
0x180002218  lea     rcx, [rbp+0C0h+Buf1]; lpSystemTime
0x18000221f  xor     r14d, r14d
0x180002222  mov     qword ptr [rbp+0C0h+var_80.dwLowDateTime], rax
0x180002226  xorps   xmm0, xmm0
0x180002229  mov     [rbp+0C0h+var_70], r14
0x18000222d  mov     [rbp+0C0h+var_68], r14d
0x180002231  movups  xmmword ptr [rbp+0C0h+var_90.wYear], xmm0
0x180002235  mov     [rbp+0C0h+var_78], rax
0x180002239  mov     [rbp+0C0h+var_40], r14
0x180002240  mov     [rbp+0C0h+var_38], r14d
0x180002247  movups  xmmword ptr [rbp+0C0h+SystemTime.wYear], xmm0
0x18000224b  mov     qword ptr [rbp+0C0h+FileTime.dwLowDateTime], rax
0x18000224f  mov     [rbp+0C0h+var_48], rax
0x180002253  movups  [rbp+0C0h+Buf1], xmm0
0x18000225a  call    cs:__imp_GetSystemTime
0x180002260  movups  xmm0, [rbp+0C0h+Buf1]
0x180002267  lea     rdx, [rbp+0C0h+FileTime]; lpFileTime
0x18000226b  lea     rcx, [rbp+0C0h+SystemTime]; lpSystemTime
0x18000226f  movaps  xmmword ptr [rbp+0C0h+SystemTime.wYear], xmm0
0x180002273  call    cs:__imp_SystemTimeToFileTime
0x180002279  test    eax, eax
0x18000227b  jz      short loc_18000229A
0x18000227d  mov     eax, [rbp+0C0h+FileTime.dwHighDateTime]
0x180002280  mov     dword ptr [rbp+0C0h+var_48+4], eax
0x180002283  mov     eax, [rbp+0C0h+FileTime.dwLowDateTime]
0x180002286  mov     dword ptr [rbp+0C0h+var_48], eax
0x180002289  mov     [rbp+0C0h+var_40], r14
0x180002290  mov     [rbp+0C0h+var_38], 1
0x18000229a  xorps   xmm0, xmm0
0x18000229d  lea     rcx, [rsp+1C0h+Buf2]; lpSystemTime
0x1800022a2  movups  [rsp+1C0h+Buf2], xmm0
0x1800022a7  call    cs:__imp_GetLocalTime
0x1800022ad  movups  xmm0, [rsp+1C0h+Buf2]
0x1800022b2  lea     rdx, [rbp+0C0h+var_80]; lpFileTime
0x1800022b6  lea     rcx, [rbp+0C0h+var_90]; lpSystemTime
0x1800022ba  movaps  xmmword ptr [rbp+0C0h+var_90.wYear], xmm0
0x1800022be  call    cs:__imp_SystemTimeToFileTime
0x1800022c4  test    eax, eax
0x1800022c6  jz      short loc_1800022DF
0x1800022c8  mov     eax, [rbp+0C0h+var_80.dwHighDateTime]
0x1800022cb  mov     dword ptr [rbp+0C0h+var_78+4], eax
0x1800022ce  mov     eax, [rbp+0C0h+var_80.dwLowDateTime]
0x1800022d1  mov     dword ptr [rbp+0C0h+var_78], eax
0x1800022d4  mov     [rbp+0C0h+var_70], r14
0x1800022d8  mov     [rbp+0C0h+var_68], 1
0x1800022df  lea     rcx, [rbp+0C0h+TimeZoneInformation]; lpTimeZoneInformation
0x1800022e3  call    cs:__imp_GetTimeZoneInformation
0x1800022e9  movzx   ecx, cs:byte_180030D02
0x1800022f0  mov     esi, eax
0x1800022f2  mov     [rbp+0C0h+var_94], eax
0x1800022f5  test    cl, 1
0x1800022f8  jnz     loc_1800023FC
0x1800022fe  xor     r8d, r8d; int *
0x180002301  lea     rdx, [rbp+0C0h+TimeZoneInformation]; struct TimeInfo *
0x180002305  mov     rcx, rdi; this
0x180002308  call    ?TimeTransitionsCallback@CSchedule@@QEAAJAEBVTimeInfo@@PEAH@Z; CSchedule::TimeTransitionsCallback(TimeInfo const &,int *)
0x18000230d  cmp     dword ptr [rdi+108h], 0
0x180002314  mov     r14, [rsp+1C0h+arg_0]
0x18000231c  jnz     loc_1800024D9
0x180002322  test    cs:byte_180030D06, 40h
0x180002329  jnz     loc_180002523
0x18000232f  lea     rcx, CriticalSection; lpCriticalSection
0x180002336  call    cs:__imp_LeaveCriticalSection
0x18000233c  lea     rax, [rsp+1C0h+var_160]
0x180002341  cmp     [rsp+1C0h+var_160], rax
0x180002346  jnz     short loc_180002372
0x180002348  mov     rcx, [rbp+0C0h+var_20]
0x18000234f  xor     rcx, rsp; StackCookie
0x180002352  call    __security_check_cookie
0x180002357  mov     rbx, [rsp+1C0h+arg_10]
0x18000235f  add     rsp, 1B0h
0x180002366  pop     rdi
0x180002367  pop     rsi
0x180002368  pop     rbp
0x180002369  retn
0x18000236a  mov     rbx, [rbx]
0x18000236d  jmp     loc_1800021C7
0x180002372  lea     rcx, ?CritLockExpired@CScheduleMgr@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002379  call    cs:__imp_EnterCriticalSection
0x18000237f  mov     rdx, [rsp+1C0h+var_160]
0x180002384  lea     rax, [rsp+1C0h+var_160]
0x180002389  cmp     rdx, rax
0x18000238c  jnz     loc_180002546
0x180002392  lea     r8, ?ThreadpoolCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x180002399  xor     edx, edx; pv
0x18000239b  lea     rcx, ?DeleteExpiredWorker@CScheduleMgr@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800023a2  call    cs:__imp_CreateThreadpoolWork
0x1800023a8  mov     rbx, rax
0x1800023ab  test    rax, rax
0x1800023ae  jnz     loc_180002588
0x1800023b4  lea     rcx, ?CritLockExpired@CScheduleMgr@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800023bb  call    cs:__imp_LeaveCriticalSection
0x1800023c1  jmp     short loc_180002348
0x1800023c3  lea     rcx, CriticalSection; lpCriticalSection
0x1800023ca  call    cs:__imp_LeaveCriticalSection
0x1800023d0  lea     rcx, CriticalSection
0x1800023d7  jmp     short loc_1800023BB
0x1800023d9  lea     rax, [rbp+0C0h+Buf1]
0x1800023e0  mov     r9d, 1
0x1800023e6  lea     rdx, TimeTransitionProcessingStart
0x1800023ed  mov     [rsp+1C0h+var_1A0], rax
0x1800023f2  call    McGenEventWrite_EventWriteTransfer
0x1800023f7  jmp     loc_180002216
0x1800023fc  mov     rbx, qword ptr [rbp+0C0h+var_90.wHour]
0x180002400  mov     r10d, r14d
0x180002403  mov     r11, qword ptr [rbp+0C0h+var_90.wYear]
0x180002407  cmp     esi, 2
0x18000240a  mov     rdx, r11
0x18000240d  mov     r9, r11
0x180002410  setz    r10b
0x180002414  mov     r8, rbx
0x180002417  mov     [rsp+1C0h+var_170], r10d
0x18000241c  mov     rcx, rbx
0x18000241f  mov     [rsp+1C0h+var_178], esi
0x180002423  mov     rax, rbx
0x180002426  shr     r8, 30h
0x18000242a  mov     [rsp+1C0h+var_180], r8w
0x180002430  movzx   r8d, r11w
0x180002434  shr     rdx, 30h
0x180002438  shr     rcx, 20h
0x18000243c  mov     [rsp+1C0h+var_188], cx
0x180002441  shr     rax, 10h
0x180002445  mov     [rsp+1C0h+var_190], ax
0x18000244a  mov     [rsp+1C0h+var_198], bx
0x18000244f  mov     word ptr [rsp+1C0h+var_1A0], dx
0x180002454  lea     rdx, TimeDateLocal
0x18000245b  shr     r9, 10h
0x18000245f  call    McTemplateU0hhhhhhhqt_EventWriteTransfer
0x180002464  movzx   ecx, cs:byte_180030D02
0x18000246b  test    cl, 1
0x18000246e  jz      loc_1800022FE
0x180002474  mov     r11, qword ptr [rbp+0C0h+SystemTime.wHour]
0x180002478  mov     r10, qword ptr [rbp+0C0h+SystemTime.wYear]
0x18000247c  mov     r8, r11
0x18000247f  mov     [rsp+1C0h+var_170], r14d
0x180002484  mov     rcx, r11
0x180002487  mov     [rsp+1C0h+var_178], r14d
0x18000248c  mov     rax, r11
0x18000248f  shr     r8, 30h
0x180002493  mov     rdx, r10
0x180002496  mov     [rsp+1C0h+var_180], r8w
0x18000249c  mov     r9, r10
0x18000249f  shr     rdx, 30h
0x1800024a3  movzx   r8d, r10w
0x1800024a7  shr     rcx, 20h
0x1800024ab  mov     [rsp+1C0h+var_188], cx
0x1800024b0  shr     rax, 10h
0x1800024b4  mov     [rsp+1C0h+var_190], ax
0x1800024b9  mov     [rsp+1C0h+var_198], r11w
0x1800024bf  mov     word ptr [rsp+1C0h+var_1A0], dx
0x1800024c4  lea     rdx, TimeDateUTC
0x1800024cb  shr     r9, 10h
0x1800024cf  call    McTemplateU0hhhhhhhqt_EventWriteTransfer
0x1800024d4  jmp     loc_1800022FE
0x1800024d9  test    byte ptr [rdi+2Ch], 4
0x1800024dd  jz      loc_180002322
0x1800024e3  mov     rax, [rdi+8]
0x1800024e7  mov     rcx, [rdi]
0x1800024ea  mov     [rax], rcx
0x1800024ed  mov     [rcx+8], rax
0x1800024f1  lea     rcx, [rsp+1C0h+var_160]; this
0x1800024f6  mov     rax, [rsp+1C0h+var_160]
0x1800024fb  mov     [rdi], rax
0x1800024fe  mov     [rdi+8], rcx
0x180002502  mov     [rax+8], rdi
0x180002506  test    byte ptr [rdi+2Ch], 1
0x18000250a  mov     [rsp+1C0h+var_160], rdi
0x18000250f  jz      loc_180002322
0x180002515  lea     rdx, [rdi+10h]; struct _GUID *
0x180002519  call    ?Delete@TaskStore@@QEAAJAEBU_GUID@@@Z; TaskStore::Delete(_GUID const &)
0x18000251e  jmp     loc_180002322
0x180002523  lea     rax, [rbp+0C0h+Buf1]
0x18000252a  mov     r9d, 1
0x180002530  lea     rdx, TimeTransitionProcessingCompleted
0x180002537  mov     [rsp+1C0h+var_1A0], rax
0x18000253c  call    McGenEventWrite_EventWriteTransfer
0x180002541  jmp     loc_18000232F
0x180002546  lea     r8, ?ExpiredScheduleList@CScheduleMgr@@0U_LIST_ENTRY@@A; _LIST_ENTRY CScheduleMgr::ExpiredScheduleList
0x18000254d  mov     rax, [rdx+8]
0x180002551  mov     rcx, [rdx]
0x180002554  mov     [rax], rcx
0x180002557  mov     [rcx+8], rax
0x18000255b  mov     rax, cs:?ExpiredScheduleList@CScheduleMgr@@0U_LIST_ENTRY@@A; _LIST_ENTRY CScheduleMgr::ExpiredScheduleList
0x180002562  mov     [rdx], rax
0x180002565  mov     [rdx+8], r8
0x180002569  mov     [rax+8], rdx
0x18000256d  lea     rax, [rsp+1C0h+var_160]
0x180002572  mov     cs:?ExpiredScheduleList@CScheduleMgr@@0U_LIST_ENTRY@@A, rdx; _LIST_ENTRY CScheduleMgr::ExpiredScheduleList
0x180002579  mov     rdx, [rsp+1C0h+var_160]
0x18000257e  cmp     rdx, rax
0x180002581  jnz     short loc_18000254D
0x180002583  jmp     loc_180002392
0x180002588  mov     rcx, rbx; pwk
0x18000258b  call    cs:__imp_SubmitThreadpoolWork
0x180002591  mov     rcx, rbx; pwk
0x180002594  call    cs:__imp_CloseThreadpoolWork
0x18000259a  jmp     loc_1800023B4
```
