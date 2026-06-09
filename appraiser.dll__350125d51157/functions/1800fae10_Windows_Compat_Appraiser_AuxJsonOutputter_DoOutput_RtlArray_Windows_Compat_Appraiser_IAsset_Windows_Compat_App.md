# Windows::Compat::Appraiser::AuxJsonOutputter::DoOutput(RtlArray<Windows::Compat::Appraiser::IAsset *> *,Windows::Compat::Appraiser::WicaRun *)

- ea: `0x1800fae10`
- end: `0x1800fba24`
- name: `?DoOutput@AuxJsonOutputter@Appraiser@Compat@Windows@@UEAAJPEAV?$RtlArray@PEAVIAsset@Appraiser@Compat@Windows@@@@PEAUWicaRun@234@@Z`
- size: `3092`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1800018a0`
- `0x180002a0c`
- `0x180008570`
- `0x180008a1c`
- `0x18000a594`
- `0x180013c7c`
- `0x1800151f4`
- `0x180029258`
- `0x18002ebb8`
- `0x1800301d0`
- `0x1800a5d88`
- `0x1800a817c`
- `0x1800b5e8c`
- `0x1800b5f90`
- `0x1800f8f4c`
- `0x1800f9264`
- `0x1800f9350`
- `0x1800fa900`
- `0x1800fae10`
- `0x1800fcc90`
- `0x18020f158`
- `0x18021f010`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x1800faefa`
- `KERNEL32!GetSystemTime` at `0x1800fb699`
- `KERNEL32!GetSystemTime` at `0x1800fb995`
- `KERNEL32!GetSystemTime` at `0x1800faefa`
- `KERNEL32!GetSystemTime` at `0x1800fb699`
- `KERNEL32!GetSystemTime` at `0x1800fb995`
- `KERNEL32!GetProcessHeap` at `0x1800faf7b`
- `KERNEL32!GetProcessHeap` at `0x1800fb005`
- `KERNEL32!GetProcessHeap` at `0x1800faf7b`
- `KERNEL32!GetProcessHeap` at `0x1800fb005`
- `KERNEL32!HeapFree` at `0x1800fafef`
- `KERNEL32!HeapFree` at `0x1800fb8e1`
- `KERNEL32!HeapFree` at `0x1800fb9f1`
- `KERNEL32!HeapFree` at `0x1800fafef`
- `KERNEL32!HeapFree` at `0x1800fb8e1`
- `KERNEL32!HeapFree` at `0x1800fb9f1`

## string_xrefs

- `0x1800fb045`: `onecore\base\appcompat\appraiser\outputters\auxjson.cpp`
- `0x1800fb0b1`: `onecore\base\appcompat\appraiser\outputters\auxjson.cpp`
- `0x1800fb0e8`: `onecore\base\appcompat\appraiser\outputters\auxjson.cpp`
- `0x1800fb270`: `onecore\base\appcompat\appraiser\outputters\auxjson.cpp`
- `0x1800fb2c1`: `onecore\base\appcompat\appraiser\outputters\auxjson.cpp`
- `0x1800fb312`: `onecore\base\appcompat\appraiser\outputters\auxjson.cpp`
- `0x1800fb363`: `onecore\base\appcompat\appraiser\outputters\auxjson.cpp`
- `0x1800fb41e`: `onecore\base\appcompat\appraiser\outputters\auxjson.cpp`
- `0x1800fb49b`: `onecore\base\appcompat\appraiser\outputters\auxjson.cpp`
- `0x1800fb4d5`: `onecore\base\appcompat\appraiser\outputters\auxjson.cpp`
- `0x1800fb56f`: `onecore\base\appcompat\appraiser\outputters\auxjson.cpp`
- `0x1800fb772`: `onecore\base\appcompat\appraiser\outputters\auxjson.cpp`
- `0x1800fb7ab`: `onecore\base\appcompat\appraiser\outputters\auxjson.cpp`
- `0x1800fb09a`: `Failed to create sorted AuxBucketArray: [0x%x].`
- `0x1800fb0da`: `Failed to create sorted AuxBucketArray: [0x%x].`
- `0x1800fb03e`: `Windows::Compat::Appraiser::AuxJsonOutputter::DoOutput`
- `0x1800fb0aa`: `Windows::Compat::Appraiser::AuxJsonOutputter::DoOutput`
- `0x1800fb0e1`: `Windows::Compat::Appraiser::AuxJsonOutputter::DoOutput`
- `0x1800fb269`: `Windows::Compat::Appraiser::AuxJsonOutputter::DoOutput`
- `0x1800fb2ba`: `Windows::Compat::Appraiser::AuxJsonOutputter::DoOutput`
- `0x1800fb30b`: `Windows::Compat::Appraiser::AuxJsonOutputter::DoOutput`
- `0x1800fb35c`: `Windows::Compat::Appraiser::AuxJsonOutputter::DoOutput`
- `0x1800fb417`: `Windows::Compat::Appraiser::AuxJsonOutputter::DoOutput`
- `0x1800fb494`: `Windows::Compat::Appraiser::AuxJsonOutputter::DoOutput`
- `0x1800fb4ce`: `Windows::Compat::Appraiser::AuxJsonOutputter::DoOutput`
- `0x1800fb568`: `Windows::Compat::Appraiser::AuxJsonOutputter::DoOutput`
- `0x1800fb76b`: `Windows::Compat::Appraiser::AuxJsonOutputter::DoOutput`
- `0x1800fb7a4`: `Windows::Compat::Appraiser::AuxJsonOutputter::DoOutput`
- `0x1800fb484`: `Failed to Write AuxJson Compat Report: [0x%x].`
- `0x1800fb561`: `Failed to Write AuxJson Compat Report: [0x%x].`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Compat::Appraiser::AuxJsonOutputter::DoOutput(
        Windows::Compat::Appraiser::AuxJsonOutputter *a1,
        unsigned __int64 *a2,
        __int64 *a3)
{
  volatile signed __int64 *v6; // rcx
  unsigned __int64 v7; // r15
  void **v8; // rdx
  __int64 v9; // rbx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rdi
  Windows::Compat::Appraiser::TableCache *v13; // r14
  char ComponentStatus; // al
  __int64 v15; // rcx
  int SortedBucketArray; // eax
  int v17; // ebx
  unsigned __int64 v18; // rsi
  struct Windows::Compat::Appraiser::AuxBucket *v19; // rax
  __int64 *v20; // rax
  __int64 v21; // rbx
  struct Windows::Compat::Appraiser::AuxBucket *v22; // rax
  __int64 v23; // rcx
  int v24; // eax
  const char *v25; // rax
  char v26; // dl
  unsigned __int64 i; // rbx
  volatile signed __int64 *v28; // rcx
  void **v29; // rdx
  __int64 v30; // rdi
  char *v31; // rax
  _DWORD **v32; // rax
  __int64 v33; // r8
  __int64 v34; // r9
  char *v35; // rax
  int v36; // r8d
  _DWORD **v37; // rax
  __int64 v38; // rcx
  unsigned __int64 j; // rsi
  struct Windows::Compat::Appraiser::AuxBucket **v40; // rax
  volatile signed __int64 *v41; // rcx
  void **v42; // rdx
  __int64 v43; // rdi
  __int64 v44; // r8
  __int64 v45; // r9
  char *v47; // [rsp+28h] [rbp-E0h]
  char *v48; // [rsp+38h] [rbp-D0h]
  __int64 v49; // [rsp+40h] [rbp-C8h]
  struct Windows::Compat::Appraiser::AuxBucket *v50; // [rsp+58h] [rbp-B0h] BYREF
  struct Windows::Compat::Appraiser::IPropertyListEnumerator *v51; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v52; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v53; // [rsp+70h] [rbp-98h] BYREF
  __int64 hHeap; // [rsp+78h] [rbp-90h] BYREF
  HANDLE hHeap_8[2]; // [rsp+80h] [rbp-88h] BYREF
  __int128 v56; // [rsp+90h] [rbp-78h]
  LPVOID lpMem[2]; // [rsp+A0h] [rbp-68h]
  struct _SYSTEMTIME *v58; // [rsp+B0h] [rbp-58h] BYREF
  char v59[8]; // [rsp+B8h] [rbp-50h] BYREF
  char *v60; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v61; // [rsp+C8h] [rbp-40h] BYREF
  const size_t *v62; // [rsp+D0h] [rbp-38h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+D8h] [rbp-30h] BYREF
  void **v64; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v65; // [rsp+F0h] [rbp-18h]
  __int64 v66; // [rsp+F8h] [rbp-10h]
  __int64 v67; // [rsp+100h] [rbp-8h]
  struct _SYSTEMTIME v68; // [rsp+108h] [rbp+0h] BYREF
  struct _SYSTEMTIME v69; // [rsp+118h] [rbp+10h] BYREF
  char v70[144]; // [rsp+128h] [rbp+20h] BYREF
  char v71[144]; // [rsp+1B8h] [rbp+B0h] BYREF

  v67 = -2;
  TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v70);
  v6 = (volatile signed __int64 *)v70;
  v7 = 0;
  if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
    v6 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v6,
    _InterlockedExchangeAdd64(v6 + 17, 0),
    v71);
  if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
    UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v8);
  v9 = qword_1802C9628;
  if ( *(_DWORD *)qword_1802C9628 > 5u
    && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000020LL) != 0
    && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000020LL) == *(_QWORD *)(qword_1802C9628 + 24) )
  {
    v60 = v71;
    *(_QWORD *)v59 = 0x1000000;
    v61 = (__int64)&szValueBuf;
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    v68 = SystemTime;
    v58 = &v68;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
      v9,
      (__int64)&dword_1802A4CEC,
      v10,
      v11,
      (__int64 *)&v58,
      (const size_t **)&v61,
      (__int64)v59,
      (const char **)&v60);
  }
  v64 = &Windows::Compat::Appraiser::MetadataPropertyEnumerator::`vftable';
  v65 = 0;
  v66 = 0;
  hHeap_8[0] = GetProcessHeap();
  lpMem[0] = (LPVOID)16;
  v56 = 0;
  lpMem[1] = 0;
  hHeap_8[1] = (HANDLE)8;
  *(_QWORD *)&SystemTime.wYear = 0;
  v12 = 0;
  hHeap = 0;
  v53 = 0;
  v52 = 0;
  v51 = 0;
  v13 = 0;
  v66 = *a3;
  HIDWORD(v65) = *((_DWORD *)a3 + 16);
  ((void (__fastcall *)(void ***))v64[1])(&v64);
  hHeap_8[0] = GetProcessHeap();
  lpMem[0] = (LPVOID)16;
  v56 = 0;
  lpMem[1] = 0;
  hHeap_8[1] = (HANDLE)8;
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xC2u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
      "Windows::Compat::Appraiser::AuxJsonOutputter::DoOutput",
      "Failed to initialize RtlArray: [0x%x].",
      0);
  ComponentStatus = Windows::Compat::Appraiser::ComponentStatusQuery::GetComponentStatus(
                      (Windows::Compat::Appraiser::ComponentStatusQuery *)a3[7],
                      L"DatasourceWuDriver");
  v15 = ComponentStatus & 5;
  if ( (_BYTE)v15 == 5 || (ComponentStatus & 3) != 3 )
  {
    v17 = 1;
    if ( Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors() )
    {
      LODWORD(v47) = 1;
      v38 = 1;
    }
    else
    {
      v47 = 0;
      v38 = 0;
    }
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)v38,
      203,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
      "Windows::Compat::Appraiser::AuxJsonOutputter::DoOutput",
      v47,
      (int)"Not running outputter in offline mode.",
      v48);
  }
  else
  {
    SortedBucketArray = Windows::Compat::Appraiser::AuxJsonOutputter::CreateSortedBucketArray(
                          v15,
                          hHeap_8,
                          *((_QWORD *)a1 + 132));
    v17 = SortedBucketArray;
    if ( SortedBucketArray >= 0 )
    {
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xD4u,
          "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
          "Windows::Compat::Appraiser::AuxJsonOutputter::DoOutput",
          "Failed to create sorted AuxBucketArray: [0x%x].",
          SortedBucketArray);
      v18 = 0;
      if ( a2[2] )
      {
        while ( 1 )
        {
          if ( v13 )
          {
            Windows::Compat::Appraiser::TableCache::~TableCache(v13);
            operator delete(v13);
          }
          v19 = (struct Windows::Compat::Appraiser::AuxBucket *)operator new(
                                                                  0x60u,
                                                                  (const struct std::nothrow_t *)&std::nothrow);
          v50 = v19;
          if ( !v19 )
          {
            v13 = 0;
LABEL_69:
            v17 = -2147024882;
            goto LABEL_70;
          }
          v13 = Windows::Compat::Appraiser::TableCache::TableCache(v19);
          if ( !v13 )
            goto LABEL_69;
          v20 = 0;
          if ( v7 < a2[2] )
          {
            v50 = 0;
            if ( !is_mul_ok(a2[1], v7) || (v20 = (__int64 *)(a2[5] + a2[1] * v7), (unsigned __int64)v20 < a2[5]) )
              v20 = 0;
          }
          v21 = *v20;
          v22 = (struct Windows::Compat::Appraiser::AuxBucket *)operator new(
                                                                  0xE0u,
                                                                  (const struct std::nothrow_t *)&std::nothrow);
          v50 = v22;
          if ( !v22 )
            break;
          v12 = Windows::Compat::Appraiser::TargetVersionAssetReader::TargetVersionAssetReader(
                  (__int64)v22,
                  v21,
                  *((_QWORD *)a1 + 134),
                  14);
          if ( !v12 )
            goto LABEL_67;
          if ( v51 )
          {
            (*(void (__fastcall **)(struct Windows::Compat::Appraiser::IPropertyListEnumerator *))(*(_QWORD *)v51 + 32LL))(v51);
            v51 = 0;
          }
          if ( v52 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 32LL))(v52);
            v52 = 0;
          }
          if ( v53 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 32LL))(v53);
            v53 = 0;
          }
          if ( hHeap )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)hHeap + 32LL))(hHeap);
            hHeap = 0;
          }
          v17 = (**(__int64 (__fastcall ***)(__int64, struct Windows::Compat::Appraiser::IPropertyListEnumerator **, __int64))v12)(
                  v12,
                  &v51,
                  1);
          if ( v17 < 0 )
          {
            v25 = "Error getting enumerator: [0x%x].";
            v26 = -12;
            goto LABEL_61;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0xF4u,
              "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
              "Windows::Compat::Appraiser::AuxJsonOutputter::DoOutput",
              "Error getting enumerator: [0x%x].",
              v17);
          v17 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64))v12)(v12, &v52, 2);
          if ( v17 < 0 )
          {
            v25 = "Error getting enumerator: [0x%x].";
            v26 = -9;
            goto LABEL_61;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0xF7u,
              "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
              "Windows::Compat::Appraiser::AuxJsonOutputter::DoOutput",
              "Error getting enumerator: [0x%x].",
              v17);
          v17 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64))v12)(v12, &v53, 4);
          if ( v17 < 0 )
          {
            v25 = "Error getting enumerator: [0x%x].";
            v26 = -6;
            goto LABEL_61;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0xFAu,
              "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
              "Windows::Compat::Appraiser::AuxJsonOutputter::DoOutput",
              "Error getting enumerator: [0x%x].",
              v17);
          v17 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64))v12)(v12, &hHeap, 8);
          if ( v17 < 0 )
          {
            v25 = "Error getting enumerator: [0x%x].";
            v26 = -3;
LABEL_61:
            LODWORD(v48) = v17;
            LODWORD(v47) = v17;
            Windows::Compat::Appraiser::WriteLog(
              (Windows::Compat::Appraiser *)1,
              v26,
              (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
              "Windows::Compat::Appraiser::AuxJsonOutputter::DoOutput",
              v47,
              (int)v25,
              v48);
            goto LABEL_104;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0xFDu,
              "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
              "Windows::Compat::Appraiser::AuxJsonOutputter::DoOutput",
              "Error getting enumerator: [0x%x].",
              v17);
          v23 = *((_QWORD *)a1 + 132);
          if ( *(_QWORD *)(v23 + 16) )
          {
            while ( 1 )
            {
              if ( v18 < *(_QWORD *)(v23 + 16) )
              {
                v50 = 0;
                is_mul_ok(*(_QWORD *)(v23 + 8), v18);
              }
              v17 = Windows::Compat::Appraiser::AuxJsonOutputter::BucketizeAsset(
                      a1,
                      (struct Windows::Compat::Appraiser::IPropertyListEnumerator *)&v64,
                      v51,
                      v52,
                      v53,
                      hHeap,
                      (__int64)v13);
              if ( v17 < 0 )
                break;
              if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
                Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                  0x10Cu,
                  "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
                  "Windows::Compat::Appraiser::AuxJsonOutputter::DoOutput",
                  "Failed to bucketize Asset: [0x%x].",
                  v17);
              if ( v17 )
              {
                ++v18;
                v23 = *((_QWORD *)a1 + 132);
                if ( v18 < *(_QWORD *)(v23 + 16) )
                  continue;
              }
              v18 = 0;
              goto LABEL_57;
            }
            v25 = "Failed to bucketize Asset: [0x%x].";
            v26 = 12;
            goto LABEL_61;
          }
LABEL_57:
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 32LL))(v12);
          if ( ++v7 >= a2[2] )
            goto LABEL_58;
        }
        v12 = 0;
LABEL_67:
        v17 = -2147024882;
      }
      else
      {
LABEL_58:
        v24 = Windows::Compat::Appraiser::AuxJsonOutputter::WriteAuxJsonCompatReport(
                (__int64)a1,
                (unsigned __int64 *)hHeap_8);
        v17 = v24;
        if ( v24 >= 0 )
        {
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x121u,
              "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
              "Windows::Compat::Appraiser::AuxJsonOutputter::DoOutput",
              "Failed to Write AuxJson Compat Report: [0x%x].",
              v24);
          for ( i = 0; i < (unsigned __int64)v56; ++i )
          {
            TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v70);
            v28 = (volatile signed __int64 *)v70;
            if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
              v28 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
            TraceLoggingCorrelationVector::ToStringImpl(
              (TraceLoggingCorrelationVector *)v28,
              _InterlockedExchangeAdd64(v28 + 17, 0),
              v71);
            if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
              UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v29);
            v30 = qword_1802C9628;
            if ( *(_DWORD *)qword_1802C9628 > 5u
              && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000020LL) != 0
              && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000020LL) == *(_QWORD *)(qword_1802C9628 + 24) )
            {
              v58 = (struct _SYSTEMTIME *)v71;
              v61 = 0x1000000;
              v31 = 0;
              if ( i < (unsigned __int64)v56 )
              {
                v50 = 0;
                if ( !is_mul_ok((unsigned __int64)hHeap_8[1], i)
                  || (v31 = (char *)lpMem[1] + (unsigned __int64)hHeap_8[1] * i, v31 < lpMem[1]) )
                {
                  v31 = 0;
                }
              }
              *(_DWORD *)v59 = *(_DWORD *)(*(_QWORD *)v31 + 32LL);
              v32 = 0;
              if ( i < (unsigned __int64)v56 )
              {
                v50 = 0;
                if ( !is_mul_ok((unsigned __int64)hHeap_8[1], i)
                  || (v32 = (_DWORD **)((char *)lpMem[1] + (unsigned __int64)hHeap_8[1] * i), v32 < lpMem[1]) )
                {
                  v32 = 0;
                }
              }
              LODWORD(v60) = **v32;
              v62 = &szValueBuf;
              v68 = 0;
              GetSystemTime(&v68);
              v69 = v68;
              v50 = (struct Windows::Compat::Appraiser::AuxBucket *)&v69;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
                v30,
                (__int64)byte_1802A4C41,
                v33,
                v34,
                (__int64 *)&v50,
                &v62,
                (__int64)&v60,
                (__int64)v59,
                (__int64)&v61,
                (const char **)&v58);
            }
            v35 = 0;
            if ( i < (unsigned __int64)v56 )
            {
              v50 = 0;
              if ( !is_mul_ok((unsigned __int64)hHeap_8[1], i)
                || (v35 = (char *)lpMem[1] + (unsigned __int64)hHeap_8[1] * i, v35 < lpMem[1]) )
              {
                v35 = 0;
              }
            }
            v36 = *(_DWORD *)(*(_QWORD *)v35 + 32LL);
            v37 = 0;
            if ( i < (unsigned __int64)v56 )
            {
              v50 = 0;
              if ( !is_mul_ok((unsigned __int64)hHeap_8[1], i)
                || (v37 = (_DWORD **)((char *)lpMem[1] + (unsigned __int64)hHeap_8[1] * i), v37 < lpMem[1]) )
              {
                v37 = 0;
              }
            }
            LODWORD(v49) = v36;
            LODWORD(v48) = **v37;
            Windows::Compat::Appraiser::WriteLog(
              0,
              41,
              (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
              "Windows::Compat::Appraiser::AuxJsonOutputter::DoOutput",
              0,
              (int)"Bucket %d contains %d Assets.",
              v48,
              v49);
          }
          v17 = 0;
          v12 = 0;
        }
        else
        {
          LODWORD(v48) = v24;
          LODWORD(v47) = v24;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            33,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
            "Windows::Compat::Appraiser::AuxJsonOutputter::DoOutput",
            v47,
            (int)"Failed to Write AuxJson Compat Report: [0x%x].",
            v48);
LABEL_70:
          v12 = 0;
        }
      }
    }
    else
    {
      LODWORD(v48) = SortedBucketArray;
      LODWORD(v47) = SortedBucketArray;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        212,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
        "Windows::Compat::Appraiser::AuxJsonOutputter::DoOutput",
        v47,
        (int)"Failed to create sorted AuxBucketArray: [0x%x].",
        v48);
    }
  }
LABEL_104:
  for ( j = 0; j < (unsigned __int64)v56; ++j )
  {
    v40 = 0;
    if ( j < (unsigned __int64)v56 )
    {
      v50 = 0;
      if ( !is_mul_ok((unsigned __int64)hHeap_8[1], j)
        || (v40 = (struct Windows::Compat::Appraiser::AuxBucket **)((char *)lpMem[1] + (unsigned __int64)hHeap_8[1] * j),
            v40 < lpMem[1]) )
      {
        v40 = 0;
      }
    }
    v50 = *v40;
    Windows::Compat::Appraiser::AuxJsonOutputter::CleanupAuxBucket(&v50);
  }
  if ( v13 )
  {
    Windows::Compat::Appraiser::TableCache::~TableCache(v13);
    operator delete(v13);
  }
  if ( v51 )
  {
    (*(void (__fastcall **)(struct Windows::Compat::Appraiser::IPropertyListEnumerator *))(*(_QWORD *)v51 + 32LL))(v51);
    v51 = 0;
  }
  if ( v52 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 32LL))(v52);
    v52 = 0;
  }
  if ( v53 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 32LL))(v53);
    v53 = 0;
  }
  if ( hHeap )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)hHeap + 32LL))(hHeap);
    hHeap = 0;
  }
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 32LL))(v12);
  if ( lpMem[1] )
    HeapFree(hHeap_8[0], 0, lpMem[1]);
  *(_OWORD *)hHeap_8 = 0;
  v56 = 0;
  *(_OWORD *)lpMem = 0;
  Windows::Compat::Appraiser::AuxJsonOutputter::CleanupAuxAsset((struct Windows::Compat::Appraiser::AuxAsset **)&SystemTime);
  TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v70);
  v41 = (volatile signed __int64 *)v70;
  if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
    v41 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v41,
    _InterlockedExchangeAdd64(v41 + 17, 0),
    v71);
  if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
    UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v42);
  v43 = qword_1802C9628;
  if ( *(_DWORD *)qword_1802C9628 > 5u
    && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000020LL) != 0
    && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000020LL) == *(_QWORD *)(qword_1802C9628 + 24) )
  {
    *(_QWORD *)&SystemTime.wYear = v71;
    v50 = (struct Windows::Compat::Appraiser::AuxBucket *)0x1000000;
    v62 = &szValueBuf;
    v68 = 0;
    GetSystemTime(&v68);
    v69 = v68;
    v58 = &v69;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
      v43,
      (__int64)&byte_1802A4C9F,
      v44,
      v45,
      (__int64 *)&v58,
      &v62,
      (__int64)&v50,
      (const char **)&SystemTime);
  }
  if ( lpMem[1] )
    HeapFree(hHeap_8[0], 0, lpMem[1]);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1800fae10  mov     rax, rsp
0x1800fae13  push    rbp
0x1800fae14  push    rsi
0x1800fae15  push    rdi
0x1800fae16  push    r12
0x1800fae18  push    r13
0x1800fae1a  push    r14
0x1800fae1c  push    r15
0x1800fae1e  lea     rbp, [rax-188h]
0x1800fae25  sub     rsp, 250h
0x1800fae2c  mov     [rbp+180h+var_188], 0FFFFFFFFFFFFFFFEh
0x1800fae34  mov     [rax+20h], rbx
0x1800fae38  mov     rax, cs:__security_cookie
0x1800fae3f  xor     rax, rsp
0x1800fae42  mov     [rbp+180h+var_40], rax
0x1800fae49  mov     rsi, r8
0x1800fae4c  mov     r12, rdx
0x1800fae4f  mov     r13, rcx
0x1800fae52  lea     rcx, [rbp+180h+var_160]; this
0x1800fae56  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1800fae5b  lea     rcx, [rbp+180h+var_160]
0x1800fae5f  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x1800fae66  xor     r15d, r15d
0x1800fae69  test    rax, rax
0x1800fae6c  cmovnz  rcx, rax; this
0x1800fae70  mov     edx, r15d
0x1800fae73  lock xadd [rcx+88h], rdx; unsigned __int64
0x1800fae7c  lea     r8, [rbp+180h+var_D0]; char *
0x1800fae83  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1800fae88  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, r15b; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x1800fae8f  jz      short loc_1800FAE9D
0x1800fae91  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x1800fae98  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x1800fae9d  mov     rbx, cs:qword_1802C9628
0x1800faea4  mov     eax, [rbx]
0x1800faea6  mov     rdx, 200000000020h
0x1800faeb0  lea     r8, szValueBuf
0x1800faeb7  cmp     eax, 5
0x1800faeba  jbe     loc_1800FAF44
0x1800faec0  mov     rcx, [rbx+18h]
0x1800faec4  mov     rax, [rbx+10h]
0x1800faec8  test    rdx, rax
0x1800faecb  jz      short loc_1800FAF44
0x1800faecd  mov     rax, rcx
0x1800faed0  and     rax, rdx
0x1800faed3  cmp     rax, rcx
0x1800faed6  jnz     short loc_1800FAF44
0x1800faed8  lea     rax, [rbp+180h+var_D0]
0x1800faedf  mov     [rbp+180h+var_1C8], rax
0x1800faee3  mov     qword ptr [rbp+180h+var_1D0], 1000000h
0x1800faeeb  mov     [rbp+180h+var_1C0], r8
0x1800faeef  xorps   xmm0, xmm0
0x1800faef2  movups  xmmword ptr [rbp+180h+SystemTime.wYear], xmm0
0x1800faef6  lea     rcx, [rbp+180h+SystemTime]; lpSystemTime
0x1800faefa  call    cs:__imp_GetSystemTime
0x1800faf00  movaps  xmm0, xmmword ptr [rbp+180h+SystemTime.wYear]
0x1800faf04  movdqa  xmmword ptr [rbp+180h+var_180.wYear], xmm0
0x1800faf09  lea     rax, [rbp+180h+var_180]
0x1800faf0d  mov     [rbp+180h+var_1D8], rax
0x1800faf11  lea     rax, [rbp+180h+var_1C8]
0x1800faf15  mov     [rsp+280h+var_248], rax
0x1800faf1a  lea     rax, [rbp+180h+var_1D0]
0x1800faf1e  mov     [rsp+280h+var_250], rax; char *
0x1800faf23  lea     rax, [rbp+180h+var_1C0]
0x1800faf27  mov     qword ptr [rsp+280h+var_258], rax
0x1800faf2c  lea     rax, [rbp+180h+var_1D8]
0x1800faf30  mov     [rsp+280h+var_260], rax
0x1800faf35  lea     rdx, dword_1802A4CEC
0x1800faf3c  mov     rcx, rbx
0x1800faf3f  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x1800faf44  lea     rax, ??_7MetadataPropertyEnumerator@Appraiser@Compat@Windows@@6B@; const Windows::Compat::Appraiser::MetadataPropertyEnumerator::`vftable'
0x1800faf4b  mov     [rbp+180h+var_1A0], rax
0x1800faf4f  mov     [rbp+180h+var_198], r15
0x1800faf53  mov     [rbp+180h+var_190], r15
0x1800faf57  mov     [rsp+280h+var_228], r15
0x1800faf5c  mov     [rsp+280h+var_220], r15
0x1800faf61  mov     [rsp+280h+var_218], r15
0x1800faf66  mov     [rsp+280h+hHeap], r15
0x1800faf6b  xorps   xmm0, xmm0
0x1800faf6e  movups  xmmword ptr [rsp+280h+hHeap+8], xmm0
0x1800faf73  movups  [rbp+180h+var_1F8], xmm0
0x1800faf77  movups  xmmword ptr [rbp+180h+lpMem], xmm0
0x1800faf7b  call    cs:__imp_GetProcessHeap
0x1800faf81  mov     [rsp+280h+hHeap+8], rax
0x1800faf86  mov     ebx, 10h
0x1800faf8b  mov     [rbp+180h+lpMem], rbx
0x1800faf8f  xorps   xmm0, xmm0
0x1800faf92  movdqu  [rbp+180h+var_1F8], xmm0
0x1800faf97  mov     [rbp+180h+lpMem+8], r15
0x1800faf9b  mov     [rbp+180h+var_200], 8
0x1800fafa3  mov     qword ptr [rbp+180h+SystemTime.wYear], r15
0x1800fafa7  mov     rdi, r15
0x1800fafaa  mov     [rsp+280h+hHeap], r15
0x1800fafaf  mov     [rsp+280h+var_218], r15
0x1800fafb4  mov     [rsp+280h+var_220], r15
0x1800fafb9  mov     [rsp+280h+var_228], r15
0x1800fafbe  mov     r14, r15
0x1800fafc1  mov     rax, [rsi]
0x1800fafc4  mov     [rbp+180h+var_190], rax
0x1800fafc8  mov     eax, [rsi+40h]
0x1800fafcb  mov     dword ptr [rbp+180h+var_198+4], eax
0x1800fafce  mov     rax, [rbp+180h+var_1A0]
0x1800fafd2  lea     rcx, [rbp+180h+var_1A0]
0x1800fafd6  mov     rax, [rax+8]
0x1800fafda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fafdf  mov     r8, [rbp+180h+lpMem+8]; lpMem
0x1800fafe3  test    r8, r8
0x1800fafe6  jz      short loc_1800FAFF5
0x1800fafe8  xor     edx, edx; dwFlags
0x1800fafea  mov     rcx, [rsp+280h+hHeap+8]; hHeap
0x1800fafef  call    cs:__imp_HeapFree
0x1800faff5  xorps   xmm0, xmm0
0x1800faff8  movups  xmmword ptr [rsp+280h+hHeap+8], xmm0
0x1800faffd  movups  [rbp+180h+var_1F8], xmm0
0x1800fb001  movups  xmmword ptr [rbp+180h+lpMem], xmm0
0x1800fb005  call    cs:__imp_GetProcessHeap
0x1800fb00b  mov     [rsp+280h+hHeap+8], rax
0x1800fb010  mov     [rbp+180h+lpMem], rbx
0x1800fb014  xorps   xmm0, xmm0
0x1800fb017  movdqu  [rbp+180h+var_1F8], xmm0
0x1800fb01c  mov     [rbp+180h+lpMem+8], r15
0x1800fb020  mov     [rbp+180h+var_200], 8
0x1800fb028  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800fb02e  test    al, 1
0x1800fb030  jz      short loc_1800FB056
0x1800fb032  mov     dword ptr [rsp+280h+var_260], r15d
0x1800fb037  lea     r9, aFailedToInitia_32; "Failed to initialize RtlArray: [0x%x]."
0x1800fb03e  lea     r8, aWindowsCompatA_639; "Windows::Compat::Appraiser::AuxJsonOutp"...
0x1800fb045  lea     rdx, aOnecoreBaseApp_62; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800fb04c  mov     ecx, 0C2h; unsigned int
0x1800fb051  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800fb056  lea     rdx, aDatasourcewudr; "DatasourceWuDriver"
0x1800fb05d  mov     rcx, [rsi+38h]; this
0x1800fb061  call    ?GetComponentStatus@ComponentStatusQuery@Appraiser@Compat@Windows@@QEBA?AW4ComponentStatus@234@PEBG@Z; Windows::Compat::Appraiser::ComponentStatusQuery::GetComponentStatus(ushort const *)
0x1800fb066  mov     ecx, eax
0x1800fb068  and     ecx, 5
0x1800fb06b  cmp     cl, 5
0x1800fb06e  jz      loc_1800FB79A
0x1800fb074  and     eax, 3
0x1800fb077  cmp     al, 3
0x1800fb079  jnz     loc_1800FB79A
0x1800fb07f  mov     r8, [r13+420h]
0x1800fb086  lea     rdx, [rsp+280h+hHeap+8]
0x1800fb08b  call    ?CreateSortedBucketArray@AuxJsonOutputter@Appraiser@Compat@Windows@@AEAAJPEAV?$RtlArray@PEAUAuxBucket@Appraiser@Compat@Windows@@@@PEBV?$RtlArray@PEAVTable@Appraiser@Compat@Windows@@@@@Z; Windows::Compat::Appraiser::AuxJsonOutputter::CreateSortedBucketArray(RtlArray<Windows::Compat::Appraiser::AuxBucket *> *,RtlArray<Windows::Compat::Appraiser::Table *> const *)
0x1800fb090  mov     ebx, eax
0x1800fb092  test    eax, eax
0x1800fb094  jns     short loc_1800FB0CC
0x1800fb096  mov     dword ptr [rsp+280h+var_250], eax; char *
0x1800fb09a  lea     r9, aFailedToCreate_46; "Failed to create sorted AuxBucketArray:"...
0x1800fb0a1  mov     qword ptr [rsp+280h+var_258], r9; int
0x1800fb0a6  mov     dword ptr [rsp+280h+var_260], eax; char *
0x1800fb0aa  lea     r9, aWindowsCompatA_639; "Windows::Compat::Appraiser::AuxJsonOutp"...
0x1800fb0b1  lea     r8, aOnecoreBaseApp_62; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800fb0b8  mov     edx, 0D4h; bool
0x1800fb0bd  mov     ecx, 1; this
0x1800fb0c2  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800fb0c7  jmp     loc_1800FB7DB
0x1800fb0cc  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800fb0d2  test    al, 1
0x1800fb0d4  jz      short loc_1800FB0F9
0x1800fb0d6  mov     dword ptr [rsp+280h+var_260], ebx
0x1800fb0da  lea     r9, aFailedToCreate_46; "Failed to create sorted AuxBucketArray:"...
0x1800fb0e1  lea     r8, aWindowsCompatA_639; "Windows::Compat::Appraiser::AuxJsonOutp"...
0x1800fb0e8  lea     rdx, aOnecoreBaseApp_62; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800fb0ef  mov     ecx, 0D4h; unsigned int
0x1800fb0f4  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800fb0f9  xor     esi, esi
0x1800fb0fb  cmp     [r12+10h], rsi
0x1800fb100  jbe     loc_1800FB466
0x1800fb106  test    r14, r14
0x1800fb109  jz      short loc_1800FB120
0x1800fb10b  mov     rcx, r14; this
0x1800fb10e  call    ??1TableCache@Appraiser@Compat@Windows@@QEAA@XZ; Windows::Compat::Appraiser::TableCache::~TableCache(void)
0x1800fb113  mov     edx, 60h ; '`'
0x1800fb118  mov     rcx, r14; Block
0x1800fb11b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800fb120  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800fb127  mov     ecx, 60h ; '`'; unsigned __int64
0x1800fb12c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800fb131  mov     [rsp+280h+var_230], rax
0x1800fb136  test    rax, rax
0x1800fb139  jz      loc_1800FB53B
0x1800fb13f  mov     rcx, rax; this
0x1800fb142  call    ??0TableCache@Appraiser@Compat@Windows@@QEAA@XZ; Windows::Compat::Appraiser::TableCache::TableCache(void)
0x1800fb147  mov     r14, rax
0x1800fb14a  test    rax, rax
0x1800fb14d  jz      loc_1800FB543
0x1800fb153  mov     rax, rsi
0x1800fb156  cmp     r15, [r12+10h]
0x1800fb15b  jnb     short loc_1800FB17E
0x1800fb15d  mov     [rsp+280h+var_230], rsi
0x1800fb162  mov     rax, r15
0x1800fb165  mul     qword ptr [r12+8]
0x1800fb16a  test    rdx, rdx
0x1800fb16d  jnz     short loc_1800FB17B
0x1800fb16f  add     rax, [r12+28h]
0x1800fb174  cmp     rax, [r12+28h]
0x1800fb179  jnb     short loc_1800FB17E
0x1800fb17b  mov     rax, rsi
0x1800fb17e  mov     rbx, [rax]
0x1800fb181  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800fb188  mov     ecx, 0E0h; unsigned __int64
0x1800fb18d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800fb192  mov     [rsp+280h+var_230], rax
0x1800fb197  test    rax, rax
0x1800fb19a  jz      loc_1800FB526
0x1800fb1a0  mov     r9d, 0Eh
0x1800fb1a6  mov     r8, [r13+430h]
0x1800fb1ad  mov     rdx, rbx
0x1800fb1b0  mov     rcx, rax
0x1800fb1b3  call    ??0TargetVersionAssetReader@Appraiser@Compat@Windows@@QEAA@PEAVIAsset@123@PEBGW4Tier@123@@Z; Windows::Compat::Appraiser::TargetVersionAssetReader::TargetVersionAssetReader(Windows::Compat::Appraiser::IAsset *,ushort const *,Windows::Compat::Appraiser::Tier)
0x1800fb1b8  mov     rdi, rax
0x1800fb1bb  test    rax, rax
0x1800fb1be  jz      loc_1800FB52E
0x1800fb1c4  mov     rcx, [rsp+280h+var_228]
0x1800fb1c9  test    rcx, rcx
0x1800fb1cc  jz      short loc_1800FB1DF
0x1800fb1ce  mov     rax, [rcx]
0x1800fb1d1  mov     rax, [rax+20h]
0x1800fb1d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb1da  mov     [rsp+280h+var_228], rsi
0x1800fb1df  mov     rcx, [rsp+280h+var_220]
0x1800fb1e4  test    rcx, rcx
0x1800fb1e7  jz      short loc_1800FB1FA
0x1800fb1e9  mov     rax, [rcx]
0x1800fb1ec  mov     rax, [rax+20h]
0x1800fb1f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb1f5  mov     [rsp+280h+var_220], rsi
0x1800fb1fa  mov     rcx, [rsp+280h+var_218]
0x1800fb1ff  test    rcx, rcx
0x1800fb202  jz      short loc_1800FB215
0x1800fb204  mov     rax, [rcx]
0x1800fb207  mov     rax, [rax+20h]
0x1800fb20b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb210  mov     [rsp+280h+var_218], rsi
0x1800fb215  mov     rcx, [rsp+280h+hHeap]
0x1800fb21a  test    rcx, rcx
0x1800fb21d  jz      short loc_1800FB230
0x1800fb21f  mov     rax, [rcx]
0x1800fb222  mov     rax, [rax+20h]
0x1800fb226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb22b  mov     [rsp+280h+hHeap], rsi
0x1800fb230  mov     rax, [rdi]
0x1800fb233  xor     r9d, r9d
0x1800fb236  lea     r8d, [r9+1]
0x1800fb23a  lea     rdx, [rsp+280h+var_228]
0x1800fb23f  mov     rcx, rdi
0x1800fb242  mov     rax, [rax]
0x1800fb245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb24a  mov     ebx, eax
0x1800fb24c  test    eax, eax
0x1800fb24e  js      loc_1800FB518
0x1800fb254  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800fb25a  test    al, 1
0x1800fb25c  jz      short loc_1800FB281
0x1800fb25e  mov     dword ptr [rsp+280h+var_260], ebx
0x1800fb262  lea     r9, aErrorGettingEn_1; "Error getting enumerator: [0x%x]."
0x1800fb269  lea     r8, aWindowsCompatA_639; "Windows::Compat::Appraiser::AuxJsonOutp"...
0x1800fb270  lea     rdx, aOnecoreBaseApp_62; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800fb277  mov     ecx, 0F4h; unsigned int
0x1800fb27c  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800fb281  mov     rax, [rdi]
0x1800fb284  xor     r9d, r9d
0x1800fb287  lea     r8d, [r9+2]
0x1800fb28b  lea     rdx, [rsp+280h+var_220]
0x1800fb290  mov     rcx, rdi
0x1800fb293  mov     rax, [rax]
0x1800fb296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb29b  mov     ebx, eax
0x1800fb29d  test    eax, eax
0x1800fb29f  js      loc_1800FB50A
0x1800fb2a5  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800fb2ab  test    al, 1
0x1800fb2ad  jz      short loc_1800FB2D2
0x1800fb2af  mov     dword ptr [rsp+280h+var_260], ebx
0x1800fb2b3  lea     r9, aErrorGettingEn_1; "Error getting enumerator: [0x%x]."
0x1800fb2ba  lea     r8, aWindowsCompatA_639; "Windows::Compat::Appraiser::AuxJsonOutp"...
0x1800fb2c1  lea     rdx, aOnecoreBaseApp_62; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800fb2c8  mov     ecx, 0F7h; unsigned int
0x1800fb2cd  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800fb2d2  mov     rax, [rdi]
0x1800fb2d5  xor     r9d, r9d
0x1800fb2d8  lea     r8d, [r9+4]
0x1800fb2dc  lea     rdx, [rsp+280h+var_218]
0x1800fb2e1  mov     rcx, rdi
0x1800fb2e4  mov     rax, [rax]
0x1800fb2e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb2ec  mov     ebx, eax
0x1800fb2ee  test    eax, eax
0x1800fb2f0  js      loc_1800FB4FC
0x1800fb2f6  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800fb2fc  test    al, 1
0x1800fb2fe  jz      short loc_1800FB323
0x1800fb300  mov     dword ptr [rsp+280h+var_260], ebx
0x1800fb304  lea     r9, aErrorGettingEn_1; "Error getting enumerator: [0x%x]."
0x1800fb30b  lea     r8, aWindowsCompatA_639; "Windows::Compat::Appraiser::AuxJsonOutp"...
0x1800fb312  lea     rdx, aOnecoreBaseApp_62; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800fb319  mov     ecx, 0FAh; unsigned int
0x1800fb31e  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800fb323  mov     rax, [rdi]
  ... truncated ...
```
