# ProtobufHelper::WriteElementReturn(UIAutomationCoreProto::ElementRefRetMsg &,ElementRefRet &,IServerConnection *,bool)

- ea: `0x180068664`
- end: `0x180068daf`
- name: `?WriteElementReturn@ProtobufHelper@@SAXAEAVElementRefRetMsg@UIAutomationCoreProto@@AEAUElementRefRet@@PEAVIServerConnection@@_N@Z`
- size: `1867`
- prototype: `static void(struct UIAutomationCoreProto::ElementRefRetMsg *, struct ElementRefRet *, struct IServerConnection *, bool)`
- caller_count: `5`
- callee_count: `28`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000defc`
- `0x180057efc`
- `0x180067070`
- `0x180123e24`
- `0x1801274bc`

## callees

- `0x1800206e8`
- `0x18002f580`
- `0x180032724`
- `0x18003c820`
- `0x18004e194`
- `0x18004e318`
- `0x18004e410`
- `0x18004e5f8`
- `0x18004e668`
- `0x18004e6c8`
- `0x180068664`
- `0x180068db8`
- `0x180068f08`
- `0x1800690c4`
- `0x180181488`
- `0x180189804`
- `0x1801a9630`
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

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180068ab9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180068ab9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068b0c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068b0c`
- `OLEAUT32!__imp_SysFreeString` at `0x18006880d`
- `OLEAUT32!__imp_SysFreeString` at `0x180068a30`
- `OLEAUT32!__imp_SysFreeString` at `0x180068b26`
- `OLEAUT32!__imp_SysFreeString` at `0x18006880d`
- `OLEAUT32!__imp_SysFreeString` at `0x180068a30`
- `OLEAUT32!__imp_SysFreeString` at `0x180068b26`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800689ff`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800689ff`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180068888`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180068888`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180068900`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180068900`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800688e1`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800688e1`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180068926`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180068926`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18006899c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180068bcf`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18006899c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180068bcf`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800688a6`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800688a6`

## string_xrefs

- `0x180068bb1`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x180068c4a`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x1800689af`: `onecore\windows\accessibletech\uiautomationcore\protobufhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall ProtobufHelper::WriteElementReturn(
        struct UIAutomationCoreProto::ElementRefRetMsg *a1,
        struct ElementRefRet *a2,
        struct IServerConnection *a3,
        char a4)
{
  struct IServerConnection *v4; // r15
  char v7; // r13
  ProviderEntryPoint *v8; // rcx
  const unsigned __int16 *v9; // rcx
  UIAutomationCoreProto::ElementExtraInfoMsg *v10; // r14
  _QWORD *v11; // rcx
  struct UIAutomationCoreProto::ProviderEntryPointMsg *v12; // rax
  _QWORD *v13; // rcx
  unsigned int v14; // edx
  _BYTE *v15; // rcx
  _QWORD *v16; // rcx
  char *v17; // rdx
  SAFEARRAY *v18; // r14
  __int64 v19; // r13
  struct google::protobuf::Arena *v20; // rcx
  _DWORD *v21; // rbx
  int i; // r15d
  HRESULT Vartype; // eax
  int v24; // edi
  unsigned __int64 v25; // rax
  _DWORD *v26; // r9
  __int64 v27; // r8
  __int64 j; // rdi
  char v29; // bl
  ProviderEntryPoint *v30; // rcx
  const unsigned __int16 *v31; // rcx
  ProviderEntryPoint *v32; // rdi
  unsigned int v33; // edx
  UIAutomationCoreProto::UiaPropertyConditionMsg *v34; // rdi
  struct UIAutomationCoreProto::GuidMsg *v35; // rax
  const unsigned __int16 *v36; // rbx
  struct UIAutomationCoreProto::WstringMsg *v37; // rax
  __int64 v38; // rdx
  ProviderEntryPoint *v39; // rcx
  const unsigned __int16 *v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // r9
  struct UIAutomationCoreProto::CrossMachinePlaceHolderMsg *v43; // rax
  int v44; // [rsp+20h] [rbp-99h]
  VARTYPE pvt; // [rsp+24h] [rbp-95h] BYREF
  LONG plLbound; // [rsp+28h] [rbp-91h] BYREF
  LONG plUbound; // [rsp+30h] [rbp-89h] BYREF
  int v48; // [rsp+34h] [rbp-85h]
  SAFEARRAY *v49; // [rsp+38h] [rbp-81h]
  unsigned int v50; // [rsp+40h] [rbp-79h]
  void *ppvData; // [rsp+48h] [rbp-71h] BYREF
  _QWORD v52[2]; // [rsp+50h] [rbp-69h] BYREF
  struct IServerConnection *v53; // [rsp+60h] [rbp-59h]
  SAFEARRAY *psa; // [rsp+68h] [rbp-51h] BYREF
  ProviderEntryPoint *v55; // [rsp+70h] [rbp-49h] BYREF
  char v56; // [rsp+78h] [rbp-41h]
  GUID Buf1; // [rsp+7Ch] [rbp-3Dh] BYREF
  BSTR bstrString; // [rsp+90h] [rbp-29h] BYREF
  _BYTE v59[40]; // [rsp+98h] [rbp-21h] BYREF
  char v60; // [rsp+C0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  LOBYTE(v44) = a4;
  v4 = a3;
  v53 = a3;
  v7 = 0;
  v48 = 0;
  *((_DWORD *)a1 + 10) = *(_DWORD *)a2;
  if ( *(_DWORD *)a2 )
  {
    v8 = (ProviderEntryPoint *)*((_QWORD *)a2 + 1);
    v55 = v8;
    if ( v8 )
      (*(void (__fastcall **)(ProviderEntryPoint *))(*(_QWORD *)v8 + 8LL))(v8);
    v56 = *((_BYTE *)a2 + 16);
    Buf1 = *(GUID *)((char *)a2 + 20);
    bstrString = 0;
    v60 = 0;
    if ( *((_BYTE *)a2 + 88) )
      std::_Optional_construct_base<CrossMachinePlaceholderInfo>::_Construct<CrossMachinePlaceholderInfo const &>(
        v59,
        (char *)a2 + 48);
    v9 = (const unsigned __int16 *)*((_QWORD *)a2 + 5);
    if ( v9 && (int)HrSysAllocString(v9, &bstrString) < 0 )
      Buf1 = GUID_NULL;
    v10 = (UIAutomationCoreProto::ElementExtraInfoMsg *)*((_QWORD *)a1 + 2);
    if ( !v10 )
    {
      v11 = (_QWORD *)(*((_QWORD *)a1 + 1) & 0xFFFFFFFFFFFFFFFCuLL);
      if ( (*((_BYTE *)a1 + 8) & 1) != 0 )
        v11 = (_QWORD *)*v11;
      v10 = (UIAutomationCoreProto::ElementExtraInfoMsg *)google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::ElementExtraInfoMsg,>(v11);
      *((_QWORD *)a1 + 2) = v10;
    }
    if ( v55 )
    {
      v12 = (struct UIAutomationCoreProto::ProviderEntryPointMsg *)*((_QWORD *)v10 + 2);
      if ( !v12 )
      {
        v13 = (_QWORD *)(*((_QWORD *)v10 + 1) & 0xFFFFFFFFFFFFFFFCuLL);
        if ( (*((_BYTE *)v10 + 8) & 1) != 0 )
          v13 = (_QWORD *)*v13;
        v12 = (struct UIAutomationCoreProto::ProviderEntryPointMsg *)google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::ProviderEntryPointMsg,>(v13);
        *((_QWORD *)v10 + 2) = v12;
      }
      ProviderEntryPoint::WriteToMessage(v55, v12);
    }
    if ( memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
    {
      v34 = UIAutomationCoreProto::ElementExtraInfoMsg::_internal_mutable_component_site(v10);
      v35 = UIAutomationCoreProto::UiaPropertyConditionMsg::_internal_mutable_property_id(v34);
      ProtobufHelper::WriteGuid(v35, &Buf1);
      v36 = bstrString;
      v37 = UIAutomationCoreProto::StructuredMarkupRangeGetMarkupWithMarkedRangeRequestMsg::_internal_mutable_language(v34);
      ProtobufHelper::WriteString(v37, v36, 1);
    }
    if ( v60 )
    {
      v43 = UIAutomationCoreProto::ElementExtraInfoMsg::_internal_mutable_cross_machine_placeholder(v10);
      CrossMachinePlaceholderInfo::WriteToMessage((CrossMachinePlaceholderInfo *)v59, v43);
    }
    v15 = (_BYTE *)*((_QWORD *)v10 + 6);
    if ( !v15 )
    {
      v16 = (_QWORD *)(*((_QWORD *)v10 + 1) & 0xFFFFFFFFFFFFFFFCuLL);
      if ( (*((_BYTE *)v10 + 8) & 1) != 0 )
        v16 = (_QWORD *)*v16;
      v15 = (_BYTE *)google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::ElementExtraInfoFlagsMsg,>(v16);
      *((_QWORD *)v10 + 6) = v15;
    }
    v15[16] = v56 & 1;
    v15[17] = (v56 & 2) != 0;
    v15[18] = (v56 & 4) != 0;
    v15[19] = (v56 & 8) != 0;
    v15[20] = (v56 & 0x10) != 0;
    v15[21] = (v56 & 0x20) != 0;
    if ( v60 )
      CrossMachinePlaceholderInfo::`scalar deleting destructor'((CrossMachinePlaceholderInfo *)v59, v14);
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v55);
  }
  ElementRefRet::TryGetRuntimeIdCopy(a2, &psa);
  v18 = psa;
  if ( psa )
  {
    v19 = *((_QWORD *)a1 + 4);
    if ( !v19 )
    {
      v20 = (struct google::protobuf::Arena *)(*((_QWORD *)a1 + 1) & 0xFFFFFFFFFFFFFFFCuLL);
      if ( (*((_BYTE *)a1 + 8) & 1) != 0 )
        v20 = *(struct google::protobuf::Arena **)v20;
      v19 = google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::IntArrayMsg,>(v20);
      *((_QWORD *)a1 + 4) = v19;
    }
    if ( !v18 )
    {
      google::protobuf::RepeatedField<bool>::Clear(v19 + 16);
LABEL_55:
      v7 = v48;
      goto LABEL_56;
    }
    v21 = 0;
    v52[0] = 0;
    v50 = 0;
    ppvData = 0;
    i = 0;
    v49 = v18;
    if ( SafeArrayGetDim(v18) == 1 )
    {
      pvt = 0;
      Vartype = SafeArrayGetVartype(v49, &pvt);
      v24 = Vartype;
      if ( Vartype < 0 )
      {
        v41 = 95;
      }
      else
      {
        if ( pvt != 3 && pvt != 22 )
        {
          v42 = 2147942487LL;
          v24 = -2147024809;
          v41 = 106;
          goto LABEL_98;
        }
        plLbound = 0;
        plUbound = 0;
        Vartype = SafeArrayGetLBound(v49, 1u, &plLbound);
        v24 = Vartype;
        if ( Vartype < 0 )
        {
          v41 = 111;
        }
        else
        {
          Vartype = SafeArrayGetUBound(v49, 1u, &plUbound);
          v24 = Vartype;
          if ( Vartype < 0 )
          {
            v41 = 112;
          }
          else
          {
            v50 = plUbound - plLbound + 1;
            Vartype = SafeArrayAccessData(v49, &ppvData);
            v24 = Vartype;
            if ( Vartype >= 0 )
            {
              v25 = 4LL * v50;
              if ( !is_mul_ok(v50, 4u) )
                v25 = -1;
              v26 = operator new[](v25, (const struct std::nothrow_t *)std::nothrow);
              if ( v26 )
              {
                v27 = 0;
                for ( i = v50; (unsigned int)v27 < v50; i = v50 )
                {
                  v26[v27] = *((_DWORD *)ppvData + v27);
                  v27 = (unsigned int)(v27 + 1);
                }
                v21 = v26;
                v52[0] = v26;
                if ( v49 )
                  SafeArrayUnaccessData(v49);
                v24 = 0;
                goto LABEL_50;
              }
              v24 = -2147024882;
              v38 = 162;
LABEL_87:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v38,
                (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
                (const char *)(unsigned int)v24,
                v44);
              if ( v49 )
                SafeArrayUnaccessData(v49);
LABEL_50:
              if ( v24 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x290,
                  (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\protobufhelper.cpp",
                  (const char *)(unsigned int)v24,
                  v44);
              for ( j = 0; (int)j < i; j = (unsigned int)(j + 1) )
              {
                plLbound = v21[j];
                google::protobuf::RepeatedField<unsigned int>::Add(v19 + 16, &plLbound, v27);
              }
              operator delete(v21);
              v4 = v53;
              goto LABEL_55;
            }
            v41 = 115;
          }
        }
      }
      v42 = (unsigned int)Vartype;
    }
    else
    {
      v42 = 2147942487LL;
      v24 = -2147024809;
      v41 = 92;
    }
LABEL_98:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v41,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      (const char *)v42,
      v44);
    v38 = 159;
    goto LABEL_87;
  }
LABEL_56:
  if ( v18 )
    SafeArrayDestroy(v18);
  if ( !(_BYTE)v44 || !*(_DWORD *)a2 )
    goto LABEL_60;
  v39 = (ProviderEntryPoint *)*((_QWORD *)a2 + 1);
  v55 = v39;
  if ( v39 )
    (*(void (__fastcall **)(ProviderEntryPoint *))(*(_QWORD *)v39 + 8LL))(v39);
  v56 = *((_BYTE *)a2 + 16);
  Buf1 = *(GUID *)((char *)a2 + 20);
  bstrString = 0;
  v17 = (char *)a2 + 48;
  v60 = 0;
  if ( *((_BYTE *)a2 + 88) )
    std::_Optional_construct_base<CrossMachinePlaceholderInfo>::_Construct<CrossMachinePlaceholderInfo const &>(
      v59,
      v17);
  v40 = (const unsigned __int16 *)*((_QWORD *)a2 + 5);
  if ( v40 && (int)HrSysAllocString(v40, &bstrString) < 0 )
    Buf1 = GUID_NULL;
  v7 = 1;
  v29 = 1;
  if ( !v55 )
LABEL_60:
    v29 = 0;
  if ( (v7 & 1) != 0 )
  {
    if ( v60 )
      CrossMachinePlaceholderInfo::`scalar deleting destructor'((CrossMachinePlaceholderInfo *)v59, (unsigned int)v17);
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v55);
  }
  if ( v29 )
  {
    v30 = (ProviderEntryPoint *)*((_QWORD *)a2 + 1);
    v55 = v30;
    if ( v30 )
      (*(void (__fastcall **)(ProviderEntryPoint *))(*(_QWORD *)v30 + 8LL))(v30);
    v56 = *((_BYTE *)a2 + 16);
    Buf1 = *(GUID *)((char *)a2 + 20);
    bstrString = 0;
    v60 = 0;
    if ( *((_BYTE *)a2 + 88) )
      std::_Optional_construct_base<CrossMachinePlaceholderInfo>::_Construct<CrossMachinePlaceholderInfo const &>(
        v59,
        (char *)a2 + 48);
    v31 = (const unsigned __int16 *)*((_QWORD *)a2 + 5);
    if ( v31 && (int)HrSysAllocString(v31, &bstrString) < 0 )
      Buf1 = GUID_NULL;
    v32 = v55;
    if ( (**(unsigned __int8 (__fastcall ***)(struct IServerConnection *, __int64))v4)(v4, 2) )
    {
      AcquireSRWLockExclusive((PSRWLOCK)v4 + 12);
      v53 = (struct IServerConnection *)((char *)v4 + 96);
      v52[0] = v32;
      if ( v32 )
        (*(void (__fastcall **)(ProviderEntryPoint *))(*(_QWORD *)v32 + 8LL))(v32);
      v52[1] = a1;
      std::vector<IServerConnection::WriteCompletionInfoQueueItem>::_Emplace_one_at_back<IServerConnection::WriteCompletionInfoQueueItem>(
        (char *)v4 + 72,
        v52);
      if ( v52[0] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v52[0] + 16LL))(v52[0]);
      if ( v4 != (struct IServerConnection *)-96LL )
        ReleaseSRWLockExclusive((PSRWLOCK)v4 + 12);
    }
    if ( v60 )
      CrossMachinePlaceholderInfo::`scalar deleting destructor'((CrossMachinePlaceholderInfo *)v59, v33);
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v55);
  }
}

```

## disassembly

```asm
0x180068664  mov     [rsp-8+arg_18], rbx
0x180068669  push    rbp
0x18006866a  push    rsi
0x18006866b  push    rdi
0x18006866c  push    r12
0x18006866e  push    r13
0x180068670  push    r14
0x180068672  push    r15
0x180068674  lea     rbp, [rsp-27h]
0x180068679  sub     rsp, 0E0h
0x180068680  mov     rax, cs:__security_cookie
0x180068687  xor     rax, rsp
0x18006868a  mov     [rbp+57h+var_40], rax
0x18006868e  mov     byte ptr [rsp+110h+var_F0], r9b; int
0x180068693  mov     r15, r8
0x180068696  mov     [rbp+57h+var_B0], r8
0x18006869a  mov     rsi, rdx
0x18006869d  mov     r12, rcx
0x1800686a0  xor     edi, edi
0x1800686a2  mov     r13d, edi
0x1800686a5  mov     [rsp+110h+var_DC], edi
0x1800686a9  mov     eax, [rdx]
0x1800686ab  mov     [rcx+28h], eax
0x1800686ae  cmp     [rdx], edi
0x1800686b0  jz      loc_180068820
0x1800686b6  mov     rcx, [rdx+8]
0x1800686ba  mov     [rbp+57h+var_A0], rcx
0x1800686be  test    rcx, rcx
0x1800686c1  jz      short loc_1800686D0
0x1800686c3  mov     rax, [rcx]
0x1800686c6  mov     rax, [rax+8]
0x1800686ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800686cf  nop
0x1800686d0  mov     al, [rsi+10h]
0x1800686d3  mov     [rbp+57h+var_98], al
0x1800686d6  mov     rax, [rsi+14h]
0x1800686da  mov     qword ptr [rbp+57h+Buf1.Data1], rax
0x1800686de  mov     rax, [rsi+1Ch]
0x1800686e2  mov     qword ptr [rbp+57h+Buf1.Data4], rax
0x1800686e6  mov     [rbp+57h+bstrString], rdi
0x1800686ea  lea     rdx, [rsi+30h]
0x1800686ee  mov     [rbp+57h+var_50], dil
0x1800686f2  cmp     [rdx+28h], dil
0x1800686f6  jnz     loc_180068CD2
0x1800686fc  mov     rcx, [rsi+28h]; unsigned __int16 *
0x180068700  test    rcx, rcx
0x180068703  jnz     loc_180068CE0
0x180068709  mov     r14, [r12+10h]
0x18006870e  test    r14, r14
0x180068711  jnz     short loc_180068735
0x180068713  mov     rcx, [r12+8]
0x180068718  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18006871c  test    byte ptr [r12+8], 1
0x180068722  jnz     loc_180068C86
0x180068728  call    ??$CreateMaybeMessage@VElementExtraInfoMsg@UIAutomationCoreProto@@$$V@Arena@protobuf@google@@CAPEAVElementExtraInfoMsg@UIAutomationCoreProto@@PEAV012@@Z; google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::ElementExtraInfoMsg,>(google::protobuf::Arena *)
0x18006872d  mov     r14, rax
0x180068730  mov     [r12+10h], rax
0x180068735  cmp     [rbp+57h+var_A0], rdi
0x180068739  jz      short loc_18006876C
0x18006873b  mov     rax, [r14+10h]
0x18006873f  test    rax, rax
0x180068742  jnz     short loc_180068760
0x180068744  mov     rcx, [r14+8]
0x180068748  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18006874c  test    byte ptr [r14+8], 1
0x180068751  jnz     loc_180068C96
0x180068757  call    ??$CreateMaybeMessage@VProviderEntryPointMsg@UIAutomationCoreProto@@$$V@Arena@protobuf@google@@CAPEAVProviderEntryPointMsg@UIAutomationCoreProto@@PEAV012@@Z; google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::ProviderEntryPointMsg,>(google::protobuf::Arena *)
0x18006875c  mov     [r14+10h], rax
0x180068760  mov     rdx, rax; struct UIAutomationCoreProto::ProviderEntryPointMsg *
0x180068763  mov     rcx, [rbp+57h+var_A0]; this
0x180068767  call    ?WriteToMessage@ProviderEntryPoint@@QEBAJPEAVProviderEntryPointMsg@UIAutomationCoreProto@@@Z; ProviderEntryPoint::WriteToMessage(UIAutomationCoreProto::ProviderEntryPointMsg *)
0x18006876c  mov     r8d, 10h; Size
0x180068772  lea     rdx, GUID_NULL; Buf2
0x180068779  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18006877d  call    memcmp_0
0x180068782  test    eax, eax
0x180068784  jnz     loc_180068B64
0x18006878a  cmp     [rbp+57h+var_50], dil
0x18006878e  jnz     loc_180068D0C
0x180068794  mov     rcx, [r14+30h]
0x180068798  test    rcx, rcx
0x18006879b  jnz     short loc_1800687BC
0x18006879d  mov     rcx, [r14+8]
0x1800687a1  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1800687a5  test    byte ptr [r14+8], 1
0x1800687aa  jnz     loc_180068C8E
0x1800687b0  call    ??$CreateMaybeMessage@VElementExtraInfoFlagsMsg@UIAutomationCoreProto@@$$V@Arena@protobuf@google@@CAPEAVElementExtraInfoFlagsMsg@UIAutomationCoreProto@@PEAV012@@Z; google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::ElementExtraInfoFlagsMsg,>(google::protobuf::Arena *)
0x1800687b5  mov     rcx, rax
0x1800687b8  mov     [r14+30h], rax
0x1800687bc  mov     al, [rbp+57h+var_98]
0x1800687bf  and     al, 1
0x1800687c1  mov     [rcx+10h], al
0x1800687c4  mov     al, [rbp+57h+var_98]
0x1800687c7  shr     al, 1
0x1800687c9  and     al, 1
0x1800687cb  mov     [rcx+11h], al
0x1800687ce  mov     al, [rbp+57h+var_98]
0x1800687d1  shr     al, 2
0x1800687d4  and     al, 1
0x1800687d6  mov     [rcx+12h], al
0x1800687d9  mov     al, [rbp+57h+var_98]
0x1800687dc  shr     al, 3
0x1800687df  and     al, 1
0x1800687e1  mov     [rcx+13h], al
0x1800687e4  mov     al, [rbp+57h+var_98]
0x1800687e7  shr     al, 4
0x1800687ea  and     al, 1
0x1800687ec  mov     [rcx+14h], al
0x1800687ef  mov     al, [rbp+57h+var_98]
0x1800687f2  shr     al, 5
0x1800687f5  and     al, 1
0x1800687f7  mov     [rcx+15h], al
0x1800687fa  cmp     [rbp+57h+var_50], dil
0x1800687fe  jnz     loc_180068D25
0x180068804  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180068808  test    rcx, rcx
0x18006880b  jz      short loc_180068817
0x18006880d  call    cs:__imp_SysFreeString
0x180068813  mov     [rbp+57h+bstrString], rdi
0x180068817  lea     rcx, [rbp+57h+var_A0]
0x18006881b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180068820  lea     rdx, [rbp+57h+psa]
0x180068824  mov     rcx, rsi
0x180068827  call    ?TryGetRuntimeIdCopy@ElementRefRet@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUtagSAFEARRAY@@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; ElementRefRet::TryGetRuntimeIdCopy(void)
0x18006882c  nop
0x18006882d  mov     r14, [rbp+57h+psa]
0x180068831  test    r14, r14
0x180068834  jz      loc_1800689F7
0x18006883a  mov     r13, [r12+20h]
0x18006883f  test    r13, r13
0x180068842  jnz     short loc_180068866
0x180068844  mov     rcx, [r12+8]
0x180068849  and     rcx, 0FFFFFFFFFFFFFFFCh; struct google::protobuf::Arena *
0x18006884d  test    byte ptr [r12+8], 1
0x180068853  jnz     loc_180068C7E
0x180068859  call    ??$CreateMaybeMessage@VIntArrayMsg@UIAutomationCoreProto@@$$V@Arena@protobuf@google@@CAPEAVIntArrayMsg@UIAutomationCoreProto@@PEAV012@@Z; google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::IntArrayMsg,>(google::protobuf::Arena *)
0x18006885e  mov     r13, rax
0x180068861  mov     [r12+20h], rax
0x180068866  test    r14, r14
0x180068869  jz      loc_180068C9E
0x18006886f  mov     rbx, rdi
0x180068872  mov     [rbp+57h+var_C0], rbx
0x180068876  mov     [rbp+57h+var_D0], edi
0x180068879  mov     [rbp+57h+ppvData], rdi
0x18006887d  mov     r15d, edi
0x180068880  mov     [rsp+110h+var_D8], r14
0x180068885  mov     rcx, r14; psa
0x180068888  call    cs:__imp_SafeArrayGetDim
0x18006888e  cmp     eax, 1
0x180068891  jnz     loc_180068C67
0x180068897  mov     [rsp+110h+pvt], di
0x18006889c  lea     rdx, [rsp+110h+pvt]; pvt
0x1800688a1  mov     rcx, [rsp+110h+var_D8]; psa
0x1800688a6  call    cs:__imp_SafeArrayGetVartype
0x1800688ac  mov     edi, eax
0x1800688ae  test    eax, eax
0x1800688b0  js      loc_180068C77
0x1800688b6  cmp     [rsp+110h+pvt], 3
0x1800688bc  jnz     loc_180068CB3
0x1800688c2  mov     [rsp+110h+plLbound], 0
0x1800688ca  mov     [rsp+110h+plUbound], 0
0x1800688d2  lea     r8, [rsp+110h+plLbound]; plLbound
0x1800688d7  mov     edx, 1; nDim
0x1800688dc  mov     rcx, [rsp+110h+var_D8]; psa
0x1800688e1  call    cs:__imp_SafeArrayGetLBound
0x1800688e7  mov     edi, eax
0x1800688e9  test    eax, eax
0x1800688eb  js      loc_180068C3E
0x1800688f1  lea     r8, [rsp+110h+plUbound]; plUbound
0x1800688f6  mov     edx, 1; nDim
0x1800688fb  mov     rcx, [rsp+110h+var_D8]; psa
0x180068900  call    cs:__imp_SafeArrayGetUBound
0x180068906  mov     edi, eax
0x180068908  test    eax, eax
0x18006890a  js      loc_180068C60
0x180068910  mov     eax, [rsp+110h+plUbound]
0x180068914  sub     eax, [rsp+110h+plLbound]
0x180068918  inc     eax
0x18006891a  mov     [rbp+57h+var_D0], eax
0x18006891d  lea     rdx, [rbp+57h+ppvData]; ppvData
0x180068921  mov     rcx, [rsp+110h+var_D8]; psa
0x180068926  call    cs:__imp_SafeArrayAccessData
0x18006892c  mov     edi, eax
0x18006892e  test    eax, eax
0x180068930  js      loc_180068CAC
0x180068936  mov     ecx, [rbp+57h+var_D0]
0x180068939  mov     eax, 4
0x18006893e  mul     rcx
0x180068941  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180068948  cmovb   rax, rcx
0x18006894c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180068953  mov     rcx, rax; unsigned __int64
0x180068956  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18006895b  mov     r9, rax
0x18006895e  test    rax, rax
0x180068961  jz      loc_180068BA4
0x180068967  xor     r8d, r8d
0x18006896a  mov     r15d, [rbp+57h+var_D0]
0x18006896e  test    r15d, r15d
0x180068971  jz      short loc_18006898B
0x180068973  mov     rcx, [rbp+57h+ppvData]
0x180068977  mov     eax, [rcx+r8*4]
0x18006897b  mov     [r9+r8*4], eax
0x18006897f  inc     r8d
0x180068982  mov     r15d, [rbp+57h+var_D0]
0x180068986  cmp     r8d, r15d
0x180068989  jb      short loc_180068973
0x18006898b  mov     rbx, r9
0x18006898e  mov     [rbp+57h+var_C0], rbx
0x180068992  mov     rcx, [rsp+110h+var_D8]; psa
0x180068997  test    rcx, rcx
0x18006899a  jz      short loc_1800689A2
0x18006899c  call    cs:__imp_SafeArrayUnaccessData
0x1800689a2  xor     edi, edi
0x1800689a4  mov     rcx, [rbp+5Fh]; this
0x1800689a8  test    edi, edi
0x1800689aa  jns     short loc_1800689C1
0x1800689ac  mov     r9d, edi; char *
0x1800689af  lea     r8, aOnecoreWindows_122; "onecore\\windows\\accessibletech\\uiaut"...
0x1800689b6  mov     edx, 290h; void *
0x1800689bb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800689c1  xor     edi, edi
0x1800689c3  test    r15d, r15d
0x1800689c6  jle     short loc_1800689E4
0x1800689c8  mov     ecx, [rbx+rdi*4]
0x1800689cb  mov     [rsp+110h+plLbound], ecx
0x1800689cf  lea     rdx, [rsp+110h+plLbound]
0x1800689d4  lea     rcx, [r13+10h]
0x1800689d8  call    ?Add@?$RepeatedField@I@protobuf@google@@QEAAXAEBI@Z; google::protobuf::RepeatedField<uint>::Add(uint const &)
0x1800689dd  inc     edi
0x1800689df  cmp     edi, r15d
0x1800689e2  jl      short loc_1800689C8
0x1800689e4  mov     rcx, rbx; Block
0x1800689e7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800689ec  mov     r15, [rbp+57h+var_B0]
0x1800689f0  xor     edi, edi
0x1800689f2  mov     r13d, [rsp+110h+var_DC]
0x1800689f7  test    r14, r14
0x1800689fa  jz      short loc_180068A05
0x1800689fc  mov     rcx, r14; psa
0x1800689ff  call    cs:__imp_SafeArrayDestroy
0x180068a05  cmp     byte ptr [rsp+110h+var_F0], dil
0x180068a0a  jz      short loc_180068A14
0x180068a0c  cmp     [rsi], edi
0x180068a0e  jnz     loc_180068BDA
0x180068a14  mov     bl, dil
0x180068a17  test    r13b, 1
0x180068a1b  jz      short loc_180068A43
0x180068a1d  cmp     [rbp+57h+var_50], dil
0x180068a21  jnz     loc_180068D63
0x180068a27  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180068a2b  test    rcx, rcx
0x180068a2e  jz      short loc_180068A3A
0x180068a30  call    cs:__imp_SysFreeString
0x180068a36  mov     [rbp+57h+bstrString], rdi
0x180068a3a  lea     rcx, [rbp+57h+var_A0]
0x180068a3e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180068a43  test    bl, bl
0x180068a45  jz      loc_180068B3D
0x180068a4b  mov     rcx, [rsi+8]
0x180068a4f  mov     [rbp+57h+var_A0], rcx
0x180068a53  test    rcx, rcx
0x180068a56  jz      short loc_180068A65
0x180068a58  mov     rax, [rcx]
0x180068a5b  mov     rax, [rax+8]
0x180068a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068a64  nop
0x180068a65  mov     al, [rsi+10h]
0x180068a68  mov     [rbp+57h+var_98], al
0x180068a6b  movups  xmm0, xmmword ptr [rsi+14h]
0x180068a6f  movdqu  xmmword ptr [rbp+57h+Buf1.Data1], xmm0
0x180068a74  mov     [rbp+57h+bstrString], rdi
0x180068a78  lea     rdx, [rsi+30h]
0x180068a7c  mov     [rbp+57h+var_50], dil
0x180068a80  cmp     [rdx+28h], dil
0x180068a84  jnz     loc_180068D71
0x180068a8a  mov     rcx, [rsi+28h]; unsigned __int16 *
0x180068a8e  test    rcx, rcx
0x180068a91  jnz     loc_180068D7F
0x180068a97  mov     rdi, [rbp+57h+var_A0]
0x180068a9b  mov     rax, [r15]
0x180068a9e  mov     edx, 2
0x180068aa3  mov     rcx, r15
0x180068aa6  mov     rax, [rax]
0x180068aa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068aae  test    al, al
0x180068ab0  jz      short loc_180068B13
0x180068ab2  lea     rbx, [r15+60h]
0x180068ab6  mov     rcx, rbx; SRWLock
0x180068ab9  call    cs:__imp_AcquireSRWLockExclusive
0x180068abf  mov     [rbp+57h+var_B0], rbx
0x180068ac3  mov     [rbp+57h+var_C0], rdi
0x180068ac7  test    rdi, rdi
0x180068aca  jz      short loc_180068ADC
0x180068acc  mov     rax, [rdi]
0x180068acf  mov     rcx, rdi
0x180068ad2  mov     rax, [rax+8]
0x180068ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068adb  nop
0x180068adc  mov     [rbp+57h+var_B8], r12
  ... truncated ...
```
