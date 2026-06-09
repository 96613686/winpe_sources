# ProtobufHelper::WriteElement(UIAutomationCoreProto::ElementRefRetMsg &,IUiaNode *,IServerConnection *,bool)

- ea: `0x180067d64`
- end: `0x18006865e`
- name: `?WriteElement@ProtobufHelper@@SAXAEAVElementRefRetMsg@UIAutomationCoreProto@@PEAVIUiaNode@@PEAVIServerConnection@@_N@Z`
- size: `2298`
- prototype: `void __fastcall(struct UIAutomationCoreProto::ElementRefRetMsg *, struct IUiaNode *, struct IServerConnection *, bool)`
- caller_count: `18`
- callee_count: `34`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180023028`
- `0x1800239fc`
- `0x180069100`
- `0x180069440`
- `0x1800c4ba0`
- `0x1800c4ff0`
- `0x1800d38a0`
- `0x18014fa30`
- `0x18015b774`
- `0x18017bc58`
- `0x18018fbd0`
- `0x180190570`
- `0x180190c20`
- `0x180190e44`
- `0x180194950`
- `0x1801aec94`
- `0x1801af118`
- `0x1801d8df0`

## callees

- `0x1800206e8`
- `0x18002f580`
- `0x180030cd4`
- `0x180030ee4`
- `0x180032724`
- `0x18003c820`
- `0x18004c8c0`
- `0x18004dd30`
- `0x18004e194`
- `0x18004e318`
- `0x18004e410`
- `0x18004e5f8`
- `0x18004e668`
- `0x18004e6c8`
- `0x180067d64`
- `0x180068db8`
- `0x180068f08`
- `0x1800690c4`
- `0x1800be9c8`
- `0x180181488`
- `0x180189804`
- `0x1801a9630`
- `0x1801ad0e0`
- `0x1801b7238`
- `0x1801b799c`
- `0x1801e8320`
- `0x1801e8344`
- `0x1801e88a0`
- `0x1801e9234`
- `0x1801eae30`
- `0x1801eafa0`
- `0x1801fc5d8`
- `0x1801fc640`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800682bc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800682bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068316`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068316`
- `OLEAUT32!__imp_SysFreeString` at `0x180067ff8`
- `OLEAUT32!__imp_SysFreeString` at `0x18006822e`
- `OLEAUT32!__imp_SysFreeString` at `0x180068330`
- `OLEAUT32!__imp_SysFreeString` at `0x180068360`
- `OLEAUT32!__imp_SysFreeString` at `0x180067ff8`
- `OLEAUT32!__imp_SysFreeString` at `0x18006822e`
- `OLEAUT32!__imp_SysFreeString` at `0x180068330`
- `OLEAUT32!__imp_SysFreeString` at `0x180068360`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180067e85`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800681f8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18006839a`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180067e85`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800681f8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18006839a`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180068078`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180068078`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800680ec`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800680ec`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800680cf`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800680cf`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180068115`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180068115`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180068190`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180068410`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180068190`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180068410`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x180068096`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x180068096`

## string_xrefs

- `0x1800683ef`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x18006848b`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x18006853d`: `onecore\windows\accessibletech\uiautomationcore\ElementPatternRef.h`
- `0x1800681a6`: `onecore\windows\accessibletech\uiautomationcore\protobufhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall ProtobufHelper::WriteElement(
        struct UIAutomationCoreProto::ElementRefRetMsg *a1,
        struct IUiaNode *a2,
        RTL_SRWLOCK *a3,
        char a4)
{
  RTL_SRWLOCK *v4; // r15
  char v7; // r13
  UiaNode *v8; // rdi
  int v9; // eax
  char v10; // r14
  UIAutomationCoreProto::ElementExtraInfoMsg *v11; // rsi
  _QWORD *v12; // rcx
  struct UIAutomationCoreProto::ProviderEntryPointMsg *v13; // rax
  _QWORD *v14; // rcx
  unsigned int v15; // edx
  _BYTE *v16; // rcx
  _QWORD *v17; // rcx
  unsigned int v18; // edx
  SAFEARRAY *v19; // rsi
  __int64 v20; // r13
  struct google::protobuf::Arena *v21; // rcx
  _DWORD *v22; // rbx
  int i; // r15d
  HRESULT Vartype; // eax
  int v25; // edi
  unsigned __int64 v26; // rax
  _DWORD *v27; // r9
  __int64 v28; // r8
  __int64 j; // rdi
  ProviderEntryPoint *v30; // rdi
  unsigned int v31; // edx
  UIAutomationCoreProto::UiaPropertyConditionMsg *v32; // rdi
  struct UIAutomationCoreProto::GuidMsg *v33; // rax
  const unsigned __int16 *v34; // rbx
  struct UIAutomationCoreProto::WstringMsg *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // r9
  unsigned int v39; // eax
  struct UIAutomationCoreProto::CrossMachinePlaceHolderMsg *v40; // rax
  int v41; // [rsp+20h] [rbp-E0h]
  VARTYPE pvt; // [rsp+34h] [rbp-CCh] BYREF
  SAFEARRAY *psa; // [rsp+38h] [rbp-C8h] BYREF
  ProviderEntryPoint *v45; // [rsp+40h] [rbp-C0h] BYREF
  void *Block; // [rsp+48h] [rbp-B8h]
  LONG plUbound; // [rsp+50h] [rbp-B0h] BYREF
  int v48; // [rsp+54h] [rbp-ACh]
  SAFEARRAY *v49; // [rsp+58h] [rbp-A8h]
  unsigned int v50; // [rsp+60h] [rbp-A0h]
  void *ppvData; // [rsp+68h] [rbp-98h] BYREF
  struct IServerConnection *v52; // [rsp+70h] [rbp-90h]
  SAFEARRAY *v53; // [rsp+78h] [rbp-88h] BYREF
  ProviderEntryPoint *v54; // [rsp+80h] [rbp-80h] BYREF
  char v55; // [rsp+88h] [rbp-78h]
  GUID Buf1; // [rsp+8Ch] [rbp-74h] BYREF
  BSTR bstrString; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v58[40]; // [rsp+A8h] [rbp-58h] BYREF
  char v59; // [rsp+D0h] [rbp-30h]
  int v60; // [rsp+E0h] [rbp-20h] BYREF
  ProviderEntryPoint *v61; // [rsp+E8h] [rbp-18h] BYREF
  char v62; // [rsp+F0h] [rbp-10h]
  GUID v63; // [rsp+F4h] [rbp-Ch]
  BSTR v64; // [rsp+108h] [rbp+8h]
  _BYTE v65[40]; // [rsp+110h] [rbp+10h] BYREF
  char v66; // [rsp+138h] [rbp+38h]
  SAFEARRAY *v67; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v4 = a3;
  v52 = (struct IServerConnection *)a3;
  v7 = 0;
  v48 = 0;
  v61 = 0;
  v62 &= 0xC0u;
  v63 = GUID_NULL;
  v64 = 0;
  v66 = 0;
  v67 = 0;
  if ( a2 )
  {
    v8 = (UiaNode *)(*(__int64 (__fastcall **)(struct IUiaNode *))(*(_QWORD *)a2 + 32LL))(a2);
    if ( v8 )
    {
      GetRuntimeIdSafeArray(&psa, a2);
      LODWORD(v45) = 0;
      Block = 0;
      SafeArrayToRuntimeId(psa, &v45);
      v41 = 0;
      v60 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *, struct IUiaNode *, int *, ProviderEntryPoint **))v4->Ptr + 5))(
              v4,
              a2,
              &NodeMarker,
              &v45);
      UiaNode::GetElementExtraInfo(v8, (struct ElementExtraInfo *)&v61);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t>>>::operator=(
        &v67,
        &psa);
      if ( Block )
        operator delete(Block);
      LODWORD(v45) = 0;
      Block = 0;
      if ( psa )
        SafeArrayDestroy(psa);
    }
    else
    {
      v60 = 0;
      v39 = Error::InternalErrorWorker(L"Expecting object to be local");
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0xC4,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\ElementPatternRef.h",
        (const char *)v39,
        v41);
    }
  }
  else
  {
    v60 = 0;
  }
  v9 = v60;
  *((_DWORD *)a1 + 10) = v60;
  v10 = 1;
  if ( v9 )
  {
    v54 = v61;
    if ( v61 )
      (*(void (__fastcall **)(ProviderEntryPoint *))(*(_QWORD *)v61 + 8LL))(v61);
    v55 = v62;
    Buf1 = v63;
    bstrString = 0;
    v59 = 0;
    if ( v66 )
      std::_Optional_construct_base<CrossMachinePlaceholderInfo>::_Construct<CrossMachinePlaceholderInfo const &>(
        v58,
        v65);
    if ( v64 && (int)HrSysAllocString(v64, &bstrString) < 0 )
      Buf1 = GUID_NULL;
    v11 = (UIAutomationCoreProto::ElementExtraInfoMsg *)*((_QWORD *)a1 + 2);
    if ( !v11 )
    {
      v12 = (_QWORD *)(*((_QWORD *)a1 + 1) & 0xFFFFFFFFFFFFFFFCuLL);
      if ( (*((_BYTE *)a1 + 8) & 1) != 0 )
        v12 = (_QWORD *)*v12;
      v11 = (UIAutomationCoreProto::ElementExtraInfoMsg *)google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::ElementExtraInfoMsg,>(v12);
      *((_QWORD *)a1 + 2) = v11;
    }
    if ( v54 )
    {
      v13 = (struct UIAutomationCoreProto::ProviderEntryPointMsg *)*((_QWORD *)v11 + 2);
      if ( !v13 )
      {
        v14 = (_QWORD *)(*((_QWORD *)v11 + 1) & 0xFFFFFFFFFFFFFFFCuLL);
        if ( (*((_BYTE *)v11 + 8) & 1) != 0 )
          v14 = (_QWORD *)*v14;
        v13 = (struct UIAutomationCoreProto::ProviderEntryPointMsg *)google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::ProviderEntryPointMsg,>(v14);
        *((_QWORD *)v11 + 2) = v13;
      }
      ProviderEntryPoint::WriteToMessage(v54, v13);
    }
    if ( memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
    {
      v32 = UIAutomationCoreProto::ElementExtraInfoMsg::_internal_mutable_component_site(v11);
      v33 = UIAutomationCoreProto::UiaPropertyConditionMsg::_internal_mutable_property_id(v32);
      ProtobufHelper::WriteGuid(v33, &Buf1);
      v34 = bstrString;
      v35 = UIAutomationCoreProto::StructuredMarkupRangeGetMarkupWithMarkedRangeRequestMsg::_internal_mutable_language(v32);
      ProtobufHelper::WriteString(v35, v34, 1);
    }
    if ( v59 )
    {
      v40 = UIAutomationCoreProto::ElementExtraInfoMsg::_internal_mutable_cross_machine_placeholder(v11);
      CrossMachinePlaceholderInfo::WriteToMessage((CrossMachinePlaceholderInfo *)v58, v40);
    }
    v16 = (_BYTE *)*((_QWORD *)v11 + 6);
    if ( !v16 )
    {
      v17 = (_QWORD *)(*((_QWORD *)v11 + 1) & 0xFFFFFFFFFFFFFFFCuLL);
      if ( (*((_BYTE *)v11 + 8) & 1) != 0 )
        v17 = (_QWORD *)*v17;
      v16 = (_BYTE *)google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::ElementExtraInfoFlagsMsg,>(v17);
      *((_QWORD *)v11 + 6) = v16;
    }
    v16[16] = v55 & 1;
    v16[17] = (v55 & 2) != 0;
    v16[18] = (v55 & 4) != 0;
    v16[19] = (v55 & 8) != 0;
    v16[20] = (v55 & 0x10) != 0;
    v16[21] = (v55 & 0x20) != 0;
    if ( v59 )
      CrossMachinePlaceholderInfo::`scalar deleting destructor'((CrossMachinePlaceholderInfo *)v58, v15);
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v54);
  }
  ElementRefRet::TryGetRuntimeIdCopy(&v60, &v53);
  v19 = v53;
  if ( v53 )
  {
    v20 = *((_QWORD *)a1 + 4);
    if ( !v20 )
    {
      v21 = (struct google::protobuf::Arena *)(*((_QWORD *)a1 + 1) & 0xFFFFFFFFFFFFFFFCuLL);
      if ( (*((_BYTE *)a1 + 8) & 1) != 0 )
        v21 = *(struct google::protobuf::Arena **)v21;
      v20 = google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::IntArrayMsg,>(v21);
      *((_QWORD *)a1 + 4) = v20;
    }
    if ( !v19 )
    {
      google::protobuf::RepeatedField<bool>::Clear(v20 + 16);
LABEL_61:
      v7 = v48;
      goto LABEL_62;
    }
    v22 = 0;
    v45 = 0;
    v50 = 0;
    ppvData = 0;
    i = 0;
    v49 = v19;
    if ( SafeArrayGetDim(v19) == 1 )
    {
      pvt = 0;
      Vartype = SafeArrayGetVartype(v49, &pvt);
      v25 = Vartype;
      if ( Vartype < 0 )
      {
        v37 = 95;
      }
      else
      {
        if ( pvt != 3 && pvt != 22 )
        {
          v38 = 2147942487LL;
          v25 = -2147024809;
          v37 = 106;
          goto LABEL_110;
        }
        LODWORD(psa) = 0;
        plUbound = 0;
        Vartype = SafeArrayGetLBound(v49, 1u, (LONG *)&psa);
        v25 = Vartype;
        if ( Vartype < 0 )
        {
          v37 = 111;
        }
        else
        {
          Vartype = SafeArrayGetUBound(v49, 1u, &plUbound);
          v25 = Vartype;
          if ( Vartype < 0 )
          {
            v37 = 112;
          }
          else
          {
            v50 = plUbound - (_DWORD)psa + 1;
            Vartype = SafeArrayAccessData(v49, &ppvData);
            v25 = Vartype;
            if ( Vartype >= 0 )
            {
              v26 = 4LL * v50;
              if ( !is_mul_ok(v50, 4u) )
                v26 = -1;
              v27 = operator new[](v26, (const struct std::nothrow_t *)std::nothrow);
              if ( v27 )
              {
                v28 = 0;
                for ( i = v50; (unsigned int)v28 < v50; i = v50 )
                {
                  v27[v28] = *((_DWORD *)ppvData + v28);
                  v28 = (unsigned int)(v28 + 1);
                }
                v22 = v27;
                v45 = (ProviderEntryPoint *)v27;
                if ( v49 )
                  SafeArrayUnaccessData(v49);
                v25 = 0;
                goto LABEL_56;
              }
              v25 = -2147024882;
              v36 = 162;
LABEL_99:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v36,
                (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
                (const char *)(unsigned int)v25,
                v41);
              if ( v49 )
                SafeArrayUnaccessData(v49);
LABEL_56:
              if ( v25 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x290,
                  (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\protobufhelper.cpp",
                  (const char *)(unsigned int)v25,
                  v41);
              for ( j = 0; (int)j < i; j = (unsigned int)(j + 1) )
              {
                LODWORD(psa) = v22[j];
                google::protobuf::RepeatedField<unsigned int>::Add(v20 + 16, &psa, v28);
              }
              operator delete(v22);
              v4 = (RTL_SRWLOCK *)v52;
              goto LABEL_61;
            }
            v37 = 115;
          }
        }
      }
      v38 = (unsigned int)Vartype;
    }
    else
    {
      v38 = 2147942487LL;
      v25 = -2147024809;
      v37 = 92;
    }
LABEL_110:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v37,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      (const char *)v38,
      v41);
    v36 = 159;
    goto LABEL_99;
  }
LABEL_62:
  if ( v19 )
    SafeArrayDestroy(v19);
  if ( !a4 || !v60 )
    goto LABEL_66;
  v54 = v61;
  if ( v61 )
    (*(void (__fastcall **)(ProviderEntryPoint *))(*(_QWORD *)v61 + 8LL))(v61);
  v55 = v62;
  Buf1 = v63;
  bstrString = 0;
  v59 = 0;
  if ( v66 )
    std::_Optional_construct_base<CrossMachinePlaceholderInfo>::_Construct<CrossMachinePlaceholderInfo const &>(
      v58,
      v65);
  if ( v64 && (int)HrSysAllocString(v64, &bstrString) < 0 )
    Buf1 = GUID_NULL;
  v7 = 2;
  if ( !v54 )
LABEL_66:
    v10 = 0;
  if ( (v7 & 2) != 0 )
  {
    if ( v59 )
      CrossMachinePlaceholderInfo::`scalar deleting destructor'((CrossMachinePlaceholderInfo *)v58, v18);
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v54);
  }
  if ( v10 )
  {
    v54 = v61;
    if ( v61 )
      (*(void (__fastcall **)(ProviderEntryPoint *))(*(_QWORD *)v61 + 8LL))(v61);
    v55 = v62;
    Buf1 = v63;
    bstrString = 0;
    v59 = 0;
    if ( v66 )
      std::_Optional_construct_base<CrossMachinePlaceholderInfo>::_Construct<CrossMachinePlaceholderInfo const &>(
        v58,
        v65);
    if ( v64 && (int)HrSysAllocString(v64, &bstrString) < 0 )
      Buf1 = GUID_NULL;
    v30 = v54;
    if ( (*(unsigned __int8 (__fastcall **)(RTL_SRWLOCK *, __int64))v4->Ptr)(v4, 2) )
    {
      AcquireSRWLockExclusive(v4 + 12);
      v52 = (struct IServerConnection *)&v4[12];
      v45 = v30;
      if ( v30 )
        (*(void (__fastcall **)(ProviderEntryPoint *))(*(_QWORD *)v30 + 8LL))(v30);
      Block = a1;
      std::vector<IServerConnection::WriteCompletionInfoQueueItem>::_Emplace_one_at_back<IServerConnection::WriteCompletionInfoQueueItem>(
        &v4[9],
        &v45);
      if ( v45 )
        (*(void (__fastcall **)(ProviderEntryPoint *))(*(_QWORD *)v45 + 16LL))(v45);
      if ( v4 != (RTL_SRWLOCK *)-96LL )
        ReleaseSRWLockExclusive(v4 + 12);
    }
    if ( v59 )
      CrossMachinePlaceholderInfo::`scalar deleting destructor'((CrossMachinePlaceholderInfo *)v58, v31);
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v54);
  }
  if ( v67 )
    SafeArrayDestroy(v67);
  if ( v66 )
    CrossMachinePlaceholderInfo::`scalar deleting destructor'((CrossMachinePlaceholderInfo *)v65, v18);
  if ( v64 )
  {
    SysFreeString(v64);
    v64 = 0;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v61);
}

```

## disassembly

```asm
0x180067d64  mov     [rsp-8+arg_18], rbx
0x180067d69  push    rbp
0x180067d6a  push    rsi
0x180067d6b  push    rdi
0x180067d6c  push    r12
0x180067d6e  push    r13
0x180067d70  push    r14
0x180067d72  push    r15
0x180067d74  lea     rbp, [rsp-60h]
0x180067d79  sub     rsp, 160h
0x180067d80  mov     rax, cs:__security_cookie
0x180067d87  xor     rax, rsp
0x180067d8a  mov     [rbp+90h+var_40], rax
0x180067d8e  mov     [rsp+190h+var_160], r9b
0x180067d93  mov     r15, r8
0x180067d96  mov     [rsp+190h+var_120], r8
0x180067d9b  mov     rbx, rdx
0x180067d9e  mov     r12, rcx
0x180067da1  xor     edi, edi
0x180067da3  mov     r13d, edi
0x180067da6  mov     [rsp+190h+var_13C], edi
0x180067daa  mov     [rbp+90h+var_A8], rdi
0x180067dae  and     [rbp+90h+var_A0], 0C0h
0x180067db2  mov     rax, qword ptr cs:GUID_NULL.Data1
0x180067db9  mov     [rbp+90h+var_9C], rax
0x180067dbd  mov     rax, qword ptr cs:GUID_NULL.Data4
0x180067dc4  mov     [rbp+90h+var_94], rax
0x180067dc8  mov     [rbp+90h+var_88], rdi
0x180067dcc  mov     [rbp+90h+var_58], dil
0x180067dd0  mov     [rbp+90h+var_50], rdi
0x180067dd4  test    rdx, rdx
0x180067dd7  jz      loc_18006851A
0x180067ddd  mov     rax, [rdx]
0x180067de0  mov     rcx, rdx
0x180067de3  mov     rax, [rax+20h]
0x180067de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067dec  mov     rdi, rax
0x180067def  xor     esi, esi
0x180067df1  test    rax, rax
0x180067df4  jz      loc_180068522
0x180067dfa  mov     rdx, rbx
0x180067dfd  lea     rcx, [rsp+190h+psa]
0x180067e02  call    ?GetRuntimeIdSafeArray@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUtagSAFEARRAY@@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAVIUiaNode@@@Z; GetRuntimeIdSafeArray(IUiaNode *)
0x180067e07  nop
0x180067e08  mov     dword ptr [rsp+190h+var_150], esi
0x180067e0c  mov     [rsp+190h+Block], rsi
0x180067e11  lea     rdx, [rsp+190h+var_150]
0x180067e16  mov     rcx, [rsp+190h+psa]
0x180067e1b  call    ?SafeArrayToRuntimeId@@YAXPEAUtagSAFEARRAY@@PEAU?$BasicArrayPair@H@@@Z; SafeArrayToRuntimeId(tagSAFEARRAY *,BasicArrayPair<int> *)
0x180067e20  mov     rax, [r15]
0x180067e23  mov     qword ptr [rsp+190h+var_170], rsi; int
0x180067e28  lea     r9, [rsp+190h+var_150]
0x180067e2d  lea     r8, ?NodeMarker@@3HA; int NodeMarker
0x180067e34  mov     rdx, rbx
0x180067e37  mov     rcx, r15
0x180067e3a  mov     rax, [rax+28h]
0x180067e3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067e43  mov     [rbp+90h+var_B0], eax
0x180067e46  lea     rdx, [rbp+90h+var_A8]; struct ElementExtraInfo *
0x180067e4a  mov     rcx, rdi; this
0x180067e4d  call    ?GetElementExtraInfo@UiaNode@@QEAAXPEAUElementExtraInfo@@@Z; UiaNode::GetElementExtraInfo(ElementExtraInfo *)
0x180067e52  lea     rdx, [rsp+190h+psa]
0x180067e57  lea     rcx, [rbp+90h+var_50]
0x180067e5b  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUtagSAFEARRAY@@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t>>> &&)
0x180067e60  nop
0x180067e61  mov     rcx, [rsp+190h+Block]; Block
0x180067e66  xor     edi, edi
0x180067e68  test    rcx, rcx
0x180067e6b  jz      short loc_180067E72
0x180067e6d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180067e72  mov     dword ptr [rsp+190h+var_150], edi
0x180067e76  mov     [rsp+190h+Block], rdi
0x180067e7b  mov     rcx, [rsp+190h+psa]; psa
0x180067e80  test    rcx, rcx
0x180067e83  jz      short loc_180067E8C
0x180067e85  call    cs:__imp_SafeArrayDestroy
0x180067e8b  nop
0x180067e8c  mov     eax, [rbp+90h+var_B0]
0x180067e8f  mov     [r12+28h], eax
0x180067e94  mov     r14d, 1
0x180067e9a  test    eax, eax
0x180067e9c  jz      loc_18006800B
0x180067ea2  mov     rcx, [rbp+90h+var_A8]
0x180067ea6  mov     [rbp+90h+var_110], rcx
0x180067eaa  test    rcx, rcx
0x180067ead  jz      short loc_180067EBC
0x180067eaf  mov     rax, [rcx]
0x180067eb2  mov     rax, [rax+8]
0x180067eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067ebb  nop
0x180067ebc  mov     al, [rbp+90h+var_A0]
0x180067ebf  mov     [rbp+90h+var_108], al
0x180067ec2  mov     rax, [rbp+90h+var_9C]
0x180067ec6  mov     [rbp+90h+Buf1], rax
0x180067eca  mov     rax, [rbp+90h+var_94]
0x180067ece  mov     [rbp+90h+var_FC], rax
0x180067ed2  mov     [rbp+90h+bstrString], rdi
0x180067ed6  mov     [rbp+90h+var_C0], dil
0x180067eda  cmp     [rbp+90h+var_58], dil
0x180067ede  jnz     loc_180068553
0x180067ee4  mov     rcx, [rbp+90h+var_88]; unsigned __int16 *
0x180067ee8  test    rcx, rcx
0x180067eeb  jnz     loc_180068565
0x180067ef1  mov     rsi, [r12+10h]
0x180067ef6  test    rsi, rsi
0x180067ef9  jnz     short loc_180067F1C
0x180067efb  mov     rcx, [r12+8]
0x180067f00  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180067f04  test    [r12+8], r14b
0x180067f09  jnz     loc_1800684C7
0x180067f0f  call    ??$CreateMaybeMessage@VElementExtraInfoMsg@UIAutomationCoreProto@@$$V@Arena@protobuf@google@@CAPEAVElementExtraInfoMsg@UIAutomationCoreProto@@PEAV012@@Z; google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::ElementExtraInfoMsg,>(google::protobuf::Arena *)
0x180067f14  mov     rsi, rax
0x180067f17  mov     [r12+10h], rax
0x180067f1c  cmp     [rbp+90h+var_110], rdi
0x180067f20  jz      short loc_180067F52
0x180067f22  mov     rax, [rsi+10h]
0x180067f26  test    rax, rax
0x180067f29  jnz     short loc_180067F46
0x180067f2b  mov     rcx, [rsi+8]
0x180067f2f  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180067f33  test    [rsi+8], r14b
0x180067f37  jnz     loc_1800684D7
0x180067f3d  call    ??$CreateMaybeMessage@VProviderEntryPointMsg@UIAutomationCoreProto@@$$V@Arena@protobuf@google@@CAPEAVProviderEntryPointMsg@UIAutomationCoreProto@@PEAV012@@Z; google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::ProviderEntryPointMsg,>(google::protobuf::Arena *)
0x180067f42  mov     [rsi+10h], rax
0x180067f46  mov     rdx, rax; struct UIAutomationCoreProto::ProviderEntryPointMsg *
0x180067f49  mov     rcx, [rbp+90h+var_110]; this
0x180067f4d  call    ?WriteToMessage@ProviderEntryPoint@@QEBAJPEAVProviderEntryPointMsg@UIAutomationCoreProto@@@Z; ProviderEntryPoint::WriteToMessage(UIAutomationCoreProto::ProviderEntryPointMsg *)
0x180067f52  mov     r8d, 10h; Size
0x180067f58  lea     rdx, GUID_NULL; Buf2
0x180067f5f  lea     rcx, [rbp+90h+Buf1]; Buf1
0x180067f63  call    memcmp_0
0x180067f68  test    eax, eax
0x180067f6a  jnz     loc_1800683A2
0x180067f70  cmp     [rbp+90h+var_C0], dil
0x180067f74  jnz     loc_180068591
0x180067f7a  mov     rcx, [rsi+30h]
0x180067f7e  test    rcx, rcx
0x180067f81  jnz     short loc_180067FA1
0x180067f83  mov     rcx, [rsi+8]
0x180067f87  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180067f8b  test    [rsi+8], r14b
0x180067f8f  jnz     loc_1800684CF
0x180067f95  call    ??$CreateMaybeMessage@VElementExtraInfoFlagsMsg@UIAutomationCoreProto@@$$V@Arena@protobuf@google@@CAPEAVElementExtraInfoFlagsMsg@UIAutomationCoreProto@@PEAV012@@Z; google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::ElementExtraInfoFlagsMsg,>(google::protobuf::Arena *)
0x180067f9a  mov     rcx, rax
0x180067f9d  mov     [rsi+30h], rax
0x180067fa1  mov     al, [rbp+90h+var_108]
0x180067fa4  and     al, r14b
0x180067fa7  mov     [rcx+10h], al
0x180067faa  mov     al, [rbp+90h+var_108]
0x180067fad  shr     al, 1
0x180067faf  and     al, r14b
0x180067fb2  mov     [rcx+11h], al
0x180067fb5  mov     al, [rbp+90h+var_108]
0x180067fb8  shr     al, 2
0x180067fbb  and     al, r14b
0x180067fbe  mov     [rcx+12h], al
0x180067fc1  mov     al, [rbp+90h+var_108]
0x180067fc4  shr     al, 3
0x180067fc7  and     al, r14b
0x180067fca  mov     [rcx+13h], al
0x180067fcd  mov     al, [rbp+90h+var_108]
0x180067fd0  shr     al, 4
0x180067fd3  and     al, r14b
0x180067fd6  mov     [rcx+14h], al
0x180067fd9  mov     al, [rbp+90h+var_108]
0x180067fdc  shr     al, 5
0x180067fdf  and     al, r14b
0x180067fe2  mov     [rcx+15h], al
0x180067fe5  cmp     [rbp+90h+var_C0], dil
0x180067fe9  jnz     loc_1800685AA
0x180067fef  mov     rcx, [rbp+90h+bstrString]; bstrString
0x180067ff3  test    rcx, rcx
0x180067ff6  jz      short loc_180068002
0x180067ff8  call    cs:__imp_SysFreeString
0x180067ffe  mov     [rbp+90h+bstrString], rdi
0x180068002  lea     rcx, [rbp+90h+var_110]
0x180068006  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006800b  lea     rdx, [rsp+190h+var_118]
0x180068010  lea     rcx, [rbp+90h+var_B0]
0x180068014  call    ?TryGetRuntimeIdCopy@ElementRefRet@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUtagSAFEARRAY@@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; ElementRefRet::TryGetRuntimeIdCopy(void)
0x180068019  nop
0x18006801a  mov     rsi, [rsp+190h+var_118]
0x18006801f  test    rsi, rsi
0x180068022  jz      loc_1800681F0
0x180068028  mov     r13, [r12+20h]
0x18006802d  test    r13, r13
0x180068030  jnz     short loc_180068053
0x180068032  mov     rcx, [r12+8]
0x180068037  and     rcx, 0FFFFFFFFFFFFFFFCh; struct google::protobuf::Arena *
0x18006803b  test    [r12+8], r14b
0x180068040  jnz     loc_1800684BF
0x180068046  call    ??$CreateMaybeMessage@VIntArrayMsg@UIAutomationCoreProto@@$$V@Arena@protobuf@google@@CAPEAVIntArrayMsg@UIAutomationCoreProto@@PEAV012@@Z; google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::IntArrayMsg,>(google::protobuf::Arena *)
0x18006804b  mov     r13, rax
0x18006804e  mov     [r12+20h], rax
0x180068053  test    rsi, rsi
0x180068056  jz      loc_1800684DF
0x18006805c  mov     rbx, rdi
0x18006805f  mov     [rsp+190h+var_150], rbx
0x180068064  mov     [rsp+190h+var_130], edi
0x180068068  mov     [rsp+190h+ppvData], rdi
0x18006806d  mov     r15d, edi
0x180068070  mov     [rsp+190h+var_138], rsi
0x180068075  mov     rcx, rsi; psa
0x180068078  call    cs:__imp_SafeArrayGetDim
0x18006807e  cmp     eax, r14d
0x180068081  jnz     loc_1800684A8
0x180068087  mov     [rsp+190h+pvt], di
0x18006808c  lea     rdx, [rsp+190h+pvt]; pvt
0x180068091  mov     rcx, [rsp+190h+var_138]; psa
0x180068096  call    cs:__imp_SafeArrayGetVartype
0x18006809c  mov     edi, eax
0x18006809e  test    eax, eax
0x1800680a0  js      loc_1800684B8
0x1800680a6  cmp     [rsp+190h+pvt], 3
0x1800680ac  jnz     loc_1800684FB
0x1800680b2  mov     dword ptr [rsp+190h+psa], 0
0x1800680ba  mov     [rsp+190h+plUbound], 0
0x1800680c2  lea     r8, [rsp+190h+psa]; plLbound
0x1800680c7  mov     edx, r14d; nDim
0x1800680ca  mov     rcx, [rsp+190h+var_138]; psa
0x1800680cf  call    cs:__imp_SafeArrayGetLBound
0x1800680d5  mov     edi, eax
0x1800680d7  test    eax, eax
0x1800680d9  js      loc_18006847C
0x1800680df  lea     r8, [rsp+190h+plUbound]; plUbound
0x1800680e4  mov     edx, r14d; nDim
0x1800680e7  mov     rcx, [rsp+190h+var_138]; psa
0x1800680ec  call    cs:__imp_SafeArrayGetUBound
0x1800680f2  mov     edi, eax
0x1800680f4  test    eax, eax
0x1800680f6  js      loc_1800684A1
0x1800680fc  mov     eax, [rsp+190h+plUbound]
0x180068100  sub     eax, dword ptr [rsp+190h+psa]
0x180068104  add     eax, r14d
0x180068107  mov     [rsp+190h+var_130], eax
0x18006810b  lea     rdx, [rsp+190h+ppvData]; ppvData
0x180068110  mov     rcx, [rsp+190h+var_138]; psa
0x180068115  call    cs:__imp_SafeArrayAccessData
0x18006811b  mov     edi, eax
0x18006811d  test    eax, eax
0x18006811f  js      loc_1800684F4
0x180068125  mov     ecx, [rsp+190h+var_130]
0x180068129  mov     eax, 4
0x18006812e  mul     rcx
0x180068131  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180068138  cmovb   rax, rcx
0x18006813c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180068143  mov     rcx, rax; unsigned __int64
0x180068146  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18006814b  mov     r9, rax
0x18006814e  test    rax, rax
0x180068151  jz      loc_1800683E2
0x180068157  xor     r8d, r8d
0x18006815a  mov     r15d, [rsp+190h+var_130]
0x18006815f  test    r15d, r15d
0x180068162  jz      short loc_18006817E
0x180068164  mov     rcx, [rsp+190h+ppvData]
0x180068169  mov     eax, [rcx+r8*4]
0x18006816d  mov     [r9+r8*4], eax
0x180068171  add     r8d, r14d
0x180068174  mov     r15d, [rsp+190h+var_130]
0x180068179  cmp     r8d, r15d
0x18006817c  jb      short loc_180068164
0x18006817e  mov     rbx, r9
0x180068181  mov     [rsp+190h+var_150], rbx
0x180068186  mov     rcx, [rsp+190h+var_138]; psa
0x18006818b  test    rcx, rcx
0x18006818e  jz      short loc_180068196
0x180068190  call    cs:__imp_SafeArrayUnaccessData
0x180068196  xor     edi, edi
0x180068198  mov     rcx, [rbp+98h]; this
0x18006819f  test    edi, edi
0x1800681a1  jns     short loc_1800681B8
0x1800681a3  mov     r9d, edi; char *
0x1800681a6  lea     r8, aOnecoreWindows_122; "onecore\\windows\\accessibletech\\uiaut"...
0x1800681ad  mov     edx, 290h; void *
0x1800681b2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800681b8  xor     edi, edi
0x1800681ba  test    r15d, r15d
0x1800681bd  jle     short loc_1800681DC
0x1800681bf  mov     ecx, [rbx+rdi*4]
0x1800681c2  mov     dword ptr [rsp+190h+psa], ecx
0x1800681c6  lea     rdx, [rsp+190h+psa]
0x1800681cb  lea     rcx, [r13+10h]
0x1800681cf  call    ?Add@?$RepeatedField@I@protobuf@google@@QEAAXAEBI@Z; google::protobuf::RepeatedField<uint>::Add(uint const &)
0x1800681d4  add     edi, r14d
0x1800681d7  cmp     edi, r15d
0x1800681da  jl      short loc_1800681BF
0x1800681dc  mov     rcx, rbx; Block
0x1800681df  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800681e4  mov     r15, [rsp+190h+var_120]
0x1800681e9  xor     edi, edi
0x1800681eb  mov     r13d, [rsp+190h+var_13C]
0x1800681f0  test    rsi, rsi
0x1800681f3  jz      short loc_1800681FE
0x1800681f5  mov     rcx, rsi; psa
0x1800681f8  call    cs:__imp_SafeArrayDestroy
0x1800681fe  mov     ebx, 2
0x180068203  cmp     [rsp+190h+var_160], dil
0x180068208  jz      short loc_180068213
  ... truncated ...
```
