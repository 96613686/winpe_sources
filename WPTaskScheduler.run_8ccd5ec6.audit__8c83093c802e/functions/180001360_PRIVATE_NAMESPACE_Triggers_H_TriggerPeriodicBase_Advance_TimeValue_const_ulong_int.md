# PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::Advance(TimeValue const &,ulong,int)

- ea: `0x180001360`
- end: `0x180001b04`
- name: `?Advance@TriggerPeriodicBase@PRIVATE_NAMESPACE_Triggers_H@@EEAAKAEBVTimeValue@@KH@Z`
- size: `1956`
- prototype: `unsigned int __fastcall(PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *__hidden this, const struct TimeValue *, unsigned int, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001260`
- `0x180001360`
- `0x180001b10`
- `0x180001cd0`
- `0x180005c30`
- `0x18000d8c0`
- `0x18000eef0`
- `0x18001dde0`
- `0x18001fadc`
- `0x18001fcd0`
- `0x180020c30`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000142d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000142d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180001440`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180001440`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180001413`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180001413`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000144e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000144e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180001457`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180001457`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180001424`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180001424`
- `TimeBrokerClient!TbUpdateCEvent` at `0x180001a82`
- `TimeBrokerClient!TbUpdateCEvent` at `0x180001a82`

## pseudocode

```c
__int64 __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::Advance(
        PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *this,
        SYSTEMTIME *a2,
        unsigned int a3,
        int a4)
{
  PTP_TIMER *v4; // rdi
  PTP_TIMER v9; // rdx
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v11; // r15
  SYSTEMTIME *v12; // rdi
  int BrokerNextTriggerTimeUTC; // eax
  int updated; // r13d
  __int128 v15; // xmm1
  __int64 v16; // rax
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  int v20; // ecx
  int v21; // eax
  __int128 v22; // xmm0
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rcx
  SYSTEMTIME v26; // xmm1
  __int64 v27; // rdx
  SYSTEMTIME v28; // xmm0
  __int128 v29; // xmm1
  __int64 v30; // rdi
  __int128 v31; // xmm6
  __int128 v32; // xmm7
  __int128 v33; // xmm8
  __int128 v34; // xmm9
  __int128 v35; // xmm10
  __int128 v36; // xmm11
  __int128 v37; // xmm12
  __int128 v38; // xmm13
  __int128 v39; // xmm14
  __int128 v40; // xmm15
  __int128 v41; // xmm0
  __int64 v42; // rdx
  SYSTEMTIME v43; // xmm0
  __int64 v44; // rdx
  unsigned int v45; // r15d
  TimeValue *v46; // rcx
  SYSTEMTIME v47; // xmm0
  __int128 v48; // xmm1
  bool v49; // zf
  __int128 v50; // xmm0
  __int128 v51; // xmm2
  __int128 v52; // xmm3
  __int128 v53; // xmm4
  __int128 v54; // xmm5
  __int128 v55; // xmm6
  __int128 v56; // xmm7
  __int128 v57; // xmm8
  __int128 v58; // xmm9
  __int128 v59; // xmm10
  __int128 v60; // xmm11
  SYSTEMTIME v61; // xmm12
  SYSTEMTIME v62; // xmm13
  __int128 v63; // xmm14
  int v64; // eax
  int v66; // [rsp+28h] [rbp-E0h]
  __int128 v67; // [rsp+38h] [rbp-D0h] BYREF
  __int128 v68; // [rsp+48h] [rbp-C0h]
  __int128 v69; // [rsp+58h] [rbp-B0h]
  __int128 v70; // [rsp+68h] [rbp-A0h]
  __int128 v71; // [rsp+78h] [rbp-90h]
  __int128 v72; // [rsp+88h] [rbp-80h]
  __int128 v73; // [rsp+98h] [rbp-70h]
  __int128 v74; // [rsp+A8h] [rbp-60h]
  __int128 v75; // [rsp+B8h] [rbp-50h]
  __int128 v76; // [rsp+C8h] [rbp-40h]
  __int128 v77; // [rsp+D8h] [rbp-30h]
  __int128 v78; // [rsp+E8h] [rbp-20h]
  SYSTEMTIME v79; // [rsp+F8h] [rbp-10h]
  SYSTEMTIME v80; // [rsp+108h] [rbp+0h]
  __int128 v81; // [rsp+118h] [rbp+10h]
  __int64 v82; // [rsp+128h] [rbp+20h]
  __int128 v83; // [rsp+138h] [rbp+30h]
  SYSTEMTIME SystemTime; // [rsp+148h] [rbp+40h] BYREF
  __int64 v85; // [rsp+158h] [rbp+50h]
  __int64 v86; // [rsp+160h] [rbp+58h]
  int v87; // [rsp+168h] [rbp+60h]
  int v88; // [rsp+16Ch] [rbp+64h]
  int v89; // [rsp+170h] [rbp+68h]
  SYSTEMTIME v90; // [rsp+178h] [rbp+70h] BYREF
  __int128 v91; // [rsp+188h] [rbp+80h]
  int v92; // [rsp+198h] [rbp+90h]
  int v93; // [rsp+19Ch] [rbp+94h]
  int v94; // [rsp+1A0h] [rbp+98h]
  int v95; // [rsp+1A4h] [rbp+9Ch]
  SYSTEMTIME v96; // [rsp+1A8h] [rbp+A0h] BYREF
  SYSTEMTIME v97; // [rsp+1B8h] [rbp+B0h] BYREF
  TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+1C8h] [rbp+C0h] BYREF
  SYSTEMTIME v99; // [rsp+278h] [rbp+170h]
  __int128 v100; // [rsp+288h] [rbp+180h]
  int v101; // [rsp+298h] [rbp+190h]
  int v102; // [rsp+29Ch] [rbp+194h]
  TIME_ZONE_INFORMATION v103; // [rsp+2D8h] [rbp+1D0h] BYREF
  __int128 v104; // [rsp+3B8h] [rbp+2B0h]

  v4 = (PTP_TIMER *)((char *)this + 440);
  if ( *((_DWORD *)this + 28) || (v66 = 0, *v4) )
  {
    v9 = *v4;
    *((_DWORD *)this + 28) = 0;
    if ( v9 )
    {
      ThreadpoolWork = CreateThreadpoolWork(CloseThreadpoolWorker, v9, &ThreadpoolCallBackEnvironment);
      v11 = ThreadpoolWork;
      if ( ThreadpoolWork )
      {
        SubmitThreadpoolWork(ThreadpoolWork);
        CloseThreadpoolWork(v11);
      }
      else
      {
        SetThreadpoolTimer(*v4, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(*v4, 1);
        CloseThreadpoolTimer(*v4);
      }
      *v4 = 0;
    }
    if ( !a3 )
      goto LABEL_47;
    --a3;
    v66 = 1;
  }
  if ( !a3 )
    goto LABEL_47;
  v12 = (SYSTEMTIME *)((char *)this + 216);
  if ( !a4 )
  {
    if ( a3 == -1 )
    {
      v42 = *((_QWORD *)this + 24);
      *v12 = *a2;
      *(SYSTEMTIME *)((char *)this + 232) = a2[1];
      *(SYSTEMTIME *)((char *)this + 248) = a2[2];
      TimeValue::AdvanceNs100((SYSTEMTIME *)((char *)this + 216), v42, 0);
      TimeValue::ChompMs((PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *)((char *)this + 216));
      goto LABEL_47;
    }
    v43 = *v12;
    v44 = *((_QWORD *)this + 25);
    v85 = *((_QWORD *)this + 29);
    v45 = a3;
    v86 = *((_QWORD *)this + 30);
    v87 = *((_DWORD *)this + 62);
    v88 = *((_DWORD *)this + 63);
    SystemTime = v43;
    v89 = 1;
    TimeValue::AdvanceNs100(&SystemTime, -v44, 0);
    TimeValue::ChompMs((TimeValue *)&SystemTime);
    if ( (unsigned int)operator<=(&SystemTime, a2) )
    {
      v46 = (PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *)((char *)this + 216);
      if ( *((_DWORD *)this + 52) == 1 )
      {
        if ( (unsigned int)operator<(v46, a2) )
          v45 = a3 + (*(_QWORD *)&a2[1].wHour - *((_QWORD *)this + 30)) / *((__int64 *)this + 24);
      }
      else
      {
        *v12 = *a2;
        *(SYSTEMTIME *)((char *)this + 232) = a2[1];
        *(SYSTEMTIME *)((char *)this + 248) = a2[2];
        TimeValue::ChompMs(v46);
      }
    }
    TimeValue::AdvanceNs100((SYSTEMTIME *)((char *)this + 216), *((_QWORD *)this + 24) * v45, 0);
    v47 = *v12;
    v91 = *(_OWORD *)((char *)this + 232);
    v92 = *((_DWORD *)this + 62);
    v93 = *((_DWORD *)this + 63);
    v90 = v47;
    v94 = 1;
    if ( *((_DWORD *)this + 53) )
      TimeValue::AdvanceNs100(&v90, -*((_QWORD *)this + 25), 0);
    TimeInfo::TimeInfo(&v103);
    if ( (*(_BYTE *)(*((_QWORD *)this + 22) + 44LL) & 8) != 0 )
      TimeInfo::SetUTC(&v103, (const struct TimeValue *)&v90);
    else
      TimeInfo::SetLocal(&v103, (const struct TimeValue *)&v90);
    v48 = *((_OWORD *)this + 32);
    v49 = *((_DWORD *)this + 53) == 0;
    v50 = *((_OWORD *)this + 31);
    v51 = *((_OWORD *)this + 33);
    v82 = *((_QWORD *)this + 92);
    v52 = *((_OWORD *)this + 34);
    v53 = *((_OWORD *)this + 35);
    v54 = *((_OWORD *)this + 36);
    v55 = *((_OWORD *)this + 37);
    v56 = *((_OWORD *)this + 38);
    v57 = *((_OWORD *)this + 39);
    v58 = *((_OWORD *)this + 40);
    v59 = *((_OWORD *)this + 41);
    v60 = *((_OWORD *)this + 42);
    v61 = (SYSTEMTIME)*((_OWORD *)this + 43);
    v62 = (SYSTEMTIME)*((_OWORD *)this + 44);
    v63 = *((_OWORD *)this + 45);
    *(_OWORD *)&TimeZoneInformation.StandardName[6] = v48;
    v64 = HIDWORD(v48);
    *(_OWORD *)&TimeZoneInformation.Bias = v50;
    if ( !v49 )
      v64 = 1;
    *(_OWORD *)&TimeZoneInformation.StandardName[2] = v104;
    *(_DWORD *)&TimeZoneInformation.StandardName[12] = v64;
    v68 = *(_OWORD *)&TimeZoneInformation.StandardName[6];
    v67 = *(_OWORD *)&TimeZoneInformation.Bias;
    v69 = v51;
    v70 = v52;
    v71 = v53;
    v72 = v54;
    v73 = v55;
    v74 = v56;
    v75 = v57;
    v76 = v58;
    v77 = v59;
    v78 = v60;
    v79 = v61;
    v80 = v62;
    v81 = v63;
    goto LABEL_44;
  }
  BrokerNextTriggerTimeUTC = PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::GetBrokerNextTriggerTimeUTC(
                               this,
                               (PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *)((char *)this + 312),
                               (PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *)((char *)this + 360));
  updated = BrokerNextTriggerTimeUTC;
  if ( *((_DWORD *)this + 52) != 1 )
  {
    if ( BrokerNextTriggerTimeUTC < 0 )
    {
      *((_DWORD *)this + 88) = 0;
      *((_DWORD *)this + 100) = 0;
      *((_DWORD *)this + 64) = 0;
LABEL_46:
      a3 = v66;
      goto LABEL_47;
    }
    v27 = *((_QWORD *)this + 24);
    *v12 = *a2;
    *(SYSTEMTIME *)((char *)this + 232) = a2[1];
    *(SYSTEMTIME *)((char *)this + 248) = a2[2];
    TimeValue::AdvanceNs100((SYSTEMTIME *)((char *)this + 216), v27, 0);
    TimeValue::ChompMs((PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *)((char *)this + 216));
    v28 = *v12;
    v29 = *((_OWORD *)this + 32);
    v30 = *((_QWORD *)this + 92);
    v31 = *((_OWORD *)this + 33);
    v85 = *((_QWORD *)this + 29);
    v32 = *((_OWORD *)this + 34);
    v86 = *((_QWORD *)this + 30);
    v33 = *((_OWORD *)this + 35);
    v87 = *((_DWORD *)this + 62);
    v34 = *((_OWORD *)this + 36);
    v88 = *((_DWORD *)this + 63);
    v35 = *((_OWORD *)this + 37);
    v89 = 1;
    v36 = *((_OWORD *)this + 38);
    v37 = *((_OWORD *)this + 39);
    v38 = *((_OWORD *)this + 40);
    v39 = *((_OWORD *)this + 41);
    v40 = *((_OWORD *)this + 42);
    SystemTime = v28;
    v41 = *((_OWORD *)this + 31);
    *(_OWORD *)&TimeZoneInformation.StandardName[6] = v29;
    *(_OWORD *)&TimeZoneInformation.Bias = v41;
    v97 = (SYSTEMTIME)*((_OWORD *)this + 43);
    v96 = (SYSTEMTIME)*((_OWORD *)this + 44);
    v83 = *((_OWORD *)this + 45);
    TimeInfo::TimeInfo(&v103);
    if ( *((_DWORD *)this + 53) )
    {
      TimeValue::AdvanceNs100(&SystemTime, -*((_QWORD *)this + 25), 0);
      *(_DWORD *)&TimeZoneInformation.StandardName[12] = 1;
    }
    if ( (*(_BYTE *)(*((_QWORD *)this + 22) + 44LL) & 8) != 0 )
      TimeInfo::SetUTC(&v103, (const struct TimeValue *)&SystemTime);
    else
      TimeInfo::SetLocal(&v103, (const struct TimeValue *)&SystemTime);
    *(_OWORD *)&TimeZoneInformation.StandardName[2] = v104;
    v82 = v30;
    v68 = *(_OWORD *)&TimeZoneInformation.StandardName[6];
    v67 = *(_OWORD *)&TimeZoneInformation.Bias;
    v79 = v97;
    v69 = v31;
    v81 = v83;
    v70 = v32;
    v71 = v33;
    v72 = v34;
    v73 = v35;
    v74 = v36;
    v75 = v37;
    v76 = v38;
    v77 = v39;
    v78 = v40;
    v80 = v96;
LABEL_44:
    updated = TbUpdateCEvent(*((_QWORD *)this + 52), &v67);
    goto LABEL_45;
  }
  if ( *((__int64 *)this + 25) <= 0 )
  {
    v18 = *(_OWORD *)((char *)this + 376);
    *v12 = *(SYSTEMTIME *)((char *)this + 360);
    v19 = *(_OWORD *)((char *)this + 392);
    *(_OWORD *)((char *)this + 232) = v18;
    *(_OWORD *)((char *)this + 248) = v19;
  }
  else
  {
    v15 = *(_OWORD *)((char *)this + 328);
    v16 = (*((_QWORD *)this + 48) - *((_QWORD *)this + 42)) / 2LL;
    *v12 = *(SYSTEMTIME *)((char *)this + 312);
    v17 = *(_OWORD *)((char *)this + 344);
    *(_OWORD *)((char *)this + 232) = v15;
    *(_OWORD *)((char *)this + 248) = v17;
    TimeValue::AdvanceNs100((SYSTEMTIME *)((char *)this + 216), v16, 0);
  }
  if ( (*(_BYTE *)(*((_QWORD *)this + 22) + 44LL) & 8) == 0 )
  {
    TimeInfo::TimeInfo(&TimeZoneInformation);
    TimeInfo::SetUTC(&TimeZoneInformation, (PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *)((char *)this + 216));
    v20 = v102;
    v91 = v100;
    v21 = v101;
    *v12 = v99;
    *((_DWORD *)this + 62) = v21;
    v22 = v91;
    v23 = v95;
    *((_DWORD *)this + 63) = v20;
    *(_OWORD *)((char *)this + 232) = v22;
    *((_DWORD *)this + 64) = 1;
    *((_DWORD *)this + 65) = v23;
  }
  if ( (unsigned int)operator<=((char *)this + 216, a2) )
  {
    v26 = *v12;
    v97 = *a2;
    v96 = v26;
    if ( (byte_180030D01 & 0x10) != 0 )
      McTemplateU0yy_EventWriteTransfer(v25, v24, &v97, &v96);
  }
LABEL_45:
  if ( updated < 0 )
    goto LABEL_46;
LABEL_47:
  *((_DWORD *)this + 46) = 0;
  return a3;
}

```

## disassembly

```asm
0x180001360  mov     rax, rsp
0x180001363  mov     [rax+20h], rbx
0x180001367  push    rbp
0x180001368  push    rsi
0x180001369  push    rdi
0x18000136a  push    r12
0x18000136c  push    r13
0x18000136e  push    r14
0x180001370  push    r15
0x180001372  lea     rbp, [rax-3C8h]
0x180001379  sub     rsp, 490h
0x180001380  movaps  xmmword ptr [rax-48h], xmm6
0x180001384  movaps  xmmword ptr [rax-58h], xmm7
0x180001388  movaps  xmmword ptr [rax-68h], xmm8
0x18000138d  movaps  xmmword ptr [rax-78h], xmm9
0x180001392  movaps  xmmword ptr [rax-88h], xmm10
0x18000139a  movaps  xmmword ptr [rax-98h], xmm11
0x1800013a2  movaps  xmmword ptr [rax-0A8h], xmm12
0x1800013aa  movaps  xmmword ptr [rax-0B8h], xmm13
0x1800013b2  movaps  xmmword ptr [rax-0C8h], xmm14
0x1800013ba  movaps  xmmword ptr [rax-0D8h], xmm15
0x1800013c2  mov     rax, cs:__security_cookie
0x1800013c9  xor     rax, rsp
0x1800013cc  mov     [rbp+3C0h+var_E0], rax
0x1800013d3  xor     r13d, r13d
0x1800013d6  lea     rdi, [rcx+1B8h]
0x1800013dd  mov     r12d, r9d
0x1800013e0  mov     r14d, r8d
0x1800013e3  mov     rsi, rdx
0x1800013e6  mov     rbx, rcx
0x1800013e9  cmp     [rcx+70h], r13d
0x1800013ed  jnz     short loc_1800013F9
0x1800013ef  mov     [rsp+4C0h+var_4A0], r13d
0x1800013f4  cmp     [rdi], r13
0x1800013f7  jz      short loc_180001474
0x1800013f9  mov     rdx, [rdi]; pv
0x1800013fc  mov     [rcx+70h], r13d
0x180001400  test    rdx, rdx
0x180001403  jz      short loc_180001460
0x180001405  lea     r8, ?ThreadpoolCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x18000140c  lea     rcx, CloseThreadpoolWorker; pfnwk
0x180001413  call    cs:__imp_CreateThreadpoolWork
0x180001419  mov     r15, rax
0x18000141c  test    rax, rax
0x18000141f  jz      short loc_180001435
0x180001421  mov     rcx, rax; pwk
0x180001424  call    cs:__imp_SubmitThreadpoolWork
0x18000142a  mov     rcx, r15; pwk
0x18000142d  call    cs:__imp_CloseThreadpoolWork
0x180001433  jmp     short loc_18000145D
0x180001435  mov     rcx, [rdi]; pti
0x180001438  xor     r9d, r9d; msWindowLength
0x18000143b  xor     r8d, r8d; msPeriod
0x18000143e  xor     edx, edx; pftDueTime
0x180001440  call    cs:__imp_SetThreadpoolTimer
0x180001446  mov     rcx, [rdi]; pti
0x180001449  mov     edx, 1; fCancelPendingCallbacks
0x18000144e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180001454  mov     rcx, [rdi]; pti
0x180001457  call    cs:__imp_CloseThreadpoolTimer
0x18000145d  mov     [rdi], r13
0x180001460  test    r14d, r14d
0x180001463  jz      loc_180001A95
0x180001469  dec     r14d
0x18000146c  mov     [rsp+4C0h+var_4A0], 1
0x180001474  test    r14d, r14d
0x180001477  jz      loc_180001A95
0x18000147d  lea     rdi, [rbx+0D8h]
0x180001484  test    r12d, r12d
0x180001487  jz      loc_1800017E4
0x18000148d  lea     r15, [rbx+168h]
0x180001494  mov     rcx, rbx; this
0x180001497  lea     r12, [rbx+138h]
0x18000149e  mov     r8, r15; struct TimeValue *
0x1800014a1  mov     rdx, r12; struct TimeValue *
0x1800014a4  call    ?GetBrokerNextTriggerTimeUTC@TriggerPeriodicBase@PRIVATE_NAMESPACE_Triggers_H@@AEAAJAEAVTimeValue@@0@Z; PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::GetBrokerNextTriggerTimeUTC(TimeValue &,TimeValue &)
0x1800014a9  cmp     dword ptr [rbx+0D0h], 1
0x1800014b0  mov     r13d, eax
0x1800014b3  jnz     loc_1800015E6
0x1800014b9  cmp     qword ptr [rbx+0C8h], 0
0x1800014c1  jle     short loc_180001504
0x1800014c3  mov     rax, [r15+18h]
0x1800014c7  mov     ecx, 2
0x1800014cc  sub     rax, [rbx+150h]
0x1800014d3  xor     r8d, r8d; int
0x1800014d6  movups  xmm0, xmmword ptr [r12]
0x1800014db  cqo
0x1800014dd  movups  xmm1, xmmword ptr [r12+10h]
0x1800014e3  idiv    rcx
0x1800014e6  movups  xmmword ptr [rdi], xmm0
0x1800014e9  mov     rdx, rax; __int64
0x1800014ec  mov     rcx, rdi; lpSystemTime
0x1800014ef  movups  xmm0, xmmword ptr [r12+20h]
0x1800014f5  movups  xmmword ptr [rdi+10h], xmm1
0x1800014f9  movups  xmmword ptr [rdi+20h], xmm0
0x1800014fd  call    ?AdvanceNs100@TimeValue@@QEAAX_JH@Z; TimeValue::AdvanceNs100(__int64,int)
0x180001502  jmp     short loc_18000151D
0x180001504  movups  xmm0, xmmword ptr [r15]
0x180001508  movups  xmm1, xmmword ptr [r15+10h]
0x18000150d  movups  xmmword ptr [rdi], xmm0
0x180001510  movups  xmm0, xmmword ptr [r15+20h]
0x180001515  movups  xmmword ptr [rdi+10h], xmm1
0x180001519  movups  xmmword ptr [rdi+20h], xmm0
0x18000151d  mov     rax, [rbx+0B0h]
0x180001524  test    byte ptr [rax+2Ch], 8
0x180001528  jnz     short loc_180001598
0x18000152a  lea     rcx, [rbp+3C0h+TimeZoneInformation]; lpTimeZoneInformation
0x180001531  call    ??0TimeInfo@@QEAA@XZ; TimeInfo::TimeInfo(void)
0x180001536  mov     rdx, rdi; struct TimeValue *
0x180001539  lea     rcx, [rbp+3C0h+TimeZoneInformation]; lpTimeZoneInformation
0x180001540  call    ?SetUTC@TimeInfo@@QEAAXAEBVTimeValue@@@Z; TimeInfo::SetUTC(TimeValue const &)
0x180001545  mov     rax, qword ptr [rbp+3C0h+var_240]
0x18000154c  movaps  xmm0, [rbp+3C0h+var_250]
0x180001553  mov     ecx, [rbp+3C0h+var_22C]
0x180001559  mov     qword ptr [rbp+3C0h+var_340], rax
0x180001560  mov     rax, qword ptr [rbp+3C0h+var_240+8]
0x180001567  mov     qword ptr [rbp+3C0h+var_340+8], rax
0x18000156e  mov     eax, [rbp+3C0h+var_230]
0x180001574  movups  xmmword ptr [rdi], xmm0
0x180001577  mov     [rdi+20h], eax
0x18000157a  movups  xmm0, [rbp+3C0h+var_340]
0x180001581  mov     eax, [rbp+3C0h+var_324]
0x180001587  mov     [rdi+24h], ecx
0x18000158a  movups  xmmword ptr [rdi+10h], xmm0
0x18000158e  mov     dword ptr [rdi+28h], 1
0x180001595  mov     [rdi+2Ch], eax
0x180001598  mov     rdx, rsi
0x18000159b  mov     rcx, rdi
0x18000159e  call    ??N@YAHAEBVTimeValue@@0@Z; operator<=(TimeValue const &,TimeValue const &)
0x1800015a3  test    eax, eax
0x1800015a5  jz      loc_180001A8B
0x1800015ab  test    cs:byte_180030D01, 10h
0x1800015b2  movups  xmm0, xmmword ptr [rsi]
0x1800015b5  movups  xmm1, xmmword ptr [rdi]
0x1800015b8  movdqu  [rbp+3C0h+var_310], xmm0
0x1800015c0  movdqu  [rbp+3C0h+var_320], xmm1
0x1800015c8  jz      loc_180001A8B
0x1800015ce  lea     r9, [rbp+3C0h+var_320]
0x1800015d5  lea     r8, [rbp+3C0h+var_310]
0x1800015dc  call    McTemplateU0yy_EventWriteTransfer
0x1800015e1  jmp     loc_180001A8B
0x1800015e6  test    eax, eax
0x1800015e8  js      loc_1800017C4
0x1800015ee  movups  xmm0, xmmword ptr [rsi]
0x1800015f1  mov     rdx, [rbx+0C0h]; __int64
0x1800015f8  xor     r8d, r8d; int
0x1800015fb  mov     rcx, rdi; lpSystemTime
0x1800015fe  movups  xmmword ptr [rdi], xmm0
0x180001601  movups  xmm1, xmmword ptr [rsi+10h]
0x180001605  movups  xmmword ptr [rdi+10h], xmm1
0x180001609  movups  xmm0, xmmword ptr [rsi+20h]
0x18000160d  movups  xmmword ptr [rdi+20h], xmm0
0x180001611  call    ?AdvanceNs100@TimeValue@@QEAAX_JH@Z; TimeValue::AdvanceNs100(__int64,int)
0x180001616  mov     rcx, rdi; this
0x180001619  call    ?ChompMs@TimeValue@@QEAAXXZ; TimeValue::ChompMs(void)
0x18000161e  movups  xmm0, xmmword ptr [rdi]
0x180001621  mov     rax, [rbx+0E8h]
0x180001628  lea     rcx, [rbp+3C0h+var_1F0]; lpTimeZoneInformation
0x18000162f  movups  xmm1, xmmword ptr [rbx+200h]
0x180001636  mov     rdi, [rbx+2E0h]
0x18000163d  mov     esi, 1
0x180001642  movups  xmm6, xmmword ptr [rbx+210h]
0x180001649  mov     [rbp+3C0h+var_370], rax
0x18000164d  mov     rax, [rbx+0F0h]
0x180001654  movups  xmm7, xmmword ptr [rbx+220h]
0x18000165b  mov     [rbp+3C0h+var_368], rax
0x18000165f  mov     eax, [rbx+0F8h]
0x180001665  movups  xmm8, xmmword ptr [rbx+230h]
0x18000166d  mov     [rbp+3C0h+var_360], eax
0x180001670  mov     eax, [rbx+0FCh]
0x180001676  movups  xmm9, xmmword ptr [rbx+240h]
0x18000167e  mov     [rbp+3C0h+var_35C], eax
0x180001681  movups  xmm10, xmmword ptr [rbx+250h]
0x180001689  mov     [rbp+3C0h+var_358], esi
0x18000168c  movups  xmm11, xmmword ptr [rbx+260h]
0x180001694  movups  xmm12, xmmword ptr [rbx+270h]
0x18000169c  movups  xmm13, xmmword ptr [rbx+280h]
0x1800016a4  movups  xmm14, xmmword ptr [rbx+290h]
0x1800016ac  movups  xmm15, xmmword ptr [rbx+2A0h]
0x1800016b4  movdqu  xmmword ptr [rbp+3C0h+SystemTime.wYear], xmm0
0x1800016b9  movups  xmm0, xmmword ptr [rbx+1F0h]
0x1800016c0  movups  xmmword ptr [rbp+3C0h+TimeZoneInformation.StandardName+0Ch], xmm1
0x1800016c7  movups  xmmword ptr [rbp+3C0h+TimeZoneInformation.Bias], xmm0
0x1800016ce  movups  xmm0, xmmword ptr [rbx+2B0h]
0x1800016d5  movups  [rbp+3C0h+var_310], xmm0
0x1800016dc  movups  xmm0, xmmword ptr [rbx+2C0h]
0x1800016e3  movups  [rbp+3C0h+var_320], xmm0
0x1800016ea  movups  xmm0, xmmword ptr [rbx+2D0h]
0x1800016f1  movups  [rbp+3C0h+var_390], xmm0
0x1800016f5  call    ??0TimeInfo@@QEAA@XZ; TimeInfo::TimeInfo(void)
0x1800016fa  cmp     dword ptr [rbx+0D4h], 0
0x180001701  jz      short loc_18000171F
0x180001703  mov     rdx, [rbx+0C8h]
0x18000170a  lea     rcx, [rbp+3C0h+SystemTime]; lpSystemTime
0x18000170e  neg     rdx; __int64
0x180001711  xor     r8d, r8d; int
0x180001714  call    ?AdvanceNs100@TimeValue@@QEAAX_JH@Z; TimeValue::AdvanceNs100(__int64,int)
0x180001719  mov     dword ptr [rbp+3C0h+TimeZoneInformation.StandardName+18h], esi
0x18000171f  mov     rax, [rbx+0B0h]
0x180001726  lea     rdx, [rbp+3C0h+SystemTime]; struct TimeValue *
0x18000172a  lea     rcx, [rbp+3C0h+var_1F0]; lpTimeZoneInformation
0x180001731  test    byte ptr [rax+2Ch], 8
0x180001735  jz      short loc_18000173E
0x180001737  call    ?SetUTC@TimeInfo@@QEAAXAEBVTimeValue@@@Z; TimeInfo::SetUTC(TimeValue const &)
0x18000173c  jmp     short loc_180001743
0x18000173e  call    ?SetLocal@TimeInfo@@QEAAXAEBVTimeValue@@@Z; TimeInfo::SetLocal(TimeValue const &)
0x180001743  movaps  xmm0, [rbp+3C0h+var_110]
0x18000174a  movdqu  xmmword ptr [rbp+3C0h+TimeZoneInformation.StandardName+4], xmm0
0x180001752  mov     [rbp+3C0h+var_3A0], rdi
0x180001756  movaps  xmm0, xmmword ptr [rbp+3C0h+TimeZoneInformation.StandardName+0Ch]
0x18000175d  movaps  xmm1, xmmword ptr [rbp+3C0h+TimeZoneInformation.Bias]
0x180001764  movups  [rsp+4C0h+var_488+8], xmm0
0x180001769  movups  xmm0, [rbp+3C0h+var_310]
0x180001770  movups  [rsp+4C0h+var_498+8], xmm1
0x180001775  movups  xmm1, [rbp+3C0h+var_320]
0x18000177c  movups  [rbp+3C0h+var_3D0], xmm0
0x180001780  movups  xmm0, [rbp+3C0h+var_390]
0x180001784  movups  [rsp+4C0h+var_478+8], xmm6
0x180001789  movups  [rbp+3C0h+var_3B0], xmm0
0x18000178d  movups  [rsp+4C0h+var_468+8], xmm7
0x180001792  movups  xmmword ptr [rsp+4C0h+var_458+8], xmm8
0x180001798  movups  [rbp+3C0h+var_440], xmm9
0x18000179d  movups  [rbp+3C0h+var_430], xmm10
0x1800017a2  movups  [rbp+3C0h+var_420], xmm11
0x1800017a7  movups  [rbp+3C0h+var_410], xmm12
0x1800017ac  movups  [rbp+3C0h+var_400], xmm13
0x1800017b1  movups  [rbp+3C0h+var_3F0], xmm14
0x1800017b6  movups  [rbp+3C0h+var_3E0], xmm15
0x1800017bb  movups  [rbp+3C0h+var_3C0], xmm1
0x1800017bf  jmp     loc_180001A76
0x1800017c4  mov     dword ptr [rbx+160h], 0
0x1800017ce  mov     dword ptr [rbx+190h], 0
0x1800017d8  mov     dword ptr [rdi+28h], 0
0x1800017df  jmp     loc_180001A90
0x1800017e4  xor     r8d, r8d; int
0x1800017e7  cmp     r14d, 0FFFFFFFFh
0x1800017eb  jnz     short loc_18000181F
0x1800017ed  movups  xmm0, xmmword ptr [rsi]
0x1800017f0  mov     rdx, [rbx+0C0h]; __int64
0x1800017f7  mov     rcx, rdi; lpSystemTime
0x1800017fa  movups  xmmword ptr [rdi], xmm0
0x1800017fd  movups  xmm1, xmmword ptr [rsi+10h]
0x180001801  movups  xmmword ptr [rdi+10h], xmm1
0x180001805  movups  xmm0, xmmword ptr [rsi+20h]
0x180001809  movups  xmmword ptr [rdi+20h], xmm0
0x18000180d  call    ?AdvanceNs100@TimeValue@@QEAAX_JH@Z; TimeValue::AdvanceNs100(__int64,int)
0x180001812  mov     rcx, rdi; this
0x180001815  call    ?ChompMs@TimeValue@@QEAAXXZ; TimeValue::ChompMs(void)
0x18000181a  jmp     loc_180001A95
0x18000181f  mov     rax, [rdi+10h]
0x180001823  lea     rcx, [rbp+3C0h+SystemTime]; lpSystemTime
0x180001827  movups  xmm0, xmmword ptr [rdi]
0x18000182a  mov     rdx, [rbx+0C8h]
0x180001831  mov     r12d, 1
0x180001837  mov     [rbp+3C0h+var_370], rax
0x18000183b  neg     rdx; __int64
0x18000183e  mov     rax, [rdi+18h]
0x180001842  mov     r15d, r14d
0x180001845  mov     [rbp+3C0h+var_368], rax
0x180001849  mov     eax, [rdi+20h]
0x18000184c  mov     [rbp+3C0h+var_360], eax
0x18000184f  mov     eax, [rdi+24h]
0x180001852  mov     [rbp+3C0h+var_35C], eax
0x180001855  movdqu  xmmword ptr [rbp+3C0h+SystemTime.wYear], xmm0
0x18000185a  mov     [rbp+3C0h+var_358], r12d
0x18000185e  call    ?AdvanceNs100@TimeValue@@QEAAX_JH@Z; TimeValue::AdvanceNs100(__int64,int)
0x180001863  lea     rcx, [rbp+3C0h+SystemTime]; this
0x180001867  call    ?ChompMs@TimeValue@@QEAAXXZ; TimeValue::ChompMs(void)
0x18000186c  mov     rdx, rsi
0x18000186f  lea     rcx, [rbp+3C0h+SystemTime]
0x180001873  call    ??N@YAHAEBVTimeValue@@0@Z; operator<=(TimeValue const &,TimeValue const &)
0x180001878  test    eax, eax
0x18000187a  jz      short loc_1800018C9
0x18000187c  mov     rcx, rdi; this
0x18000187f  cmp     [rbx+0D0h], r12d
0x180001886  jnz     short loc_1800018AE
0x180001888  mov     rdx, rsi
0x18000188b  call    ??M@YAHAEBVTimeValue@@0@Z; operator<(TimeValue const &,TimeValue const &)
0x180001890  test    eax, eax
0x180001892  jz      short loc_1800018C9
0x180001894  mov     rax, [rsi+18h]
0x180001898  sub     rax, [rbx+0F0h]
0x18000189f  cqo
0x1800018a1  idiv    qword ptr [rbx+0C0h]
0x1800018a8  lea     r15d, [r14+rax]
0x1800018ac  jmp     short loc_1800018C9
0x1800018ae  movups  xmm0, xmmword ptr [rsi]
0x1800018b1  movups  xmmword ptr [rdi], xmm0
0x1800018b4  movups  xmm1, xmmword ptr [rsi+10h]
0x1800018b8  movups  xmmword ptr [rdi+10h], xmm1
0x1800018bc  movups  xmm0, xmmword ptr [rsi+20h]
0x1800018c0  movups  xmmword ptr [rdi+20h], xmm0
0x1800018c4  call    ?ChompMs@TimeValue@@QEAAXXZ; TimeValue::ChompMs(void)
0x1800018c9  mov     edx, r15d
0x1800018cc  xor     r8d, r8d; int
0x1800018cf  imul    rdx, [rbx+0C0h]; __int64
0x1800018d7  mov     rcx, rdi; lpSystemTime
0x1800018da  call    ?AdvanceNs100@TimeValue@@QEAAX_JH@Z; TimeValue::AdvanceNs100(__int64,int)
0x1800018df  mov     rax, [rbx+0E8h]
0x1800018e6  movups  xmm0, xmmword ptr [rdi]
  ... truncated ...
```
