# Windows::Compat::Appraiser::RegistryMarkerOutputter::DoOutput(RtlArray<Windows::Compat::Appraiser::IAsset *> *,Windows::Compat::Appraiser::WicaRun *)

- ea: `0x1800da600`
- end: `0x1800db000`
- name: `?DoOutput@RegistryMarkerOutputter@Appraiser@Compat@Windows@@UEAAJPEAV?$RtlArray@PEAVIAsset@Appraiser@Compat@Windows@@@@PEAUWicaRun@234@@Z`
- size: `2560`
- prototype: `__int64 __fastcall(Windows::Compat::Appraiser::RegistryMarkerOutputter *this)`
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002d00`
- `0x180008570`
- `0x180013c7c`
- `0x180013f90`
- `0x1800144c4`
- `0x1800151f4`
- `0x180029258`
- `0x18002ebb8`
- `0x1800301d0`
- `0x18008efd8`
- `0x1800a5d88`
- `0x1800d9f1c`
- `0x1800da2b0`
- `0x1800da600`
- `0x1800db008`
- `0x1800db694`
- `0x1800dbcac`
- `0x1800de208`
- `0x1800de72c`
- `0x1800df914`
- `0x1800e09dc`
- `0x1802174cc`
- `0x18021f010`

## import_xrefs

- `KERNEL32!InitOnceExecuteOnce` at `0x1800dad03`
- `KERNEL32!InitOnceExecuteOnce` at `0x1800dad03`
- `KERNEL32!GetSystemTime` at `0x1800dae86`
- `KERNEL32!GetSystemTime` at `0x1800dae86`
- `KERNEL32!GetProcessHeap` at `0x1800da667`
- `KERNEL32!GetProcessHeap` at `0x1800da667`
- `KERNEL32!HeapFree` at `0x1800dafcd`
- `KERNEL32!HeapFree` at `0x1800dafcd`

## string_xrefs

- `0x1800da71e`: `onecore\base\appcompat\appraiser\outputters\registrymarker.cpp`
- `0x1800da758`: `onecore\base\appcompat\appraiser\outputters\registrymarker.cpp`
- `0x1800da786`: `onecore\base\appcompat\appraiser\outputters\registrymarker.cpp`
- `0x1800da7df`: `onecore\base\appcompat\appraiser\outputters\registrymarker.cpp`
- `0x1800da84d`: `onecore\base\appcompat\appraiser\outputters\registrymarker.cpp`
- `0x1800da891`: `onecore\base\appcompat\appraiser\outputters\registrymarker.cpp`
- `0x1800da8c2`: `onecore\base\appcompat\appraiser\outputters\registrymarker.cpp`
- `0x1800da919`: `onecore\base\appcompat\appraiser\outputters\registrymarker.cpp`
- `0x1800da962`: `onecore\base\appcompat\appraiser\outputters\registrymarker.cpp`
- `0x1800da9a4`: `onecore\base\appcompat\appraiser\outputters\registrymarker.cpp`
- `0x1800da9e6`: `onecore\base\appcompat\appraiser\outputters\registrymarker.cpp`
- `0x1800daa20`: `onecore\base\appcompat\appraiser\outputters\registrymarker.cpp`
- `0x1800daa6e`: `onecore\base\appcompat\appraiser\outputters\registrymarker.cpp`
- `0x1800dab03`: `onecore\base\appcompat\appraiser\outputters\registrymarker.cpp`
- `0x1800dab6d`: `onecore\base\appcompat\appraiser\outputters\registrymarker.cpp`
- `0x1800dabf7`: `onecore\base\appcompat\appraiser\outputters\registrymarker.cpp`
- `0x1800dac82`: `onecore\base\appcompat\appraiser\outputters\registrymarker.cpp`
- `0x1800dacba`: `onecore\base\appcompat\appraiser\outputters\registrymarker.cpp`
- `0x1800da6dc`: `Windows::Compat::Appraiser::RegistryMarkerOutputter::DoOutput`
- `0x1800da82e`: `Windows::Compat::Appraiser::RegistryMarkerOutputter::DoOutput`
- `0x1800daa67`: `Windows::Compat::Appraiser::RegistryMarkerOutputter::DoOutput`
- `0x1800daad4`: `Windows::Compat::Appraiser::RegistryMarkerOutputter::DoOutput`
- `0x1800daafc`: `Windows::Compat::Appraiser::RegistryMarkerOutputter::DoOutput`
- `0x1800dab3e`: `Windows::Compat::Appraiser::RegistryMarkerOutputter::DoOutput`
- `0x1800dab66`: `Windows::Compat::Appraiser::RegistryMarkerOutputter::DoOutput`
- `0x1800dabf0`: `Windows::Compat::Appraiser::RegistryMarkerOutputter::DoOutput`
- `0x1800dac7b`: `Windows::Compat::Appraiser::RegistryMarkerOutputter::DoOutput`
- `0x1800dacb3`: `Windows::Compat::Appraiser::RegistryMarkerOutputter::DoOutput`
- `0x1800da839`: `Components did not succeed, appraiser data is not sufficient for markers and indicators.`
- `0x1800dac6b`: `Failed to write %ls indicators: [0x%x].`
- `0x1800dacac`: `Failed to write %ls indicators: [0x%x].`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Compat::Appraiser::RegistryMarkerOutputter::DoOutput(
        Windows::Compat::Appraiser::RegistryMarkerOutputter *this,
        __int64 a2,
        __int64 *a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // esi
  int ShouldOutputScanResults; // ebx
  const char *v10; // r9
  char v11; // dl
  int v12; // r12d
  unsigned __int8 v13; // r14
  unsigned int v14; // r15d
  unsigned __int8 IsNewAppraiserDataSufficient; // al
  const char *v16; // r9
  char v17; // dl
  int v18; // eax
  unsigned __int8 v19; // r13
  bool v20; // al
  __int64 v21; // r9
  int v22; // eax
  HANDLE *v23; // rdx
  int v24; // eax
  unsigned __int64 v25; // rax
  unsigned __int64 i; // rbx
  _QWORD *v27; // r8
  unsigned __int64 v28; // rax
  unsigned __int64 v29; // rcx
  int v30; // eax
  __int64 **v31; // rcx
  __int64 *j; // rax
  volatile signed __int64 *v33; // rcx
  void **v34; // rdx
  int v35; // r15d
  unsigned int v36; // ecx
  unsigned int v37; // ecx
  bool v38; // dl
  int v39; // eax
  int v40; // r8d
  int v41; // r9d
  struct Windows::Compat::Appraiser::IPropertyListEnumerator *v43; // [rsp+28h] [rbp-150h]
  struct Windows::Compat::Appraiser::IPropertyListEnumerator *v44; // [rsp+28h] [rbp-150h]
  const char *v45; // [rsp+30h] [rbp-148h]
  char *v46; // [rsp+38h] [rbp-140h]
  bool v47[8]; // [rsp+40h] [rbp-138h]
  unsigned __int8 v48; // [rsp+F8h] [rbp-80h] BYREF
  char v49; // [rsp+F9h] [rbp-7Fh] BYREF
  unsigned __int8 v50; // [rsp+FAh] [rbp-7Eh] BYREF
  unsigned __int8 v51; // [rsp+FBh] [rbp-7Dh]
  unsigned int v52; // [rsp+FCh] [rbp-7Ch] BYREF
  unsigned int v53; // [rsp+100h] [rbp-78h] BYREF
  BOOL v54; // [rsp+104h] [rbp-74h] BYREF
  int v55; // [rsp+108h] [rbp-70h] BYREF
  int v56; // [rsp+10Ch] [rbp-6Ch] BYREF
  int v57; // [rsp+110h] [rbp-68h] BYREF
  int v58; // [rsp+114h] [rbp-64h] BYREF
  int v59; // [rsp+118h] [rbp-60h] BYREF
  int v60; // [rsp+11Ch] [rbp-5Ch] BYREF
  int v61; // [rsp+120h] [rbp-58h] BYREF
  int v62; // [rsp+124h] [rbp-54h] BYREF
  int v63; // [rsp+128h] [rbp-50h] BYREF
  BOOL v64; // [rsp+12Ch] [rbp-4Ch] BYREF
  int v65; // [rsp+130h] [rbp-48h] BYREF
  int v66; // [rsp+134h] [rbp-44h] BYREF
  int v67; // [rsp+138h] [rbp-40h] BYREF
  int v68; // [rsp+13Ch] [rbp-3Ch] BYREF
  int v69; // [rsp+140h] [rbp-38h] BYREF
  int v70; // [rsp+144h] [rbp-34h] BYREF
  int v71; // [rsp+148h] [rbp-30h] BYREF
  void **v72; // [rsp+150h] [rbp-28h] BYREF
  __int64 v73; // [rsp+158h] [rbp-20h]
  __int64 v74; // [rsp+160h] [rbp-18h]
  struct _SYSTEMTIME *v75; // [rsp+168h] [rbp-10h] BYREF
  HANDLE hHeap[2]; // [rsp+170h] [rbp-8h] BYREF
  __int128 v77; // [rsp+180h] [rbp+8h]
  LPVOID lpMem[2]; // [rsp+190h] [rbp+18h]
  int v79; // [rsp+1A0h] [rbp+28h]
  char *v80; // [rsp+1A8h] [rbp+30h] BYREF
  __int64 v81; // [rsp+1B0h] [rbp+38h] BYREF
  char *v82; // [rsp+1B8h] [rbp+40h] BYREF
  const size_t *v83; // [rsp+1C0h] [rbp+48h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+1C8h] [rbp+50h] BYREF
  __int64 v85; // [rsp+1D8h] [rbp+60h]
  struct _SYSTEMTIME v86; // [rsp+1E8h] [rbp+70h] BYREF
  char v87[144]; // [rsp+1F8h] [rbp+80h] BYREF
  char v88[144]; // [rsp+288h] [rbp+110h] BYREF

  v85 = -2;
  v72 = &Windows::Compat::Appraiser::MetadataPropertyEnumerator::`vftable';
  v73 = 0;
  v74 = 0;
  *(_OWORD *)hHeap = 0;
  *(_OWORD *)lpMem = 0;
  hHeap[0] = GetProcessHeap();
  lpMem[0] = (LPVOID)16;
  v77 = 0;
  lpMem[1] = 0;
  hHeap[1] = (HANDLE)16;
  v79 = 0;
  RtlArray<RtlStringArray::RTL_STRING_ITEM>::Initialize(hHeap, v6, v7, 16);
  v8 = 1;
  v55 = 1;
  v56 = 1;
  v48 = 0;
  v50 = 0;
  v49 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v74 = *a3;
  HIDWORD(v73) = *((_DWORD *)a3 + 16);
  Windows::Compat::Appraiser::MetadataPropertyEnumerator::Reset((Windows::Compat::Appraiser::MetadataPropertyEnumerator *)&v72);
  if ( !*((_QWORD *)this + 112) )
    goto LABEL_11;
  ShouldOutputScanResults = Windows::Compat::Appraiser::RegistryMarkerOutputter::PartialScanAndShouldOutputScanResults(
                              this,
                              &v49,
                              a2,
                              &v72);
  if ( ShouldOutputScanResults >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x27Fu,
        "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
        "Windows::Compat::Appraiser::RegistryMarkerOutputter::DoOutput",
        "Failed to determine if partial scan should output scan results: [0x%x].",
        ShouldOutputScanResults);
    if ( !v49 )
    {
      ShouldOutputScanResults = 0;
      Windows::Compat::Appraiser::WriteLog(
        0,
        132,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
        "Windows::Compat::Appraiser::RegistryMarkerOutputter::DoOutput",
        0,
        (int)"Not running outputter: No interesting assets found for OutputPartialScanUsefulResultTable.",
        v46);
      goto LABEL_5;
    }
LABEL_11:
    ShouldOutputScanResults = Windows::Compat::Appraiser::RegistryMarkerOutputter::AreGeneralTelMarkersUsable(
                                this,
                                &v50,
                                &v53,
                                a2);
    if ( ShouldOutputScanResults < 0 )
    {
      v10 = "Failed to determine general tel marker usablility: [0x%x].";
      v11 = -114;
      goto LABEL_4;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x28Eu,
        "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
        "Windows::Compat::Appraiser::RegistryMarkerOutputter::DoOutput",
        "Failed to determine general tel marker usablility: [0x%x].",
        ShouldOutputScanResults);
    if ( !wcscmp_0(L"UNV", *((const wchar_t **)this + 46)) )
    {
      LOBYTE(v12) = 1;
      v14 = 1;
      goto LABEL_39;
    }
    IsNewAppraiserDataSufficient = Windows::Compat::Appraiser::Utilities::IsNewAppraiserDataSufficient(
                                     &v54,
                                     hHeap,
                                     a3[7],
                                     (char *)this + 208);
    v12 = IsNewAppraiserDataSufficient;
    if ( !IsNewAppraiserDataSufficient )
      Windows::Compat::Appraiser::WriteLog(
        0,
        167,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
        "Windows::Compat::Appraiser::RegistryMarkerOutputter::DoOutput",
        0,
        (int)"Components did not succeed, appraiser data is not sufficient for markers and indicators.",
        v46);
    ShouldOutputScanResults = Windows::Compat::Appraiser::RegistryMarkerOutputter::AreOldAppraiserMarkersUsable(
                                this,
                                &v48,
                                &v52,
                                a2);
    if ( ShouldOutputScanResults < 0 )
    {
      v16 = "Failed to determine old appraiser marker usablility: [0x%x].";
      v17 = -85;
LABEL_21:
      LODWORD(v46) = ShouldOutputScanResults;
      LODWORD(v45) = (_DWORD)v16;
LABEL_22:
      LODWORD(v43) = ShouldOutputScanResults;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        v17,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
        "Windows::Compat::Appraiser::RegistryMarkerOutputter::DoOutput",
        (const char *)v43,
        (int)v45,
        v46);
      goto LABEL_6;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x2ABu,
        "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
        "Windows::Compat::Appraiser::RegistryMarkerOutputter::DoOutput",
        "Failed to determine old appraiser marker usablility: [0x%x].",
        ShouldOutputScanResults);
    if ( (_BYTE)v12 )
    {
      ShouldOutputScanResults = Windows::Compat::Appraiser::RegistryMarkerOutputter::FillNewAppraiserMarkers(
                                  this,
                                  a2,
                                  &v72);
      if ( ShouldOutputScanResults < 0 )
      {
        v16 = "Failed to determine new appraiser markers: [0x%x].";
        v17 = -76;
        goto LABEL_21;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x2B4u,
          "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
          "Windows::Compat::Appraiser::RegistryMarkerOutputter::DoOutput",
          "Failed to determine new appraiser markers: [0x%x].",
          ShouldOutputScanResults);
      v51 = 1;
      v18 = Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteNewAppraiserMarkers(this);
      ShouldOutputScanResults = v18;
      v56 = v18;
      if ( v18 < 0 )
      {
        LODWORD(v43) = v18;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          184,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
          "Windows::Compat::Appraiser::RegistryMarkerOutputter::DoOutput",
          (const char *)v43,
          (int)"Failed to output new %ls appraiser markers: [0x%x].",
          *((const char **)this + 46),
          v18);
        goto LABEL_6;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x2B8u,
          "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
          "Windows::Compat::Appraiser::RegistryMarkerOutputter::DoOutput",
          "Failed to output new %ls appraiser markers: [0x%x].",
          *((const wchar_t **)this + 46),
          v18);
    }
    else
    {
      v19 = v48;
      if ( !v48 )
      {
        if ( !*((_BYTE *)this + 340) )
        {
          ShouldOutputScanResults = 1;
          Windows::Compat::Appraiser::WriteLog(
            0,
            196,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
            "Windows::Compat::Appraiser::RegistryMarkerOutputter::DoOutput",
            0,
            (int)"Not running outputter: Appraiser cannot provide sufficient marker data.",
            v46);
          v13 = 0;
          goto LABEL_75;
        }
        v20 = Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors();
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)v20,
          201,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
          "Windows::Compat::Appraiser::RegistryMarkerOutputter::DoOutput",
          0,
          (int)"Running marker outputter even though Appraiser cannot provide sufficient data.",
          v46);
        v14 = 5;
        goto LABEL_39;
      }
    }
    v14 = (2 * v12 + 2) | 1;
LABEL_39:
    if ( !v50 && *((_BYTE *)this + 317) )
    {
      ShouldOutputScanResults = 1;
      Windows::Compat::Appraiser::WriteLog(
        0,
        215,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
        "Windows::Compat::Appraiser::RegistryMarkerOutputter::DoOutput",
        0,
        (int)"Not running outputter: GeneralTel cannot provide sufficient marker data.",
        v46);
      goto LABEL_6;
    }
    LODWORD(v21) = (_DWORD)this + 376;
    if ( (v14 & 2) == 0 )
      v21 = *((_QWORD *)this + 46);
    v22 = Windows::Compat::Appraiser::RegistryMarkerOutputter::FillIndicatorsOfSpecificTypes(
            (int)this + 64,
            a2,
            v14,
            v21,
            (struct Windows::Compat::Appraiser::IPropertyListEnumerator *)&v72,
            *((struct Windows::Compat::Appraiser::Table **)this + 113));
    ShouldOutputScanResults = v22;
    if ( v22 >= 0 )
    {
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x2E9u,
          "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
          "Windows::Compat::Appraiser::RegistryMarkerOutputter::DoOutput",
          "Failed to determine indicators: [0x%x].",
          v22);
      v23 = hHeap;
      if ( (v14 & 4) == 0 )
        v23 = 0;
      v24 = Windows::Compat::Appraiser::RegistryMarkerOutputter::FillNonDataIndicators(
              this,
              (struct RtlStringArray *)v23);
      ShouldOutputScanResults = v24;
      if ( v24 >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x2ECu,
            "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
            "Windows::Compat::Appraiser::RegistryMarkerOutputter::DoOutput",
            "Failed to determine non-data indicators: [0x%x].",
            v24);
        v25 = *((_QWORD *)this + 124);
        if ( v25 )
        {
          for ( i = 0; i < v25; ++i )
          {
            v27 = 0;
            if ( i < v25 )
            {
              v75 = 0;
              v28 = *((_QWORD *)this + 123) * i;
              if ( !is_mul_ok(*((_QWORD *)this + 123), i)
                || (v29 = *((_QWORD *)this + 127), v27 = (_QWORD *)(v29 + v28), v29 + v28 < v29) )
              {
                v27 = 0;
              }
            }
            Windows::Compat::Appraiser::RegistryMarkerOutputter::ParseIndicatorToDedupe(this, v14, *v27);
            v25 = *((_QWORD *)this + 124);
          }
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x2EEu,
            "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
            "Windows::Compat::Appraiser::RegistryMarkerOutputter::DoOutput",
            "Failed to determine indicators to dedupe, swallowing: [0x%x].",
            0);
        v13 = 1;
        v30 = Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteIndicators(
                (unsigned __int64 *)this + 8,
                (unsigned __int64 *)this + 14,
                (struct _SYSTEMTIME *)this + 10,
                (Windows::Compat::Appraiser::RegistryMarkerOutputter *)((char *)this + 256),
                v14,
                (int)L"TargetVersionUpgradeExperienceIndicators",
                (unsigned __int16 *)this + 188,
                *((_BYTE *)this + 360),
                (__int64)this + 912);
        ShouldOutputScanResults = v30;
        v55 = v30;
        if ( v30 >= 0 )
        {
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x2FEu,
              "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
              "Windows::Compat::Appraiser::RegistryMarkerOutputter::DoOutput",
              "Failed to write %ls indicators: [0x%x].",
              (const wchar_t *)this + 188,
              v30);
          if ( *((_QWORD *)this + 116) )
          {
            v31 = (__int64 **)*((_QWORD *)this + 115);
            for ( j = *v31; j != (__int64 *)v31; j = (__int64 *)*j )
            {
              if ( !*((_DWORD *)j + 12) )
                goto LABEL_73;
            }
            InitOnceExecuteOnce(
              &Windows::Compat::Appraiser::RegistryMarkerOutputter::IndicatorDeltasInitOnce,
              Windows::Compat::Appraiser::RegistryMarkerOutputter::IndicatorDeltasInitOnceCallback,
              0,
              0);
          }
LABEL_73:
          ShouldOutputScanResults = 0;
        }
        else
        {
          *(_DWORD *)v47 = v30;
          LODWORD(v44) = v30;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            254,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
            "Windows::Compat::Appraiser::RegistryMarkerOutputter::DoOutput",
            (const char *)v44,
            (int)"Failed to write %ls indicators: [0x%x].",
            (const char *)this + 376,
            *(_QWORD *)v47);
        }
        goto LABEL_74;
      }
      LODWORD(v46) = v24;
      v45 = "Failed to determine non-data indicators: [0x%x].";
      v17 = -20;
    }
    else
    {
      LODWORD(v46) = v22;
      v45 = "Failed to determine indicators: [0x%x].";
      v17 = -23;
    }
    goto LABEL_22;
  }
  v10 = "Failed to determine if partial scan should output scan results: [0x%x].";
  v11 = 127;
LABEL_4:
  LODWORD(v46) = ShouldOutputScanResults;
  LODWORD(v43) = ShouldOutputScanResults;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    v11,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
    "Windows::Compat::Appraiser::RegistryMarkerOutputter::DoOutput",
    (const char *)v43,
    (int)v10,
    v46);
LABEL_5:
  LOBYTE(v12) = 0;
LABEL_6:
  v13 = 0;
LABEL_74:
  v19 = v48;
LABEL_75:
  TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v87);
  v33 = (volatile signed __int64 *)v87;
  if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
    v33 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v33,
    _InterlockedExchangeAdd64(v33 + 17, 0),
    v88);
  if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
    UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v34);
  v35 = qword_1802C9628;
  if ( *(_DWORD *)qword_1802C9628 > 5u
    && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000020LL) != 0
    && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000020LL) == *(_QWORD *)(qword_1802C9628 + 24) )
  {
    v80 = v88;
    v81 = 0x1000000;
    v36 = v52;
    v52 = (v52 >> 4) & 1;
    v57 = (v36 >> 2) & 1;
    v58 = (v36 >> 1) & 1;
    v59 = v36 & 1;
    v37 = v53;
    v53 = (v53 >> 4) & 1;
    v60 = (v37 >> 3) & 1;
    v61 = (v37 >> 2) & 1;
    v62 = (v37 >> 1) & 1;
    v63 = v37 & 1;
    v38 = v54;
    v54 = (v54 & 5) == 5;
    v64 = (v38 & 3) == 3;
    v39 = 1;
    if ( v13 )
      v39 = v55;
    v55 = v39;
    if ( v51 )
      v8 = v56;
    v56 = v8;
    v65 = ShouldOutputScanResults;
    v66 = v13;
    v67 = v51;
    v68 = *((unsigned __int8 *)this + 340);
    v69 = v19;
    v70 = v50;
    v71 = (unsigned __int8)v12;
    v82 = (char *)this + 376;
    v83 = &szValueBuf;
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    v86 = SystemTime;
    v75 = &v86;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
      v35,
      (unsigned int)&unk_1802A4063,
      v40,
      v41,
      (__int64)&v75,
      (__int64)&v83,
      (__int64)&v82,
      (__int64)&v71,
      (__int64)&v70,
      (__int64)&v69,
      (__int64)&v68,
      (__int64)&v67,
      (__int64)&v66,
      (__int64)&v65,
      (__int64)&v56,
      (__int64)&v55,
      (__int64)&v64,
      (__int64)&v54,
      (__int64)&v63,
      (__int64)&v62,
      (__int64)&v61,
      (__int64)&v60,
      (__int64)&v53,
      (__int64)&v59,
      (__int64)&v58,
      (__int64)&v57,
      (__int64)&v52,
      (__int64)&v81,
      (__int64)&v80);
  }
  RtlStringArray::Clear((RtlStringArray *)hHeap);
  if ( lpMem[1] )
    HeapFree(hHeap[0], 0, lpMem[1]);
  return (unsigned int)ShouldOutputScanResults;
}

```

## disassembly

```asm
0x1800da600  mov     rax, rsp
0x1800da603  push    rbp
0x1800da604  push    rsi
0x1800da605  push    rdi
0x1800da606  push    r12
0x1800da608  push    r13
0x1800da60a  push    r14
0x1800da60c  push    r15
0x1800da60e  lea     rbp, [rax-1E8h]
0x1800da615  sub     rsp, 320h
0x1800da61c  mov     [rbp+1E0h+var_180], 0FFFFFFFFFFFFFFFEh
0x1800da624  mov     [rax+20h], rbx
0x1800da628  mov     rax, cs:__security_cookie
0x1800da62f  xor     rax, rsp
0x1800da632  mov     [rbp+1E0h+var_40], rax
0x1800da639  mov     r15, r8
0x1800da63c  mov     r14, rdx
0x1800da63f  mov     rdi, rcx
0x1800da642  xor     r13d, r13d
0x1800da645  mov     [rbp+1E0h+var_25F], r13b
0x1800da649  lea     rax, ??_7MetadataPropertyEnumerator@Appraiser@Compat@Windows@@6B@; const Windows::Compat::Appraiser::MetadataPropertyEnumerator::`vftable'
0x1800da650  mov     [rbp+1E0h+var_208], rax
0x1800da654  mov     [rbp+1E0h+var_200], r13
0x1800da658  mov     [rbp+1E0h+var_1F8], r13
0x1800da65c  xorps   xmm0, xmm0
0x1800da65f  movups  xmmword ptr [rbp+1E0h+hHeap], xmm0
0x1800da663  movups  xmmword ptr [rbp+1E0h+lpMem], xmm0
0x1800da667  call    cs:__imp_GetProcessHeap
0x1800da66d  mov     [rbp+1E0h+hHeap], rax
0x1800da671  lea     r9d, [r13+10h]
0x1800da675  mov     [rbp+1E0h+lpMem], r9
0x1800da679  xorps   xmm0, xmm0
0x1800da67c  movdqu  [rbp+1E0h+var_1D8], xmm0
0x1800da681  mov     [rbp+1E0h+lpMem+8], r13
0x1800da685  mov     [rbp+1E0h+hHeap+8], r9
0x1800da689  mov     [rbp+1E0h+var_1B8], r13d
0x1800da68d  lea     rcx, [rbp+1E0h+hHeap]
0x1800da691  call    ?Initialize@?$RtlArray@URTL_STRING_ITEM@RtlStringArray@@@@QEAAJPEAX_K1H@Z; RtlArray<RtlStringArray::RTL_STRING_ITEM>::Initialize(void *,unsigned __int64,unsigned __int64,int)
0x1800da696  nop
0x1800da697  lea     esi, [r13+1]
0x1800da69b  mov     [rbp+1E0h+var_250], esi
0x1800da69e  mov     [rbp+1E0h+var_24C], esi
0x1800da6a1  mov     [rbp+1E0h+var_260], r13b
0x1800da6a5  mov     [rbp+1E0h+var_25E], r13b
0x1800da6a9  mov     [rbp+1E0h+var_25F], r13b
0x1800da6ad  mov     [rbp+1E0h+var_25D], r13b
0x1800da6b1  mov     [rbp+1E0h+var_25C], r13d
0x1800da6b5  mov     [rbp+1E0h+var_258], r13d
0x1800da6b9  mov     [rbp+1E0h+var_254], r13d
0x1800da6bd  mov     rax, [r15]
0x1800da6c0  mov     [rbp+1E0h+var_1F8], rax
0x1800da6c4  mov     eax, [r15+40h]
0x1800da6c8  mov     dword ptr [rbp+1E0h+var_200+4], eax
0x1800da6cb  mov     rax, [rbp+1E0h+var_208]
0x1800da6cf  lea     rcx, [rbp+1E0h+var_208]
0x1800da6d3  mov     rax, [rax+8]
0x1800da6d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da6dc  lea     r12, aWindowsCompatA_697; "Windows::Compat::Appraiser::RegistryMar"...
0x1800da6e3  cmp     [rdi+380h], r13
0x1800da6ea  jz      loc_1800DA79B
0x1800da6f0  lea     r9, [rbp+1E0h+var_208]
0x1800da6f4  mov     r8, r14
0x1800da6f7  lea     rdx, [rbp+1E0h+var_25F]
0x1800da6fb  mov     rcx, rdi
0x1800da6fe  call    ?PartialScanAndShouldOutputScanResults@RegistryMarkerOutputter@Appraiser@Compat@Windows@@AEAAJAEA_NPEAV?$RtlArray@PEAVIAsset@Appraiser@Compat@Windows@@@@PEAVIPropertyListEnumerator@234@@Z; Windows::Compat::Appraiser::RegistryMarkerOutputter::PartialScanAndShouldOutputScanResults(bool &,RtlArray<Windows::Compat::Appraiser::IAsset *> *,Windows::Compat::Appraiser::IPropertyListEnumerator *)
0x1800da703  mov     ebx, eax
0x1800da705  test    eax, eax
0x1800da707  jns     short loc_1800DA73E
0x1800da709  lea     r9, aFailedToDeterm_14; "Failed to determine if partial scan sho"...
0x1800da710  mov     edx, 27Fh; bool
0x1800da715  mov     dword ptr [rsp+350h+var_320], ebx; char *
0x1800da719  mov     [rsp+350h+var_328], r9; int
0x1800da71e  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800da725  mov     r9, r12; char *
0x1800da728  mov     dword ptr [rsp+350h+var_330], ebx; char *
0x1800da72c  mov     ecx, esi; this
0x1800da72e  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800da733  mov     r12b, r13b
0x1800da736  mov     r14b, r13b
0x1800da739  jmp     loc_1800DAD0B
0x1800da73e  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800da744  and     eax, esi
0x1800da746  test    al, al
0x1800da748  jz      short loc_1800DA769
0x1800da74a  mov     dword ptr [rsp+350h+var_330], ebx
0x1800da74e  lea     r9, aFailedToDeterm_14; "Failed to determine if partial scan sho"...
0x1800da755  mov     r8, r12; char *
0x1800da758  lea     rdx, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800da75f  mov     ecx, 27Fh; unsigned int
0x1800da764  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800da769  cmp     [rbp+1E0h+var_25F], r13b
0x1800da76d  jnz     short loc_1800DA79B
0x1800da76f  mov     ebx, r13d
0x1800da772  lea     rax, aNotRunningOutp_1; "Not running outputter: No interesting a"...
0x1800da779  mov     [rsp+350h+var_328], rax; int
0x1800da77e  mov     [rsp+350h+var_330], r13; char *
0x1800da783  mov     r9, r12; char *
0x1800da786  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800da78d  mov     edx, 284h; bool
0x1800da792  xor     ecx, ecx; this
0x1800da794  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800da799  jmp     short loc_1800DA733
0x1800da79b  mov     r9, r14
0x1800da79e  lea     r8, [rbp+1E0h+var_258]
0x1800da7a2  lea     rdx, [rbp+1E0h+var_25E]
0x1800da7a6  mov     rcx, rdi
0x1800da7a9  call    ?AreGeneralTelMarkersUsable@RegistryMarkerOutputter@Appraiser@Compat@Windows@@AEAAJAEA_NAEAKPEAV?$RtlArray@PEAVIAsset@Appraiser@Compat@Windows@@@@@Z; Windows::Compat::Appraiser::RegistryMarkerOutputter::AreGeneralTelMarkersUsable(bool &,ulong &,RtlArray<Windows::Compat::Appraiser::IAsset *> *)
0x1800da7ae  mov     ebx, eax
0x1800da7b0  test    eax, eax
0x1800da7b2  jns     short loc_1800DA7C5
0x1800da7b4  lea     r9, aFailedToDeterm_0; "Failed to determine general tel marker "...
0x1800da7bb  mov     edx, 28Eh
0x1800da7c0  jmp     loc_1800DA715
0x1800da7c5  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800da7cb  and     eax, esi
0x1800da7cd  test    al, al
0x1800da7cf  jz      short loc_1800DA7F0
0x1800da7d1  mov     dword ptr [rsp+350h+var_330], ebx
0x1800da7d5  lea     r9, aFailedToDeterm_0; "Failed to determine general tel marker "...
0x1800da7dc  mov     r8, r12; char *
0x1800da7df  lea     rdx, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800da7e6  mov     ecx, 28Eh; unsigned int
0x1800da7eb  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800da7f0  mov     rdx, [rdi+170h]; String2
0x1800da7f7  lea     rcx, aUnv; "UNV"
0x1800da7fe  call    wcscmp_0
0x1800da803  test    eax, eax
0x1800da805  jnz     short loc_1800DA812
0x1800da807  mov     r12b, sil
0x1800da80a  mov     r15d, esi
0x1800da80d  jmp     loc_1800DAA45
0x1800da812  lea     r9, [rdi+0D0h]
0x1800da819  mov     r8, [r15+38h]
0x1800da81d  lea     rdx, [rbp+1E0h+hHeap]
0x1800da821  lea     rcx, [rbp+1E0h+var_254]
0x1800da825  call    ?IsNewAppraiserDataSufficient@Utilities@Appraiser@Compat@Windows@@SA_NAEAW4ComponentStatus@234@AEAVRtlStringArray@@PEAVComponentStatusQuery@234@PEAV?$RtlArray@PEAUListTable@Appraiser@Compat@Windows@@@@@Z; Windows::Compat::Appraiser::Utilities::IsNewAppraiserDataSufficient(Windows::Compat::Appraiser::ComponentStatus &,RtlStringArray &,Windows::Compat::Appraiser::ComponentStatusQuery *,RtlArray<Windows::Compat::Appraiser::ListTable *> *)
0x1800da82a  movzx   r12d, al
0x1800da82e  lea     r15, aWindowsCompatA_697; "Windows::Compat::Appraiser::RegistryMar"...
0x1800da835  test    al, al
0x1800da837  jnz     short loc_1800DA860
0x1800da839  lea     rax, aComponentsDidN; "Components did not succeed, appraiser d"...
0x1800da840  mov     [rsp+350h+var_328], rax; int
0x1800da845  mov     [rsp+350h+var_330], r13; char *
0x1800da84a  mov     r9, r15; char *
0x1800da84d  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800da854  mov     edx, 2A7h; bool
0x1800da859  xor     ecx, ecx; this
0x1800da85b  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800da860  mov     r9, r14
0x1800da863  lea     r8, [rbp+1E0h+var_25C]
0x1800da867  lea     rdx, [rbp+1E0h+var_260]
0x1800da86b  mov     rcx, rdi
0x1800da86e  call    ?AreOldAppraiserMarkersUsable@RegistryMarkerOutputter@Appraiser@Compat@Windows@@AEAAJAEA_NAEAKPEAV?$RtlArray@PEAVIAsset@Appraiser@Compat@Windows@@@@@Z; Windows::Compat::Appraiser::RegistryMarkerOutputter::AreOldAppraiserMarkersUsable(bool &,ulong &,RtlArray<Windows::Compat::Appraiser::IAsset *> *)
0x1800da873  mov     ebx, eax
0x1800da875  test    eax, eax
0x1800da877  jns     short loc_1800DA8A8
0x1800da879  lea     r9, aFailedToDeterm_6; "Failed to determine old appraiser marke"...
0x1800da880  mov     edx, 2ABh; bool
0x1800da885  mov     dword ptr [rsp+350h+var_320], ebx; char *
0x1800da889  mov     [rsp+350h+var_328], r9; int
0x1800da88e  mov     r9, r15; char *
0x1800da891  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800da898  mov     dword ptr [rsp+350h+var_330], ebx; char *
0x1800da89c  mov     ecx, esi; this
0x1800da89e  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800da8a3  jmp     loc_1800DA736
0x1800da8a8  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800da8ae  and     eax, esi
0x1800da8b0  test    al, al
0x1800da8b2  jz      short loc_1800DA8D3
0x1800da8b4  mov     dword ptr [rsp+350h+var_330], ebx
0x1800da8b8  lea     r9, aFailedToDeterm_6; "Failed to determine old appraiser marke"...
0x1800da8bf  mov     r8, r15; char *
0x1800da8c2  lea     rdx, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800da8c9  mov     ecx, 2ABh; unsigned int
0x1800da8ce  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800da8d3  test    r12b, r12b
0x1800da8d6  jz      loc_1800DA9BA
0x1800da8dc  lea     r8, [rbp+1E0h+var_208]
0x1800da8e0  mov     rdx, r14
0x1800da8e3  mov     rcx, rdi
0x1800da8e6  call    ?FillNewAppraiserMarkers@RegistryMarkerOutputter@Appraiser@Compat@Windows@@AEAAJPEAV?$RtlArray@PEAVIAsset@Appraiser@Compat@Windows@@@@PEAVIPropertyListEnumerator@234@@Z; Windows::Compat::Appraiser::RegistryMarkerOutputter::FillNewAppraiserMarkers(RtlArray<Windows::Compat::Appraiser::IAsset *> *,Windows::Compat::Appraiser::IPropertyListEnumerator *)
0x1800da8eb  mov     ebx, eax
0x1800da8ed  test    eax, eax
0x1800da8ef  jns     short loc_1800DA8FF
0x1800da8f1  lea     r9, aFailedToDeterm_11; "Failed to determine new appraiser marke"...
0x1800da8f8  mov     edx, 2B4h
0x1800da8fd  jmp     short loc_1800DA885
0x1800da8ff  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800da905  and     eax, esi
0x1800da907  test    al, al
0x1800da909  jz      short loc_1800DA92A
0x1800da90b  mov     dword ptr [rsp+350h+var_330], ebx
0x1800da90f  lea     r9, aFailedToDeterm_11; "Failed to determine new appraiser marke"...
0x1800da916  mov     r8, r15; char *
0x1800da919  lea     rdx, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800da920  mov     ecx, 2B4h; unsigned int
0x1800da925  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800da92a  mov     [rbp+1E0h+var_25D], sil
0x1800da92e  mov     rcx, rdi; this
0x1800da931  call    ?WriteNewAppraiserMarkers@RegistryMarkerOutputter@Appraiser@Compat@Windows@@AEAAJXZ; Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteNewAppraiserMarkers(void)
0x1800da936  mov     ebx, eax
0x1800da938  mov     [rbp+1E0h+var_24C], eax
0x1800da93b  test    eax, eax
0x1800da93d  jns     short loc_1800DA97A
0x1800da93f  mov     dword ptr [rsp+350h+var_318], eax
0x1800da943  mov     rax, [rdi+170h]
0x1800da94a  mov     [rsp+350h+var_320], rax; char *
0x1800da94f  lea     r9, aFailedToOutput; "Failed to output new %ls appraiser mark"...
0x1800da956  mov     [rsp+350h+var_328], r9; int
0x1800da95b  mov     dword ptr [rsp+350h+var_330], ebx; char *
0x1800da95f  mov     r9, r15; char *
0x1800da962  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800da969  mov     edx, 2B8h; bool
0x1800da96e  mov     ecx, esi; this
0x1800da970  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800da975  jmp     loc_1800DA736
0x1800da97a  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800da980  and     eax, esi
0x1800da982  test    al, al
0x1800da984  jz      loc_1800DAA3A
0x1800da98a  mov     dword ptr [rsp+350h+var_328], ebx
0x1800da98e  mov     rax, [rdi+170h]
0x1800da995  mov     [rsp+350h+var_330], rax
0x1800da99a  lea     r9, aFailedToOutput; "Failed to output new %ls appraiser mark"...
0x1800da9a1  mov     r8, r15; char *
0x1800da9a4  lea     rdx, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800da9ab  mov     ecx, 2B8h; unsigned int
0x1800da9b0  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800da9b5  jmp     loc_1800DAA3A
0x1800da9ba  mov     r13b, [rbp+1E0h+var_260]
0x1800da9be  test    r13b, r13b
0x1800da9c1  jnz     short loc_1800DAA37
0x1800da9c3  cmp     [rdi+154h], r13b
0x1800da9ca  jnz     short loc_1800DAA01
0x1800da9cc  mov     ebx, esi
0x1800da9ce  lea     rax, aNotRunningOutp; "Not running outputter: Appraiser cannot"...
0x1800da9d5  mov     [rsp+350h+var_328], rax; int
0x1800da9da  mov     [rsp+350h+var_330], 0; char *
0x1800da9e3  mov     r9, r15; char *
0x1800da9e6  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800da9ed  mov     edx, 2C4h; bool
0x1800da9f2  xor     ecx, ecx; this
0x1800da9f4  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800da9f9  xor     r14b, r14b
0x1800da9fc  jmp     loc_1800DAD0F
0x1800daa01  call    ?TreatWarningsAsErrors@AppraiserTestHooks@Appraiser@Compat@Windows@@SA_NXZ; Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors(void)
0x1800daa06  movzx   ecx, al; this
0x1800daa09  lea     rax, aRunningMarkerO; "Running marker outputter even though Ap"...
0x1800daa10  mov     [rsp+350h+var_328], rax; int
0x1800daa15  xor     r13d, r13d
0x1800daa18  mov     [rsp+350h+var_330], r13; char *
0x1800daa1d  mov     r9, r15; char *
0x1800daa20  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800daa27  mov     edx, 2C9h; bool
0x1800daa2c  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800daa31  lea     r15d, [r13+5]
0x1800daa35  jmp     short loc_1800DAA45
0x1800daa37  xor     r13d, r13d
0x1800daa3a  lea     r15d, ds:2[r12*2]
0x1800daa42  or      r15d, esi
0x1800daa45  cmp     [rbp+1E0h+var_25E], r13b
0x1800daa49  jnz     short loc_1800DAA86
0x1800daa4b  cmp     [rdi+13Dh], r13b
0x1800daa52  jz      short loc_1800DAA86
0x1800daa54  mov     ebx, esi
0x1800daa56  lea     rax, aNotRunningOutp_0; "Not running outputter: GeneralTel canno"...
0x1800daa5d  mov     [rsp+350h+var_328], rax; int
0x1800daa62  mov     [rsp+350h+var_330], r13; char *
0x1800daa67  lea     r9, aWindowsCompatA_697; "Windows::Compat::Appraiser::RegistryMar"...
0x1800daa6e  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800daa75  mov     edx, 2D7h; bool
0x1800daa7a  xor     ecx, ecx; this
0x1800daa7c  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800daa81  jmp     loc_1800DA736
0x1800daa86  mov     rcx, [rdi+388h]
0x1800daa8d  test    r15b, 2
0x1800daa91  lea     r9, [rdi+178h]
0x1800daa98  jnz     short loc_1800DAAA1
0x1800daa9a  mov     r9, [rdi+170h]; int
0x1800daaa1  mov     [rsp+350h+var_328], rcx; struct Windows::Compat::Appraiser::Table *
0x1800daaa6  lea     rcx, [rbp+1E0h+var_208]
0x1800daaaa  mov     [rsp+350h+var_330], rcx; struct Windows::Compat::Appraiser::IPropertyListEnumerator *
0x1800daaaf  mov     r8d, r15d; int
0x1800daab2  mov     rdx, r14; int
0x1800daab5  lea     rcx, [rdi+40h]; int
0x1800daab9  call    ?FillIndicatorsOfSpecificTypes@RegistryMarkerOutputter@Appraiser@Compat@Windows@@CAJAEAV?$RtlArray@VRegistryIndicatorConstraintEntry@Appraiser@Compat@Windows@@@@PEAV?$RtlArray@PEAVIAsset@Appraiser@Compat@Windows@@@@W4IndicatorType@234@PEBGPEAVIPropertyListEnumerator@234@PEAVTable@234@@Z; Windows::Compat::Appraiser::RegistryMarkerOutputter::FillIndicatorsOfSpecificTypes(RtlArray<Windows::Compat::Appraiser::RegistryIndicatorConstraintEntry> &,RtlArray<Windows::Compat::Appraiser::IAsset *> *,Windows::Compat::Appraiser::IndicatorType,ushort const *,Windows::Compat::Appraiser::IPropertyListEnumerator *,Windows::Compat::Appraiser::Table *)
0x1800daabe  mov     ebx, eax
0x1800daac0  test    eax, eax
0x1800daac2  jns     short loc_1800DAAE5
0x1800daac4  mov     dword ptr [rsp+350h+var_320], eax
0x1800daac8  lea     r9, aFailedToDeterm; "Failed to determine indicators: [0x%x]."
0x1800daacf  mov     [rsp+350h+var_328], r9
0x1800daad4  lea     r9, aWindowsCompatA_697; "Windows::Compat::Appraiser::RegistryMar"...
0x1800daadb  mov     edx, 2E9h
0x1800daae0  jmp     loc_1800DA891
0x1800daae5  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800daaeb  and     eax, esi
0x1800daaed  test    al, al
0x1800daaef  jz      short loc_1800DAB14
  ... truncated ...
```
