# Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize(Windows::Compat::Appraiser::IPropertyListEnumerator *,void *)

- ea: `0x1800ddb30`
- end: `0x1800de090`
- name: `?Initialize@RegistryMarkerOutputter@Appraiser@Compat@Windows@@UEAAJPEAVIPropertyListEnumerator@234@PEAX@Z`
- size: `1376`
- prototype: `int(Windows::Compat::Appraiser::RegistryMarkerOutputter *__hidden this, struct Windows::Compat::Appraiser::IPropertyListEnumerator *, void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18002ebb8`
- `0x1800301d0`
- `0x1800aafec`
- `0x1800ad640`
- `0x1800ae638`
- `0x1800b013c`
- `0x1800dc444`
- `0x1800ddb30`
- `0x18021f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x1800ddd70`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x1800ddd70`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800ddd4c`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800ddd4c`
- `KERNEL32!GetProcessHeap` at `0x1800ddb73`
- `KERNEL32!GetProcessHeap` at `0x1800ddba8`
- `KERNEL32!GetProcessHeap` at `0x1800ddbd2`
- `KERNEL32!GetProcessHeap` at `0x1800ddb73`
- `KERNEL32!GetProcessHeap` at `0x1800ddba8`
- `KERNEL32!GetProcessHeap` at `0x1800ddbd2`
- `KERNEL32!HeapFree` at `0x1800de025`
- `KERNEL32!HeapFree` at `0x1800de049`
- `KERNEL32!HeapFree` at `0x1800de06d`
- `KERNEL32!HeapFree` at `0x1800de025`
- `KERNEL32!HeapFree` at `0x1800de049`
- `KERNEL32!HeapFree` at `0x1800de06d`

## string_xrefs

- `0x1800ddc26`: `onecore\base\appcompat\appraiser\outputters\registrymarker.cpp`
- `0x1800ddc61`: `onecore\base\appcompat\appraiser\outputters\registrymarker.cpp`
- `0x1800ddc1f`: `Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize`
- `0x1800ddc5a`: `Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize`
- `0x1800ddc02`: `OutputRegistryMarkerNewAppraiserMarkersRequiredComponentSuccess`
- `0x1800ddd15`: `OutputRegistryMarkerSelectiveOutputMarkersTableName`
- `0x1800ddcd1`: `OutputRegistryMarkerRequestedIndicatorsToOutput`
- `0x1800ddc86`: `OutputRegistryMarkerRequestedMarkersToOutput`
- `0x1800ddd34`: `OutputRegistryMarkerCurrentTimestamp`
- `0x1800ddea5`: `OutputRegistryMarkerRecommendedDataVersion`
- `0x1800dde93`: `OutputRegistryMarkerSendFullSync`
- `0x1800dde7e`: `OutputRegistryMarkerSkipIndicatorDeltas`
- `0x1800dde64`: `OutputRegistryMarkerTargetVersionSuffixOverride`
- `0x1800ddeed`: `OutputRegistryMarkerOldAppraiserMarkersChecksumValidityRequired`
- `0x1800ddedb`: `OutputRegistryMarkerOldAppraiserMarkersMaxAgeDays`
- `0x1800ddec9`: `OutputRegistryMarkerOldAppraiserMarkersMinVersion`
- `0x1800ddeb7`: `OutputRegistryMarkerNewAppraiserDataAllowedToFailPrereqs`
- `0x1800ddf3c`: `OutputRegistryMarkerGeneralTelMarkersChecksumValidityRequired`
- `0x1800ddf2a`: `OutputRegistryMarkerGeneralTelMarkersMustBeNew`
- `0x1800ddf18`: `OutputRegistryMarkerGeneralTelMarkersMaxAgeDays`
- `0x1800ddf06`: `OutputRegistryMarkerGeneralTelMarkersMinVersion`
- `0x1800ddf52`: `OutputRegistryMarkerGeneralTelMarkerNotRequired`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize(
        Windows::Compat::Appraiser::RegistryMarkerOutputter *this,
        struct Windows::Compat::Appraiser::IPropertyListEnumerator *a2,
        _QWORD *a3)
{
  int AllValuesFromPropertiesWithName; // edi
  char v6; // dl
  const wchar_t *v7; // rax
  __int64 v8; // rbx
  const unsigned __int16 *v9; // rdx
  const char *v10; // rcx
  char v11; // dl
  struct Windows::Compat::Appraiser::DataFile *v12; // rax
  int TargetVersionReference; // eax
  int v14; // r13d
  char v15; // r12
  int v16; // r15d
  int v17; // r14d
  char *v19; // [rsp+20h] [rbp-110h]
  char *v20; // [rsp+30h] [rbp-100h]
  bool v21; // [rsp+B0h] [rbp-80h]
  bool v22; // [rsp+B1h] [rbp-7Fh]
  unsigned int PropertyDword; // [rsp+B4h] [rbp-7Ch]
  unsigned int v24; // [rsp+B8h] [rbp-78h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+C0h] [rbp-70h] BYREF
  unsigned __int16 *v26; // [rsp+C8h] [rbp-68h] BYREF
  HANDLE hHeap[2]; // [rsp+D0h] [rbp-60h] BYREF
  __int128 v28; // [rsp+E0h] [rbp-50h]
  LPVOID lpMem[2]; // [rsp+F0h] [rbp-40h]
  HANDLE v30[2]; // [rsp+100h] [rbp-30h] BYREF
  __int128 v31; // [rsp+110h] [rbp-20h]
  LPVOID v32[2]; // [rsp+120h] [rbp-10h]
  __int64 v33; // [rsp+130h] [rbp+0h]
  __int64 v34; // [rsp+138h] [rbp+8h]
  __int64 v35; // [rsp+140h] [rbp+10h]
  HANDLE v36[2]; // [rsp+148h] [rbp+18h] BYREF
  __int128 v37; // [rsp+158h] [rbp+28h]
  LPVOID v38[2]; // [rsp+168h] [rbp+38h]
  __int64 v39; // [rsp+178h] [rbp+48h]
  char IsPropertyTrue; // [rsp+1D8h] [rbp+A8h]

  v39 = -2;
  *(_OWORD *)v36 = 0;
  v37 = 0;
  *(_OWORD *)v38 = 0;
  v36[0] = GetProcessHeap();
  v38[0] = (LPVOID)16;
  v37 = 0;
  v38[1] = 0;
  v36[1] = (HANDLE)8;
  v30[0] = GetProcessHeap();
  v32[0] = (LPVOID)16;
  v31 = 0;
  v32[1] = 0;
  v30[1] = (HANDLE)8;
  hHeap[0] = GetProcessHeap();
  lpMem[0] = (LPVOID)16;
  v28 = 0;
  lpMem[1] = 0;
  hHeap[1] = (HANDLE)8;
  SystemTimeAsFileTime = 0;
  v26 = 0;
  AllValuesFromPropertiesWithName = Windows::Compat::Appraiser::AssetUtils::GetAllValuesFromPropertiesWithName(
                                      v36,
                                      L"OutputRegistryMarkerNewAppraiserMarkersRequiredComponentSuccess",
                                      a2);
  if ( AllValuesFromPropertiesWithName < 0 )
  {
    v6 = 124;
LABEL_3:
    LODWORD(v20) = AllValuesFromPropertiesWithName;
    LODWORD(v19) = AllValuesFromPropertiesWithName;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v6,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
      "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize",
      v19,
      (int)"Error finding parameters: [0x%x].",
      v20);
    goto LABEL_29;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x17Cu,
      "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
      "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize",
      "Error finding parameters: [0x%x].",
      AllValuesFromPropertiesWithName);
  AllValuesFromPropertiesWithName = Windows::Compat::Appraiser::AssetUtils::GetAllValuesFromPropertiesWithName(
                                      v30,
                                      L"OutputRegistryMarkerRequestedMarkersToOutput",
                                      a2);
  if ( AllValuesFromPropertiesWithName < 0 )
  {
    v6 = 127;
    goto LABEL_3;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x17Fu,
      "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
      "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize",
      "Error finding parameters: [0x%x].",
      AllValuesFromPropertiesWithName);
  AllValuesFromPropertiesWithName = Windows::Compat::Appraiser::AssetUtils::GetAllValuesFromPropertiesWithName(
                                      hHeap,
                                      L"OutputRegistryMarkerRequestedIndicatorsToOutput",
                                      a2);
  if ( AllValuesFromPropertiesWithName < 0 )
  {
    v6 = -126;
    goto LABEL_3;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x182u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
      "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize",
      "Error finding parameters: [0x%x].",
      AllValuesFromPropertiesWithName);
  v33 = (*(__int64 (__fastcall **)(struct Windows::Compat::Appraiser::IPropertyListEnumerator *, const wchar_t *))(*(_QWORD *)a2 + 40LL))(
          a2,
          L"OutputRegistryMarkerSelectiveOutputMarkersTableName");
  v7 = (const wchar_t *)(*(__int64 (__fastcall **)(struct Windows::Compat::Appraiser::IPropertyListEnumerator *, const wchar_t *))(*(_QWORD *)a2 + 40LL))(
                          a2,
                          L"OutputRegistryMarkerCurrentTimestamp");
  if ( v7 )
  {
    v8 = _wtoi64(v7);
  }
  else
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v8 = (__int64)SystemTimeAsFileTime;
  }
  v9 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct Windows::Compat::Appraiser::IPropertyListEnumerator *, const wchar_t *))(*(_QWORD *)a2 + 40LL))(
                                   a2,
                                   L"TargetVersion");
  if ( !v9 )
  {
    v10 = "TargetVersionLocal";
    v11 = -109;
LABEL_19:
    AllValuesFromPropertiesWithName = -2147024809;
    LODWORD(v19) = -2147024809;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v11,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
      "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize",
      v19,
      (int)"Required parameter [%s] missing: [0x%x].",
      v10,
      -2147024809);
    goto LABEL_29;
  }
  if ( !a3 )
  {
    v10 = "Data";
    v11 = -107;
    goto LABEL_19;
  }
  v12 = (struct Windows::Compat::Appraiser::DataFile *)a3[1];
  v34 = (__int64)v12;
  if ( !v12 )
  {
    v10 = "DataFile";
    v11 = -104;
    goto LABEL_19;
  }
  TargetVersionReference = Windows::Compat::Appraiser::AppraiserTarget::GetTargetVersionReference(
                             (const unsigned __int16 **)&v26,
                             v9,
                             v12);
  AllValuesFromPropertiesWithName = TargetVersionReference;
  if ( TargetVersionReference >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x19Bu,
        "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
        "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize",
        "Invalid Target Version");
    v35 = (*(__int64 (__fastcall **)(struct Windows::Compat::Appraiser::IPropertyListEnumerator *, const wchar_t *))(*(_QWORD *)a2 + 40LL))(
            a2,
            L"OutputRegistryMarkerTargetVersionSuffixOverride");
    IsPropertyTrue = Windows::Compat::Appraiser::AssetUtils::IsPropertyTrue(
                       L"OutputRegistryMarkerSkipIndicatorDeltas",
                       a2);
    v21 = Windows::Compat::Appraiser::AssetUtils::IsPropertyTrue(L"OutputRegistryMarkerSendFullSync", a2);
    PropertyDword = Windows::Compat::Appraiser::AssetUtils::GetPropertyDword(
                      L"OutputRegistryMarkerRecommendedDataVersion",
                      a2);
    v22 = Windows::Compat::Appraiser::AssetUtils::IsPropertyTrue(
            L"OutputRegistryMarkerNewAppraiserDataAllowedToFailPrereqs",
            a2);
    v24 = Windows::Compat::Appraiser::AssetUtils::GetPropertyDword(
            L"OutputRegistryMarkerOldAppraiserMarkersMinVersion",
            a2);
    v14 = Windows::Compat::Appraiser::AssetUtils::GetPropertyDword(
            L"OutputRegistryMarkerOldAppraiserMarkersMaxAgeDays",
            a2);
    v15 = Windows::Compat::Appraiser::AssetUtils::IsPropertyTrue(
            L"OutputRegistryMarkerOldAppraiserMarkersChecksumValidityRequired",
            a2);
    v16 = Windows::Compat::Appraiser::AssetUtils::GetPropertyDword(
            L"OutputRegistryMarkerGeneralTelMarkersMinVersion",
            a2);
    v17 = Windows::Compat::Appraiser::AssetUtils::GetPropertyDword(
            L"OutputRegistryMarkerGeneralTelMarkersMaxAgeDays",
            a2);
    Windows::Compat::Appraiser::AssetUtils::IsPropertyTrue(L"OutputRegistryMarkerGeneralTelMarkersMustBeNew", a2);
    Windows::Compat::Appraiser::AssetUtils::IsPropertyTrue(
      L"OutputRegistryMarkerGeneralTelMarkersChecksumValidityRequired",
      a2);
    Windows::Compat::Appraiser::AssetUtils::IsPropertyTrue(L"OutputRegistryMarkerGeneralTelMarkerNotRequired", a2);
    AllValuesFromPropertiesWithName = Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize(
                                        (Windows::Compat::Appraiser::RegistryMarkerOutputter *)((char *)this - 8),
                                        v17,
                                        v16,
                                        v15,
                                        v14,
                                        v24,
                                        v22,
                                        PropertyDword,
                                        (__int64)v36,
                                        (__int64)v30,
                                        (__int64)hHeap,
                                        v8,
                                        v21,
                                        (__int64)v26,
                                        v35,
                                        v34,
                                        (int)L"LT_IndicatorsToIgnoreForUTC",
                                        v33,
                                        IsPropertyTrue);
  }
  else
  {
    LODWORD(v19) = TargetVersionReference;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      155,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
      "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize",
      v19,
      (int)"Invalid Target Version",
      v20);
  }
LABEL_29:
  if ( lpMem[1] )
    HeapFree(hHeap[0], 0, lpMem[1]);
  *(_OWORD *)hHeap = 0;
  v28 = 0;
  *(_OWORD *)lpMem = 0;
  if ( v32[1] )
    HeapFree(v30[0], 0, v32[1]);
  *(_OWORD *)v30 = 0;
  v31 = 0;
  *(_OWORD *)v32 = 0;
  if ( v38[1] )
    HeapFree(v36[0], 0, v38[1]);
  return (unsigned int)AllValuesFromPropertiesWithName;
}

```

## disassembly

```asm
0x1800ddb30  mov     rax, rsp
0x1800ddb33  mov     [rax+10h], rdx
0x1800ddb37  mov     [rax+8], rcx
0x1800ddb3b  push    rbp
0x1800ddb3c  push    rsi
0x1800ddb3d  push    rdi
0x1800ddb3e  push    r12
0x1800ddb40  push    r13
0x1800ddb42  push    r14
0x1800ddb44  push    r15
0x1800ddb46  lea     rbp, [rsp-50h]
0x1800ddb4b  sub     rsp, 180h
0x1800ddb52  mov     [rbp+80h+var_38], 0FFFFFFFFFFFFFFFEh
0x1800ddb5a  mov     [rax+18h], rbx
0x1800ddb5e  mov     r13, r8
0x1800ddb61  mov     r12, rdx
0x1800ddb64  xorps   xmm0, xmm0
0x1800ddb67  movups  xmmword ptr [rbp+80h+var_68], xmm0
0x1800ddb6b  movups  [rbp+80h+var_58], xmm0
0x1800ddb6f  movups  xmmword ptr [rbp+80h+var_48], xmm0
0x1800ddb73  call    cs:__imp_GetProcessHeap
0x1800ddb79  mov     [rbp+80h+var_68], rax
0x1800ddb7d  mov     edi, 10h
0x1800ddb82  mov     [rbp+80h+var_48], rdi
0x1800ddb86  xorps   xmm0, xmm0
0x1800ddb89  movdqu  [rbp+80h+var_58], xmm0
0x1800ddb8e  xor     r14d, r14d
0x1800ddb91  mov     [rbp+80h+var_48+8], r14
0x1800ddb95  lea     ebx, [rdi-8]
0x1800ddb98  mov     [rbp+80h+var_68+8], rbx
0x1800ddb9c  movups  xmmword ptr [rbp+80h+var_B0], xmm0
0x1800ddba0  movups  [rbp+80h+var_A0], xmm0
0x1800ddba4  movups  xmmword ptr [rbp+80h+var_90], xmm0
0x1800ddba8  call    cs:__imp_GetProcessHeap
0x1800ddbae  mov     [rbp+80h+var_B0], rax
0x1800ddbb2  mov     [rbp+80h+var_90], rdi
0x1800ddbb6  xorps   xmm0, xmm0
0x1800ddbb9  movdqu  [rbp+80h+var_A0], xmm0
0x1800ddbbe  mov     [rbp+80h+var_90+8], r14
0x1800ddbc2  mov     [rbp+80h+var_B0+8], rbx
0x1800ddbc6  movups  xmmword ptr [rbp+80h+hHeap], xmm0
0x1800ddbca  movups  [rbp+80h+var_D0], xmm0
0x1800ddbce  movups  xmmword ptr [rbp+80h+lpMem], xmm0
0x1800ddbd2  call    cs:__imp_GetProcessHeap
0x1800ddbd8  mov     [rbp+80h+hHeap], rax
0x1800ddbdc  mov     [rbp+80h+lpMem], rdi
0x1800ddbe0  xorps   xmm0, xmm0
0x1800ddbe3  movdqu  [rbp+80h+var_D0], xmm0
0x1800ddbe8  mov     [rbp+80h+lpMem+8], r14
0x1800ddbec  mov     [rbp+80h+hHeap+8], rbx
0x1800ddbf0  mov     qword ptr [rbp+80h+SystemTimeAsFileTime.dwLowDateTime], r14
0x1800ddbf4  mov     [rbp+80h+arg_18], r14
0x1800ddbfb  mov     [rbp+80h+var_E8], r14
0x1800ddbff  mov     r8, r12
0x1800ddc02  lea     rdx, aOutputregistry_15; "OutputRegistryMarkerNewAppraiserMarkers"...
0x1800ddc09  lea     rcx, [rbp+80h+var_68]
0x1800ddc0d  call    ?GetAllValuesFromPropertiesWithName@AssetUtils@Appraiser@Compat@Windows@@SAJAEAV?$RtlArray@PEBG@@PEBGPEAVIPropertyListEnumerator@234@@Z; Windows::Compat::Appraiser::AssetUtils::GetAllValuesFromPropertiesWithName(RtlArray<ushort const *> &,ushort const *,Windows::Compat::Appraiser::IPropertyListEnumerator *)
0x1800ddc12  mov     edi, eax
0x1800ddc14  lea     rbx, aErrorFindingPa; "Error finding parameters: [0x%x]."
0x1800ddc1b  test    eax, eax
0x1800ddc1d  jns     short loc_1800DDC4D
0x1800ddc1f  lea     r9, aWindowsCompatA_185; "Windows::Compat::Appraiser::RegistryMar"...
0x1800ddc26  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800ddc2d  mov     edx, 17Ch; bool
0x1800ddc32  lea     ecx, [r14+1]; this
0x1800ddc36  mov     dword ptr [rsp+1B0h+var_180], edi; char *
0x1800ddc3a  mov     qword ptr [rsp+1B0h+var_188], rbx; int
0x1800ddc3f  mov     dword ptr [rsp+1B0h+var_190], edi; char *
0x1800ddc43  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800ddc48  jmp     loc_1800DE016
0x1800ddc4d  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800ddc53  mov     esi, 1
0x1800ddc58  and     eax, esi
0x1800ddc5a  lea     r14, aWindowsCompatA_185; "Windows::Compat::Appraiser::RegistryMar"...
0x1800ddc61  lea     r15, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800ddc68  test    al, al
0x1800ddc6a  jz      short loc_1800DDC83
0x1800ddc6c  mov     dword ptr [rsp+1B0h+var_190], edi
0x1800ddc70  mov     r9, rbx; char *
0x1800ddc73  mov     r8, r14; char *
0x1800ddc76  mov     rdx, r15; char *
0x1800ddc79  mov     ecx, 17Ch; unsigned int
0x1800ddc7e  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800ddc83  mov     r8, r12
0x1800ddc86  lea     rdx, aOutputregistry_5; "OutputRegistryMarkerRequestedMarkersToO"...
0x1800ddc8d  lea     rcx, [rbp+80h+var_B0]
0x1800ddc91  call    ?GetAllValuesFromPropertiesWithName@AssetUtils@Appraiser@Compat@Windows@@SAJAEAV?$RtlArray@PEBG@@PEBGPEAVIPropertyListEnumerator@234@@Z; Windows::Compat::Appraiser::AssetUtils::GetAllValuesFromPropertiesWithName(RtlArray<ushort const *> &,ushort const *,Windows::Compat::Appraiser::IPropertyListEnumerator *)
0x1800ddc96  mov     edi, eax
0x1800ddc98  test    eax, eax
0x1800ddc9a  jns     short loc_1800DDCAB
0x1800ddc9c  mov     edx, 17Fh
0x1800ddca1  mov     r8, r15
0x1800ddca4  mov     r9, r14
0x1800ddca7  mov     ecx, esi
0x1800ddca9  jmp     short loc_1800DDC36
0x1800ddcab  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800ddcb1  and     eax, esi
0x1800ddcb3  test    al, al
0x1800ddcb5  jz      short loc_1800DDCCE
0x1800ddcb7  mov     dword ptr [rsp+1B0h+var_190], edi
0x1800ddcbb  mov     r9, rbx; char *
0x1800ddcbe  mov     r8, r14; char *
0x1800ddcc1  mov     rdx, r15; char *
0x1800ddcc4  mov     ecx, 17Fh; unsigned int
0x1800ddcc9  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800ddcce  mov     r8, r12
0x1800ddcd1  lea     rdx, aOutputregistry_20; "OutputRegistryMarkerRequestedIndicators"...
0x1800ddcd8  lea     rcx, [rbp+80h+hHeap]
0x1800ddcdc  call    ?GetAllValuesFromPropertiesWithName@AssetUtils@Appraiser@Compat@Windows@@SAJAEAV?$RtlArray@PEBG@@PEBGPEAVIPropertyListEnumerator@234@@Z; Windows::Compat::Appraiser::AssetUtils::GetAllValuesFromPropertiesWithName(RtlArray<ushort const *> &,ushort const *,Windows::Compat::Appraiser::IPropertyListEnumerator *)
0x1800ddce1  mov     edi, eax
0x1800ddce3  test    eax, eax
0x1800ddce5  jns     short loc_1800DDCEE
0x1800ddce7  mov     edx, 182h
0x1800ddcec  jmp     short loc_1800DDCA1
0x1800ddcee  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800ddcf4  and     eax, esi
0x1800ddcf6  test    al, al
0x1800ddcf8  jz      short loc_1800DDD11
0x1800ddcfa  mov     dword ptr [rsp+1B0h+var_190], edi
0x1800ddcfe  mov     r9, rbx; char *
0x1800ddd01  mov     r8, r14; char *
0x1800ddd04  mov     rdx, r15; char *
0x1800ddd07  mov     ecx, 182h; unsigned int
0x1800ddd0c  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800ddd11  mov     rax, [r12]
0x1800ddd15  lea     rdx, aOutputregistry_16; "OutputRegistryMarkerSelectiveOutputMark"...
0x1800ddd1c  mov     rcx, r12
0x1800ddd1f  mov     rax, [rax+28h]
0x1800ddd23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddd28  mov     [rbp+80h+var_80], rax
0x1800ddd2c  mov     rcx, [r12]
0x1800ddd30  mov     rax, [rcx+28h]
0x1800ddd34  lea     rdx, aOutputregistry_18; "OutputRegistryMarkerCurrentTimestamp"
0x1800ddd3b  mov     rcx, r12
0x1800ddd3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddd43  test    rax, rax
0x1800ddd46  jnz     short loc_1800DDD6D
0x1800ddd48  lea     rcx, [rbp+80h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800ddd4c  call    cs:__imp_GetSystemTimeAsFileTime
0x1800ddd52  mov     ecx, [rbp+80h+SystemTimeAsFileTime.dwHighDateTime]
0x1800ddd55  mov     dword ptr [rbp+80h+arg_18+4], ecx
0x1800ddd5b  mov     eax, [rbp+80h+SystemTimeAsFileTime.dwLowDateTime]
0x1800ddd5e  mov     dword ptr [rbp+80h+arg_18], eax
0x1800ddd64  mov     rbx, [rbp+80h+arg_18]
0x1800ddd6b  jmp     short loc_1800DDD79
0x1800ddd6d  mov     rcx, rax; String
0x1800ddd70  call    cs:__imp__wtoi64
0x1800ddd76  mov     rbx, rax
0x1800ddd79  mov     rax, [r12]
0x1800ddd7d  lea     rdx, aTargetversion; "TargetVersion"
0x1800ddd84  mov     rcx, r12
0x1800ddd87  mov     rax, [rax+28h]
0x1800ddd8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddd90  mov     rdx, rax; unsigned __int16 *
0x1800ddd93  test    rax, rax
0x1800ddd96  jnz     short loc_1800DDDD6
0x1800ddd98  lea     rcx, aTargetversionl; "TargetVersionLocal"
0x1800ddd9f  mov     edx, 193h; bool
0x1800ddda4  mov     eax, 80070057h
0x1800ddda9  mov     [rsp+1B0h+var_178], eax
0x1800dddad  mov     [rsp+1B0h+var_180], rcx; char *
0x1800dddb2  lea     rcx, aRequiredParame; "Required parameter [%s] missing: [0x%x]"...
0x1800dddb9  mov     qword ptr [rsp+1B0h+var_188], rcx; int
0x1800dddbe  mov     edi, eax
0x1800dddc0  mov     dword ptr [rsp+1B0h+var_190], eax; char *
0x1800dddc4  mov     r9, r14; char *
0x1800dddc7  mov     r8, r15; unsigned int
0x1800dddca  mov     ecx, esi; this
0x1800dddcc  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800dddd1  jmp     loc_1800DE016
0x1800dddd6  test    r13, r13
0x1800dddd9  jnz     short loc_1800DDDE9
0x1800ddddb  lea     rcx, aData; "Data"
0x1800ddde2  mov     edx, 195h
0x1800ddde7  jmp     short loc_1800DDDA4
0x1800ddde9  mov     rax, [r13+8]
0x1800ddded  mov     [rbp+80h+var_78], rax
0x1800dddf1  test    rax, rax
0x1800dddf4  jnz     short loc_1800DDE04
0x1800dddf6  lea     rcx, aDatafile; "DataFile"
0x1800dddfd  mov     edx, 198h
0x1800dde02  jmp     short loc_1800DDDA4
0x1800dde04  mov     r8, rax; struct Windows::Compat::Appraiser::DataFile *
0x1800dde07  lea     rcx, [rbp+80h+var_E8]; unsigned __int16 **
0x1800dde0b  call    ?GetTargetVersionReference@AppraiserTarget@Appraiser@Compat@Windows@@SAJPEAPEBGPEBGPEAVDataFile@234@@Z; Windows::Compat::Appraiser::AppraiserTarget::GetTargetVersionReference(ushort const * *,ushort const *,Windows::Compat::Appraiser::DataFile *)
0x1800dde10  mov     edi, eax
0x1800dde12  test    eax, eax
0x1800dde14  jns     short loc_1800DDE3D
0x1800dde16  lea     r9, aInvalidTargetV_0; "Invalid Target Version"
0x1800dde1d  mov     qword ptr [rsp+1B0h+var_188], r9; int
0x1800dde22  mov     dword ptr [rsp+1B0h+var_190], eax; char *
0x1800dde26  mov     r9, r14; char *
0x1800dde29  mov     r8, r15; unsigned int
0x1800dde2c  mov     edx, 19Bh; bool
0x1800dde31  mov     ecx, esi; this
0x1800dde33  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800dde38  jmp     loc_1800DE016
0x1800dde3d  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800dde43  and     eax, esi
0x1800dde45  test    al, al
0x1800dde47  jz      short loc_1800DDE60
0x1800dde49  lea     r9, aInvalidTargetV_0; "Invalid Target Version"
0x1800dde50  mov     r8, r14; char *
0x1800dde53  mov     rdx, r15; char *
0x1800dde56  mov     ecx, 19Bh; unsigned int
0x1800dde5b  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800dde60  mov     rax, [r12]
0x1800dde64  lea     rdx, aOutputregistry_17; "OutputRegistryMarkerTargetVersionSuffix"...
0x1800dde6b  mov     rcx, r12
0x1800dde6e  mov     rax, [rax+28h]
0x1800dde72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dde77  mov     [rbp+80h+var_70], rax
0x1800dde7b  mov     rdx, r12; struct Windows::Compat::Appraiser::IPropertyListEnumerator *
0x1800dde7e  lea     rcx, aOutputregistry_9; "OutputRegistryMarkerSkipIndicatorDeltas"
0x1800dde85  call    ?IsPropertyTrue@AssetUtils@Appraiser@Compat@Windows@@SA_NPEBGPEAVIPropertyListEnumerator@234@@Z; Windows::Compat::Appraiser::AssetUtils::IsPropertyTrue(ushort const *,Windows::Compat::Appraiser::IPropertyListEnumerator *)
0x1800dde8a  mov     byte ptr [rbp+80h+arg_18], al
0x1800dde90  mov     rdx, r12; struct Windows::Compat::Appraiser::IPropertyListEnumerator *
0x1800dde93  lea     rcx, aOutputregistry_8; "OutputRegistryMarkerSendFullSync"
0x1800dde9a  call    ?IsPropertyTrue@AssetUtils@Appraiser@Compat@Windows@@SA_NPEBGPEAVIPropertyListEnumerator@234@@Z; Windows::Compat::Appraiser::AssetUtils::IsPropertyTrue(ushort const *,Windows::Compat::Appraiser::IPropertyListEnumerator *)
0x1800dde9f  mov     [rbp+80h+var_100], al
0x1800ddea2  mov     rdx, r12; struct Windows::Compat::Appraiser::IPropertyListEnumerator *
0x1800ddea5  lea     rcx, aOutputregistry_4; "OutputRegistryMarkerRecommendedDataVers"...
0x1800ddeac  call    ?GetPropertyDword@AssetUtils@Appraiser@Compat@Windows@@SAKPEBGPEAVIPropertyListEnumerator@234@@Z; Windows::Compat::Appraiser::AssetUtils::GetPropertyDword(ushort const *,Windows::Compat::Appraiser::IPropertyListEnumerator *)
0x1800ddeb1  mov     [rbp+80h+var_FC], eax
0x1800ddeb4  mov     rdx, r12; struct Windows::Compat::Appraiser::IPropertyListEnumerator *
0x1800ddeb7  lea     rcx, aOutputregistry_10; "OutputRegistryMarkerNewAppraiserDataAll"...
0x1800ddebe  call    ?IsPropertyTrue@AssetUtils@Appraiser@Compat@Windows@@SA_NPEBGPEAVIPropertyListEnumerator@234@@Z; Windows::Compat::Appraiser::AssetUtils::IsPropertyTrue(ushort const *,Windows::Compat::Appraiser::IPropertyListEnumerator *)
0x1800ddec3  mov     [rbp+80h+var_FF], al
0x1800ddec6  mov     rdx, r12; struct Windows::Compat::Appraiser::IPropertyListEnumerator *
0x1800ddec9  lea     rcx, aOutputregistry_11; "OutputRegistryMarkerOldAppraiserMarkers"...
0x1800dded0  call    ?GetPropertyDword@AssetUtils@Appraiser@Compat@Windows@@SAKPEBGPEAVIPropertyListEnumerator@234@@Z; Windows::Compat::Appraiser::AssetUtils::GetPropertyDword(ushort const *,Windows::Compat::Appraiser::IPropertyListEnumerator *)
0x1800dded5  mov     [rbp+80h+var_F8], eax
0x1800dded8  mov     rdx, r12; struct Windows::Compat::Appraiser::IPropertyListEnumerator *
0x1800ddedb  lea     rcx, aOutputregistry_21; "OutputRegistryMarkerOldAppraiserMarkers"...
0x1800ddee2  call    ?GetPropertyDword@AssetUtils@Appraiser@Compat@Windows@@SAKPEBGPEAVIPropertyListEnumerator@234@@Z; Windows::Compat::Appraiser::AssetUtils::GetPropertyDword(ushort const *,Windows::Compat::Appraiser::IPropertyListEnumerator *)
0x1800ddee7  mov     r13d, eax
0x1800ddeea  mov     rdx, r12; struct Windows::Compat::Appraiser::IPropertyListEnumerator *
0x1800ddeed  lea     rcx, aOutputregistry_3; "OutputRegistryMarkerOldAppraiserMarkers"...
0x1800ddef4  call    ?IsPropertyTrue@AssetUtils@Appraiser@Compat@Windows@@SA_NPEBGPEAVIPropertyListEnumerator@234@@Z; Windows::Compat::Appraiser::AssetUtils::IsPropertyTrue(ushort const *,Windows::Compat::Appraiser::IPropertyListEnumerator *)
0x1800ddef9  mov     r12b, al
0x1800ddefc  mov     rdi, [rbp+80h+arg_8]
0x1800ddf03  mov     rdx, rdi; struct Windows::Compat::Appraiser::IPropertyListEnumerator *
0x1800ddf06  lea     rcx, aOutputregistry_7; "OutputRegistryMarkerGeneralTelMarkersMi"...
0x1800ddf0d  call    ?GetPropertyDword@AssetUtils@Appraiser@Compat@Windows@@SAKPEBGPEAVIPropertyListEnumerator@234@@Z; Windows::Compat::Appraiser::AssetUtils::GetPropertyDword(ushort const *,Windows::Compat::Appraiser::IPropertyListEnumerator *)
0x1800ddf12  mov     r15d, eax
0x1800ddf15  mov     rdx, rdi; struct Windows::Compat::Appraiser::IPropertyListEnumerator *
0x1800ddf18  lea     rcx, aOutputregistry_2; "OutputRegistryMarkerGeneralTelMarkersMa"...
0x1800ddf1f  call    ?GetPropertyDword@AssetUtils@Appraiser@Compat@Windows@@SAKPEBGPEAVIPropertyListEnumerator@234@@Z; Windows::Compat::Appraiser::AssetUtils::GetPropertyDword(ushort const *,Windows::Compat::Appraiser::IPropertyListEnumerator *)
0x1800ddf24  mov     r14d, eax
0x1800ddf27  mov     rdx, rdi; struct Windows::Compat::Appraiser::IPropertyListEnumerator *
0x1800ddf2a  lea     rcx, aOutputregistry_14; "OutputRegistryMarkerGeneralTelMarkersMu"...
0x1800ddf31  call    ?IsPropertyTrue@AssetUtils@Appraiser@Compat@Windows@@SA_NPEBGPEAVIPropertyListEnumerator@234@@Z; Windows::Compat::Appraiser::AssetUtils::IsPropertyTrue(ushort const *,Windows::Compat::Appraiser::IPropertyListEnumerator *)
0x1800ddf36  mov     sil, al
0x1800ddf39  mov     rdx, rdi; struct Windows::Compat::Appraiser::IPropertyListEnumerator *
0x1800ddf3c  lea     rcx, aOutputregistry_19; "OutputRegistryMarkerGeneralTelMarkersCh"...
0x1800ddf43  call    ?IsPropertyTrue@AssetUtils@Appraiser@Compat@Windows@@SA_NPEBGPEAVIPropertyListEnumerator@234@@Z; Windows::Compat::Appraiser::AssetUtils::IsPropertyTrue(ushort const *,Windows::Compat::Appraiser::IPropertyListEnumerator *)
0x1800ddf48  mov     dil, al
0x1800ddf4b  mov     rdx, [rbp+80h+arg_8]; struct Windows::Compat::Appraiser::IPropertyListEnumerator *
0x1800ddf52  lea     rcx, aOutputregistry; "OutputRegistryMarkerGeneralTelMarkerNot"...
0x1800ddf59  call    ?IsPropertyTrue@AssetUtils@Appraiser@Compat@Windows@@SA_NPEBGPEAVIPropertyListEnumerator@234@@Z; Windows::Compat::Appraiser::AssetUtils::IsPropertyTrue(ushort const *,Windows::Compat::Appraiser::IPropertyListEnumerator *)
0x1800ddf5e  xor     al, 1
0x1800ddf60  mov     rcx, [rbp+80h+arg_0]
0x1800ddf67  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x1800ddf6b  mov     dl, byte ptr [rbp+80h+arg_18]
0x1800ddf71  mov     [rsp+1B0h+var_108], dl; char
0x1800ddf78  mov     rdx, [rbp+80h+var_80]
0x1800ddf7c  mov     [rsp+1B0h+var_110], rdx; __int64
0x1800ddf84  lea     rdx, aLtIndicatorsto; "LT_IndicatorsToIgnoreForUTC"
0x1800ddf8b  mov     qword ptr [rsp+1B0h+var_118], rdx; int
0x1800ddf93  mov     rdx, [rbp+80h+var_78]
0x1800ddf97  mov     [rsp+1B0h+var_120], rdx; __int64
0x1800ddf9f  mov     rdx, [rbp+80h+var_70]
0x1800ddfa3  mov     [rsp+1B0h+var_128], rdx; __int64
0x1800ddfab  mov     rdx, [rbp+80h+var_E8]
0x1800ddfaf  mov     [rsp+1B0h+var_130], rdx; __int64
0x1800ddfb7  mov     dl, [rbp+80h+var_100]
0x1800ddfba  mov     [rsp+1B0h+var_138], dl; char
0x1800ddfbe  mov     [rsp+1B0h+var_140], rbx; __int64
0x1800ddfc3  lea     rdx, [rbp+80h+hHeap]
0x1800ddfc7  mov     [rsp+1B0h+var_148], rdx; __int64
0x1800ddfcc  lea     rdx, [rbp+80h+var_B0]
0x1800ddfd0  mov     [rsp+1B0h+var_150], rdx; __int64
0x1800ddfd5  lea     rdx, [rbp+80h+var_68]
0x1800ddfd9  mov     [rsp+1B0h+var_158], rdx; __int64
0x1800ddfde  mov     edx, [rbp+80h+var_FC]
0x1800ddfe1  mov     [rsp+1B0h+var_160], edx; int
0x1800ddfe5  mov     dl, [rbp+80h+var_FF]
0x1800ddfe8  mov     [rsp+1B0h+var_168], dl; char
0x1800ddfec  mov     edx, [rbp+80h+var_F8]
0x1800ddfef  mov     [rsp+1B0h+var_170], edx; int
0x1800ddff3  mov     [rsp+1B0h+var_178], r13d; int
0x1800ddff8  mov     byte ptr [rsp+1B0h+var_180], r12b; char
0x1800ddffd  mov     [rsp+1B0h+var_188], r15d; int
0x1800de002  mov     dword ptr [rsp+1B0h+var_190], r14d; int
0x1800de007  mov     r9b, sil
0x1800de00a  mov     r8b, dil
0x1800de00d  mov     dl, al
0x1800de00f  call    ?Initialize@RegistryMarkerOutputter@Appraiser@Compat@Windows@@QEAAJ_N00KK0KK0KPEBV?$RtlArray@PEBG@@11T_LARGE_INTEGER@@0PEBG3PEAVDataFile@234@330@Z; Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize(bool,bool,bool,ulong,ulong,bool,ulong,ulong,bool,ulong,RtlArray<ushort const *> const *,RtlArray<ushort const *> const *,RtlArray<ushort const *> const *,_LARGE_INTEGER,bool,ushort const *,ushort const *,Windows::Compat::Appraiser::DataFile *,ushort const *,ushort const *,bool)
0x1800de014  mov     edi, eax
0x1800de016  mov     r8, [rbp+80h+lpMem+8]; lpMem
  ... truncated ...
```
