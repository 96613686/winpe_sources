# _parseRootNode

- ea: `0x18000c4a0`
- end: `0x18000cf75`
- name: `_parseRootNode`
- size: `2773`
- prototype: `unsigned int __fastcall(struct IXMLDOMNode *, unsigned __int16 *, int, unsigned int)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180009220`
- `0x18000b4b0`
- `0x18000bbd8`
- `0x18000c4a0`
- `0x18000d4bc`
- `0x18001288c`
- `0x180012968`
- `0x180012a4c`
- `0x180012bc8`
- `0x1800131e4`
- `0x180013458`
- `0x180014010`

## string_xrefs

- `0x18000c55e`: `MBNProfileV9:ICONFilePath`
- `0x18000c567`: `MBNProfileV4:ICONFilePath`
- `0x18000c56e`: `MBNProfile:ICONFilePath`
- `0x18000cb42`: `MBNProfileV9:MmsConfiguration`
- `0x18000cb4b`: `MBNProfileV4:MmsConfiguration`
- `0x18000cb52`: `MBNProfile:MmsConfiguration`
- `0x18000cecd`: `MBNProfileV9:TrafficDescriptor`
- `0x18000cef8`: `MBNProfileV9:RouteSelectionDescriptors`

## pseudocode

```c
unsigned int __fastcall parseRootNode(struct IXMLDOMNode *a1, unsigned __int16 *a2, int a3, unsigned int a4)
{
  const unsigned __int16 *v8; // rdx
  unsigned int result; // eax
  const wchar_t *v10; // rdx
  const wchar_t *v11; // rdx
  const unsigned __int16 *v12; // rdx
  const unsigned __int16 *v13; // rdx
  int v14; // ecx
  const unsigned __int16 *v15; // rdx
  unsigned __int16 *v16; // r14
  int NodeStringValue; // r15d
  const unsigned __int16 *v18; // rdx
  const unsigned __int16 *v19; // rdx
  unsigned int SingleNode; // r14d
  const unsigned __int16 *v21; // rdx
  const unsigned __int16 *v22; // rdx
  const unsigned __int16 *v23; // rdx
  const unsigned __int16 *v24; // rdx
  const unsigned __int16 *v25; // rdx
  const unsigned __int16 *v26; // rdx
  const unsigned __int16 *v27; // rdx
  const unsigned __int16 *v28; // rdx
  const unsigned __int16 *v29; // rdx
  const unsigned __int16 *v30; // rdx
  unsigned int v31; // r9d
  const unsigned __int16 *v32; // rdx
  unsigned __int16 *v33; // r15
  const unsigned __int16 *v34; // rdx
  const unsigned __int16 *v35; // rdx
  int v36; // eax
  void *lpMem; // [rsp+40h] [rbp-10h] BYREF
  struct IXMLDOMNode *v38; // [rsp+98h] [rbp+48h] BYREF
  unsigned int v39; // [rsp+A8h] [rbp+58h] BYREF

  if ( a4 < 3 )
  {
    v8 = L"MBNProfileV4:Name";
    if ( a4 != 2 )
      v8 = L"MBNProfile:Name";
  }
  else
  {
    v8 = L"MBNProfileV9:Name";
  }
  result = XcGetNodeStringValue(a1, v8, a2, 0x100u, 0, 0, 0);
  if ( result )
    return result;
  if ( a4 < 3 )
  {
    v10 = L"MBNProfileV4:Description";
    if ( a4 != 2 )
      v10 = L"MBNProfile:Description";
  }
  else
  {
    v10 = L"MBNProfileV9:Description";
  }
  result = getOptNodeStringValue(a1, v10, a2 + 256, 256, 0);
  if ( result )
    return result;
  if ( a4 < 3 )
  {
    v11 = L"MBNProfileV4:ICONFilePath";
    if ( a4 != 2 )
      v11 = L"MBNProfile:ICONFilePath";
  }
  else
  {
    v11 = L"MBNProfileV9:ICONFilePath";
  }
  result = getOptNodeStringValue(a1, v11, a2 + 512, 1024, 0);
  if ( result )
    return result;
  if ( a4 < 3 )
  {
    v12 = L"MBNProfileV4:IsDefault";
    if ( a4 != 2 )
      v12 = L"MBNProfile:IsDefault";
  }
  else
  {
    v12 = L"MBNProfileV9:IsDefault";
  }
  result = XcGetNodeEnumValue(
             a1,
             v12,
             (const struct _XC_STRING_VALUE_MAPPING *)&off_180015490,
             4u,
             (unsigned int *)a2 + 768,
             0,
             0,
             0);
  if ( result )
    return result;
  if ( a4 < 3 )
  {
    v13 = L"MBNProfileV4:ProfileCreationType";
    if ( a4 != 2 )
      v13 = L"MBNProfile:ProfileCreationType";
  }
  else
  {
    v13 = L"MBNProfileV9:ProfileCreationType";
  }
  result = XcGetNodeEnumValue(
             a1,
             v13,
             (const struct _XC_STRING_VALUE_MAPPING *)&_creationType,
             6u,
             (unsigned int *)a2 + 769,
             1,
             0,
             0);
  if ( result )
    return result;
  if ( a4 == 2 )
  {
    v39 = 0;
    result = XcGetNodeEnumValue(
               a1,
               L"MBNProfileV7:IsBasedOnModemProvisionedContext",
               (const struct _XC_STRING_VALUE_MAPPING *)&off_180015490,
               4u,
               &v39,
               1,
               0,
               0);
    if ( result )
      return result;
    if ( v39 )
      *((_DWORD *)a2 + 769) = 4;
  }
  v14 = 0;
  if ( !a3 )
  {
    if ( a4 < 3 )
    {
      v15 = L"MBNProfileV4:SubscriberID";
      if ( a4 != 2 )
        v15 = L"MBNProfile:SubscriberID";
    }
    else
    {
      v15 = L"MBNProfileV9:SubscriberID";
    }
    v16 = a2 + 1540;
    LOBYTE(v14) = a4 != 1;
    NodeStringValue = XcGetNodeStringValue(a1, v15, a2 + 1540, 0x10u, v14, 0, 0);
    goto LABEL_54;
  }
  v38 = 0;
  lpMem = 0;
  v39 = 0;
  if ( a4 < 3 )
  {
    v18 = L"MBNProfileV4:SubscriberID";
    if ( a4 != 2 )
      v18 = L"MBNProfile:SubscriberID";
  }
  else
  {
    v18 = L"MBNProfileV9:SubscriberID";
  }
  SingleNode = XcGetSingleNode(a1, v18, &v38);
  if ( SingleNode == 1168 )
  {
    if ( a4 != 1 )
    {
      v16 = a2 + 1540;
      a2[1540] = 0;
      NodeStringValue = 0;
      goto LABEL_52;
    }
    goto LABEL_44;
  }
  if ( SingleNode )
  {
LABEL_44:
    if ( v38 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v38->lpVtbl->Release)(v38);
    return SingleNode;
  }
  SingleNode = XcGetNodeHexBinaryValue(v38, v19, (unsigned __int8 **)&lpMem, &v39);
  if ( SingleNode )
  {
    if ( v38 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v38->lpVtbl->Release)(v38);
    return SingleNode;
  }
  v16 = a2 + 1540;
  NodeStringValue = decryptData(lpMem, v39, a2 + 1540, 32);
  Xc_Process_user_free(lpMem);
LABEL_52:
  if ( v38 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v38->lpVtbl->Release)(v38);
LABEL_54:
  if ( NodeStringValue )
    return NodeStringValue;
  result = validateSubId(v16);
  if ( !result )
  {
    if ( a4 < 3 )
    {
      v21 = L"MBNProfileV4:SimIccID";
      if ( a4 != 2 )
        v21 = L"MBNProfile:SimIccID";
    }
    else
    {
      v21 = L"MBNProfileV9:SimIccID";
    }
    result = XcGetNodeStringValue(a1, v21, a2 + 1556, 0x15u, a4 == 1, 0, 0);
    if ( !result )
    {
      if ( a4 < 3 )
      {
        v22 = L"MBNProfileV4:HomeProviderName";
        if ( a4 != 2 )
          v22 = L"MBNProfile:HomeProviderName";
      }
      else
      {
        v22 = L"MBNProfileV9:HomeProviderName";
      }
      result = XcGetNodeStringValue(a1, v22, a2 + 1577, 0x15u, 1, 0, 0);
      if ( !result )
      {
        if ( a4 < 3 )
        {
          v23 = L"MBNProfileV4:ConnectionMode";
          if ( a4 != 2 )
            v23 = L"MBNProfile:ConnectionMode";
        }
        else
        {
          v23 = L"MBNProfileV9:ConnectionMode";
        }
        result = XcGetNodeEnumValue(
                   a1,
                   v23,
                   (const struct _XC_STRING_VALUE_MAPPING *)&_connMode,
                   3u,
                   (unsigned int *)a2 + 799,
                   1,
                   0,
                   0);
        if ( !result )
        {
          if ( a4 < 3 )
          {
            v24 = L"MBNProfileV4:Context";
            if ( a4 != 2 )
              v24 = L"MBNProfile:Context";
          }
          else
          {
            v24 = L"MBNProfileV9:Context";
          }
          result = _parseNode(
                     a1,
                     v24,
                     1,
                     (unsigned int (*)(struct IXMLDOMNode *, void *, int, unsigned int))_parseContextNode,
                     (struct WWAN_PROFILE *)a2,
                     0,
                     a4);
          if ( !result )
          {
            if ( a4 < 3 )
            {
              v25 = L"MBNProfileV4:DataRoamingPartners";
              if ( a4 != 2 )
                v25 = L"MBNProfile:DataRoamingPartners";
            }
            else
            {
              v25 = L"MBNProfileV9:DataRoamingPartners";
            }
            result = _parseNode(a1, v25, 1, parseDataRoamingProviderListNode, (struct WWAN_PROFILE *)a2, 0, a4);
            if ( !result )
            {
              if ( a4 == 2 )
              {
                result = _parseNode(
                           a1,
                           L"MBNProfileV4:PurposeGroups",
                           1,
                           parsePurposeGroupsNode,
                           (struct WWAN_PROFILE *)a2,
                           0,
                           2u);
                if ( result )
                  return result;
                v26 = L"MBNProfileV4:ProfileConditionedOn";
              }
              else
              {
                if ( a4 < 2 )
                  goto LABEL_104;
                v26 = L"MBNProfileV9:ProfileConditionedOn";
              }
              result = _parseNode(
                         a1,
                         v26,
                         1,
                         (unsigned int (*)(struct IXMLDOMNode *, void *, int, unsigned int))parseProfileConditionsNode,
                         (struct WWAN_PROFILE *)a2,
                         0,
                         a4);
              if ( result )
                return result;
              v27 = a4 < 3 ? L"MBNProfileV4:AdminRoamControl" : L"MBNProfileV9:AdminRoamControl";
              result = XcGetNodeEnumValue(
                         a1,
                         v27,
                         (const struct _XC_STRING_VALUE_MAPPING *)&_roamControl,
                         3u,
                         (unsigned int *)a2 + 1172,
                         1,
                         0,
                         0);
              if ( result )
                return result;
              v28 = a4 < 3 ? L"MBNProfileV4:IsProvisioningProfile" : L"MBNProfileV9:IsProvisioningProfile";
              result = XcGetNodeEnumValue(
                         a1,
                         v28,
                         (const struct _XC_STRING_VALUE_MAPPING *)&off_180015490,
                         4u,
                         (unsigned int *)a2 + 1173,
                         1,
                         0,
                         0);
              if ( result )
                return result;
              v29 = a4 < 3 ? L"MBNProfileV4:AdminEnable" : L"MBNProfileV9:AdminEnable";
              result = XcGetNodeEnumValue(
                         a1,
                         v29,
                         (const struct _XC_STRING_VALUE_MAPPING *)&off_180015490,
                         4u,
                         (unsigned int *)a2 + 1174,
                         1,
                         1u,
                         0);
              if ( result )
                return result;
              v30 = a4 < 3 ? L"MBNProfileV4:MmsConfiguration" : L"MBNProfileV9:MmsConfiguration";
              result = _parseNode(
                         a1,
                         v30,
                         1,
                         (unsigned int (*)(struct IXMLDOMNode *, void *, int, unsigned int))parseMmsConfigurationNode,
                         (struct WWAN_PROFILE *)a2,
                         0,
                         a4);
              if ( result )
                return result;
LABEL_104:
              result = XcGetNodeEnumValue(
                         a1,
                         L"MBNProfileV2:IsPurchaseProfile",
                         (const struct _XC_STRING_VALUE_MAPPING *)&off_180015490,
                         4u,
                         (unsigned int *)a2 + 1120,
                         1,
                         0,
                         0);
              if ( result )
                return result;
              result = XcGetNodeStringValue(a1, L"MBNProfileV2:DisplayProviderName", a2 + 2244, 0x15u, 1, 0, 0);
              if ( result )
                return result;
              result = XcGetNodeEnumValue(
                         a1,
                         L"MBNProfileV3:IsAdditionalPdpContextProfile",
                         (const struct _XC_STRING_VALUE_MAPPING *)&off_180015490,
                         4u,
                         (unsigned int *)a2 + 1155,
                         1,
                         0,
                         0);
              if ( result )
                return result;
              result = XcGetNodeEnumValue(
                         a1,
                         L"MBNProfileV3:IsTetheringProfile",
                         (const struct _XC_STRING_VALUE_MAPPING *)&off_180015490,
                         4u,
                         (unsigned int *)a2 + 1156,
                         1,
                         0,
                         0);
              if ( result )
                return result;
              if ( (*((_DWORD *)a2 + 1155) || *((_DWORD *)a2 + 1156) || *((_DWORD *)a2 + 1173))
                && (*((_DWORD *)a2 + 768) || *((_DWORD *)a2 + 799)) )
              {
                return 1206;
              }
              if ( a4 <= 1 )
              {
                v33 = a2 + 2622;
              }
              else
              {
                v32 = L"MBNProfileV9:FollowInternetConnectionEnablementPolicy";
                if ( a4 <= 2 )
                  v32 = L"MBNProfileV5:FollowInternetConnectionEnablementPolicy";
                result = XcGetNodeEnumValue(
                           a1,
                           v32,
                           (const struct _XC_STRING_VALUE_MAPPING *)&off_180015490,
                           4u,
                           (unsigned int *)a2 + 1310,
                           1,
                           0,
                           0);
                if ( result )
                  return result;
                v33 = a2 + 2622;
                v34 = L"MBNProfileV9:FollowInternetConnectionRoamingPolicy";
                if ( a4 <= 2 )
                  v34 = L"MBNProfileV5:FollowInternetConnectionRoamingPolicy";
                result = XcGetNodeEnumValue(
                           a1,
                           v34,
                           (const struct _XC_STRING_VALUE_MAPPING *)&off_180015490,
                           4u,
                           (unsigned int *)a2 + 1311,
                           1,
                           0,
                           0);
                if ( result )
                  return result;
              }
              if ( *((_DWORD *)a2 + 1310) || *(_DWORD *)v33 )
              {
                NodeStringValue = 0;
                if ( !*((_DWORD *)a2 + 1155) || a4 == 1 )
                  return 1206;
              }
              else
              {
                NodeStringValue = 0;
              }
              if ( a4 > 1 )
              {
                v35 = L"MBNProfileV9:DisplayProviderNameLong";
                if ( a4 <= 2 )
                  v35 = L"MBNProfileV6:DisplayProviderNameLong";
                result = XcGetNodeStringValue(a1, v35, a2 + 2244, 0x41u, 1, a2 + 2244, (int *)a2 + 1121);
                if ( result )
                  return result;
              }
              if ( a4 == 2 )
              {
                if ( *((_DWORD *)a2 + 769) == 3 && !*((_DWORD *)a2 + 1120) )
                {
                  v39 = 0;
                  if ( !XcGetNodeDWORDValue(
                          a1,
                          L"MBNProfileV8:AutoConnectOrder",
                          (unsigned int *)a2 + 1312,
                          v31,
                          0xFFFFFFFF,
                          1,
                          0xFFFFFFFF,
                          (int *)&v39)
                    && v39
                    && (unsigned int)(*((_DWORD *)a2 + 1312) - 1) > 0xFFFE )
                  {
                    return 1206;
                  }
                }
              }
              else if ( a4 < 2 )
              {
LABEL_141:
                if ( a4 != 3 )
                  return result;
                result = XcGetNodeDWORDValue(
                           a1,
                           L"MBNProfileV9:RulePrecedence",
                           (unsigned int *)a2 + 1312,
                           v31,
                           0xFFFFFFFF,
                           0,
                           0xFFFFFFFF,
                           0);
                if ( result )
                  return result;
                result = _parseNode(
                           a1,
                           L"MBNProfileV9:TrafficDescriptor",
                           0,
                           (unsigned int (*)(struct IXMLDOMNode *, void *, int, unsigned int))_parseTrafficDescriptor,
                           (struct WWAN_PROFILE *)a2,
                           0,
                           3u);
                if ( result )
                  return result;
                result = _parseNode(
                           a1,
                           L"MBNProfileV9:RouteSelectionDescriptors",
                           0,
                           (unsigned int (*)(struct IXMLDOMNode *, void *, int, unsigned int))_parseRouteSelectionDescriptors,
                           (struct WWAN_PROFILE *)a2,
                           0,
                           3u);
                if ( result )
                  return result;
                if ( !*((_DWORD *)a2 + 1313) )
                  return NodeStringValue;
                if ( (a2[1600] & 1) == 0 )
                {
                  v36 = *((_DWORD *)a2 + 1314);
                  if ( *((_DWORD *)a2 + 1315) )
                  {
                    if ( !v36 && !*((_DWORD *)a2 + 1384) )
                      return NodeStringValue;
                  }
                  else if ( v36 || *((_DWORD *)a2 + 1384) )
                  {
                    return NodeStringValue;
                  }
                }
                return 1206;
              }
              result = _parseNode(
                         a1,
                         L"MBNProfileV9:RATApplicabilityCheck",
                         1,
                         parseRATApplicability,
                         (struct WWAN_PROFILE *)a2,
                         0,
                         a4);
              if ( result )
                return result;
              goto LABEL_141;
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c4a0  mov     [rsp-38h+arg_0], rbx
0x18000c4a5  push    rbp
0x18000c4a6  push    rsi
0x18000c4a7  push    rdi
0x18000c4a8  push    r12
0x18000c4aa  push    r13
0x18000c4ac  push    r14
0x18000c4ae  push    r15
0x18000c4b0  mov     rbp, rsp
0x18000c4b3  sub     rsp, 50h
0x18000c4b7  mov     ebx, r9d
0x18000c4ba  mov     r14d, r8d
0x18000c4bd  mov     rdi, rdx
0x18000c4c0  mov     rsi, rcx
0x18000c4c3  mov     r13d, 3
0x18000c4c9  cmp     r9d, r13d
0x18000c4cc  jb      short loc_18000C4D7
0x18000c4ce  lea     rdx, aMbnprofilev9Na; "MBNProfileV9:Name"
0x18000c4d5  jmp     short loc_18000C4EC
0x18000c4d7  lea     rdx, aMbnprofilev4Na; "MBNProfileV4:Name"
0x18000c4de  lea     rax, aMbnprofileName; "MBNProfile:Name"
0x18000c4e5  cmp     ebx, 2
0x18000c4e8  cmovnz  rdx, rax; unsigned __int16 *
0x18000c4ec  xor     r12d, r12d
0x18000c4ef  mov     [rsp+50h+var_20], r12; int *
0x18000c4f4  mov     [rsp+50h+var_28], r12; unsigned __int16 *
0x18000c4f9  mov     dword ptr [rsp+50h+var_30], r12d; int
0x18000c4fe  mov     r15d, 100h
0x18000c504  mov     r9d, r15d; unsigned __int64
0x18000c507  mov     r8, rdi; unsigned __int16 *
0x18000c50a  call    ?XcGetNodeStringValue@@YAKPEAUIXMLDOMNode@@PEBGPEAG_KH1PEAH@Z; XcGetNodeStringValue(IXMLDOMNode *,ushort const *,ushort *,unsigned __int64,int,ushort const *,int *)
0x18000c50f  test    eax, eax
0x18000c511  jnz     loc_18000CF5D
0x18000c517  cmp     ebx, r13d
0x18000c51a  jb      short loc_18000C525
0x18000c51c  lea     rdx, aMbnprofilev9De; "MBNProfileV9:Description"
0x18000c523  jmp     short loc_18000C53A
0x18000c525  lea     rdx, aMbnprofilev4De; "MBNProfileV4:Description"
0x18000c52c  lea     rax, aMbnprofileDesc; "MBNProfile:Description"
0x18000c533  cmp     ebx, 2
0x18000c536  cmovnz  rdx, rax
0x18000c53a  lea     r8, [rdi+200h]
0x18000c541  mov     [rsp+50h+var_30], r12
0x18000c546  mov     r9, r15
0x18000c549  mov     rcx, rsi
0x18000c54c  call    _getOptNodeStringValue
0x18000c551  test    eax, eax
0x18000c553  jnz     loc_18000CF5D
0x18000c559  cmp     ebx, r13d
0x18000c55c  jb      short loc_18000C567
0x18000c55e  lea     rdx, aMbnprofilev9Ic; "MBNProfileV9:ICONFilePath"
0x18000c565  jmp     short loc_18000C57C
0x18000c567  lea     rdx, aMbnprofilev4Ic; "MBNProfileV4:ICONFilePath"
0x18000c56e  lea     rax, aMbnprofileIcon; "MBNProfile:ICONFilePath"
0x18000c575  cmp     ebx, 2
0x18000c578  cmovnz  rdx, rax
0x18000c57c  lea     r8, [rdi+400h]
0x18000c583  mov     [rsp+50h+var_30], r12
0x18000c588  mov     r9d, 400h
0x18000c58e  mov     rcx, rsi
0x18000c591  call    _getOptNodeStringValue
0x18000c596  test    eax, eax
0x18000c598  jnz     loc_18000CF5D
0x18000c59e  cmp     ebx, r13d
0x18000c5a1  jb      short loc_18000C5AC
0x18000c5a3  lea     rdx, aMbnprofilev9Is; "MBNProfileV9:IsDefault"
0x18000c5aa  jmp     short loc_18000C5C1
0x18000c5ac  lea     rdx, aMbnprofilev4Is_0; "MBNProfileV4:IsDefault"
0x18000c5b3  lea     rax, aMbnprofileIsde; "MBNProfile:IsDefault"
0x18000c5ba  cmp     ebx, 2
0x18000c5bd  cmovnz  rdx, rax; unsigned __int16 *
0x18000c5c1  lea     rax, [rdi+0C00h]
0x18000c5c8  mov     [rsp+50h+var_18], r12; int *
0x18000c5cd  mov     dword ptr [rsp+50h+var_20], r12d; unsigned int
0x18000c5d2  mov     dword ptr [rsp+50h+var_28], r12d; int
0x18000c5d7  mov     [rsp+50h+var_30], rax; unsigned int *
0x18000c5dc  mov     r9d, 4; unsigned int
0x18000c5e2  lea     r8, off_180015490; struct _XC_STRING_VALUE_MAPPING *
0x18000c5e9  mov     rcx, rsi; struct IXMLDOMNode *
0x18000c5ec  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x18000c5f1  test    eax, eax
0x18000c5f3  jnz     loc_18000CF5D
0x18000c5f9  cmp     ebx, r13d
0x18000c5fc  jb      short loc_18000C607
0x18000c5fe  lea     rdx, aMbnprofilev9Pr_1; "MBNProfileV9:ProfileCreationType"
0x18000c605  jmp     short loc_18000C61C
0x18000c607  lea     rdx, aMbnprofilev4Pr_0; "MBNProfileV4:ProfileCreationType"
0x18000c60e  lea     rax, aMbnprofileProf; "MBNProfile:ProfileCreationType"
0x18000c615  cmp     ebx, 2
0x18000c618  cmovnz  rdx, rax; unsigned __int16 *
0x18000c61c  lea     r15, [rdi+0C04h]
0x18000c623  mov     [rsp+50h+var_18], r12; int *
0x18000c628  mov     dword ptr [rsp+50h+var_20], r12d; unsigned int
0x18000c62d  mov     dword ptr [rsp+50h+var_28], 1; int
0x18000c635  mov     [rsp+50h+var_30], r15; unsigned int *
0x18000c63a  mov     r9d, 6; unsigned int
0x18000c640  lea     r8, ?_creationType@@3QBU_XC_STRING_VALUE_MAPPING@@B; struct _XC_STRING_VALUE_MAPPING *
0x18000c647  mov     rcx, rsi; struct IXMLDOMNode *
0x18000c64a  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x18000c64f  test    eax, eax
0x18000c651  jnz     loc_18000CF5D
0x18000c657  cmp     ebx, 2
0x18000c65a  jnz     short loc_18000C6AA
0x18000c65c  mov     [rbp+arg_18], r12d
0x18000c660  mov     [rsp+50h+var_18], r12; int *
0x18000c665  mov     dword ptr [rsp+50h+var_20], r12d; unsigned int
0x18000c66a  mov     dword ptr [rsp+50h+var_28], 1; int
0x18000c672  lea     rax, [rbp+arg_18]
0x18000c676  mov     [rsp+50h+var_30], rax; unsigned int *
0x18000c67b  lea     r9d, [rbx+2]; unsigned int
0x18000c67f  lea     r8, off_180015490; struct _XC_STRING_VALUE_MAPPING *
0x18000c686  lea     rdx, aMbnprofilev7Is; "MBNProfileV7:IsBasedOnModemProvisionedC"...
0x18000c68d  mov     rcx, rsi; struct IXMLDOMNode *
0x18000c690  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x18000c695  test    eax, eax
0x18000c697  jnz     loc_18000CF5D
0x18000c69d  cmp     [rbp+arg_18], r12d
0x18000c6a1  jz      short loc_18000C6AA
0x18000c6a3  mov     dword ptr [r15], 4
0x18000c6aa  mov     ecx, r12d
0x18000c6ad  cmp     ebx, 1
0x18000c6b0  setnz   cl
0x18000c6b3  test    r14d, r14d
0x18000c6b6  jnz     short loc_18000C709
0x18000c6b8  cmp     ebx, r13d
0x18000c6bb  jb      short loc_18000C6C6
0x18000c6bd  lea     rdx, aMbnprofilev9Su; "MBNProfileV9:SubscriberID"
0x18000c6c4  jmp     short loc_18000C6DB
0x18000c6c6  lea     rdx, aMbnprofilev4Su; "MBNProfileV4:SubscriberID"
0x18000c6cd  lea     rax, aMbnprofileSubs; "MBNProfile:SubscriberID"
0x18000c6d4  cmp     ebx, 2
0x18000c6d7  cmovnz  rdx, rax; unsigned __int16 *
0x18000c6db  lea     r14, [rdi+0C08h]
0x18000c6e2  mov     [rsp+50h+var_20], r12; int *
0x18000c6e7  mov     [rsp+50h+var_28], r12; unsigned __int16 *
0x18000c6ec  mov     dword ptr [rsp+50h+var_30], ecx; int
0x18000c6f0  mov     r9d, 10h; unsigned __int64
0x18000c6f6  mov     r8, r14; unsigned __int16 *
0x18000c6f9  mov     rcx, rsi; struct IXMLDOMNode *
0x18000c6fc  call    ?XcGetNodeStringValue@@YAKPEAUIXMLDOMNode@@PEBGPEAG_KH1PEAH@Z; XcGetNodeStringValue(IXMLDOMNode *,ushort const *,ushort *,unsigned __int64,int,ushort const *,int *)
0x18000c701  mov     r15d, eax
0x18000c704  jmp     loc_18000C7F5
0x18000c709  mov     [rbp+arg_8], r12
0x18000c70d  mov     [rbp+lpMem], r12
0x18000c711  mov     [rbp+arg_18], r12d
0x18000c715  cmp     ebx, r13d
0x18000c718  jb      short loc_18000C723
0x18000c71a  lea     rdx, aMbnprofilev9Su; "MBNProfileV9:SubscriberID"
0x18000c721  jmp     short loc_18000C738
0x18000c723  lea     rdx, aMbnprofilev4Su; "MBNProfileV4:SubscriberID"
0x18000c72a  lea     rax, aMbnprofileSubs; "MBNProfile:SubscriberID"
0x18000c731  cmp     ebx, 2
0x18000c734  cmovnz  rdx, rax; unsigned __int16 *
0x18000c738  lea     r8, [rbp+arg_8]; struct IXMLDOMNode **
0x18000c73c  mov     rcx, rsi; struct IXMLDOMNode *
0x18000c73f  call    ?XcGetSingleNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; XcGetSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18000c744  mov     r14d, eax
0x18000c747  cmp     eax, 490h
0x18000c74c  jnz     short loc_18000C763
0x18000c74e  cmp     ebx, 1
0x18000c751  jz      short loc_18000C768
0x18000c753  lea     r14, [rdi+0C08h]
0x18000c75a  mov     [r14], r12w
0x18000c75e  mov     r15d, r12d
0x18000c761  jmp     short loc_18000C7DF
0x18000c763  test    r14d, r14d
0x18000c766  jz      short loc_18000C786
0x18000c768  mov     rcx, [rbp+arg_8]
0x18000c76c  test    rcx, rcx
0x18000c76f  jz      short loc_18000C77E
0x18000c771  mov     rax, [rcx]
0x18000c774  mov     rax, [rax+10h]
0x18000c778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c77d  nop
0x18000c77e  mov     eax, r14d
0x18000c781  jmp     loc_18000CF5D
0x18000c786  lea     r9, [rbp+arg_18]; unsigned int *
0x18000c78a  lea     r8, [rbp+lpMem]; unsigned __int8 **
0x18000c78e  mov     rcx, [rbp+arg_8]; struct IXMLDOMNode *
0x18000c792  call    ?XcGetNodeHexBinaryValue@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAEPEAK@Z; XcGetNodeHexBinaryValue(IXMLDOMNode *,ushort const *,uchar * *,ulong *)
0x18000c797  mov     r14d, eax
0x18000c79a  test    eax, eax
0x18000c79c  jz      short loc_18000C7B6
0x18000c79e  mov     rcx, [rbp+arg_8]
0x18000c7a2  test    rcx, rcx
0x18000c7a5  jz      short loc_18000C7B4
0x18000c7a7  mov     rdx, [rcx]
0x18000c7aa  mov     rax, [rdx+10h]
0x18000c7ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7b3  nop
0x18000c7b4  jmp     short loc_18000C77E
0x18000c7b6  lea     r14, [rdi+0C08h]
0x18000c7bd  mov     r9d, 20h ; ' '
0x18000c7c3  mov     r8, r14
0x18000c7c6  mov     edx, [rbp+arg_18]
0x18000c7c9  mov     rcx, [rbp+lpMem]
0x18000c7cd  call    _decryptData
0x18000c7d2  mov     r15d, eax
0x18000c7d5  mov     rcx, [rbp+lpMem]; lpMem
0x18000c7d9  call    ?Xc_Process_user_free@@YAXPEAX@Z; Xc_Process_user_free(void *)
0x18000c7de  nop
0x18000c7df  mov     rcx, [rbp+arg_8]
0x18000c7e3  test    rcx, rcx
0x18000c7e6  jz      short loc_18000C7F5
0x18000c7e8  mov     rax, [rcx]
0x18000c7eb  mov     rax, [rax+10h]
0x18000c7ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7f4  nop
0x18000c7f5  test    r15d, r15d
0x18000c7f8  jz      short loc_18000C802
0x18000c7fa  mov     eax, r15d
0x18000c7fd  jmp     loc_18000CF5D
0x18000c802  mov     rcx, r14
0x18000c805  call    _validateSubId
0x18000c80a  test    eax, eax
0x18000c80c  jnz     loc_18000CF5D
0x18000c812  mov     eax, r12d
0x18000c815  mov     r14d, 1
0x18000c81b  cmp     ebx, r14d
0x18000c81e  setz    al
0x18000c821  lea     r15d, [r14+1]
0x18000c825  cmp     ebx, r13d
0x18000c828  jb      short loc_18000C833
0x18000c82a  lea     rdx, aMbnprofilev9Si; "MBNProfileV9:SimIccID"
0x18000c831  jmp     short loc_18000C848
0x18000c833  lea     rdx, aMbnprofilev4Si; "MBNProfileV4:SimIccID"
0x18000c83a  lea     rcx, aMbnprofileSimi; "MBNProfile:SimIccID"
0x18000c841  cmp     ebx, r15d
0x18000c844  cmovnz  rdx, rcx; unsigned __int16 *
0x18000c848  lea     r8, [rdi+0C28h]; unsigned __int16 *
0x18000c84f  mov     [rsp+50h+var_20], r12; int *
0x18000c854  mov     [rsp+50h+var_28], r12; unsigned __int16 *
0x18000c859  mov     dword ptr [rsp+50h+var_30], eax; int
0x18000c85d  mov     r9d, 15h; unsigned __int64
0x18000c863  mov     rcx, rsi; struct IXMLDOMNode *
0x18000c866  call    ?XcGetNodeStringValue@@YAKPEAUIXMLDOMNode@@PEBGPEAG_KH1PEAH@Z; XcGetNodeStringValue(IXMLDOMNode *,ushort const *,ushort *,unsigned __int64,int,ushort const *,int *)
0x18000c86b  test    eax, eax
0x18000c86d  jnz     loc_18000CF5D
0x18000c873  cmp     ebx, r13d
0x18000c876  jb      short loc_18000C881
0x18000c878  lea     rdx, aMbnprofilev9Ho; "MBNProfileV9:HomeProviderName"
0x18000c87f  jmp     short loc_18000C896
0x18000c881  lea     rdx, aMbnprofilev4Ho; "MBNProfileV4:HomeProviderName"
0x18000c888  lea     rax, aMbnprofileHome; "MBNProfile:HomeProviderName"
0x18000c88f  cmp     ebx, r15d
0x18000c892  cmovnz  rdx, rax; unsigned __int16 *
0x18000c896  lea     r8, [rdi+0C52h]; unsigned __int16 *
0x18000c89d  mov     [rsp+50h+var_20], r12; int *
0x18000c8a2  mov     [rsp+50h+var_28], r12; unsigned __int16 *
0x18000c8a7  mov     dword ptr [rsp+50h+var_30], r14d; int
0x18000c8ac  mov     r9d, 15h; unsigned __int64
0x18000c8b2  mov     rcx, rsi; struct IXMLDOMNode *
0x18000c8b5  call    ?XcGetNodeStringValue@@YAKPEAUIXMLDOMNode@@PEBGPEAG_KH1PEAH@Z; XcGetNodeStringValue(IXMLDOMNode *,ushort const *,ushort *,unsigned __int64,int,ushort const *,int *)
0x18000c8ba  test    eax, eax
0x18000c8bc  jnz     loc_18000CF5D
0x18000c8c2  cmp     ebx, r13d
0x18000c8c5  jb      short loc_18000C8D0
0x18000c8c7  lea     rdx, aMbnprofilev9Co_3; "MBNProfileV9:ConnectionMode"
0x18000c8ce  jmp     short loc_18000C8E5
0x18000c8d0  lea     rdx, aMbnprofilev4Co_2; "MBNProfileV4:ConnectionMode"
0x18000c8d7  lea     rax, aMbnprofileConn_0; "MBNProfile:ConnectionMode"
0x18000c8de  cmp     ebx, r15d
0x18000c8e1  cmovnz  rdx, rax; unsigned __int16 *
0x18000c8e5  lea     rax, [rdi+0C7Ch]
0x18000c8ec  mov     [rsp+50h+var_18], r12; int *
0x18000c8f1  mov     dword ptr [rsp+50h+var_20], r12d; unsigned int
0x18000c8f6  mov     dword ptr [rsp+50h+var_28], r14d; int
0x18000c8fb  mov     [rsp+50h+var_30], rax; unsigned int *
0x18000c900  mov     r9d, r13d; unsigned int
0x18000c903  lea     r8, ?_connMode@@3QBU_XC_STRING_VALUE_MAPPING@@B; struct _XC_STRING_VALUE_MAPPING *
0x18000c90a  mov     rcx, rsi; struct IXMLDOMNode *
0x18000c90d  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x18000c912  test    eax, eax
0x18000c914  jnz     loc_18000CF5D
0x18000c91a  cmp     ebx, r13d
0x18000c91d  jb      short loc_18000C928
0x18000c91f  lea     rdx, aMbnprofilev9Co_1; "MBNProfileV9:Context"
0x18000c926  jmp     short loc_18000C93D
0x18000c928  lea     rdx, aMbnprofilev4Co_3; "MBNProfileV4:Context"
0x18000c92f  lea     rax, aMbnprofileCont; "MBNProfile:Context"
0x18000c936  cmp     ebx, r15d
0x18000c939  cmovnz  rdx, rax; unsigned __int16 *
0x18000c93d  mov     dword ptr [rsp+50h+var_20], ebx; unsigned int
0x18000c941  mov     dword ptr [rsp+50h+var_28], r12d; int
0x18000c946  mov     [rsp+50h+var_30], rdi; struct WWAN_PROFILE *
0x18000c94b  lea     r9, ?_parseContextNode@@YAKPEAUIXMLDOMNode@@PEAUWWAN_PROFILE@@HK@Z; unsigned int (*)(struct IXMLDOMNode *, void *, int, unsigned int)
0x18000c952  mov     r8d, r14d; int
0x18000c955  mov     rcx, rsi; struct IXMLDOMNode *
0x18000c958  call    ?_parseNode@@YAKPEAUIXMLDOMNode@@PEBGHP6AK0PEAXHK@ZPEAUWWAN_PROFILE@@HK@Z; _parseNode(IXMLDOMNode *,ushort const *,int,ulong (*)(IXMLDOMNode *,void *,int,ulong),WWAN_PROFILE *,int,ulong)
0x18000c95d  test    eax, eax
0x18000c95f  jnz     loc_18000CF5D
0x18000c965  cmp     ebx, r13d
0x18000c968  jb      short loc_18000C973
0x18000c96a  lea     rdx, aMbnprofilev9Da; "MBNProfileV9:DataRoamingPartners"
0x18000c971  jmp     short loc_18000C988
0x18000c973  lea     rdx, aMbnprofilev4Da; "MBNProfileV4:DataRoamingPartners"
0x18000c97a  lea     rax, aMbnprofileData; "MBNProfile:DataRoamingPartners"
0x18000c981  cmp     ebx, r15d
0x18000c984  cmovnz  rdx, rax; unsigned __int16 *
0x18000c988  mov     dword ptr [rsp+50h+var_20], ebx; unsigned int
  ... truncated ...
```
