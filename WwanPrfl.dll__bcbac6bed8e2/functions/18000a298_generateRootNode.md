# _generateRootNode

- ea: `0x18000a298`
- end: `0x18000b057`
- name: `_generateRootNode`
- size: `3519`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, OLECHAR *, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009b30`

## callees

- `0x1800092fc`
- `0x180009574`
- `0x1800097a4`
- `0x180009c84`
- `0x180009f74`
- `0x18000a0f0`
- `0x18000a298`
- `0x18000d4bc`
- `0x1800100ac`
- `0x1800103ac`
- `0x180011f90`
- `0x180012260`
- `0x180012310`
- `0x1800123d4`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6b2`
- `CRYPT32!CryptProtectData` at `0x18000a6a8`
- `CRYPT32!CryptProtectData` at `0x18000a6a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a6c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a733`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a6c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a733`

## string_xrefs

- `0x18000a2dc`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x18000a344`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x18000a3af`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x18000a41d`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x18000a47e`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x18000a51c`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x18000a623`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x18000a6f5`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x18000a778`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x18000a7e6`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x18000a84d`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x18000a9b5`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x18000aa36`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x18000aab0`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x18000abd5`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x18000af85`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x18000a2c9`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x18000a2c2`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000a3be`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000a42c`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000a48d`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000a632`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000a704`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000a787`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000a7f5`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000a85c`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000a9c4`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000aa45`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000aabc`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000a441`: `ICONFilePath`
- `0x18000ab72`: `http://www.microsoft.com/networking/WWAN/profile/v2`
- `0x18000ac48`: `http://www.microsoft.com/networking/WWAN/profile/v2`
- `0x18000ac15`: `http://www.microsoft.com/networking/WWAN/profile/v6`
- `0x18000acaf`: `http://www.microsoft.com/networking/WWAN/profile/v3`
- `0x18000ad21`: `http://www.microsoft.com/networking/WWAN/profile/v3`
- `0x18000ad93`: `http://www.microsoft.com/networking/WWAN/profile/v5`
- `0x18000ae05`: `http://www.microsoft.com/networking/WWAN/profile/v5`
- `0x18000ae72`: `http://www.microsoft.com/networking/WWAN/profile/v7`
- `0x18000aed1`: `http://www.microsoft.com/networking/WWAN/profile/v8`

## pseudocode

```c
__int64 __fastcall generateRootNode(struct IXMLDOMDocument2 *a1, OLECHAR *a2, int a3)
{
  int v6; // r12d
  int v7; // eax
  OLECHAR *v8; // r15
  OLECHAR *v9; // r8
  OLECHAR *v10; // r9
  unsigned int v11; // ebx
  unsigned int v13; // eax
  OLECHAR *v14; // r9
  struct IXMLDOMNode *v15; // rbx
  unsigned int ContextNode; // esi
  unsigned int v17; // eax
  OLECHAR *v18; // r9
  unsigned int v19; // eax
  OLECHAR *v20; // r9
  unsigned int v21; // eax
  OLECHAR *v22; // r9
  unsigned int v23; // eax
  unsigned int v24; // eax
  OLECHAR *v25; // r12
  unsigned int v26; // eax
  OLECHAR *v27; // r9
  __int64 v28; // rax
  DWORD LastError; // edi
  unsigned int v30; // eax
  OLECHAR *v31; // r9
  unsigned int v32; // eax
  OLECHAR *v33; // r9
  unsigned int v34; // eax
  OLECHAR *v35; // r9
  unsigned int v36; // eax
  OLECHAR *v37; // r9
  _DWORD *v38; // r8
  unsigned int v39; // r9d
  unsigned int v40; // eax
  OLECHAR *v41; // r9
  unsigned int v42; // eax
  OLECHAR *v43; // r9
  unsigned int v44; // ecx
  unsigned int v45; // eax
  bool v46; // cf
  LONG v47; // ecx
  int v48; // r8d
  unsigned int v49; // r9d
  OLECHAR *pPromptStruct; // [rsp+20h] [rbp-48h]
  DATA_BLOB pDataOut; // [rsp+40h] [rbp-28h] BYREF
  DATA_BLOB pDataIn; // [rsp+50h] [rbp-18h] BYREF
  struct IXMLDOMNode *v53; // [rsp+B8h] [rbp+50h] BYREF

  v6 = 0;
  v53 = 0;
  v7 = *((_DWORD *)a2 + 1157);
  v8 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
  if ( v7 == 3 )
  {
    v9 = L"MBNProfileV3";
    v10 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
  }
  else if ( v7 == 2 )
  {
    v9 = L"MBNProfileExt";
    v10 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
  }
  else
  {
    v9 = (OLECHAR *)L"MBNProfile";
    v10 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
  }
  v11 = XcAddChildElement(a1, (struct IXMLDOMNode *)a1, v9, v10, 0, &v53);
  if ( v11 )
  {
    if ( v53 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v53->lpVtbl->Release)(v53);
    return v11;
  }
  v13 = *((_DWORD *)a2 + 1157);
  if ( v13 < 3 )
  {
    v14 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
    if ( v13 != 2 )
      v14 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
  }
  else
  {
    v14 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
  }
  v15 = v53;
  ContextNode = XcAddChildElement(a1, v53, (OLECHAR *)L"Name", v14, a2, 0);
  if ( ContextNode )
  {
    if ( v15 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
    return ContextNode;
  }
  if ( a2[256] )
  {
    v17 = *((_DWORD *)a2 + 1157);
    if ( v17 < 3 )
    {
      v18 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
      if ( v17 != 2 )
        v18 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
    }
    else
    {
      v18 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
    }
    ContextNode = XcAddChildElement(a1, v15, (OLECHAR *)L"Description", v18, a2 + 256, 0);
    if ( ContextNode )
    {
      if ( v15 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
      return ContextNode;
    }
  }
  if ( a2[512] )
  {
    v19 = *((_DWORD *)a2 + 1157);
    if ( v19 < 3 )
    {
      v20 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
      if ( v19 != 2 )
        v20 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
    }
    else
    {
      v20 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
    }
    ContextNode = XcAddChildElement(a1, v15, (OLECHAR *)L"ICONFilePath", v20, a2 + 512, 0);
    if ( ContextNode )
    {
      if ( v15 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
      return ContextNode;
    }
  }
  v21 = *((_DWORD *)a2 + 1157);
  if ( v21 < 3 )
  {
    v22 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
    if ( v21 != 2 )
      v22 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
  }
  else
  {
    v22 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
  }
  ContextNode = XcAddChildElementEnum(
                  a1,
                  v15,
                  (OLECHAR *)L"IsDefault",
                  v22,
                  *((_DWORD *)a2 + 768) != 0,
                  (const struct _XC_STRING_VALUE_MAPPING *)&off_180015490,
                  4u);
  if ( ContextNode )
  {
    if ( v15 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
    return ContextNode;
  }
  v23 = *((_DWORD *)a2 + 1157);
  if ( v23 < 3 )
  {
    if ( v23 == 2 )
    {
      v24 = *((_DWORD *)a2 + 769);
      if ( v24 == 4 )
      {
        v6 = 1;
        *((_DWORD *)a2 + 769) = 3;
        v24 = 3;
      }
      ContextNode = XcAddChildElementEnum(
                      a1,
                      v15,
                      (OLECHAR *)L"ProfileCreationType",
                      (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4",
                      v24,
                      (const struct _XC_STRING_VALUE_MAPPING *)&_creationType,
                      4u);
      if ( ContextNode )
      {
        if ( v15 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
        return ContextNode;
      }
      if ( v6 == 1 )
        *((_DWORD *)a2 + 769) = 4;
    }
  }
  else
  {
    ContextNode = XcAddChildElementEnum(
                    a1,
                    v15,
                    (OLECHAR *)L"ProfileCreationType",
                    (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9",
                    *((_DWORD *)a2 + 769),
                    (const struct _XC_STRING_VALUE_MAPPING *)&_creationType,
                    6u);
    if ( ContextNode )
    {
      if ( v15 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
      return ContextNode;
    }
  }
  v25 = a2 + 1540;
  ContextNode = validateSubId(a2 + 1540);
  if ( ContextNode )
  {
    if ( v15 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
    return ContextNode;
  }
  v26 = *((_DWORD *)a2 + 1157);
  if ( v26 >= 2 && !*v25 )
  {
LABEL_87:
    if ( a2[1556] )
    {
      v32 = *((_DWORD *)a2 + 1157);
      if ( v32 < 3 )
      {
        v33 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
        if ( v32 != 2 )
          v33 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
      }
      else
      {
        v33 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
      }
      ContextNode = XcAddChildElement(a1, v15, (OLECHAR *)L"SimIccID", v33, a2 + 1556, 0);
      if ( ContextNode )
      {
        if ( v15 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
        return ContextNode;
      }
    }
    if ( a2[1577] )
    {
      v34 = *((_DWORD *)a2 + 1157);
      if ( v34 < 3 )
      {
        v35 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
        if ( v34 != 2 )
          v35 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
      }
      else
      {
        v35 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
      }
      ContextNode = XcAddChildElement(a1, v15, (OLECHAR *)L"HomeProviderName", v35, a2 + 1577, 0);
      if ( ContextNode )
      {
        if ( v15 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
        return ContextNode;
      }
    }
    v36 = *((_DWORD *)a2 + 1157);
    if ( v36 < 3 )
    {
      v37 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
      if ( v36 != 2 )
        v37 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
    }
    else
    {
      v37 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
    }
    ContextNode = XcAddChildElementEnum(
                    a1,
                    v15,
                    (OLECHAR *)L"ConnectionMode",
                    v37,
                    *((_DWORD *)a2 + 799),
                    (const struct _XC_STRING_VALUE_MAPPING *)&_connMode,
                    3u);
    if ( ContextNode )
    {
      if ( v15 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
      return ContextNode;
    }
    if ( *((_DWORD *)a2 + 800) )
    {
      ContextNode = _generateContextNode(a1, v15, (struct WWAN_CONTEXT_INFO *)(a2 + 1600), *((_DWORD *)a2 + 1157));
      if ( ContextNode )
      {
        if ( v15 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
        return ContextNode;
      }
    }
    v38 = (_DWORD *)*((_QWORD *)a2 + 559);
    if ( v38 && *v38 )
      ContextNode = generateDataRoamingProviderListNode(a1, v15, v38, *((_DWORD *)a2 + 1157));
    if ( *((_DWORD *)a2 + 1157) == 2 )
    {
      ContextNode = generatePurposeGroupsNode(a1, v15, (__int64)a2);
      if ( ContextNode )
      {
        if ( v15 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
        return ContextNode;
      }
    }
    v39 = *((_DWORD *)a2 + 1157);
    if ( v39 >= 2 )
    {
      ContextNode = generateProfileConditionsNode(a1, v15, (__int64)(a2 + 2316), v39);
      if ( ContextNode )
      {
        if ( v15 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
        return ContextNode;
      }
      if ( *((_DWORD *)a2 + 1173) )
      {
        if ( *((_DWORD *)a2 + 768) || *((_DWORD *)a2 + 799) )
          goto LABEL_234;
        v40 = *((_DWORD *)a2 + 1157);
        if ( v40 < 3 )
        {
          v41 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
          if ( v40 != 2 )
            v41 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
        }
        else
        {
          v41 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
        }
        ContextNode = XcAddChildElementEnum(
                        a1,
                        v15,
                        (OLECHAR *)L"IsProvisioningProfile",
                        v41,
                        1u,
                        (const struct _XC_STRING_VALUE_MAPPING *)&off_180015490,
                        4u);
        if ( ContextNode )
        {
          if ( v15 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
          return ContextNode;
        }
      }
      if ( !*((_DWORD *)a2 + 1174) )
      {
        v42 = *((_DWORD *)a2 + 1157);
        if ( v42 < 3 )
        {
          v43 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
          if ( v42 != 2 )
            v43 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
        }
        else
        {
          v43 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
        }
        ContextNode = XcAddChildElementEnum(
                        a1,
                        v15,
                        (OLECHAR *)L"AdminEnable",
                        v43,
                        0,
                        (const struct _XC_STRING_VALUE_MAPPING *)&off_180015490,
                        4u);
        if ( ContextNode )
        {
          if ( v15 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
          return ContextNode;
        }
      }
      v44 = *((_DWORD *)a2 + 1172);
      if ( v44 )
      {
        v45 = *((_DWORD *)a2 + 1157);
        if ( v45 < 3 )
        {
          if ( v45 != 2 )
            v8 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
        }
        else
        {
          v8 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
        }
        ContextNode = XcAddChildElementEnum(
                        a1,
                        v15,
                        (OLECHAR *)L"AdminRoamControl",
                        v8,
                        v44,
                        (const struct _XC_STRING_VALUE_MAPPING *)&_roamControl,
                        3u);
        if ( ContextNode )
        {
          if ( v15 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
          return ContextNode;
        }
      }
      ContextNode = generateMmsConfigurationNode(a1, v15, (__int64)(a2 + 2360), *((_DWORD *)a2 + 1157));
      if ( ContextNode )
      {
        if ( v15 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
        return ContextNode;
      }
    }
    if ( *((_DWORD *)a2 + 1120) )
    {
      ContextNode = XcAddChildElementEnum(
                      a1,
                      v15,
                      (OLECHAR *)L"IsPurchaseProfile",
                      (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v2",
                      1u,
                      (const struct _XC_STRING_VALUE_MAPPING *)&off_180015490,
                      4u);
      if ( ContextNode )
      {
        if ( v15 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
        return ContextNode;
      }
    }
    if ( a2[2244] )
    {
      pPromptStruct = a2 + 2244;
      if ( *((_DWORD *)a2 + 1157) < 3u )
      {
        if ( *((_DWORD *)a2 + 1121) )
        {
          ContextNode = XcAddChildElement(
                          a1,
                          v15,
                          (OLECHAR *)L"DisplayProviderNameLong",
                          (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v6",
                          pPromptStruct,
                          0);
          if ( ContextNode )
          {
            if ( v15 )
              ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
            return ContextNode;
          }
        }
        else
        {
          ContextNode = XcAddChildElement(
                          a1,
                          v15,
                          (OLECHAR *)L"DisplayProviderName",
                          (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v2",
                          pPromptStruct,
                          0);
          if ( ContextNode )
          {
            if ( v15 )
              ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
            return ContextNode;
          }
        }
      }
      else
      {
        ContextNode = XcAddChildElement(
                        a1,
                        v15,
                        (OLECHAR *)L"DisplayProviderName",
                        (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9",
                        pPromptStruct,
                        0);
        if ( ContextNode )
        {
          if ( v15 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
          return ContextNode;
        }
      }
    }
    if ( *((_DWORD *)a2 + 1155) )
    {
      if ( *((_DWORD *)a2 + 768) || *((_DWORD *)a2 + 799) )
        goto LABEL_234;
      ContextNode = XcAddChildElementEnum(
                      a1,
                      v15,
                      (OLECHAR *)L"IsAdditionalPdpContextProfile",
                      (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v3",
                      1u,
                      (const struct _XC_STRING_VALUE_MAPPING *)&off_180015490,
                      4u);
      if ( ContextNode )
      {
        if ( v15 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
        return ContextNode;
      }
    }
    if ( *((_DWORD *)a2 + 1156) )
    {
      if ( *((_DWORD *)a2 + 768) || *((_DWORD *)a2 + 799) )
        goto LABEL_234;
      ContextNode = XcAddChildElementEnum(
                      a1,
                      v15,
                      (OLECHAR *)L"IsTetheringProfile",
                      (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v3",
                      1u,
                      (const struct _XC_STRING_VALUE_MAPPING *)&off_180015490,
                      4u);
      if ( ContextNode )
      {
        if ( v15 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
        return ContextNode;
      }
    }
    if ( *((_DWORD *)a2 + 1310) )
    {
      if ( !*((_DWORD *)a2 + 1155) || *((_DWORD *)a2 + 1157) < 2u )
        goto LABEL_234;
      ContextNode = XcAddChildElementEnum(
                      a1,
                      v15,
                      (OLECHAR *)L"FollowInternetConnectionEnablementPolicy",
                      (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v5",
                      1u,
                      (const struct _XC_STRING_VALUE_MAPPING *)&off_180015490,
                      4u);
      if ( ContextNode )
      {
        if ( v15 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
        return ContextNode;
      }
    }
    if ( *((_DWORD *)a2 + 1311) )
    {
      if ( !*((_DWORD *)a2 + 1155) || *((_DWORD *)a2 + 1157) < 2u )
        goto LABEL_234;
      ContextNode = XcAddChildElementEnum(
                      a1,
                      v15,
                      (OLECHAR *)L"FollowInternetConnectionRoamingPolicy",
                      (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v5",
                      1u,
                      (const struct _XC_STRING_VALUE_MAPPING *)&off_180015490,
                      4u);
      if ( ContextNode )
      {
        if ( v15 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
        return ContextNode;
      }
    }
    v46 = *((_DWORD *)a2 + 1157) < 2u;
    if ( *((_DWORD *)a2 + 1157) == 2 )
    {
      if ( *((_DWORD *)a2 + 769) == 4 )
      {
        ContextNode = XcAddChildElementEnum(
                        a1,
                        v15,
                        (OLECHAR *)L"IsBasedOnModemProvisionedContext",
                        (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v7",
                        1u,
                        (const struct _XC_STRING_VALUE_MAPPING *)&off_180015490,
                        4u);
        if ( ContextNode )
        {
          if ( v15 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
          return ContextNode;
        }
      }
      if ( *((_DWORD *)a2 + 769) == 3 && !*((_DWORD *)a2 + 1120) )
      {
        v47 = *((_DWORD *)a2 + 1312);
        if ( (unsigned int)(v47 - 1) <= 0xFFFE )
        {
          ContextNode = XcAddChildElementDWORD(
                          a1,
                          v15,
                          (OLECHAR *)L"AutoConnectOrder",
                          (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v8",
                          v47);
          if ( ContextNode )
          {
            if ( v15 )
              ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
            return ContextNode;
          }
        }
      }
      v46 = *((_DWORD *)a2 + 1157) < 2u;
    }
    if ( !v46 )
    {
      v48 = *((_DWORD *)a2 + 1160);
      if ( v48 )
      {
        if ( *((_DWORD *)a2 + 1159) )
        {
LABEL_234:
          if ( v15 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
          return 1206;
        }
        ContextNode = _generateRATApplicabilityNode(a1, v15, v48);
        if ( ContextNode )
        {
          if ( v15 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
          return ContextNode;
        }
      }
    }
    if ( *((_DWORD *)a2 + 1157) != 3
      || (ContextNode = XcAddChildElementDWORD(
                          a1,
                          v15,
                          (OLECHAR *)L"RulePrecedence",
                          (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9",
                          *((_DWORD *)a2 + 1312))) == 0 )
    {
      v49 = *((_DWORD *)a2 + 1157);
      if ( v49 >= 3 )
      {
        ContextNode = _generateTrafficDescriptorNode(a1, v15, (struct _TRAFFIC_DESCRIPTOR *)(a2 + 2628), v49);
        if ( ContextNode )
        {
          if ( v15 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
          return ContextNode;
        }
        ContextNode = _generateRouteSelectionDescriptorsNode(
                        a1,
                        v15,
                        *((struct ROUTE_SELECTION_DESCRIPTOR_LIST **)a2 + 789),
                        *((_DWORD *)a2 + 1157));
        if ( ContextNode )
        {
          if ( v15 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
          return ContextNode;
        }
      }
      if ( v15 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
      return ContextNode;
    }
    if ( v15 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
    return ContextNode;
  }
  if ( !a3 )
  {
    if ( v26 < 3 )
    {
      v27 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
      if ( v26 != 2 )
        v27 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
    }
    else
    {
      v27 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
    }
    ContextNode = XcAddChildElement(a1, v15, (OLECHAR *)L"SubscriberID", v27, a2 + 1540, 0);
    goto LABEL_83;
  }
  *(&pDataIn.cbData + 1) = 0;
  *(_QWORD *)&pDataOut.cbData = 0;
  pDataOut.pbData = 0;
  v28 = -1;
  do
    ++v28;
  while ( v25[v28] );
  pDataIn.cbData = 2 * v28;
  pDataIn.pbData = (BYTE *)(a2 + 1540);
  if ( CryptProtectData(&pDataIn, 0, 0, 0, 0, 0, &pDataOut) )
  {
    v30 = *((_DWORD *)a2 + 1157);
    if ( v30 < 3 )
    {
      v31 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
      if ( v30 != 2 )
        v31 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
    }
    else
    {
      v31 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
    }
    ContextNode = XcAddChildElementHexBinary(a1, v15, (OLECHAR *)L"SubscriberID", v31, pDataOut.pbData, pDataOut.cbData);
    LocalFree(pDataOut.pbData);
LABEL_83:
    if ( ContextNode )
    {
      if ( v15 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
      return ContextNode;
    }
    goto LABEL_87;
  }
  LastError = GetLastError();
  if ( pDataOut.pbData )
    LocalFree(pDataOut.pbData);
  if ( v15 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
  return LastError;
}

```

## disassembly

```asm
0x18000a298  push    rbp
0x18000a29a  push    rbx
0x18000a29b  push    rsi
0x18000a29c  push    rdi
0x18000a29d  push    r12
0x18000a29f  push    r13
0x18000a2a1  push    r14
0x18000a2a3  push    r15
0x18000a2a5  mov     rbp, rsp
0x18000a2a8  sub     rsp, 68h
0x18000a2ac  mov     r13d, r8d
0x18000a2af  mov     rdi, rdx
0x18000a2b2  mov     r14, rcx
0x18000a2b5  xor     r12d, r12d
0x18000a2b8  mov     [rbp+arg_8], r12
0x18000a2bc  mov     eax, [rdx+1214h]
0x18000a2c2  lea     rsi, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x18000a2c9  lea     r15, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x18000a2d0  cmp     eax, 3
0x18000a2d3  jnz     short loc_18000A2E5
0x18000a2d5  lea     r8, aMbnprofilev3; "MBNProfileV3"
0x18000a2dc  lea     r9, aHttpWwwMicroso_6; "http://www.microsoft.com/networking/WWA"...
0x18000a2e3  jmp     short loc_18000A300
0x18000a2e5  cmp     eax, 2
0x18000a2e8  jnz     short loc_18000A2F6
0x18000a2ea  lea     r8, aMbnprofileext; "MBNProfileExt"
0x18000a2f1  mov     r9, r15
0x18000a2f4  jmp     short loc_18000A300
0x18000a2f6  lea     r8, aMbnprofile; "MBNProfile"
0x18000a2fd  mov     r9, rsi; OLECHAR *
0x18000a300  lea     rax, [rbp+arg_8]
0x18000a304  mov     qword ptr [rsp+68h+dwFlags], rax; struct IXMLDOMNode **
0x18000a309  mov     [rsp+68h+pPromptStruct], r12; OLECHAR *
0x18000a30e  mov     rdx, r14; struct IXMLDOMNode *
0x18000a311  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000a316  mov     ebx, eax
0x18000a318  test    eax, eax
0x18000a31a  jz      short loc_18000A339
0x18000a31c  mov     rcx, [rbp+arg_8]
0x18000a320  test    rcx, rcx
0x18000a323  jz      short loc_18000A332
0x18000a325  mov     rdx, [rcx]
0x18000a328  mov     rax, [rdx+10h]
0x18000a32c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a331  nop
0x18000a332  mov     eax, ebx
0x18000a334  jmp     loc_18000B046
0x18000a339  mov     eax, [rdi+1214h]
0x18000a33f  cmp     eax, 3
0x18000a342  jb      short loc_18000A34D
0x18000a344  lea     r9, aHttpWwwMicroso_6; "http://www.microsoft.com/networking/WWA"...
0x18000a34b  jmp     short loc_18000A357
0x18000a34d  mov     r9, r15
0x18000a350  cmp     eax, 2
0x18000a353  cmovnz  r9, rsi; OLECHAR *
0x18000a357  mov     qword ptr [rsp+68h+dwFlags], r12; struct IXMLDOMNode **
0x18000a35c  mov     [rsp+68h+pPromptStruct], rdi; OLECHAR *
0x18000a361  lea     r8, aName; "Name"
0x18000a368  mov     rbx, [rbp+arg_8]
0x18000a36c  mov     rdx, rbx; struct IXMLDOMNode *
0x18000a36f  mov     rcx, r14; struct IXMLDOMDocument2 *
0x18000a372  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000a377  mov     esi, eax
0x18000a379  test    eax, eax
0x18000a37b  jz      short loc_18000A397
0x18000a37d  test    rbx, rbx
0x18000a380  jz      short loc_18000A392
0x18000a382  mov     rdx, [rbx]
0x18000a385  mov     rcx, rbx
0x18000a388  mov     rax, [rdx+10h]
0x18000a38c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a391  nop
0x18000a392  jmp     loc_18000B044
0x18000a397  lea     rcx, [rdi+200h]
0x18000a39e  cmp     [rcx], r12w
0x18000a3a2  jz      short loc_18000A405
0x18000a3a4  mov     eax, [rdi+1214h]
0x18000a3aa  cmp     eax, 3
0x18000a3ad  jb      short loc_18000A3B8
0x18000a3af  lea     r9, aHttpWwwMicroso_6; "http://www.microsoft.com/networking/WWA"...
0x18000a3b6  jmp     short loc_18000A3C9
0x18000a3b8  mov     r9, r15
0x18000a3bb  cmp     eax, 2
0x18000a3be  lea     rax, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x18000a3c5  cmovnz  r9, rax; OLECHAR *
0x18000a3c9  mov     qword ptr [rsp+68h+dwFlags], r12; struct IXMLDOMNode **
0x18000a3ce  mov     [rsp+68h+pPromptStruct], rcx; OLECHAR *
0x18000a3d3  lea     r8, aDescription; "Description"
0x18000a3da  mov     rdx, rbx; struct IXMLDOMNode *
0x18000a3dd  mov     rcx, r14; struct IXMLDOMDocument2 *
0x18000a3e0  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000a3e5  mov     esi, eax
0x18000a3e7  test    eax, eax
0x18000a3e9  jz      short loc_18000A405
0x18000a3eb  test    rbx, rbx
0x18000a3ee  jz      short loc_18000A400
0x18000a3f0  mov     rcx, [rbx]
0x18000a3f3  mov     rax, [rcx+10h]
0x18000a3f7  mov     rcx, rbx
0x18000a3fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3ff  nop
0x18000a400  jmp     loc_18000B044
0x18000a405  lea     rcx, [rdi+400h]
0x18000a40c  cmp     [rcx], r12w
0x18000a410  jz      short loc_18000A473
0x18000a412  mov     eax, [rdi+1214h]
0x18000a418  cmp     eax, 3
0x18000a41b  jb      short loc_18000A426
0x18000a41d  lea     r9, aHttpWwwMicroso_6; "http://www.microsoft.com/networking/WWA"...
0x18000a424  jmp     short loc_18000A437
0x18000a426  mov     r9, r15
0x18000a429  cmp     eax, 2
0x18000a42c  lea     rax, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x18000a433  cmovnz  r9, rax; OLECHAR *
0x18000a437  mov     qword ptr [rsp+68h+dwFlags], r12; struct IXMLDOMNode **
0x18000a43c  mov     [rsp+68h+pPromptStruct], rcx; OLECHAR *
0x18000a441  lea     r8, aIconfilepath; "ICONFilePath"
0x18000a448  mov     rdx, rbx; struct IXMLDOMNode *
0x18000a44b  mov     rcx, r14; struct IXMLDOMDocument2 *
0x18000a44e  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000a453  mov     esi, eax
0x18000a455  test    eax, eax
0x18000a457  jz      short loc_18000A473
0x18000a459  test    rbx, rbx
0x18000a45c  jz      short loc_18000A46E
0x18000a45e  mov     rcx, [rbx]
0x18000a461  mov     rax, [rcx+10h]
0x18000a465  mov     rcx, rbx
0x18000a468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a46d  nop
0x18000a46e  jmp     loc_18000B044
0x18000a473  mov     eax, [rdi+1214h]
0x18000a479  cmp     eax, 3
0x18000a47c  jb      short loc_18000A487
0x18000a47e  lea     r9, aHttpWwwMicroso_6; "http://www.microsoft.com/networking/WWA"...
0x18000a485  jmp     short loc_18000A498
0x18000a487  mov     r9, r15
0x18000a48a  cmp     eax, 2
0x18000a48d  lea     rax, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x18000a494  cmovnz  r9, rax; OLECHAR *
0x18000a498  mov     eax, r12d
0x18000a49b  cmp     [rdi+0C00h], r12d
0x18000a4a2  setnz   al
0x18000a4a5  mov     dword ptr [rsp+68h+pDataOut], 4; unsigned int
0x18000a4ad  lea     rcx, off_180015490; "true"
0x18000a4b4  mov     qword ptr [rsp+68h+dwFlags], rcx; struct _XC_STRING_VALUE_MAPPING *
0x18000a4b9  mov     dword ptr [rsp+68h+pPromptStruct], eax; unsigned int
0x18000a4bd  lea     r8, aIsdefault; "IsDefault"
0x18000a4c4  mov     rdx, rbx; struct IXMLDOMNode *
0x18000a4c7  mov     rcx, r14; struct IXMLDOMDocument2 *
0x18000a4ca  call    ?XcAddChildElementEnum@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEBU_XC_STRING_VALUE_MAPPING@@KPEAPEAU2@@Z; XcAddChildElementEnum(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,_XC_STRING_VALUE_MAPPING const *,ulong,IXMLDOMNode * *)
0x18000a4cf  mov     esi, eax
0x18000a4d1  test    eax, eax
0x18000a4d3  jz      short loc_18000A4EF
0x18000a4d5  test    rbx, rbx
0x18000a4d8  jz      short loc_18000A4EA
0x18000a4da  mov     rcx, [rbx]
0x18000a4dd  mov     rax, [rcx+10h]
0x18000a4e1  mov     rcx, rbx
0x18000a4e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4e9  nop
0x18000a4ea  jmp     loc_18000B044
0x18000a4ef  mov     eax, [rdi+1214h]
0x18000a4f5  mov     ecx, 3
0x18000a4fa  cmp     eax, ecx
0x18000a4fc  jb      short loc_18000A559
0x18000a4fe  mov     dword ptr [rsp+68h+pDataOut], 6; unsigned int
0x18000a506  lea     rcx, ?_creationType@@3QBU_XC_STRING_VALUE_MAPPING@@B; _XC_STRING_VALUE_MAPPING const near * const _creationType
0x18000a50d  mov     qword ptr [rsp+68h+dwFlags], rcx; struct _XC_STRING_VALUE_MAPPING *
0x18000a512  mov     eax, [rdi+0C04h]
0x18000a518  mov     dword ptr [rsp+68h+pPromptStruct], eax; unsigned int
0x18000a51c  lea     r9, aHttpWwwMicroso_6; "http://www.microsoft.com/networking/WWA"...
0x18000a523  lea     r8, aProfilecreatio; "ProfileCreationType"
0x18000a52a  mov     rdx, rbx; struct IXMLDOMNode *
0x18000a52d  mov     rcx, r14; struct IXMLDOMDocument2 *
0x18000a530  call    ?XcAddChildElementEnum@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEBU_XC_STRING_VALUE_MAPPING@@KPEAPEAU2@@Z; XcAddChildElementEnum(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,_XC_STRING_VALUE_MAPPING const *,ulong,IXMLDOMNode * *)
0x18000a535  mov     esi, eax
0x18000a537  test    eax, eax
0x18000a539  jz      loc_18000A5D2
0x18000a53f  test    rbx, rbx
0x18000a542  jz      short loc_18000A554
0x18000a544  mov     rcx, [rbx]
0x18000a547  mov     rax, [rcx+10h]
0x18000a54b  mov     rcx, rbx
0x18000a54e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a553  nop
0x18000a554  jmp     loc_18000B044
0x18000a559  cmp     eax, 2
0x18000a55c  jnz     short loc_18000A5D2
0x18000a55e  mov     eax, [rdi+0C04h]
0x18000a564  cmp     eax, 4
0x18000a567  jnz     short loc_18000A575
0x18000a569  lea     r12d, [rax-3]
0x18000a56d  mov     [rdi+0C04h], ecx
0x18000a573  mov     eax, ecx
0x18000a575  mov     dword ptr [rsp+68h+pDataOut], 4; unsigned int
0x18000a57d  lea     rcx, ?_creationType@@3QBU_XC_STRING_VALUE_MAPPING@@B; _XC_STRING_VALUE_MAPPING const near * const _creationType
0x18000a584  mov     qword ptr [rsp+68h+dwFlags], rcx; struct _XC_STRING_VALUE_MAPPING *
0x18000a589  mov     dword ptr [rsp+68h+pPromptStruct], eax; unsigned int
0x18000a58d  mov     r9, r15; OLECHAR *
0x18000a590  lea     r8, aProfilecreatio; "ProfileCreationType"
0x18000a597  mov     rdx, rbx; struct IXMLDOMNode *
0x18000a59a  mov     rcx, r14; struct IXMLDOMDocument2 *
0x18000a59d  call    ?XcAddChildElementEnum@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEBU_XC_STRING_VALUE_MAPPING@@KPEAPEAU2@@Z; XcAddChildElementEnum(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,_XC_STRING_VALUE_MAPPING const *,ulong,IXMLDOMNode * *)
0x18000a5a2  mov     esi, eax
0x18000a5a4  test    eax, eax
0x18000a5a6  jz      short loc_18000A5C2
0x18000a5a8  test    rbx, rbx
0x18000a5ab  jz      short loc_18000A5BD
0x18000a5ad  mov     rcx, [rbx]
0x18000a5b0  mov     rax, [rcx+10h]
0x18000a5b4  mov     rcx, rbx
0x18000a5b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5bc  nop
0x18000a5bd  jmp     loc_18000B044
0x18000a5c2  cmp     r12d, 1
0x18000a5c6  jnz     short loc_18000A5D2
0x18000a5c8  mov     dword ptr [rdi+0C04h], 4
0x18000a5d2  lea     r12, [rdi+0C08h]
0x18000a5d9  mov     rcx, r12
0x18000a5dc  call    _validateSubId
0x18000a5e1  mov     esi, eax
0x18000a5e3  xor     ecx, ecx
0x18000a5e5  test    eax, eax
0x18000a5e7  jz      short loc_18000A603
0x18000a5e9  test    rbx, rbx
0x18000a5ec  jz      short loc_18000A5FE
0x18000a5ee  mov     rcx, [rbx]
0x18000a5f1  mov     rax, [rcx+10h]
0x18000a5f5  mov     rcx, rbx
0x18000a5f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5fd  nop
0x18000a5fe  jmp     loc_18000B044
0x18000a603  mov     eax, [rdi+1214h]
0x18000a609  cmp     eax, 2
0x18000a60c  jb      short loc_18000A619
0x18000a60e  cmp     [r12], cx
0x18000a613  jz      loc_18000A757
0x18000a619  test    r13d, r13d
0x18000a61c  jnz     short loc_18000A663
0x18000a61e  cmp     eax, 3
0x18000a621  jb      short loc_18000A62C
0x18000a623  lea     r9, aHttpWwwMicroso_6; "http://www.microsoft.com/networking/WWA"...
0x18000a62a  jmp     short loc_18000A63D
0x18000a62c  mov     r9, r15
0x18000a62f  cmp     eax, 2
0x18000a632  lea     rax, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x18000a639  cmovnz  r9, rax; OLECHAR *
0x18000a63d  xor     r13d, r13d
0x18000a640  mov     qword ptr [rsp+68h+dwFlags], r13; struct IXMLDOMNode **
0x18000a645  mov     [rsp+68h+pPromptStruct], r12; OLECHAR *
0x18000a64a  lea     r8, aSubscriberid; "SubscriberID"
0x18000a651  mov     rdx, rbx; struct IXMLDOMNode *
0x18000a654  mov     rcx, r14; struct IXMLDOMDocument2 *
0x18000a657  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000a65c  mov     esi, eax
0x18000a65e  jmp     loc_18000A739
0x18000a663  xor     r13d, r13d
0x18000a666  mov     dword ptr [rbp+pDataIn+4], r13d
0x18000a66a  mov     qword ptr [rbp+var_28.cbData], r13
0x18000a66e  mov     [rbp+var_28.pbData], r13
0x18000a672  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a676  inc     rax
0x18000a679  cmp     [r12+rax*2], r13w
0x18000a67e  jnz     short loc_18000A676
0x18000a680  add     eax, eax
0x18000a682  mov     [rbp+pDataIn.cbData], eax
0x18000a685  mov     [rbp+pDataIn.pbData], r12
0x18000a689  lea     rax, [rbp+var_28]
0x18000a68d  mov     [rsp+68h+pDataOut], rax; struct IXMLDOMNode **
0x18000a692  mov     [rsp+68h+dwFlags], r13d; dwFlags
0x18000a697  mov     [rsp+68h+pPromptStruct], r13; pPromptStruct
0x18000a69c  xor     r9d, r9d; pvReserved
0x18000a69f  xor     r8d, r8d; pOptionalEntropy
0x18000a6a2  xor     edx, edx; szDataDescr
0x18000a6a4  lea     rcx, [rbp+pDataIn]; pDataIn
0x18000a6a8  call    cs:__imp_CryptProtectData
0x18000a6ae  test    eax, eax
0x18000a6b0  jnz     short loc_18000A6E6
0x18000a6b2  call    cs:__imp_GetLastError
0x18000a6b8  mov     edi, eax
0x18000a6ba  mov     rcx, [rbp+var_28.pbData]; hMem
0x18000a6be  test    rcx, rcx
0x18000a6c1  jz      short loc_18000A6CA
0x18000a6c3  call    cs:__imp_LocalFree
0x18000a6c9  nop
0x18000a6ca  test    rbx, rbx
0x18000a6cd  jz      short loc_18000A6DF
0x18000a6cf  mov     rax, [rbx]
0x18000a6d2  mov     rcx, rbx
0x18000a6d5  mov     rax, [rax+10h]
0x18000a6d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6de  nop
0x18000a6df  mov     eax, edi
0x18000a6e1  jmp     loc_18000B046
0x18000a6e6  mov     rcx, [rbp+var_28.pbData]
0x18000a6ea  mov     eax, [rdi+1214h]
0x18000a6f0  cmp     eax, 3
0x18000a6f3  jb      short loc_18000A6FE
0x18000a6f5  lea     r9, aHttpWwwMicroso_6; "http://www.microsoft.com/networking/WWA"...
  ... truncated ...
```
