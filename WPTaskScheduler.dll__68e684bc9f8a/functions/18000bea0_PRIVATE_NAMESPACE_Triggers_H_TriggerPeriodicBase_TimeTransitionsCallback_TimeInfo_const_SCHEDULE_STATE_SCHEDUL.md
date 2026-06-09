# PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::TimeTransitionsCallback(TimeInfo const &,_SCHEDULE_STATE,_SCHEDULE_STATE)

- ea: `0x18000bea0`
- end: `0x18000c443`
- name: `?TimeTransitionsCallback@TriggerPeriodicBase@PRIVATE_NAMESPACE_Triggers_H@@EEAAJAEBVTimeInfo@@W4_SCHEDULE_STATE@@1@Z`
- size: `1443`
- prototype: `__int64 __fastcall(__int64, __int64, int, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001260`
- `0x180001cd0`
- `0x180005c30`
- `0x18000bea0`
- `0x18000cbb0`
- `0x18000ce80`
- `0x18000d8c0`
- `0x180020c30`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000c417`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000c417`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000c181`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000c1b2`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000c181`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000c1b2`
- `EventAggregation!EACreateAggregateEvent` at `0x18000c11b`
- `EventAggregation!EACreateAggregateEvent` at `0x18000c11b`
- `TimeBrokerClient!TbQueryCEventTriggerTime` at `0x18000c156`
- `TimeBrokerClient!TbQueryCEventTriggerTime` at `0x18000c156`
- `TimeBrokerClient!TbCreateCEvent` at `0x18000c069`
- `TimeBrokerClient!TbCreateCEvent` at `0x18000c069`

## pseudocode

```c
__int64 __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::TimeTransitionsCallback(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4)
{
  _DWORD *v5; // rsi
  bool v6; // zf
  __int64 v7; // rdi
  __int128 v8; // xmm1
  __int128 v9; // xmm6
  __int128 v10; // xmm7
  __int128 v11; // xmm8
  __int128 v12; // xmm9
  __int128 v13; // xmm10
  __int128 v14; // xmm11
  __int128 v15; // xmm12
  __int128 v16; // xmm13
  __int128 v17; // xmm14
  __int128 v18; // xmm15
  struct _SYSTEMTIME v19; // xmm0
  int CEvent; // r15d
  __int64 v21; // rcx
  int v22; // r14d
  __int64 v23; // rsi
  __int64 v24; // rbx
  unsigned int v26; // edi
  __int64 v27; // rax
  SYSTEMTIME v28; // xmm0
  int v29; // eax
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  int v34; // r8d
  SYSTEMTIME v35; // xmm0
  __int64 v36; // rdx
  struct _SYSTEMTIME v37; // [rsp+28h] [rbp-E0h] BYREF
  __int128 v38; // [rsp+38h] [rbp-D0h] BYREF
  __int128 v39; // [rsp+48h] [rbp-C0h]
  SYSTEMTIME SystemTime_8; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v41; // [rsp+68h] [rbp-A0h]
  __int128 v42; // [rsp+78h] [rbp-90h]
  __int64 v43; // [rsp+88h] [rbp-80h]
  _OWORD TimeZoneInformation[14]; // [rsp+98h] [rbp-70h] BYREF
  __int128 v45; // [rsp+178h] [rbp+70h]
  __int64 v46; // [rsp+188h] [rbp+80h]
  TIME_ZONE_INFORMATION v47; // [rsp+1A8h] [rbp+A0h] BYREF
  __int128 v48; // [rsp+288h] [rbp+180h]

  if ( a3 == 4 )
  {
    if ( a4 != 3 )
    {
      if ( *(_DWORD *)(a1 + 208) )
      {
        v32 = *(_OWORD *)(a1 + 280);
        *(_OWORD *)(a1 + 216) = *(_OWORD *)(a1 + 264);
        v33 = *(_OWORD *)(a1 + 296);
        *(_OWORD *)(a1 + 232) = v32;
        *(_OWORD *)(a1 + 248) = v33;
        TimeInfo::TimeInfo(&v47);
        v34 = *(_DWORD *)(*(_QWORD *)(a1 + 176) + 44LL) & 8;
        v37 = *(struct _SYSTEMTIME *)(a1 + 264);
        TimeInfo::SetTime(&v47, &v37, v34);
        *(_OWORD *)(a1 + 504) = v48;
      }
      else
      {
        v27 = *(_QWORD *)(a1 + 176);
        DWORD2(v42) = 1;
        if ( (*(_BYTE *)(v27 + 44) & 8) != 0 )
        {
          v28 = *(SYSTEMTIME *)(a2 + 224);
          v41 = *(_OWORD *)(a2 + 240);
          LODWORD(v42) = *(_DWORD *)(a2 + 256);
          v29 = *(_DWORD *)(a2 + 260);
        }
        else
        {
          v28 = *(SYSTEMTIME *)(a2 + 176);
          v41 = *(_OWORD *)(a2 + 192);
          LODWORD(v42) = *(_DWORD *)(a2 + 208);
          v29 = *(_DWORD *)(a2 + 212);
        }
        DWORD1(v42) = v29;
        SystemTime_8 = v28;
        v30 = v41;
        *(SYSTEMTIME *)(a1 + 216) = v28;
        v31 = v42;
        *(_OWORD *)(a1 + 232) = v30;
        *(_OWORD *)(a1 + 248) = v31;
        *(_OWORD *)(a1 + 504) = *(_OWORD *)(a2 + 224);
      }
    }
    v5 = (_DWORD *)(a1 + 420);
    if ( *(_QWORD *)(a1 + 432) || *(_QWORD *)(a1 + 416) )
      PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::UnregisterPeriodicEvent((PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *)a1);
    v6 = *(_DWORD *)(a1 + 212) == 0;
    v7 = *(_QWORD *)(a1 + 736);
    v8 = *(_OWORD *)(a1 + 512);
    v9 = *(_OWORD *)(a1 + 528);
    v10 = *(_OWORD *)(a1 + 544);
    v11 = *(_OWORD *)(a1 + 560);
    v12 = *(_OWORD *)(a1 + 576);
    v13 = *(_OWORD *)(a1 + 592);
    v14 = *(_OWORD *)(a1 + 608);
    v15 = *(_OWORD *)(a1 + 624);
    v16 = *(_OWORD *)(a1 + 640);
    v17 = *(_OWORD *)(a1 + 656);
    v18 = *(_OWORD *)(a1 + 672);
    *(_OWORD *)&v47.Bias = *(_OWORD *)(a1 + 496);
    v19 = *(struct _SYSTEMTIME *)(a1 + 688);
    *(_OWORD *)&v47.StandardName[6] = v8;
    v37 = v19;
    v38 = *(_OWORD *)(a1 + 704);
    v39 = *(_OWORD *)(a1 + 720);
    if ( !v6 )
    {
      v35 = *(SYSTEMTIME *)(a1 + 216);
      v36 = *(_QWORD *)(a1 + 200);
      v41 = *(_OWORD *)(a1 + 232);
      *(_QWORD *)&v42 = *(_QWORD *)(a1 + 248);
      SystemTime_8 = v35;
      DWORD2(v42) = 1;
      TimeValue::AdvanceNs100(&SystemTime_8, -v36, 0);
      TimeInfo::TimeInfo((LPTIME_ZONE_INFORMATION)TimeZoneInformation);
      if ( (*(_BYTE *)(*(_QWORD *)(a1 + 176) + 44LL) & 8) != 0 )
        TimeInfo::SetUTC((TIME_ZONE_INFORMATION *)TimeZoneInformation, &SystemTime_8);
      else
        TimeInfo::SetLocal((TIME_ZONE_INFORMATION *)TimeZoneInformation, &SystemTime_8);
      v6 = *(_DWORD *)(a1 + 208) == 1;
      *(_OWORD *)&v47.StandardName[2] = v45;
      *(_DWORD *)&v47.StandardName[12] = 1;
      if ( v6 )
        v5 = (_DWORD *)(a1 + 420);
    }
    TimeZoneInformation[0] = *(_OWORD *)&v47.Bias;
    v46 = v7;
    TimeZoneInformation[1] = *(_OWORD *)&v47.StandardName[6];
    TimeZoneInformation[12] = v37;
    TimeZoneInformation[2] = v9;
    v45 = v39;
    TimeZoneInformation[3] = v10;
    TimeZoneInformation[4] = v11;
    TimeZoneInformation[5] = v12;
    TimeZoneInformation[6] = v13;
    TimeZoneInformation[7] = v14;
    TimeZoneInformation[8] = v15;
    TimeZoneInformation[9] = v16;
    TimeZoneInformation[10] = v17;
    TimeZoneInformation[11] = v18;
    TimeZoneInformation[13] = v38;
    CEvent = TbCreateCEvent(TimeZoneInformation, a1 + 416);
    if ( CEvent < 0 )
      goto LABEL_30;
    *(_QWORD *)&v42 = CScheduleMgr::BaseCentralEventAggregateCallback;
    v43 = *(_QWORD *)(a1 + 176);
    *(_DWORD *)&SystemTime_8.wYear = *(_DWORD *)(a1 + 416);
    *(_DWORD *)&SystemTime_8.wDayOfWeek = *v5;
    *(_QWORD *)&SystemTime_8.wHour = 0;
    v41 = 0u;
    *((_QWORD *)&v42 + 1) = 0;
    CEvent = EACreateAggregateEvent(&SystemTime_8, a1 + 432);
    if ( (_QWORD)v41 )
      operator delete[]((void *)v41);
    if ( CEvent < 0 )
    {
LABEL_30:
      PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::UnregisterPeriodicEvent((PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *)a1);
      return (unsigned int)CEvent;
    }
    else
    {
      v21 = *(_QWORD *)(a1 + 416);
      *(_QWORD *)&v38 = 0;
      *(_QWORD *)&v37.wYear = 0;
      v22 = TbQueryCEventTriggerTime(v21, &v38, &v37);
      if ( v22 >= 0 )
      {
        v23 = a1 + 360;
        v24 = a1 + 312;
        *(_QWORD *)(v24 + 16) = v38;
        if ( FileTimeToSystemTime((const FILETIME *)(v24 + 16), (LPSYSTEMTIME)v24) )
        {
          *(_DWORD *)(v24 + 28) = *(_DWORD *)(v24 + 20);
          *(_DWORD *)(v24 + 24) = *(_DWORD *)(v24 + 16);
          *(_QWORD *)(v24 + 32) = 0;
          *(_DWORD *)(v24 + 40) = 1;
        }
        *(_QWORD *)(v23 + 16) = *(_QWORD *)&v37.wYear;
        if ( FileTimeToSystemTime((const FILETIME *)(v23 + 16), (LPSYSTEMTIME)v23) )
        {
          *(_DWORD *)(v23 + 28) = *(_DWORD *)(v23 + 20);
          *(_DWORD *)(v23 + 24) = *(_DWORD *)(v23 + 16);
          *(_QWORD *)(v23 + 32) = 0;
          *(_DWORD *)(v23 + 40) = 1;
        }
      }
      return (unsigned int)v22;
    }
  }
  else
  {
    v26 = 0;
    if ( a3 == 5 && a4 == 2 )
      return 47120640;
    return v26;
  }
}

```

## disassembly

```asm
0x18000bea0  mov     r11, rsp
0x18000bea3  push    rbp
0x18000bea4  push    rbx
0x18000bea5  push    rdi
0x18000bea6  lea     rbp, [r11-288h]
0x18000bead  sub     rsp, 370h
0x18000beb4  mov     rax, cs:__security_cookie
0x18000bebb  xor     rax, rsp
0x18000bebe  mov     [rbp+280h+var_D0], rax
0x18000bec5  mov     rbx, rcx
0x18000bec8  cmp     r8d, 4
0x18000becc  jnz     loc_18000C210
0x18000bed2  mov     [r11+18h], r12
0x18000bed6  mov     [r11-20h], r14
0x18000beda  mov     [r11-28h], r15
0x18000bede  movaps  xmmword ptr [r11-38h], xmm6
0x18000bee3  movaps  xmmword ptr [r11-48h], xmm7
0x18000bee8  movaps  xmmword ptr [r11-58h], xmm8
0x18000beed  movaps  xmmword ptr [r11-68h], xmm9
0x18000bef2  movaps  xmmword ptr [r11-78h], xmm10
0x18000bef7  movaps  xmmword ptr [r11-88h], xmm11
0x18000beff  movaps  xmmword ptr [r11-98h], xmm12
0x18000bf07  movaps  xmmword ptr [r11-0A8h], xmm13
0x18000bf0f  movaps  xmmword ptr [r11-0B8h], xmm14
0x18000bf17  movaps  xmmword ptr [r11-0C8h], xmm15
0x18000bf1f  cmp     r9d, 3
0x18000bf23  jnz     loc_18000C220
0x18000bf29  cmp     qword ptr [rbx+1B0h], 0
0x18000bf31  mov     [rsp+380h+arg_8], rsi
0x18000bf39  lea     rsi, [rbx+1A4h]
0x18000bf40  jnz     loc_18000C35A
0x18000bf46  mov     eax, [rbx+1A0h]
0x18000bf4c  or      eax, [rsi]
0x18000bf4e  jnz     loc_18000C35A
0x18000bf54  cmp     dword ptr [rbx+0D4h], 0
0x18000bf5b  movups  xmm0, xmmword ptr [rbx+1F0h]
0x18000bf62  mov     rdi, [rbx+2E0h]
0x18000bf69  movups  xmm1, xmmword ptr [rbx+200h]
0x18000bf70  movups  xmm6, xmmword ptr [rbx+210h]
0x18000bf77  movups  xmm7, xmmword ptr [rbx+220h]
0x18000bf7e  movups  xmm8, xmmword ptr [rbx+230h]
0x18000bf86  movups  xmm9, xmmword ptr [rbx+240h]
0x18000bf8e  movups  xmm10, xmmword ptr [rbx+250h]
0x18000bf96  movups  xmm11, xmmword ptr [rbx+260h]
0x18000bf9e  movups  xmm12, xmmword ptr [rbx+270h]
0x18000bfa6  movups  xmm13, xmmword ptr [rbx+280h]
0x18000bfae  movups  xmm14, xmmword ptr [rbx+290h]
0x18000bfb6  movups  xmm15, xmmword ptr [rbx+2A0h]
0x18000bfbe  movups  xmmword ptr [rbp+280h+var_1E0.Bias], xmm0
0x18000bfc5  movups  xmm0, xmmword ptr [rbx+2B0h]
0x18000bfcc  movups  xmmword ptr [rbp+280h+var_1E0.StandardName+0Ch], xmm1
0x18000bfd3  movups  xmmword ptr [rsp+380h+var_368.wHour], xmm0
0x18000bfd8  movups  xmm0, xmmword ptr [rbx+2C0h]
0x18000bfdf  movups  [rsp+380h+var_358+8], xmm0
0x18000bfe4  movups  xmm0, xmmword ptr [rbx+2D0h]
0x18000bfeb  movups  [rsp+380h+var_348+8], xmm0
0x18000bff0  jnz     loc_18000C367
0x18000bff6  movaps  xmm0, xmmword ptr [rbp+280h+var_1E0.Bias]
0x18000bffd  lea     rdx, [rbx+1A0h]
0x18000c004  movaps  xmm1, xmmword ptr [rbp+280h+var_1E0.StandardName+0Ch]
0x18000c00b  lea     rcx, [rbp+280h+TimeZoneInformation]
0x18000c00f  movups  xmmword ptr [rbp+280h+TimeZoneInformation.Bias], xmm0
0x18000c013  mov     [rbp+280h+var_200], rdi
0x18000c01a  movups  xmm0, xmmword ptr [rsp+380h+var_368.wHour]
0x18000c01f  movups  xmmword ptr [rbp+280h+TimeZoneInformation.StandardName+0Ch], xmm1
0x18000c023  movups  xmm1, [rsp+380h+var_358+8]
0x18000c028  movups  [rbp+280h+var_230], xmm0
0x18000c02c  movups  xmm0, [rsp+380h+var_348+8]
0x18000c031  movups  xmmword ptr [rbp+280h+TimeZoneInformation.StandardName+1Ch], xmm6
0x18000c035  movups  [rbp+280h+var_210], xmm0
0x18000c039  movups  xmmword ptr [rbp+280h+TimeZoneInformation.StandardName+2Ch], xmm7
0x18000c03d  movups  xmmword ptr [rbp+280h+TimeZoneInformation.StandardName+3Ch], xmm8
0x18000c042  movups  xmmword ptr [rbp+280h+TimeZoneInformation.StandardDate.wSecond], xmm9
0x18000c047  movups  xmmword ptr [rbp+280h+TimeZoneInformation.DaylightName+8], xmm10
0x18000c04c  movups  xmmword ptr [rbp+280h+TimeZoneInformation.DaylightName+18h], xmm11
0x18000c051  movups  xmmword ptr [rbp+280h+TimeZoneInformation.DaylightName+28h], xmm12
0x18000c056  movups  xmmword ptr [rbp+280h+TimeZoneInformation.DaylightName+38h], xmm13
0x18000c05b  movups  xmmword ptr [rbp+280h+TimeZoneInformation.DaylightDate.wHour], xmm14
0x18000c060  movups  [rbp+280h+var_240], xmm15
0x18000c065  movups  [rbp+280h+var_220], xmm1
0x18000c069  call    cs:__imp_TbCreateCEvent
0x18000c06f  movaps  xmm15, [rsp+380h+var_C8+8]
0x18000c078  mov     r15d, eax
0x18000c07b  movaps  xmm14, [rsp+380h+var_B8+8]
0x18000c084  movaps  xmm13, [rsp+380h+var_A8+8]
0x18000c08d  movaps  xmm12, [rsp+380h+var_98+8]
0x18000c096  movaps  xmm11, [rsp+380h+var_88+8]
0x18000c09f  movaps  xmm10, [rsp+380h+var_78+8]
0x18000c0a8  movaps  xmm9, [rsp+380h+var_68+8]
0x18000c0b1  movaps  xmm8, [rsp+380h+var_58+8]
0x18000c0ba  movaps  xmm7, [rsp+380h+var_48+8]
0x18000c0c2  movaps  xmm6, [rsp+380h+var_38+8]
0x18000c0ca  test    eax, eax
0x18000c0cc  js      loc_18000C422
0x18000c0d2  xor     edi, edi
0x18000c0d4  lea     rax, ?BaseCentralEventAggregateCallback@CScheduleMgr@@SAXPEAXU_CBROKERED_EVENT_ID@@00K@Z; CScheduleMgr::BaseCentralEventAggregateCallback(void *,_CBROKERED_EVENT_ID,void *,void *,ulong)
0x18000c0db  mov     qword ptr [rsp+380h+var_310], rax
0x18000c0e0  lea     rdx, [rbx+1B0h]
0x18000c0e7  mov     rax, [rbx+0B0h]
0x18000c0ee  lea     rcx, [rsp+380h+SystemTime.wHour]
0x18000c0f3  mov     [rbp+280h+var_300], rax
0x18000c0f7  mov     eax, [rbx+1A0h]
0x18000c0fd  mov     dword ptr [rsp+380h+SystemTime.wHour], eax
0x18000c101  mov     eax, [rsi]
0x18000c103  mov     dword ptr [rsp+380h+SystemTime.wSecond], eax
0x18000c107  mov     [rsp+380h+var_328], rdi
0x18000c10c  mov     [rsp+380h+var_320], rdi
0x18000c111  mov     [rsp+380h+var_318], rdi
0x18000c116  mov     qword ptr [rsp+380h+var_310+8], rdi
0x18000c11b  call    cs:__imp_EACreateAggregateEvent
0x18000c121  mov     rcx, [rsp+380h+var_320]
0x18000c126  mov     r15d, eax
0x18000c129  test    rcx, rcx
0x18000c12c  jnz     loc_18000C417
0x18000c132  test    r15d, r15d
0x18000c135  js      loc_18000C422
0x18000c13b  mov     rcx, [rbx+1A0h]
0x18000c142  lea     r8, [rsp+380h+var_368.wHour]
0x18000c147  lea     rdx, [rsp+380h+var_358+8]
0x18000c14c  mov     qword ptr [rsp+380h+var_358+8], rdi
0x18000c151  mov     qword ptr [rsp+380h+var_368.wHour], rdi
0x18000c156  call    cs:__imp_TbQueryCEventTriggerTime
0x18000c15c  mov     r14d, eax
0x18000c15f  test    eax, eax
0x18000c161  js      short loc_18000C1D3
0x18000c163  mov     rax, qword ptr [rsp+380h+var_358+8]
0x18000c168  lea     rsi, [rbx+168h]
0x18000c16f  add     rbx, 138h
0x18000c176  mov     rdx, rbx; lpSystemTime
0x18000c179  lea     rcx, [rbx+10h]; lpFileTime
0x18000c17d  mov     [rbx+10h], rax
0x18000c181  call    cs:__imp_FileTimeToSystemTime
0x18000c187  test    eax, eax
0x18000c189  jz      short loc_18000C1A2
0x18000c18b  mov     eax, [rbx+14h]
0x18000c18e  mov     [rbx+1Ch], eax
0x18000c191  mov     eax, [rbx+10h]
0x18000c194  mov     [rbx+18h], eax
0x18000c197  mov     [rbx+20h], rdi
0x18000c19b  mov     dword ptr [rbx+28h], 1
0x18000c1a2  mov     rax, qword ptr [rsp+380h+var_368.wHour]
0x18000c1a7  lea     rcx, [rsi+10h]; lpFileTime
0x18000c1ab  mov     rdx, rsi; lpSystemTime
0x18000c1ae  mov     [rsi+10h], rax
0x18000c1b2  call    cs:__imp_FileTimeToSystemTime
0x18000c1b8  test    eax, eax
0x18000c1ba  jz      short loc_18000C1D3
0x18000c1bc  mov     ecx, [rsi+14h]
0x18000c1bf  mov     [rsi+1Ch], ecx
0x18000c1c2  mov     ecx, [rsi+10h]
0x18000c1c5  mov     [rsi+18h], ecx
0x18000c1c8  mov     [rsi+20h], rdi
0x18000c1cc  mov     dword ptr [rsi+28h], 1
0x18000c1d3  mov     eax, r14d
0x18000c1d6  mov     rsi, [rsp+380h+arg_8]
0x18000c1de  mov     r12, [rsp+380h+arg_10]
0x18000c1e6  mov     r14, [rsp+368h]
0x18000c1ee  mov     r15, [rsp+380h+var_20]
0x18000c1f6  mov     rcx, [rbp+280h+var_D0]
0x18000c1fd  xor     rcx, rsp; StackCookie
0x18000c200  call    __security_check_cookie
0x18000c205  add     rsp, 370h
0x18000c20c  pop     rdi
0x18000c20d  pop     rbx
0x18000c20e  pop     rbp
0x18000c20f  retn
0x18000c210  xor     edi, edi
0x18000c212  cmp     r8d, 5
0x18000c216  jz      loc_18000C432
0x18000c21c  mov     eax, edi
0x18000c21e  jmp     short loc_18000C1F6
0x18000c220  cmp     dword ptr [rcx+0D0h], 0
0x18000c227  jnz     loc_18000C2E5
0x18000c22d  mov     rax, [rcx+0B0h]
0x18000c234  lea     rcx, [rsp+380h+SystemTime.wHour]
0x18000c239  mov     dword ptr [rsp+380h+var_310+8], 1
0x18000c241  test    byte ptr [rax+2Ch], 8
0x18000c245  jz      short loc_18000C278
0x18000c247  mov     rax, [rdx+0F0h]
0x18000c24e  movups  xmm0, xmmword ptr [rdx+0E0h]
0x18000c255  mov     [rsp+380h+var_320], rax
0x18000c25a  mov     rax, [rdx+0F8h]
0x18000c261  mov     [rsp+380h+var_318], rax
0x18000c266  mov     eax, [rdx+100h]
0x18000c26c  mov     dword ptr [rsp+380h+var_310], eax
0x18000c270  mov     eax, [rdx+104h]
0x18000c276  jmp     short loc_18000C2A7
0x18000c278  mov     rax, [rdx+0C0h]
0x18000c27f  movups  xmm0, xmmword ptr [rdx+0B0h]
0x18000c286  mov     [rsp+380h+var_320], rax
0x18000c28b  mov     rax, [rdx+0C8h]
0x18000c292  mov     [rsp+380h+var_318], rax
0x18000c297  mov     eax, [rdx+0D0h]
0x18000c29d  mov     dword ptr [rsp+380h+var_310], eax
0x18000c2a1  mov     eax, [rdx+0D4h]
0x18000c2a7  mov     dword ptr [rsp+380h+var_310+4], eax
0x18000c2ab  mov     eax, 0E0h
0x18000c2b0  movups  xmmword ptr [rsp+380h+SystemTime.wHour], xmm0
0x18000c2b5  movups  xmm0, xmmword ptr [rcx]
0x18000c2b8  movups  xmm1, xmmword ptr [rcx+10h]
0x18000c2bc  movups  xmmword ptr [rbx+0D8h], xmm0
0x18000c2c3  movups  xmm0, xmmword ptr [rcx+20h]
0x18000c2c7  movups  xmmword ptr [rbx+0E8h], xmm1
0x18000c2ce  movups  xmmword ptr [rbx+0F8h], xmm0
0x18000c2d5  movups  xmm1, xmmword ptr [rdx+rax]
0x18000c2d9  movups  xmmword ptr [rbx+1F8h], xmm1
0x18000c2e0  jmp     loc_18000BF29
0x18000c2e5  movups  xmm0, xmmword ptr [rcx+108h]
0x18000c2ec  movups  xmm1, xmmword ptr [rcx+118h]
0x18000c2f3  movups  xmmword ptr [rcx+0D8h], xmm0
0x18000c2fa  movups  xmm0, xmmword ptr [rcx+128h]
0x18000c301  movups  xmmword ptr [rcx+0E8h], xmm1
0x18000c308  movups  xmmword ptr [rcx+0F8h], xmm0
0x18000c30f  lea     rcx, [rbp+280h+var_1E0]; lpTimeZoneInformation
0x18000c316  call    ??0TimeInfo@@QEAA@XZ; TimeInfo::TimeInfo(void)
0x18000c31b  mov     rax, [rbx+0B0h]
0x18000c322  lea     rdx, [rsp+380h+var_368.wHour]; struct _SYSTEMTIME
0x18000c327  movups  xmm0, xmmword ptr [rbx+108h]
0x18000c32e  lea     rcx, [rbp+280h+var_1E0]; lpTimeZoneInformation
0x18000c335  mov     r8d, [rax+2Ch]
0x18000c339  and     r8d, 8; int
0x18000c33d  movaps  xmmword ptr [rsp+380h+var_368.wHour], xmm0
0x18000c342  call    ?SetTime@TimeInfo@@QEAAXU_SYSTEMTIME@@H@Z; TimeInfo::SetTime(_SYSTEMTIME,int)
0x18000c347  movaps  xmm0, [rbp+280h+var_100]
0x18000c34e  movups  xmmword ptr [rbx+1F8h], xmm0
0x18000c355  jmp     loc_18000BF29
0x18000c35a  mov     rcx, rbx; this
0x18000c35d  call    ?UnregisterPeriodicEvent@TriggerPeriodicBase@PRIVATE_NAMESPACE_Triggers_H@@AEAAJXZ; PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::UnregisterPeriodicEvent(void)
0x18000c362  jmp     loc_18000BF54
0x18000c367  mov     rax, [rbx+0E8h]
0x18000c36e  lea     rcx, [rsp+380h+SystemTime.wHour]; lpSystemTime
0x18000c373  movups  xmm0, xmmword ptr [rbx+0D8h]
0x18000c37a  mov     rdx, [rbx+0C8h]
0x18000c381  xor     r8d, r8d; int
0x18000c384  mov     [rsp+380h+var_320], rax
0x18000c389  neg     rdx; __int64
0x18000c38c  mov     rax, [rbx+0F0h]
0x18000c393  mov     [rsp+380h+var_318], rax
0x18000c398  mov     eax, [rbx+0F8h]
0x18000c39e  mov     dword ptr [rsp+380h+var_310], eax
0x18000c3a2  mov     eax, [rbx+0FCh]
0x18000c3a8  mov     dword ptr [rsp+380h+var_310+4], eax
0x18000c3ac  movups  xmmword ptr [rsp+380h+SystemTime.wHour], xmm0
0x18000c3b1  mov     dword ptr [rsp+380h+var_310+8], 1
0x18000c3b9  call    ?AdvanceNs100@TimeValue@@QEAAX_JH@Z; TimeValue::AdvanceNs100(__int64,int)
0x18000c3be  lea     rcx, [rbp+280h+TimeZoneInformation]; lpTimeZoneInformation
0x18000c3c2  call    ??0TimeInfo@@QEAA@XZ; TimeInfo::TimeInfo(void)
0x18000c3c7  mov     rax, [rbx+0B0h]
0x18000c3ce  lea     rdx, [rsp+380h+SystemTime.wHour]; struct TimeValue *
0x18000c3d3  lea     rcx, [rbp+280h+TimeZoneInformation]; lpTimeZoneInformation
0x18000c3d7  test    byte ptr [rax+2Ch], 8
0x18000c3db  jz      short loc_18000C3E4
0x18000c3dd  call    ?SetUTC@TimeInfo@@QEAAXAEBVTimeValue@@@Z; TimeInfo::SetUTC(TimeValue const &)
0x18000c3e2  jmp     short loc_18000C3E9
0x18000c3e4  call    ?SetLocal@TimeInfo@@QEAAXAEBVTimeValue@@@Z; TimeInfo::SetLocal(TimeValue const &)
0x18000c3e9  cmp     dword ptr [rbx+0D0h], 1
0x18000c3f0  movaps  xmm0, [rbp+280h+var_210]
0x18000c3f4  movups  xmmword ptr [rbp+280h+var_1E0.StandardName+4], xmm0
0x18000c3fb  mov     dword ptr [rbp+280h+var_1E0.StandardName+18h], 1
0x18000c405  jnz     loc_18000BFF6
0x18000c40b  lea     rsi, [rbx+1A4h]
0x18000c412  jmp     loc_18000BFF6
0x18000c417  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000c41d  jmp     loc_18000C132
0x18000c422  mov     rcx, rbx; this
0x18000c425  call    ?UnregisterPeriodicEvent@TriggerPeriodicBase@PRIVATE_NAMESPACE_Triggers_H@@AEAAJXZ; PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::UnregisterPeriodicEvent(void)
0x18000c42a  mov     eax, r15d
0x18000c42d  jmp     loc_18000C1D6
0x18000c432  cmp     r9d, 2
0x18000c436  mov     eax, 2CF0100h
0x18000c43b  cmovz   edi, eax
0x18000c43e  jmp     loc_18000C21C
```
