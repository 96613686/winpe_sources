# CScheduleMgr::TimeChangeEventCallback(__int64)

- ea: `0x180005440`
- end: `0x180005afe`
- name: `?TimeChangeEventCallback@CScheduleMgr@@AEAAJ_J@Z`
- size: `1726`
- prototype: `__int64 __fastcall(CScheduleMgr *this, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18000db80`

## callees

- `0x1800025b0`
- `0x180005440`
- `0x180005b10`
- `0x180005c30`
- `0x180005d40`
- `0x18000e290`
- `0x18000ea40`
- `0x18000f7cc`
- `0x180017370`
- `0x18001996c`
- `0x1800199c4`
- `0x18001f65c`
- `0x180020bf6`
- `0x180020c30`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005ab8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005ab8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800058e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800058e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800054c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800054c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005755`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005755`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800058d2`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800058d2`

## string_xrefs

- `0x180005a55`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule\WP\TaskScheduler\Parameters`

## pseudocode

```c
__int64 __fastcall CScheduleMgr::TimeChangeEventCallback(CScheduleMgr *this, int a2)
{
  unsigned int v3; // r15d
  __int64 v4; // rdx
  unsigned __int64 v5; // rcx
  __int64 v6; // r8
  unsigned __int64 v7; // rsi
  __int64 v8; // r14
  int v9; // eax
  __int64 v10; // rdx
  __int64 StandardBias; // rcx
  _QWORD *v12; // rbx
  _TIME_ZONE_INFORMATION *v13; // rcx
  __int128 *v14; // rax
  __int64 v15; // rdx
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm6
  __int128 v25; // xmm7
  __int128 v26; // xmm8
  __int128 v27; // xmm9
  __int128 v28; // xmm10
  __int128 v29; // xmm11
  __int128 v30; // xmm12
  __int128 v31; // xmm13
  __int128 v32; // xmm14
  __int128 v33; // xmm15
  __int64 v34; // rcx
  __int64 v35; // r8
  _QWORD *v37; // r8
  __int64 *v38; // r13
  _QWORD *v39; // rdi
  struct _LIST_ENTRY **v40; // rdx
  __int64 v41; // rcx
  __int128 v42; // xmm0
  int v43; // eax
  LSTATUS v44; // eax
  int v45; // eax
  __int64 v46; // rcx
  __int64 *v47; // rax
  __int64 v48; // rcx
  struct _LIST_ENTRY *Flink; // rax
  HKEY phkResult; // [rsp+38h] [rbp-D0h] BYREF
  int v51[2]; // [rsp+48h] [rbp-C0h] BYREF
  struct _LIST_ENTRY v52; // [rsp+50h] [rbp-B8h] BYREF
  _OWORD Buf1_8[11]; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v54; // [rsp+118h] [rbp+10h] BYREF
  __int64 v55; // [rsp+128h] [rbp+20h]
  __int64 v56; // [rsp+130h] [rbp+28h]
  int v57; // [rsp+138h] [rbp+30h]
  int v58; // [rsp+13Ch] [rbp+34h]
  int v59; // [rsp+140h] [rbp+38h]
  _OWORD TimeZoneInformation[5]; // [rsp+148h] [rbp+40h] BYREF
  __int128 TimeZoneInformation_80; // [rsp+198h] [rbp+90h]
  __int128 TimeZoneInformation_96; // [rsp+1A8h] [rbp+A0h]
  __int128 TimeZoneInformation_112; // [rsp+1B8h] [rbp+B0h]
  __int128 TimeZoneInformation_128; // [rsp+1C8h] [rbp+C0h]
  __int128 TimeZoneInformation_144; // [rsp+1D8h] [rbp+D0h]
  __int128 TimeZoneInformation_160; // [rsp+1E8h] [rbp+E0h]
  __int128 v67; // [rsp+1F8h] [rbp+F0h]
  __int64 v68; // [rsp+208h] [rbp+100h]
  __int64 v69; // [rsp+210h] [rbp+108h]
  int v70; // [rsp+218h] [rbp+110h]
  int v71; // [rsp+21Ch] [rbp+114h]
  __int128 v72; // [rsp+228h] [rbp+120h]
  __int64 v73; // [rsp+238h] [rbp+130h]
  __int64 v74; // [rsp+240h] [rbp+138h]
  int v75; // [rsp+248h] [rbp+140h]
  int v76; // [rsp+24Ch] [rbp+144h]
  _BYTE v77[16]; // [rsp+258h] [rbp+150h] BYREF

  v3 = 0;
  EnterCriticalSection(&CriticalSection);
  TimeInfo::TimeInfo((LPTIME_ZONE_INFORMATION)TimeZoneInformation);
  TimeInfo::LogTimeETW((TimeInfo *)TimeZoneInformation);
  v4 = ((unsigned int)(a2 / 10000) * (unsigned __int128)0x624DD2F1A9FBE77uLL) >> 64;
  v5 = (v4 + (((unsigned __int64)(unsigned int)(a2 / 10000) - v4) >> 1)) >> 9;
  v6 = (unsigned int)(a2 / 10000) - 1000 * v5;
  v7 = v5 + (v6 >= 500);
  if ( byte_180030D01 < 0 )
    McTemplateU0i_EventWriteTransfer(v5, TimeChangeProcessingStart, v5 + (v6 >= 500));
  v8 = LODWORD(TimeZoneInformation[0]) - ::TimeZoneInformation.Bias;
  if ( HIDWORD(TimeZoneInformation_160) == 1 )
  {
    v9 = DWORD1(TimeZoneInformation_80);
  }
  else
  {
    v9 = 0;
    if ( HIDWORD(TimeZoneInformation_160) == 2 )
      v9 = DWORD2(TimeZoneInformation_160);
  }
  v10 = (unsigned int)dword_180030B7C;
  if ( dword_180030B7C == 1 )
  {
    StandardBias = (unsigned int)::TimeZoneInformation.StandardBias;
  }
  else
  {
    StandardBias = 0;
    if ( dword_180030B7C == 2 )
      StandardBias = (unsigned int)::TimeZoneInformation.DaylightBias;
  }
  if ( v9 != (_DWORD)StandardBias )
  {
    TimeInfo::DSTBias((TimeInfo *)&::TimeZoneInformation);
    v45 = TimeInfo::DSTBias((TimeInfo *)TimeZoneInformation);
    StandardBias = v45 - (int)v10;
    v8 += StandardBias;
  }
  if ( (byte_180030D03 & 1) != 0 )
    McTemplateU0ii_EventWriteTransfer(StandardBias, v10, v7, v8);
  v12 = (_QWORD *)g_ScheduleMgr;
  v52.Blink = &v52;
  v52.Flink = &v52;
  while ( v12 != (_QWORD *)&g_ScheduleMgr )
  {
    v37 = v12;
    v59 = 1;
    v38 = v12;
    v39 = v12;
    v40 = (struct _LIST_ENTRY **)v12;
    v12 = (_QWORD *)*v12;
    v41 = *((_DWORD *)v37 + 11) & 8;
    if ( (*((_DWORD *)v37 + 11) & 8) != 0 )
    {
      v42 = v72;
      v55 = v73;
      v56 = v74;
      v57 = v75;
      v43 = v76;
    }
    else
    {
      v42 = v67;
      v55 = v68;
      v56 = v69;
      v57 = v70;
      v43 = v71;
    }
    v58 = v43;
    v54 = v42;
    if ( !v39[25] || !v39[27] )
    {
      if ( (byte_180030D04 & 1) != 0 )
      {
        McGenEventWrite_EventWriteTransfer(v41, ErrorNullPointer, v37, 1, v77);
        v40 = (struct _LIST_ENTRY **)v39;
        v37 = v39;
      }
      goto LABEL_31;
    }
    if ( !(_DWORD)v41 || 10000000 * v7 )
    {
      v51[0] = 0;
      if ( (int)CSchedule::TimeTransitionsCallback((CSchedule *)v39, (const struct TimeInfo *)TimeZoneInformation, v51) < 0 )
        goto LABEL_45;
      if ( !v51[0] && *((_DWORD *)v39 + 10) == 4 )
        (*(void (__fastcall **)(_QWORD, __int128 *, unsigned __int64, __int64))(*(_QWORD *)v39[25] + 104LL))(
          v39[25],
          &v54,
          10000000 * v7,
          v8);
      v40 = (struct _LIST_ENTRY **)v39;
      v37 = v39;
    }
    if ( (*((_BYTE *)v39 + 44) & 1) == 0 )
      goto LABEL_31;
    if ( (int)TaskStore::PersistRuntimeData((CScheduleMgr **)qword_180030AC8, (struct _GUID *)v39 + 1, 0) < 0
      && (byte_180030D05 & 0x40) != 0 )
    {
      McTemplateU0j_EventWriteTransfer(v46, PersistScheduleError, v39 + 2);
    }
LABEL_45:
    v40 = (struct _LIST_ENTRY **)v39;
    v37 = v39;
LABEL_31:
    if ( *((_DWORD *)v39 + 66) )
    {
      if ( (*((_BYTE *)v39 + 44) & 4) != 0 )
      {
        v47 = (__int64 *)v38[1];
        v48 = *v38;
        *v47 = *v38;
        *(_QWORD *)(v48 + 8) = v47;
        Flink = v52.Flink;
        *v40 = v52.Flink;
        v38[1] = (__int64)&v52;
        Flink->Blink = (struct _LIST_ENTRY *)v39;
        v52.Flink = (struct _LIST_ENTRY *)v37;
        if ( (*((_BYTE *)v39 + 44) & 1) != 0 )
          TaskStore::Delete((TaskStore *)&v52, (struct _GUID *)v39 + 1);
      }
    }
  }
  v13 = &::TimeZoneInformation;
  v14 = TimeZoneInformation;
  v15 = 2;
  do
  {
    v13 = (_TIME_ZONE_INFORMATION *)((char *)v13 + 128);
    v16 = *v14;
    v17 = v14[1];
    v14 += 8;
    *(_OWORD *)&v13[-1].StandardName[20] = v16;
    v18 = *(v14 - 6);
    *(_OWORD *)&v13[-1].StandardName[28] = v17;
    v19 = *(v14 - 5);
    *(_OWORD *)&v13[-1].StandardDate.wHour = v18;
    v20 = *(v14 - 4);
    *(_OWORD *)&v13[-1].DaylightName[2] = v19;
    v21 = *(v14 - 3);
    *(_OWORD *)&v13[-1].DaylightName[10] = v20;
    v22 = *(v14 - 2);
    *(_OWORD *)&v13[-1].DaylightName[18] = v21;
    v23 = *(v14 - 1);
    *(_OWORD *)&v13[-1].DaylightName[26] = v22;
    *(_OWORD *)&v13[-1].DaylightDate.wDayOfWeek = v23;
    --v15;
  }
  while ( v15 );
  v24 = TimeZoneInformation[0];
  v25 = TimeZoneInformation[1];
  v26 = TimeZoneInformation[2];
  v27 = TimeZoneInformation[3];
  v28 = TimeZoneInformation[4];
  v29 = TimeZoneInformation_80;
  v30 = TimeZoneInformation_96;
  v31 = TimeZoneInformation_112;
  v32 = TimeZoneInformation_128;
  v33 = TimeZoneInformation_144;
  *(_OWORD *)&v13->Bias = *v14;
  Buf1_8[10] = TimeZoneInformation_160;
  Buf1_8[0] = v24;
  Buf1_8[1] = v25;
  Buf1_8[2] = v26;
  Buf1_8[3] = v27;
  Buf1_8[4] = v28;
  Buf1_8[5] = v29;
  Buf1_8[6] = v30;
  Buf1_8[7] = v31;
  Buf1_8[8] = v32;
  Buf1_8[9] = v33;
  if ( memcmp_0(Buf1_8, &g_CurrentTimeZoneInfo, 0xB0u) )
  {
    phkResult = 0;
    *(_OWORD *)&g_CurrentTimeZoneInfo.DaylightDate.wHour = TimeZoneInformation_160;
    *(_OWORD *)&g_CurrentTimeZoneInfo.Bias = v24;
    *(_OWORD *)&g_CurrentTimeZoneInfo.StandardName[6] = v25;
    *(_OWORD *)&g_CurrentTimeZoneInfo.StandardName[14] = v26;
    *(_OWORD *)&g_CurrentTimeZoneInfo.StandardName[22] = v27;
    *(_OWORD *)&g_CurrentTimeZoneInfo.StandardName[30] = v28;
    *(_OWORD *)&g_CurrentTimeZoneInfo.StandardDate.wSecond = v29;
    *(_OWORD *)&g_CurrentTimeZoneInfo.DaylightName[4] = v30;
    *(_OWORD *)&g_CurrentTimeZoneInfo.DaylightName[12] = v31;
    *(_OWORD *)&g_CurrentTimeZoneInfo.DaylightName[20] = v32;
    *(_OWORD *)&g_CurrentTimeZoneInfo.DaylightName[28] = v33;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, g_szTaskSchedulerParametersRegPath, 0, 0x2001Bu, &phkResult) )
    {
      v44 = RegSetKeyValueW(phkResult, 0, L"TimeZoneInfo", 3u, &g_CurrentTimeZoneInfo, 0xB0u);
      v3 = v44;
      if ( v44 > 0 )
        v3 = (unsigned __int16)v44 | 0x80070000;
      RegCloseKey(phkResult);
    }
  }
  if ( byte_180030D01 < 0 )
    McGenEventWrite_EventWriteTransfer(v34, TimeChangeProcessingCompleted, v35, 1, v77);
  LeaveCriticalSection(&CriticalSection);
  CScheduleMgr::DeleteExpired(&v52);
  return v3;
}

```

## disassembly

```asm
0x180005440  mov     r11, rsp
0x180005443  push    rbp
0x180005444  push    r15
0x180005446  lea     rbp, [r11-238h]
0x18000544d  sub     rsp, 328h
0x180005454  mov     rax, cs:__security_cookie
0x18000545b  xor     rax, rsp
0x18000545e  mov     [rbp+230h+var_D0], rax
0x180005465  mov     [r11+8], rbx
0x180005469  lea     rcx, CriticalSection; lpCriticalSection
0x180005470  mov     [r11+18h], rsi
0x180005474  mov     rbx, rdx
0x180005477  mov     [r11-18h], r12
0x18000547b  xor     r15d, r15d
0x18000547e  mov     [r11-28h], r14
0x180005482  movaps  xmmword ptr [r11-38h], xmm6
0x180005487  movaps  xmmword ptr [r11-48h], xmm7
0x18000548c  movaps  xmmword ptr [r11-58h], xmm8
0x180005491  movaps  xmmword ptr [r11-68h], xmm9
0x180005496  movaps  xmmword ptr [r11-78h], xmm10
0x18000549b  movaps  xmmword ptr [r11-88h], xmm11
0x1800054a3  movaps  xmmword ptr [r11-98h], xmm12
0x1800054ab  movaps  xmmword ptr [r11-0A8h], xmm13
0x1800054b3  movaps  xmmword ptr [r11-0B8h], xmm14
0x1800054bb  movaps  xmmword ptr [r11-0C8h], xmm15
0x1800054c3  call    cs:__imp_EnterCriticalSection
0x1800054c9  lea     rcx, [rbp+230h+TimeZoneInformation]; lpTimeZoneInformation
0x1800054cd  call    ??0TimeInfo@@QEAA@XZ; TimeInfo::TimeInfo(void)
0x1800054d2  lea     rcx, [rbp+230h+TimeZoneInformation]; this
0x1800054d6  call    ?LogTimeETW@TimeInfo@@QEBAXXZ; TimeInfo::LogTimeETW(void)
0x1800054db  xor     esi, esi
0x1800054dd  mov     rax, 346DC5D63886594Bh
0x1800054e7  imul    rbx
0x1800054ea  mov     rax, 624DD2F1A9FBE77h
0x1800054f4  sar     rdx, 0Bh
0x1800054f8  mov     r8, rdx
0x1800054fb  shr     r8, 3Fh
0x1800054ff  add     r8, rdx
0x180005502  mov     r8d, r8d
0x180005505  mul     r8
0x180005508  mov     ecx, r8d
0x18000550b  sub     rcx, rdx
0x18000550e  shr     rcx, 1
0x180005511  add     rcx, rdx
0x180005514  shr     rcx, 9
0x180005518  imul    rax, rcx, 3E8h
0x18000551f  sub     r8, rax
0x180005522  cmp     r8, 1F4h
0x180005529  setnl   sil
0x18000552d  add     rsi, rcx
0x180005530  cmp     cs:byte_180030D01, r15b
0x180005537  jl      loc_1800058F3
0x18000553d  mov     eax, [rbp+230h+TimeZoneInformation.Bias]
0x180005540  sub     eax, cs:TimeZoneInformation.Bias
0x180005546  mov     ecx, [rbp+230h+var_144]
0x18000554c  movsxd  r14, eax
0x18000554f  cmp     ecx, 1
0x180005552  jz      loc_18000589B
0x180005558  xor     eax, eax
0x18000555a  cmp     ecx, 2
0x18000555d  cmovz   eax, [rbp+230h+TimeZoneInformation.DaylightBias]
0x180005564  mov     edx, cs:dword_180030B7C
0x18000556a  cmp     edx, 1
0x18000556d  jz      loc_1800058A6
0x180005573  xor     ecx, ecx
0x180005575  cmp     edx, 2
0x180005578  cmovz   ecx, cs:TimeZoneInformation.DaylightBias
0x18000557f  cmp     eax, ecx
0x180005581  jnz     loc_180005907
0x180005587  test    cs:byte_180030D03, 1
0x18000558e  jnz     loc_18000592B
0x180005594  mov     rbx, cs:?g_ScheduleMgr@@3VCScheduleMgr@@A; CScheduleMgr g_ScheduleMgr
0x18000559b  lea     rax, [rsp+330h+var_2E8]
0x1800055a0  mov     [rsp+330h+var_2E8.Blink], rax
0x1800055a5  lea     r12, ?g_ScheduleMgr@@3VCScheduleMgr@@A; CScheduleMgr g_ScheduleMgr
0x1800055ac  lea     rax, [rsp+330h+var_2E8]
0x1800055b1  mov     [rsp+330h+var_2E8.Flink], rax
0x1800055b6  cmp     rbx, r12
0x1800055b9  jnz     loc_180005782
0x1800055bf  mov     r14, [rsp+330h+var_20]
0x1800055c7  lea     rcx, TimeZoneInformation
0x1800055ce  mov     r12, [rsp+320h]
0x1800055d6  lea     rax, [rbp+230h+TimeZoneInformation]
0x1800055da  mov     rsi, [rsp+330h+arg_10]
0x1800055e2  mov     edx, 2
0x1800055e7  lea     rcx, [rcx+80h]
0x1800055ee  movups  xmm0, xmmword ptr [rax]
0x1800055f1  movups  xmm1, xmmword ptr [rax+10h]
0x1800055f5  lea     rax, [rax+80h]
0x1800055fc  movups  xmmword ptr [rcx-80h], xmm0
0x180005600  movups  xmm0, xmmword ptr [rax-60h]
0x180005604  movups  xmmword ptr [rcx-70h], xmm1
0x180005608  movups  xmm1, xmmword ptr [rax-50h]
0x18000560c  movups  xmmword ptr [rcx-60h], xmm0
0x180005610  movups  xmm0, xmmword ptr [rax-40h]
0x180005614  movups  xmmword ptr [rcx-50h], xmm1
0x180005618  movups  xmm1, xmmword ptr [rax-30h]
0x18000561c  movups  xmmword ptr [rcx-40h], xmm0
0x180005620  movups  xmm0, xmmword ptr [rax-20h]
0x180005624  movups  xmmword ptr [rcx-30h], xmm1
0x180005628  movups  xmm1, xmmword ptr [rax-10h]
0x18000562c  movups  xmmword ptr [rcx-20h], xmm0
0x180005630  movups  xmmword ptr [rcx-10h], xmm1
0x180005634  sub     rdx, 1
0x180005638  jnz     short loc_1800055E7
0x18000563a  movups  xmm0, xmmword ptr [rax]
0x18000563d  lea     rbx, ?g_CurrentTimeZoneInfo@@3U_TIMEZONEINFO@@A; _TIMEZONEINFO g_CurrentTimeZoneInfo
0x180005644  mov     r8d, 0B0h; Size
0x18000564a  movaps  xmm6, xmmword ptr [rbp+230h+TimeZoneInformation.Bias]
0x18000564e  mov     rdx, rbx; Buf2
0x180005651  movaps  xmm7, xmmword ptr [rbp+230h+TimeZoneInformation.StandardName+0Ch]
0x180005655  movaps  xmm8, xmmword ptr [rbp+230h+TimeZoneInformation.StandardName+1Ch]
0x18000565a  movaps  xmm9, xmmword ptr [rbp+230h+TimeZoneInformation.StandardName+2Ch]
0x18000565f  movaps  xmm10, xmmword ptr [rbp+230h+TimeZoneInformation.StandardName+3Ch]
0x180005667  movaps  xmm11, xmmword ptr [rbp+230h+TimeZoneInformation.StandardDate.wSecond]
0x18000566f  movaps  xmm12, xmmword ptr [rbp+230h+TimeZoneInformation.DaylightName+8]
0x180005677  movaps  xmm13, xmmword ptr [rbp+230h+TimeZoneInformation.DaylightName+18h]
0x18000567f  movaps  xmm14, xmmword ptr [rbp+230h+TimeZoneInformation.DaylightName+28h]
0x180005687  movaps  xmm15, xmmword ptr [rbp+230h+TimeZoneInformation.DaylightName+38h]
0x18000568f  movups  xmmword ptr [rcx], xmm0
0x180005692  lea     rcx, [rsp+330h+Buf1+8]; Buf1
0x180005697  movaps  xmm0, xmmword ptr [rbp+0E0h]
0x18000569e  movups  [rbp+230h+var_230], xmm0
0x1800056a2  movups  [rsp+330h+Buf1+8], xmm6
0x1800056a7  movups  [rsp+330h+var_2C8+8], xmm7
0x1800056ac  movups  [rbp+230h+var_2B0], xmm8
0x1800056b1  movups  [rbp+230h+var_2A0], xmm9
0x1800056b6  movups  [rbp+230h+var_290], xmm10
0x1800056bb  movups  [rbp+230h+var_280], xmm11
0x1800056c0  movups  [rbp+230h+var_270], xmm12
0x1800056c5  movups  [rbp+230h+var_260], xmm13
0x1800056ca  movups  [rbp+230h+var_250], xmm14
0x1800056cf  movups  [rbp+230h+var_240], xmm15
0x1800056d4  call    memcmp_0
0x1800056d9  test    eax, eax
0x1800056db  jnz     loc_180005A36
0x1800056e1  cmp     cs:byte_180030D01, 0
0x1800056e8  movaps  xmm15, [rsp+330h+var_C8+8]
0x1800056f1  movaps  xmm14, [rsp+330h+var_B8+8]
0x1800056fa  movaps  xmm13, [rsp+330h+var_A8+8]
0x180005703  movaps  xmm12, [rsp+330h+var_98+8]
0x18000570c  movaps  xmm11, [rsp+330h+var_88+8]
0x180005715  movaps  xmm10, [rsp+330h+var_78+8]
0x18000571e  movaps  xmm9, [rsp+330h+var_68+8]
0x180005727  movaps  xmm8, [rsp+330h+var_58+8]
0x180005730  movaps  xmm7, [rsp+330h+var_48+8]
0x180005738  movaps  xmm6, [rsp+330h+var_38+8]
0x180005740  mov     rbx, [rsp+330h+arg_0]
0x180005748  jl      loc_180005ADB
0x18000574e  lea     rcx, CriticalSection; lpCriticalSection
0x180005755  call    cs:__imp_LeaveCriticalSection
0x18000575b  lea     rcx, [rsp+330h+var_2E8]; struct _LIST_ENTRY *
0x180005760  call    ?DeleteExpired@CScheduleMgr@@CAXPEAU_LIST_ENTRY@@@Z; CScheduleMgr::DeleteExpired(_LIST_ENTRY *)
0x180005765  mov     eax, r15d
0x180005768  mov     rcx, [rbp+230h+var_D0]
0x18000576f  xor     rcx, rsp; StackCookie
0x180005772  call    __security_check_cookie
0x180005777  add     rsp, 328h
0x18000577e  pop     r15
0x180005780  pop     rbp
0x180005781  retn
0x180005782  mov     [rsp+330h+arg_18], rdi
0x18000578a  mov     [rsp+330h+var_18], r13
0x180005792  mov     r8, rbx
0x180005795  mov     [rbp+230h+var_1F8], 1
0x18000579c  mov     r13, rbx
0x18000579f  mov     rdi, rbx
0x1800057a2  mov     rdx, rbx
0x1800057a5  mov     rbx, [rbx]
0x1800057a8  mov     ecx, [r8+2Ch]
0x1800057ac  and     ecx, 8
0x1800057af  jnz     loc_18000593B
0x1800057b5  mov     rax, [rbp+230h+var_130]
0x1800057bc  movaps  xmm0, [rbp+230h+var_140]
0x1800057c3  mov     [rbp+230h+var_210], rax
0x1800057c7  mov     rax, [rbp+230h+var_128]
0x1800057ce  mov     [rbp+230h+var_208], rax
0x1800057d2  mov     eax, [rbp+230h+var_120]
0x1800057d8  mov     [rbp+230h+var_200], eax
0x1800057db  mov     eax, [rbp+230h+var_11C]
0x1800057e1  mov     [rbp+230h+var_1FC], eax
0x1800057e4  movups  [rbp+230h+var_220], xmm0
0x1800057e8  cmp     [rdi+0C8h], r15
0x1800057ef  jz      loc_1800059B5
0x1800057f5  cmp     [rdi+0D8h], r15
0x1800057fc  jz      loc_1800059B5
0x180005802  imul    r12, rsi, 989680h
0x180005809  test    ecx, ecx
0x18000580b  jnz     loc_18000596C
0x180005811  lea     r8, [rsp+330h+var_2F0]; int *
0x180005816  mov     [rsp+330h+var_2F0], r15d
0x18000581b  lea     rdx, [rbp+230h+TimeZoneInformation]; struct TimeInfo *
0x18000581f  mov     rcx, rdi; this
0x180005822  call    ?TimeTransitionsCallback@CSchedule@@QEAAJAEBVTimeInfo@@PEAH@Z; CSchedule::TimeTransitionsCallback(TimeInfo const &,int *)
0x180005827  test    eax, eax
0x180005829  js      loc_1800059AA
0x18000582f  cmp     [rsp+330h+var_2F0], r15d
0x180005834  jnz     short loc_180005859
0x180005836  cmp     dword ptr [rdi+28h], 4
0x18000583a  jnz     short loc_180005859
0x18000583c  mov     rcx, [rdi+0C8h]
0x180005843  lea     rdx, [rbp+230h+var_220]
0x180005847  mov     r9, r14
0x18000584a  mov     r8, r12
0x18000584d  mov     rax, [rcx]
0x180005850  mov     rax, [rax+68h]
0x180005854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005859  mov     rdx, rdi
0x18000585c  mov     r8, rdi
0x18000585f  test    byte ptr [rdi+2Ch], 1
0x180005863  jnz     loc_18000597A
0x180005869  lea     r12, ?g_ScheduleMgr@@3VCScheduleMgr@@A; CScheduleMgr g_ScheduleMgr
0x180005870  cmp     [rdi+108h], r15d
0x180005877  jnz     loc_1800059EB
0x18000587d  cmp     rbx, r12
0x180005880  jnz     loc_180005792
0x180005886  mov     r13, [rsp+330h+var_18]
0x18000588e  mov     rdi, [rsp+330h+arg_18]
0x180005896  jmp     loc_1800055BF
0x18000589b  mov     eax, [rbp+230h+TimeZoneInformation.StandardBias]
0x1800058a1  jmp     loc_180005564
0x1800058a6  mov     ecx, cs:TimeZoneInformation.StandardBias
0x1800058ac  jmp     loc_18000557F
0x1800058b1  mov     rcx, [rsp+330h+phkResult]; hKey
0x1800058b6  lea     r8, ValueName; "TimeZoneInfo"
0x1800058bd  mov     [rsp+330h+cbData], 0B0h; cbData
0x1800058c5  mov     r9d, 3; dwType
0x1800058cb  xor     edx, edx; lpSubKey
0x1800058cd  mov     [rsp+330h+lpData], rbx; lpData
0x1800058d2  call    cs:__imp_RegSetKeyValueW
0x1800058d8  mov     r15d, eax
0x1800058db  test    eax, eax
0x1800058dd  jg      loc_180005ACB
0x1800058e3  mov     rcx, [rsp+330h+phkResult]; hKey
0x1800058e8  call    cs:__imp_RegCloseKey
0x1800058ee  jmp     loc_1800056E1
0x1800058f3  mov     r8, rsi
0x1800058f6  lea     rdx, TimeChangeProcessingStart
0x1800058fd  call    McTemplateU0i_EventWriteTransfer
0x180005902  jmp     loc_18000553D
0x180005907  lea     rcx, TimeZoneInformation; this
0x18000590e  call    ?DSTBias@TimeInfo@@QEBAJXZ; TimeInfo::DSTBias(void)
0x180005913  lea     rcx, [rbp+230h+TimeZoneInformation]; this
0x180005917  mov     edx, eax
0x180005919  call    ?DSTBias@TimeInfo@@QEBAJXZ; TimeInfo::DSTBias(void)
0x18000591e  sub     eax, edx
0x180005920  movsxd  rcx, eax
0x180005923  add     r14, rcx
0x180005926  jmp     loc_180005587
0x18000592b  mov     r9, r14
0x18000592e  mov     r8, rsi
0x180005931  call    McTemplateU0ii_EventWriteTransfer
0x180005936  jmp     loc_180005594
0x18000593b  mov     rax, [rbp+230h+var_100]
0x180005942  movaps  xmm0, [rbp+230h+var_110]
0x180005949  mov     [rbp+230h+var_210], rax
0x18000594d  mov     rax, [rbp+230h+var_F8]
0x180005954  mov     [rbp+230h+var_208], rax
0x180005958  mov     eax, [rbp+230h+var_F0]
0x18000595e  mov     [rbp+230h+var_200], eax
0x180005961  mov     eax, [rbp+230h+var_EC]
0x180005967  jmp     loc_1800057E1
0x18000596c  test    r12, r12
0x18000596f  jz      loc_18000585F
0x180005975  jmp     loc_180005811
0x18000597a  mov     rcx, cs:qword_180030AC8; this
0x180005981  lea     rdx, [rdi+10h]; struct _GUID *
0x180005985  xor     r8d, r8d; bool
0x180005988  call    ?PersistRuntimeData@TaskStore@@QEAAJAEBU_GUID@@_N@Z; TaskStore::PersistRuntimeData(_GUID const &,bool)
0x18000598d  test    eax, eax
0x18000598f  jns     short loc_1800059AA
0x180005991  test    cs:byte_180030D05, 40h
0x180005998  jz      short loc_1800059AA
0x18000599a  lea     r8, [rdi+10h]
0x18000599e  lea     rdx, PersistScheduleError
0x1800059a5  call    McTemplateU0j_EventWriteTransfer
0x1800059aa  mov     rdx, rdi
0x1800059ad  mov     r8, rdi
0x1800059b0  jmp     loc_180005869
0x1800059b5  test    cs:byte_180030D04, 1
0x1800059bc  jz      loc_180005870
0x1800059c2  lea     rax, [rbp+230h+var_E0]
0x1800059c9  mov     r9d, 1
0x1800059cf  lea     rdx, ErrorNullPointer
0x1800059d6  mov     [rsp+330h+lpData], rax
0x1800059db  call    McGenEventWrite_EventWriteTransfer
0x1800059e0  mov     rdx, rdi
0x1800059e3  mov     r8, rdi
0x1800059e6  jmp     loc_180005870
0x1800059eb  test    byte ptr [rdi+2Ch], 4
0x1800059ef  jz      loc_18000587D
0x1800059f5  mov     rax, [r13+8]
0x1800059f9  mov     rcx, [r13+0]
0x1800059fd  mov     [rax], rcx
0x180005a00  mov     [rcx+8], rax
0x180005a04  lea     rcx, [rsp+330h+var_2E8]; this
0x180005a09  mov     rax, [rsp+330h+var_2E8.Flink]
0x180005a0e  mov     [rdx], rax
0x180005a11  mov     [r13+8], rcx
0x180005a15  mov     [rax+8], rdi
  ... truncated ...
```
