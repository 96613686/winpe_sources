# Windows::Compat::Appraiser::InboxRequirementsDataSource::ApplyDataSource(Windows::Compat::Appraiser::IPropertyListEnumerator *,Windows::Compat::Appraiser::IPropertyAppender *)

- ea: `0x1801edcf0`
- end: `0x1801ee4da`
- name: `?ApplyDataSource@InboxRequirementsDataSource@Appraiser@Compat@Windows@@UEAAJPEAVIPropertyListEnumerator@234@PEAVIPropertyAppender@234@@Z`
- size: `2026`
- prototype: `int(Windows::Compat::Appraiser::InboxRequirementsDataSource *__hidden this, struct Windows::Compat::Appraiser::IPropertyListEnumerator *, struct Windows::Compat::Appraiser::IPropertyAppender *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x18002ebb8`
- `0x1800301d0`
- `0x180083094`
- `0x180083390`
- `0x180087348`
- `0x1800ad71c`
- `0x1801edcf0`
- `0x1802174cc`
- `0x18021f010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1801ee496`
- `KERNEL32!GetProcessHeap` at `0x1801ee4b3`
- `KERNEL32!GetProcessHeap` at `0x1801ee496`
- `KERNEL32!GetProcessHeap` at `0x1801ee4b3`
- `KERNEL32!HeapFree` at `0x1801ee4a4`
- `KERNEL32!HeapFree` at `0x1801ee4c1`
- `KERNEL32!HeapFree` at `0x1801ee4a4`
- `KERNEL32!HeapFree` at `0x1801ee4c1`

## string_xrefs

- `0x1801edf32`: `ReinstallUpgradeMessage`
- `0x1801ee136`: `ReinstallUpgradeMessage`
- `0x1801edf86`: `ReinstallUpgradeMessageStringPresent`
- `0x1801ee193`: `ReinstallUpgradeMessageStringPresent`
- `0x1801edd42`: `onecore\base\appcompat\appraiser\datasource\inboxcomponentrequirements.cpp`
- `0x1801edd79`: `onecore\base\appcompat\appraiser\datasource\inboxcomponentrequirements.cpp`
- `0x1801edf98`: `Failed to append reinstall upgrade message present property. result: [0x%x].`
- `0x1801edfb5`: `Failed to append reinstall upgrade message present property. result: [0x%x].`
- `0x1801ee1ae`: `Failed to append reinstall upgrade message present property. result: [0x%x].`
- `0x1801ee1cb`: `Failed to append reinstall upgrade message present property. result: [0x%x].`
- `0x1801edd49`: `Windows::Compat::Appraiser::InboxRequirementsDataSource::ApplyDataSource`
- `0x1801edd6d`: `Windows::Compat::Appraiser::InboxRequirementsDataSource::ApplyDataSource`
- `0x1801edf44`: `Failed to append reinstall upgrade message property. result: [0x%x].`
- `0x1801edf61`: `Failed to append reinstall upgrade message property. result: [0x%x].`
- `0x1801ee151`: `Failed to append reinstall upgrade message property. result: [0x%x].`
- `0x1801ee16e`: `Failed to append reinstall upgrade message property. result: [0x%x].`
- `0x1801ede69`: `String copy failed for %ls: [0x%x].`
- `0x1801edeb3`: `String copy failed for %ls: [0x%x].`
- `0x1801ee086`: `String copy failed for %ls: [0x%x].`
- `0x1801ee0ae`: `String copy failed for %ls: [0x%x].`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::InboxRequirementsDataSource::ApplyDataSource(
        Windows::Compat::Appraiser::InboxRequirementsDataSource *this,
        struct Windows::Compat::Appraiser::IPropertyListEnumerator *a2,
        struct Windows::Compat::Appraiser::IPropertyAppender *a3)
{
  int RequiredSingleValue; // eax
  int v6; // ebx
  unsigned int v7; // eax
  const unsigned __int16 *v8; // r8
  const char *v9; // r9
  char v10; // dl
  int v11; // eax
  char v12; // dl
  unsigned int v13; // eax
  const unsigned __int16 *v14; // r8
  int ResourceStringAlloc; // eax
  int v16; // eax
  int appended; // eax
  int v18; // eax
  int v19; // eax
  const unsigned __int16 *v20; // rdx
  int v21; // eax
  const unsigned __int16 *v22; // rdx
  int v23; // eax
  const unsigned __int16 *v24; // rdx
  int v25; // eax
  const unsigned __int16 *v26; // rdx
  int v27; // eax
  const unsigned __int16 *v28; // rdx
  int v29; // eax
  int v30; // eax
  void *v31; // rdi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v33; // rdi
  HANDLE v34; // rax
  char *v36; // [rsp+20h] [rbp-48h]
  const char *v37; // [rsp+28h] [rbp-40h]
  char *v38; // [rsp+30h] [rbp-38h]
  char *v39; // [rsp+30h] [rbp-38h]
  int v40; // [rsp+38h] [rbp-30h]
  wchar_t *String2; // [rsp+40h] [rbp-28h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-20h] BYREF
  unsigned __int16 *v43[3]; // [rsp+50h] [rbp-18h] BYREF
  unsigned int v44; // [rsp+C8h] [rbp+60h] BYREF

  String2 = 0;
  v43[0] = 0;
  lpMem = 0;
  RequiredSingleValue = Windows::Compat::Appraiser::AssetUtils::GetRequiredSingleValue(
                          (const unsigned __int16 **)&String2,
                          L"AssetType",
                          a2);
  v6 = RequiredSingleValue;
  if ( RequiredSingleValue < 0 )
  {
    LODWORD(v38) = RequiredSingleValue;
    LODWORD(v36) = RequiredSingleValue;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      132,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\inboxcomponentrequirements.cpp",
      "Windows::Compat::Appraiser::InboxRequirementsDataSource::ApplyDataSource",
      v36,
      (int)"Failed to get asset type. result: [0x%x].",
      v38);
    return (unsigned int)v6;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x84u,
      "onecore\\base\\appcompat\\appraiser\\datasource\\inboxcomponentrequirements.cpp",
      "Windows::Compat::Appraiser::InboxRequirementsDataSource::ApplyDataSource",
      "Failed to get asset type. result: [0x%x].",
      RequiredSingleValue);
  if ( wcscmp_0(L"MediaCenter", String2) )
  {
LABEL_30:
    if ( wcscmp_0(L"Wmdrm", String2) )
      goto LABEL_52;
    v13 = (*(__int64 (__fastcall **)(struct Windows::Compat::Appraiser::IPropertyAppender *))(*(_QWORD *)a3 + 8LL))(a3);
    v14 = (const unsigned __int16 *)*((_QWORD *)this + 2);
    v44 = v13;
    if ( v14 )
    {
      ResourceStringAlloc = Windows::Compat::Appraiser::Utilities::ExtractResourceStringAlloc(v43, 0x4A7u, v14);
      v6 = ResourceStringAlloc;
      if ( ResourceStringAlloc < 0 )
      {
        LODWORD(v38) = ResourceStringAlloc;
        v10 = -86;
        v37 = "Failed to extract string from resource. result: [0x%x].";
        goto LABEL_10;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xAAu,
          "onecore\\base\\appcompat\\appraiser\\datasource\\inboxcomponentrequirements.cpp",
          "Windows::Compat::Appraiser::InboxRequirementsDataSource::ApplyDataSource",
          "Failed to extract string from resource. result: [0x%x].",
          ResourceStringAlloc);
      goto LABEL_40;
    }
    v16 = Windows::Compat::Appraiser::Utilities::CopyStringNonConstAlloc(v43, L"[TestWmdrmMessageText]");
    v6 = v16;
    if ( v16 >= 0 )
    {
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xAFu,
          "onecore\\base\\appcompat\\appraiser\\datasource\\inboxcomponentrequirements.cpp",
          "Windows::Compat::Appraiser::InboxRequirementsDataSource::ApplyDataSource",
          "String copy failed for %ls: [0x%x].",
          L"[TestWmdrmMessageText]",
          v16);
LABEL_40:
      appended = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                   L"ApplicableTargetVersion",
                   L"ALL",
                   &v44,
                   a3);
      v6 = appended;
      if ( appended < 0 )
      {
        LODWORD(v38) = appended;
        v10 = -77;
        v37 = "Error appending target version property: [0x%x].";
        goto LABEL_10;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xB3u,
          "onecore\\base\\appcompat\\appraiser\\datasource\\inboxcomponentrequirements.cpp",
          "Windows::Compat::Appraiser::InboxRequirementsDataSource::ApplyDataSource",
          "Error appending target version property: [0x%x].",
          appended);
      v18 = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(L"ReinstallUpgradeMessage", v43[0], &v44, a3);
      v6 = v18;
      if ( v18 < 0 )
      {
        LODWORD(v38) = v18;
        v10 = -74;
        v37 = "Failed to append reinstall upgrade message property. result: [0x%x].";
        goto LABEL_10;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xB6u,
          "onecore\\base\\appcompat\\appraiser\\datasource\\inboxcomponentrequirements.cpp",
          "Windows::Compat::Appraiser::InboxRequirementsDataSource::ApplyDataSource",
          "Failed to append reinstall upgrade message property. result: [0x%x].",
          v18);
      v19 = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
              L"ReinstallUpgradeMessageStringPresent",
              L"TRUE",
              &v44,
              a3);
      v6 = v19;
      if ( v19 < 0 )
      {
        LODWORD(v38) = v19;
        v10 = -71;
        v37 = "Failed to append reinstall upgrade message present property. result: [0x%x].";
        goto LABEL_10;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xB9u,
          "onecore\\base\\appcompat\\appraiser\\datasource\\inboxcomponentrequirements.cpp",
          "Windows::Compat::Appraiser::InboxRequirementsDataSource::ApplyDataSource",
          "Failed to append reinstall upgrade message present property. result: [0x%x].",
          v19);
LABEL_52:
      if ( !wcscmp_0(L"GatedState", String2) && *((_BYTE *)this + 25) )
      {
        v44 = (*(__int64 (__fastcall **)(struct Windows::Compat::Appraiser::IPropertyAppender *))(*(_QWORD *)a3 + 8LL))(a3);
        v20 = L"TRUE";
        if ( !*(_BYTE *)(*((_QWORD *)this + 4) + 1LL) )
          v20 = L"FALSE";
        v21 = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(L"GatedStateIsSet", v20, &v44, a3);
        v6 = v21;
        if ( v21 < 0 )
        {
          LODWORD(v38) = v21;
          v10 = -59;
          v37 = "Failed to append gated info property. result: [0x%x].";
          goto LABEL_10;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0xC5u,
            "onecore\\base\\appcompat\\appraiser\\datasource\\inboxcomponentrequirements.cpp",
            "Windows::Compat::Appraiser::InboxRequirementsDataSource::ApplyDataSource",
            "Failed to append gated info property. result: [0x%x].",
            v21);
        v22 = L"TRUE";
        if ( !**((_BYTE **)this + 4) )
          v22 = L"FALSE";
        v23 = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(L"GatedStateIsTrusted", v22, &v44, a3);
        v6 = v23;
        if ( v23 < 0 )
        {
          LODWORD(v38) = v23;
          v10 = -53;
          v37 = "Failed to append gated info property. result: [0x%x].";
          goto LABEL_10;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0xCBu,
            "onecore\\base\\appcompat\\appraiser\\datasource\\inboxcomponentrequirements.cpp",
            "Windows::Compat::Appraiser::InboxRequirementsDataSource::ApplyDataSource",
            "Failed to append gated info property. result: [0x%x].",
            v23);
        v24 = L"TRUE";
        if ( !*(_BYTE *)(*((_QWORD *)this + 4) + 2LL) )
          v24 = L"FALSE";
        v25 = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(L"GatedStateIsGated", v24, &v44, a3);
        v6 = v25;
        if ( v25 < 0 )
        {
          LODWORD(v38) = v25;
          v10 = -47;
          v37 = "Failed to append gated info property. result: [0x%x].";
          goto LABEL_10;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0xD1u,
            "onecore\\base\\appcompat\\appraiser\\datasource\\inboxcomponentrequirements.cpp",
            "Windows::Compat::Appraiser::InboxRequirementsDataSource::ApplyDataSource",
            "Failed to append gated info property. result: [0x%x].",
            v25);
        v26 = L"TRUE";
        if ( !*(_BYTE *)(*((_QWORD *)this + 4) + 3LL) )
          v26 = L"FALSE";
        v27 = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                L"GatedStateNewScanImproves",
                v26,
                &v44,
                a3);
        v6 = v27;
        if ( v27 < 0 )
        {
          LODWORD(v38) = v27;
          v10 = -41;
          v37 = "Failed to append gated info property. result: [0x%x].";
          goto LABEL_10;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0xD7u,
            "onecore\\base\\appcompat\\appraiser\\datasource\\inboxcomponentrequirements.cpp",
            "Windows::Compat::Appraiser::InboxRequirementsDataSource::ApplyDataSource",
            "Failed to append gated info property. result: [0x%x].",
            v27);
        v28 = L"TRUE";
        if ( !*(_BYTE *)(*((_QWORD *)this + 4) + 4LL) )
          v28 = L"FALSE";
        v29 = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(L"GatedStateNewScanTrusted", v28, &v44, a3);
        v6 = v29;
        if ( v29 < 0 )
        {
          LODWORD(v38) = v29;
          v10 = -35;
          v37 = "Failed to append gated info property. result: [0x%x].";
          goto LABEL_10;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0xDDu,
            "onecore\\base\\appcompat\\appraiser\\datasource\\inboxcomponentrequirements.cpp",
            "Windows::Compat::Appraiser::InboxRequirementsDataSource::ApplyDataSource",
            "Failed to append gated info property. result: [0x%x].",
            v29);
        v30 = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                L"ApplicableTargetVersion",
                L"ALL",
                &v44,
                a3);
        v6 = v30;
        if ( v30 < 0 )
        {
          LODWORD(v38) = v30;
          v10 = -32;
          v37 = "Error appending target version property: [0x%x].";
          goto LABEL_10;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0xE0u,
            "onecore\\base\\appcompat\\appraiser\\datasource\\inboxcomponentrequirements.cpp",
            "Windows::Compat::Appraiser::InboxRequirementsDataSource::ApplyDataSource",
            "Error appending target version property: [0x%x].",
            v30);
      }
      v6 = 0;
      goto LABEL_89;
    }
    v40 = v16;
    v12 = -81;
    v39 = (char *)L"[TestWmdrmMessageText]";
LABEL_15:
    LODWORD(v36) = v6;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v12,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\inboxcomponentrequirements.cpp",
      "Windows::Compat::Appraiser::InboxRequirementsDataSource::ApplyDataSource",
      v36,
      (int)"String copy failed for %ls: [0x%x].",
      v39,
      v40);
    goto LABEL_89;
  }
  v7 = (*(__int64 (__fastcall **)(struct Windows::Compat::Appraiser::IPropertyAppender *))(*(_QWORD *)a3 + 8LL))(a3);
  v8 = (const unsigned __int16 *)*((_QWORD *)this + 2);
  v44 = v7;
  if ( !v8 )
  {
    v11 = Windows::Compat::Appraiser::Utilities::CopyStringNonConstAlloc(
            (unsigned __int16 **)&lpMem,
            L"[TestMediaCenterMessage]");
    v6 = v11;
    if ( v11 < 0 )
    {
      v40 = v11;
      v12 = -108;
      v39 = (char *)L"[TestMediaCenterMessage]";
      goto LABEL_15;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x94u,
        "onecore\\base\\appcompat\\appraiser\\datasource\\inboxcomponentrequirements.cpp",
        "Windows::Compat::Appraiser::InboxRequirementsDataSource::ApplyDataSource",
        "String copy failed for %ls: [0x%x].",
        (const wchar_t *)L"[TestMediaCenterMessage]",
        v11);
    goto LABEL_18;
  }
  v6 = Windows::Compat::Appraiser::Utilities::ExtractResourceStringAlloc(
         (unsigned __int16 **)&lpMem,
         (unsigned int)(*((_BYTE *)this + 24) != 0) + 1217,
         v8);
  if ( v6 >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x8Fu,
        "onecore\\base\\appcompat\\appraiser\\datasource\\inboxcomponentrequirements.cpp",
        "Windows::Compat::Appraiser::InboxRequirementsDataSource::ApplyDataSource",
        "Failed to extract string from resource. result: [0x%x].",
        v6);
LABEL_18:
    v6 = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(L"ApplicableTargetVersion", L"ALL", &v44, a3);
    if ( v6 < 0 )
    {
      v9 = "Error appending target version property: [0x%x].";
      v10 = -104;
      goto LABEL_9;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x98u,
        "onecore\\base\\appcompat\\appraiser\\datasource\\inboxcomponentrequirements.cpp",
        "Windows::Compat::Appraiser::InboxRequirementsDataSource::ApplyDataSource",
        "Error appending target version property: [0x%x].",
        v6);
    v6 = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
           L"ReinstallUpgradeMessage",
           (const unsigned __int16 *)lpMem,
           &v44,
           a3);
    if ( v6 < 0 )
    {
      v9 = "Failed to append reinstall upgrade message property. result: [0x%x].";
      v10 = -101;
      goto LABEL_9;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x9Bu,
        "onecore\\base\\appcompat\\appraiser\\datasource\\inboxcomponentrequirements.cpp",
        "Windows::Compat::Appraiser::InboxRequirementsDataSource::ApplyDataSource",
        "Failed to append reinstall upgrade message property. result: [0x%x].",
        v6);
    v6 = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
           L"ReinstallUpgradeMessageStringPresent",
           L"TRUE",
           &v44,
           a3);
    if ( v6 < 0 )
    {
      v9 = "Failed to append reinstall upgrade message present property. result: [0x%x].";
      v10 = -98;
      goto LABEL_9;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x9Eu,
        "onecore\\base\\appcompat\\appraiser\\datasource\\inboxcomponentrequirements.cpp",
        "Windows::Compat::Appraiser::InboxRequirementsDataSource::ApplyDataSource",
        "Failed to append reinstall upgrade message present property. result: [0x%x].",
        v6);
    goto LABEL_30;
  }
  v9 = "Failed to extract string from resource. result: [0x%x].";
  v10 = -113;
LABEL_9:
  LODWORD(v38) = v6;
  LODWORD(v37) = (_DWORD)v9;
LABEL_10:
  LODWORD(v36) = v6;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    v10,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\inboxcomponentrequirements.cpp",
    "Windows::Compat::Appraiser::InboxRequirementsDataSource::ApplyDataSource",
    v36,
    (int)v37,
    v38);
LABEL_89:
  v31 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v31);
  }
  v33 = v43[0];
  if ( v43[0] )
  {
    v34 = GetProcessHeap();
    HeapFree(v34, 0, v33);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801edcf0  push    rbp
0x1801edcf2  push    rbx
0x1801edcf3  push    rsi
0x1801edcf4  push    rdi
0x1801edcf5  push    r12
0x1801edcf7  push    r13
0x1801edcf9  push    r14
0x1801edcfb  push    r15
0x1801edcfd  mov     rbp, rsp
0x1801edd00  sub     rsp, 68h
0x1801edd04  xor     r15d, r15d
0x1801edd07  mov     r12, r8
0x1801edd0a  mov     r8, rdx; struct Windows::Compat::Appraiser::IPropertyListEnumerator *
0x1801edd0d  mov     [rbp+String2], r15
0x1801edd11  mov     r13, rcx
0x1801edd14  mov     [rbp+var_18], r15
0x1801edd18  lea     rdx, aAssettype; "AssetType"
0x1801edd1f  mov     [rbp+lpMem], r15
0x1801edd23  lea     rcx, [rbp+String2]; unsigned __int16 **
0x1801edd27  call    ?GetRequiredSingleValue@AssetUtils@Appraiser@Compat@Windows@@SAJPEAPEBGPEBGPEAVIPropertyListEnumerator@234@@Z; Windows::Compat::Appraiser::AssetUtils::GetRequiredSingleValue(ushort const * *,ushort const *,Windows::Compat::Appraiser::IPropertyListEnumerator *)
0x1801edd2c  mov     ebx, eax
0x1801edd2e  test    eax, eax
0x1801edd30  jns     short loc_1801EDD67
0x1801edd32  mov     dword ptr [rsp+68h+var_38], eax; char *
0x1801edd36  lea     r9, aFailedToGetAss_2; "Failed to get asset type. result: [0x%x"...
0x1801edd3d  mov     qword ptr [rsp+68h+var_40], r9; int
0x1801edd42  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appcompat\\appraiser\\da"...
0x1801edd49  lea     r9, aWindowsCompatA_375; "Windows::Compat::Appraiser::InboxRequir"...
0x1801edd50  mov     dword ptr [rsp+68h+var_48], eax; char *
0x1801edd54  mov     edx, 84h; bool
0x1801edd59  lea     ecx, [r15+1]; this
0x1801edd5d  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1801edd62  jmp     loc_1801EE4C7
0x1801edd67  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801edd6d  lea     rsi, aWindowsCompatA_375; "Windows::Compat::Appraiser::InboxRequir"...
0x1801edd74  mov     edi, 1
0x1801edd79  lea     r14, aOnecoreBaseApp_17; "onecore\\base\\appcompat\\appraiser\\da"...
0x1801edd80  and     eax, edi
0x1801edd82  test    al, al
0x1801edd84  jz      short loc_1801EDDA1
0x1801edd86  lea     r9, aFailedToGetAss_2; "Failed to get asset type. result: [0x%x"...
0x1801edd8d  mov     dword ptr [rsp+68h+var_48], ebx
0x1801edd91  mov     r8, rsi; char *
0x1801edd94  mov     rdx, r14; char *
0x1801edd97  mov     ecx, 84h; unsigned int
0x1801edd9c  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801edda1  mov     rdx, [rbp+String2]; String2
0x1801edda5  lea     rcx, aMediacenter; "MediaCenter"
0x1801eddac  call    wcscmp_0
0x1801eddb1  lea     r15, aTrue_2; "TRUE"
0x1801eddb8  test    eax, eax
0x1801eddba  jnz     loc_1801EDFD0
0x1801eddc0  mov     rax, [r12]
0x1801eddc4  mov     rcx, r12
0x1801eddc7  mov     rax, [rax+8]
0x1801eddcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eddd0  mov     r8, [r13+10h]; unsigned __int16 *
0x1801eddd4  lea     rcx, [rbp+lpMem]; unsigned __int16 **
0x1801eddd8  mov     [rbp+arg_18], eax
0x1801edddb  test    r8, r8
0x1801eddde  jz      short loc_1801EDE53
0x1801edde0  mov     al, [r13+18h]
0x1801edde4  neg     al
0x1801edde6  sbb     edx, edx
0x1801edde8  neg     edx
0x1801eddea  add     edx, 4C1h; unsigned int
0x1801eddf0  call    ?ExtractResourceStringAlloc@Utilities@Appraiser@Compat@Windows@@SAJPEAPEAGKPEBG@Z; Windows::Compat::Appraiser::Utilities::ExtractResourceStringAlloc(ushort * *,ulong,ushort const *)
0x1801eddf5  mov     ebx, eax
0x1801eddf7  test    eax, eax
0x1801eddf9  jns     short loc_1801EDE26
0x1801eddfb  lea     r9, aFailedToExtrac; "Failed to extract string from resource."...
0x1801ede02  mov     edx, 8Fh; bool
0x1801ede07  mov     dword ptr [rsp+68h+var_38], ebx; char *
0x1801ede0b  mov     qword ptr [rsp+68h+var_40], r9; int
0x1801ede10  mov     r8, r14; unsigned int
0x1801ede13  mov     dword ptr [rsp+68h+var_48], ebx; char *
0x1801ede17  mov     r9, rsi; char *
0x1801ede1a  mov     ecx, edi; this
0x1801ede1c  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1801ede21  jmp     loc_1801EE48D
0x1801ede26  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801ede2c  and     eax, edi
0x1801ede2e  test    al, al
0x1801ede30  jz      loc_1801EDECF
0x1801ede36  lea     r9, aFailedToExtrac; "Failed to extract string from resource."...
0x1801ede3d  mov     dword ptr [rsp+68h+var_48], ebx
0x1801ede41  mov     r8, rsi; char *
0x1801ede44  mov     rdx, r14; char *
0x1801ede47  mov     ecx, 8Fh; unsigned int
0x1801ede4c  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801ede51  jmp     short loc_1801EDECF
0x1801ede53  lea     rdx, aTestmediacente_0; "[TestMediaCenterMessage]"
0x1801ede5a  call    ?CopyStringNonConstAlloc@Utilities@Appraiser@Compat@Windows@@SAJPEAPEAGPEBG@Z; Windows::Compat::Appraiser::Utilities::CopyStringNonConstAlloc(ushort * *,ushort const *)
0x1801ede5f  mov     ebx, eax
0x1801ede61  test    eax, eax
0x1801ede63  jns     short loc_1801EDE9C
0x1801ede65  mov     [rsp+68h+var_30], eax
0x1801ede69  lea     r9, aStringCopyFail_1; "String copy failed for %ls: [0x%x]."
0x1801ede70  lea     rax, aTestmediacente_0; "[TestMediaCenterMessage]"
0x1801ede77  mov     edx, 94h; bool
0x1801ede7c  mov     [rsp+68h+var_38], rax; char *
0x1801ede81  mov     qword ptr [rsp+68h+var_40], r9; int
0x1801ede86  mov     r8, r14; unsigned int
0x1801ede89  mov     dword ptr [rsp+68h+var_48], ebx; char *
0x1801ede8d  mov     r9, rsi; char *
0x1801ede90  mov     ecx, edi; this
0x1801ede92  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1801ede97  jmp     loc_1801EE48D
0x1801ede9c  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801edea2  and     eax, edi
0x1801edea4  test    al, al
0x1801edea6  jz      short loc_1801EDECF
0x1801edea8  lea     rax, aTestmediacente_0; "[TestMediaCenterMessage]"
0x1801edeaf  mov     [rsp+68h+var_40], ebx
0x1801edeb3  lea     r9, aStringCopyFail_1; "String copy failed for %ls: [0x%x]."
0x1801edeba  mov     [rsp+68h+var_48], rax
0x1801edebf  mov     r8, rsi; char *
0x1801edec2  mov     rdx, r14; char *
0x1801edec5  mov     ecx, 94h; unsigned int
0x1801edeca  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801edecf  mov     r9, r12; struct Windows::Compat::Appraiser::IPropertyAppender *
0x1801eded2  lea     r8, [rbp+arg_18]; unsigned int *
0x1801eded6  lea     rdx, aAll; "ALL"
0x1801ededd  lea     rcx, aApplicabletarg_0; "ApplicableTargetVersion"
0x1801edee4  call    ?CreateAndAppendProperty@Utilities@Appraiser@Compat@Windows@@SAJPEBG0PEAKPEAVIPropertyAppender@234@@Z; Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(ushort const *,ushort const *,ulong *,Windows::Compat::Appraiser::IPropertyAppender *)
0x1801edee9  mov     ebx, eax
0x1801edeeb  test    eax, eax
0x1801edeed  jns     short loc_1801EDF00
0x1801edeef  lea     r9, aErrorAppending_13; "Error appending target version property"...
0x1801edef6  mov     edx, 98h
0x1801edefb  jmp     loc_1801EDE07
0x1801edf00  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801edf06  and     eax, edi
0x1801edf08  test    al, al
0x1801edf0a  jz      short loc_1801EDF27
0x1801edf0c  lea     r9, aErrorAppending_13; "Error appending target version property"...
0x1801edf13  mov     dword ptr [rsp+68h+var_48], ebx
0x1801edf17  mov     r8, rsi; char *
0x1801edf1a  mov     rdx, r14; char *
0x1801edf1d  mov     ecx, 98h; unsigned int
0x1801edf22  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801edf27  mov     rdx, [rbp+lpMem]; unsigned __int16 *
0x1801edf2b  lea     r8, [rbp+arg_18]; unsigned int *
0x1801edf2f  mov     r9, r12; struct Windows::Compat::Appraiser::IPropertyAppender *
0x1801edf32  lea     rcx, aReinstallupgra_3; "ReinstallUpgradeMessage"
0x1801edf39  call    ?CreateAndAppendProperty@Utilities@Appraiser@Compat@Windows@@SAJPEBG0PEAKPEAVIPropertyAppender@234@@Z; Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(ushort const *,ushort const *,ulong *,Windows::Compat::Appraiser::IPropertyAppender *)
0x1801edf3e  mov     ebx, eax
0x1801edf40  test    eax, eax
0x1801edf42  jns     short loc_1801EDF55
0x1801edf44  lea     r9, aFailedToAppend_77; "Failed to append reinstall upgrade mess"...
0x1801edf4b  mov     edx, 9Bh
0x1801edf50  jmp     loc_1801EDE07
0x1801edf55  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801edf5b  and     eax, edi
0x1801edf5d  test    al, al
0x1801edf5f  jz      short loc_1801EDF7C
0x1801edf61  lea     r9, aFailedToAppend_77; "Failed to append reinstall upgrade mess"...
0x1801edf68  mov     dword ptr [rsp+68h+var_48], ebx
0x1801edf6c  mov     r8, rsi; char *
0x1801edf6f  mov     rdx, r14; char *
0x1801edf72  mov     ecx, 9Bh; unsigned int
0x1801edf77  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801edf7c  mov     r9, r12; struct Windows::Compat::Appraiser::IPropertyAppender *
0x1801edf7f  lea     r8, [rbp+arg_18]; unsigned int *
0x1801edf83  mov     rdx, r15; unsigned __int16 *
0x1801edf86  lea     rcx, aReinstallupgra_0; "ReinstallUpgradeMessageStringPresent"
0x1801edf8d  call    ?CreateAndAppendProperty@Utilities@Appraiser@Compat@Windows@@SAJPEBG0PEAKPEAVIPropertyAppender@234@@Z; Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(ushort const *,ushort const *,ulong *,Windows::Compat::Appraiser::IPropertyAppender *)
0x1801edf92  mov     ebx, eax
0x1801edf94  test    eax, eax
0x1801edf96  jns     short loc_1801EDFA9
0x1801edf98  lea     r9, aFailedToAppend_100; "Failed to append reinstall upgrade mess"...
0x1801edf9f  mov     edx, 9Eh
0x1801edfa4  jmp     loc_1801EDE07
0x1801edfa9  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801edfaf  and     eax, edi
0x1801edfb1  test    al, al
0x1801edfb3  jz      short loc_1801EDFD0
0x1801edfb5  lea     r9, aFailedToAppend_100; "Failed to append reinstall upgrade mess"...
0x1801edfbc  mov     dword ptr [rsp+68h+var_48], ebx
0x1801edfc0  mov     r8, rsi; char *
0x1801edfc3  mov     rdx, r14; char *
0x1801edfc6  mov     ecx, 9Eh; unsigned int
0x1801edfcb  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801edfd0  mov     rdx, [rbp+String2]; String2
0x1801edfd4  lea     rcx, aWmdrm; "Wmdrm"
0x1801edfdb  call    wcscmp_0
0x1801edfe0  test    eax, eax
0x1801edfe2  jnz     loc_1801EE1E6
0x1801edfe8  mov     rax, [r12]
0x1801edfec  mov     rcx, r12
0x1801edfef  mov     rax, [rax+8]
0x1801edff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801edff8  mov     r8, [r13+10h]; unsigned __int16 *
0x1801edffc  lea     rcx, [rbp+var_18]; unsigned __int16 **
0x1801ee000  mov     [rbp+arg_18], eax
0x1801ee003  test    r8, r8
0x1801ee006  jz      short loc_1801EE05F
0x1801ee008  mov     edx, 4A7h; unsigned int
0x1801ee00d  call    ?ExtractResourceStringAlloc@Utilities@Appraiser@Compat@Windows@@SAJPEAPEAGKPEBG@Z; Windows::Compat::Appraiser::Utilities::ExtractResourceStringAlloc(ushort * *,ulong,ushort const *)
0x1801ee012  mov     ebx, eax
0x1801ee014  test    eax, eax
0x1801ee016  jns     short loc_1801EE032
0x1801ee018  mov     dword ptr [rsp+68h+var_38], eax
0x1801ee01c  mov     edx, 0AAh
0x1801ee021  lea     rax, aFailedToExtrac; "Failed to extract string from resource."...
0x1801ee028  mov     qword ptr [rsp+68h+var_40], rax
0x1801ee02d  jmp     loc_1801EDE10
0x1801ee032  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801ee038  and     eax, edi
0x1801ee03a  test    al, al
0x1801ee03c  jz      loc_1801EE0CA
0x1801ee042  lea     r9, aFailedToExtrac; "Failed to extract string from resource."...
0x1801ee049  mov     dword ptr [rsp+68h+var_48], ebx
0x1801ee04d  mov     r8, rsi; char *
0x1801ee050  mov     rdx, r14; char *
0x1801ee053  mov     ecx, 0AAh; unsigned int
0x1801ee058  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801ee05d  jmp     short loc_1801EE0CA
0x1801ee05f  lea     rdx, aTestwmdrmmessa; "[TestWmdrmMessageText]"
0x1801ee066  call    ?CopyStringNonConstAlloc@Utilities@Appraiser@Compat@Windows@@SAJPEAPEAGPEBG@Z; Windows::Compat::Appraiser::Utilities::CopyStringNonConstAlloc(ushort * *,ushort const *)
0x1801ee06b  mov     ebx, eax
0x1801ee06d  test    eax, eax
0x1801ee06f  jns     short loc_1801EE097
0x1801ee071  mov     [rsp+68h+var_30], eax
0x1801ee075  mov     edx, 0AFh
0x1801ee07a  lea     rax, aTestwmdrmmessa; "[TestWmdrmMessageText]"
0x1801ee081  mov     [rsp+68h+var_38], rax
0x1801ee086  lea     rax, aStringCopyFail_1; "String copy failed for %ls: [0x%x]."
0x1801ee08d  mov     qword ptr [rsp+68h+var_40], rax
0x1801ee092  jmp     loc_1801EDE86
0x1801ee097  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801ee09d  and     eax, edi
0x1801ee09f  test    al, al
0x1801ee0a1  jz      short loc_1801EE0CA
0x1801ee0a3  lea     rax, aTestwmdrmmessa; "[TestWmdrmMessageText]"
0x1801ee0aa  mov     [rsp+68h+var_40], ebx
0x1801ee0ae  lea     r9, aStringCopyFail_1; "String copy failed for %ls: [0x%x]."
0x1801ee0b5  mov     [rsp+68h+var_48], rax
0x1801ee0ba  mov     r8, rsi; char *
0x1801ee0bd  mov     rdx, r14; char *
0x1801ee0c0  mov     ecx, 0AFh; unsigned int
0x1801ee0c5  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801ee0ca  mov     r9, r12; struct Windows::Compat::Appraiser::IPropertyAppender *
0x1801ee0cd  lea     r8, [rbp+arg_18]; unsigned int *
0x1801ee0d1  lea     rdx, aAll; "ALL"
0x1801ee0d8  lea     rcx, aApplicabletarg_0; "ApplicableTargetVersion"
0x1801ee0df  call    ?CreateAndAppendProperty@Utilities@Appraiser@Compat@Windows@@SAJPEBG0PEAKPEAVIPropertyAppender@234@@Z; Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(ushort const *,ushort const *,ulong *,Windows::Compat::Appraiser::IPropertyAppender *)
0x1801ee0e4  mov     ebx, eax
0x1801ee0e6  test    eax, eax
0x1801ee0e8  jns     short loc_1801EE104
0x1801ee0ea  mov     dword ptr [rsp+68h+var_38], eax
0x1801ee0ee  mov     edx, 0B3h
0x1801ee0f3  lea     rax, aErrorAppending_13; "Error appending target version property"...
0x1801ee0fa  mov     qword ptr [rsp+68h+var_40], rax
0x1801ee0ff  jmp     loc_1801EDE10
0x1801ee104  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801ee10a  and     eax, edi
0x1801ee10c  test    al, al
0x1801ee10e  jz      short loc_1801EE12B
0x1801ee110  lea     r9, aErrorAppending_13; "Error appending target version property"...
0x1801ee117  mov     dword ptr [rsp+68h+var_48], ebx
0x1801ee11b  mov     r8, rsi; char *
0x1801ee11e  mov     rdx, r14; char *
0x1801ee121  mov     ecx, 0B3h; unsigned int
0x1801ee126  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801ee12b  mov     rdx, [rbp+var_18]; unsigned __int16 *
0x1801ee12f  lea     r8, [rbp+arg_18]; unsigned int *
0x1801ee133  mov     r9, r12; struct Windows::Compat::Appraiser::IPropertyAppender *
0x1801ee136  lea     rcx, aReinstallupgra_3; "ReinstallUpgradeMessage"
0x1801ee13d  call    ?CreateAndAppendProperty@Utilities@Appraiser@Compat@Windows@@SAJPEBG0PEAKPEAVIPropertyAppender@234@@Z; Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(ushort const *,ushort const *,ulong *,Windows::Compat::Appraiser::IPropertyAppender *)
0x1801ee142  mov     ebx, eax
0x1801ee144  test    eax, eax
0x1801ee146  jns     short loc_1801EE162
0x1801ee148  mov     dword ptr [rsp+68h+var_38], eax
0x1801ee14c  mov     edx, 0B6h
0x1801ee151  lea     rax, aFailedToAppend_77; "Failed to append reinstall upgrade mess"...
0x1801ee158  mov     qword ptr [rsp+68h+var_40], rax
0x1801ee15d  jmp     loc_1801EDE10
0x1801ee162  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801ee168  and     eax, edi
0x1801ee16a  test    al, al
0x1801ee16c  jz      short loc_1801EE189
0x1801ee16e  lea     r9, aFailedToAppend_77; "Failed to append reinstall upgrade mess"...
0x1801ee175  mov     dword ptr [rsp+68h+var_48], ebx
0x1801ee179  mov     r8, rsi; char *
0x1801ee17c  mov     rdx, r14; char *
0x1801ee17f  mov     ecx, 0B6h; unsigned int
0x1801ee184  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801ee189  mov     r9, r12; struct Windows::Compat::Appraiser::IPropertyAppender *
0x1801ee18c  lea     r8, [rbp+arg_18]; unsigned int *
0x1801ee190  mov     rdx, r15; unsigned __int16 *
0x1801ee193  lea     rcx, aReinstallupgra_0; "ReinstallUpgradeMessageStringPresent"
0x1801ee19a  call    ?CreateAndAppendProperty@Utilities@Appraiser@Compat@Windows@@SAJPEBG0PEAKPEAVIPropertyAppender@234@@Z; Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(ushort const *,ushort const *,ulong *,Windows::Compat::Appraiser::IPropertyAppender *)
0x1801ee19f  mov     ebx, eax
0x1801ee1a1  test    eax, eax
0x1801ee1a3  jns     short loc_1801EE1BF
0x1801ee1a5  mov     dword ptr [rsp+68h+var_38], eax
0x1801ee1a9  mov     edx, 0B9h
0x1801ee1ae  lea     rax, aFailedToAppend_100; "Failed to append reinstall upgrade mess"...
0x1801ee1b5  mov     qword ptr [rsp+68h+var_40], rax
  ... truncated ...
```
