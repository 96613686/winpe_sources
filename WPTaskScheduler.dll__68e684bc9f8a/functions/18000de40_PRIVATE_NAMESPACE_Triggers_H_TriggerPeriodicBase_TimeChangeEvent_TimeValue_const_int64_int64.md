# PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::TimeChangeEvent(TimeValue const &,__int64,__int64)

- ea: `0x18000de40`
- end: `0x18000e28a`
- name: `?TimeChangeEvent@TriggerPeriodicBase@PRIVATE_NAMESPACE_Triggers_H@@EEAAJAEBVTimeValue@@_J1@Z`
- size: `1098`
- prototype: `__int64 __fastcall(PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *this, SYSTEMTIME *, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001260`
- `0x180001b10`
- `0x180001cd0`
- `0x180005c30`
- `0x18000c540`
- `0x18000d8c0`
- `0x18000de40`
- `0x180020c30`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x18000df72`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x18000df72`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000e20f`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000e242`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000e20f`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000e242`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x18000df58`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x18000df58`
- `TimeBrokerClient!TbQueryCEventTriggerTime` at `0x18000e1e5`
- `TimeBrokerClient!TbQueryCEventTriggerTime` at `0x18000e1e5`
- `TimeBrokerClient!TbUpdateCEvent` at `0x18000e1bc`
- `TimeBrokerClient!TbUpdateCEvent` at `0x18000e1bc`

## pseudocode

```c
__int64 __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::TimeChangeEvent(
        PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *this,
        SYSTEMTIME *a2,
        __int64 a3,
        __int64 a4)
{
  SYSTEMTIME *v8; // rbx
  __int64 v9; // rcx
  SYSTEMTIME *v10; // rbx
  SYSTEMTIME v11; // xmm0
  int v12; // r8d
  int v13; // edx
  __int64 v14; // rax
  SYSTEMTIME v15; // xmm0
  SYSTEMTIME v16; // xmm0
  int v17; // eax
  char v18; // al
  SYSTEMTIME v19; // xmm0
  SYSTEMTIME *v20; // rdx
  __int64 v21; // rcx
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  SYSTEMTIME v33; // xmm1
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  SYSTEMTIME v36; // xmm0
  __int64 v37; // rcx
  char *v38; // rbx
  char *v39; // rdi
  SYSTEMTIME SystemTime; // [rsp+20h] [rbp-E0h] BYREF
  SYSTEMTIME v42; // [rsp+30h] [rbp-D0h]
  int v43; // [rsp+40h] [rbp-C0h]
  int v44; // [rsp+44h] [rbp-BCh]
  int v45; // [rsp+48h] [rbp-B8h]
  int v46; // [rsp+4Ch] [rbp-B4h]
  struct _SYSTEMTIME v47; // [rsp+50h] [rbp-B0h] BYREF
  struct _SYSTEMTIME UniversalTime; // [rsp+60h] [rbp-A0h] BYREF
  SYSTEMTIME LocalTime; // [rsp+70h] [rbp-90h] BYREF
  _OWORD TimeZoneInformation[11]; // [rsp+80h] [rbp-80h] BYREF
  SYSTEMTIME v51; // [rsp+130h] [rbp+30h]
  __int128 v52; // [rsp+140h] [rbp+40h]
  __int128 v53; // [rsp+150h] [rbp+50h]
  SYSTEMTIME v54; // [rsp+160h] [rbp+60h]
  __int64 v55; // [rsp+170h] [rbp+70h]
  __int64 v56; // [rsp+178h] [rbp+78h]
  int v57; // [rsp+180h] [rbp+80h]
  int v58; // [rsp+184h] [rbp+84h]
  TIME_ZONE_INFORMATION v59; // [rsp+190h] [rbp+90h] BYREF
  __int128 v60; // [rsp+270h] [rbp+170h]

  if ( !*((_DWORD *)this + 52) )
  {
    v8 = (SYSTEMTIME *)((char *)this + 360);
    PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::GetBrokerNextTriggerTimeUTC(
      this,
      (PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *)((char *)this + 312),
      (PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *)((char *)this + 360));
    TimeInfo::TimeInfo((LPTIME_ZONE_INFORMATION)TimeZoneInformation);
    TimeInfo::SetUTC((TIME_ZONE_INFORMATION *)TimeZoneInformation, v8);
    v9 = *((_QWORD *)this + 22);
    v10 = (SYSTEMTIME *)((char *)this + 216);
    if ( (*(_BYTE *)(v9 + 44) & 8) != 0 )
    {
      v11 = v54;
      v12 = v57;
      v13 = v58;
      *(_QWORD *)&v42.wYear = v55;
      v14 = v56;
    }
    else
    {
      v11 = v51;
      v12 = v53;
      v13 = DWORD1(v53);
      v14 = *((_QWORD *)&v52 + 1);
      *(_QWORD *)&v42.wYear = v52;
    }
    *v10 = v11;
    *(_QWORD *)&v42.wHour = v14;
    v15 = v42;
    *((_DWORD *)this + 65) = v46;
    *(SYSTEMTIME *)((char *)this + 232) = v15;
    *((_DWORD *)this + 62) = v12;
    *((_DWORD *)this + 63) = v13;
    *((_DWORD *)this + 64) = 1;
    if ( (*(_BYTE *)(v9 + 44) & 8) == 0 && a4 )
    {
      LocalTime = *v10;
      UniversalTime = 0;
      TzSpecificLocalTimeToSystemTime(&g_CurrentTimeZoneInfo, &LocalTime, &UniversalTime);
      v47 = 0;
      SystemTimeToTzSpecificLocalTime(0, &UniversalTime, &v47);
      TimeValue::Set((PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *)((char *)this + 216), &v47);
    }
    return 0;
  }
  if ( (*(_BYTE *)(*((_QWORD *)this + 22) + 44LL) & 8) != 0 )
  {
    if ( a3 >= 0 )
      goto LABEL_20;
    v16 = *a2;
    v42 = a2[1];
    v43 = *(_DWORD *)&a2[2].wYear;
    v17 = *(_DWORD *)&a2[2].wDayOfWeek;
    SystemTime = v16;
    v44 = v17;
    v45 = 1;
    TimeValue::AdvanceNs100(&SystemTime, a3, 0);
    TimeValue::AdvanceNs100(
      (SYSTEMTIME *)((char *)this + 216),
      (__int64)(*((_QWORD *)this + 30) - *(_QWORD *)&v42.wHour) % *((_QWORD *)this + 24)
    - (*((_QWORD *)this + 30)
     - *(_QWORD *)&v42.wHour),
      0);
  }
  else
  {
    v18 = 0;
    if ( a4 )
    {
      TimeValue::AdvanceNs100(
        (SYSTEMTIME *)((char *)this + 216),
        -600000000 * a4 - -600000000 * a4 % *((_QWORD *)this + 24),
        0);
      v18 = 1;
    }
    if ( a3 < 0 )
    {
      v19 = *a2;
      v42 = a2[1];
      v43 = *(_DWORD *)&a2[2].wYear;
      v44 = *(_DWORD *)&a2[2].wDayOfWeek;
      SystemTime = v19;
      v45 = 1;
      TimeValue::AdvanceNs100(&SystemTime, a3, 0);
      TimeValue::AdvanceNs100(
        (SYSTEMTIME *)((char *)this + 216),
        (__int64)(*((_QWORD *)this + 30) - *(_QWORD *)&v42.wHour) % *((_QWORD *)this + 24)
      - (*((_QWORD *)this + 30)
       - *(_QWORD *)&v42.wHour),
        0);
      v18 = 1;
    }
    if ( !v18 )
      goto LABEL_20;
  }
  TimeInfo::TimeInfo(&v59);
  v20 = (SYSTEMTIME *)((char *)this + 216);
  if ( (*(_BYTE *)(*((_QWORD *)this + 22) + 44LL) & 8) != 0 )
    TimeInfo::SetUTC(&v59, v20);
  else
    TimeInfo::SetLocal(&v59, v20);
  v21 = *((_QWORD *)this + 52);
  *(_OWORD *)((char *)this + 504) = v60;
  v22 = *((_OWORD *)this + 31);
  v55 = *((_QWORD *)this + 92);
  v23 = *((_OWORD *)this + 32);
  TimeZoneInformation[0] = v22;
  v24 = *((_OWORD *)this + 33);
  TimeZoneInformation[1] = v23;
  v25 = *((_OWORD *)this + 34);
  TimeZoneInformation[2] = v24;
  v26 = *((_OWORD *)this + 35);
  TimeZoneInformation[3] = v25;
  v27 = *((_OWORD *)this + 36);
  TimeZoneInformation[4] = v26;
  v28 = *((_OWORD *)this + 37);
  TimeZoneInformation[5] = v27;
  v29 = *((_OWORD *)this + 38);
  TimeZoneInformation[6] = v28;
  v30 = *((_OWORD *)this + 39);
  TimeZoneInformation[7] = v29;
  v31 = *((_OWORD *)this + 40);
  TimeZoneInformation[8] = v30;
  v32 = *((_OWORD *)this + 41);
  TimeZoneInformation[9] = v31;
  v33 = (SYSTEMTIME)*((_OWORD *)this + 42);
  TimeZoneInformation[10] = v32;
  v34 = *((_OWORD *)this + 43);
  v51 = v33;
  v35 = *((_OWORD *)this + 44);
  v52 = v34;
  v36 = (SYSTEMTIME)*((_OWORD *)this + 45);
  v53 = v35;
  v54 = v36;
  TbUpdateCEvent(v21, TimeZoneInformation);
LABEL_20:
  v37 = *((_QWORD *)this + 52);
  *(_QWORD *)&v47.wYear = 0;
  *(_QWORD *)&UniversalTime.wYear = 0;
  if ( (int)TbQueryCEventTriggerTime(v37, &v47, &UniversalTime) >= 0 )
  {
    v38 = (char *)this + 360;
    v39 = (char *)this + 312;
    *((_QWORD *)v39 + 2) = *(_QWORD *)&v47.wYear;
    if ( FileTimeToSystemTime((const FILETIME *)v39 + 2, (LPSYSTEMTIME)v39) )
    {
      *((_DWORD *)v39 + 7) = *((_DWORD *)v39 + 5);
      *((_DWORD *)v39 + 6) = *((_DWORD *)v39 + 4);
      *((_QWORD *)v39 + 4) = 0;
      *((_DWORD *)v39 + 10) = 1;
    }
    *((_QWORD *)v38 + 2) = *(_QWORD *)&UniversalTime.wYear;
    if ( FileTimeToSystemTime((const FILETIME *)v38 + 2, (LPSYSTEMTIME)v38) )
    {
      *((_DWORD *)v38 + 7) = *((_DWORD *)v38 + 5);
      *((_DWORD *)v38 + 6) = *((_DWORD *)v38 + 4);
      *((_QWORD *)v38 + 4) = 0;
      *((_DWORD *)v38 + 10) = 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000de40  mov     [rsp-8+arg_8], rbx
0x18000de45  push    rbp
0x18000de46  push    rsi
0x18000de47  push    rdi
0x18000de48  push    r14
0x18000de4a  push    r15
0x18000de4c  lea     rbp, [rsp-1B0h]
0x18000de54  sub     rsp, 2B0h
0x18000de5b  mov     rax, cs:__security_cookie
0x18000de62  xor     rax, rsp
0x18000de65  mov     [rbp+1D0h+var_30], rax
0x18000de6c  cmp     dword ptr [rcx+0D0h], 0
0x18000de73  mov     r14, r9
0x18000de76  mov     rbx, r8
0x18000de79  mov     r15, rdx
0x18000de7c  mov     rdi, rcx
0x18000de7f  jnz     loc_18000DF8A
0x18000de85  lea     rbx, [rcx+168h]
0x18000de8c  mov     r8, rbx; struct TimeValue *
0x18000de8f  lea     rdx, [rcx+138h]; struct TimeValue *
0x18000de96  call    ?GetBrokerNextTriggerTimeUTC@TriggerPeriodicBase@PRIVATE_NAMESPACE_Triggers_H@@AEAAJAEAVTimeValue@@0@Z; PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::GetBrokerNextTriggerTimeUTC(TimeValue &,TimeValue &)
0x18000de9b  lea     rcx, [rbp+1D0h+TimeZoneInformation]; lpTimeZoneInformation
0x18000de9f  call    ??0TimeInfo@@QEAA@XZ; TimeInfo::TimeInfo(void)
0x18000dea4  mov     rdx, rbx; struct TimeValue *
0x18000dea7  lea     rcx, [rbp+1D0h+TimeZoneInformation]; lpTimeZoneInformation
0x18000deab  call    ?SetUTC@TimeInfo@@QEAAXAEBVTimeValue@@@Z; TimeInfo::SetUTC(TimeValue const &)
0x18000deb0  mov     rcx, [rdi+0B0h]
0x18000deb7  lea     rbx, [rdi+0D8h]
0x18000debe  mov     esi, 1
0x18000dec3  test    byte ptr [rcx+2Ch], 8
0x18000dec7  jz      short loc_18000DEE9
0x18000dec9  mov     rax, [rbp+1D0h+var_160]
0x18000decd  movaps  xmm0, [rbp+1D0h+var_170]
0x18000ded1  mov     r8d, [rbp+1D0h+var_150]
0x18000ded8  mov     edx, [rbp+1D0h+var_14C]
0x18000dede  mov     qword ptr [rsp+2D0h+var_2A0], rax
0x18000dee3  mov     rax, [rbp+1D0h+var_158]
0x18000dee7  jmp     short loc_18000DF01
0x18000dee9  mov     rax, qword ptr [rbp+1D0h+var_190]
0x18000deed  movaps  xmm0, [rbp+1D0h+var_1A0]
0x18000def1  mov     r8d, dword ptr [rbp+1D0h+var_180]
0x18000def5  mov     edx, dword ptr [rbp+1D0h+var_180+4]
0x18000def8  mov     qword ptr [rsp+2D0h+var_2A0], rax
0x18000defd  mov     rax, qword ptr [rbp+1D0h+var_190+8]
0x18000df01  movups  xmmword ptr [rbx], xmm0
0x18000df04  mov     qword ptr [rsp+2D0h+var_2A0+8], rax
0x18000df09  movups  xmm0, [rsp+2D0h+var_2A0]
0x18000df0e  mov     eax, [rsp+2D0h+var_284]
0x18000df12  mov     [rbx+2Ch], eax
0x18000df15  movups  xmmword ptr [rbx+10h], xmm0
0x18000df19  mov     [rbx+20h], r8d
0x18000df1d  mov     [rbx+24h], edx
0x18000df20  mov     [rbx+28h], esi
0x18000df23  test    byte ptr [rcx+2Ch], 8
0x18000df27  jnz     loc_18000E262
0x18000df2d  test    r14, r14
0x18000df30  jz      loc_18000E262
0x18000df36  movups  xmm0, xmmword ptr [rbx]
0x18000df39  lea     r8, [rsp+2D0h+UniversalTime]; lpUniversalTime
0x18000df3e  xorps   xmm1, xmm1
0x18000df41  lea     rdx, [rsp+2D0h+LocalTime]; lpLocalTime
0x18000df46  lea     rcx, ?g_CurrentTimeZoneInfo@@3U_TIMEZONEINFO@@A; lpTimeZoneInformation
0x18000df4d  movdqu  xmmword ptr [rsp+2D0h+LocalTime.wYear], xmm0
0x18000df53  movups  xmmword ptr [rsp+2D0h+UniversalTime.wYear], xmm1
0x18000df58  call    cs:__imp_TzSpecificLocalTimeToSystemTime
0x18000df5e  xorps   xmm0, xmm0
0x18000df61  lea     r8, [rsp+2D0h+var_280]; lpLocalTime
0x18000df66  lea     rdx, [rsp+2D0h+UniversalTime]; lpUniversalTime
0x18000df6b  xor     ecx, ecx; lpTimeZoneInformation
0x18000df6d  movups  xmmword ptr [rsp+2D0h+var_280.wYear], xmm0
0x18000df72  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x18000df78  lea     rdx, [rsp+2D0h+var_280]; struct _SYSTEMTIME *
0x18000df7d  mov     rcx, rbx; this
0x18000df80  call    ?Set@TimeValue@@QEAAHAEBU_SYSTEMTIME@@@Z; TimeValue::Set(_SYSTEMTIME const &)
0x18000df85  jmp     loc_18000E262
0x18000df8a  mov     rax, [rcx+0B0h]
0x18000df91  mov     esi, 1
0x18000df96  test    byte ptr [rax+2Ch], 8
0x18000df9a  jz      short loc_18000E014
0x18000df9c  test    rbx, rbx
0x18000df9f  jg      loc_18000E1C2
0x18000dfa5  jns     loc_18000E1C2
0x18000dfab  mov     rax, [rdx+10h]
0x18000dfaf  lea     rcx, [rsp+2D0h+SystemTime]; lpSystemTime
0x18000dfb4  movups  xmm0, xmmword ptr [rdx]
0x18000dfb7  mov     qword ptr [rsp+2D0h+var_2A0], rax
0x18000dfbc  xor     r8d, r8d; int
0x18000dfbf  mov     rax, [rdx+18h]
0x18000dfc3  mov     qword ptr [rsp+2D0h+var_2A0+8], rax
0x18000dfc8  mov     eax, [rdx+20h]
0x18000dfcb  mov     [rsp+2D0h+var_290], eax
0x18000dfcf  mov     eax, [rdx+24h]
0x18000dfd2  mov     rdx, rbx; __int64
0x18000dfd5  movdqu  xmmword ptr [rsp+2D0h+SystemTime.wYear], xmm0
0x18000dfdb  mov     [rsp+2D0h+var_28C], eax
0x18000dfdf  mov     [rsp+2D0h+var_288], esi
0x18000dfe3  call    ?AdvanceNs100@TimeValue@@QEAAX_JH@Z; TimeValue::AdvanceNs100(__int64,int)
0x18000dfe8  lea     rcx, [rdi+0D8h]; lpSystemTime
0x18000dfef  mov     r8, [rcx+18h]
0x18000dff3  sub     r8, qword ptr [rsp+2D0h+var_2A0+8]
0x18000dff8  mov     rax, r8
0x18000dffb  cqo
0x18000dffd  idiv    qword ptr [rdi+0C0h]
0x18000e004  sub     rdx, r8; __int64
0x18000e007  xor     r8d, r8d; int
0x18000e00a  call    ?AdvanceNs100@TimeValue@@QEAAX_JH@Z; TimeValue::AdvanceNs100(__int64,int)
0x18000e00f  jmp     loc_18000E0BF
0x18000e014  xor     al, al
0x18000e016  test    r14, r14
0x18000e019  jz      short loc_18000E046
0x18000e01b  imul    r9, r14, 0FFFFFFFFDC3CBA00h
0x18000e022  xor     r8d, r8d; int
0x18000e025  mov     rax, r9
0x18000e028  cqo
0x18000e02a  idiv    qword ptr [rcx+0C0h]
0x18000e031  add     rcx, 0D8h; lpSystemTime
0x18000e038  sub     r9, rdx
0x18000e03b  mov     rdx, r9; __int64
0x18000e03e  call    ?AdvanceNs100@TimeValue@@QEAAX_JH@Z; TimeValue::AdvanceNs100(__int64,int)
0x18000e043  mov     al, sil
0x18000e046  test    rbx, rbx
0x18000e049  jg      short loc_18000E0B7
0x18000e04b  jns     short loc_18000E0B7
0x18000e04d  mov     rax, [r15+10h]
0x18000e051  lea     rcx, [rsp+2D0h+SystemTime]; lpSystemTime
0x18000e056  movups  xmm0, xmmword ptr [r15]
0x18000e05a  mov     qword ptr [rsp+2D0h+var_2A0], rax
0x18000e05f  xor     r8d, r8d; int
0x18000e062  mov     rax, [r15+18h]
0x18000e066  mov     rdx, rbx; __int64
0x18000e069  mov     qword ptr [rsp+2D0h+var_2A0+8], rax
0x18000e06e  mov     eax, [r15+20h]
0x18000e072  mov     [rsp+2D0h+var_290], eax
0x18000e076  mov     eax, [r15+24h]
0x18000e07a  mov     [rsp+2D0h+var_28C], eax
0x18000e07e  movdqu  xmmword ptr [rsp+2D0h+SystemTime.wYear], xmm0
0x18000e084  mov     [rsp+2D0h+var_288], esi
0x18000e088  call    ?AdvanceNs100@TimeValue@@QEAAX_JH@Z; TimeValue::AdvanceNs100(__int64,int)
0x18000e08d  lea     rcx, [rdi+0D8h]; lpSystemTime
0x18000e094  mov     r8, [rcx+18h]
0x18000e098  sub     r8, qword ptr [rsp+2D0h+var_2A0+8]
0x18000e09d  mov     rax, r8
0x18000e0a0  cqo
0x18000e0a2  idiv    qword ptr [rdi+0C0h]
0x18000e0a9  sub     rdx, r8; __int64
0x18000e0ac  xor     r8d, r8d; int
0x18000e0af  call    ?AdvanceNs100@TimeValue@@QEAAX_JH@Z; TimeValue::AdvanceNs100(__int64,int)
0x18000e0b4  mov     al, sil
0x18000e0b7  test    al, al
0x18000e0b9  jz      loc_18000E1C2
0x18000e0bf  lea     rcx, [rbp+1D0h+var_140]; lpTimeZoneInformation
0x18000e0c6  call    ??0TimeInfo@@QEAA@XZ; TimeInfo::TimeInfo(void)
0x18000e0cb  mov     rax, [rdi+0B0h]
0x18000e0d2  lea     rdx, [rdi+0D8h]; struct TimeValue *
0x18000e0d9  lea     rcx, [rbp+1D0h+var_140]; lpTimeZoneInformation
0x18000e0e0  test    byte ptr [rax+2Ch], 8
0x18000e0e4  jz      short loc_18000E0ED
0x18000e0e6  call    ?SetUTC@TimeInfo@@QEAAXAEBVTimeValue@@@Z; TimeInfo::SetUTC(TimeValue const &)
0x18000e0eb  jmp     short loc_18000E0F2
0x18000e0ed  call    ?SetLocal@TimeInfo@@QEAAXAEBVTimeValue@@@Z; TimeInfo::SetLocal(TimeValue const &)
0x18000e0f2  movaps  xmm0, [rbp+1D0h+var_60]
0x18000e0f9  lea     rdx, [rbp+1D0h+TimeZoneInformation]
0x18000e0fd  mov     rcx, [rdi+1A0h]
0x18000e104  movdqu  xmmword ptr [rdi+1F8h], xmm0
0x18000e10c  mov     rax, [rdi+2E0h]
0x18000e113  movups  xmm0, xmmword ptr [rdi+1F0h]
0x18000e11a  mov     [rbp+1D0h+var_160], rax
0x18000e11e  movups  xmm1, xmmword ptr [rdi+200h]
0x18000e125  movups  xmmword ptr [rbp+1D0h+TimeZoneInformation.Bias], xmm0
0x18000e129  movups  xmm0, xmmword ptr [rdi+210h]
0x18000e130  movups  xmmword ptr [rbp+1D0h+TimeZoneInformation.StandardName+0Ch], xmm1
0x18000e134  movups  xmm1, xmmword ptr [rdi+220h]
0x18000e13b  movups  xmmword ptr [rbp+1D0h+TimeZoneInformation.StandardName+1Ch], xmm0
0x18000e13f  movups  xmm0, xmmword ptr [rdi+230h]
0x18000e146  movups  xmmword ptr [rbp+1D0h+TimeZoneInformation.StandardName+2Ch], xmm1
0x18000e14a  movups  xmm1, xmmword ptr [rdi+240h]
0x18000e151  movups  xmmword ptr [rbp+1D0h+TimeZoneInformation.StandardName+3Ch], xmm0
0x18000e155  movups  xmm0, xmmword ptr [rdi+250h]
0x18000e15c  movups  xmmword ptr [rbp+1D0h+TimeZoneInformation.StandardDate.wSecond], xmm1
0x18000e160  movups  xmm1, xmmword ptr [rdi+260h]
0x18000e167  movups  xmmword ptr [rbp+1D0h+TimeZoneInformation.DaylightName+8], xmm0
0x18000e16b  movups  xmm0, xmmword ptr [rdi+270h]
0x18000e172  movups  xmmword ptr [rbp+1D0h+TimeZoneInformation.DaylightName+18h], xmm1
0x18000e176  movups  xmm1, xmmword ptr [rdi+280h]
0x18000e17d  movups  xmmword ptr [rbp+1D0h+TimeZoneInformation.DaylightName+28h], xmm0
0x18000e181  movups  xmm0, xmmword ptr [rdi+290h]
0x18000e188  movups  xmmword ptr [rbp+1D0h+TimeZoneInformation.DaylightName+38h], xmm1
0x18000e18c  movups  xmm1, xmmword ptr [rdi+2A0h]
0x18000e193  movups  xmmword ptr [rbp+1D0h+TimeZoneInformation.DaylightDate.wHour], xmm0
0x18000e197  movups  xmm0, xmmword ptr [rdi+2B0h]
0x18000e19e  movups  [rbp+1D0h+var_1A0], xmm1
0x18000e1a2  movups  xmm1, xmmword ptr [rdi+2C0h]
0x18000e1a9  movups  [rbp+1D0h+var_190], xmm0
0x18000e1ad  movups  xmm0, xmmword ptr [rdi+2D0h]
0x18000e1b4  movups  [rbp+1D0h+var_180], xmm1
0x18000e1b8  movups  [rbp+1D0h+var_170], xmm0
0x18000e1bc  call    cs:__imp_TbUpdateCEvent
0x18000e1c2  mov     rcx, [rdi+1A0h]
0x18000e1c9  lea     r8, [rsp+2D0h+UniversalTime]
0x18000e1ce  lea     rdx, [rsp+2D0h+var_280]
0x18000e1d3  mov     qword ptr [rsp+2D0h+var_280.wYear], 0
0x18000e1dc  mov     qword ptr [rsp+2D0h+UniversalTime.wYear], 0
0x18000e1e5  call    cs:__imp_TbQueryCEventTriggerTime
0x18000e1eb  test    eax, eax
0x18000e1ed  js      short loc_18000E262
0x18000e1ef  mov     rax, qword ptr [rsp+2D0h+var_280.wYear]
0x18000e1f4  lea     rbx, [rdi+168h]
0x18000e1fb  add     rdi, 138h
0x18000e202  mov     rdx, rdi; lpSystemTime
0x18000e205  lea     r14, [rdi+10h]
0x18000e209  mov     rcx, r14; lpFileTime
0x18000e20c  mov     [r14], rax
0x18000e20f  call    cs:__imp_FileTimeToSystemTime
0x18000e215  test    eax, eax
0x18000e217  jz      short loc_18000E230
0x18000e219  mov     eax, [rdi+14h]
0x18000e21c  mov     [rdi+1Ch], eax
0x18000e21f  mov     eax, [r14]
0x18000e222  mov     [rdi+18h], eax
0x18000e225  mov     qword ptr [rdi+20h], 0
0x18000e22d  mov     [rdi+28h], esi
0x18000e230  mov     rax, qword ptr [rsp+2D0h+UniversalTime.wYear]
0x18000e235  lea     rdi, [rbx+10h]
0x18000e239  mov     rcx, rdi; lpFileTime
0x18000e23c  mov     [rdi], rax
0x18000e23f  mov     rdx, rbx; lpSystemTime
0x18000e242  call    cs:__imp_FileTimeToSystemTime
0x18000e248  test    eax, eax
0x18000e24a  jz      short loc_18000E262
0x18000e24c  mov     eax, [rbx+14h]
0x18000e24f  mov     [rbx+1Ch], eax
0x18000e252  mov     eax, [rdi]
0x18000e254  mov     [rbx+18h], eax
0x18000e257  mov     qword ptr [rbx+20h], 0
0x18000e25f  mov     [rbx+28h], esi
0x18000e262  xor     eax, eax
0x18000e264  mov     rcx, [rbp+1D0h+var_30]
0x18000e26b  xor     rcx, rsp; StackCookie
0x18000e26e  call    __security_check_cookie
0x18000e273  mov     rbx, [rsp+2D0h+arg_8]
0x18000e27b  add     rsp, 2B0h
0x18000e282  pop     r15
0x18000e284  pop     r14
0x18000e286  pop     rdi
0x18000e287  pop     rsi
0x18000e288  pop     rbp
0x18000e289  retn
```
