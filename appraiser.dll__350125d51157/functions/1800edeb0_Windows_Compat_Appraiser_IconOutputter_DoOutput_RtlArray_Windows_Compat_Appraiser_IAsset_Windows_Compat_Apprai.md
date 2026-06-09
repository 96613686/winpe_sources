# Windows::Compat::Appraiser::IconOutputter::DoOutput(RtlArray<Windows::Compat::Appraiser::IAsset *> *,Windows::Compat::Appraiser::WicaRun *)

- ea: `0x1800edeb0`
- end: `0x1800ee56c`
- name: `?DoOutput@IconOutputter@Appraiser@Compat@Windows@@UEAAJPEAV?$RtlArray@PEAVIAsset@Appraiser@Compat@Windows@@@@PEAUWicaRun@234@@Z`
- size: `1724`
- prototype: `__int64 __fastcall(Windows::Compat::Appraiser::IconOutputter *this, unsigned __int64 *, __int64 *)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800018a0`
- `0x180008570`
- `0x180013c7c`
- `0x1800151f4`
- `0x180029258`
- `0x18002ebb8`
- `0x1800301d0`
- `0x1800ad680`
- `0x1800ae378`
- `0x1800b1474`
- `0x1800edeb0`
- `0x1800ee574`
- `0x1800ee988`
- `0x1800eeb40`
- `0x1800ef074`
- `0x1802174cc`
- `0x18021f010`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x1800edfb6`
- `KERNEL32!GetSystemTime` at `0x1800ee430`
- `KERNEL32!GetSystemTime` at `0x1800edfb6`
- `KERNEL32!GetSystemTime` at `0x1800ee430`
- `KERNEL32!LoadLibraryExW` at `0x1800ee0eb`
- `KERNEL32!LoadLibraryExW` at `0x1800ee0eb`
- `KERNEL32!FreeLibrary` at `0x1800ee37b`
- `KERNEL32!FreeLibrary` at `0x1800ee37b`
- `KERNEL32!GetLastError` at `0x1800ee4ad`
- `KERNEL32!GetLastError` at `0x1800ee4ad`

## string_xrefs

- `0x1800ee0b7`: `onecore\base\appcompat\appraiser\outputters\icon.cpp`
- `0x1800ee13d`: `onecore\base\appcompat\appraiser\outputters\icon.cpp`
- `0x1800ee20b`: `onecore\base\appcompat\appraiser\outputters\icon.cpp`
- `0x1800ee242`: `onecore\base\appcompat\appraiser\outputters\icon.cpp`
- `0x1800ee344`: `onecore\base\appcompat\appraiser\outputters\icon.cpp`
- `0x1800ee4e4`: `onecore\base\appcompat\appraiser\outputters\icon.cpp`
- `0x1800ee54a`: `onecore\base\appcompat\appraiser\outputters\icon.cpp`
- `0x1800ee0e4`: `gdiplus.dll`
- `0x1800ee0b0`: `Windows::Compat::Appraiser::IconOutputter::DoOutput`
- `0x1800ee136`: `Windows::Compat::Appraiser::IconOutputter::DoOutput`
- `0x1800ee33d`: `Windows::Compat::Appraiser::IconOutputter::DoOutput`
- `0x1800ee4dd`: `Windows::Compat::Appraiser::IconOutputter::DoOutput`
- `0x1800ee551`: `Windows::Compat::Appraiser::IconOutputter::DoOutput`
- `0x1800ee4cd`: `Failed to load gdiplus.dll`
- `0x1800ee204`: `Windows::Compat::Appraiser::IconOutputter::ExtractSystemIconToIconPath`
- `0x1800ee23b`: `Windows::Compat::Appraiser::IconOutputter::ExtractSystemIconToIconPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Compat::Appraiser::IconOutputter::DoOutput(
        Windows::Compat::Appraiser::IconOutputter *this,
        unsigned __int64 *a2,
        __int64 *a3)
{
  volatile signed __int64 *v6; // rcx
  void **v7; // rdx
  int v8; // ebx
  __int64 v9; // rdx
  const size_t *v10; // r8
  int v11; // r8d
  int v12; // r9d
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // r15
  struct Windows::Compat::Appraiser::IAsset **v15; // rdx
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // rcx
  struct Windows::Compat::Appraiser::IAsset *v18; // r14
  int v19; // eax
  signed int RequiredSingleValue; // ebx
  wchar_t *v21; // rdi
  int AppIconToIconPath; // eax
  int v23; // ebx
  int v24; // eax
  volatile signed __int64 *v25; // rcx
  void **v26; // rdx
  int v27; // edi
  int v28; // r8d
  int v29; // r9d
  signed int LastError; // eax
  const char *v32; // rax
  char v33; // dl
  struct Windows::Compat::Appraiser::TableCache *v34; // [rsp+28h] [rbp-E0h]
  unsigned __int16 *v35; // [rsp+30h] [rbp-D8h]
  char *v36; // [rsp+38h] [rbp-D0h]
  bool v37[8]; // [rsp+48h] [rbp-C0h] BYREF
  char *v38; // [rsp+50h] [rbp-B8h] BYREF
  char *v39; // [rsp+58h] [rbp-B0h] BYREF
  char v40[8]; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v41; // [rsp+68h] [rbp-A0h] BYREF
  const wchar_t *SystemTime[3]; // [rsp+70h] [rbp-98h] BYREF
  void **v43; // [rsp+88h] [rbp-80h] BYREF
  __int64 v44; // [rsp+90h] [rbp-78h]
  __int64 v45; // [rsp+98h] [rbp-70h]
  __int64 v46; // [rsp+A0h] [rbp-68h]
  __int128 v47; // [rsp+A8h] [rbp-60h] BYREF
  char v48[144]; // [rsp+B8h] [rbp-50h] BYREF
  char v49[144]; // [rsp+148h] [rbp+40h] BYREF

  v46 = -2;
  v43 = &Windows::Compat::Appraiser::MetadataPropertyEnumerator::`vftable';
  v44 = 0;
  v45 = 0;
  SystemTime[0] = 0;
  v37[0] = 0;
  TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v48);
  v6 = (volatile signed __int64 *)v48;
  if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
    v6 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v6,
    _InterlockedExchangeAdd64(v6 + 17, 0),
    v49);
  if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
    UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v7);
  v8 = qword_1802C9628;
  v9 = 0x200000000020LL;
  v10 = &szValueBuf;
  if ( *(_DWORD *)qword_1802C9628 > 5u
    && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000020LL) != 0
    && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000020LL) == *(_QWORD *)(qword_1802C9628 + 24) )
  {
    v39 = v49;
    *(_QWORD *)v40 = 0x1000000;
    v41 = (__int64)&szValueBuf;
    *(_OWORD *)&SystemTime[1] = 0;
    GetSystemTime((LPSYSTEMTIME)&SystemTime[1]);
    v47 = *(_OWORD *)&SystemTime[1];
    v38 = (char *)&v47;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
      v8,
      (unsigned int)byte_1802A4931,
      v11,
      v12,
      (__int64)&v38,
      (__int64)&v41,
      (__int64)v40,
      (__int64)&v39);
  }
  v37[0] = 0;
  *((_BYTE *)this + 544) = 0;
  v45 = *a3;
  HIDWORD(v44) = *((_DWORD *)a3 + 16);
  ((void (__fastcall *)(void ***, __int64, const size_t *))v43[1])(&v43, v9, v10);
  v13 = a2[2];
  if ( !v13 )
  {
LABEL_53:
    RequiredSingleValue = 0;
    goto LABEL_54;
  }
  v14 = 0;
  while ( 1 )
  {
    v15 = 0;
    if ( v14 < v13 )
    {
      v38 = 0;
      v16 = a2[1] * v14;
      if ( !is_mul_ok(a2[1], v14)
        || (v17 = a2[5], v15 = (struct Windows::Compat::Appraiser::IAsset **)(v17 + v16), v17 + v16 < v17) )
      {
        v15 = 0;
      }
    }
    v18 = *v15;
    v19 = Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable(
            v37,
            *v15,
            *((struct Windows::Compat::Appraiser::Table **)this + 67),
            (struct Windows::Compat::Appraiser::IPropertyListEnumerator *)&v43,
            v34,
            0);
    RequiredSingleValue = v19;
    if ( v19 < 0 )
    {
      v32 = "Error filtering: [0x%x].";
      v33 = -78;
LABEL_74:
      LODWORD(v36) = RequiredSingleValue;
      goto LABEL_75;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xB2u,
        "onecore\\base\\appcompat\\appraiser\\outputters\\icon.cpp",
        "Windows::Compat::Appraiser::IconOutputter::DoOutput",
        "Error filtering: [0x%x].",
        v19);
    if ( !v37[0] )
      goto LABEL_52;
    if ( !gdiplusModule )
    {
      gdiplusModule = LoadLibraryExW(L"gdiplus.dll", 0, 0x800u);
      if ( !gdiplusModule )
        break;
    }
    RequiredSingleValue = Windows::Compat::Appraiser::AssetUtils::GetRequiredSingleValue(
                            SystemTime,
                            L"AssetType",
                            v18,
                            1);
    if ( RequiredSingleValue < 0 )
    {
      LODWORD(v36) = RequiredSingleValue;
      v35 = (unsigned __int16 *)"Error getting asset type: [0x%x].";
      v33 = -60;
LABEL_76:
      LODWORD(v34) = RequiredSingleValue;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        v33,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\icon.cpp",
        "Windows::Compat::Appraiser::IconOutputter::DoOutput",
        (const char *)v34,
        (int)v35,
        v36);
      goto LABEL_54;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xC4u,
        "onecore\\base\\appcompat\\appraiser\\outputters\\icon.cpp",
        "Windows::Compat::Appraiser::IconOutputter::DoOutput",
        "Error getting asset type: [0x%x].",
        RequiredSingleValue);
    v21 = (wchar_t *)SystemTime[0];
    if ( !wcscmp_0(L"Application", SystemTime[0]) )
    {
      AppIconToIconPath = Windows::Compat::Appraiser::IconOutputter::ExtractAppIconToIconPath(this, v18);
LABEL_47:
      v23 = AppIconToIconPath;
      goto LABEL_48;
    }
    if ( !wcscmp_0(L"Device", v21) )
    {
      AppIconToIconPath = Windows::Compat::Appraiser::IconOutputter::ExtractDeviceIconToIconPath(this, v18);
      goto LABEL_47;
    }
    if ( !wcscmp_0(L"File", v21) )
    {
      AppIconToIconPath = Windows::Compat::Appraiser::IconOutputter::ExtractFileIconToIconPath(this, v18);
      goto LABEL_47;
    }
    if ( !Windows::Compat::Appraiser::AssetUtils::IsAssetTypeSystem(v21) )
    {
      if ( wcscmp_0(L"BlockingMatchingInfo", v21)
        && wcscmp_0(L"PassiveMatchingInfo", v21)
        && wcscmp_0(L"PostUpgradeMatchingInfo", v21)
        && wcscmp_0(L"BlockingMatchingInfoEntry", v21)
        && wcscmp_0(L"PassiveMatchingInfoEntry", v21)
        && wcscmp_0(L"PostUpgradeMatchingInfoEntry", v21)
        && wcscmp_0(L"MediaCenter", v21)
        && wcscmp_0(L"Wmdrm", v21) )
      {
        RequiredSingleValue = -2147467263;
        v36 = (char *)v21;
        v32 = "Icon fetching for AssetType %ls is not currently implemented.";
        v33 = -28;
LABEL_75:
        LODWORD(v35) = (_DWORD)v32;
        goto LABEL_76;
      }
      AppIconToIconPath = Windows::Compat::Appraiser::IconOutputter::UseDefaultImage(this, v18);
      goto LABEL_47;
    }
    if ( *((_BYTE *)this + 544) )
    {
      v23 = 1;
    }
    else
    {
      v24 = Windows::Compat::Appraiser::IconOutputter::UseDefaultImage(this, v18);
      v23 = v24;
      if ( v24 >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x1B8u,
            "onecore\\base\\appcompat\\appraiser\\outputters\\icon.cpp",
            "Windows::Compat::Appraiser::IconOutputter::ExtractSystemIconToIconPath",
            "Failed to get generic SystemBlock image: [0x%x].",
            v24);
        *((_BYTE *)this + 544) = 1;
        v23 = 0;
      }
      else
      {
        LODWORD(v36) = v24;
        LODWORD(v34) = v24;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          184,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\icon.cpp",
          "Windows::Compat::Appraiser::IconOutputter::ExtractSystemIconToIconPath",
          (const char *)v34,
          (int)"Failed to get generic SystemBlock image: [0x%x].",
          v36);
      }
    }
LABEL_48:
    if ( v23 < 0 )
    {
      RequiredSingleValue = Windows::Compat::Appraiser::IconOutputter::UseDefaultImage(this, v18);
      if ( RequiredSingleValue >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0xEAu,
            "onecore\\base\\appcompat\\appraiser\\outputters\\icon.cpp",
            "Windows::Compat::Appraiser::IconOutputter::DoOutput",
            "Failed to get Default Icon: [0x%x]",
            RequiredSingleValue);
        goto LABEL_52;
      }
      v32 = "Failed to get Default Icon: [0x%x]";
      v33 = -22;
      goto LABEL_74;
    }
LABEL_52:
    ++v14;
    v13 = a2[2];
    if ( v14 >= v13 )
      goto LABEL_53;
  }
  LastError = GetLastError();
  RequiredSingleValue = LastError;
  if ( LastError > 0 )
    RequiredSingleValue = (unsigned __int16)LastError | 0x80070000;
  if ( RequiredSingleValue >= 0 )
    RequiredSingleValue = -2147467259;
  LODWORD(v34) = RequiredSingleValue;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    190,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\icon.cpp",
    "Windows::Compat::Appraiser::IconOutputter::DoOutput",
    (const char *)v34,
    (int)"Failed to load gdiplus.dll",
    v36);
LABEL_54:
  if ( gdiplusModule )
  {
    FreeLibrary(gdiplusModule);
    gdiplusModule = 0;
  }
  TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v48);
  v25 = (volatile signed __int64 *)v48;
  if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
    v25 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v25,
    _InterlockedExchangeAdd64(v25 + 17, 0),
    v49);
  if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
    UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v26);
  v27 = qword_1802C9628;
  if ( *(_DWORD *)qword_1802C9628 > 5u
    && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000020LL) != 0
    && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000020LL) == *(_QWORD *)(qword_1802C9628 + 24) )
  {
    v38 = v49;
    v41 = 0x1000000;
    *(_QWORD *)v40 = &szValueBuf;
    *(_OWORD *)&SystemTime[1] = 0;
    GetSystemTime((LPSYSTEMTIME)&SystemTime[1]);
    v47 = *(_OWORD *)&SystemTime[1];
    v39 = (char *)&v47;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
      v27,
      (unsigned int)&byte_1802A48E7,
      v28,
      v29,
      (__int64)&v39,
      (__int64)v40,
      (__int64)&v41,
      (__int64)&v38);
  }
  return (unsigned int)RequiredSingleValue;
}

```

## disassembly

```asm
0x1800edeb0  mov     rax, rsp
0x1800edeb3  push    rbp
0x1800edeb4  push    rsi
0x1800edeb5  push    rdi
0x1800edeb6  push    r12
0x1800edeb8  push    r13
0x1800edeba  push    r14
0x1800edebc  push    r15
0x1800edebe  lea     rbp, [rax-118h]
0x1800edec5  sub     rsp, 1E0h
0x1800edecc  mov     [rbp+110h+var_178], 0FFFFFFFFFFFFFFFEh
0x1800eded4  mov     [rax+18h], rbx
0x1800eded8  mov     rax, cs:__security_cookie
0x1800ededf  xor     rax, rsp
0x1800edee2  mov     [rbp+110h+var_40], rax
0x1800edee9  mov     rdi, r8
0x1800edeec  mov     r13, rdx
0x1800edeef  mov     rsi, rcx
0x1800edef2  lea     rax, ??_7MetadataPropertyEnumerator@Appraiser@Compat@Windows@@6B@; const Windows::Compat::Appraiser::MetadataPropertyEnumerator::`vftable'
0x1800edef9  mov     [rbp+110h+var_190], rax
0x1800edefd  xor     r12d, r12d
0x1800edf00  mov     [rbp+110h+var_188], r12
0x1800edf04  mov     [rbp+110h+var_180], r12
0x1800edf08  mov     qword ptr [rsp+210h+SystemTime], r12
0x1800edf0d  mov     [rsp+210h+var_1D0], r12b
0x1800edf12  lea     rcx, [rbp+110h+var_160]; this
0x1800edf16  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1800edf1b  lea     rcx, [rbp+110h+var_160]
0x1800edf1f  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x1800edf26  test    rax, rax
0x1800edf29  cmovnz  rcx, rax; this
0x1800edf2d  mov     edx, r12d
0x1800edf30  lock xadd [rcx+88h], rdx; unsigned __int64
0x1800edf39  lea     r8, [rbp+110h+var_D0]; char *
0x1800edf3d  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1800edf42  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, r12b; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x1800edf49  jz      short loc_1800EDF57
0x1800edf4b  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x1800edf52  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x1800edf57  mov     rbx, cs:qword_1802C9628
0x1800edf5e  mov     eax, [rbx]
0x1800edf60  mov     rdx, 200000000020h
0x1800edf6a  lea     r8, szValueBuf
0x1800edf71  cmp     eax, 5
0x1800edf74  jbe     loc_1800EE006
0x1800edf7a  mov     rcx, [rbx+18h]
0x1800edf7e  mov     rax, [rbx+10h]
0x1800edf82  test    rdx, rax
0x1800edf85  jz      short loc_1800EE006
0x1800edf87  mov     rax, rcx
0x1800edf8a  and     rax, rdx
0x1800edf8d  cmp     rax, rcx
0x1800edf90  jnz     short loc_1800EE006
0x1800edf92  lea     rax, [rbp+110h+var_D0]
0x1800edf96  mov     [rsp+210h+var_1C0], rax
0x1800edf9b  mov     qword ptr [rsp+210h+var_1B8], 1000000h
0x1800edfa4  mov     [rsp+210h+var_1B0], r8
0x1800edfa9  xorps   xmm0, xmm0
0x1800edfac  movups  xmmword ptr [rsp+210h+SystemTime+8], xmm0
0x1800edfb1  lea     rcx, [rsp+210h+SystemTime+8]; lpSystemTime
0x1800edfb6  call    cs:__imp_GetSystemTime
0x1800edfbc  movaps  xmm0, xmmword ptr [rsp+210h+SystemTime+8]
0x1800edfc1  movdqa  [rbp+110h+var_170], xmm0
0x1800edfc6  lea     rax, [rbp+110h+var_170]
0x1800edfca  mov     [rsp+210h+var_1C8], rax
0x1800edfcf  lea     rax, [rsp+210h+var_1C0]
0x1800edfd4  mov     qword ptr [rsp+210h+var_1D8], rax
0x1800edfd9  lea     rax, [rsp+210h+var_1B8]
0x1800edfde  mov     [rsp+210h+var_1E0], rax; char *
0x1800edfe3  lea     rax, [rsp+210h+var_1B0]
0x1800edfe8  mov     [rsp+210h+var_1E8], rax
0x1800edfed  lea     rax, [rsp+210h+var_1C8]
0x1800edff2  mov     [rsp+210h+var_1F0], rax; struct Windows::Compat::Appraiser::TableCache *
0x1800edff7  lea     rdx, byte_1802A4931
0x1800edffe  mov     rcx, rbx
0x1800ee001  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x1800ee006  mov     [rsp+210h+var_1D0], r12b
0x1800ee00b  mov     [rsi+220h], r12b
0x1800ee012  mov     rax, [rdi]
0x1800ee015  mov     [rbp+110h+var_180], rax
0x1800ee019  mov     eax, [rdi+40h]
0x1800ee01c  mov     dword ptr [rbp+110h+var_188+4], eax
0x1800ee01f  mov     rax, [rbp+110h+var_190]
0x1800ee023  lea     rcx, [rbp+110h+var_190]
0x1800ee027  mov     rax, [rax+8]
0x1800ee02b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee030  mov     rax, [r13+10h]
0x1800ee034  test    rax, rax
0x1800ee037  jz      loc_1800EE36C
0x1800ee03d  mov     r15, r12
0x1800ee040  lea     rdi, aErrorGettingAs_0; "Error getting asset type: [0x%x]."
0x1800ee047  mov     rdx, r12
0x1800ee04a  cmp     r15, rax
0x1800ee04d  jnb     short loc_1800EE070
0x1800ee04f  mov     [rsp+210h+var_1C8], r12
0x1800ee054  mov     rax, r15
0x1800ee057  mul     qword ptr [r13+8]
0x1800ee05b  test    rdx, rdx
0x1800ee05e  jnz     short loc_1800EE06D
0x1800ee060  mov     rcx, [r13+28h]
0x1800ee064  lea     rdx, [rcx+rax]
0x1800ee068  cmp     rdx, rcx
0x1800ee06b  jnb     short loc_1800EE070
0x1800ee06d  mov     rdx, r12
0x1800ee070  mov     r14, [rdx]
0x1800ee073  mov     [rsp+210h+var_1E8], r12; unsigned __int16 *
0x1800ee078  lea     r9, [rbp+110h+var_190]; struct Windows::Compat::Appraiser::IPropertyListEnumerator *
0x1800ee07c  mov     r8, [rsi+218h]; struct Windows::Compat::Appraiser::Table *
0x1800ee083  mov     rdx, r14; struct Windows::Compat::Appraiser::IAsset *
0x1800ee086  lea     rcx, [rsp+210h+var_1D0]; bool *
0x1800ee08b  call    ?EvaluateTable@ConstraintTableQuery@Appraiser@Compat@Windows@@SAJPEA_NPEAVIAsset@234@PEAVTable@234@PEAVIPropertyListEnumerator@234@PEAVTableCache@234@PEBG@Z; Windows::Compat::Appraiser::ConstraintTableQuery::EvaluateTable(bool *,Windows::Compat::Appraiser::IAsset *,Windows::Compat::Appraiser::Table *,Windows::Compat::Appraiser::IPropertyListEnumerator *,Windows::Compat::Appraiser::TableCache *,ushort const *)
0x1800ee090  mov     ebx, eax
0x1800ee092  test    eax, eax
0x1800ee094  js      loc_1800EE535
0x1800ee09a  mov     ecx, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800ee0a0  test    cl, 1
0x1800ee0a3  jz      short loc_1800EE0C8
0x1800ee0a5  mov     dword ptr [rsp+210h+var_1F0], eax
0x1800ee0a9  lea     r9, aErrorFiltering; "Error filtering: [0x%x]."
0x1800ee0b0  lea     r8, aWindowsCompatA_248; "Windows::Compat::Appraiser::IconOutputt"...
0x1800ee0b7  lea     rdx, aOnecoreBaseApp_93; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800ee0be  mov     ecx, 0B2h; unsigned int
0x1800ee0c3  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800ee0c8  cmp     [rsp+210h+var_1D0], r12b
0x1800ee0cd  jz      loc_1800EE35C
0x1800ee0d3  cmp     cs:gdiplusModule, r12
0x1800ee0da  jnz     short loc_1800EE101
0x1800ee0dc  xor     edx, edx; hFile
0x1800ee0de  mov     r8d, 800h; dwFlags
0x1800ee0e4  lea     rcx, aGdiplusDll; "gdiplus.dll"
0x1800ee0eb  call    cs:__imp_LoadLibraryExW
0x1800ee0f1  mov     cs:gdiplusModule, rax
0x1800ee0f8  test    rax, rax
0x1800ee0fb  jz      loc_1800EE4AD
0x1800ee101  mov     r9d, 1
0x1800ee107  mov     r8, r14
0x1800ee10a  lea     rdx, aAssettype; "AssetType"
0x1800ee111  lea     rcx, [rsp+210h+SystemTime]
0x1800ee116  call    ?GetRequiredSingleValue@AssetUtils@Appraiser@Compat@Windows@@SAJPEAPEBGPEBGPEAVIAsset@234@W4Tier@234@@Z; Windows::Compat::Appraiser::AssetUtils::GetRequiredSingleValue(ushort const * *,ushort const *,Windows::Compat::Appraiser::IAsset *,Windows::Compat::Appraiser::Tier)
0x1800ee11b  mov     ebx, eax
0x1800ee11d  test    eax, eax
0x1800ee11f  js      loc_1800EE525
0x1800ee125  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800ee12b  test    al, 1
0x1800ee12d  jz      short loc_1800EE14E
0x1800ee12f  mov     dword ptr [rsp+210h+var_1F0], ebx
0x1800ee133  mov     r9, rdi; char *
0x1800ee136  lea     r8, aWindowsCompatA_248; "Windows::Compat::Appraiser::IconOutputt"...
0x1800ee13d  lea     rdx, aOnecoreBaseApp_93; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800ee144  mov     ecx, 0C4h; unsigned int
0x1800ee149  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800ee14e  mov     rdi, qword ptr [rsp+210h+SystemTime]
0x1800ee153  mov     rdx, rdi; String2
0x1800ee156  lea     rcx, aApplication; "Application"
0x1800ee15d  call    wcscmp_0
0x1800ee162  test    eax, eax
0x1800ee164  jnz     short loc_1800EE176
0x1800ee166  mov     rdx, r14; struct Windows::Compat::Appraiser::IAsset *
0x1800ee169  mov     rcx, rsi; this
0x1800ee16c  call    ?ExtractAppIconToIconPath@IconOutputter@Appraiser@Compat@Windows@@AEAAJPEAVIAsset@234@@Z; Windows::Compat::Appraiser::IconOutputter::ExtractAppIconToIconPath(Windows::Compat::Appraiser::IAsset *)
0x1800ee171  jmp     loc_1800EE30D
0x1800ee176  mov     rdx, rdi; String2
0x1800ee179  lea     rcx, aDevice_0; "Device"
0x1800ee180  call    wcscmp_0
0x1800ee185  test    eax, eax
0x1800ee187  jnz     short loc_1800EE199
0x1800ee189  mov     rdx, r14; struct Windows::Compat::Appraiser::IAsset *
0x1800ee18c  mov     rcx, rsi; this
0x1800ee18f  call    ?ExtractDeviceIconToIconPath@IconOutputter@Appraiser@Compat@Windows@@AEAAJPEAVIAsset@234@@Z; Windows::Compat::Appraiser::IconOutputter::ExtractDeviceIconToIconPath(Windows::Compat::Appraiser::IAsset *)
0x1800ee194  jmp     loc_1800EE30D
0x1800ee199  mov     rdx, rdi; String2
0x1800ee19c  lea     rcx, aFile_0; "File"
0x1800ee1a3  call    wcscmp_0
0x1800ee1a8  test    eax, eax
0x1800ee1aa  jnz     short loc_1800EE1BC
0x1800ee1ac  mov     rdx, r14; struct Windows::Compat::Appraiser::IAsset *
0x1800ee1af  mov     rcx, rsi; this
0x1800ee1b2  call    ?ExtractFileIconToIconPath@IconOutputter@Appraiser@Compat@Windows@@AEAAJPEAVIAsset@234@@Z; Windows::Compat::Appraiser::IconOutputter::ExtractFileIconToIconPath(Windows::Compat::Appraiser::IAsset *)
0x1800ee1b7  jmp     loc_1800EE30D
0x1800ee1bc  mov     rcx, rdi; String2
0x1800ee1bf  call    ?IsAssetTypeSystem@AssetUtils@Appraiser@Compat@Windows@@SA_NPEBG@Z; Windows::Compat::Appraiser::AssetUtils::IsAssetTypeSystem(ushort const *)
0x1800ee1c4  test    al, al
0x1800ee1c6  jz      loc_1800EE262
0x1800ee1cc  cmp     [rsi+220h], r12b
0x1800ee1d3  jz      short loc_1800EE1DF
0x1800ee1d5  mov     ebx, 1
0x1800ee1da  jmp     loc_1800EE30F
0x1800ee1df  mov     rdx, r14; struct Windows::Compat::Appraiser::IAsset *
0x1800ee1e2  mov     rcx, rsi; this
0x1800ee1e5  call    ?UseDefaultImage@IconOutputter@Appraiser@Compat@Windows@@AEAAJPEAVIAsset@234@@Z; Windows::Compat::Appraiser::IconOutputter::UseDefaultImage(Windows::Compat::Appraiser::IAsset *)
0x1800ee1ea  mov     ebx, eax
0x1800ee1ec  test    eax, eax
0x1800ee1ee  jns     short loc_1800EE226
0x1800ee1f0  mov     dword ptr [rsp+210h+var_1E0], eax; char *
0x1800ee1f4  lea     rax, aFailedToGetGen; "Failed to get generic SystemBlock image"...
0x1800ee1fb  mov     [rsp+210h+var_1E8], rax; int
0x1800ee200  mov     dword ptr [rsp+210h+var_1F0], ebx; char *
0x1800ee204  lea     r9, aWindowsCompatA_545; "Windows::Compat::Appraiser::IconOutputt"...
0x1800ee20b  lea     r8, aOnecoreBaseApp_93; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800ee212  mov     edx, 1B8h; bool
0x1800ee217  mov     ecx, 1; this
0x1800ee21c  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800ee221  jmp     loc_1800EE30F
0x1800ee226  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800ee22c  test    al, 1
0x1800ee22e  jz      short loc_1800EE253
0x1800ee230  mov     dword ptr [rsp+210h+var_1F0], ebx
0x1800ee234  lea     r9, aFailedToGetGen; "Failed to get generic SystemBlock image"...
0x1800ee23b  lea     r8, aWindowsCompatA_545; "Windows::Compat::Appraiser::IconOutputt"...
0x1800ee242  lea     rdx, aOnecoreBaseApp_93; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800ee249  mov     ecx, 1B8h; unsigned int
0x1800ee24e  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800ee253  mov     byte ptr [rsi+220h], 1
0x1800ee25a  mov     ebx, r12d
0x1800ee25d  jmp     loc_1800EE30F
0x1800ee262  mov     rdx, rdi; String2
0x1800ee265  lea     rcx, aBlockingmatchi_1; "BlockingMatchingInfo"
0x1800ee26c  call    wcscmp_0
0x1800ee271  test    eax, eax
0x1800ee273  jz      loc_1800EE302
0x1800ee279  mov     rdx, rdi; String2
0x1800ee27c  lea     rcx, aPassivematchin_0; "PassiveMatchingInfo"
0x1800ee283  call    wcscmp_0
0x1800ee288  test    eax, eax
0x1800ee28a  jz      short loc_1800EE302
0x1800ee28c  mov     rdx, rdi; String2
0x1800ee28f  lea     rcx, aPostupgrademat_0; "PostUpgradeMatchingInfo"
0x1800ee296  call    wcscmp_0
0x1800ee29b  test    eax, eax
0x1800ee29d  jz      short loc_1800EE302
0x1800ee29f  mov     rdx, rdi; String2
0x1800ee2a2  lea     rcx, aBlockingmatchi_0; "BlockingMatchingInfoEntry"
0x1800ee2a9  call    wcscmp_0
0x1800ee2ae  test    eax, eax
0x1800ee2b0  jz      short loc_1800EE302
0x1800ee2b2  mov     rdx, rdi; String2
0x1800ee2b5  lea     rcx, aPassivematchin; "PassiveMatchingInfoEntry"
0x1800ee2bc  call    wcscmp_0
0x1800ee2c1  test    eax, eax
0x1800ee2c3  jz      short loc_1800EE302
0x1800ee2c5  mov     rdx, rdi; String2
0x1800ee2c8  lea     rcx, aPostupgrademat; "PostUpgradeMatchingInfoEntry"
0x1800ee2cf  call    wcscmp_0
0x1800ee2d4  test    eax, eax
0x1800ee2d6  jz      short loc_1800EE302
0x1800ee2d8  mov     rdx, rdi; String2
0x1800ee2db  lea     rcx, aMediacenter; "MediaCenter"
0x1800ee2e2  call    wcscmp_0
0x1800ee2e7  test    eax, eax
0x1800ee2e9  jz      short loc_1800EE302
0x1800ee2eb  mov     rdx, rdi; String2
0x1800ee2ee  lea     rcx, aWmdrm; "Wmdrm"
0x1800ee2f5  call    wcscmp_0
0x1800ee2fa  test    eax, eax
0x1800ee2fc  jnz     loc_1800EE4FF
0x1800ee302  mov     rdx, r14; struct Windows::Compat::Appraiser::IAsset *
0x1800ee305  mov     rcx, rsi; this
0x1800ee308  call    ?UseDefaultImage@IconOutputter@Appraiser@Compat@Windows@@AEAAJPEAVIAsset@234@@Z; Windows::Compat::Appraiser::IconOutputter::UseDefaultImage(Windows::Compat::Appraiser::IAsset *)
0x1800ee30d  mov     ebx, eax
0x1800ee30f  test    ebx, ebx
0x1800ee311  jns     short loc_1800EE355
0x1800ee313  mov     rdx, r14; struct Windows::Compat::Appraiser::IAsset *
0x1800ee316  mov     rcx, rsi; this
0x1800ee319  call    ?UseDefaultImage@IconOutputter@Appraiser@Compat@Windows@@AEAAJPEAVIAsset@234@@Z; Windows::Compat::Appraiser::IconOutputter::UseDefaultImage(Windows::Compat::Appraiser::IAsset *)
0x1800ee31e  mov     ebx, eax
0x1800ee320  test    eax, eax
0x1800ee322  js      loc_1800EE517
0x1800ee328  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800ee32e  test    al, 1
0x1800ee330  jz      short loc_1800EE355
0x1800ee332  mov     dword ptr [rsp+210h+var_1F0], ebx
0x1800ee336  lea     r9, aFailedToGetDef; "Failed to get Default Icon: [0x%x]"
0x1800ee33d  lea     r8, aWindowsCompatA_248; "Windows::Compat::Appraiser::IconOutputt"...
0x1800ee344  lea     rdx, aOnecoreBaseApp_93; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800ee34b  mov     ecx, 0EAh; unsigned int
0x1800ee350  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800ee355  lea     rdi, aErrorGettingAs_0; "Error getting asset type: [0x%x]."
0x1800ee35c  inc     r15
0x1800ee35f  mov     rax, [r13+10h]
0x1800ee363  cmp     r15, rax
0x1800ee366  jb      loc_1800EE047
0x1800ee36c  mov     ebx, r12d
0x1800ee36f  mov     rcx, cs:gdiplusModule; hLibModule
0x1800ee376  test    rcx, rcx
0x1800ee379  jz      short loc_1800EE388
0x1800ee37b  call    cs:__imp_FreeLibrary
0x1800ee381  mov     cs:gdiplusModule, r12
0x1800ee388  lea     rcx, [rbp+110h+var_160]; this
0x1800ee38c  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1800ee391  lea     rcx, [rbp+110h+var_160]
0x1800ee395  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x1800ee39c  test    rax, rax
0x1800ee39f  cmovnz  rcx, rax; this
0x1800ee3a3  mov     rdx, r12
0x1800ee3a6  lock xadd [rcx+88h], rdx; unsigned __int64
0x1800ee3af  lea     r8, [rbp+110h+var_D0]; char *
0x1800ee3b3  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1800ee3b8  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, r12b; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x1800ee3bf  jz      short loc_1800EE3CD
0x1800ee3c1  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
  ... truncated ...
```
