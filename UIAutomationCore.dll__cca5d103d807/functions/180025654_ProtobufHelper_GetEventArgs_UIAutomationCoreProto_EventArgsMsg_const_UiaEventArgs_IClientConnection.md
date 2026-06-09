# ProtobufHelper::GetEventArgs(UIAutomationCoreProto::EventArgsMsg const &,UiaEventArgs * *,IClientConnection *)

- ea: `0x180025654`
- end: `0x180026053`
- name: `?GetEventArgs@ProtobufHelper@@SAXAEBVEventArgsMsg@UIAutomationCoreProto@@PEAPEAUUiaEventArgs@@PEAVIClientConnection@@@Z`
- size: `2559`
- prototype: `void __fastcall(const struct UIAutomationCoreProto::EventArgsMsg *, struct UiaEventArgs **, struct IClientConnection *)`
- caller_count: `3`
- callee_count: `36`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180134c70`
- `0x18014d404`
- `0x180154e34`

## callees

- `0x18000f680`
- `0x18000fc68`
- `0x180025654`
- `0x18002605c`
- `0x1800264f8`
- `0x180026970`
- `0x180026efc`
- `0x180032724`
- `0x18008a7e4`
- `0x18008ae94`
- `0x1800d4930`
- `0x1800e081c`
- `0x1800f0558`
- `0x18011edf8`
- `0x18014fca8`
- `0x180160094`
- `0x180170260`
- `0x180197840`
- `0x1801a4e68`
- `0x1801a8bd4`
- `0x1801b4d54`
- `0x1801b78fc`
- `0x1801e2dd8`
- `0x1801e8320`
- `0x1801e8344`
- `0x1801e887c`
- `0x1801eb460`
- `0x180249b4c`
- `0x18024a868`
- `0x18024abd0`
- `0x18024acc0`
- `0x18024ae74`
- `0x18024aec0`
- `0x18024af24`
- `0x1802a4f70`
- `0x1802dd010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800257ff`
- `OLEAUT32!__imp_VariantInit` at `0x18002580f`
- `OLEAUT32!__imp_VariantInit` at `0x1800258b5`
- `OLEAUT32!__imp_VariantInit` at `0x1800258d9`
- `OLEAUT32!__imp_VariantInit` at `0x1800257ff`
- `OLEAUT32!__imp_VariantInit` at `0x18002580f`
- `OLEAUT32!__imp_VariantInit` at `0x1800258b5`
- `OLEAUT32!__imp_VariantInit` at `0x1800258d9`
- `OLEAUT32!__imp_VariantClear` at `0x1800258ee`
- `OLEAUT32!__imp_VariantClear` at `0x1800258f9`
- `OLEAUT32!__imp_VariantClear` at `0x1800258ee`
- `OLEAUT32!__imp_VariantClear` at `0x1800258f9`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800256fb`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800256fb`

## string_xrefs

- `0x18002570c`: `onecore\windows\accessibletech\uiautomationcore\protobufhelper.cpp`
- `0x180025889`: `onecore\windows\accessibletech\uiautomationcore\protobufhelper.cpp`
- `0x18002599f`: `onecore\windows\accessibletech\uiautomationcore\protobufhelper.cpp`
- `0x180025a88`: `onecore\windows\accessibletech\uiautomationcore\protobufhelper.cpp`
- `0x180025b03`: `onecore\windows\accessibletech\uiautomationcore\protobufhelper.cpp`
- `0x180025c06`: `onecore\windows\accessibletech\uiautomationcore\protobufhelper.cpp`
- `0x180025caa`: `onecore\windows\accessibletech\uiautomationcore\protobufhelper.cpp`
- `0x180025d05`: `onecore\windows\accessibletech\uiautomationcore\protobufhelper.cpp`
- `0x180025d48`: `onecore\windows\accessibletech\uiautomationcore\protobufhelper.cpp`
- `0x180025da9`: `onecore\windows\accessibletech\uiautomationcore\protobufhelper.cpp`
- `0x180025e15`: `onecore\windows\accessibletech\uiautomationcore\protobufhelper.cpp`
- `0x180025e65`: `onecore\windows\accessibletech\uiautomationcore\protobufhelper.cpp`
- `0x180025ed9`: `onecore\windows\accessibletech\uiautomationcore\protobufhelper.cpp`
- `0x180025f41`: `onecore\windows\accessibletech\uiautomationcore\protobufhelper.cpp`
- `0x18002601e`: `onecore\windows\accessibletech\uiautomationcore\protobufhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
void __fastcall ProtobufHelper::GetEventArgs(
        const struct UIAutomationCoreProto::EventArgsMsg *a1,
        struct UiaEventArgs **a2,
        struct IClientConnection *a3)
{
  int v6; // r13d
  int v7; // r8d
  EventArgsType v8; // edi
  const struct UIAutomationCoreProto::GuidMsg *v9; // r12
  _QWORD *v10; // rax
  void *v11; // r14
  void *v12; // rdx
  VARIANTARG *p_lpsz; // rcx
  HRESULT v14; // eax
  wil::details::in1diag3 *v15; // rcx
  GUID v16; // xmm6
  unsigned __int64 v17; // rdx
  void *v18; // rcx
  __int64 v19; // rax
  struct UiaEventArgs *v20; // rax
  const char *v21; // r9
  int v22; // r8d
  _QWORD *v23; // r14
  int AutomationId; // r12d
  const struct UIAutomationCoreProto::VariantObjectMsg *v25; // rbx
  const struct UIAutomationCoreProto::VariantObjectMsg *v26; // rcx
  char *v27; // rax
  const char *v28; // r9
  char *v29; // rbx
  unsigned int *v30; // r14
  int v31; // r15d
  const struct UIAutomationCoreProto::IntArrayMsg *v32; // rbx
  char *v33; // rcx
  unsigned int v34; // eax
  _DWORD *v35; // rax
  const char *v36; // r9
  const struct UIAutomationCoreProto::StructuredMarkupRangeMsg *v37; // rcx
  struct IUnknown *v38; // r15
  void *v39; // r14
  const struct UIAutomationCoreProto::IntArrayMsg *v40; // rbx
  char *v41; // rcx
  unsigned int v42; // eax
  int v43; // eax
  _QWORD *v44; // r14
  unsigned int *v45; // rbx
  void *v46; // r14
  int v47; // eax
  void *v48; // r14
  const struct UIAutomationCoreProto::TextRangeMsg *v49; // rcx
  const struct UIAutomationCoreProto::NotificationPayloadMsg *v50; // rdx
  const struct UIAutomationCoreProto::ChangesEventPayloadMsg *v51; // rcx
  int v52; // r8d
  int v53; // r8d
  int v54; // r8d
  int v55; // r8d
  int v56; // r8d
  _QWORD *v57; // rax
  const char *v58; // r9
  _DWORD *v59; // rbx
  const char *v60; // r9
  int v61; // r14d
  const struct UIAutomationCoreProto::WstringArrayMsg *v62; // rcx
  struct IUnknown *v63; // rax
  const char *v64; // r9
  struct UiaEventArgs *v65; // rax
  const char *v66; // r9
  struct UiaEventArgs *v67; // rbx
  struct UiaEventArgs v68; // rcx
  struct UiaEventArgs *v69; // rax
  const char *v70; // r9
  struct UiaEventArgs *v71; // rbx
  _DWORD *v72; // rbx
  const char *v73; // r9
  __int64 v74; // r8
  IRecordInfo *pRecInfo; // rdx
  __int64 *Bstr; // rax
  __int64 v77; // rcx
  __int64 *v78; // rax
  __int64 v79; // rcx
  _DWORD *v80; // rax
  const char *v81; // r9
  struct IUnknown *v82; // [rsp+28h] [rbp-59h] BYREF
  VARIANTARG pvarg; // [rsp+30h] [rbp-51h] BYREF
  GUID iid; // [rsp+48h] [rbp-39h] BYREF
  VARIANTARG lpsz; // [rsp+58h] [rbp-29h] BYREF
  unsigned __int64 v86; // [rsp+70h] [rbp-11h]
  unsigned int v87; // [rsp+78h] [rbp-9h]
  unsigned int v88; // [rsp+7Ch] [rbp-5h]
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+5Fh]

  v6 = 0;
  *a2 = 0;
  v7 = *((_DWORD *)a1 + 6);
  if ( v7 == 5 )
  {
    v8 = EventArgsType_TextEditTextChanged;
    goto LABEL_5;
  }
  if ( v7 > 5 )
  {
    v54 = v7 - 6;
    if ( v54 )
    {
      v55 = v54 - 1;
      if ( v55 )
      {
        v56 = v55 - 1;
        if ( v56 )
        {
          if ( v56 != 1 )
            goto LABEL_91;
          v8 = EventArgsType_ActiveTextPositionChanged|EventArgsType_PropertyChanged;
        }
        else
        {
          v8 = EventArgsType_ActiveTextPositionChanged;
        }
      }
      else
      {
        v8 = EventArgsType_Notification;
      }
    }
    else
    {
      v8 = EventArgsType_Changes;
    }
  }
  else
  {
    if ( !v7 )
    {
      v8 = EventArgsType_Simple;
      goto LABEL_5;
    }
    v22 = v7 - 1;
    if ( !v22 )
    {
      v8 = EventArgsType_PropertyChanged;
      goto LABEL_5;
    }
    v52 = v22 - 1;
    if ( v52 )
    {
      v53 = v52 - 1;
      if ( v53 )
      {
        if ( v53 == 1 )
        {
          v8 = EventArgsType_WindowClosed;
          goto LABEL_5;
        }
LABEL_91:
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8DF,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\protobufhelper.cpp",
          (const char *)0x8000FFFFLL,
          (int)v82);
      }
      v8 = EventArgsType_AsyncContentLoaded;
    }
    else
    {
      v8 = EventArgsType_StructureChanged;
    }
  }
LABEL_5:
  v9 = (const struct UIAutomationCoreProto::GuidMsg *)&UIAutomationCoreProto::_GuidMsg_default_instance_;
  v10 = &UIAutomationCoreProto::_GuidMsg_default_instance_;
  if ( *((_QWORD *)a1 + 2) )
    v10 = (_QWORD *)*((_QWORD *)a1 + 2);
  v11 = &UIAutomationCoreProto::_WstringMsg_default_instance_;
  v12 = &UIAutomationCoreProto::_WstringMsg_default_instance_;
  if ( v10[2] )
    v12 = (void *)v10[2];
  ProtobufHelper::GetWstring(&lpsz, v12);
  iid = 0;
  p_lpsz = &lpsz;
  if ( v86 > 7 )
    p_lpsz = *(VARIANTARG **)&lpsz.vt;
  v14 = IIDFromString(&p_lpsz->vt, &iid);
  v15 = retaddr;
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\protobufhelper.cpp",
      (const char *)(unsigned int)v14,
      (int)v82);
  v16 = iid;
  v17 = v86;
  if ( v86 > 7 )
  {
    v82 = (struct IUnknown *)(2 * v86 + 2);
    v18 = *(void **)&lpsz.vt;
    *(_QWORD *)&pvarg.vt = *(_QWORD *)&lpsz.vt;
    if ( (unsigned __int64)v82 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned((void **)&pvarg, (unsigned __int64 *)&v82);
      v18 = *(void **)&pvarg.vt;
    }
    operator delete(v18);
  }
  iid = v16;
  v19 = LookupBaseFromGUID_NoLock<EventInfo const,UserDefinedEventInfo>(v15, v17, &iid);
  if ( v19 )
    v6 = *(_DWORD *)(v19 + 8);
  if ( (unsigned int)v8 > EventArgsType_TextEditTextChanged )
  {
    switch ( v8 )
    {
      case EventArgsType_Changes:
        if ( *((_DWORD *)a1 + 11) == 15 )
          v51 = (const struct UIAutomationCoreProto::ChangesEventPayloadMsg *)*((_QWORD *)a1 + 4);
        else
          v51 = (const struct UIAutomationCoreProto::ChangesEventPayloadMsg *)&UIAutomationCoreProto::_ChangesEventPayloadMsg_default_instance_;
        LODWORD(v82) = 0;
        *(_QWORD *)&iid.Data1 = 0;
        ProtobufHelper::GetChangesEventPayload(v51, (struct UiaChangeInfo **)&iid, (int *)&v82, a3);
        v80 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
        *(_QWORD *)&pvarg.vt = v80;
        if ( !v80 )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0xB41,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\protobufhelper.cpp",
            v81);
        v80[2] = (_DWORD)v82;
        *((_QWORD *)v80 + 2) = *(_QWORD *)&iid.Data1;
        *(_QWORD *)&pvarg.vt = 0;
        *a2 = (struct UiaEventArgs *)v80;
        std::unique_ptr<UiaWindowClosedEventArgs>::~unique_ptr<UiaWindowClosedEventArgs>(&pvarg);
        break;
      case EventArgsType_Notification:
        if ( *((_DWORD *)a1 + 11) == 18 )
          v50 = (const struct UIAutomationCoreProto::NotificationPayloadMsg *)*((_QWORD *)a1 + 4);
        else
          v50 = (const struct UIAutomationCoreProto::NotificationPayloadMsg *)&UIAutomationCoreProto::_NotificationPayloadMsg_default_instance_;
        UIAutomationCoreProto::NotificationPayloadMsg::NotificationPayloadMsg(
          (UIAutomationCoreProto::NotificationPayloadMsg *)&lpsz,
          v50);
        v72 = operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
        *(_QWORD *)&iid.Data1 = v72;
        if ( !v72 )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0xB6F,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\protobufhelper.cpp",
            v73);
        v72[2] = ProtobufHelper::ToUiaNotificationKind(v87);
        v72[3] = ProtobufHelper::ToUiaNotificationProcessing(v88);
        pRecInfo = (IRecordInfo *)&UIAutomationCoreProto::_WstringMsg_default_instance_;
        if ( lpsz.pRecInfo )
          pRecInfo = lpsz.pRecInfo;
        LOBYTE(v74) = 1;
        Bstr = (__int64 *)ProtobufHelper::GetBstr(&pvarg, pRecInfo, v74);
        v77 = *Bstr;
        *Bstr = 0;
        *((_QWORD *)v72 + 2) = v77;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pvarg);
        if ( v86 )
          v11 = (void *)v86;
        v78 = (__int64 *)ProtobufHelper::GetBstr(&pvarg, v11, 0);
        v79 = *v78;
        *v78 = 0;
        *((_QWORD *)v72 + 3) = v79;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pvarg);
        *(_QWORD *)&iid.Data1 = 0;
        *a2 = (struct UiaEventArgs *)v72;
        std::unique_ptr<UiaNotificationEventArgs>::~unique_ptr<UiaNotificationEventArgs>(&iid);
        UIAutomationCoreProto::NotificationPayloadMsg::~NotificationPayloadMsg((UIAutomationCoreProto::NotificationPayloadMsg *)&lpsz);
        break;
      case EventArgsType_ActiveTextPositionChanged:
        if ( *((_DWORD *)a1 + 11) == 19 )
          v48 = (void *)*((_QWORD *)a1 + 4);
        else
          v48 = &UIAutomationCoreProto::_ActiveTextPositionChangedPayloadMsg_default_instance_;
        v69 = (struct UiaEventArgs *)operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
        v71 = v69;
        if ( v69 )
        {
          v69[1] = 0;
          v69[2] = 0;
        }
        else
        {
          v71 = 0;
        }
        *(_QWORD *)&iid.Data1 = v71;
        if ( !v71 )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0xB7C,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\protobufhelper.cpp",
            v70);
        v82 = 0;
        wil::com_ptr_t<IAccessible2,wil::err_exception_policy>::reset(&v82);
        v49 = (const struct UIAutomationCoreProto::TextRangeMsg *)&UIAutomationCoreProto::_TextRangeMsg_default_instance_;
        if ( *((_QWORD *)v48 + 2) )
          v49 = (const struct UIAutomationCoreProto::TextRangeMsg *)*((_QWORD *)v48 + 2);
        ProtobufHelper::GetTextRange(v49, &v82, a3);
        if ( v82 )
        {
          wil::com_ptr_t<ITextRangeProvider,wil::err_exception_policy>::com_ptr_t<ITextRangeProvider,wil::err_exception_policy>(&pvarg);
          wil::com_ptr_t<IAgileReference,wil::err_exception_policy>::operator=(&v71[1], &pvarg);
          wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&pvarg);
        }
        *(_QWORD *)&iid.Data1 = 0;
        *a2 = v71;
        wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v82);
        std::unique_ptr<UiaActiveTextPositionChangedEventArgs>::~unique_ptr<UiaActiveTextPositionChangedEventArgs>(&iid);
        break;
      default:
        if ( *((_DWORD *)a1 + 11) == 20 )
          v46 = (void *)*((_QWORD *)a1 + 4);
        else
          v46 = &UIAutomationCoreProto::_StructureMarkupPayloadMsg_default_instance_;
        v65 = (struct UiaEventArgs *)operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
        v67 = v65;
        if ( v65 )
        {
          v65[1] = 0;
          v65[2] = 0;
        }
        else
        {
          v67 = 0;
        }
        *(_QWORD *)&pvarg.vt = v67;
        if ( !v67 )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0xB8E,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\protobufhelper.cpp",
            v66);
        v82 = 0;
        wil::com_ptr_t<IAccessible2,wil::err_exception_policy>::reset(&v82);
        v37 = (const struct UIAutomationCoreProto::StructuredMarkupRangeMsg *)&UIAutomationCoreProto::_StructuredMarkupRangeMsg_default_instance_;
        if ( *((_QWORD *)v46 + 2) )
          v37 = (const struct UIAutomationCoreProto::StructuredMarkupRangeMsg *)*((_QWORD *)v46 + 2);
        ProtobufHelper::GetStructuredMarkupRange(v37, a3, &v82);
        v38 = v82;
        if ( v82 )
        {
          v68 = v67[1];
          v67[1] = 0;
          if ( v68 )
            (*(void (__fastcall **)(struct UiaEventArgs))(**(_QWORD **)&v68 + 16LL))(v68);
          v47 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct UiaEventArgs *))v38->lpVtbl->QueryInterface)(
                  v38,
                  &GUID_65a73f38_15ba_445f_b41d_46054a5efc50,
                  &v67[1]);
          if ( v47 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xB94,
              (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\protobufhelper.cpp",
              (const char *)(unsigned int)v47,
              (int)v82);
        }
        *(_QWORD *)&pvarg.vt = 0;
        *a2 = v67;
        wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v82);
        std::unique_ptr<UiaActiveTextPositionChangedEventArgs>::~unique_ptr<UiaActiveTextPositionChangedEventArgs>(&pvarg);
        break;
    }
  }
  else if ( v8 == EventArgsType_TextEditTextChanged )
  {
    if ( *((_DWORD *)a1 + 11) == 14 )
      v45 = (unsigned int *)*((_QWORD *)a1 + 4);
    else
      v45 = (unsigned int *)&UIAutomationCoreProto::_TextEditTextChangedEventPayloadMsg_default_instance_;
    v61 = ProtobufHelper::ToUiaTextEditChangeType(v45[6]);
    *(_QWORD *)&pvarg.vt = 0;
    v62 = (const struct UIAutomationCoreProto::WstringArrayMsg *)&UIAutomationCoreProto::_WstringArrayMsg_default_instance_;
    if ( *((_QWORD *)v45 + 2) )
      v62 = (const struct UIAutomationCoreProto::WstringArrayMsg *)*((_QWORD *)v45 + 2);
    ProtobufHelper::GetStringArray(v62, (struct tagSAFEARRAY **)&pvarg);
    v63 = (struct IUnknown *)operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
    v82 = v63;
    if ( !v63 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xB2F,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\protobufhelper.cpp",
        v64);
    LODWORD(v63[1].lpVtbl) = v61;
    v63[2].lpVtbl = *(struct IUnknownVtbl **)&pvarg.vt;
    v82 = 0;
    *a2 = (struct UiaEventArgs *)v63;
    std::unique_ptr<UiaWindowClosedEventArgs>::~unique_ptr<UiaWindowClosedEventArgs>(&v82);
  }
  else if ( v8 )
  {
    switch ( v8 )
    {
      case EventArgsType_PropertyChanged:
        if ( *((_DWORD *)a1 + 11) == 12 )
          v23 = (_QWORD *)*((_QWORD *)a1 + 4);
        else
          v23 = &UIAutomationCoreProto::_PropertyChangedEventPayloadMsg_default_instance_;
        VariantInit(&lpsz);
        lpsz.llVal = 0;
        VariantInit(&pvarg);
        pvarg.llVal = 0;
        if ( v23[2] )
          v9 = (const struct UIAutomationCoreProto::GuidMsg *)v23[2];
        AutomationId = ProtobufHelper::GetAutomationId(v9, AutomationIdentifierType_Property);
        v25 = (const struct UIAutomationCoreProto::VariantObjectMsg *)&UIAutomationCoreProto::_VariantObjectMsg_default_instance_;
        v26 = (const struct UIAutomationCoreProto::VariantObjectMsg *)&UIAutomationCoreProto::_VariantObjectMsg_default_instance_;
        if ( v23[3] )
          v26 = (const struct UIAutomationCoreProto::VariantObjectMsg *)v23[3];
        ProtobufHelper::GetObj(v26, &lpsz, a3);
        if ( v23[4] )
          v25 = (const struct UIAutomationCoreProto::VariantObjectMsg *)v23[4];
        ProtobufHelper::GetObj(v25, &pvarg, a3);
        v27 = (char *)operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
        v29 = v27;
        *(_QWORD *)&iid.Data1 = v27;
        if ( !v27 )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0xB05,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\protobufhelper.cpp",
            v28);
        *((_DWORD *)v27 + 2) = AutomationId;
        *(VARIANTARG *)(v27 + 16) = lpsz;
        VariantInit(&lpsz);
        lpsz.llVal = 0;
        *(VARIANTARG *)(v29 + 40) = pvarg;
        VariantInit(&pvarg);
        pvarg.llVal = 0;
        *a2 = (struct UiaEventArgs *)v29;
        VariantClear(&pvarg);
        VariantClear(&lpsz);
        break;
      case EventArgsType_StructureChanged:
        if ( *((_DWORD *)a1 + 11) == 13 )
          v30 = (unsigned int *)*((_QWORD *)a1 + 4);
        else
          v30 = (unsigned int *)&UIAutomationCoreProto::_StructureChangedEventPayloadMsg_default_instance_;
        v31 = ProtobufHelper::ToUiaStructureChangeType(v30[6]);
        *(_DWORD *)&pvarg.vt = 0;
        pvarg.llVal = 0;
        v32 = (const struct UIAutomationCoreProto::IntArrayMsg *)&UIAutomationCoreProto::_IntArrayMsg_default_instance_;
        v33 = (char *)&UIAutomationCoreProto::_IntArrayMsg_default_instance_;
        if ( *((_QWORD *)v30 + 2) )
          v33 = (char *)*((_QWORD *)v30 + 2);
        v34 = google::protobuf::RepeatedField<bool>::size(v33 + 16);
        BasicArrayPair<int>::AllocInit(&pvarg, v34);
        if ( *((_QWORD *)v30 + 2) )
          v32 = (const struct UIAutomationCoreProto::IntArrayMsg *)*((_QWORD *)v30 + 2);
        ProtobufHelper::GetIntArray(v32, &pvarg.plVal, (int *)&pvarg);
        v35 = operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
        *(_QWORD *)&iid.Data1 = v35;
        if ( !v35 )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0xB1B,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\protobufhelper.cpp",
            v36);
        v35[2] = v31;
        *((_QWORD *)v35 + 2) = pvarg.llVal;
        v35[6] = *(_DWORD *)&pvarg.vt;
        *a2 = (struct UiaEventArgs *)v35;
        break;
      case EventArgsType_AsyncContentLoaded:
        if ( *((_DWORD *)a1 + 11) == 16 )
          v44 = (_QWORD *)*((_QWORD *)a1 + 4);
        else
          v44 = &UIAutomationCoreProto::_AsyncContentLoadedPayloadMsg_default_instance_;
        v59 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
        *(_QWORD *)&pvarg.vt = v59;
        if ( !v59 )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0xB4F,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\protobufhelper.cpp",
            v60);
        v59[2] = ProtobufHelper::ToUiaAsyncContentLoadedState(*((unsigned int *)v44 + 6));
        *((_QWORD *)v59 + 2) = v44[2];
        *(_QWORD *)&pvarg.vt = 0;
        *a2 = (struct UiaEventArgs *)v59;
        std::unique_ptr<UiaWindowClosedEventArgs>::~unique_ptr<UiaWindowClosedEventArgs>(&pvarg);
        break;
      default:
        if ( *((_DWORD *)a1 + 11) == 17 )
          v39 = (void *)*((_QWORD *)a1 + 4);
        else
          v39 = &UIAutomationCoreProto::_WindowClosedPayloadMsg_default_instance_;
        iid.Data1 = 0;
        *(_QWORD *)iid.Data4 = 0;
        v40 = (const struct UIAutomationCoreProto::IntArrayMsg *)&UIAutomationCoreProto::_IntArrayMsg_default_instance_;
        v41 = (char *)&UIAutomationCoreProto::_IntArrayMsg_default_instance_;
        if ( *((_QWORD *)v39 + 2) )
          v41 = (char *)*((_QWORD *)v39 + 2);
        v42 = google::protobuf::RepeatedField<bool>::size(v41 + 16);
        v43 = BasicArrayPair<int>::AllocInit(&iid, v42);
        if ( v43 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xB5B,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\protobufhelper.cpp",
            (const char *)(unsigned int)v43,
            (int)v82);
        if ( *((_QWORD *)v39 + 2) )
          v40 = (const struct UIAutomationCoreProto::IntArrayMsg *)*((_QWORD *)v39 + 2);
        ProtobufHelper::GetIntArray(v40, (int **)iid.Data4, (int *)&iid);
        v57 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
        *(_QWORD *)&pvarg.vt = v57;
        if ( !v57 )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0xB5F,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\protobufhelper.cpp",
            v58);
        v57[1] = *(_QWORD *)iid.Data4;
        *((_DWORD *)v57 + 4) = iid.Data1;
        *(_QWORD *)&pvarg.vt = 0;
        *a2 = (struct UiaEventArgs *)v57;
        std::unique_ptr<UiaWindowClosedEventArgs>::~unique_ptr<UiaWindowClosedEventArgs>(&pvarg);
        break;
    }
  }
  else
  {
    v20 = (struct UiaEventArgs *)operator new(8u, (const struct std::nothrow_t *)std::nothrow);
    *a2 = v20;
    if ( !v20 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xAF4,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\protobufhelper.cpp",
        v21);
  }
  (*a2)->Type = v8;
  (*a2)->EventId = v6;
}

```

## disassembly

```asm
0x180025654  mov     rax, rsp
0x180025657  mov     [rax+20h], rbx
0x18002565b  push    rbp
0x18002565c  push    rsi
0x18002565d  push    rdi
0x18002565e  push    r12
0x180025660  push    r13
0x180025662  push    r14
0x180025664  push    r15
0x180025666  lea     rbp, [rax-5Fh]
0x18002566a  sub     rsp, 0A0h
0x180025671  movaps  xmmword ptr [rax-48h], xmm6
0x180025675  mov     rax, cs:__security_cookie
0x18002567c  xor     rax, rsp
0x18002567f  mov     [rbp+57h+var_50], rax
0x180025683  mov     r15, r8
0x180025686  mov     rsi, rdx
0x180025689  mov     rbx, rcx
0x18002568c  xor     r13d, r13d
0x18002568f  mov     [rdx], r13
0x180025692  mov     r8d, [rcx+18h]
0x180025696  cmp     r8d, 5
0x18002569a  jz      loc_1800259D7
0x1800256a0  jg      loc_180025BDB
0x1800256a6  test    r8d, r8d
0x1800256a9  jnz     loc_1800257D1
0x1800256af  mov     edi, r13d
0x1800256b2  lea     r12, ?_GuidMsg_default_instance_@UIAutomationCoreProto@@3UGuidMsgDefaultTypeInternal@1@A; UIAutomationCoreProto::GuidMsgDefaultTypeInternal UIAutomationCoreProto::_GuidMsg_default_instance_
0x1800256b9  mov     rax, r12
0x1800256bc  cmp     [rcx+10h], r13
0x1800256c0  cmovnz  rax, [rcx+10h]
0x1800256c5  lea     r14, ?_WstringMsg_default_instance_@UIAutomationCoreProto@@3UWstringMsgDefaultTypeInternal@1@A; UIAutomationCoreProto::WstringMsgDefaultTypeInternal UIAutomationCoreProto::_WstringMsg_default_instance_
0x1800256cc  mov     rdx, r14
0x1800256cf  cmp     [rax+10h], r13
0x1800256d3  cmovnz  rdx, [rax+10h]
0x1800256d8  lea     rcx, [rbp+57h+lpsz]
0x1800256dc  call    ?GetWstring@ProtobufHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVWstringMsg@UIAutomationCoreProto@@@Z; ProtobufHelper::GetWstring(UIAutomationCoreProto::WstringMsg const &)
0x1800256e1  nop
0x1800256e2  xorps   xmm0, xmm0
0x1800256e5  movups  xmmword ptr [rbp+57h+iid.Data1], xmm0
0x1800256e9  lea     rcx, [rbp+57h+lpsz]
0x1800256ed  cmp     [rbp+57h+var_68], 7
0x1800256f2  cmova   rcx, [rbp+57h+lpsz]; lpsz
0x1800256f7  lea     rdx, [rbp+57h+iid]; lpiid
0x1800256fb  call    cs:__imp_IIDFromString
0x180025701  mov     rcx, [rbp+5Fh]; this
0x180025705  test    eax, eax
0x180025707  jns     short loc_18002571E
0x180025709  mov     r9d, eax; char *
0x18002570c  lea     r8, aOnecoreWindows_122; "onecore\\windows\\accessibletech\\uiaut"...
0x180025713  mov     edx, 46h ; 'F'; void *
0x180025718  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002571e  movaps  xmm6, xmmword ptr [rbp+57h+iid.Data1]
0x180025722  mov     rdx, [rbp+57h+var_68]
0x180025726  cmp     rdx, 7
0x18002572a  jbe     short loc_180025752
0x18002572c  lea     rdx, ds:2[rdx*2]
0x180025734  mov     [rbp+57h+var_B0], rdx
0x180025738  mov     rcx, [rbp+57h+lpsz]; Block
0x18002573c  mov     qword ptr [rbp+57h+pvarg], rcx
0x180025740  cmp     rdx, 1000h
0x180025747  jnb     loc_180025C36
0x18002574d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180025752  movdqa  xmmword ptr [rbp+57h+iid.Data1], xmm6
0x180025757  lea     r8, [rbp+57h+iid]
0x18002575b  call    ??$LookupBaseFromGUID_NoLock@$$CBUEventInfo@@UUserDefinedEventInfo@@@@YAPEBUBaseInfo@@PEBUEventInfo@@HPEBU_GUID@@PEAUUserDefinedEventInfo@@@Z; LookupBaseFromGUID_NoLock<EventInfo const,UserDefinedEventInfo>(EventInfo const *,int,_GUID const *,UserDefinedEventInfo *)
0x180025760  test    rax, rax
0x180025763  jz      short loc_180025769
0x180025765  mov     r13d, [rax+8]
0x180025769  cmp     edi, 5
0x18002576c  ja      loc_180025DDC
0x180025772  jz      loc_180025AB0
0x180025778  mov     ecx, edi
0x18002577a  test    edi, edi
0x18002577c  jnz     short loc_1800257E4
0x18002577e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180025785  lea     ecx, [rdi+8]; unsigned __int64
0x180025788  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002578d  mov     [rsi], rax
0x180025790  test    rax, rax
0x180025793  jz      loc_180025D44
0x180025799  mov     rax, [rsi]
0x18002579c  mov     [rax], edi
0x18002579e  mov     rax, [rsi]
0x1800257a1  mov     [rax+4], r13d
0x1800257a5  mov     rcx, [rbp+57h+var_50]
0x1800257a9  xor     rcx, rsp; StackCookie
0x1800257ac  call    __security_check_cookie
0x1800257b1  lea     r11, [rsp+0D0h+var_30]
0x1800257b9  mov     rbx, [r11+58h]
0x1800257bd  movaps  xmm6, xmmword ptr [r11-10h]
0x1800257c2  mov     rsp, r11
0x1800257c5  pop     r15
0x1800257c7  pop     r14
0x1800257c9  pop     r13
0x1800257cb  pop     r12
0x1800257cd  pop     rdi
0x1800257ce  pop     rsi
0x1800257cf  pop     rbp
0x1800257d0  retn
0x1800257d1  sub     r8d, 1
0x1800257d5  jnz     loc_180025BAC
0x1800257db  lea     edi, [r8+1]
0x1800257df  jmp     loc_1800256B2
0x1800257e4  sub     ecx, 1
0x1800257e7  jnz     loc_180025910
0x1800257ed  cmp     dword ptr [rbx+2Ch], 0Ch
0x1800257f1  jnz     loc_180025904
0x1800257f7  mov     r14, [rbx+20h]
0x1800257fb  lea     rcx, [rbp+57h+lpsz]; pvarg
0x1800257ff  call    cs:__imp_VariantInit
0x180025805  xor     ebx, ebx
0x180025807  mov     [rbp+57h+lpsz+8], rbx
0x18002580b  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002580f  call    cs:__imp_VariantInit
0x180025815  mov     qword ptr [rbp+57h+pvarg+8], rbx
0x180025819  cmp     [r14+10h], rbx
0x18002581d  cmovnz  r12, [r14+10h]
0x180025822  xor     edx, edx; enum AutomationIdentifierType
0x180025824  mov     rcx, r12; struct UIAutomationCoreProto::GuidMsg *
0x180025827  call    ?GetAutomationId@ProtobufHelper@@CAHAEBVGuidMsg@UIAutomationCoreProto@@W4AutomationIdentifierType@@@Z; ProtobufHelper::GetAutomationId(UIAutomationCoreProto::GuidMsg const &,AutomationIdentifierType)
0x18002582c  mov     r12d, eax
0x18002582f  lea     rbx, ?_VariantObjectMsg_default_instance_@UIAutomationCoreProto@@3UVariantObjectMsgDefaultTypeInternal@1@A; UIAutomationCoreProto::VariantObjectMsgDefaultTypeInternal UIAutomationCoreProto::_VariantObjectMsg_default_instance_
0x180025836  mov     rcx, rbx
0x180025839  cmp     qword ptr [r14+18h], 0
0x18002583e  cmovnz  rcx, [r14+18h]; struct UIAutomationCoreProto::VariantObjectMsg *
0x180025843  mov     r8, r15; struct IClientConnection *
0x180025846  lea     rdx, [rbp+57h+lpsz]; struct tagVARIANT *
0x18002584a  call    ?GetObj@ProtobufHelper@@SAXAEBVVariantObjectMsg@UIAutomationCoreProto@@PEAUtagVARIANT@@PEAVIClientConnection@@@Z; ProtobufHelper::GetObj(UIAutomationCoreProto::VariantObjectMsg const &,tagVARIANT *,IClientConnection *)
0x18002584f  cmp     qword ptr [r14+20h], 0
0x180025854  cmovnz  rbx, [r14+20h]
0x180025859  mov     r8, r15; struct IClientConnection *
0x18002585c  lea     rdx, [rbp+57h+pvarg]; struct tagVARIANT *
0x180025860  mov     rcx, rbx; struct UIAutomationCoreProto::VariantObjectMsg *
0x180025863  call    ?GetObj@ProtobufHelper@@SAXAEBVVariantObjectMsg@UIAutomationCoreProto@@PEAUtagVARIANT@@PEAVIClientConnection@@@Z; ProtobufHelper::GetObj(UIAutomationCoreProto::VariantObjectMsg const &,tagVARIANT *,IClientConnection *)
0x180025868  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002586f  mov     ecx, 40h ; '@'; unsigned __int64
0x180025874  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180025879  mov     rbx, rax
0x18002587c  mov     qword ptr [rbp+57h+iid.Data1], rax
0x180025880  mov     rcx, [rbp+5Fh]; this
0x180025884  test    rax, rax
0x180025887  jnz     short loc_18002589B
0x180025889  lea     r8, aOnecoreWindows_122; "onecore\\windows\\accessibletech\\uiaut"...
0x180025890  mov     edx, 0B05h; void *
0x180025895  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18002589b  mov     [rax+8], r12d
0x18002589f  movups  xmm0, xmmword ptr [rbp+57h+lpsz]
0x1800258a3  movups  xmmword ptr [rax+10h], xmm0
0x1800258a7  movsd   xmm1, [rbp+57h+var_70]
0x1800258ac  movsd   qword ptr [rax+20h], xmm1
0x1800258b1  lea     rcx, [rbp+57h+lpsz]; pvarg
0x1800258b5  call    cs:__imp_VariantInit
0x1800258bb  mov     [rbp+57h+lpsz+8], 0
0x1800258c3  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x1800258c7  movups  xmmword ptr [rbx+28h], xmm0
0x1800258cb  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x1800258d0  movsd   qword ptr [rbx+38h], xmm1
0x1800258d5  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800258d9  call    cs:__imp_VariantInit
0x1800258df  mov     qword ptr [rbp+57h+pvarg+8], 0
0x1800258e7  mov     [rsi], rbx
0x1800258ea  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800258ee  call    cs:__imp_VariantClear
0x1800258f4  nop
0x1800258f5  lea     rcx, [rbp+57h+lpsz]; pvarg
0x1800258f9  call    cs:__imp_VariantClear
0x1800258ff  jmp     loc_180025799
0x180025904  lea     r14, ?_PropertyChangedEventPayloadMsg_default_instance_@UIAutomationCoreProto@@3UPropertyChangedEventPayloadMsgDefaultTypeInternal@1@A; UIAutomationCoreProto::PropertyChangedEventPayloadMsgDefaultTypeInternal UIAutomationCoreProto::_PropertyChangedEventPayloadMsg_default_instance_
0x18002590b  jmp     loc_1800257FB
0x180025910  sub     ecx, 1
0x180025913  jnz     loc_180025C50
0x180025919  cmp     dword ptr [rbx+2Ch], 0Dh
0x18002591d  jnz     loc_1800259B1
0x180025923  mov     r14, [rbx+20h]
0x180025927  mov     ecx, [r14+18h]
0x18002592b  call    ?ToUiaStructureChangeType@ProtobufHelper@@SA?AW4StructureChangeType@@W4StructureChangeTypeProto@UIAutomationCoreProto@@@Z; ProtobufHelper::ToUiaStructureChangeType(UIAutomationCoreProto::StructureChangeTypeProto)
0x180025930  mov     r15d, eax
0x180025933  xor     r12d, r12d
0x180025936  mov     dword ptr [rbp+57h+pvarg], r12d
0x18002593a  mov     qword ptr [rbp+57h+pvarg+8], r12
0x18002593e  lea     rbx, ?_IntArrayMsg_default_instance_@UIAutomationCoreProto@@3UIntArrayMsgDefaultTypeInternal@1@A; UIAutomationCoreProto::IntArrayMsgDefaultTypeInternal UIAutomationCoreProto::_IntArrayMsg_default_instance_
0x180025945  mov     rcx, rbx
0x180025948  cmp     [r14+10h], r12
0x18002594c  cmovnz  rcx, [r14+10h]
0x180025951  add     rcx, 10h
0x180025955  call    ?size@?$RepeatedField@_N@protobuf@google@@QEBAHXZ; google::protobuf::RepeatedField<bool>::size(void)
0x18002595a  mov     edx, eax
0x18002595c  lea     rcx, [rbp+57h+pvarg]
0x180025960  call    ?AllocInit@?$BasicArrayPair@H@@QEAAJI@Z; BasicArrayPair<int>::AllocInit(uint)
0x180025965  cmp     [r14+10h], r12
0x180025969  cmovnz  rbx, [r14+10h]
0x18002596e  lea     r8, [rbp+57h+pvarg]; int *
0x180025972  lea     rdx, [rbp+57h+pvarg+8]; int **
0x180025976  mov     rcx, rbx; struct UIAutomationCoreProto::IntArrayMsg *
0x180025979  call    ?GetIntArray@ProtobufHelper@@SAXAEBVIntArrayMsg@UIAutomationCoreProto@@PEAPEAHPEAH@Z; ProtobufHelper::GetIntArray(UIAutomationCoreProto::IntArrayMsg const &,int * *,int *)
0x18002597e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180025985  lea     ecx, [r12+20h]; unsigned __int64
0x18002598a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002598f  mov     rdx, rax
0x180025992  mov     qword ptr [rbp+57h+iid.Data1], rax
0x180025996  mov     rcx, [rbp+5Fh]; this
0x18002599a  test    rax, rax
0x18002599d  jnz     short loc_1800259BD
0x18002599f  lea     r8, aOnecoreWindows_122; "onecore\\windows\\accessibletech\\uiaut"...
0x1800259a6  mov     edx, 0B1Bh; void *
0x1800259ab  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800259b1  lea     r14, ?_StructureChangedEventPayloadMsg_default_instance_@UIAutomationCoreProto@@3UStructureChangedEventPayloadMsgDefaultTypeInternal@1@A; UIAutomationCoreProto::StructureChangedEventPayloadMsgDefaultTypeInternal UIAutomationCoreProto::_StructureChangedEventPayloadMsg_default_instance_
0x1800259b8  jmp     loc_180025927
0x1800259bd  mov     [rax+8], r15d
0x1800259c1  mov     rax, qword ptr [rbp+57h+pvarg+8]
0x1800259c5  mov     [rdx+10h], rax
0x1800259c9  mov     eax, dword ptr [rbp+57h+pvarg]
0x1800259cc  mov     [rdx+18h], eax
0x1800259cf  mov     [rsi], rdx
0x1800259d2  jmp     loc_180025799
0x1800259d7  mov     edi, 5
0x1800259dc  jmp     loc_1800256B2
0x1800259e1  mov     [rbp+57h+var_B0], r12
0x1800259e5  lea     rcx, [rbp+57h+var_B0]
0x1800259e9  call    ?reset@?$com_ptr_t@UIAccessible2@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IAccessible2,wil::err_exception_policy>::reset(void)
0x1800259ee  lea     rcx, ?_StructuredMarkupRangeMsg_default_instance_@UIAutomationCoreProto@@3UStructuredMarkupRangeMsgDefaultTypeInternal@1@A; UIAutomationCoreProto::StructuredMarkupRangeMsgDefaultTypeInternal UIAutomationCoreProto::_StructuredMarkupRangeMsg_default_instance_
0x1800259f5  cmp     [r14+10h], r12
0x1800259f9  cmovnz  rcx, [r14+10h]; struct UIAutomationCoreProto::StructuredMarkupRangeMsg *
0x1800259fe  lea     r8, [rbp+57h+var_B0]; struct IUnknown **
0x180025a02  mov     rdx, r15; struct IClientConnection *
0x180025a05  call    ?GetStructuredMarkupRange@ProtobufHelper@@SAXAEBVStructuredMarkupRangeMsg@UIAutomationCoreProto@@PEAVIClientConnection@@PEAPEAUIUnknown@@@Z; ProtobufHelper::GetStructuredMarkupRange(UIAutomationCoreProto::StructuredMarkupRangeMsg const &,IClientConnection *,IUnknown * *)
0x180025a0a  mov     r15, [rbp+57h+var_B0]
0x180025a0e  test    r15, r15
0x180025a11  jnz     loc_180025E77
0x180025a17  mov     qword ptr [rbp+57h+pvarg], r12
0x180025a1b  mov     [rsi], rbx
0x180025a1e  lea     rcx, [rbp+57h+var_B0]; void *
0x180025a22  call    ??1?$com_ptr_t@UIAccessibleAction@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(void)
0x180025a27  nop
0x180025a28  lea     rcx, [rbp+57h+pvarg]
0x180025a2c  call    ??1?$unique_ptr@UUiaActiveTextPositionChangedEventArgs@@U?$default_delete@UUiaActiveTextPositionChangedEventArgs@@@std@@@std@@QEAA@XZ; std::unique_ptr<UiaActiveTextPositionChangedEventArgs>::~unique_ptr<UiaActiveTextPositionChangedEventArgs>(void)
0x180025a31  jmp     loc_180025799
0x180025a36  cmp     dword ptr [rbx+2Ch], 11h
0x180025a3a  jz      loc_180025C67
0x180025a40  lea     r14, ?_WindowClosedPayloadMsg_default_instance_@UIAutomationCoreProto@@3UWindowClosedPayloadMsgDefaultTypeInternal@1@A; UIAutomationCoreProto::WindowClosedPayloadMsgDefaultTypeInternal UIAutomationCoreProto::_WindowClosedPayloadMsg_default_instance_
0x180025a47  xor     r15d, r15d
0x180025a4a  mov     [rbp+57h+iid.Data1], r15d
0x180025a4e  mov     qword ptr [rbp+57h+iid.Data4], r15
0x180025a52  lea     rbx, ?_IntArrayMsg_default_instance_@UIAutomationCoreProto@@3UIntArrayMsgDefaultTypeInternal@1@A; UIAutomationCoreProto::IntArrayMsgDefaultTypeInternal UIAutomationCoreProto::_IntArrayMsg_default_instance_
0x180025a59  mov     rcx, rbx
0x180025a5c  cmp     [r14+10h], r15
0x180025a60  cmovnz  rcx, [r14+10h]
0x180025a65  add     rcx, 10h
0x180025a69  call    ?size@?$RepeatedField@_N@protobuf@google@@QEBAHXZ; google::protobuf::RepeatedField<bool>::size(void)
0x180025a6e  mov     edx, eax
0x180025a70  lea     rcx, [rbp+57h+iid]
0x180025a74  call    ?AllocInit@?$BasicArrayPair@H@@QEAAJI@Z; BasicArrayPair<int>::AllocInit(uint)
0x180025a79  mov     rcx, [rbp+5Fh]; this
0x180025a7d  test    eax, eax
0x180025a7f  jns     loc_180025C70
0x180025a85  mov     r9d, eax; char *
0x180025a88  lea     r8, aOnecoreWindows_122; "onecore\\windows\\accessibletech\\uiaut"...
0x180025a8f  mov     edx, 0B5Bh; void *
0x180025a94  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180025a9a  cmp     dword ptr [rbx+2Ch], 10h
0x180025a9e  jz      loc_180025CE0
0x180025aa4  lea     r14, ?_AsyncContentLoadedPayloadMsg_default_instance_@UIAutomationCoreProto@@3UAsyncContentLoadedPayloadMsgDefaultTypeInternal@1@A; UIAutomationCoreProto::AsyncContentLoadedPayloadMsgDefaultTypeInternal UIAutomationCoreProto::_AsyncContentLoadedPayloadMsg_default_instance_
0x180025aab  jmp     loc_180025CE4
0x180025ab0  cmp     dword ptr [rbx+2Ch], 0Eh
0x180025ab4  jz      loc_180025D5A
0x180025aba  lea     rbx, ?_TextEditTextChangedEventPayloadMsg_default_instance_@UIAutomationCoreProto@@3UTextEditTextChangedEventPayloadMsgDefaultTypeInternal@1@A; UIAutomationCoreProto::TextEditTextChangedEventPayloadMsgDefaultTypeInternal UIAutomationCoreProto::_TextEditTextChangedEventPayloadMsg_default_instance_
0x180025ac1  jmp     loc_180025D5E
0x180025ac6  cmp     dword ptr [rbx+2Ch], 14h
0x180025aca  jz      loc_180025E27
0x180025ad0  lea     r14, ?_StructureMarkupPayloadMsg_default_instance_@UIAutomationCoreProto@@3UStructureMarkupPayloadMsgDefaultTypeInternal@1@A; UIAutomationCoreProto::StructureMarkupPayloadMsgDefaultTypeInternal UIAutomationCoreProto::_StructureMarkupPayloadMsg_default_instance_
0x180025ad7  jmp     loc_180025E2B
0x180025adc  mov     rax, [r15]
0x180025adf  mov     r8, r14
0x180025ae2  lea     rdx, _GUID_65a73f38_15ba_445f_b41d_46054a5efc50
0x180025ae9  mov     rcx, r15
0x180025aec  mov     rax, [rax]
0x180025aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025af4  mov     rcx, [rbp+5Fh]; this
0x180025af8  test    eax, eax
0x180025afa  jns     loc_180025A17
0x180025b00  mov     r9d, eax; char *
0x180025b03  lea     r8, aOnecoreWindows_122; "onecore\\windows\\accessibletech\\uiaut"...
0x180025b0a  mov     edx, 0B94h; void *
0x180025b0f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180025b15  cmp     dword ptr [rbx+2Ch], 13h
0x180025b19  jz      loc_180025E9B
0x180025b1f  lea     r14, ?_ActiveTextPositionChangedPayloadMsg_default_instance_@UIAutomationCoreProto@@3UActiveTextPositionChangedPayloadMsgDefaultTypeInternal@1@A; UIAutomationCoreProto::ActiveTextPositionChangedPayloadMsgDefaultTypeInternal UIAutomationCoreProto::_ActiveTextPositionChangedPayloadMsg_default_instance_
0x180025b26  jmp     loc_180025E9F
0x180025b2b  mov     [rbp+57h+var_B0], r12
0x180025b2f  lea     rcx, [rbp+57h+var_B0]
0x180025b33  call    ?reset@?$com_ptr_t@UIAccessible2@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IAccessible2,wil::err_exception_policy>::reset(void)
0x180025b38  lea     rcx, ?_TextRangeMsg_default_instance_@UIAutomationCoreProto@@3UTextRangeMsgDefaultTypeInternal@1@A; UIAutomationCoreProto::TextRangeMsgDefaultTypeInternal UIAutomationCoreProto::_TextRangeMsg_default_instance_
0x180025b3f  cmp     [r14+10h], r12
0x180025b43  cmovnz  rcx, [r14+10h]; struct UIAutomationCoreProto::TextRangeMsg *
0x180025b48  mov     r8, r15; struct IClientConnection *
0x180025b4b  lea     rdx, [rbp+57h+var_B0]; struct IUnknown **
0x180025b4f  call    ?GetTextRange@ProtobufHelper@@SAXAEBVTextRangeMsg@UIAutomationCoreProto@@PEAPEAUIUnknown@@PEAVIClientConnection@@@Z; ProtobufHelper::GetTextRange(UIAutomationCoreProto::TextRangeMsg const &,IUnknown * *,IClientConnection *)
0x180025b54  mov     rdx, [rbp+57h+var_B0]
0x180025b58  test    rdx, rdx
  ... truncated ...
```
