# Windows::Compat::Appraiser::SetupXmlOutputter::WriteBlockingMatchingInfos(IXmlWriter *,RtlArray<Windows::Compat::Appraiser::IAsset *> &,Windows::Compat::Appraiser::IPropertyListEnumerator *,Windows::Compat::Appraiser::MapTable *,Windows::Compat::Appraiser::MapTable *)

- ea: `0x1801117ec`
- end: `0x18011219c`
- name: `?WriteBlockingMatchingInfos@SetupXmlOutputter@Appraiser@Compat@Windows@@AEAAJPEAUIXmlWriter@@AEAV?$RtlArray@PEAVIAsset@Appraiser@Compat@Windows@@@@PEAVIPropertyListEnumerator@234@PEAUMapTable@234@3@Z`
- size: `2480`
- prototype: `__int64 __fastcall(int, int, int, int, struct Windows::Compat::Appraiser::MapTable *, struct Windows::Compat::Appraiser::MapTable *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18011442c`

## callees

- `0x1800092dc`
- `0x18002ebb8`
- `0x1800301d0`
- `0x18003b2a0`
- `0x1800aa27c`
- `0x1800ad680`
- `0x1800ad88c`
- `0x1800ad97c`
- `0x1801117ec`
- `0x1801121a4`
- `0x180112ed0`
- `0x180113574`
- `0x1802174cc`
- `0x18021f010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18011183a`
- `KERNEL32!GetProcessHeap` at `0x180111874`
- `KERNEL32!GetProcessHeap` at `0x1801118a2`
- `KERNEL32!GetProcessHeap` at `0x18011183a`
- `KERNEL32!GetProcessHeap` at `0x180111874`
- `KERNEL32!GetProcessHeap` at `0x1801118a2`
- `KERNEL32!HeapFree` at `0x180111fb4`
- `KERNEL32!HeapFree` at `0x180111fdb`
- `KERNEL32!HeapFree` at `0x180111fff`
- `KERNEL32!HeapFree` at `0x180112024`
- `KERNEL32!HeapFree` at `0x180111fb4`
- `KERNEL32!HeapFree` at `0x180111fdb`
- `KERNEL32!HeapFree` at `0x180111fff`
- `KERNEL32!HeapFree` at `0x180112024`

## string_xrefs

- `0x1801118eb`: `onecore\base\appcompat\appraiser\outputters\setupxml_app.cpp`
- `0x18011191c`: `onecore\base\appcompat\appraiser\outputters\setupxml_app.cpp`
- `0x1801118e4`: `Windows::Compat::Appraiser::SetupXmlOutputter::WriteBlockingMatchingInfos`
- `0x180111915`: `Windows::Compat::Appraiser::SetupXmlOutputter::WriteBlockingMatchingInfos`
- `0x180111f36`: `Failed to write program action: [0x%x].`
- `0x18011207f`: `Failed to write program action: [0x%x].`
- `0x180111df9`: `Failed to write name attribute: [0x%x].`
- `0x1801120e7`: `Failed to write name attribute: [0x%x].`
- `0x180111bfc`: `Error getting app hyperlink target and text from matching info block asset: [0x%x].`
- `0x180112135`: `Error getting app hyperlink target and text from matching info block asset: [0x%x].`
- `0x180111ef2`: `Failed to write orphan program compat info: [0x%x].`
- `0x180112099`: `Failed to write orphan program compat info: [0x%x].`
- `0x180111e4e`: `Failed to write id attribute: [0x%x].`
- `0x1801120cd`: `Failed to write id attribute: [0x%x].`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Compat::Appraiser::SetupXmlOutputter::WriteBlockingMatchingInfos(
        Windows::Compat::Appraiser::SetupXmlOutputter *a1,
        struct IXmlWriter *a2,
        unsigned __int64 *a3,
        struct Windows::Compat::Appraiser::IPropertyListEnumerator *a4,
        struct Windows::Compat::Appraiser::MapTable *a5,
        struct Windows::Compat::Appraiser::MapTable *a6)
{
  int v7; // eax
  int RequiredSingleValue; // ebx
  const char *v9; // r15
  char v10; // dl
  unsigned __int64 v11; // rbx
  _QWORD *v12; // r8
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rcx
  wchar_t *v15; // r15
  struct Windows::Compat::Appraiser::IAsset **v16; // rax
  struct Windows::Compat::Appraiser::IAsset *v17; // r12
  const unsigned __int16 **v18; // rdx
  struct Windows::Compat::Appraiser::UniqueIdentifierTable *v19; // r8
  unsigned __int64 v20; // r15
  unsigned __int16 **v21; // rax
  unsigned __int16 *v22; // r10
  const unsigned __int16 **v23; // rax
  const unsigned __int16 *v24; // r9
  const unsigned __int16 **v25; // r8
  unsigned __int64 v26; // rax
  _QWORD *v27; // rax
  struct Windows::Compat::Appraiser::MapTable *v29; // [rsp+28h] [rbp-C9h]
  const char *v30; // [rsp+30h] [rbp-C1h]
  const char *v31; // [rsp+38h] [rbp-B9h]
  HANDLE hHeap_8[2]; // [rsp+50h] [rbp-A1h] BYREF
  __int128 v33; // [rsp+60h] [rbp-91h]
  __int128 v34; // [rsp+70h] [rbp-81h]
  unsigned __int64 v35; // [rsp+80h] [rbp-71h]
  HANDLE v36[2]; // [rsp+88h] [rbp-69h] BYREF
  __int128 v37; // [rsp+98h] [rbp-59h]
  void *v38[2]; // [rsp+A8h] [rbp-49h]
  HANDLE v39[2]; // [rsp+B8h] [rbp-39h] BYREF
  __int128 v40; // [rsp+C8h] [rbp-29h]
  void *v41[2]; // [rsp+D8h] [rbp-19h]
  wchar_t *String1; // [rsp+E8h] [rbp-9h] BYREF
  wchar_t *v43; // [rsp+F0h] [rbp-1h] BYREF
  unsigned __int16 *v44[8]; // [rsp+F8h] [rbp+7h] BYREF

  v44[1] = (unsigned __int16 *)-2LL;
  v44[0] = 0;
  hHeap_8[0] = GetProcessHeap();
  v34 = 0x10u;
  v33 = 0;
  hHeap_8[1] = (HANDLE)8;
  v39[0] = GetProcessHeap();
  v41[0] = (void *)16;
  v40 = 0;
  v41[1] = 0;
  v39[1] = (HANDLE)8;
  v36[0] = GetProcessHeap();
  v38[0] = (void *)16;
  v37 = 0;
  v38[1] = 0;
  v36[1] = (HANDLE)8;
  v7 = RtlArray<Windows::Compat::Appraiser::IProperty *>::Initialize(hHeap_8);
  RequiredSingleValue = v7;
  v9 = "Failed to initialize RtlArray: [0x%x].";
  if ( v7 < 0 )
  {
    LODWORD(v31) = v7;
    v30 = "Failed to initialize RtlArray: [0x%x].";
    v10 = -91;
    goto LABEL_3;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xA5u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml_app.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::WriteBlockingMatchingInfos",
      "Failed to initialize RtlArray: [0x%x].",
      v7);
  RequiredSingleValue = RtlArray<Windows::Compat::Appraiser::IProperty *>::Initialize(v39);
  if ( RequiredSingleValue < 0 )
  {
    v10 = -90;
LABEL_8:
    LODWORD(v31) = RequiredSingleValue;
    LODWORD(v30) = (_DWORD)v9;
    goto LABEL_3;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xA6u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml_app.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::WriteBlockingMatchingInfos",
      "Failed to initialize RtlArray: [0x%x].",
      RequiredSingleValue);
  RequiredSingleValue = RtlArray<Windows::Compat::Appraiser::IProperty *>::Initialize(v36);
  if ( RequiredSingleValue < 0 )
  {
    v10 = -89;
    goto LABEL_8;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xA7u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml_app.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::WriteBlockingMatchingInfos",
      "Failed to initialize RtlArray: [0x%x].",
      RequiredSingleValue);
  v11 = 0;
  v35 = 0;
  if ( !a3[2] )
  {
LABEL_96:
    RequiredSingleValue = 0;
    goto LABEL_97;
  }
  while ( 1 )
  {
    v9 = "Error getting asset type: [0x%x].";
    String1 = 0;
    v43 = 0;
    if ( (_QWORD)v33 && is_mul_ok(v33, (unsigned __int64)hHeap_8[1]) )
    {
      memset_0(
        *((void **)&v34 + 1),
        ((unsigned __int64)v33 * (unsigned __int128)(unsigned __int64)hHeap_8[1]) >> 64,
        v33 * (__int128)hHeap_8[1]);
      *(_QWORD *)&v33 = 0;
    }
    if ( (_QWORD)v40 && is_mul_ok(v40, (unsigned __int64)v39[1]) )
    {
      memset_0(
        v41[1],
        ((unsigned __int64)v40 * (unsigned __int128)(unsigned __int64)v39[1]) >> 64,
        v40 * (__int128)v39[1]);
      *(_QWORD *)&v40 = 0;
    }
    if ( (_QWORD)v37 && is_mul_ok(v37, (unsigned __int64)v36[1]) )
    {
      memset_0(
        v38[1],
        ((unsigned __int64)v37 * (unsigned __int128)(unsigned __int64)v36[1]) >> 64,
        v37 * (__int128)v36[1]);
      *(_QWORD *)&v37 = 0;
    }
    v12 = 0;
    if ( v11 < a3[2] )
    {
      v13 = a3[1] * v11;
      if ( !is_mul_ok(a3[1], v11) || (v14 = a3[5], v12 = (_QWORD *)(v14 + v13), v14 + v13 < v14) )
        v12 = 0;
    }
    RequiredSingleValue = Windows::Compat::Appraiser::AssetUtils::GetRequiredSingleValue(
                            &String1,
                            L"AssetType",
                            *v12,
                            1);
    if ( RequiredSingleValue < 0 )
    {
      v10 = -77;
      goto LABEL_8;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xB3u,
        "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml_app.cpp",
        "Windows::Compat::Appraiser::SetupXmlOutputter::WriteBlockingMatchingInfos",
        "Error getting asset type: [0x%x].",
        RequiredSingleValue);
    v15 = String1;
    if ( !wcscmp_0(String1, L"BlockingMatchingInfo") || !wcscmp_0(v15, L"BlockingMatchingInfoEntry") )
    {
      v16 = 0;
      if ( v35 < a3[2] )
      {
        if ( !is_mul_ok(a3[1], v35)
          || (v16 = (struct Windows::Compat::Appraiser::IAsset **)(a3[5] + a3[1] * v35), (unsigned __int64)v16 < a3[5]) )
        {
          v16 = 0;
        }
      }
      v17 = *v16;
      RequiredSingleValue = Windows::Compat::Appraiser::AssetUtils::GetSingleValue(
                              &v43,
                              L"DT_ORD_FIL_DisplayAsGenericHardware",
                              *v16,
                              4);
      if ( RequiredSingleValue < 0 )
      {
        LODWORD(v31) = RequiredSingleValue;
        v30 = "Failed to get value: [0x%x].";
        v10 = -70;
        goto LABEL_3;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xBAu,
          "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml_app.cpp",
          "Windows::Compat::Appraiser::SetupXmlOutputter::WriteBlockingMatchingInfos",
          "Failed to get value: [0x%x].",
          RequiredSingleValue);
      if ( !v43 )
      {
        RequiredSingleValue = -2147467259;
        LODWORD(v29) = -2147467259;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          191,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\setupxml_app.cpp",
          "Windows::Compat::Appraiser::SetupXmlOutputter::WriteBlockingMatchingInfos",
          (const char *)v29,
          (int)"Asset was missing DisplayAsGenericHardware decision.",
          v31);
        goto LABEL_97;
      }
      if ( v17 && wcscmp_0(v43, L"TRUE") )
        break;
    }
LABEL_95:
    v11 = v35 + 1;
    v35 = v11;
    if ( v11 >= a3[2] )
      goto LABEL_96;
  }
  RequiredSingleValue = Windows::Compat::Appraiser::AssetUtils::GetAllHyperlinkInfoAndNamedInfo(
                          (int)hHeap_8,
                          (int)v39,
                          (int)v36,
                          (int)v17,
                          a5,
                          a6);
  if ( RequiredSingleValue < 0 )
  {
    LODWORD(v31) = RequiredSingleValue;
    v30 = "Error getting app hyperlink target and text from matching info block asset: [0x%x].";
    v10 = -52;
    goto LABEL_3;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xCCu,
      "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml_app.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::WriteBlockingMatchingInfos",
      "Error getting app hyperlink target and text from matching info block asset: [0x%x].",
      RequiredSingleValue);
  if ( wcscmp_0(v15, L"BlockingMatchingInfo") )
  {
    if ( (_QWORD)v33 )
    {
      RequiredSingleValue = Windows::Compat::Appraiser::AssetUtils::GetUniqueIdentifier(
                              (const unsigned __int16 **)v44,
                              v18,
                              v19,
                              v17);
      if ( RequiredSingleValue < 0 )
      {
        LODWORD(v31) = RequiredSingleValue;
        v30 = "Error getting unique id: [0x%x].";
        v10 = -39;
        goto LABEL_3;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xD9u,
          "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml_app.cpp",
          "Windows::Compat::Appraiser::SetupXmlOutputter::WriteBlockingMatchingInfos",
          "Error getting unique id: [0x%x].",
          RequiredSingleValue);
      RequiredSingleValue = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, const wchar_t *, _QWORD))a2->lpVtbl->WriteStartElement)(
                              a2,
                              0,
                              L"Program",
                              0);
      if ( RequiredSingleValue < 0 )
      {
        LODWORD(v31) = RequiredSingleValue;
        v30 = "Failed to start Program node: [0x%x].";
        v10 = -36;
        goto LABEL_3;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xDCu,
          "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml_app.cpp",
          "Windows::Compat::Appraiser::SetupXmlOutputter::WriteBlockingMatchingInfos",
          "Failed to start Program node: [0x%x].",
          RequiredSingleValue);
      v27 = 0;
      if ( (_QWORD)v33 )
      {
        if ( is_mul_ok((unsigned __int64)hHeap_8[1], 0) )
          v27 = (_QWORD *)*((_QWORD *)&v34 + 1);
        else
          v27 = 0;
      }
      RequiredSingleValue = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, const wchar_t *, _QWORD, _QWORD))a2->lpVtbl->WriteAttributeString)(
                              a2,
                              0,
                              L"Name",
                              0,
                              *v27);
      if ( RequiredSingleValue < 0 )
      {
        LODWORD(v31) = RequiredSingleValue;
        v30 = "Failed to write name attribute: [0x%x].";
        v10 = -33;
        goto LABEL_3;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xDFu,
          "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml_app.cpp",
          "Windows::Compat::Appraiser::SetupXmlOutputter::WriteBlockingMatchingInfos",
          "Failed to write name attribute: [0x%x].",
          RequiredSingleValue);
      RequiredSingleValue = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, const wchar_t *, _QWORD, unsigned __int16 *))a2->lpVtbl->WriteAttributeString)(
                              a2,
                              0,
                              L"Id",
                              0,
                              v44[0]);
      if ( RequiredSingleValue < 0 )
      {
        LODWORD(v31) = RequiredSingleValue;
        v30 = "Failed to write id attribute: [0x%x].";
        v10 = -30;
        goto LABEL_3;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xE2u,
          "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml_app.cpp",
          "Windows::Compat::Appraiser::SetupXmlOutputter::WriteBlockingMatchingInfos",
          "Failed to write id attribute: [0x%x].",
          RequiredSingleValue);
      RequiredSingleValue = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, const wchar_t *, _QWORD, const wchar_t *))a2->lpVtbl->WriteAttributeString)(
                              a2,
                              0,
                              L"DefaultIcon",
                              0,
                              L"True");
      if ( RequiredSingleValue < 0 )
      {
        LODWORD(v31) = RequiredSingleValue;
        v30 = "Error writing attribute for icon: [0x%x].";
        v10 = -27;
        goto LABEL_3;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xE5u,
          "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml_app.cpp",
          "Windows::Compat::Appraiser::SetupXmlOutputter::WriteBlockingMatchingInfos",
          "Error writing attribute for icon: [0x%x].",
          RequiredSingleValue);
      RequiredSingleValue = Windows::Compat::Appraiser::SetupXmlOutputter::WriteProgramCompatInfo(a2, v17, 0, a5, a6);
      if ( RequiredSingleValue < 0 )
      {
        LODWORD(v31) = RequiredSingleValue;
        v30 = "Failed to write orphan program compat info: [0x%x].";
        v10 = -24;
        goto LABEL_3;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xE8u,
          "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml_app.cpp",
          "Windows::Compat::Appraiser::SetupXmlOutputter::WriteBlockingMatchingInfos",
          "Failed to write orphan program compat info: [0x%x].",
          RequiredSingleValue);
      RequiredSingleValue = Windows::Compat::Appraiser::SetupXmlOutputter::WriteProgramAction(a1, a2, v17, a4);
      if ( RequiredSingleValue < 0 )
      {
        LODWORD(v31) = RequiredSingleValue;
        v30 = "Failed to write program action: [0x%x].";
        v10 = -21;
        goto LABEL_3;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xEBu,
          "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml_app.cpp",
          "Windows::Compat::Appraiser::SetupXmlOutputter::WriteBlockingMatchingInfos",
          "Failed to write program action: [0x%x].",
          RequiredSingleValue);
      RequiredSingleValue = ((__int64 (__fastcall *)(struct IXmlWriter *))a2->lpVtbl->WriteEndElement)(a2);
      if ( RequiredSingleValue < 0 )
      {
        LODWORD(v31) = RequiredSingleValue;
        v30 = "Failed to end Program node: [0x%x].";
        v10 = -18;
        goto LABEL_3;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xEEu,
          "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml_app.cpp",
          "Windows::Compat::Appraiser::SetupXmlOutputter::WriteBlockingMatchingInfos",
          "Failed to end Program node: [0x%x].",
          RequiredSingleValue);
    }
    goto LABEL_95;
  }
  v20 = 0;
  if ( !(_QWORD)v33 )
    goto LABEL_95;
  while ( 1 )
  {
    v21 = 0;
    if ( v20 < (unsigned __int64)v37 )
    {
      if ( !is_mul_ok((unsigned __int64)v36[1], v20)
        || (v21 = (unsigned __int16 **)((char *)v38[1] + (unsigned __int64)v36[1] * v20), v21 < v38[1]) )
      {
        v21 = 0;
      }
    }
    v22 = *v21;
    v23 = 0;
    if ( v20 < (unsigned __int64)v40 )
    {
      if ( !is_mul_ok((unsigned __int64)v39[1], v20)
        || (v23 = (const unsigned __int16 **)((char *)v41[1] + (unsigned __int64)v39[1] * v20), v23 < v41[1]) )
      {
        v23 = 0;
      }
    }
    v24 = *v23;
    v25 = 0;
    if ( v20 < (unsigned __int64)v33 )
    {
      v26 = (unsigned __int64)hHeap_8[1] * v20;
      if ( !is_mul_ok((unsigned __int64)hHeap_8[1], v20)
        || (v25 = (const unsigned __int16 **)(*((_QWORD *)&v34 + 1) + v26),
            *((_QWORD *)&v34 + 1) + v26 < *((_QWORD *)&v34 + 1)) )
      {
        v25 = 0;
      }
    }
    RequiredSingleValue = Windows::Compat::Appraiser::SetupXmlOutputter::WriteManualBlockingProgram(
                            a1,
                            a2,
                            *v25,
                            v24,
                            v22);
    if ( RequiredSingleValue < 0 )
      break;
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xD3u,
        "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml_app.cpp",
        "Windows::Compat::Appraiser::SetupXmlOutputter::WriteBlockingMatchingInfos",
        "Error writing manual blocking program: [0x%x].",
        RequiredSingleValue);
    if ( ++v20 >= (unsigned __int64)v33 )
      goto LABEL_95;
  }
  LODWORD(v31) = RequiredSingleValue;
  v30 = "Error writing manual blocking program: [0x%x].";
  v10 = -45;
LABEL_3:
  LODWORD(v29) = RequiredSingleValue;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    v10,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\setupxml_app.cpp",
    "Windows::Compat::Appraiser::SetupXmlOutputter::WriteBlockingMatchingInfos",
    (const char *)v29,
    (int)v30,
    v31);
LABEL_97:
  if ( *((_QWORD *)&v34 + 1) )
    HeapFree(hHeap_8[0], 0, *((LPVOID *)&v34 + 1));
  *(_OWORD *)hHeap_8 = 0;
  v33 = 0;
  v34 = 0;
  if ( v38[1] )
    HeapFree(v36[0], 0, v38[1]);
  *(_OWORD *)v36 = 0;
  v37 = 0;
  *(_OWORD *)v38 = 0;
  if ( v41[1] )
    HeapFree(v39[0], 0, v41[1]);
  *(_OWORD *)v39 = 0;
  v40 = 0;
  *(_OWORD *)v41 = 0;
  if ( *((_QWORD *)&v34 + 1) )
    HeapFree(hHeap_8[0], 0, *((LPVOID *)&v34 + 1));
  return (unsigned int)RequiredSingleValue;
}

```

## disassembly

```asm
0x1801117ec  mov     rax, rsp
0x1801117ef  mov     [rax+20h], r9
0x1801117f3  mov     [rax+10h], rdx
0x1801117f7  mov     [rax+8], rcx
0x1801117fb  push    rbp
0x1801117fc  push    rsi
0x1801117fd  push    rdi
0x1801117fe  push    r12
0x180111800  push    r13
0x180111802  push    r14
0x180111804  push    r15
0x180111806  lea     rbp, [rax-4Fh]
0x18011180a  sub     rsp, 100h
0x180111811  mov     [rbp+47h+var_38], 0FFFFFFFFFFFFFFFEh
0x180111819  mov     [rax+18h], rbx
0x18011181d  mov     r13, r8
0x180111820  mov     [rbp+47h+var_40], 0
0x180111828  xorps   xmm0, xmm0
0x18011182b  movups  xmmword ptr [rsp+130h+hHeap+8], xmm0
0x180111830  movups  [rsp+130h+var_E0+8], xmm0
0x180111835  movups  [rsp+130h+var_D0+8], xmm0
0x18011183a  call    cs:__imp_GetProcessHeap
0x180111840  mov     [rsp+130h+hHeap+8], rax
0x180111845  mov     edi, 10h
0x18011184a  mov     qword ptr [rsp+130h+var_D0+8], rdi
0x18011184f  xorps   xmm0, xmm0
0x180111852  movdqu  [rsp+130h+var_E0+8], xmm0
0x180111858  mov     [rbp+47h+lpMem], 0
0x180111860  lea     ebx, [rdi-8]
0x180111863  mov     qword ptr [rsp+130h+var_E0], rbx
0x180111868  movups  xmmword ptr [rbp+47h+var_80], xmm0
0x18011186c  movups  [rbp+47h+var_70], xmm0
0x180111870  movups  xmmword ptr [rbp+47h+var_60], xmm0
0x180111874  call    cs:__imp_GetProcessHeap
0x18011187a  mov     [rbp+47h+var_80], rax
0x18011187e  mov     [rbp+47h+var_60], rdi
0x180111882  xorps   xmm0, xmm0
0x180111885  movdqu  [rbp+47h+var_70], xmm0
0x18011188a  mov     [rbp+47h+var_60+8], 0
0x180111892  mov     [rbp+47h+var_80+8], rbx
0x180111896  movups  xmmword ptr [rbp+47h+var_B0], xmm0
0x18011189a  movups  [rbp+47h+var_A0], xmm0
0x18011189e  movups  xmmword ptr [rbp+47h+var_90], xmm0
0x1801118a2  call    cs:__imp_GetProcessHeap
0x1801118a8  mov     [rbp+47h+var_B0], rax
0x1801118ac  mov     [rbp+47h+var_90], rdi
0x1801118b0  xorps   xmm0, xmm0
0x1801118b3  movdqu  [rbp+47h+var_A0], xmm0
0x1801118b8  mov     [rbp+47h+var_90+8], 0
0x1801118c0  mov     [rbp+47h+var_B0+8], rbx
0x1801118c4  lea     rcx, [rsp+130h+hHeap+8]
0x1801118c9  call    ?Initialize@?$RtlArray@PEAVIProperty@Appraiser@Compat@Windows@@@@QEAAJ_K@Z; RtlArray<Windows::Compat::Appraiser::IProperty *>::Initialize(unsigned __int64)
0x1801118ce  mov     ebx, eax
0x1801118d0  lea     r15, aFailedToInitia_32; "Failed to initialize RtlArray: [0x%x]."
0x1801118d7  test    eax, eax
0x1801118d9  jns     short loc_180111908
0x1801118db  mov     [rsp+30h], eax; char *
0x1801118df  mov     [rsp+130h+var_108], r15; int
0x1801118e4  lea     r9, aWindowsCompatA_442; "Windows::Compat::Appraiser::SetupXmlOut"...
0x1801118eb  lea     r8, aOnecoreBaseApp_88; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1801118f2  mov     edx, 0A5h; bool
0x1801118f7  lea     ecx, [rdi-0Fh]; this
0x1801118fa  mov     dword ptr [rsp+130h+var_110], ebx; char *
0x1801118fe  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180111903  jmp     loc_180111FA4
0x180111908  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18011190e  mov     edi, 1
0x180111913  and     eax, edi
0x180111915  lea     rsi, aWindowsCompatA_442; "Windows::Compat::Appraiser::SetupXmlOut"...
0x18011191c  lea     r14, aOnecoreBaseApp_88; "onecore\\base\\appcompat\\appraiser\\ou"...
0x180111923  test    al, al
0x180111925  jz      short loc_18011193E
0x180111927  mov     dword ptr [rsp+130h+var_110], ebx
0x18011192b  mov     r9, r15; char *
0x18011192e  mov     r8, rsi; char *
0x180111931  mov     rdx, r14; char *
0x180111934  mov     ecx, 0A5h; unsigned int
0x180111939  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18011193e  lea     rcx, [rbp+47h+var_80]
0x180111942  call    ?Initialize@?$RtlArray@PEAVIProperty@Appraiser@Compat@Windows@@@@QEAAJ_K@Z; RtlArray<Windows::Compat::Appraiser::IProperty *>::Initialize(unsigned __int64)
0x180111947  mov     ebx, eax
0x180111949  test    eax, eax
0x18011194b  jns     short loc_180111965
0x18011194d  mov     edx, 0A6h
0x180111952  mov     [rsp+30h], ebx
0x180111956  mov     [rsp+130h+var_108], r15
0x18011195b  mov     r8, r14
0x18011195e  mov     r9, rsi
0x180111961  mov     ecx, edi
0x180111963  jmp     short loc_1801118FA
0x180111965  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18011196b  and     eax, edi
0x18011196d  test    al, al
0x18011196f  jz      short loc_180111988
0x180111971  mov     dword ptr [rsp+130h+var_110], ebx
0x180111975  mov     r9, r15; char *
0x180111978  mov     r8, rsi; char *
0x18011197b  mov     rdx, r14; char *
0x18011197e  mov     ecx, 0A6h; unsigned int
0x180111983  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180111988  lea     rcx, [rbp+47h+var_B0]
0x18011198c  call    ?Initialize@?$RtlArray@PEAVIProperty@Appraiser@Compat@Windows@@@@QEAAJ_K@Z; RtlArray<Windows::Compat::Appraiser::IProperty *>::Initialize(unsigned __int64)
0x180111991  mov     ebx, eax
0x180111993  test    eax, eax
0x180111995  jns     short loc_18011199E
0x180111997  mov     edx, 0A7h
0x18011199c  jmp     short loc_180111952
0x18011199e  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801119a4  and     eax, edi
0x1801119a6  test    al, al
0x1801119a8  jz      short loc_1801119C1
0x1801119aa  mov     dword ptr [rsp+130h+var_110], ebx
0x1801119ae  mov     r9, r15; char *
0x1801119b1  mov     r8, rsi; char *
0x1801119b4  mov     rdx, r14; char *
0x1801119b7  mov     ecx, 0A7h; unsigned int
0x1801119bc  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801119c1  xor     ebx, ebx
0x1801119c3  mov     [rbp+47h+var_B8], rbx
0x1801119c7  cmp     [r13+10h], rbx
0x1801119cb  jbe     loc_180111FA2
0x1801119d1  lea     r15, aErrorGettingAs_0; "Error getting asset type: [0x%x]."
0x1801119d8  mov     [rbp+47h+String1], 0
0x1801119e0  mov     [rbp+47h+var_48], 0
0x1801119e8  mov     rcx, qword ptr [rsp+130h+var_E0+8]
0x1801119ed  test    rcx, rcx
0x1801119f0  jz      short loc_180111A1D
0x1801119f2  mov     [rsp+130h+hHeap], 0
0x1801119fb  mov     rax, qword ptr [rsp+130h+var_E0]
0x180111a00  mul     rcx
0x180111a03  test    rdx, rdx
0x180111a06  jnz     short loc_180111A1D
0x180111a08  mov     r8, rax; Size
0x180111a0b  mov     rcx, [rbp+47h+lpMem]; void *
0x180111a0f  call    memset_0
0x180111a14  mov     qword ptr [rsp+130h+var_E0+8], 0
0x180111a1d  mov     rcx, qword ptr [rbp+47h+var_70]
0x180111a21  test    rcx, rcx
0x180111a24  jz      short loc_180111A4F
0x180111a26  mov     [rsp+130h+hHeap], 0
0x180111a2f  mov     rax, [rbp+47h+var_80+8]
0x180111a33  mul     rcx
0x180111a36  test    rdx, rdx
0x180111a39  jnz     short loc_180111A4F
0x180111a3b  mov     r8, rax; Size
0x180111a3e  mov     rcx, [rbp+47h+var_60+8]; void *
0x180111a42  call    memset_0
0x180111a47  mov     qword ptr [rbp+47h+var_70], 0
0x180111a4f  mov     rcx, qword ptr [rbp+47h+var_A0]
0x180111a53  test    rcx, rcx
0x180111a56  jz      short loc_180111A81
0x180111a58  mov     [rsp+130h+hHeap], 0
0x180111a61  mov     rax, [rbp+47h+var_B0+8]
0x180111a65  mul     rcx
0x180111a68  test    rdx, rdx
0x180111a6b  jnz     short loc_180111A81
0x180111a6d  mov     r8, rax; Size
0x180111a70  mov     rcx, [rbp+47h+var_90+8]; void *
0x180111a74  call    memset_0
0x180111a79  mov     qword ptr [rbp+47h+var_A0], 0
0x180111a81  xor     r8d, r8d
0x180111a84  cmp     rbx, [r13+10h]
0x180111a88  jnb     short loc_180111AA6
0x180111a8a  mov     rax, rbx
0x180111a8d  mul     qword ptr [r13+8]
0x180111a91  test    rdx, rdx
0x180111a94  jnz     short loc_180111AA3
0x180111a96  mov     rcx, [r13+28h]
0x180111a9a  lea     r8, [rcx+rax]
0x180111a9e  cmp     r8, rcx
0x180111aa1  jnb     short loc_180111AA6
0x180111aa3  xor     r8d, r8d
0x180111aa6  mov     r9d, edi
0x180111aa9  mov     r8, [r8]
0x180111aac  lea     rdx, aAssettype; "AssetType"
0x180111ab3  lea     rcx, [rbp+47h+String1]
0x180111ab7  call    ?GetRequiredSingleValue@AssetUtils@Appraiser@Compat@Windows@@SAJPEAPEBGPEBGPEAVIAsset@234@W4Tier@234@@Z; Windows::Compat::Appraiser::AssetUtils::GetRequiredSingleValue(ushort const * *,ushort const *,Windows::Compat::Appraiser::IAsset *,Windows::Compat::Appraiser::Tier)
0x180111abc  mov     ebx, eax
0x180111abe  test    eax, eax
0x180111ac0  js      loc_180112191
0x180111ac6  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180111acc  and     eax, edi
0x180111ace  test    al, al
0x180111ad0  jz      short loc_180111AE9
0x180111ad2  mov     dword ptr [rsp+130h+var_110], ebx
0x180111ad6  mov     r9, r15; char *
0x180111ad9  mov     r8, rsi; char *
0x180111adc  mov     rdx, r14; char *
0x180111adf  mov     ecx, 0B3h; unsigned int
0x180111ae4  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180111ae9  lea     rdx, aBlockingmatchi_1; "BlockingMatchingInfo"
0x180111af0  mov     r15, [rbp+47h+String1]
0x180111af4  mov     rcx, r15; String1
0x180111af7  call    wcscmp_0
0x180111afc  test    eax, eax
0x180111afe  jz      short loc_180111B17
0x180111b00  lea     rdx, aBlockingmatchi_0; "BlockingMatchingInfoEntry"
0x180111b07  mov     rcx, r15; String1
0x180111b0a  call    wcscmp_0
0x180111b0f  test    eax, eax
0x180111b11  jnz     loc_180111F8D
0x180111b17  xor     eax, eax
0x180111b19  mov     rcx, [rbp+47h+var_B8]
0x180111b1d  cmp     rcx, [r13+10h]
0x180111b21  jnb     short loc_180111B3B
0x180111b23  mov     rax, rcx
0x180111b26  mul     qword ptr [r13+8]
0x180111b2a  test    rdx, rdx
0x180111b2d  jnz     short loc_180111B39
0x180111b2f  add     rax, [r13+28h]
0x180111b33  cmp     rax, [r13+28h]
0x180111b37  jnb     short loc_180111B3B
0x180111b39  xor     eax, eax
0x180111b3b  mov     r12, [rax]
0x180111b3e  mov     r9d, 4
0x180111b44  mov     r8, r12
0x180111b47  lea     rdx, aDtOrdFilDispla; "DT_ORD_FIL_DisplayAsGenericHardware"
0x180111b4e  lea     rcx, [rbp+47h+var_48]
0x180111b52  call    ?GetSingleValue@AssetUtils@Appraiser@Compat@Windows@@SAJPEAPEBGPEBGPEAVIAsset@234@W4Tier@234@@Z; Windows::Compat::Appraiser::AssetUtils::GetSingleValue(ushort const * *,ushort const *,Windows::Compat::Appraiser::IAsset *,Windows::Compat::Appraiser::Tier)
0x180111b57  mov     ebx, eax
0x180111b59  test    eax, eax
0x180111b5b  js      loc_180112177
0x180111b61  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180111b67  and     eax, edi
0x180111b69  test    al, al
0x180111b6b  jz      short loc_180111B88
0x180111b6d  mov     dword ptr [rsp+130h+var_110], ebx
0x180111b71  lea     r9, aFailedToGetVal; "Failed to get value: [0x%x]."
0x180111b78  mov     r8, rsi; char *
0x180111b7b  mov     rdx, r14; char *
0x180111b7e  mov     ecx, 0BAh; unsigned int
0x180111b83  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180111b88  mov     rcx, [rbp+47h+var_48]; String1
0x180111b8c  test    rcx, rcx
0x180111b8f  jz      loc_18011214B
0x180111b95  test    r12, r12
0x180111b98  jz      loc_180111F8D
0x180111b9e  test    rcx, rcx
0x180111ba1  jz      loc_180111F8D
0x180111ba7  lea     rdx, aTrue_2; "TRUE"
0x180111bae  call    wcscmp_0
0x180111bb3  test    eax, eax
0x180111bb5  jz      loc_180111F8D
0x180111bbb  mov     rax, [rbp+47h+arg_28]
0x180111bbf  mov     [rsp+130h+var_108], rax; struct Windows::Compat::Appraiser::MapTable *
0x180111bc4  mov     rax, [rbp+47h+arg_20]
0x180111bc8  mov     [rsp+130h+var_110], rax; struct Windows::Compat::Appraiser::MapTable *
0x180111bcd  mov     r9, r12; int
0x180111bd0  lea     r8, [rbp+47h+var_B0]; int
0x180111bd4  lea     rdx, [rbp+47h+var_80]; int
0x180111bd8  lea     rcx, [rsp+130h+hHeap+8]; int
0x180111bdd  call    ?GetAllHyperlinkInfoAndNamedInfo@AssetUtils@Appraiser@Compat@Windows@@SAJAEAV?$RtlArray@PEBG@@00PEAVIAsset@234@PEAUMapTable@234@2@Z; Windows::Compat::Appraiser::AssetUtils::GetAllHyperlinkInfoAndNamedInfo(RtlArray<ushort const *> &,RtlArray<ushort const *> &,RtlArray<ushort const *> &,Windows::Compat::Appraiser::IAsset *,Windows::Compat::Appraiser::MapTable *,Windows::Compat::Appraiser::MapTable *)
0x180111be2  mov     ebx, eax
0x180111be4  test    eax, eax
0x180111be6  js      loc_180112131
0x180111bec  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180111bf2  and     eax, edi
0x180111bf4  test    al, al
0x180111bf6  jz      short loc_180111C13
0x180111bf8  mov     dword ptr [rsp+130h+var_110], ebx
0x180111bfc  lea     r9, aErrorGettingAp; "Error getting app hyperlink target and "...
0x180111c03  mov     r8, rsi; char *
0x180111c06  mov     rdx, r14; char *
0x180111c09  mov     ecx, 0CCh; unsigned int
0x180111c0e  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180111c13  lea     rdx, aBlockingmatchi_1; "BlockingMatchingInfo"
0x180111c1a  mov     rcx, r15; String1
0x180111c1d  call    wcscmp_0
0x180111c22  test    eax, eax
0x180111c24  jnz     loc_180111CFE
0x180111c2a  xor     r15d, r15d
0x180111c2d  cmp     qword ptr [rsp+130h+var_E0+8], r15
0x180111c32  jbe     loc_180111F8D
0x180111c38  xor     eax, eax
0x180111c3a  cmp     r15, qword ptr [rbp+47h+var_A0]
0x180111c3e  jnb     short loc_180111C58
0x180111c40  mov     rax, r15
0x180111c43  mul     [rbp+47h+var_B0+8]
0x180111c47  test    rdx, rdx
0x180111c4a  jnz     short loc_180111C56
0x180111c4c  add     rax, [rbp+47h+var_90+8]
0x180111c50  cmp     rax, [rbp+47h+var_90+8]
0x180111c54  jnb     short loc_180111C58
0x180111c56  xor     eax, eax
0x180111c58  mov     r10, [rax]
0x180111c5b  xor     eax, eax
0x180111c5d  cmp     r15, qword ptr [rbp+47h+var_70]
0x180111c61  jnb     short loc_180111C7B
0x180111c63  mov     rax, r15
0x180111c66  mul     [rbp+47h+var_80+8]
0x180111c6a  test    rdx, rdx
0x180111c6d  jnz     short loc_180111C79
0x180111c6f  add     rax, [rbp+47h+var_60+8]
0x180111c73  cmp     rax, [rbp+47h+var_60+8]
0x180111c77  jnb     short loc_180111C7B
0x180111c79  xor     eax, eax
0x180111c7b  mov     r9, [rax]; unsigned __int16 *
0x180111c7e  xor     r8d, r8d
0x180111c81  cmp     r15, qword ptr [rsp+130h+var_E0+8]
0x180111c86  jnb     short loc_180111CA5
  ... truncated ...
```
