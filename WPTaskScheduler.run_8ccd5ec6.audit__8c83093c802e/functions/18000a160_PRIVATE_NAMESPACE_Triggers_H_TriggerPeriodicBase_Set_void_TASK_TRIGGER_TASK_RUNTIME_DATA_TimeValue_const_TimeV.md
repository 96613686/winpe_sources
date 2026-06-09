# PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::Set(void *,_TASK_TRIGGER *,_TASK_RUNTIME_DATA *,TimeValue const &,TimeValue const &,uchar,ulong)

- ea: `0x18000a160`
- end: `0x18000aa7a`
- name: `?Set@TriggerPeriodicBase@PRIVATE_NAMESPACE_Triggers_H@@EEAAJPEAXPEAU_TASK_TRIGGER@@PEAU_TASK_RUNTIME_DATA@@AEBVTimeValue@@3EK@Z`
- size: `2330`
- prototype: `__int64 __usercall@<rax>(PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *__hidden this@<rcx>, void *@<rdx>, struct _TASK_TRIGGER *@<r8>, struct _TASK_RUNTIME_DATA *@<r9>, const struct TimeValue *, const struct TimeValue *, unsigned __int8, unsigned int)`
- caller_count: `2`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a0b0`
- `0x18001d2f0`

## callees

- `0x180001260`
- `0x180005c30`
- `0x18000a160`
- `0x18000c700`
- `0x18000d640`
- `0x18000e970`
- `0x18000ea40`
- `0x180018498`
- `0x18001996c`
- `0x18001d4e8`
- `0x18001fa4c`
- `0x18001fadc`
- `0x18001fbac`
- `0x180020c02`
- `0x180020c30`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a79b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a79b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a7ad`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a7ad`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a7ba`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a7ba`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000a346`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000a39f`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000a408`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000a479`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000a6c1`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000a732`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000a346`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000a39f`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000a408`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000a479`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000a6c1`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000a732`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x18000a70e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x18000a70e`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000a2bc`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000a2bc`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x18000a3c2`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x18000a3ef`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x18000a6a8`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x18000a3c2`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x18000a3ef`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x18000a6a8`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x18000a455`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x18000a455`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000a37b`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000a37b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18000a326`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18000a326`
- `EventAggregation!EADeleteAggregateEvent` at `0x18000a4f9`
- `EventAggregation!EADeleteAggregateEvent` at `0x18000a4f9`
- `TimeBrokerClient!TbDeleteCEvent` at `0x18000a516`
- `TimeBrokerClient!TbDeleteCEvent` at `0x18000a516`

## pseudocode

```c
__int64 __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::Set(
        PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *this,
        void *a2,
        struct _TASK_TRIGGER *a3,
        const struct _FILETIME *a4,
        const struct TimeValue *a5,
        const struct TimeValue *a6,
        unsigned __int8 a7)
{
  FILETIME *v10; // rbx
  __int64 v11; // rcx
  void (__fastcall ***v12)(_QWORD, __int64, struct _TASK_TRIGGER *); // rcx
  struct _TP_TIMER *v13; // rcx
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  DWORD v17; // eax
  __int64 v18; // r12
  __int64 v19; // rbx
  DWORD v20; // eax
  int v21; // ebx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r10
  __int64 v26; // rdx
  bool v27; // zf
  unsigned int v28; // eax
  DWORD v29; // eax
  const struct _FILETIME *v30; // rax
  __int64 v31; // rcx
  __int64 v32; // r8
  char v33; // r11
  __int64 v34; // rdx
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  const struct TimeValue *v37; // rdx
  int v38; // [rsp+28h] [rbp-E0h]
  struct _SYSTEMTIME SystemTime_8; // [rsp+58h] [rbp-B0h] BYREF
  struct _TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+68h] [rbp-A0h] BYREF
  DWORD v41; // [rsp+114h] [rbp+Ch]
  SYSTEMTIME v42; // [rsp+118h] [rbp+10h] BYREF
  struct _FILETIME v43; // [rsp+128h] [rbp+20h] BYREF
  struct _FILETIME v44; // [rsp+130h] [rbp+28h]
  __int64 v45; // [rsp+138h] [rbp+30h]
  int v46; // [rsp+140h] [rbp+38h]
  SYSTEMTIME v47; // [rsp+148h] [rbp+40h] BYREF
  struct _FILETIME FileTime; // [rsp+158h] [rbp+50h] BYREF
  struct _FILETIME v49; // [rsp+160h] [rbp+58h]
  __int64 v50; // [rsp+168h] [rbp+60h]
  int v51; // [rsp+170h] [rbp+68h]
  struct _SYSTEMTIME v52; // [rsp+178h] [rbp+70h] BYREF
  __int128 v53; // [rsp+188h] [rbp+80h]
  __int128 v54; // [rsp+198h] [rbp+90h]
  struct _TIME_ZONE_INFORMATION v55; // [rsp+1A8h] [rbp+A0h] BYREF
  struct _SYSTEMTIME UniversalTime; // [rsp+2B8h] [rbp+1B0h] BYREF

  if ( a2 )
  {
    v10 = (FILETIME *)((char *)this + 216);
    *((_DWORD *)this + 28) = 0;
    *((_DWORD *)this + 76) = 0;
    *((_DWORD *)this + 16) = 0;
    *((_DWORD *)this + 88) = 0;
    *((_DWORD *)this + 100) = 0;
    *((_DWORD *)this + 122) = 0;
    *((_QWORD *)this + 22) = a2;
    v11 = *((_QWORD *)this + 54);
    v10[5].dwLowDateTime = 0;
    if ( v11 )
    {
      EADeleteAggregateEvent(v11, a2, a3);
      *((_QWORD *)this + 54) = 0;
    }
    if ( *((_QWORD *)this + 52) )
    {
      TbDeleteCEvent(*((_QWORD *)this + 52), a2, a3);
      *((_QWORD *)this + 52) = 0;
    }
    v12 = (void (__fastcall ***)(_QWORD, __int64, struct _TASK_TRIGGER *))*((_QWORD *)this + 51);
    if ( v12 )
      (**v12)(v12, 1, a3);
    *((_QWORD *)this + 51) = 0;
    *((_QWORD *)this + 53) = 0;
    v13 = (struct _TP_TIMER *)*((_QWORD *)this + 55);
    *((_DWORD *)this + 46) = 0;
    *((_DWORD *)this + 53) = 0;
    if ( v13 )
    {
      SetThreadpoolTimer(v13, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 55), 1);
      CloseThreadpoolTimer(*((PTP_TIMER *)this + 55));
      *((_QWORD *)this + 55) = 0;
      *((_DWORD *)this + 28) = 0;
    }
    if ( (byte_180030D03 & 8) != 0 )
      McTemplateU0q_EventWriteTransfer(v13, PeriodicTriggerType);
    if ( (byte_180030D04 & 2) != 0 )
    {
      McTemplateU0i_EventWriteTransfer(0x1CA213D840BAF7D5LL, PeriodicIntervalMins, *((_QWORD *)this + 24) / 600000000LL);
      if ( (byte_180030D04 & 2) != 0 )
        McTemplateU0q_EventWriteTransfer(0x1CA213D840BAF7D5LL, PeriodicToleranceMins);
    }
    if ( a4
      && (TimeInfo::TimeInfo(&v55),
          v30 = (const struct _FILETIME *)TimeInfo::FileTime((TimeInfo *)&v55, (int)&SystemTime_8),
          TimeValue::Set(&v52, v30),
          (unsigned int)TimeValue::Set((LPSYSTEMTIME)v10, a4)) )
    {
      if ( (byte_180030D03 & 8) != 0 )
        McTemplateU0hhhhhhh_EventWriteTransfer(
          LOWORD(v10[1].dwLowDateTime),
          (unsigned int)HasRuntimeData,
          LOWORD(v10->dwLowDateTime),
          HIWORD(v10->dwLowDateTime),
          HIWORD(v10->dwHighDateTime),
          v10[1].dwLowDateTime,
          HIWORD(v10[1].dwLowDateTime),
          v10[1].dwHighDateTime,
          HIWORD(v10[1].dwHighDateTime));
      if ( (unsigned int)operator<(&v52, v10) && *((_QWORD *)this + 30) - *((_QWORD *)&v53 + 1) > *((_QWORD *)this + 24) )
      {
        if ( v33 < 0 )
          McGenEventWrite_EventWriteTransfer(v31, TimeDifferenceExceedsMaxInterval, v32, 1, &UniversalTime);
        v34 = *((_QWORD *)this + 24);
        v35 = v53;
        *(struct _SYSTEMTIME *)&v10->dwLowDateTime = v52;
        v36 = v54;
        *(_OWORD *)&v10[2].dwLowDateTime = v35;
        *(_OWORD *)&v10[4].dwLowDateTime = v36;
        TimeValue::AdvanceNs100((SYSTEMTIME *)v10, v34, 0);
        RoundMinutes((LPSYSTEMTIME)v10);
      }
      if ( a4[1] )
      {
        TimeValue::Set((LPSYSTEMTIME)((char *)this + 72), a4 + 1);
        if ( (unsigned int)operator>=((char *)this + 72, v10) )
          *((_DWORD *)this + 28) = 0;
        else
          PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::SetSnoozeTimer(
            this,
            v37,
            (PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *)((char *)this + 72));
      }
    }
    else if ( *((_DWORD *)a6 + 10) )
    {
      *(_OWORD *)&v10->dwLowDateTime = *(_OWORD *)a6;
      *(_OWORD *)&v10[2].dwLowDateTime = *((_OWORD *)a6 + 1);
      *(_OWORD *)&v10[4].dwLowDateTime = *((_OWORD *)a6 + 2);
    }
    else
    {
      *(_OWORD *)&v10->dwLowDateTime = *(_OWORD *)a5;
      *(_OWORD *)&v10[2].dwLowDateTime = *((_OWORD *)a5 + 1);
      *(_OWORD *)&v10[4].dwLowDateTime = *((_OWORD *)a5 + 2);
      if ( v10[5].dwLowDateTime )
      {
        *(_QWORD *)&v10[3] += *((_QWORD *)this + 24);
        v10[2] = v10[3];
        FileTimeToSystemTime(v10 + 2, (LPSYSTEMTIME)v10);
      }
    }
    v14 = *(_OWORD *)((char *)this + 216);
    v15 = *(_OWORD *)((char *)this + 232);
    v45 = 0;
    *(_OWORD *)((char *)this + 264) = v14;
    v46 = 0;
    v16 = *(_OWORD *)((char *)this + 248);
    v43 = 0;
    *(_OWORD *)((char *)this + 280) = v15;
    v44 = 0;
    *(_OWORD *)((char *)this + 296) = v16;
    v50 = 0;
    v51 = 0;
    v42 = 0;
    FileTime = 0;
    v47 = 0;
    v49 = 0;
    SystemTime_8 = 0;
    GetSystemTime(&SystemTime_8);
    v47 = SystemTime_8;
    if ( SystemTimeToFileTime(&v47, &FileTime) )
    {
      v49 = FileTime;
      v50 = 0;
      v51 = 1;
    }
    UniversalTime = 0;
    GetLocalTime(&UniversalTime);
    v42 = UniversalTime;
    if ( SystemTimeToFileTime(&v42, &v43) )
    {
      v44 = v43;
      v45 = 0;
      v46 = 1;
    }
    v17 = GetTimeZoneInformation(&TimeZoneInformation);
    v18 = *((_QWORD *)this + 27);
    v19 = *((_QWORD *)this + 28);
    v41 = v17;
    if ( (*(_BYTE *)(*((_QWORD *)this + 22) + 44LL) & 8) != 0 )
    {
      v29 = GetTimeZoneInformation(&TimeZoneInformation);
      *(_QWORD *)&v47.wYear = v18;
      v41 = v29;
      *(_QWORD *)&v47.wHour = v19;
      if ( SystemTimeToFileTime(&v47, &FileTime) )
      {
        v49 = FileTime;
        v50 = 0;
        v51 = 1;
      }
      SystemTime_8 = v47;
      UniversalTime = 0;
      SystemTimeToTzSpecificLocalTime(&TimeZoneInformation, &SystemTime_8, &UniversalTime);
      v42 = UniversalTime;
      if ( SystemTimeToFileTime(&v42, &v43) )
      {
        v44 = v43;
        v45 = 0;
        v46 = 1;
      }
    }
    else
    {
      v20 = GetTimeZoneInformation(&TimeZoneInformation);
      *(_QWORD *)&v42.wYear = v18;
      v41 = v20;
      *(_QWORD *)&v42.wHour = v19;
      if ( SystemTimeToFileTime(&v42, &v43) )
      {
        v44 = v43;
        v45 = 0;
        v46 = 1;
      }
      SystemTime_8 = v42;
      UniversalTime = 0;
      TzSpecificLocalTimeToSystemTime(&TimeZoneInformation, &SystemTime_8, &UniversalTime);
      v47 = UniversalTime;
      if ( SystemTimeToFileTime(&v47, &FileTime) )
      {
        v49 = FileTime;
        v50 = 0;
        v51 = 1;
      }
    }
    LOBYTE(v38) = a7;
    v21 = (*(__int64 (__fastcall **)(PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *, void *, const struct TimeValue *, const struct TimeValue *, int))(*(_QWORD *)this + 136LL))(
            this,
            a2,
            a5,
            a6,
            v38);
    if ( v21 < 0 )
      return (unsigned int)v21;
    memset_0((char *)this + 496, 0, 0xF8u);
    v23 = *((_QWORD *)this + 24);
    v24 = *((_QWORD *)this + 25);
    *((_BYTE *)this + 549) = 1;
    v25 = v23 / 10000000;
    *((_DWORD *)this + 130) = v23 / 10000000;
    v26 = v24 / 10000000;
    v27 = *((_DWORD *)this + 52) == 1;
    UniversalTime = v47;
    *(SYSTEMTIME *)((char *)this + 504) = v47;
    if ( v27 )
    {
      v28 = 2 * v26;
      *((_DWORD *)this + 124) = 4;
      if ( !(2 * (_DWORD)v26) )
        v28 = 1;
      if ( (_DWORD)v25 && v28 <= (unsigned int)v25 )
      {
        if ( v28 == (_DWORD)v25 )
          v28 -= 2;
      }
      else
      {
        v21 = -2147467259;
      }
      *((_DWORD *)this + 131) = v28;
      if ( v21 < 0 )
        return (unsigned int)v21;
    }
    else
    {
      *((_DWORD *)this + 124) = 5;
      *((_DWORD *)this + 131) = v26;
      if ( !(_DWORD)v26 )
        *((_DWORD *)this + 131) = 1;
    }
    if ( *((_DWORD *)a6 + 10) && (byte_180030D04 & 2) != 0 )
      McTemplateU0hhhhhhh_EventWriteTransfer(
        *((unsigned __int16 *)a6 + 4),
        (unsigned int)TriggerStartTimeDate,
        *(unsigned __int16 *)a6,
        *((unsigned __int16 *)a6 + 1),
        *((_WORD *)a6 + 3),
        *((_WORD *)a6 + 4),
        *((_WORD *)a6 + 5),
        *((_WORD *)a6 + 6),
        *((_WORD *)a6 + 7));
    if ( (byte_180030D04 & 2) != 0 )
      McTemplateU0hhhhhhh_EventWriteTransfer(
        *((unsigned __int16 *)this + 112),
        (unsigned int)NextTriggerTimeDate,
        *((unsigned __int16 *)this + 108),
        *((unsigned __int16 *)this + 109),
        *((_WORD *)this + 111),
        *((_WORD *)this + 112),
        *((_WORD *)this + 113),
        *((_WORD *)this + 114),
        *((_WORD *)this + 115));
    if ( (byte_180030D04 & 2) != 0 )
      McTemplateU0hhhhhhh_EventWriteTransfer(
        *((unsigned __int16 *)this + 40),
        (unsigned int)SnoozedTriggerTimeDate,
        *((unsigned __int16 *)this + 36),
        *((unsigned __int16 *)this + 37),
        *((_WORD *)this + 39),
        *((_WORD *)this + 40),
        *((_WORD *)this + 41),
        *((_WORD *)this + 42),
        *((_WORD *)this + 43));
    return (unsigned int)v21;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x18000a160  mov     r11, rsp
0x18000a163  push    rbp
0x18000a164  push    rsi
0x18000a165  push    rdi
0x18000a166  push    r13
0x18000a168  push    r14
0x18000a16a  push    r15
0x18000a16c  lea     rbp, [r11-208h]
0x18000a173  sub     rsp, 2D8h
0x18000a17a  mov     rax, cs:__security_cookie
0x18000a181  xor     rax, rsp
0x18000a184  mov     [rbp+200h+var_40], rax
0x18000a18b  mov     r15, [rbp+200h+arg_28]
0x18000a192  mov     r13, r9
0x18000a195  mov     rsi, [rbp+200h+arg_20]
0x18000a19c  mov     r14, rdx
0x18000a19f  mov     rdi, rcx
0x18000a1a2  test    rdx, rdx
0x18000a1a5  jz      loc_18000A78B
0x18000a1ab  xor     eax, eax
0x18000a1ad  mov     [r11+18h], rbx
0x18000a1b1  lea     rbx, [rcx+0D8h]
0x18000a1b8  mov     [rcx+70h], eax
0x18000a1bb  mov     [rcx+130h], eax
0x18000a1c1  mov     [rcx+40h], eax
0x18000a1c4  mov     [rcx+160h], eax
0x18000a1ca  mov     [rcx+190h], eax
0x18000a1d0  mov     [rcx+1E8h], eax
0x18000a1d6  mov     [rcx+0B0h], rdx
0x18000a1dd  mov     rcx, [rcx+1B0h]
0x18000a1e4  mov     [r11-38h], r12
0x18000a1e8  mov     [rbx+28h], eax
0x18000a1eb  test    rcx, rcx
0x18000a1ee  jnz     loc_18000A4F9
0x18000a1f4  mov     eax, [rdi+1A4h]
0x18000a1fa  or      eax, [rdi+1A0h]
0x18000a200  jnz     loc_18000A50F
0x18000a206  mov     rcx, [rdi+198h]
0x18000a20d  test    rcx, rcx
0x18000a210  jnz     loc_18000A693
0x18000a216  xor     edx, edx; pftDueTime
0x18000a218  xor     eax, eax
0x18000a21a  mov     [rdi+198h], rdx
0x18000a221  mov     [rdi+1A8h], rax
0x18000a228  mov     rcx, [rdi+1B8h]; pti
0x18000a22f  mov     [rdi+0B8h], edx
0x18000a235  mov     [rdi+0D4h], edx
0x18000a23b  test    rcx, rcx
0x18000a23e  jnz     loc_18000A795
0x18000a244  test    cs:byte_180030D03, 8
0x18000a24b  jnz     loc_18000A7D1
0x18000a251  movzx   eax, cs:byte_180030D04
0x18000a258  mov     rcx, 1CA213D840BAF7D5h
0x18000a262  test    al, 2
0x18000a264  jnz     loc_18000A7E9
0x18000a26a  test    r13, r13
0x18000a26d  jnz     loc_18000A84F
0x18000a273  cmp     dword ptr [r15+28h], 0
0x18000a278  jnz     loc_18000A9BD
0x18000a27e  movups  xmm0, xmmword ptr [rsi]
0x18000a281  movups  xmmword ptr [rbx], xmm0
0x18000a284  movups  xmm1, xmmword ptr [rsi+10h]
0x18000a288  movups  xmmword ptr [rbx+10h], xmm1
0x18000a28c  movups  xmm0, xmmword ptr [rsi+20h]
0x18000a290  movups  xmmword ptr [rbx+20h], xmm0
0x18000a294  cmp     dword ptr [rbx+28h], 0
0x18000a298  jz      short loc_18000A2C2
0x18000a29a  mov     rax, [rdi+0C0h]
0x18000a2a1  lea     rcx, [rbx+10h]; lpFileTime
0x18000a2a5  add     [rbx+18h], rax
0x18000a2a9  mov     rdx, [rbx+18h]
0x18000a2ad  mov     rax, rdx
0x18000a2b0  mov     [rcx], edx
0x18000a2b2  shr     rax, 20h
0x18000a2b6  mov     rdx, rbx; lpSystemTime
0x18000a2b9  mov     [rcx+4], eax
0x18000a2bc  call    cs:__imp_FileTimeToSystemTime
0x18000a2c2  movups  xmm0, xmmword ptr [rdi+0D8h]
0x18000a2c9  xor     eax, eax
0x18000a2cb  xor     r12d, r12d
0x18000a2ce  movups  xmm1, xmmword ptr [rdi+0E8h]
0x18000a2d5  lea     rcx, [rsp+300h+SystemTime.wHour]; lpSystemTime
0x18000a2da  mov     [rbp+200h+var_1D0], r12
0x18000a2de  movups  xmmword ptr [rdi+108h], xmm0
0x18000a2e5  mov     [rbp+200h+var_1C8], r12d
0x18000a2e9  movups  xmm0, xmmword ptr [rdi+0F8h]
0x18000a2f0  mov     qword ptr [rbp+200h+var_1E0.dwLowDateTime], rax
0x18000a2f4  movups  xmmword ptr [rdi+118h], xmm1
0x18000a2fb  mov     [rbp+200h+var_1D8], rax
0x18000a2ff  movups  xmmword ptr [rdi+128h], xmm0
0x18000a306  mov     [rbp+200h+var_1A0], r12
0x18000a30a  xorps   xmm0, xmm0
0x18000a30d  mov     [rbp+200h+var_198], r12d
0x18000a311  movups  xmmword ptr [rbp+200h+var_1F0.wYear], xmm0
0x18000a315  mov     qword ptr [rbp+200h+FileTime.dwLowDateTime], rax
0x18000a319  movups  xmmword ptr [rbp+200h+var_1C0.wYear], xmm0
0x18000a31d  mov     [rbp+200h+var_1A8], rax
0x18000a321  movups  xmmword ptr [rsp+300h+SystemTime.wHour], xmm0
0x18000a326  call    cs:__imp_GetSystemTime
0x18000a32c  mov     rax, qword ptr [rsp+300h+SystemTime.wHour]
0x18000a331  lea     rdx, [rbp+200h+FileTime]; lpFileTime
0x18000a335  mov     qword ptr [rbp+200h+var_1C0.wYear], rax
0x18000a339  lea     rcx, [rbp+200h+var_1C0]; lpSystemTime
0x18000a33d  mov     rax, qword ptr [rsp+300h+var_2A8]
0x18000a342  mov     qword ptr [rbp+200h+var_1C0.wHour], rax
0x18000a346  call    cs:__imp_SystemTimeToFileTime
0x18000a34c  mov     r13d, 1
0x18000a352  test    eax, eax
0x18000a354  jz      short loc_18000A36A
0x18000a356  mov     eax, [rbp+200h+FileTime.dwHighDateTime]
0x18000a359  mov     dword ptr [rbp+200h+var_1A8+4], eax
0x18000a35c  mov     eax, [rbp+200h+FileTime.dwLowDateTime]
0x18000a35f  mov     dword ptr [rbp+200h+var_1A8], eax
0x18000a362  mov     [rbp+200h+var_1A0], r12
0x18000a366  mov     [rbp+200h+var_198], r13d
0x18000a36a  xorps   xmm0, xmm0
0x18000a36d  lea     rcx, [rbp+200h+UniversalTime]; lpSystemTime
0x18000a374  movups  xmmword ptr [rbp+200h+UniversalTime.wYear], xmm0
0x18000a37b  call    cs:__imp_GetLocalTime
0x18000a381  mov     rax, qword ptr [rbp+200h+UniversalTime.wYear]
0x18000a388  lea     rdx, [rbp+200h+var_1E0]; lpFileTime
0x18000a38c  mov     qword ptr [rbp+200h+var_1F0.wYear], rax
0x18000a390  lea     rcx, [rbp+200h+var_1F0]; lpSystemTime
0x18000a394  mov     rax, qword ptr [rbp+200h+UniversalTime.wHour]
0x18000a39b  mov     qword ptr [rbp+200h+var_1F0.wHour], rax
0x18000a39f  call    cs:__imp_SystemTimeToFileTime
0x18000a3a5  test    eax, eax
0x18000a3a7  jz      short loc_18000A3BD
0x18000a3a9  mov     eax, [rbp+200h+var_1E0.dwHighDateTime]
0x18000a3ac  mov     dword ptr [rbp+200h+var_1D8+4], eax
0x18000a3af  mov     eax, [rbp+200h+var_1E0.dwLowDateTime]
0x18000a3b2  mov     dword ptr [rbp+200h+var_1D8], eax
0x18000a3b5  mov     [rbp+200h+var_1D0], r12
0x18000a3b9  mov     [rbp+200h+var_1C8], r13d
0x18000a3bd  lea     rcx, [rsp+300h+TimeZoneInformation]; lpTimeZoneInformation
0x18000a3c2  call    cs:__imp_GetTimeZoneInformation
0x18000a3c8  mov     r12, [rdi+0D8h]
0x18000a3cf  lea     rcx, [rsp+300h+TimeZoneInformation]; lpTimeZoneInformation
0x18000a3d4  mov     rbx, [rdi+0E0h]
0x18000a3db  mov     [rbp+200h+var_1F4], eax
0x18000a3de  mov     rax, [rdi+0B0h]
0x18000a3e5  test    byte ptr [rax+2Ch], 8
0x18000a3e9  jnz     loc_18000A6A8
0x18000a3ef  call    cs:__imp_GetTimeZoneInformation
0x18000a3f5  lea     rdx, [rbp+200h+var_1E0]; lpFileTime
0x18000a3f9  mov     qword ptr [rbp+200h+var_1F0.wYear], r12
0x18000a3fd  lea     rcx, [rbp+200h+var_1F0]; lpSystemTime
0x18000a401  mov     [rbp+200h+var_1F4], eax
0x18000a404  mov     qword ptr [rbp+200h+var_1F0.wHour], rbx
0x18000a408  call    cs:__imp_SystemTimeToFileTime
0x18000a40e  test    eax, eax
0x18000a410  jz      short loc_18000A428
0x18000a412  mov     eax, [rbp+200h+var_1E0.dwHighDateTime]
0x18000a415  xor     ebx, ebx
0x18000a417  mov     dword ptr [rbp+200h+var_1D8+4], eax
0x18000a41a  mov     eax, [rbp+200h+var_1E0.dwLowDateTime]
0x18000a41d  mov     dword ptr [rbp+200h+var_1D8], eax
0x18000a420  mov     [rbp+200h+var_1D0], rbx
0x18000a424  mov     [rbp+200h+var_1C8], r13d
0x18000a428  mov     rax, qword ptr [rbp+200h+var_1F0.wYear]
0x18000a42c  lea     r8, [rbp+200h+UniversalTime]; lpUniversalTime
0x18000a433  mov     qword ptr [rsp+300h+SystemTime.wHour], rax
0x18000a438  lea     rdx, [rsp+300h+SystemTime.wHour]; lpLocalTime
0x18000a43d  mov     rax, qword ptr [rbp+200h+var_1F0.wHour]
0x18000a441  lea     rcx, [rsp+300h+TimeZoneInformation]; lpTimeZoneInformation
0x18000a446  xorps   xmm0, xmm0
0x18000a449  mov     qword ptr [rsp+300h+var_2A8], rax
0x18000a44e  movups  xmmword ptr [rbp+200h+UniversalTime.wYear], xmm0
0x18000a455  call    cs:__imp_TzSpecificLocalTimeToSystemTime
0x18000a45b  mov     rax, qword ptr [rbp+200h+UniversalTime.wYear]
0x18000a462  lea     rdx, [rbp+200h+FileTime]; lpFileTime
0x18000a466  mov     qword ptr [rbp+200h+var_1C0.wYear], rax
0x18000a46a  lea     rcx, [rbp+200h+var_1C0]; lpSystemTime
0x18000a46e  mov     rax, qword ptr [rbp+200h+UniversalTime.wHour]
0x18000a475  mov     qword ptr [rbp+200h+var_1C0.wHour], rax
0x18000a479  call    cs:__imp_SystemTimeToFileTime
0x18000a47f  test    eax, eax
0x18000a481  jz      short loc_18000A49B
0x18000a483  mov     eax, [rbp+200h+FileTime.dwHighDateTime]
0x18000a486  mov     dword ptr [rbp+200h+var_1A8+4], eax
0x18000a489  mov     eax, [rbp+200h+FileTime.dwLowDateTime]
0x18000a48c  mov     dword ptr [rbp+200h+var_1A8], eax
0x18000a48f  mov     [rbp+200h+var_1A0], 0
0x18000a497  mov     [rbp+200h+var_198], r13d
0x18000a49b  mov     rax, [rdi]
0x18000a49e  mov     r9, r15
0x18000a4a1  movzx   ecx, [rbp+200h+arg_30]
0x18000a4a8  mov     r8, rsi
0x18000a4ab  mov     byte ptr [rsp+300h+var_2E0], cl
0x18000a4af  mov     rdx, r14
0x18000a4b2  mov     rcx, rdi
0x18000a4b5  mov     rax, [rax+88h]
0x18000a4bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4c1  mov     r12, [rsp+2D0h]
0x18000a4c9  mov     ebx, eax
0x18000a4cb  test    eax, eax
0x18000a4cd  jns     short loc_18000A52A
0x18000a4cf  mov     eax, ebx
0x18000a4d1  mov     rbx, [rsp+300h+arg_10]
0x18000a4d9  mov     rcx, [rbp+200h+var_40]
0x18000a4e0  xor     rcx, rsp; StackCookie
0x18000a4e3  call    __security_check_cookie
0x18000a4e8  add     rsp, 2D8h
0x18000a4ef  pop     r15
0x18000a4f1  pop     r14
0x18000a4f3  pop     r13
0x18000a4f5  pop     rdi
0x18000a4f6  pop     rsi
0x18000a4f7  pop     rbp
0x18000a4f8  retn
0x18000a4f9  call    cs:__imp_EADeleteAggregateEvent
0x18000a4ff  mov     qword ptr [rdi+1B0h], 0
0x18000a50a  jmp     loc_18000A1F4
0x18000a50f  mov     rcx, [rdi+1A0h]
0x18000a516  call    cs:__imp_TbDeleteCEvent
0x18000a51c  xor     eax, eax
0x18000a51e  mov     [rdi+1A0h], rax
0x18000a525  jmp     loc_18000A206
0x18000a52a  xor     edx, edx; Val
0x18000a52c  lea     rcx, [rdi+1F0h]; void *
0x18000a533  mov     r8d, 0F8h; Size
0x18000a539  call    memset_0
0x18000a53e  mov     rcx, [rdi+0C0h]
0x18000a545  mov     r11, 0D6BF94D5E57A42BDh
0x18000a54f  mov     r8, [rdi+0C8h]
0x18000a556  mov     rax, r11
0x18000a559  imul    rcx
0x18000a55c  mov     byte ptr [rdi+225h], 1
0x18000a563  mov     rax, r11
0x18000a566  lea     r10, [rcx+rdx]
0x18000a56a  imul    r8
0x18000a56d  sar     r10, 17h
0x18000a571  add     rdx, r8
0x18000a574  mov     rcx, r10
0x18000a577  sar     rdx, 17h
0x18000a57b  mov     rax, rdx
0x18000a57e  shr     rcx, 3Fh
0x18000a582  shr     rax, 3Fh
0x18000a586  add     r10, rcx
0x18000a589  mov     [rdi+208h], r10d
0x18000a590  add     rdx, rax
0x18000a593  cmp     dword ptr [rdi+0D0h], 1
0x18000a59a  mov     rax, qword ptr [rbp+200h+var_1C0.wYear]
0x18000a59e  mov     qword ptr [rbp+200h+UniversalTime.wYear], rax
0x18000a5a5  mov     rax, qword ptr [rbp+200h+var_1C0.wHour]
0x18000a5a9  mov     qword ptr [rbp+200h+UniversalTime.wHour], rax
0x18000a5b0  movups  xmm0, xmmword ptr [rbp+200h+UniversalTime.wYear]
0x18000a5b7  movups  xmmword ptr [rdi+1F8h], xmm0
0x18000a5be  jnz     loc_18000A767
0x18000a5c4  lea     eax, [rdx+rdx]
0x18000a5c7  mov     dword ptr [rdi+1F0h], 4
0x18000a5d1  test    eax, eax
0x18000a5d3  cmovz   eax, r13d
0x18000a5d7  test    r10d, r10d
0x18000a5da  jz      loc_18000A75D
0x18000a5e0  cmp     eax, r10d
0x18000a5e3  ja      loc_18000A75D
0x18000a5e9  jz      loc_18000A9DB
0x18000a5ef  mov     [rdi+20Ch], eax
0x18000a5f5  test    ebx, ebx
0x18000a5f7  js      loc_18000A4CF
0x18000a5fd  cmp     dword ptr [r15+28h], 0
0x18000a602  jnz     loc_18000A9E3
0x18000a608  test    cs:byte_180030D04, 2
0x18000a60f  movzx   eax, word ptr [rdi+0DEh]
0x18000a616  movzx   ecx, word ptr [rdi+0E0h]
0x18000a61d  movzx   edx, word ptr [rdi+0E2h]
0x18000a624  movzx   r8d, word ptr [rdi+0E4h]
0x18000a62c  movzx   r9d, word ptr [rdi+0E6h]
0x18000a634  jnz     loc_18000AA3E
0x18000a63a  test    cs:byte_180030D04, 2
0x18000a641  movzx   eax, word ptr [rdi+4Eh]
0x18000a645  movzx   ecx, word ptr [rdi+50h]
0x18000a649  movzx   edx, word ptr [rdi+52h]
0x18000a64d  movzx   r8d, word ptr [rdi+54h]
0x18000a652  movzx   r9d, word ptr [rdi+56h]
0x18000a657  jz      loc_18000A4CF
0x18000a65d  mov     [rsp+40h], r9w
0x18000a663  movzx   r9d, word ptr [rdi+4Ah]
0x18000a668  mov     [rsp+300h+var_2C8], r8w
0x18000a66e  movzx   r8d, word ptr [rdi+48h]
0x18000a673  mov     [rsp+300h+var_2D0], dx
0x18000a678  lea     rdx, SnoozedTriggerTimeDate
0x18000a67f  mov     [rsp+300h+var_2D8], cx
0x18000a684  mov     [rsp+300h+var_2E0], ax
0x18000a689  call    McTemplateU0hhhhhhh_EventWriteTransfer
0x18000a68e  jmp     loc_18000A4CF
0x18000a693  mov     rax, [rcx]
0x18000a696  mov     edx, 1
0x18000a69b  mov     rax, [rax]
0x18000a69e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6a3  jmp     loc_18000A216
0x18000a6a8  call    cs:__imp_GetTimeZoneInformation
0x18000a6ae  lea     rdx, [rbp+200h+FileTime]; lpFileTime
0x18000a6b2  mov     qword ptr [rbp+200h+var_1C0.wYear], r12
0x18000a6b6  lea     rcx, [rbp+200h+var_1C0]; lpSystemTime
0x18000a6ba  mov     [rbp+200h+var_1F4], eax
0x18000a6bd  mov     qword ptr [rbp+200h+var_1C0.wHour], rbx
0x18000a6c1  call    cs:__imp_SystemTimeToFileTime
0x18000a6c7  test    eax, eax
  ... truncated ...
```
