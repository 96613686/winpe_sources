# WaasMedic::CRemediationPluginBase::EvaluateTimeBlocks(winrt::Windows::Internal::WaasMedicDocked::WaaSAssessmentImpactLevel,tagPluginActionApplicability *)

- ea: `0x18001c10c`
- end: `0x18001c632`
- name: `?EvaluateTimeBlocks@CRemediationPluginBase@WaasMedic@@AEAAJW4WaaSAssessmentImpactLevel@WaasMedicDocked@Internal@Windows@winrt@@PEAW4tagPluginActionApplicability@@@Z`
- size: `1318`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, installer_update`

## callers

- `0x18001cae0`

## callees

- `0x180003bb0`
- `0x1800070cc`
- `0x180007590`
- `0x180009a54`
- `0x18001c10c`
- `0x18001c8ec`
- `0x18002543c`
- `0x180025d18`
- `0x180030890`
- `0x1800308e0`
- `0x180030954`
- `0x1800309a0`
- `0x180030f54`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001c169`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001c169`
- `OLEAUT32!__imp_SysAllocString` at `0x18001c43d`
- `OLEAUT32!__imp_SysAllocString` at `0x18001c43d`
- `OLEAUT32!__imp_VariantInit` at `0x18001c142`
- `OLEAUT32!__imp_VariantInit` at `0x18001c502`
- `OLEAUT32!__imp_VariantInit` at `0x18001c142`
- `OLEAUT32!__imp_VariantInit` at `0x18001c502`
- `OLEAUT32!__imp_VariantClear` at `0x18001c5a6`
- `OLEAUT32!__imp_VariantClear` at `0x18001c603`
- `OLEAUT32!__imp_VariantClear` at `0x18001c5a6`
- `OLEAUT32!__imp_VariantClear` at `0x18001c603`

## string_xrefs

- `0x18001c24c`: `onecore\enduser\waasmedic\lib\plugins\remediationpluginbase.cpp`
- `0x18001c27f`: `Plugin %s block interval = %u hours`
- `0x18001c260`: `Error encountered when retrieving plugin interval! hr = 0x%08x`
- `0x18001c30c`: `Plugin BlockUntilTime %s has not yet expired!`
- `0x18001c323`: `Plugin BlockUntilTime %s has expired`
- `0x18001c37c`: `Failed to retrieve OS Install time. Blocking remediation operations.`
- `0x18001c3d8`: `Device has installed the OS %d days ago. Blocking remediation operations.`
- `0x18001c47c`: `Updated %s to %s!`
- `0x18001c4df`: `Plugin %s with Interval of %u hours has an interval block because there is no existing BlockUntilTime!`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WaasMedic::CRemediationPluginBase::EvaluateTimeBlocks(__int64 a1, int a2, _DWORD *a3)
{
  int v6; // ebx
  int v7; // ebx
  DWORD v8; // eax
  __int64 (__fastcall ***v9)(_QWORD, _BYTE *, _OWORD *, struct _FILETIME *); // rbx
  __int64 (__fastcall *v10)(_QWORD, _BYTE *, _OWORD *, struct _FILETIME *); // rsi
  __int64 v11; // rdx
  __int64 v12; // r8
  int OsInstallTime; // ebx
  DWORD dwLowDateTime; // esi
  int v15; // eax
  int v16; // eax
  LONGLONG llVal; // r8
  char v18; // r15
  unsigned int UptimeThreshold; // r14d
  unsigned int DaysBetweenFileTimes; // eax
  struct _FILETIME v21; // r9
  unsigned __int64 v22; // rdx
  int v23; // eax
  int v24; // eax
  unsigned int v25; // esi
  int v26; // eax
  int v27; // eax
  int v29; // [rsp+20h] [rbp-A9h]
  bool v30; // [rsp+30h] [rbp-99h] BYREF
  struct _FILETIME v31; // [rsp+38h] [rbp-91h] BYREF
  char v32; // [rsp+40h] [rbp-89h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-81h] BYREF
  struct _FILETIME v34; // [rsp+50h] [rbp-79h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-71h] BYREF
  _BYTE v36[32]; // [rsp+70h] [rbp-59h] BYREF
  _OWORD v37[2]; // [rsp+90h] [rbp-39h] BYREF
  OLECHAR psz[8]; // [rsp+B0h] [rbp-19h] BYREF
  _BYTE v39[26]; // [rsp+C0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  VariantInit(&pvarg);
  SystemTimeAsFileTime = 0;
  v34 = 0;
  *(_OWORD *)psz = 0;
  memset(v39, 0, sizeof(v39));
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v34 = SystemTimeAsFileTime;
  *a3 = 0;
  if ( !a2 )
  {
    v8 = 0;
    goto LABEL_9;
  }
  v6 = a2 - 1;
  if ( !v6 )
    goto LABEL_7;
  v7 = v6 - 1;
  if ( !v7 )
  {
    v8 = 168;
    goto LABEL_9;
  }
  if ( v7 != 1 )
  {
LABEL_7:
    v8 = 24;
    goto LABEL_9;
  }
  v8 = 336;
LABEL_9:
  v32 = 0;
  v31.dwLowDateTime = v8;
  v31.dwHighDateTime = 2;
  v9 = *(__int64 (__fastcall ****)(_QWORD, _BYTE *, _OWORD *, struct _FILETIME *))(a1 + 104);
  v10 = **v9;
  memset(v37, 0, sizeof(v37));
  std::wstring::_Construct<1,unsigned short const *>(v37, L"INTERVALINHOURS", 15);
  v11 = *(_QWORD *)(a1 + 112);
  memset(v36, 0, sizeof(v36));
  v12 = -1;
  do
    ++v12;
  while ( *(_WORD *)(v11 + 2 * v12) );
  std::wstring::_Construct<1,unsigned short const *>(v36, v11, v12);
  OsInstallTime = v10(v9, v36, v37, &v31);
  std::wstring::~wstring(v36);
  std::wstring::~wstring(v37);
  if ( OsInstallTime >= 0 )
  {
    dwLowDateTime = v31.dwLowDateTime;
    LogLevelW(4u, L"Plugin %s block interval = %u hours", *(_QWORD *)(a1 + 112), v31.dwLowDateTime);
    v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *, VARIANTARG *))(**(_QWORD **)(a1 + 96) + 16LL))(
            *(_QWORD *)(a1 + 96),
            *(_QWORD *)(a1 + 112),
            L"BlockUntilTimeStatus",
            &pvarg);
    OsInstallTime = v15;
    if ( v15 < 0 )
    {
      LogLevelW(
        2u,
        L"Failed to retrieve %s from state provider! hr = 0x%08x",
        L"BlockUntilTimeStatus",
        (unsigned int)v15);
      goto LABEL_49;
    }
    v31 = 0;
    if ( pvarg.vt == 8 )
    {
      v16 = WaasMedic::TimeHelper::StringToFileTime(pvarg.bstrVal, &v31);
      OsInstallTime = v16;
      if ( v16 < 0 )
      {
        LogLevelW(2u, L"Failed to convert time string %s to FILETIME! hr = 0x%08x", pvarg.llVal, (unsigned int)v16);
        goto LABEL_49;
      }
      v30 = 0;
      WaasMedic::TimeHelper::TimeDiff(&SystemTimeAsFileTime, &v31, &v30);
      llVal = pvarg.llVal;
      if ( v30 )
      {
        *a3 = 3;
        LogLevelW(4u, L"Plugin BlockUntilTime %s has not yet expired!", llVal);
        goto LABEL_49;
      }
      v18 = 1;
      LogLevelW(4u, L"Plugin BlockUntilTime %s has expired", pvarg.llVal);
    }
    else
    {
      v30 = 0;
      UptimeThreshold = WaasMedic::CRemediationPluginBase::GetUptimeThreshold(
                          (WaasMedic::CRemediationPluginBase *)a1,
                          0xAu,
                          L"MinUptimeThreshold",
                          L"Minimum");
      OsInstallTime = WaasMedic::MiscUtil::GetOsInstallTime(&v31);
      if ( OsInstallTime < 0 )
      {
        LogLevelW(2u, L"Failed to retrieve OS Install time. Blocking remediation operations.");
        goto LABEL_49;
      }
      v18 = 0;
      DaysBetweenFileTimes = WaasMedic::TimeHelper::GetDaysBetweenFileTimes(v31, SystemTimeAsFileTime, &v30);
      if ( v30 )
      {
        if ( DaysBetweenFileTimes >= UptimeThreshold )
        {
          LogLevelW(
            4u,
            L"First run, OS age %d day(s). Block until %d day(s) from now.",
            DaysBetweenFileTimes,
            UptimeThreshold);
          dwLowDateTime = 24 * UptimeThreshold;
        }
        else
        {
          v34 = v21;
          *a3 = 7;
          if ( 24 * UptimeThreshold > dwLowDateTime )
            dwLowDateTime = 24 * UptimeThreshold;
          LogLevelW(
            4u,
            L"Device has installed the OS %d days ago. Blocking remediation operations.",
            DaysBetweenFileTimes);
        }
      }
    }
    WaasMedic::TimeHelper::AddDelayToFileTime(&v34, 36000000000LL * dwLowDateTime, 1);
    v23 = WaasMedic::TimeHelper::FileTimeToString(psz, v22, &v34);
    OsInstallTime = v23;
    if ( v23 < 0 )
    {
      LogLevelW(2u, L"Failed to convert BlockUntilTime to string! hr = 0x%08x", (unsigned int)v23);
      goto LABEL_49;
    }
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(psz);
    if ( pvarg.llVal )
    {
      v24 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *, VARIANTARG *))(**(_QWORD **)(a1 + 96) + 24LL))(
              *(_QWORD *)(a1 + 96),
              *(_QWORD *)(a1 + 112),
              L"BlockUntilTimeStatus",
              &pvarg);
      OsInstallTime = v24;
      if ( v24 < 0 )
      {
        LogLevelW(2u, L"Failed to save %s for %s! hr = 0x%08x", psz, *(_QWORD *)(a1 + 112), v24);
        goto LABEL_49;
      }
      LogLevelW(4u, L"Updated %s to %s!", L"BlockUntilTimeStatus", psz);
    }
    else
    {
      OsInstallTime = -2147024882;
      LogLevelW(2u, L"Failed to allocate memory to save BlockUntilTime for %s!", *(_QWORD *)(a1 + 112));
    }
    if ( v18 )
    {
      v31 = 0;
      VariantInit((VARIANTARG *)v36);
      v30 = 0;
      v25 = WaasMedic::CRemediationPluginBase::GetUptimeThreshold(
              (WaasMedic::CRemediationPluginBase *)a1,
              0x14u,
              L"MaxUptimeThreshold",
              L"Maximum");
      if ( v25 )
      {
        v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *, _BYTE *))(**(_QWORD **)(a1 + 96) + 16LL))(
                *(_QWORD *)(a1 + 96),
                *(_QWORD *)(a1 + 112),
                L"LastApplicabilityRunTime",
                v36);
        OsInstallTime = v26;
        if ( v26 < 0 )
        {
          LogLevelW(
            2u,
            L"Failed to retrieve %s from state provider! hr = 0x%08x",
            L"LastDetectionRunTime",
            (unsigned int)v26);
        }
        else if ( *(_WORD *)v36 == 8 )
        {
          v27 = WaasMedic::TimeHelper::StringToFileTime(*(const unsigned __int16 **)&v36[8], &v31);
          OsInstallTime = v27;
          if ( v27 < 0 )
          {
            LogLevelW(
              2u,
              L"Failed to convert time string %s to FILETIME! hr = 0x%08x",
              *(_QWORD *)&v36[8],
              (unsigned int)v27);
          }
          else if ( WaasMedic::TimeHelper::GetDaysBetweenFileTimes(v31, SystemTimeAsFileTime, &v30) > v25 )
          {
            *a3 = 8;
            LogLevelW(
              4u,
              L"Device was previously seen but maximum threshold of %u days have elapsed. Blocking remediation operations.",
              v25);
          }
        }
      }
      VariantClear((VARIANTARG *)v36);
    }
    else if ( dwLowDateTime )
    {
      *a3 = 3;
      LogLevelW(
        4u,
        L"Plugin %s with Interval of %u hours has an interval block because there is no existing BlockUntilTime!",
        *(_QWORD *)(a1 + 112),
        dwLowDateTime);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13E,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\remediationpluginbase.cpp",
      (const char *)(unsigned int)OsInstallTime,
      v29);
    LogLevelW(2u, L"Error encountered when retrieving plugin interval! hr = 0x%08x", (unsigned int)OsInstallTime);
  }
LABEL_49:
  VariantClear(&pvarg);
  return (unsigned int)OsInstallTime;
}

```

## disassembly

```asm
0x18001c10c  mov     [rsp-8+arg_8], rbx
0x18001c111  push    rbp
0x18001c112  push    rsi
0x18001c113  push    rdi
0x18001c114  push    r12
0x18001c116  push    r13
0x18001c118  push    r14
0x18001c11a  push    r15
0x18001c11c  lea     rbp, [rsp-27h]
0x18001c121  sub     rsp, 0F0h
0x18001c128  mov     rax, cs:__security_cookie
0x18001c12f  xor     rax, rsp
0x18001c132  mov     [rbp+57h+var_40], rax
0x18001c136  mov     r12, r8
0x18001c139  mov     ebx, edx
0x18001c13b  mov     rdi, rcx
0x18001c13e  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001c142  call    cs:__imp_VariantInit
0x18001c148  nop
0x18001c149  xor     r13d, r13d
0x18001c14c  mov     qword ptr [rsp+120h+SystemTimeAsFileTime.dwLowDateTime], r13
0x18001c151  mov     qword ptr [rbp+57h+var_D0.dwLowDateTime], r13
0x18001c155  xorps   xmm0, xmm0
0x18001c158  movups  xmmword ptr [rbp+57h+psz], xmm0
0x18001c15c  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x18001c160  movups  xmmword ptr [rbp+57h+var_60+0Ah], xmm0
0x18001c164  lea     rcx, [rsp+120h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001c169  call    cs:__imp_GetSystemTimeAsFileTime
0x18001c16f  mov     rax, qword ptr [rsp+120h+SystemTimeAsFileTime.dwLowDateTime]
0x18001c174  mov     qword ptr [rbp+57h+var_D0.dwLowDateTime], rax
0x18001c178  mov     [r12], r13d
0x18001c17c  test    ebx, ebx
0x18001c17e  jz      short loc_18001C1A4
0x18001c180  sub     ebx, 1
0x18001c183  jz      short loc_18001C19D
0x18001c185  sub     ebx, 1
0x18001c188  jz      short loc_18001C196
0x18001c18a  cmp     ebx, 1
0x18001c18d  jnz     short loc_18001C19D
0x18001c18f  mov     eax, 150h
0x18001c194  jmp     short loc_18001C1A7
0x18001c196  mov     eax, 0A8h
0x18001c19b  jmp     short loc_18001C1A7
0x18001c19d  mov     eax, 18h
0x18001c1a2  jmp     short loc_18001C1A7
0x18001c1a4  mov     eax, r13d
0x18001c1a7  mov     [rsp+120h+var_E0], r13b
0x18001c1ac  mov     [rsp+120h+var_E8.dwLowDateTime], eax
0x18001c1b0  mov     r14d, 2
0x18001c1b6  mov     [rsp+120h+var_E8.dwHighDateTime], r14d
0x18001c1bb  mov     rbx, [rdi+68h]
0x18001c1bf  mov     rax, [rbx]
0x18001c1c2  mov     rsi, [rax]
0x18001c1c5  xorps   xmm0, xmm0
0x18001c1c8  movups  [rbp+57h+var_90], xmm0
0x18001c1cc  xorps   xmm1, xmm1
0x18001c1cf  movdqu  [rbp+57h+var_80], xmm1
0x18001c1d4  lea     r8d, [r14+0Dh]
0x18001c1d8  lea     rdx, aIntervalinhour; "INTERVALINHOURS"
0x18001c1df  lea     rcx, [rbp+57h+var_90]
0x18001c1e3  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001c1e8  nop
0x18001c1e9  mov     rdx, [rdi+70h]
0x18001c1ed  xorps   xmm0, xmm0
0x18001c1f0  movups  xmmword ptr [rbp+57h+var_B0], xmm0
0x18001c1f4  xorps   xmm1, xmm1
0x18001c1f7  movdqu  xmmword ptr [rbp+57h+var_B0+10h], xmm1
0x18001c1fc  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001c200  inc     r8
0x18001c203  cmp     [rdx+r8*2], r13w
0x18001c208  jnz     short loc_18001C200
0x18001c20a  lea     rcx, [rbp+57h+var_B0]
0x18001c20e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001c213  nop
0x18001c214  lea     r9, [rsp+120h+var_E8]
0x18001c219  lea     r8, [rbp+57h+var_90]
0x18001c21d  lea     rdx, [rbp+57h+var_B0]
0x18001c221  mov     rcx, rbx
0x18001c224  mov     rax, rsi
0x18001c227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c22c  mov     ebx, eax
0x18001c22e  lea     rcx, [rbp+57h+var_B0]; void *
0x18001c232  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c237  nop
0x18001c238  lea     rcx, [rbp+57h+var_90]; void *
0x18001c23c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c241  test    ebx, ebx
0x18001c243  jns     short loc_18001C274
0x18001c245  mov     rcx, [rbp+5Fh]; this
0x18001c249  mov     r9d, ebx; char *
0x18001c24c  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18001c253  mov     edx, 13Eh; void *
0x18001c258  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c25d  mov     r8d, ebx
0x18001c260  lea     rdx, aErrorEncounter_6; "Error encountered when retrieving plugi"...
0x18001c267  mov     ecx, r14d; unsigned __int8
0x18001c26a  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18001c26f  jmp     loc_18001C5FF
0x18001c274  mov     esi, [rsp+120h+var_E8.dwLowDateTime]
0x18001c278  mov     r9d, esi
0x18001c27b  mov     r8, [rdi+70h]
0x18001c27f  lea     rdx, aPluginSBlockIn; "Plugin %s block interval = %u hours"
0x18001c286  mov     r15d, 4
0x18001c28c  mov     ecx, r15d; unsigned __int8
0x18001c28f  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18001c294  mov     rcx, [rdi+60h]
0x18001c298  mov     rax, [rcx]
0x18001c29b  lea     r9, [rbp+57h+pvarg]
0x18001c29f  lea     r8, aBlockuntiltime; "BlockUntilTimeStatus"
0x18001c2a6  mov     rdx, [rdi+70h]
0x18001c2aa  mov     rax, [rax+10h]
0x18001c2ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2b3  mov     ebx, eax
0x18001c2b5  test    eax, eax
0x18001c2b7  js      loc_18001C5E5
0x18001c2bd  lea     eax, [r15+4]
0x18001c2c1  mov     qword ptr [rsp+120h+var_E8.dwLowDateTime], r13
0x18001c2c6  cmp     ax, word ptr [rbp+57h+pvarg]
0x18001c2ca  jnz     short loc_18001C349
0x18001c2cc  lea     rdx, [rsp+120h+var_E8]; struct _FILETIME *
0x18001c2d1  mov     rcx, qword ptr [rbp+57h+pvarg+8]; unsigned __int16 *
0x18001c2d5  call    ?StringToFileTime@TimeHelper@WaasMedic@@SAJPEBGPEAU_FILETIME@@@Z; WaasMedic::TimeHelper::StringToFileTime(ushort const *,_FILETIME *)
0x18001c2da  mov     ebx, eax
0x18001c2dc  test    eax, eax
0x18001c2de  js      short loc_18001C339
0x18001c2e0  mov     [rsp+120h+var_F0], r13b
0x18001c2e5  lea     r8, [rsp+120h+var_F0]; bool *
0x18001c2ea  lea     rdx, [rsp+120h+var_E8]; struct _FILETIME *
0x18001c2ef  lea     rcx, [rsp+120h+SystemTimeAsFileTime]; struct _FILETIME *
0x18001c2f4  call    ?TimeDiff@TimeHelper@WaasMedic@@SA_KAEBU_FILETIME@@0AEA_N@Z; WaasMedic::TimeHelper::TimeDiff(_FILETIME const &,_FILETIME const &,bool &)
0x18001c2f9  mov     r8, qword ptr [rbp+57h+pvarg+8]
0x18001c2fd  cmp     [rsp+120h+var_F0], r13b
0x18001c302  jz      short loc_18001C320
0x18001c304  mov     dword ptr [r12], 3
0x18001c30c  lea     rdx, aPluginBlockunt; "Plugin BlockUntilTime %s has not yet ex"...
0x18001c313  mov     ecx, r15d; unsigned __int8
0x18001c316  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18001c31b  jmp     loc_18001C5FF
0x18001c320  mov     r15b, 1
0x18001c323  lea     rdx, aPluginBlockunt_0; "Plugin BlockUntilTime %s has expired"
0x18001c32a  mov     ecx, 4; unsigned __int8
0x18001c32f  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18001c334  jmp     loc_18001C3FD
0x18001c339  mov     r8, qword ptr [rbp+57h+pvarg+8]
0x18001c33d  lea     rdx, aFailedToConver_4; "Failed to convert time string %s to FIL"...
0x18001c344  jmp     loc_18001C5F3
0x18001c349  mov     [rsp+120h+var_F0], r13b
0x18001c34e  lea     r9, aMinimum; "Minimum"
0x18001c355  lea     r8, aMinuptimethres; "MinUptimeThreshold"
0x18001c35c  mov     edx, 0Ah; unsigned int
0x18001c361  mov     rcx, rdi; this
0x18001c364  call    ?GetUptimeThreshold@CRemediationPluginBase@WaasMedic@@AEAAKKPEBG0@Z; WaasMedic::CRemediationPluginBase::GetUptimeThreshold(ulong,ushort const *,ushort const *)
0x18001c369  mov     r14d, eax
0x18001c36c  lea     rcx, [rsp+120h+var_E8]; struct _FILETIME *
0x18001c371  call    ?GetOsInstallTime@MiscUtil@WaasMedic@@SAJAEAU_FILETIME@@@Z; WaasMedic::MiscUtil::GetOsInstallTime(_FILETIME &)
0x18001c376  mov     ebx, eax
0x18001c378  test    eax, eax
0x18001c37a  jns     short loc_18001C392
0x18001c37c  lea     rdx, aFailedToRetrie_1; "Failed to retrieve OS Install time. Blo"...
0x18001c383  mov     ecx, 2; unsigned __int8
0x18001c388  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18001c38d  jmp     loc_18001C5FF
0x18001c392  mov     r15b, r13b
0x18001c395  lea     r8, [rsp+120h+var_F0]; bool *
0x18001c39a  mov     rdx, qword ptr [rsp+120h+SystemTimeAsFileTime.dwLowDateTime]; struct _FILETIME
0x18001c39f  mov     r9, qword ptr [rsp+120h+var_E8.dwLowDateTime]
0x18001c3a4  mov     rcx, r9; struct _FILETIME
0x18001c3a7  call    ?GetDaysBetweenFileTimes@TimeHelper@WaasMedic@@SAKU_FILETIME@@0AEA_N@Z; WaasMedic::TimeHelper::GetDaysBetweenFileTimes(_FILETIME,_FILETIME,bool &)
0x18001c3ac  cmp     [rsp+120h+var_F0], r13b
0x18001c3b1  jz      short loc_18001C3F7
0x18001c3b3  lea     ebx, [r14+r14*2]
0x18001c3b7  shl     ebx, 3
0x18001c3ba  mov     r8d, eax
0x18001c3bd  mov     ecx, 4; unsigned __int8
0x18001c3c2  cmp     eax, r14d
0x18001c3c5  jnb     short loc_18001C3E6
0x18001c3c7  mov     qword ptr [rbp+57h+var_D0.dwLowDateTime], r9
0x18001c3cb  mov     dword ptr [r12], 7
0x18001c3d3  cmp     ebx, esi
0x18001c3d5  cmova   esi, ebx
0x18001c3d8  lea     rdx, aDeviceHasInsta; "Device has installed the OS %d days ago"...
0x18001c3df  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18001c3e4  jmp     short loc_18001C3F7
0x18001c3e6  mov     r9d, r14d
0x18001c3e9  lea     rdx, aFirstRunOsAgeD; "First run, OS age %d day(s). Block unti"...
0x18001c3f0  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18001c3f5  mov     esi, ebx
0x18001c3f7  mov     r14d, 2
0x18001c3fd  mov     edx, esi
0x18001c3ff  mov     rax, 861C46800h
0x18001c409  imul    rdx, rax; unsigned __int64
0x18001c40d  mov     r8b, 1; bool
0x18001c410  lea     rcx, [rbp+57h+var_D0]; struct _FILETIME *
0x18001c414  call    ?AddDelayToFileTime@TimeHelper@WaasMedic@@SAXAEAU_FILETIME@@_K_N@Z; WaasMedic::TimeHelper::AddDelayToFileTime(_FILETIME &,unsigned __int64,bool)
0x18001c419  lea     r8, [rbp+57h+var_D0]; struct _FILETIME *
0x18001c41d  lea     rcx, [rbp+57h+psz]; unsigned __int16 *
0x18001c421  call    ?FileTimeToString@TimeHelper@WaasMedic@@SAJPEAG_KAEBU_FILETIME@@@Z; WaasMedic::TimeHelper::FileTimeToString(ushort *,unsigned __int64,_FILETIME const &)
0x18001c426  mov     ebx, eax
0x18001c428  test    eax, eax
0x18001c42a  js      loc_18001C5D6
0x18001c430  mov     eax, 8
0x18001c435  mov     word ptr [rbp+57h+pvarg], ax
0x18001c439  lea     rcx, [rbp+57h+psz]; psz
0x18001c43d  call    cs:__imp_SysAllocString
0x18001c443  mov     qword ptr [rbp+57h+pvarg+8], rax
0x18001c447  test    rax, rax
0x18001c44a  jz      short loc_18001C4AF
0x18001c44c  mov     rcx, [rdi+60h]
0x18001c450  mov     rax, [rcx]
0x18001c453  lea     r9, [rbp+57h+pvarg]
0x18001c457  lea     r8, aBlockuntiltime; "BlockUntilTimeStatus"
0x18001c45e  mov     rdx, [rdi+70h]
0x18001c462  mov     rax, [rax+18h]
0x18001c466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c46b  mov     ebx, eax
0x18001c46d  test    eax, eax
0x18001c46f  js      short loc_18001C48F
0x18001c471  lea     r9, [rbp+57h+psz]
0x18001c475  lea     r8, aBlockuntiltime; "BlockUntilTimeStatus"
0x18001c47c  lea     rdx, aUpdatedSToS; "Updated %s to %s!"
0x18001c483  mov     ecx, 4; unsigned __int8
0x18001c488  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18001c48d  jmp     short loc_18001C4C7
0x18001c48f  mov     [rsp+120h+var_100], eax
0x18001c493  mov     r9, [rdi+70h]
0x18001c497  lea     r8, [rbp+57h+psz]
0x18001c49b  lea     rdx, aFailedToSaveSF; "Failed to save %s for %s! hr = 0x%08x"
0x18001c4a2  mov     ecx, r14d; unsigned __int8
0x18001c4a5  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18001c4aa  jmp     loc_18001C5FF
0x18001c4af  mov     ebx, 8007000Eh
0x18001c4b4  mov     r8, [rdi+70h]
0x18001c4b8  lea     rdx, aFailedToAlloca_16; "Failed to allocate memory to save Block"...
0x18001c4bf  mov     ecx, r14d; unsigned __int8
0x18001c4c2  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18001c4c7  test    r15b, r15b
0x18001c4ca  jnz     short loc_18001C4F9
0x18001c4cc  test    esi, esi
0x18001c4ce  jz      short loc_18001C4F0
0x18001c4d0  mov     dword ptr [r12], 3
0x18001c4d8  mov     r9d, esi
0x18001c4db  mov     r8, [rdi+70h]
0x18001c4df  lea     rdx, aPluginSWithInt; "Plugin %s with Interval of %u hours has"...
0x18001c4e6  mov     ecx, 4; unsigned __int8
0x18001c4eb  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18001c4f0  test    r15b, r15b
0x18001c4f3  jz      loc_18001C5FF
0x18001c4f9  mov     qword ptr [rsp+120h+var_E8.dwLowDateTime], r13
0x18001c4fe  lea     rcx, [rbp+57h+var_B0]; pvarg
0x18001c502  call    cs:__imp_VariantInit
0x18001c508  nop
0x18001c509  mov     [rsp+120h+var_F0], r13b
0x18001c50e  lea     r9, aMaximum; "Maximum"
0x18001c515  lea     r8, aMaxuptimethres; "MaxUptimeThreshold"
0x18001c51c  mov     edx, 14h; unsigned int
0x18001c521  mov     rcx, rdi; this
0x18001c524  call    ?GetUptimeThreshold@CRemediationPluginBase@WaasMedic@@AEAAKKPEBG0@Z; WaasMedic::CRemediationPluginBase::GetUptimeThreshold(ulong,ushort const *,ushort const *)
0x18001c529  mov     esi, eax
0x18001c52b  test    eax, eax
0x18001c52d  jz      short loc_18001C5A2
0x18001c52f  mov     rcx, [rdi+60h]
0x18001c533  mov     rdx, [rcx]
0x18001c536  mov     rax, [rdx+10h]
0x18001c53a  lea     r9, [rbp+57h+var_B0]
0x18001c53e  lea     r8, aLastapplicabil; "LastApplicabilityRunTime"
0x18001c545  mov     rdx, [rdi+70h]
0x18001c549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c54e  mov     ebx, eax
0x18001c550  test    eax, eax
0x18001c552  js      short loc_18001C5BB
0x18001c554  mov     edi, 8
0x18001c559  cmp     di, word ptr [rbp+57h+var_B0]
0x18001c55d  jnz     short loc_18001C5A2
0x18001c55f  lea     rdx, [rsp+120h+var_E8]; struct _FILETIME *
0x18001c564  mov     rcx, qword ptr [rbp+57h+var_B0+8]; unsigned __int16 *
0x18001c568  call    ?StringToFileTime@TimeHelper@WaasMedic@@SAJPEBGPEAU_FILETIME@@@Z; WaasMedic::TimeHelper::StringToFileTime(ushort const *,_FILETIME *)
0x18001c56d  mov     ebx, eax
0x18001c56f  test    eax, eax
0x18001c571  js      short loc_18001C5AE
0x18001c573  lea     r8, [rsp+120h+var_F0]; bool *
0x18001c578  mov     rdx, qword ptr [rsp+120h+SystemTimeAsFileTime.dwLowDateTime]; struct _FILETIME
0x18001c57d  mov     rcx, qword ptr [rsp+120h+var_E8.dwLowDateTime]; struct _FILETIME
0x18001c582  call    ?GetDaysBetweenFileTimes@TimeHelper@WaasMedic@@SAKU_FILETIME@@0AEA_N@Z; WaasMedic::TimeHelper::GetDaysBetweenFileTimes(_FILETIME,_FILETIME,bool &)
0x18001c587  cmp     eax, esi
0x18001c589  jbe     short loc_18001C5A2
0x18001c58b  mov     [r12], edi
0x18001c58f  mov     r8d, esi
0x18001c592  lea     rdx, aDeviceWasPrevi; "Device was previously seen but maximum "...
0x18001c599  lea     ecx, [rdi-4]; unsigned __int8
0x18001c59c  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18001c5a1  nop
0x18001c5a2  lea     rcx, [rbp+57h+var_B0]; pvarg
0x18001c5a6  call    cs:__imp_VariantClear
0x18001c5ac  jmp     short loc_18001C5FF
0x18001c5ae  mov     r8, qword ptr [rbp+57h+var_B0+8]
0x18001c5b2  lea     rdx, aFailedToConver_4; "Failed to convert time string %s to FIL"...
0x18001c5b9  jmp     short loc_18001C5C9
0x18001c5bb  lea     r8, aLastdetectionr; "LastDetectionRunTime"
0x18001c5c2  lea     rdx, aFailedToRetrie; "Failed to retrieve %s from state provid"...
0x18001c5c9  mov     r9d, eax
  ... truncated ...
```
