# Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput(RtlArray<Windows::Compat::Appraiser::IAsset *> *,Windows::Compat::Appraiser::WicaRun *)

- ea: `0x1800efba0`
- end: `0x1800f1207`
- name: `?DoOutput@SetupXmlOutputter@Appraiser@Compat@Windows@@UEAAJPEAV?$RtlArray@PEAVIAsset@Appraiser@Compat@Windows@@@@PEAUWicaRun@234@@Z`
- size: `5735`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x1800018a0`
- `0x180001f18`
- `0x180008570`
- `0x1800092dc`
- `0x180013c7c`
- `0x1800151f4`
- `0x180029258`
- `0x18002c360`
- `0x18002ebb8`
- `0x1800301d0`
- `0x180087ca8`
- `0x1800ef3fc`
- `0x1800ef848`
- `0x1800efba0`
- `0x1800f1ce8`
- `0x1800f2d44`
- `0x1800f337c`
- `0x18010f4a0`
- `0x1801108ac`
- `0x18011442c`
- `0x18021f010`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x1800efe17`
- `KERNEL32!GetSystemTime` at `0x1800f033b`
- `KERNEL32!GetSystemTime` at `0x1800f1068`
- `KERNEL32!GetSystemTime` at `0x1800efe17`
- `KERNEL32!GetSystemTime` at `0x1800f033b`
- `KERNEL32!GetSystemTime` at `0x1800f1068`
- `KERNEL32!GetProcessHeap` at `0x1800efbf4`
- `KERNEL32!GetProcessHeap` at `0x1800efc25`
- `KERNEL32!GetProcessHeap` at `0x1800efc4f`
- `KERNEL32!GetProcessHeap` at `0x1800efc79`
- `KERNEL32!GetProcessHeap` at `0x1800efca8`
- `KERNEL32!GetProcessHeap` at `0x1800efce3`
- `KERNEL32!GetProcessHeap` at `0x1800efe8e`
- `KERNEL32!GetProcessHeap` at `0x1800efeec`
- `KERNEL32!GetProcessHeap` at `0x1800eff63`
- `KERNEL32!GetProcessHeap` at `0x1800f0e31`
- `KERNEL32!GetProcessHeap` at `0x1800f10c1`
- `KERNEL32!GetProcessHeap` at `0x1800efbf4`
- `KERNEL32!GetProcessHeap` at `0x1800efc25`
- `KERNEL32!GetProcessHeap` at `0x1800efc4f`
- `KERNEL32!GetProcessHeap` at `0x1800efc79`
- `KERNEL32!GetProcessHeap` at `0x1800efca8`
- `KERNEL32!GetProcessHeap` at `0x1800efce3`
- `KERNEL32!GetProcessHeap` at `0x1800efe8e`
- `KERNEL32!GetProcessHeap` at `0x1800efeec`
- `KERNEL32!GetProcessHeap` at `0x1800eff63`
- `KERNEL32!GetProcessHeap` at `0x1800f0e31`
- `KERNEL32!GetProcessHeap` at `0x1800f10c1`
- `KERNEL32!HeapAlloc` at `0x1800f0e3f`
- `KERNEL32!HeapAlloc` at `0x1800f0e3f`
- `KERNEL32!HeapFree` at `0x1800efe79`
- `KERNEL32!HeapFree` at `0x1800eff4e`
- `KERNEL32!HeapFree` at `0x1800f10cf`
- `KERNEL32!HeapFree` at `0x1800f1142`
- `KERNEL32!HeapFree` at `0x1800f115e`
- `KERNEL32!HeapFree` at `0x1800f1177`
- `KERNEL32!HeapFree` at `0x1800f119b`
- `KERNEL32!HeapFree` at `0x1800f11bf`
- `KERNEL32!HeapFree` at `0x1800f11d5`
- `KERNEL32!HeapFree` at `0x1800efe79`
- `KERNEL32!HeapFree` at `0x1800eff4e`
- `KERNEL32!HeapFree` at `0x1800f10cf`
- `KERNEL32!HeapFree` at `0x1800f1142`
- `KERNEL32!HeapFree` at `0x1800f115e`
- `KERNEL32!HeapFree` at `0x1800f1177`
- `KERNEL32!HeapFree` at `0x1800f119b`
- `KERNEL32!HeapFree` at `0x1800f11bf`
- `KERNEL32!HeapFree` at `0x1800f11d5`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x1800f040f`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x1800f040f`
- `SHLWAPI!PathFindFileNameW` at `0x1800f06b4`
- `SHLWAPI!PathFindFileNameW` at `0x1800f06b4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f0f35`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f0f35`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f10d8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f10d8`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x1800f04a1`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x1800f04a1`
- `XmlLite!CreateXmlWriter` at `0x1800f03a8`
- `XmlLite!CreateXmlWriter` at `0x1800f03a8`

## string_xrefs

- `0x1800f03b4`: `Could not create Xml Writer: [0x%x].`
- `0x1800f03d3`: `Could not create Xml Writer: [0x%x].`
- `0x1800f0428`: `SHCreateStreamOnFileEx Failed for %ls [0x%x].`
- `0x1800f0471`: `SHCreateStreamOnFileEx Failed for %ls [0x%x].`
- `0x1800f05bd`: `Failed to write start of XML document: [0x%x].`
- `0x1800f05dc`: `Failed to write start of XML document: [0x%x].`
- `0x1800f0621`: `Could not write root element: [0x%x].`
- `0x1800f0640`: `Could not write root element: [0x%x].`
- `0x1800f0cb5`: `Write end element failed: [0x%x].`
- `0x1800f0ce1`: `Write end element failed: [0x%x].`
- `0x1800f0d13`: `Write end document failed: [0x%x].`
- `0x1800f0d3f`: `Write end document failed: [0x%x].`
- `0x1800f04ad`: `Failed to set utf-16 encoding for xml writer: [0x%x].`
- `0x1800f04cc`: `Failed to set utf-16 encoding for xml writer: [0x%x].`
- `0x1800efed0`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800eff2e`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800effa5`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800effea`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800f0020`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800f006f`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800f00c1`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800f015f`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800f01d8`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800f0226`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800f0266`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800f03e1`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800f043f`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800f047f`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800f04da`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800f0533`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800f0590`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800f05ea`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800f064e`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800f068d`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800f0709`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800f075a`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800f07fe`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800f0896`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800f08f4`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800f095e`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800f098d`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800f0a05`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800f0a61`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800f0af5`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800f0b70`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800f0be8`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800f0c64`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800f0c93`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x1800efec9`: `Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput`
- `0x1800eff27`: `Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput`
- `0x1800eff9e`: `Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput`
- `0x1800effe3`: `Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput`
- `0x1800f0019`: `Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput`
- `0x1800f0068`: `Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput`
- `0x1800f00ba`: `Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput`
- `0x1800f0158`: `Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput`
- `0x1800f01d1`: `Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput`
- `0x1800f022d`: `Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput`
- `0x1800f025f`: `Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput`
- `0x1800f03da`: `Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput`
- `0x1800f0438`: `Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput`
- `0x1800f0478`: `Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput`
- `0x1800f04d3`: `Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput`
- `0x1800f052c`: `Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput`
- `0x1800f0589`: `Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput`
- `0x1800f05e3`: `Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput`
- `0x1800f0647`: `Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput`
- `0x1800f0686`: `Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput`
- `0x1800f0702`: `Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput`
- `0x1800f0753`: `Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput`
- `0x1800f07f7`: `Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput`
- `0x1800f088f`: `Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput`
- `0x1800f08ed`: `Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput`
- `0x1800f0957`: `Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput`
- `0x1800f0974`: `Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput`
- `0x1800f0adc`: `Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput`
- `0x1800f0c5d`: `Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput`
- `0x1800f0c8c`: `Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput`
- `0x1800f0606`: `CompatReport`
- `0x1800f0211`: `Failed to write mig xml file: [0x%x].`
- `0x1800f0258`: `Failed to write mig xml file: [0x%x].`
- `0x1800f06dc`: `Failed to write mig xml: [0x%x].`
- `0x1800f06fb`: `Failed to write mig xml: [0x%x].`
- `0x1800f06c2`: `MigXmlFile`
- `0x1800f0f64`: `Failed to send xml to setup head: [0x%x].`
- `0x1800f0f95`: `Failed to send xml to setup head: [0x%x].`
- `0x1800f0eed`: `Failed to copy stream: [0x%x].`
- `0x1800f0f0b`: `Failed to copy stream: [0x%x].`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput(__int64 a1, __int64 a2, __int64 *a3)
{
  unsigned __int8 v6; // di
  OLECHAR *v7; // r12
  OLECHAR *v8; // r15
  volatile signed __int64 *v9; // rcx
  void **v10; // rdx
  __int64 v11; // rbx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // rdx
  HRESULT XmlWriter; // ebx
  char v17; // dl
  __int64 v18; // rdx
  int v19; // eax
  int Categories; // eax
  bool v21; // r15
  const char *v22; // r9
  char v23; // dl
  volatile signed __int64 *v24; // rcx
  void **v25; // rdx
  __int64 v26; // rbx
  __int64 v27; // r8
  __int64 v28; // r9
  HRESULT v29; // eax
  const WCHAR *v30; // rcx
  void *v31; // rdi
  __int64 (__fastcall *v32)(void *, _QWORD, const wchar_t *, _QWORD, LPWSTR); // rbx
  LPWSTR FileNameW; // rax
  bool v34; // di
  bool v35; // r14
  int v36; // eax
  const char *v37; // r9
  int v38; // eax
  int appended; // eax
  int v40; // eax
  int v41; // eax
  int v42; // eax
  int v43; // eax
  int v44; // eax
  int v45; // eax
  unsigned int v46; // ebx
  HANDLE ProcessHeap; // rax
  const char *v48; // r9
  char v49; // dl
  BSTR v50; // rax
  int v51; // eax
  volatile signed __int64 *v52; // rcx
  void **v53; // rdx
  __int64 v54; // rdi
  __int64 v55; // r8
  __int64 v56; // r9
  HANDLE v57; // rax
  IStream *pstmTemplate; // [rsp+28h] [rbp-E0h]
  const char *ppstm; // [rsp+30h] [rbp-D8h]
  const char *ppstma; // [rsp+30h] [rbp-D8h]
  struct Windows::Compat::Appraiser::MapTable *v62; // [rsp+38h] [rbp-D0h]
  struct Windows::Compat::Appraiser::MapTable *v63; // [rsp+40h] [rbp-C8h]
  __int64 v64; // [rsp+58h] [rbp-B0h] BYREF
  OLECHAR *v65; // [rsp+60h] [rbp-A8h]
  bool v66[8]; // [rsp+68h] [rbp-A0h] BYREF
  void *SystemTime[3]; // [rsp+70h] [rbp-98h] BYREF
  IUnknown *pOutputStream; // [rsp+88h] [rbp-80h] BYREF
  __int64 v69; // [rsp+90h] [rbp-78h] BYREF
  __int64 v70; // [rsp+98h] [rbp-70h] BYREF
  __int64 v71; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v72; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v73; // [rsp+B0h] [rbp-58h]
  __int64 v74; // [rsp+B8h] [rbp-50h]
  HANDLE v75[2]; // [rsp+C0h] [rbp-48h] BYREF
  __int128 v76; // [rsp+D0h] [rbp-38h]
  LPVOID v77[2]; // [rsp+E0h] [rbp-28h]
  char v78[8]; // [rsp+F0h] [rbp-18h] BYREF
  IXmlWriterOutput *ppOutput; // [rsp+F8h] [rbp-10h] BYREF
  HANDLE hHeap[2]; // [rsp+100h] [rbp-8h] BYREF
  __int128 v81; // [rsp+110h] [rbp+8h]
  LPVOID lpMem[2]; // [rsp+120h] [rbp+18h]
  HANDLE v83[2]; // [rsp+130h] [rbp+28h] BYREF
  __int128 v84; // [rsp+140h] [rbp+38h]
  LPVOID v85[2]; // [rsp+150h] [rbp+48h]
  HANDLE v86[2]; // [rsp+160h] [rbp+58h] BYREF
  __int128 v87; // [rsp+170h] [rbp+68h]
  LPVOID v88[2]; // [rsp+180h] [rbp+78h]
  HANDLE v89[2]; // [rsp+190h] [rbp+88h] BYREF
  __int128 v90; // [rsp+1A0h] [rbp+98h]
  LPVOID v91[2]; // [rsp+1B0h] [rbp+A8h]
  HANDLE v92[2]; // [rsp+1C0h] [rbp+B8h] BYREF
  __int128 v93; // [rsp+1D0h] [rbp+C8h]
  LPVOID v94[2]; // [rsp+1E0h] [rbp+D8h]
  __int64 v95; // [rsp+1F0h] [rbp+E8h]
  _BYTE v96[16]; // [rsp+1F8h] [rbp+F0h] BYREF
  unsigned int v97; // [rsp+208h] [rbp+100h]
  struct _SYSTEMTIME v98; // [rsp+248h] [rbp+140h] BYREF
  struct _SYSTEMTIME v99; // [rsp+258h] [rbp+150h] BYREF
  char v100[144]; // [rsp+268h] [rbp+160h] BYREF
  char v101[144]; // [rsp+2F8h] [rbp+1F0h] BYREF

  v95 = -2;
  hHeap[0] = GetProcessHeap();
  v6 = 0;
  lpMem[0] = (LPVOID)16;
  v81 = 0;
  lpMem[1] = 0;
  hHeap[1] = (HANDLE)8;
  v83[0] = GetProcessHeap();
  v85[0] = (LPVOID)16;
  v84 = 0;
  v85[1] = 0;
  v83[1] = (HANDLE)8;
  v75[0] = GetProcessHeap();
  v77[0] = (LPVOID)16;
  v76 = 0;
  v77[1] = 0;
  v75[1] = (HANDLE)8;
  v86[0] = GetProcessHeap();
  v88[0] = (LPVOID)16;
  v87 = 0;
  v88[1] = 0;
  v86[1] = (HANDLE)8;
  v92[0] = GetProcessHeap();
  v94[0] = (LPVOID)16;
  v93 = 0;
  v94[1] = 0;
  v92[1] = (HANDLE)8;
  v89[0] = GetProcessHeap();
  v91[0] = (LPVOID)16;
  v90 = 0;
  v91[1] = 0;
  v89[1] = (HANDLE)8;
  v72 = (__int64)&Windows::Compat::Appraiser::MetadataPropertyEnumerator::`vftable';
  v73 = 0;
  v74 = 0;
  SystemTime[0] = 0;
  pOutputStream = 0;
  ppOutput = 0;
  memset_0(v96, 0, 0x50u);
  v66[1] = 0;
  v66[2] = 0;
  v66[0] = 0;
  v66[4] = 0;
  v66[3] = 0;
  v7 = 0;
  v8 = 0;
  v65 = 0;
  LOBYTE(v64) = 0;
  TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v100);
  v9 = (volatile signed __int64 *)v100;
  if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
    v9 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v9,
    _InterlockedExchangeAdd64(v9 + 17, 0),
    v101);
  if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
    UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v10);
  v11 = qword_1802C9628;
  if ( *(_DWORD *)qword_1802C9628 > 5u
    && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000020LL) != 0
    && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000020LL) == *(_QWORD *)(qword_1802C9628 + 24) )
  {
    *(_QWORD *)v78 = v101;
    v69 = 0x1000000;
    v70 = (__int64)&szValueBuf;
    *(_OWORD *)&SystemTime[1] = 0;
    GetSystemTime((LPSYSTEMTIME)&SystemTime[1]);
    v98 = *(struct _SYSTEMTIME *)&SystemTime[1];
    v71 = (__int64)&v98;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
      v11,
      (__int64)byte_1802A49CB,
      v12,
      v13,
      &v71,
      (const size_t **)&v70,
      (__int64)&v69,
      (const char **)v78);
  }
  if ( lpMem[1] )
    HeapFree(hHeap[0], 0, lpMem[1]);
  *(_OWORD *)hHeap = 0;
  v81 = 0;
  *(_OWORD *)lpMem = 0;
  hHeap[0] = GetProcessHeap();
  lpMem[0] = (LPVOID)16;
  v81 = 0;
  lpMem[1] = 0;
  hHeap[1] = (HANDLE)8;
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xFEu,
      "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
      "Failed to initialize RtlArray: [0x%x].",
      0);
  *(_OWORD *)v83 = 0;
  *(_OWORD *)v85 = 0;
  v83[0] = GetProcessHeap();
  v85[0] = (LPVOID)16;
  v84 = 0;
  v85[1] = 0;
  v83[1] = (HANDLE)8;
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xFFu,
      "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
      "Failed to initialize RtlArray: [0x%x].",
      0);
  if ( v77[1] )
    HeapFree(v75[0], 0, v77[1]);
  *(_OWORD *)v75 = 0;
  v76 = 0;
  *(_OWORD *)v77 = 0;
  v75[0] = GetProcessHeap();
  v77[0] = (LPVOID)16;
  v76 = 0;
  v77[1] = 0;
  v75[1] = (HANDLE)8;
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x100u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
      "Failed to initialize RtlArray: [0x%x].",
      0);
  XmlWriter = RtlArray<Windows::Compat::Appraiser::IAsset *>::Initialize(v86, v14, 0, 16);
  if ( XmlWriter < 0 )
  {
    v17 = 1;
LABEL_21:
    LODWORD(v62) = XmlWriter;
    ppstm = "Failed to initialize RtlArray: [0x%x].";
LABEL_22:
    LODWORD(pstmTemplate) = XmlWriter;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v17,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
      (const char *)pstmTemplate,
      (int)ppstm,
      (const char *)v62);
    goto LABEL_182;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x101u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
      "Failed to initialize RtlArray: [0x%x].",
      XmlWriter);
  XmlWriter = RtlArray<Windows::Compat::Appraiser::IAsset *>::Initialize(v92, v15, 0, 16);
  if ( XmlWriter < 0 )
  {
    v17 = 2;
    goto LABEL_21;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x102u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
      "Failed to initialize RtlArray: [0x%x].",
      XmlWriter);
  XmlWriter = RtlArray<Windows::Compat::Appraiser::IAsset *>::Initialize(v89, v18, 0, 16);
  if ( XmlWriter < 0 )
  {
    v17 = 3;
    goto LABEL_21;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x103u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
      "Failed to initialize RtlArray: [0x%x].",
      XmlWriter);
  v74 = *a3;
  HIDWORD(v73) = *((_DWORD *)a3 + 16);
  (*(void (__fastcall **)(__int64 *))(v72 + 8))(&v72);
  v19 = Windows::Compat::Appraiser::SetupXmlOutputter::BucketizeAssets(
          (unsigned int)hHeap,
          (unsigned int)v83,
          (unsigned int)v75,
          (unsigned int)v86,
          (__int64)v92,
          (__int64)v89,
          a2);
  XmlWriter = v19;
  if ( v19 < 0 )
  {
    LODWORD(v62) = v19;
    ppstm = "Failed to sort assets: [0x%x].";
    v17 = 7;
    goto LABEL_22;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x107u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
      "Failed to sort assets: [0x%x].",
      v19);
  Categories = Windows::Compat::Appraiser::Utilities::FindCategories(
                 &v66[1],
                 &v66[2],
                 v66,
                 &v66[4],
                 &v66[3],
                 (struct Windows::Compat::Appraiser::IPropertyListEnumerator *)&v72);
  XmlWriter = Categories;
  if ( Categories < 0 )
  {
    LODWORD(v62) = Categories;
    ppstm = "Failed to find categories: [0x%x].";
    v17 = 10;
    goto LABEL_22;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x10Au,
      "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
      "Failed to find categories: [0x%x].",
      Categories);
  LODWORD(v73) = 0;
  v21 = v66[0];
  if ( v66[0] )
  {
    XmlWriter = Windows::Compat::Appraiser::SetupXmlOutputter::WriteMigXmlFile(a1, &v64, a2);
    if ( XmlWriter < 0 )
    {
      v22 = "Failed to write mig xml file: [0x%x].";
      v23 = 16;
LABEL_44:
      LODWORD(v62) = XmlWriter;
      LODWORD(ppstma) = (_DWORD)v22;
LABEL_45:
      LODWORD(pstmTemplate) = XmlWriter;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        v23,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
        "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
        (const char *)pstmTemplate,
        (int)ppstma,
        (const char *)v62);
LABEL_46:
      v8 = 0;
      goto LABEL_182;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x110u,
        "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
        "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
        "Failed to write mig xml file: [0x%x].",
        XmlWriter);
    v6 = v64;
  }
  TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v100);
  v24 = (volatile signed __int64 *)v100;
  if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
    v24 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v24,
    _InterlockedExchangeAdd64(v24 + 17, 0),
    v101);
  if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
    UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v25);
  v26 = qword_1802C9628;
  if ( *(_DWORD *)qword_1802C9628 > 5u
    && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000020LL) != 0
    && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000020LL) == *(_QWORD *)(qword_1802C9628 + 24) )
  {
    v71 = (__int64)v101;
    v70 = 0x1000000;
    *(_DWORD *)v78 = v6;
    v69 = (__int64)&szValueBuf;
    v98 = 0;
    GetSystemTime(&v98);
    v99 = v98;
    SystemTime[1] = &v99;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
      v26,
      (__int64)byte_1802A4A1B,
      v27,
      v28,
      (__int64 *)&SystemTime[1],
      (const size_t **)&v69,
      (__int64)v78,
      (__int64)&v70,
      (const char **)&v71);
  }
  XmlWriter = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, SystemTime, 0);
  if ( XmlWriter < 0 )
  {
    v22 = "Could not create Xml Writer: [0x%x].";
    v23 = 26;
    goto LABEL_44;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x11Au,
      "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
      "Could not create Xml Writer: [0x%x].",
      XmlWriter);
  v29 = SHCreateStreamOnFileEx(*(LPCWSTR *)(a1 + 16), 0x1002u, 0, 0, 0, (IStream **)&pOutputStream);
  XmlWriter = v29;
  if ( v29 < 0 )
  {
    LODWORD(v63) = v29;
    LODWORD(pstmTemplate) = v29;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      29,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
      (const char *)pstmTemplate,
      (int)"SHCreateStreamOnFileEx Failed for %ls [0x%x].",
      *(const char **)(a1 + 16),
      v63);
    goto LABEL_46;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x11Du,
      "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
      "SHCreateStreamOnFileEx Failed for %ls [0x%x].",
      *(const wchar_t **)(a1 + 16),
      v29);
  XmlWriter = CreateXmlWriterOutputWithEncodingName(pOutputStream, 0, L"utf-16", &ppOutput);
  if ( XmlWriter < 0 )
  {
    v22 = "Failed to set utf-16 encoding for xml writer: [0x%x].";
    v23 = 32;
    goto LABEL_44;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x120u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
      "Failed to set utf-16 encoding for xml writer: [0x%x].",
      XmlWriter);
  XmlWriter = (*(__int64 (__fastcall **)(void *, IXmlWriterOutput *))(*(_QWORD *)SystemTime[0] + 24LL))(
                SystemTime[0],
                ppOutput);
  if ( XmlWriter < 0 )
  {
    v22 = "Failed to set output: [0x%x].";
    v23 = 35;
    goto LABEL_44;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x123u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
      "Failed to set output: [0x%x].",
      XmlWriter);
  XmlWriter = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)SystemTime[0] + 40LL))(
                SystemTime[0],
                1,
                1);
  if ( XmlWriter < 0 )
  {
    v22 = "Failed to set indent property: [0x%x].";
    v23 = 38;
    goto LABEL_44;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x126u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
      "Failed to set indent property: [0x%x].",
      XmlWriter);
  XmlWriter = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)SystemTime[0] + 208LL))(SystemTime[0], 0);
  if ( XmlWriter < 0 )
  {
    v22 = "Failed to write start of XML document: [0x%x].";
    v23 = 41;
    goto LABEL_44;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x129u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
      "Failed to write start of XML document: [0x%x].",
      XmlWriter);
  XmlWriter = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)SystemTime[0] + 216LL))(
                SystemTime[0],
                0,
                L"CompatReport",
                0);
  if ( XmlWriter < 0 )
  {
    v22 = "Could not write root element: [0x%x].";
    v23 = 44;
    goto LABEL_44;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x12Cu,
      "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
      "Could not write root element: [0x%x].",
      XmlWriter);
  if ( v6 )
  {
    v30 = *(const WCHAR **)(a1 + 24);
    if ( !v30 )
    {
      XmlWriter = -2147024809;
      LODWORD(pstmTemplate) = -2147024809;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        51,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
        "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
        (const char *)pstmTemplate,
        (int)"Mig file necessary but not specified.",
        (const char *)v62);
      goto LABEL_46;
    }
    v31 = SystemTime[0];
    v32 = *(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD, LPWSTR))(*(_QWORD *)SystemTime[0] + 56LL);
    FileNameW = PathFindFileNameW(v30);
    XmlWriter = v32(v31, 0, L"MigXmlFile", 0, FileNameW);
    if ( XmlWriter < 0 )
    {
      v22 = "Failed to write mig xml: [0x%x].";
      v23 = 55;
      goto LABEL_44;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x137u,
        "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
        "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
        "Failed to write mig xml: [0x%x].",
        XmlWriter);
  }
  XmlWriter = Windows::Compat::Appraiser::SetupXmlOutputter::WriteUpgradeInfo(
                (struct IXmlWriter *)SystemTime[0],
                (struct Windows::Compat::Appraiser::WicaRun *)a3);
  if ( XmlWriter < 0 )
  {
    v22 = "Writing upgrade info (SystemInfo) node failed: [0x%x].";
    v23 = 63;
    goto LABEL_44;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x13Fu,
      "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
      "Writing upgrade info (SystemInfo) node failed: [0x%x].",
      XmlWriter);
  v34 = v66[1];
  v35 = v66[2];
  if ( !v66[3] )
  {
    if ( v66[1] )
    {
      SystemTime[1] = &Windows::Compat::Appraiser::SetupXmlOutputter::WriteHardwareNode;
      LODWORD(SystemTime[2]) = 0;
      HIDWORD(SystemTime[2]) = *(_DWORD *)&v99.wSecond;
      XmlWriter = Windows::Compat::Appraiser::SetupXmlOutputter::CreateAndStoreNode(
                    a1,
                    &SystemTime[1],
                    hHeap,
                    *(_QWORD *)(a1 + 32),
                    *(_QWORD *)(a1 + 80),
                    *(_QWORD *)(a1 + 88));
      if ( XmlWriter < 0 )
      {
        v22 = "Error creating hardware node: [0x%x].";
        v23 = 70;
        goto LABEL_44;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x146u,
          "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
          "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
          "Error creating hardware node: [0x%x].",
          XmlWriter);
    }
    if ( v35 )
    {
      SystemTime[1] = &Windows::Compat::Appraiser::SetupXmlOutputter::WriteDriversNode;
      LODWORD(SystemTime[2]) = 0;
      HIDWORD(SystemTime[2]) = *(_DWORD *)&v99.wSecond;
      v36 = Windows::Compat::Appraiser::SetupXmlOutputter::CreateAndStoreNode(
              a1,
              &SystemTime[1],
              v75,
              *(_QWORD *)(a1 + 40),
              *(_QWORD *)(a1 + 80),
              *(_QWORD *)(a1 + 88));
      XmlWriter = v36;
      if ( v36 < 0 )
      {
        LODWORD(v62) = v36;
        ppstma = "Error creating hardware node: [0x%x].";
        v23 = 76;
        goto LABEL_45;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x14Cu,
          "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
          "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
          "Error creating hardware node: [0x%x].",
          v36);
    }
  }
  if ( v34 )
  {
    XmlWriter = Windows::Compat::Appraiser::SetupXmlOutputter::LoadAndAppendNode(
                  (struct IXmlWriter *)SystemTime[0],
                  *(const unsigned __int16 **)(a1 + 32));
    if ( XmlWriter < 0 )
    {
      v22 = "Error writing Hardware node: [0x%x].";
      v23 = 83;
      goto LABEL_44;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x153u,
        "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
        "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
        "Error writing Hardware node: [0x%x].",
        XmlWriter);
  }
  if ( v35 )
  {
    XmlWriter = Windows::Compat::Appraiser::SetupXmlOutputter::WriteDevicesNode(
                  a1,
                  SystemTime[0],
                  v83,
                  &v72,
                  *(_QWORD *)(a1 + 80),
                  *(_QWORD *)(a1 + 88));
    if ( XmlWriter < 0 )
    {
      v37 = "Error creating devices node: [0x%x].";
      v23 = 89;
LABEL_116:
      LODWORD(v62) = XmlWriter;
      LODWORD(ppstma) = (_DWORD)v37;
      goto LABEL_45;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x159u,
        "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
        "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
        "Error creating devices node: [0x%x].",
        XmlWriter);
    v38 = Windows::Compat::Appraiser::SetupXmlOutputter::WriteGenericMessageHardwareNode(
            (struct IXmlWriter *)SystemTime[0],
            0,
            0,
            0,
            0);
    XmlWriter = v38;
    if ( v38 < 0 )
    {
      LODWORD(v62) = v38;
      ppstma = "Error creating generic hardware node for devices: [0x%x].";
      v23 = 92;
      goto LABEL_45;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x15Cu,
        "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
        "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
        "Error creating generic hardware node for devices: [0x%x].",
        v38);
    appended = Windows::Compat::Appraiser::SetupXmlOutputter::LoadAndAppendNode(
                 (struct IXmlWriter *)SystemTime[0],
                 *(const unsigned __int16 **)(a1 + 40));
    XmlWriter = appended;
    if ( appended < 0 )
    {
      LODWORD(v62) = appended;
      ppstma = "Error writing DriverPackages node: [0x%x].";
      v23 = 95;
      goto LABEL_45;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x15Fu,
        "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
        "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
        "Error writing DriverPackages node: [0x%x].",
        appended);
  }
  if ( v21 )
  {
    XmlWriter = Windows::Compat::Appraiser::SetupXmlOutputter::WriteProgramsNode(
                  a1,
                  (struct IXmlWriter *)SystemTime[0],
                  (int)v86,
                  (struct Windows::Compat::Appraiser::IPropertyListEnumerator *)&v72,
                  *(struct Windows::Compat::Appraiser::MapTable **)(a1 + 80),
                  *(struct Windows::Compat::Appraiser::MapTable **)(a1 + 88));
    v8 = 0;
    if ( XmlWriter < 0 )
    {
      v37 = "Writing programs node failed: [0x%x].";
      v23 = 101;
      goto LABEL_116;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x165u,
        "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
        "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
        "Writing programs node failed: [0x%x].",
        XmlWriter);
    v40 = Windows::Compat::Appraiser::SetupXmlOutputter::WriteGenericMessageHardwareNode(
            (struct IXmlWriter *)SystemTime[0],
            0,
            0,
            0,
            0);
    XmlWriter = v40;
    if ( v40 < 0 )
    {
      LODWORD(v62) = v40;
      ppstma = "Error creating generic hardware node for files: [0x%x].";
      v23 = 104;
      goto LABEL_45;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x168u,
        "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
        "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
        "Error creating generic hardware node for files: [0x%x].",
        v40);
    v41 = Windows::Compat::Appraiser::SetupXmlOutputter::WriteGenericMessageHardwareNode(
            (struct IXmlWriter *)SystemTime[0],
            0,
            0,
            0,
            0);
    XmlWriter = v41;
    if ( v41 < 0 )
    {
      LODWORD(v62) = v41;
      ppstma = "Error creating generic hardware node for matching infos: [0x%x].";
      v23 = 107;
      goto LABEL_45;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x16Bu,
        "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
        "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
        "Error creating generic hardware node for matching infos: [0x%x].",
        v41);
  }
  else
  {
    v8 = 0;
  }
  if ( v66[4] )
  {
    XmlWriter = Windows::Compat::Appraiser::SetupXmlOutputter::WriteGenericMessageHardwareNode(
                  (struct IXmlWriter *)SystemTime[0],
                  1,
                  *(_QWORD *)(a1 + 64),
                  *(_QWORD *)(a1 + 72),
                  (__int64)&v72);
    if ( XmlWriter < 0 )
    {
      v37 = "Error creating generic hardware node for gated items: [0x%x].";
      v23 = 120;
      goto LABEL_116;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x178u,
        "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
        "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
        "Error creating generic hardware node for gated items: [0x%x].",
        XmlWriter);
  }
  v42 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)SystemTime[0] + 120LL))(SystemTime[0]);
  XmlWriter = v42;
  if ( v42 < 0 )
  {
    LODWORD(v62) = v42;
    ppstma = "Write end element failed: [0x%x].";
    v23 = 0x80;
    goto LABEL_45;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x180u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
      "Write end element failed: [0x%x].",
      v42);
  v43 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)SystemTime[0] + 112LL))(SystemTime[0]);
  XmlWriter = v43;
  if ( v43 < 0 )
  {
    LODWORD(v62) = v43;
    ppstma = "Write end document failed: [0x%x].";
    v23 = -125;
    goto LABEL_45;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x183u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
      "Write end document failed: [0x%x].",
      v43);
  v44 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)SystemTime[0] + 248LL))(SystemTime[0]);
  XmlWriter = v44;
  if ( v44 < 0 )
  {
    LODWORD(v62) = v44;
    ppstma = "Flush failed: [0x%x].";
    v23 = -122;
    goto LABEL_45;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x186u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
      "Flush failed: [0x%x].",
      v44);
  if ( *(_QWORD *)(a1 + 96) )
  {
    v45 = ((__int64 (__fastcall *)(IUnknown *, _BYTE *, __int64))pOutputStream->lpVtbl[4].QueryInterface)(
            pOutputStream,
            v96,
            1);
    XmlWriter = v45;
    if ( v45 < 0 )
    {
      LODWORD(v62) = v45;
      ppstma = "Failed to query file stats: [0x%x].";
      v23 = -117;
      goto LABEL_45;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x18Bu,
        "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
        "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
        "Failed to query file stats: [0x%x].",
        v45);
    v46 = v97 + 2;
    ProcessHeap = GetProcessHeap();
    v7 = (OLECHAR *)HeapAlloc(ProcessHeap, 0, v46);
    if ( !v7 )
    {
      XmlWriter = -2147024882;
LABEL_165:
      v8 = v65;
      goto LABEL_182;
    }
    XmlWriter = ((__int64 (__fastcall *)(IUnknown *, _QWORD, _QWORD, _QWORD))pOutputStream->lpVtbl[1].Release)(
                  pOutputStream,
                  0,
                  0,
                  0);
    if ( XmlWriter < 0 )
    {
      v48 = "Failed to seek to beginning of stream: [0x%x].";
      v49 = -111;
LABEL_168:
      LODWORD(v62) = XmlWriter;
      LODWORD(pstmTemplate) = XmlWriter;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        v49,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
        "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
        (const char *)pstmTemplate,
        (int)v48,
        (const char *)v62);
      goto LABEL_165;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x191u,
        "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
        "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
        "Failed to seek to beginning of stream: [0x%x].",
        XmlWriter);
    XmlWriter = ((__int64 (__fastcall *)(IUnknown *, OLECHAR *, _QWORD, _QWORD))pOutputStream->lpVtbl[1].QueryInterface)(
                  pOutputStream,
                  v7,
                  v97,
                  0);
    if ( XmlWriter < 0 )
    {
      v48 = "Failed to copy stream: [0x%x].";
      v49 = -108;
      goto LABEL_168;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x194u,
        "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
        "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
        "Failed to copy stream: [0x%x].",
        XmlWriter);
    v7[(unsigned __int64)v97 >> 1] = 0;
    v50 = SysAllocString(v7 + 1);
    v8 = v50;
    if ( !v50 )
    {
      XmlWriter = -2147024882;
      goto LABEL_182;
    }
    v51 = (*(__int64 (__fastcall **)(BSTR, _QWORD))(a1 + 96))(v50, *(_QWORD *)(a1 + 56));
    XmlWriter = v51;
    if ( v51 < 0 )
    {
      LODWORD(v62) = v51;
      ppstm = "Failed to send xml to setup head: [0x%x].";
      v17 = -100;
      goto LABEL_22;
    }
    v8 = 0;
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x19Cu,
        "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
        "Windows::Compat::Appraiser::SetupXmlOutputter::DoOutput",
        "Failed to send xml to setup head: [0x%x].",
        v51);
  }
  XmlWriter = 0;
LABEL_182:
  TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v100);
  v52 = (volatile signed __int64 *)v100;
  if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
    v52 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v52,
    _InterlockedExchangeAdd64(v52 + 17, 0),
    v101);
  if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
    UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v53);
  v54 = qword_1802C9628;
  if ( *(_DWORD *)qword_1802C9628 > 5u
    && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000020LL) != 0
    && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000020LL) == *(_QWORD *)(qword_1802C9628 + 24) )
  {
    SystemTime[1] = v101;
    v71 = 0x1000000;
    v70 = (__int64)&szValueBuf;
    v98 = 0;
    GetSystemTime(&v98);
    v99 = v98;
    v69 = (__int64)&v99;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
      v54,
      (__int64)byte_1802A497D,
      v55,
      v56,
      &v69,
      (const size_t **)&v70,
      (__int64)&v71,
      (const char **)&SystemTime[1]);
  }
  if ( v7 )
  {
    v57 = GetProcessHeap();
    HeapFree(v57, 0, v7);
  }
  SysFreeString(v8);
  if ( ppOutput )
    ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
  if ( pOutputStream )
    ((void (__fastcall *)(IUnknown *))pOutputStream->lpVtbl->Release)(pOutputStream);
  if ( SystemTime[0] )
    (*(void (__fastcall **)(void *))(*(_QWORD *)SystemTime[0] + 16LL))(SystemTime[0]);
  v72 = (__int64)&Windows::Compat::Appraiser::IPropertyListEnumerator::`vftable';
  if ( v91[1] )
    HeapFree(v89[0], 0, v91[1]);
  if ( v94[1] )
    HeapFree(v92[0], 0, v94[1]);
  if ( v88[1] )
    HeapFree(v86[0], 0, v88[1]);
  *(_OWORD *)v86 = 0;
  v87 = 0;
  *(_OWORD *)v88 = 0;
  if ( v77[1] )
    HeapFree(v75[0], 0, v77[1]);
  *(_OWORD *)v75 = 0;
  v76 = 0;
  *(_OWORD *)v77 = 0;
  if ( v85[1] )
    HeapFree(v83[0], 0, v85[1]);
  if ( lpMem[1] )
    HeapFree(hHeap[0], 0, lpMem[1]);
  return (unsigned int)XmlWriter;
}

```

## disassembly

```asm
0x1800efba0  mov     rax, rsp
0x1800efba3  push    rbp
0x1800efba4  push    rsi
0x1800efba5  push    rdi
0x1800efba6  push    r12
0x1800efba8  push    r13
0x1800efbaa  push    r14
0x1800efbac  push    r15
0x1800efbae  lea     rbp, [rax-2C8h]
0x1800efbb5  sub     rsp, 390h
0x1800efbbc  mov     [rbp+2C0h+var_1D8], 0FFFFFFFFFFFFFFFEh
0x1800efbc7  mov     [rax+20h], rbx
0x1800efbcb  mov     rax, cs:__security_cookie
0x1800efbd2  xor     rax, rsp
0x1800efbd5  mov     [rbp+2C0h+var_40], rax
0x1800efbdc  mov     r14, r8
0x1800efbdf  mov     r13, rdx
0x1800efbe2  mov     rsi, rcx
0x1800efbe5  xorps   xmm0, xmm0
0x1800efbe8  movups  xmmword ptr [rbp+2C0h+hHeap], xmm0
0x1800efbec  movups  [rbp+2C0h+var_2B8], xmm0
0x1800efbf0  movups  xmmword ptr [rbp+2C0h+lpMem], xmm0
0x1800efbf4  call    cs:__imp_GetProcessHeap
0x1800efbfa  mov     [rbp+2C0h+hHeap], rax
0x1800efbfe  mov     edi, 10h
0x1800efc03  mov     [rbp+2C0h+lpMem], rdi
0x1800efc07  xorps   xmm0, xmm0
0x1800efc0a  movdqu  [rbp+2C0h+var_2B8], xmm0
0x1800efc0f  xor     ebx, ebx
0x1800efc11  mov     [rbp+2C0h+lpMem+8], rbx
0x1800efc15  lea     r15d, [rdi-8]
0x1800efc19  mov     [rbp+2C0h+hHeap+8], r15
0x1800efc1d  movups  xmmword ptr [rbp+2C0h+var_298], xmm0
0x1800efc21  movups  xmmword ptr [rbp+2C0h+var_278], xmm0
0x1800efc25  call    cs:__imp_GetProcessHeap
0x1800efc2b  mov     [rbp+2C0h+var_298], rax
0x1800efc2f  mov     [rbp+2C0h+var_278], rdi
0x1800efc33  xorps   xmm0, xmm0
0x1800efc36  movdqu  [rbp+2C0h+var_288], xmm0
0x1800efc3b  mov     [rbp+2C0h+var_278+8], rbx
0x1800efc3f  mov     [rbp+2C0h+var_298+8], r15
0x1800efc43  movups  xmmword ptr [rbp+2C0h+var_308], xmm0
0x1800efc47  movups  [rbp+2C0h+var_2F8], xmm0
0x1800efc4b  movups  xmmword ptr [rbp+2C0h+var_2E8], xmm0
0x1800efc4f  call    cs:__imp_GetProcessHeap
0x1800efc55  mov     [rbp+2C0h+var_308], rax
0x1800efc59  mov     [rbp+2C0h+var_2E8], rdi
0x1800efc5d  xorps   xmm0, xmm0
0x1800efc60  movdqu  [rbp+2C0h+var_2F8], xmm0
0x1800efc65  mov     [rbp+2C0h+var_2E8+8], rbx
0x1800efc69  mov     [rbp+2C0h+var_308+8], r15
0x1800efc6d  movups  xmmword ptr [rbp+2C0h+var_268], xmm0
0x1800efc71  movups  [rbp+2C0h+var_258], xmm0
0x1800efc75  movups  xmmword ptr [rbp+2C0h+var_248], xmm0
0x1800efc79  call    cs:__imp_GetProcessHeap
0x1800efc7f  mov     [rbp+2C0h+var_268], rax
0x1800efc83  mov     [rbp+2C0h+var_248], rdi
0x1800efc87  xorps   xmm0, xmm0
0x1800efc8a  movdqu  [rbp+2C0h+var_258], xmm0
0x1800efc8f  mov     [rbp+2C0h+var_248+8], rbx
0x1800efc96  mov     [rbp+2C0h+var_268+8], r15
0x1800efc9a  movups  xmmword ptr [rbp+2C0h+var_208], xmm0
0x1800efca1  movups  xmmword ptr [rbp+2C0h+var_1E8], xmm0
0x1800efca8  call    cs:__imp_GetProcessHeap
0x1800efcae  mov     [rbp+2C0h+var_208], rax
0x1800efcb5  mov     [rbp+2C0h+var_1E8], rdi
0x1800efcbc  xorps   xmm0, xmm0
0x1800efcbf  movdqu  [rbp+2C0h+var_1F8], xmm0
0x1800efcc7  mov     [rbp+2C0h+var_1E8+8], rbx
0x1800efcce  mov     [rbp+2C0h+var_208+8], r15
0x1800efcd5  movups  xmmword ptr [rbp+2C0h+var_238], xmm0
0x1800efcdc  movups  xmmword ptr [rbp+2C0h+var_218], xmm0
0x1800efce3  call    cs:__imp_GetProcessHeap
0x1800efce9  mov     [rbp+2C0h+var_238], rax
0x1800efcf0  mov     [rbp+2C0h+var_218], rdi
0x1800efcf7  xorps   xmm0, xmm0
0x1800efcfa  movdqu  [rbp+2C0h+var_228], xmm0
0x1800efd02  mov     [rbp+2C0h+var_218+8], rbx
0x1800efd09  mov     [rbp+2C0h+var_238+8], r15
0x1800efd10  lea     rax, ??_7MetadataPropertyEnumerator@Appraiser@Compat@Windows@@6B@; const Windows::Compat::Appraiser::MetadataPropertyEnumerator::`vftable'
0x1800efd17  mov     [rbp+2C0h+var_320], rax
0x1800efd1b  mov     [rbp+2C0h+var_318], rbx
0x1800efd1f  mov     [rbp+2C0h+var_310], rbx
0x1800efd23  mov     qword ptr [rsp+3C0h+SystemTime], rbx
0x1800efd28  mov     [rbp+2C0h+pOutputStream], rbx
0x1800efd2c  mov     [rbp+2C0h+ppOutput], rbx
0x1800efd30  xor     edx, edx; Val
0x1800efd32  lea     r8d, [rdi+40h]; Size
0x1800efd36  lea     rcx, [rbp+2C0h+var_1D0]; void *
0x1800efd3d  call    memset_0
0x1800efd42  mov     [rsp+3C0h+var_360+1], bl
0x1800efd46  mov     [rsp+3C0h+var_360+2], bl
0x1800efd4a  mov     [rsp+3C0h+var_360], bl
0x1800efd4e  mov     [rsp+3C0h+var_360+4], bl
0x1800efd52  mov     [rsp+3C0h+var_360+3], bl
0x1800efd56  mov     r12d, ebx
0x1800efd59  mov     r15d, ebx
0x1800efd5c  mov     qword ptr [rsp+3C0h+var_368], rbx
0x1800efd61  mov     dil, bl
0x1800efd64  mov     byte ptr [rsp+3C0h+var_370], bl
0x1800efd68  lea     rcx, [rbp+2C0h+var_160]; this
0x1800efd6f  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1800efd74  lea     rcx, [rbp+2C0h+var_160]
0x1800efd7b  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x1800efd82  test    rax, rax
0x1800efd85  cmovnz  rcx, rax; this
0x1800efd89  mov     edx, ebx
0x1800efd8b  lock xadd [rcx+88h], rdx; unsigned __int64
0x1800efd94  lea     r8, [rbp+2C0h+var_D0]; char *
0x1800efd9b  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1800efda0  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, bl; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x1800efda6  jz      short loc_1800EFDB4
0x1800efda8  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x1800efdaf  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x1800efdb4  mov     rbx, cs:qword_1802C9628
0x1800efdbb  mov     eax, [rbx]
0x1800efdbd  mov     rdx, 200000000020h
0x1800efdc7  lea     r8, szValueBuf
0x1800efdce  cmp     eax, 5
0x1800efdd1  jbe     loc_1800EFE68
0x1800efdd7  mov     rcx, [rbx+18h]
0x1800efddb  mov     rax, [rbx+10h]
0x1800efddf  test    rdx, rax
0x1800efde2  jz      loc_1800EFE68
0x1800efde8  mov     rax, rcx
0x1800efdeb  and     rax, rdx
0x1800efdee  cmp     rax, rcx
0x1800efdf1  jnz     short loc_1800EFE68
0x1800efdf3  lea     rax, [rbp+2C0h+var_D0]
0x1800efdfa  mov     qword ptr [rbp+2C0h+var_2D8], rax
0x1800efdfe  mov     [rbp+2C0h+var_338], 1000000h
0x1800efe06  mov     [rbp+2C0h+var_330], r8
0x1800efe0a  xorps   xmm0, xmm0
0x1800efe0d  movups  xmmword ptr [rsp+3C0h+SystemTime+8], xmm0
0x1800efe12  lea     rcx, [rsp+3C0h+SystemTime+8]; lpSystemTime
0x1800efe17  call    cs:__imp_GetSystemTime
0x1800efe1d  movaps  xmm0, xmmword ptr [rsp+3C0h+SystemTime+8]
0x1800efe22  movdqa  xmmword ptr [rbp+2C0h+var_180.wYear], xmm0
0x1800efe2a  lea     rax, [rbp+2C0h+var_180]
0x1800efe31  mov     [rbp+2C0h+var_328], rax
0x1800efe35  lea     rax, [rbp+2C0h+var_2D8]
0x1800efe39  mov     [rsp+3C0h+var_388], rax
0x1800efe3e  lea     rax, [rbp+2C0h+var_338]
0x1800efe42  mov     [rsp+3C0h+var_390], rax
0x1800efe47  lea     rax, [rbp+2C0h+var_330]
0x1800efe4b  mov     [rsp+3C0h+ppstm], rax
0x1800efe50  lea     rax, [rbp+2C0h+var_328]
0x1800efe54  mov     [rsp+3C0h+pstmTemplate], rax
0x1800efe59  lea     rdx, byte_1802A49CB
0x1800efe60  mov     rcx, rbx
0x1800efe63  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x1800efe68  mov     r8, [rbp+2C0h+lpMem+8]; lpMem
0x1800efe6c  xor     ebx, ebx
0x1800efe6e  test    r8, r8
0x1800efe71  jz      short loc_1800EFE7F
0x1800efe73  xor     edx, edx; dwFlags
0x1800efe75  mov     rcx, [rbp+2C0h+hHeap]; hHeap
0x1800efe79  call    cs:__imp_HeapFree
0x1800efe7f  xorps   xmm0, xmm0
0x1800efe82  movups  xmmword ptr [rbp+2C0h+hHeap], xmm0
0x1800efe86  movups  [rbp+2C0h+var_2B8], xmm0
0x1800efe8a  movups  xmmword ptr [rbp+2C0h+lpMem], xmm0
0x1800efe8e  call    cs:__imp_GetProcessHeap
0x1800efe94  mov     [rbp+2C0h+hHeap], rax
0x1800efe98  mov     [rbp+2C0h+lpMem], 10h
0x1800efea0  xorps   xmm0, xmm0
0x1800efea3  movdqu  [rbp+2C0h+var_2B8], xmm0
0x1800efea8  mov     [rbp+2C0h+lpMem+8], rbx
0x1800efeac  mov     [rbp+2C0h+hHeap+8], 8
0x1800efeb4  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800efeba  test    al, 1
0x1800efebc  jz      short loc_1800EFEE1
0x1800efebe  mov     dword ptr [rsp+3C0h+pstmTemplate], ebx
0x1800efec2  lea     r9, aFailedToInitia_32; "Failed to initialize RtlArray: [0x%x]."
0x1800efec9  lea     r8, aWindowsCompatA_771; "Windows::Compat::Appraiser::SetupXmlOut"...
0x1800efed0  lea     rdx, aOnecoreBaseApp_79; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800efed7  mov     ecx, 0FEh; unsigned int
0x1800efedc  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800efee1  xorps   xmm0, xmm0
0x1800efee4  movups  xmmword ptr [rbp+2C0h+var_298], xmm0
0x1800efee8  movups  xmmword ptr [rbp+2C0h+var_278], xmm0
0x1800efeec  call    cs:__imp_GetProcessHeap
0x1800efef2  mov     [rbp+2C0h+var_298], rax
0x1800efef6  mov     [rbp+2C0h+var_278], 10h
0x1800efefe  xorps   xmm0, xmm0
0x1800eff01  movdqu  [rbp+2C0h+var_288], xmm0
0x1800eff06  mov     [rbp+2C0h+var_278+8], rbx
0x1800eff0a  mov     [rbp+2C0h+var_298+8], 8
0x1800eff12  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800eff18  test    al, 1
0x1800eff1a  jz      short loc_1800EFF3F
0x1800eff1c  mov     dword ptr [rsp+3C0h+pstmTemplate], ebx
0x1800eff20  lea     r9, aFailedToInitia_32; "Failed to initialize RtlArray: [0x%x]."
0x1800eff27  lea     r8, aWindowsCompatA_771; "Windows::Compat::Appraiser::SetupXmlOut"...
0x1800eff2e  lea     rdx, aOnecoreBaseApp_79; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800eff35  mov     ecx, 0FFh; unsigned int
0x1800eff3a  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800eff3f  mov     r8, [rbp+2C0h+var_2E8+8]; lpMem
0x1800eff43  test    r8, r8
0x1800eff46  jz      short loc_1800EFF54
0x1800eff48  xor     edx, edx; dwFlags
0x1800eff4a  mov     rcx, [rbp+2C0h+var_308]; hHeap
0x1800eff4e  call    cs:__imp_HeapFree
0x1800eff54  xorps   xmm0, xmm0
0x1800eff57  movups  xmmword ptr [rbp+2C0h+var_308], xmm0
0x1800eff5b  movups  [rbp+2C0h+var_2F8], xmm0
0x1800eff5f  movups  xmmword ptr [rbp+2C0h+var_2E8], xmm0
0x1800eff63  call    cs:__imp_GetProcessHeap
0x1800eff69  mov     [rbp+2C0h+var_308], rax
0x1800eff6d  mov     [rbp+2C0h+var_2E8], 10h
0x1800eff75  xorps   xmm0, xmm0
0x1800eff78  movdqu  [rbp+2C0h+var_2F8], xmm0
0x1800eff7d  mov     [rbp+2C0h+var_2E8+8], rbx
0x1800eff81  mov     [rbp+2C0h+var_308+8], 8
0x1800eff89  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800eff8f  test    al, 1
0x1800eff91  jz      short loc_1800EFFB6
0x1800eff93  mov     dword ptr [rsp+3C0h+pstmTemplate], ebx
0x1800eff97  lea     r9, aFailedToInitia_32; "Failed to initialize RtlArray: [0x%x]."
0x1800eff9e  lea     r8, aWindowsCompatA_771; "Windows::Compat::Appraiser::SetupXmlOut"...
0x1800effa5  lea     rdx, aOnecoreBaseApp_79; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800effac  mov     ecx, 100h; unsigned int
0x1800effb1  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800effb6  mov     r9d, 10h
0x1800effbc  xor     r8d, r8d
0x1800effbf  lea     rcx, [rbp+2C0h+var_268]
0x1800effc3  call    ?Initialize@?$RtlArray@PEAVIAsset@Appraiser@Compat@Windows@@@@QEAAJPEAX_K1H@Z; RtlArray<Windows::Compat::Appraiser::IAsset *>::Initialize(void *,unsigned __int64,unsigned __int64,int)
0x1800effc8  mov     ebx, eax
0x1800effca  test    eax, eax
0x1800effcc  jns     short loc_1800F0004
0x1800effce  mov     edx, 101h; bool
0x1800effd3  mov     dword ptr [rsp+3C0h+var_390], ebx; char *
0x1800effd7  lea     rax, aFailedToInitia_32; "Failed to initialize RtlArray: [0x%x]."
0x1800effde  mov     [rsp+3C0h+ppstm], rax; int
0x1800effe3  lea     r9, aWindowsCompatA_771; "Windows::Compat::Appraiser::SetupXmlOut"...
0x1800effea  lea     r8, aOnecoreBaseApp_79; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800efff1  mov     ecx, 1; this
0x1800efff6  mov     dword ptr [rsp+3C0h+pstmTemplate], ebx; char *
0x1800efffa  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800effff  jmp     loc_1800F0FAF
0x1800f0004  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800f000a  test    al, 1
0x1800f000c  jz      short loc_1800F0031
0x1800f000e  mov     dword ptr [rsp+3C0h+pstmTemplate], ebx
0x1800f0012  lea     r9, aFailedToInitia_32; "Failed to initialize RtlArray: [0x%x]."
0x1800f0019  lea     r8, aWindowsCompatA_771; "Windows::Compat::Appraiser::SetupXmlOut"...
0x1800f0020  lea     rdx, aOnecoreBaseApp_79; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800f0027  mov     ecx, 101h; unsigned int
0x1800f002c  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800f0031  mov     r9d, 10h
0x1800f0037  xor     r8d, r8d
0x1800f003a  lea     rcx, [rbp+2C0h+var_208]
0x1800f0041  call    ?Initialize@?$RtlArray@PEAVIAsset@Appraiser@Compat@Windows@@@@QEAAJPEAX_K1H@Z; RtlArray<Windows::Compat::Appraiser::IAsset *>::Initialize(void *,unsigned __int64,unsigned __int64,int)
0x1800f0046  mov     ebx, eax
0x1800f0048  test    eax, eax
0x1800f004a  jns     short loc_1800F0053
0x1800f004c  mov     edx, 102h
0x1800f0051  jmp     short loc_1800EFFD3
0x1800f0053  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800f0059  test    al, 1
0x1800f005b  jz      short loc_1800F0080
0x1800f005d  mov     dword ptr [rsp+3C0h+pstmTemplate], ebx
0x1800f0061  lea     r9, aFailedToInitia_32; "Failed to initialize RtlArray: [0x%x]."
0x1800f0068  lea     r8, aWindowsCompatA_771; "Windows::Compat::Appraiser::SetupXmlOut"...
0x1800f006f  lea     rdx, aOnecoreBaseApp_79; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800f0076  mov     ecx, 102h; unsigned int
0x1800f007b  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800f0080  mov     r9d, 10h
0x1800f0086  xor     r8d, r8d
0x1800f0089  lea     rcx, [rbp+2C0h+var_238]
0x1800f0090  call    ?Initialize@?$RtlArray@PEAVIAsset@Appraiser@Compat@Windows@@@@QEAAJPEAX_K1H@Z; RtlArray<Windows::Compat::Appraiser::IAsset *>::Initialize(void *,unsigned __int64,unsigned __int64,int)
0x1800f0095  mov     ebx, eax
0x1800f0097  test    eax, eax
0x1800f0099  jns     short loc_1800F00A5
0x1800f009b  mov     edx, 103h
0x1800f00a0  jmp     loc_1800EFFD3
0x1800f00a5  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800f00ab  test    al, 1
0x1800f00ad  jz      short loc_1800F00D2
0x1800f00af  mov     dword ptr [rsp+3C0h+pstmTemplate], ebx
0x1800f00b3  lea     r9, aFailedToInitia_32; "Failed to initialize RtlArray: [0x%x]."
0x1800f00ba  lea     r8, aWindowsCompatA_771; "Windows::Compat::Appraiser::SetupXmlOut"...
0x1800f00c1  lea     rdx, aOnecoreBaseApp_79; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800f00c8  mov     ecx, 103h; unsigned int
0x1800f00cd  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800f00d2  mov     rax, [r14]
0x1800f00d5  mov     [rbp+2C0h+var_310], rax
0x1800f00d9  mov     eax, [r14+40h]
0x1800f00dd  mov     dword ptr [rbp+2C0h+var_318+4], eax
0x1800f00e0  mov     rax, [rbp+2C0h+var_320]
0x1800f00e4  lea     rcx, [rbp+2C0h+var_320]
0x1800f00e8  mov     rax, [rax+8]
0x1800f00ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f00f1  mov     [rsp+3C0h+var_390], r13
0x1800f00f6  lea     rax, [rbp+2C0h+var_238]
0x1800f00fd  mov     [rsp+3C0h+ppstm], rax
0x1800f0102  lea     rax, [rbp+2C0h+var_208]
0x1800f0109  mov     [rsp+3C0h+pstmTemplate], rax
0x1800f010e  lea     r9, [rbp+2C0h+var_268]
0x1800f0112  lea     r8, [rbp+2C0h+var_308]
  ... truncated ...
```
