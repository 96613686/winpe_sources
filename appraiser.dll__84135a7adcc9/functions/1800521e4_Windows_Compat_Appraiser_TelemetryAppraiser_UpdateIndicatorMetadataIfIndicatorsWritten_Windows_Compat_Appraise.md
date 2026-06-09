# Windows::Compat::Appraiser::TelemetryAppraiser::UpdateIndicatorMetadataIfIndicatorsWritten(Windows::Compat::Appraiser::ComponentStatusQuery &,ulong)

- ea: `0x1800521e4`
- end: `0x180052779`
- name: `?UpdateIndicatorMetadataIfIndicatorsWritten@TelemetryAppraiser@Appraiser@Compat@Windows@@CAJAEAVComponentStatusQuery@234@K@Z`
- size: `1429`
- prototype: `__int64 __fastcall(struct Windows::Compat::Appraiser::ComponentStatusQuery *this, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18004dc14`

## callees

- `0x18000147c`
- `0x180008570`
- `0x180013c7c`
- `0x1800151f4`
- `0x180026fd0`
- `0x18002750c`
- `0x180029258`
- `0x18002ebb8`
- `0x1800301d0`
- `0x1800521e4`
- `0x1800a817c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180052352`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180052352`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800523b5`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800523b5`
- `KERNEL32!InitOnceExecuteOnce` at `0x1800522f7`
- `KERNEL32!InitOnceExecuteOnce` at `0x1800526c7`
- `KERNEL32!InitOnceExecuteOnce` at `0x1800522f7`
- `KERNEL32!InitOnceExecuteOnce` at `0x1800526c7`
- `KERNEL32!GetSystemTime` at `0x180052589`
- `KERNEL32!GetSystemTime` at `0x180052589`

## string_xrefs

- `0x180052265`: `onecore\base\appcompat\appraiser\heads\telemetry\telemetryappraiser.cpp`
- `0x1800523e9`: `onecore\base\appcompat\appraiser\heads\telemetry\telemetryappraiser.cpp`
- `0x180052479`: `onecore\base\appcompat\appraiser\heads\telemetry\telemetryappraiser.cpp`
- `0x180052561`: `onecore\base\appcompat\appraiser\heads\telemetry\telemetryappraiser.cpp`
- `0x180052603`: `onecore\base\appcompat\appraiser\heads\telemetry\telemetryappraiser.cpp`
- `0x180052632`: `onecore\base\appcompat\appraiser\heads\telemetry\telemetryappraiser.cpp`
- `0x180052295`: `Failed to read old indicator data version, swallowing: [0x%x].`
- `0x1800524a7`: `Failed to read old indicator data version, swallowing: [0x%x].`
- `0x1800522a4`: `OutputRegistryMarker`
- `0x1800522c7`: `OutputRegistryMarker`
- `0x18005225c`: `Windows::Compat::Appraiser::TelemetryAppraiser::UpdateIndicatorMetadataIfIndicatorsWritten`
- `0x1800523e2`: `Windows::Compat::Appraiser::TelemetryAppraiser::UpdateIndicatorMetadataIfIndicatorsWritten`
- `0x180052480`: `Windows::Compat::Appraiser::TelemetryAppraiser::UpdateIndicatorMetadataIfIndicatorsWritten`
- `0x1800525fc`: `Windows::Compat::Appraiser::TelemetryAppraiser::UpdateIndicatorMetadataIfIndicatorsWritten`
- `0x18005262b`: `Windows::Compat::Appraiser::TelemetryAppraiser::UpdateIndicatorMetadataIfIndicatorsWritten`
- `0x1800523d1`: `Recommended data version for indicators onesetting value was invalid.`
- `0x180052345`: `TEL_RECOMMENDEDDATAVERSIONFORINDICATORS_`
- `0x180052674`: `Failed to write new indicator onesettings evidence timestamp: [0x%x].`
- `0x180052703`: `Failed to write new indicator onesettings evidence timestamp: [0x%x].`
- `0x180052732`: `Failed to write new indicator onesettings evidence timestamp: [0x%x].`
- `0x180052469`: `Failed to write new indicator data version: [0x%x].`
- `0x18005260e`: `Failed to write new indicator data version: [0x%x].`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::TelemetryAppraiser::UpdateIndicatorMetadataIfIndicatorsWritten(
        struct Windows::Compat::Appraiser::ComponentStatusQuery *this,
        unsigned int a2,
        __int64 a3,
        HKEY a4)
{
  int v6; // eax
  int v7; // ebx
  char ComponentStatus; // al
  char v9; // r15
  HKEY v10; // r9
  unsigned __int64 v11; // rax
  unsigned int v12; // r14d
  unsigned __int64 i; // rbx
  _QWORD *v14; // r9
  unsigned __int64 v15; // rax
  __int64 *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rax
  const wchar_t *v19; // r12
  unsigned int v20; // esi
  unsigned int v21; // esi
  int v22; // eax
  unsigned int v23; // ebx
  char v24; // dl
  volatile signed __int64 *v25; // rcx
  void **v26; // rdx
  int v27; // esi
  int v28; // r8d
  int v29; // r9d
  int v30; // eax
  unsigned int v31; // ecx
  const WCHAR *v32; // rbx
  HKEY v33; // r9
  int v34; // eax
  const char *lpSubKey; // [rsp+20h] [rbp-E0h]
  const char *lpSubKeya; // [rsp+20h] [rbp-E0h]
  const char *v38; // [rsp+28h] [rbp-D8h]
  char *v39; // [rsp+30h] [rbp-D0h]
  unsigned int pvData; // [rsp+60h] [rbp-A0h] BYREF
  BYTE Data[8]; // [rsp+68h] [rbp-98h] BYREF
  BYTE v42[8]; // [rsp+70h] [rbp-90h] BYREF
  int v43; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v44; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *EndPtr; // [rsp+88h] [rbp-78h] BYREF
  char *v46; // [rsp+90h] [rbp-70h] BYREF
  const char *v47; // [rsp+98h] [rbp-68h] BYREF
  const char *v48; // [rsp+A0h] [rbp-60h] BYREF
  const size_t *v49; // [rsp+A8h] [rbp-58h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+B0h] [rbp-50h] BYREF
  struct _SYSTEMTIME v51; // [rsp+C0h] [rbp-40h] BYREF
  char v52[144]; // [rsp+D0h] [rbp-30h] BYREF
  char v53[144]; // [rsp+160h] [rbp+60h] BYREF

  EndPtr = 0;
  pvData = 0;
  v44 = 4;
  v6 = Windows::Compat::Shared::Registry::ReadValue(
         &pvData,
         &v44,
         0x10u,
         a4,
         Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser,
         L"IndicatorDataVersion");
  v7 = v6;
  if ( v6 == -2147024894 )
  {
    pvData = 0;
    v7 = 0;
    goto LABEL_3;
  }
  if ( v6 >= 0 )
  {
LABEL_3:
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x609u,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
        "Windows::Compat::Appraiser::TelemetryAppraiser::UpdateIndicatorMetadataIfIndicatorsWritten",
        "Failed to read old indicator data version, swallowing: [0x%x].",
        v7);
    goto LABEL_5;
  }
  LODWORD(v39) = v6;
  LODWORD(lpSubKey) = v6;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    9,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
    "Windows::Compat::Appraiser::TelemetryAppraiser::UpdateIndicatorMetadataIfIndicatorsWritten",
    lpSubKey,
    (int)"Failed to read old indicator data version, swallowing: [0x%x].",
    v39);
  TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v52);
  v25 = (volatile signed __int64 *)v52;
  if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
    v25 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v25,
    _InterlockedExchangeAdd64(v25 + 17, 0),
    v53);
  if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
    UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v26);
  v27 = qword_1802C9628;
  if ( *(_DWORD *)qword_1802C9628 > 5u
    && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
    && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
  {
    v43 = v7;
    v46 = v53;
    v47 = "Windows::Compat::Appraiser::TelemetryAppraiser::UpdateIndicatorMetadataIfIndicatorsWritten";
    v48 = "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp";
    LODWORD(v44) = 1545;
    v49 = &szValueBuf;
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    *(_QWORD *)v42 = &v51;
    v51 = SystemTime;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v27,
      (unsigned int)&unk_18029F83C,
      v28,
      v29,
      (__int64)v42,
      (__int64)&v49,
      (__int64)&v44,
      (__int64)&v48,
      (__int64)&v47,
      (__int64)&v43,
      (__int64)&v46);
  }
LABEL_5:
  ComponentStatus = Windows::Compat::Appraiser::ComponentStatusQuery::GetComponentStatus(this, L"OutputRegistryMarker");
  if ( (ComponentStatus & 3) != 3
    || (ComponentStatus & 5) == 5
    || (v9 = 1,
        (Windows::Compat::Appraiser::ComponentStatusQuery::GetComponentStatus(this, L"OutputRegistryMarker") & 5) == 5) )
  {
    v9 = 0;
  }
  InitOnceExecuteOnce(
    &Windows::Compat::Appraiser::AppraiserSettings::InitOnce,
    Windows::Compat::Appraiser::AppraiserSettings::InitOnceCallback,
    0,
    0);
  v11 = xmmword_1802CB418;
  v12 = 0;
  for ( i = 0; i < (unsigned __int64)xmmword_1802CB418; ++i )
  {
    v14 = 0;
    if ( i < v11 )
    {
      *(_QWORD *)v42 = 0;
      v15 = (_QWORD)*(&Windows::Compat::Appraiser::AppraiserSettings::SettingTelemetryAdditionalInitProperties + 1) * i;
      if ( !is_mul_ok(
              (unsigned __int64)*(&Windows::Compat::Appraiser::AppraiserSettings::SettingTelemetryAdditionalInitProperties
                                + 1),
              i)
        || (v14 = (_QWORD *)(v15 + *((_QWORD *)&xmmword_1802CB428 + 1)),
            v15 + *((_QWORD *)&xmmword_1802CB428 + 1) < *((_QWORD *)&xmmword_1802CB428 + 1)) )
      {
        v14 = 0;
      }
    }
    if ( !(unsigned int)_o__wcsnicmp(*v14, L"TEL_RECOMMENDEDDATAVERSIONFORINDICATORS_", 40) )
    {
      v16 = 0;
      if ( i < (unsigned __int64)xmmword_1802CB418 )
      {
        *(_QWORD *)v42 = 0;
        if ( !is_mul_ok(
                (unsigned __int64)*(&Windows::Compat::Appraiser::AppraiserSettings::SettingTelemetryAdditionalInitProperties
                                  + 1),
                i)
          || (v16 = (__int64 *)(*((_QWORD *)&xmmword_1802CB428 + 1)
                              + (_QWORD)*(&Windows::Compat::Appraiser::AppraiserSettings::SettingTelemetryAdditionalInitProperties
                                        + 1)
                              * i),
              (unsigned __int64)v16 < *((_QWORD *)&xmmword_1802CB428 + 1)) )
        {
          v16 = 0;
        }
      }
      v17 = *v16;
      v18 = -1;
      do
        ++v18;
      while ( *(_WORD *)(v17 + 2 * v18) );
      v19 = (const wchar_t *)(v17 + 2 * (v18 + 1));
      v20 = wcstoul(v19, &EndPtr, 0);
      if ( !v20 && (*EndPtr || v19 == EndPtr) )
      {
        LODWORD(lpSubKey) = -2147024883;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          43,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
          "Windows::Compat::Appraiser::TelemetryAppraiser::UpdateIndicatorMetadataIfIndicatorsWritten",
          lpSubKey,
          (int)"Recommended data version for indicators onesetting value was invalid.",
          v39);
      }
      if ( v12 <= v20 )
        v12 = v20;
    }
    v11 = xmmword_1802CB418;
  }
  v21 = pvData;
  if ( !v9 )
  {
LABEL_43:
    if ( v12 <= v21 )
    {
      v32 = Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser;
      InitOnceExecuteOnce(
        &Windows::Compat::Appraiser::AppraiserSettings::InitOnce,
        Windows::Compat::Appraiser::AppraiserSettings::InitOnceCallback,
        0,
        0);
      *(_QWORD *)v42 = Windows::Compat::Appraiser::AppraiserSettings::SettingOneSettingsFreshnessTimestamp;
      v34 = Windows::Compat::Shared::Registry::WriteValue(
              v42,
              8u,
              0xBu,
              v33,
              v32,
              L"IndicatorOnesettingsEvidenceTimestamp");
      v23 = v34;
      if ( v34 < 0 )
      {
        LODWORD(v39) = v34;
        v38 = "Failed to write new indicator onesettings evidence timestamp: [0x%x].";
        v24 = 69;
        goto LABEL_31;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      {
        v31 = 1605;
        goto LABEL_52;
      }
    }
    else
    {
      *(_QWORD *)v42 = 0;
      v30 = Windows::Compat::Shared::Registry::WriteValue(
              v42,
              8u,
              0xBu,
              v10,
              Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser,
              L"IndicatorOnesettingsEvidenceTimestamp");
      v23 = v30;
      if ( v30 < 0 )
      {
        LODWORD(v39) = v30;
        v38 = "Failed to write new indicator onesettings evidence timestamp: [0x%x].";
        v24 = 64;
        goto LABEL_31;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      {
        v31 = 1600;
LABEL_52:
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          v31,
          "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
          "Windows::Compat::Appraiser::TelemetryAppraiser::UpdateIndicatorMetadataIfIndicatorsWritten",
          "Failed to write new indicator onesettings evidence timestamp: [0x%x].",
          v23);
      }
    }
    return 0;
  }
  v21 = a2;
  *(_DWORD *)Data = a2;
  v22 = Windows::Compat::Shared::Registry::WriteValue(
          Data,
          4u,
          4u,
          v10,
          Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser,
          L"IndicatorDataVersion");
  v23 = v22;
  if ( v22 >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x63Au,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
        "Windows::Compat::Appraiser::TelemetryAppraiser::UpdateIndicatorMetadataIfIndicatorsWritten",
        "Failed to write new indicator data version: [0x%x].",
        v22);
    goto LABEL_43;
  }
  LODWORD(v39) = v22;
  v38 = "Failed to write new indicator data version: [0x%x].";
  v24 = 58;
LABEL_31:
  LODWORD(lpSubKeya) = v23;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    v24,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
    "Windows::Compat::Appraiser::TelemetryAppraiser::UpdateIndicatorMetadataIfIndicatorsWritten",
    lpSubKeya,
    (int)v38,
    v39);
  return v23;
}

```

## disassembly

```asm
0x1800521e4  mov     [rsp-8+arg_10], rbx
0x1800521e9  mov     [rsp-8+arg_18], rsi
0x1800521ee  push    rbp
0x1800521ef  push    r12
0x1800521f1  push    r13
0x1800521f3  push    r14
0x1800521f5  push    r15
0x1800521f7  lea     rbp, [rsp-100h]
0x1800521ff  sub     rsp, 200h
0x180052206  mov     rax, cs:__security_cookie
0x18005220d  xor     rax, rsp
0x180052210  mov     [rbp+120h+var_30], rax
0x180052217  mov     rax, cs:?RegistryPathAppraiser@WicaFactory@Appraiser@Compat@Windows@@2PEAGEA; ushort * Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser
0x18005221e  xor     r12d, r12d
0x180052221  mov     r14, rcx
0x180052224  mov     [rbp+120h+EndPtr], r12
0x180052228  lea     rcx, aIndicatordatav; "IndicatorDataVersion"
0x18005222f  mov     [rsp+220h+pvData], r12d
0x180052234  mov     [rsp+220h+var_1F8], rcx; unsigned __int16 *
0x180052239  mov     r13d, edx
0x18005223c  lea     r8d, [r12+10h]; unsigned int
0x180052241  mov     [rbp+120h+var_1A0], 4
0x180052249  lea     rdx, [rbp+120h+var_1A0]; unsigned __int64 *
0x18005224d  mov     [rsp+220h+lpSubKey], rax; unsigned __int16 *
0x180052252  lea     rcx, [rsp+220h+pvData]; pvData
0x180052257  call    ?ReadValue@Registry@Shared@Compat@Windows@@SAJPEAEAEA_KKPEAUHKEY__@@PEBG3@Z; Windows::Compat::Shared::Registry::ReadValue(uchar *,unsigned __int64 &,ulong,HKEY__ *,ushort const *,ushort const *)
0x18005225c  lea     r15, aWindowsCompatA_491; "Windows::Compat::Appraiser::TelemetryAp"...
0x180052263  mov     ebx, eax
0x180052265  lea     rcx, aOnecoreBaseApp_75; "onecore\\base\\appcompat\\appraiser\\he"...
0x18005226c  cmp     eax, 80070002h
0x180052271  jnz     loc_18005249F
0x180052277  mov     [rsp+220h+pvData], r12d
0x18005227c  mov     ebx, r12d
0x18005227f  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180052285  test    al, 1
0x180052287  jz      short loc_1800522A4
0x180052289  mov     rdx, rcx; char *
0x18005228c  mov     dword ptr [rsp+220h+lpSubKey], ebx
0x180052290  mov     ecx, 609h; unsigned int
0x180052295  lea     r9, aFailedToReadOl; "Failed to read old indicator data versi"...
0x18005229c  mov     r8, r15; char *
0x18005229f  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800522a4  lea     rdx, aOutputregistry_12; "OutputRegistryMarker"
0x1800522ab  mov     rcx, r14; this
0x1800522ae  call    ?GetComponentStatus@ComponentStatusQuery@Appraiser@Compat@Windows@@QEBA?AW4ComponentStatus@234@PEBG@Z; Windows::Compat::Appraiser::ComponentStatusQuery::GetComponentStatus(ushort const *)
0x1800522b3  mov     r8d, eax
0x1800522b6  and     r8d, 3
0x1800522ba  cmp     r8b, 3
0x1800522be  jnz     short loc_1800522E0
0x1800522c0  and     eax, 5
0x1800522c3  cmp     al, 5
0x1800522c5  jz      short loc_1800522E0
0x1800522c7  lea     rdx, aOutputregistry_12; "OutputRegistryMarker"
0x1800522ce  mov     rcx, r14; this
0x1800522d1  call    ?GetComponentStatus@ComponentStatusQuery@Appraiser@Compat@Windows@@QEBA?AW4ComponentStatus@234@PEBG@Z; Windows::Compat::Appraiser::ComponentStatusQuery::GetComponentStatus(ushort const *)
0x1800522d6  and     eax, 5
0x1800522d9  mov     r15b, 1
0x1800522dc  cmp     al, 5
0x1800522de  jnz     short loc_1800522E3
0x1800522e0  mov     r15b, r12b
0x1800522e3  xor     r9d, r9d; Context
0x1800522e6  lea     rdx, ?InitOnceCallback@AppraiserSettings@Appraiser@Compat@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800522ed  xor     r8d, r8d; Parameter
0x1800522f0  lea     rcx, ?InitOnce@AppraiserSettings@Appraiser@Compat@Windows@@0T_RTL_RUN_ONCE@@A; InitOnce
0x1800522f7  call    cs:__imp_InitOnceExecuteOnce
0x1800522fd  mov     rax, qword ptr cs:xmmword_1802CB418
0x180052304  mov     r14d, r12d
0x180052307  mov     rbx, r12
0x18005230a  test    rax, rax
0x18005230d  jz      loc_18005241F
0x180052313  mov     r9, r12
0x180052316  cmp     rbx, rax
0x180052319  jnb     short loc_180052342
0x18005231b  mov     rax, rbx
0x18005231e  mov     qword ptr [rsp+220h+var_1B0], r12
0x180052323  mul     qword ptr cs:?SettingTelemetryAdditionalInitProperties@AppraiserSettings@Appraiser@Compat@Windows@@0VRtlNameValueArray@@A+8; RtlNameValueArray Windows::Compat::Appraiser::AppraiserSettings::SettingTelemetryAdditionalInitProperties
0x18005232a  test    rdx, rdx
0x18005232d  jnz     short loc_18005233F
0x18005232f  mov     rcx, qword ptr cs:xmmword_1802CB428+8
0x180052336  lea     r9, [rax+rcx]
0x18005233a  cmp     r9, rcx
0x18005233d  jnb     short loc_180052342
0x18005233f  mov     r9, r12
0x180052342  mov     rcx, [r9]
0x180052345  lea     rdx, aTelRecommended; "TEL_RECOMMENDEDDATAVERSIONFORINDICATORS"...
0x18005234c  mov     r8d, 28h ; '('
0x180052352  call    cs:__imp__o__wcsnicmp
0x180052358  test    eax, eax
0x18005235a  jnz     loc_18005240C
0x180052360  cmp     rbx, qword ptr cs:xmmword_1802CB418
0x180052367  mov     rax, r12
0x18005236a  jnb     short loc_180052393
0x18005236c  mov     rax, rbx
0x18005236f  mov     qword ptr [rsp+220h+var_1B0], r12
0x180052374  mul     qword ptr cs:?SettingTelemetryAdditionalInitProperties@AppraiserSettings@Appraiser@Compat@Windows@@0VRtlNameValueArray@@A+8; RtlNameValueArray Windows::Compat::Appraiser::AppraiserSettings::SettingTelemetryAdditionalInitProperties
0x18005237b  test    rdx, rdx
0x18005237e  jnz     short loc_180052390
0x180052380  add     rax, qword ptr cs:xmmword_1802CB428+8
0x180052387  cmp     rax, qword ptr cs:xmmword_1802CB428+8
0x18005238e  jnb     short loc_180052393
0x180052390  mov     rax, r12
0x180052393  mov     rcx, [rax]
0x180052396  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005239a  inc     rax
0x18005239d  cmp     [rcx+rax*2], r12w
0x1800523a2  jnz     short loc_18005239A
0x1800523a4  inc     rax
0x1800523a7  lea     rdx, [rbp+120h+EndPtr]; EndPtr
0x1800523ab  xor     r8d, r8d; Radix
0x1800523ae  lea     r12, [rcx+rax*2]
0x1800523b2  mov     rcx, r12; String
0x1800523b5  call    cs:__imp_wcstoul
0x1800523bb  mov     esi, eax
0x1800523bd  xor     eax, eax
0x1800523bf  test    esi, esi
0x1800523c1  jnz     short loc_180052402
0x1800523c3  mov     rcx, [rbp+120h+EndPtr]
0x1800523c7  cmp     [rcx], ax
0x1800523ca  jnz     short loc_1800523D1
0x1800523cc  cmp     r12, rcx
0x1800523cf  jnz     short loc_180052402
0x1800523d1  lea     rax, aRecommendedDat; "Recommended data version for indicators"...
0x1800523d8  mov     edx, 62Bh; bool
0x1800523dd  mov     [rsp+220h+var_1F8], rax; int
0x1800523e2  lea     r9, aWindowsCompatA_491; "Windows::Compat::Appraiser::TelemetryAp"...
0x1800523e9  lea     r8, aOnecoreBaseApp_75; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800523f0  mov     dword ptr [rsp+220h+lpSubKey], 8007000Dh; char *
0x1800523f8  mov     ecx, 1; this
0x1800523fd  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180052402  cmp     r14d, esi
0x180052405  cmovbe  r14d, esi
0x180052409  xor     r12d, r12d
0x18005240c  mov     rax, qword ptr cs:xmmword_1802CB418
0x180052413  inc     rbx
0x180052416  cmp     rbx, rax
0x180052419  jb      loc_180052313
0x18005241f  mov     esi, [rsp+220h+pvData]
0x180052423  test    r15b, r15b
0x180052426  cmovnz  esi, r13d
0x18005242a  jz      loc_18005262B
0x180052430  mov     rax, cs:?RegistryPathAppraiser@WicaFactory@Appraiser@Compat@Windows@@2PEAGEA; ushort * Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser
0x180052437  lea     rcx, aIndicatordatav; "IndicatorDataVersion"
0x18005243e  mov     [rsp+220h+var_1F8], rcx; unsigned __int16 *
0x180052443  mov     edx, 4; cbData
0x180052448  lea     rcx, [rsp+220h+Data]; lpData
0x18005244d  mov     dword ptr [rsp+220h+Data], r13d
0x180052452  mov     r8d, edx; dwType
0x180052455  mov     [rsp+220h+lpSubKey], rax; lpSubKey
0x18005245a  call    ?WriteValue@Registry@Shared@Compat@Windows@@SAJPEBE_KKPEAUHKEY__@@PEBG3@Z; Windows::Compat::Shared::Registry::WriteValue(uchar const *,unsigned __int64,ulong,HKEY__ *,ushort const *,ushort const *)
0x18005245f  mov     ebx, eax
0x180052461  test    eax, eax
0x180052463  jns     loc_1800525F6
0x180052469  lea     r9, aFailedToWriteN; "Failed to write new indicator data vers"...
0x180052470  mov     dword ptr [rsp+220h+var_1F0], eax; char *
0x180052474  mov     [rsp+220h+var_1F8], r9; int
0x180052479  lea     r8, aOnecoreBaseApp_75; "onecore\\base\\appcompat\\appraiser\\he"...
0x180052480  lea     r9, aWindowsCompatA_491; "Windows::Compat::Appraiser::TelemetryAp"...
0x180052487  mov     edx, 63Ah; bool
0x18005248c  mov     ecx, 1; this
0x180052491  mov     dword ptr [rsp+220h+lpSubKey], ebx; char *
0x180052495  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18005249a  jmp     loc_18005274B
0x18005249f  test    ebx, ebx
0x1800524a1  jns     loc_18005227F
0x1800524a7  lea     r9, aFailedToReadOl; "Failed to read old indicator data versi"...
0x1800524ae  mov     dword ptr [rsp+220h+var_1F0], ebx; char *
0x1800524b2  mov     [rsp+220h+var_1F8], r9; int
0x1800524b7  mov     r8, rcx; unsigned int
0x1800524ba  mov     r9, r15; char *
0x1800524bd  mov     dword ptr [rsp+220h+lpSubKey], ebx; char *
0x1800524c1  mov     edx, 609h; bool
0x1800524c6  mov     ecx, 1; this
0x1800524cb  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800524d0  lea     rcx, [rbp+120h+var_150]; this
0x1800524d4  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1800524d9  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x1800524e0  lea     rcx, [rbp+120h+var_150]
0x1800524e4  test    rax, rax
0x1800524e7  mov     rdx, r12
0x1800524ea  cmovnz  rcx, rax; this
0x1800524ee  lock xadd [rcx+88h], rdx; unsigned __int64
0x1800524f7  lea     r8, [rbp+120h+var_C0]; char *
0x1800524fb  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x180052500  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, r12b; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x180052507  jz      short loc_180052515
0x180052509  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x180052510  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x180052515  mov     rsi, cs:qword_1802C9628
0x18005251c  mov     eax, [rsi]
0x18005251e  cmp     eax, 5
0x180052521  jbe     loc_1800522A4
0x180052527  mov     rcx, [rsi+18h]
0x18005252b  mov     rdx, 200000000000h
0x180052535  mov     rax, [rsi+10h]
0x180052539  test    rdx, rax
0x18005253c  jz      loc_1800522A4
0x180052542  mov     rax, rcx
0x180052545  and     rax, rdx
0x180052548  cmp     rax, rcx
0x18005254b  jnz     loc_1800522A4
0x180052551  lea     rax, [rbp+120h+var_C0]
0x180052555  mov     [rsp+220h+var_1A8], ebx
0x180052559  mov     [rbp+120h+var_190], rax
0x18005255d  lea     rcx, [rbp+120h+SystemTime]; lpSystemTime
0x180052561  lea     rax, aOnecoreBaseApp_75; "onecore\\base\\appcompat\\appraiser\\he"...
0x180052568  mov     [rbp+120h+var_188], r15
0x18005256c  mov     [rbp+120h+var_180], rax
0x180052570  xorps   xmm0, xmm0
0x180052573  lea     rax, szValueBuf
0x18005257a  mov     dword ptr [rbp+120h+var_1A0], 609h
0x180052581  mov     [rbp+120h+var_178], rax
0x180052585  movups  xmmword ptr [rbp+120h+SystemTime.wYear], xmm0
0x180052589  call    cs:__imp_GetSystemTime
0x18005258f  movaps  xmm0, xmmword ptr [rbp+120h+SystemTime.wYear]
0x180052593  lea     rax, [rbp+120h+var_160]
0x180052597  mov     qword ptr [rsp+220h+var_1B0], rax
0x18005259c  lea     rdx, unk_18029F83C
0x1800525a3  lea     rax, [rbp+120h+var_190]
0x1800525a7  movdqa  [rbp+120h+var_160], xmm0
0x1800525ac  mov     [rsp+220h+var_1D0], rax
0x1800525b1  mov     rcx, rsi
0x1800525b4  lea     rax, [rsp+220h+var_1A8]
0x1800525b9  mov     [rsp+220h+var_1D8], rax
0x1800525be  lea     rax, [rbp+120h+var_188]
0x1800525c2  mov     [rsp+220h+var_1E0], rax
0x1800525c7  lea     rax, [rbp+120h+var_180]
0x1800525cb  mov     [rsp+220h+var_1E8], rax
0x1800525d0  lea     rax, [rbp+120h+var_1A0]
0x1800525d4  mov     [rsp+220h+var_1F0], rax
0x1800525d9  lea     rax, [rbp+120h+var_178]
0x1800525dd  mov     [rsp+220h+var_1F8], rax
0x1800525e2  lea     rax, [rsp+220h+var_1B0]
0x1800525e7  mov     [rsp+220h+lpSubKey], rax
0x1800525ec  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U4@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@656@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800525f1  jmp     loc_1800522A4
0x1800525f6  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800525fc  lea     r15, aWindowsCompatA_491; "Windows::Compat::Appraiser::TelemetryAp"...
0x180052603  lea     r13, aOnecoreBaseApp_75; "onecore\\base\\appcompat\\appraiser\\he"...
0x18005260a  test    al, 1
0x18005260c  jz      short loc_180052639
0x18005260e  lea     r9, aFailedToWriteN; "Failed to write new indicator data vers"...
0x180052615  mov     dword ptr [rsp+220h+lpSubKey], ebx
0x180052619  mov     r8, r15; char *
0x18005261c  mov     rdx, r13; char *
0x18005261f  mov     ecx, 63Ah; unsigned int
0x180052624  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180052629  jmp     short loc_180052639
0x18005262b  lea     r15, aWindowsCompatA_491; "Windows::Compat::Appraiser::TelemetryAp"...
0x180052632  lea     r13, aOnecoreBaseApp_75; "onecore\\base\\appcompat\\appraiser\\he"...
0x180052639  cmp     r14d, esi
0x18005263c  jbe     short loc_1800526AC
0x18005263e  mov     rax, cs:?RegistryPathAppraiser@WicaFactory@Appraiser@Compat@Windows@@2PEAGEA; ushort * Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser
0x180052645  lea     rcx, aIndicatoronese_0; "IndicatorOnesettingsEvidenceTimestamp"
0x18005264c  mov     [rsp+220h+var_1F8], rcx; unsigned __int16 *
0x180052651  mov     edx, 8; cbData
0x180052656  lea     rcx, [rsp+220h+var_1B0]; lpData
0x18005265b  mov     qword ptr [rsp+220h+var_1B0], r12
0x180052660  mov     [rsp+220h+lpSubKey], rax; lpSubKey
0x180052665  lea     r8d, [rdx+3]; dwType
0x180052669  call    ?WriteValue@Registry@Shared@Compat@Windows@@SAJPEBE_KKPEAUHKEY__@@PEBG3@Z; Windows::Compat::Shared::Registry::WriteValue(uchar const *,unsigned __int64,ulong,HKEY__ *,ushort const *,ushort const *)
0x18005266e  mov     ebx, eax
0x180052670  test    eax, eax
0x180052672  jns     short loc_180052694
0x180052674  lea     r9, aFailedToWriteN_0; "Failed to write new indicator onesettin"...
0x18005267b  mov     dword ptr [rsp+220h+var_1F0], eax
0x18005267f  mov     [rsp+220h+var_1F8], r9
0x180052684  mov     r8, r13
0x180052687  mov     r9, r15
0x18005268a  mov     edx, 640h
0x18005268f  jmp     loc_18005248C
0x180052694  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18005269a  test    al, 1
0x18005269c  jz      loc_180052748
0x1800526a2  mov     ecx, 640h
0x1800526a7  jmp     loc_180052732
0x1800526ac  mov     rbx, cs:?RegistryPathAppraiser@WicaFactory@Appraiser@Compat@Windows@@2PEAGEA; ushort * Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser
0x1800526b3  lea     rdx, ?InitOnceCallback@AppraiserSettings@Appraiser@Compat@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800526ba  xor     r9d, r9d; Context
0x1800526bd  lea     rcx, ?InitOnce@AppraiserSettings@Appraiser@Compat@Windows@@0T_RTL_RUN_ONCE@@A; InitOnce
0x1800526c4  xor     r8d, r8d; Parameter
0x1800526c7  call    cs:__imp_InitOnceExecuteOnce
0x1800526cd  mov     rax, cs:?SettingOneSettingsFreshnessTimestamp@AppraiserSettings@Appraiser@Compat@Windows@@0_KA; unsigned __int64 Windows::Compat::Appraiser::AppraiserSettings::SettingOneSettingsFreshnessTimestamp
0x1800526d4  lea     rcx, aIndicatoronese_0; "IndicatorOnesettingsEvidenceTimestamp"
0x1800526db  mov     [rsp+220h+var_1F8], rcx; unsigned __int16 *
0x1800526e0  mov     edx, 8; cbData
0x1800526e5  lea     rcx, [rsp+220h+var_1B0]; lpData
0x1800526ea  mov     qword ptr [rsp+220h+var_1B0], rax
0x1800526ef  mov     [rsp+220h+lpSubKey], rbx; lpSubKey
0x1800526f4  lea     r8d, [rdx+3]; dwType
0x1800526f8  call    ?WriteValue@Registry@Shared@Compat@Windows@@SAJPEBE_KKPEAUHKEY__@@PEBG3@Z; Windows::Compat::Shared::Registry::WriteValue(uchar const *,unsigned __int64,ulong,HKEY__ *,ushort const *,ushort const *)
0x1800526fd  mov     ebx, eax
0x1800526ff  test    eax, eax
0x180052701  jns     short loc_180052723
0x180052703  lea     r9, aFailedToWriteN_0; "Failed to write new indicator onesettin"...
0x18005270a  mov     dword ptr [rsp+220h+var_1F0], eax
0x18005270e  mov     [rsp+220h+var_1F8], r9
0x180052713  mov     r8, r13
0x180052716  mov     r9, r15
0x180052719  mov     edx, 645h
0x18005271e  jmp     loc_18005248C
  ... truncated ...
```
