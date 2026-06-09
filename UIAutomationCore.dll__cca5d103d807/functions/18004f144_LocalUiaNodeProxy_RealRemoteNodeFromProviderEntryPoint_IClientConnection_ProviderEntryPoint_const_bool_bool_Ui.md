# LocalUiaNodeProxy::RealRemoteNodeFromProviderEntryPoint(IClientConnection *,ProviderEntryPoint const *,bool,bool,UiaNodeType,long,long,HWND__ *,InProcProxyRequest,UIA_TIMEOUTDATA,int,IUiaNode * *,ElementExtraInfo *,CrossMachineConnectionInfo *,std::optional<ElementCompletionInfo> *)

- ea: `0x18004f144`
- end: `0x1800502bc`
- name: `?RealRemoteNodeFromProviderEntryPoint@LocalUiaNodeProxy@@CAJPEAVIClientConnection@@PEBVProviderEntryPoint@@_N2W4UiaNodeType@@JJPEAUHWND__@@UInProcProxyRequest@@UUIA_TIMEOUTDATA@@HPEAPEAVIUiaNode@@PEAUElementExtraInfo@@PEAVCrossMachineConnectionInfo@@PEAV?$optional@UElementCompletionInfo@@@std@@@Z`
- size: `4472`
- prototype: ``
- caller_count: `1`
- callee_count: `51`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180094d28`

## callees

- `0x18000e054`
- `0x180022248`
- `0x180029858`
- `0x18002ad38`
- `0x18002e42c`
- `0x18002f580`
- `0x180031ca8`
- `0x180032724`
- `0x18003331c`
- `0x18003c820`
- `0x18004cb90`
- `0x18004e194`
- `0x18004e668`
- `0x18004e6c8`
- `0x18004f144`
- `0x1800502c4`
- `0x180050444`
- `0x180050944`
- `0x180051508`
- `0x180051ab0`
- `0x180051e28`
- `0x18005633c`
- `0x1800697bc`
- `0x1800d6ee0`
- `0x180101c68`
- `0x180101cd0`
- `0x18010feac`
- `0x18012e294`
- `0x1801390ec`
- `0x180148564`
- `0x180157bac`
- `0x180176ea0`
- `0x18017bb34`
- `0x180181488`
- `0x1801a9230`
- `0x1801b78fc`
- `0x1801d582c`
- `0x1801e8320`
- `0x1801e8344`
- `0x1801e8820`
- `0x1801e887c`
- `0x1801e8a1c`
- `0x1801e8a84`
- `0x1801e9240`
- `0x1801ec660`
- `0x1801fc5ac`
- `0x1801fc5d8`
- `0x1801fc640`
- `0x1802a4530`
- `0x1802a51bc`

## import_xrefs

- `msvcp_win!_Query_perf_frequency` at `0x18004fa5f`
- `msvcp_win!_Query_perf_frequency` at `0x18004fa5f`
- `msvcp_win!_Query_perf_counter` at `0x18004fa68`
- `msvcp_win!_Query_perf_counter` at `0x18004fa68`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004fa3d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004fa3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004fdd0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004fdd0`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f6be`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fac9`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fb11`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fc91`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fd04`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f6be`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fac9`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fb11`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fc91`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fd04`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18004f69d`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18004fa97`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18004fb60`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18004fce3`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18004fdc2`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18004f69d`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18004fa97`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18004fb60`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18004fce3`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18004fdc2`

## string_xrefs

- `0x18004f406`: `onecore\windows\accessibletech\uiautomationcore\protobufhelper.cpp`
- `0x18004ff5e`: `onecore\windows\accessibletech\uiautomationcore\protobufhelper.cpp`
- `0x18004f28b`: `onecore\windows\accessibletech\uiautomationcore\localuianodeproxy.cpp`
- `0x18004f537`: `onecore\windows\accessibletech\uiautomationcore\localuianodeproxy.cpp`
- `0x18004fb42`: `onecore\windows\accessibletech\uiautomationcore\localuianodeproxy.cpp`
- `0x18004fe0d`: `onecore\windows\accessibletech\uiautomationcore\localuianodeproxy.cpp`
- `0x18004fe89`: `onecore\windows\accessibletech\uiautomationcore\localuianodeproxy.cpp`
- `0x18004ff18`: `onecore\windows\accessibletech\uiautomationcore\localuianodeproxy.cpp`
- `0x180050218`: `onecore\windows\accessibletech\uiautomationcore\localuianodeproxy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall LocalUiaNodeProxy::RealRemoteNodeFromProviderEntryPoint(
        struct IClientConnection *a1,
        ProviderEntryPoint *a2,
        char a3,
        char a4,
        int a5,
        int a6,
        int a7,
        int a8,
        _DWORD *a9,
        __int64 a10,
        int a11,
        _QWORD *a12,
        struct IUnknown **a13,
        _OWORD *a14,
        ElementCompletionInfo *a15)
{
  struct UIAutomationCoreProto::StaticMethodRequestMsg *v18; // rax
  struct UIAutomationCoreProto::StaticMethodRequestMsg *v19; // rbx
  _QWORD *v20; // rcx
  __int64 v21; // rbx
  struct UIAutomationCoreProto::ProviderEntryPointMsg *v22; // rax
  _QWORD *v23; // rsi
  _QWORD *v24; // rcx
  int v25; // eax
  __int64 v26; // r9
  _DWORD *v27; // rdx
  _QWORD *v28; // rcx
  _DWORD *v29; // r8
  int v30; // eax
  __int64 v31; // rcx
  _QWORD *v32; // rcx
  __int64 v33; // rdx
  void **v34; // r13
  unsigned int v35; // r12d
  __int64 v36; // r14
  _QWORD *v37; // rcx
  unsigned __int64 v38; // rax
  unsigned int v39; // ecx
  const char *v40; // r9
  _QWORD *v41; // rsi
  size_t v42; // rbx
  __int64 v43; // rdx
  void *v44; // rcx
  struct IClientConnection *v45; // r12
  int v46; // eax
  char v47; // al
  _QWORD *v48; // rax
  UIAutomationCoreProto::GetNodeFromProviderEntryPointResponseMsg *v49; // r14
  void *v50; // rsi
  __int64 v51; // rbx
  __int64 ElementCompletionInfo; // rsi
  const unsigned __int16 *v53; // rcx
  unsigned int v54; // edx
  unsigned int v55; // edx
  char v56; // cl
  char v57; // al
  unsigned int v58; // edx
  char *v59; // rbx
  SAFEARRAY **v60; // r14
  __int64 v61; // rsi
  __int64 v62; // rdx
  SAFEARRAY *v63; // rsi
  __int64 perf_frequency; // r14
  __int64 perf_counter; // rax
  unsigned int v66; // edx
  int v67; // ebx
  struct IUnknown **v68; // rbx
  _OWORD *v69; // rax
  unsigned int v70; // edx
  char v71; // dl
  __int64 v72; // rcx
  unsigned __int64 v73; // r8
  const char *v74; // r9
  __int64 result; // rax
  __int64 v76; // rdx
  const struct UIAutomationCoreProto::CrossMachineConnectionInfoMsg *v77; // rdx
  int v78; // eax
  google::protobuf::Arena *v79; // rcx
  void *v80; // r12
  __int64 v81; // r8
  __int64 v82; // rdx
  int v83; // [rsp+20h] [rbp-338h]
  int v84[2]; // [rsp+20h] [rbp-338h]
  void *v85; // [rsp+28h] [rbp-330h] BYREF
  struct IClientConnection *v86; // [rsp+30h] [rbp-328h]
  unsigned __int64 v87; // [rsp+38h] [rbp-320h] BYREF
  SAFEARRAY *v88; // [rsp+40h] [rbp-318h] BYREF
  _QWORD *v89; // [rsp+48h] [rbp-310h]
  struct IUnknown **v90; // [rsp+50h] [rbp-308h]
  _OWORD *v91; // [rsp+58h] [rbp-300h]
  _OWORD v92[2]; // [rsp+60h] [rbp-2F8h] BYREF
  void *Block[4]; // [rsp+80h] [rbp-2D8h] BYREF
  void **v94; // [rsp+A0h] [rbp-2B8h] BYREF
  __int64 v95; // [rsp+A8h] [rbp-2B0h] BYREF
  int v96; // [rsp+B0h] [rbp-2A8h]
  _DWORD *v97; // [rsp+B8h] [rbp-2A0h]
  __int64 v98; // [rsp+C0h] [rbp-298h]
  __int64 v99; // [rsp+D0h] [rbp-288h] BYREF
  __m256i v100; // [rsp+D8h] [rbp-280h] BYREF
  BSTR v101; // [rsp+F8h] [rbp-260h] BYREF
  _BYTE v102[40]; // [rsp+100h] [rbp-258h] BYREF
  char v103; // [rsp+128h] [rbp-230h]
  SAFEARRAY *v104; // [rsp+130h] [rbp-228h] BYREF
  char v105; // [rsp+138h] [rbp-220h]
  int v106; // [rsp+140h] [rbp-218h] BYREF
  __int64 v107; // [rsp+148h] [rbp-210h] BYREF
  __int8 v108; // [rsp+150h] [rbp-208h]
  GUID v109; // [rsp+154h] [rbp-204h]
  BSTR bstrString; // [rsp+168h] [rbp-1F0h] BYREF
  _BYTE v111[40]; // [rsp+170h] [rbp-1E8h] BYREF
  char v112; // [rsp+198h] [rbp-1C0h]
  SAFEARRAY *psa; // [rsp+1A0h] [rbp-1B8h]
  char v114; // [rsp+1A8h] [rbp-1B0h]
  struct IUnknown *v115; // [rsp+1B0h] [rbp-1A8h] BYREF
  __int8 v116; // [rsp+1B8h] [rbp-1A0h]
  GUID v117; // [rsp+1BCh] [rbp-19Ch]
  BSTR v118; // [rsp+1D0h] [rbp-188h] BYREF
  _BYTE v119[40]; // [rsp+1D8h] [rbp-180h] BYREF
  char v120; // [rsp+200h] [rbp-158h]
  _QWORD v121[6]; // [rsp+210h] [rbp-148h] BYREF
  int v122; // [rsp+240h] [rbp-118h] BYREF
  struct IUnknown *v123; // [rsp+248h] [rbp-110h] BYREF
  __int8 v124; // [rsp+250h] [rbp-108h]
  GUID v125; // [rsp+254h] [rbp-104h]
  BSTR v126; // [rsp+268h] [rbp-F0h] BYREF
  _BYTE v127[40]; // [rsp+270h] [rbp-E8h] BYREF
  char v128; // [rsp+298h] [rbp-C0h]
  SAFEARRAY *v129; // [rsp+2A0h] [rbp-B8h] BYREF
  _BYTE v130[104]; // [rsp+2A8h] [rbp-B0h] BYREF
  char v131; // [rsp+310h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+0h]

  try
  {
    v86 = a1;
    v90 = a13;
    v89 = a12;
    v91 = a14;
    *a12 = 0;
    v114 = 0;
    if ( a15 && *((_BYTE *)a15 + 104) )
    {
      ElementCompletionInfo::~ElementCompletionInfo(a15);
      *((_BYTE *)a15 + 104) = 0;
    }
    std::_Optional_destruct_base<ElementCompletionInfo,0>::~_Optional_destruct_base<ElementCompletionInfo,0>(&v106);
    v121[1] = 0;
    v121[4] = 0;
    v121[2] = 0;
    v121[0] = &UIAutomationCoreProto::UiaCoreRequestMsg::`vftable';
    v18 = UIAutomationCoreProto::UiaCoreRequestMsg::_internal_mutable_static_method_request((UIAutomationCoreProto::UiaCoreRequestMsg *)v121);
    v19 = v18;
    if ( *((_DWORD *)v18 + 9) != 11 )
    {
      UIAutomationCoreProto::StaticMethodRequestMsg::clear_request_payload(v18);
      *((_DWORD *)v19 + 9) = 11;
      v20 = (_QWORD *)(*((_QWORD *)v19 + 1) & 0xFFFFFFFFFFFFFFFCuLL);
      if ( (*((_BYTE *)v19 + 8) & 1) != 0 )
        v20 = (_QWORD *)*v20;
      *((_QWORD *)v19 + 3) = google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::GetNodeFromProviderEntryPointRequestMsg,>(v20);
    }
    v21 = *((_QWORD *)v19 + 3);
    v22 = *(struct UIAutomationCoreProto::ProviderEntryPointMsg **)(v21 + 16);
    v23 = (_QWORD *)(v21 + 8);
    if ( !v22 )
    {
      v24 = (_QWORD *)(*v23 & 0xFFFFFFFFFFFFFFFCuLL);
      if ( (*(_BYTE *)v23 & 1) != 0 )
        v24 = (_QWORD *)*v24;
      v22 = (struct UIAutomationCoreProto::ProviderEntryPointMsg *)google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::ProviderEntryPointMsg,>(v24);
      *(_QWORD *)(v21 + 16) = v22;
    }
    v25 = ProviderEntryPoint::WriteToMessage(a2, v22);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x553,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\localuianodeproxy.cpp",
        (const char *)(unsigned int)v25,
        v83);
    *(_BYTE *)(v21 + 56) = a3;
    *(_BYTE *)(v21 + 57) = a4;
    *(_DWORD *)(v21 + 48) = a5;
    *(_DWORD *)(v21 + 52) = a6;
    *(_DWORD *)(v21 + 60) = a7;
    *(_DWORD *)(v21 + 64) = a8;
    v27 = *(_DWORD **)(v21 + 24);
    if ( !v27 )
    {
      v28 = (_QWORD *)(*v23 & 0xFFFFFFFFFFFFFFFCuLL);
      if ( (*(_BYTE *)v23 & 1) != 0 )
        v28 = (_QWORD *)*v28;
      v27 = (_DWORD *)google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::InProcProxyRequestMsg,>(v28);
      *(_QWORD *)(v21 + 24) = v27;
    }
    v29 = a9;
    if ( *a9 )
    {
      switch ( *a9 )
      {
        case 1:
          v30 = 1;
          break;
        case 2:
          v30 = 2;
          break;
        case 3:
          v30 = 3;
          break;
        case 4:
          v30 = 4;
          break;
        case 5:
          v30 = 5;
          break;
        case 6:
          v30 = 6;
          break;
        default:
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x5C5,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\protobufhelper.cpp",
            (const char *)0x8000FFFFLL,
            v83);
      }
    }
    else
    {
      v30 = 0;
    }
    v27[4] = v30;
    v27[5] = a9[1];
    v27[6] = a9[2];
    v27[7] = a9[3];
    v31 = *(_QWORD *)(v21 + 32);
    if ( !v31 )
    {
      v32 = (_QWORD *)(*v23 & 0xFFFFFFFFFFFFFFFCuLL);
      if ( (*(_BYTE *)v23 & 1) != 0 )
        v32 = (_QWORD *)*v32;
      v31 = google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::TimeoutDataMsg,>(v32);
      *(_QWORD *)(v21 + 32) = v31;
    }
    *(_BYTE *)(v31 + 16) = a10;
    *(_DWORD *)(v31 + 20) = HIDWORD(a10);
    *(_BYTE *)(v21 + 58) = a11 != 0;
    v33 = 88;
    if ( dword_1803A33E8 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 88LL) )
    {
      Init_thread_header(&dword_1803A33E8);
      if ( dword_1803A33E8 == -1 )
      {
        LocalUiaNodeProxy::GetClientInfo(&dword_1803A33F0);
        atexit(LocalUiaNodeProxy::RealRemoteNodeFromProviderEntryPoint_::_3_::_dynamic_atexit_destructor_for__clientInfo__);
        Init_thread_footer(&dword_1803A33E8);
      }
    }
    *(_DWORD *)(v21 + 68) = dword_1803A33F0;
    v34 = &Src;
    if ( (unsigned __int64)qword_1803A3410 > 7 )
      v34 = (void **)Src;
    v35 = qword_1803A3408;
    v36 = *(_QWORD *)(v21 + 40);
    if ( !v36 )
    {
      v37 = (_QWORD *)(*v23 & 0xFFFFFFFFFFFFFFFCuLL);
      if ( (*(_BYTE *)v23 & 1) != 0 )
        v37 = (_QWORD *)*v37;
      v36 = google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::WstringMsg,>(v37, v33, v29, v26);
      *(_QWORD *)(v21 + 40) = v36;
    }
    v38 = 2LL * v35;
    v39 = 2 * v35;
    if ( v38 > 0xFFFFFFFF )
      v39 = -1;
    v40 = v38 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0LL;
    if ( v38 > 0xFFFFFFFF )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2E,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\protobufhelper.cpp",
        v40,
        v83);
    v41 = (_QWORD *)(*(_QWORD *)(v36 + 8) & 0xFFFFFFFFFFFFFFFCuLL);
    if ( (*(_BYTE *)(v36 + 8) & 1) != 0 )
      v41 = (_QWORD *)*v41;
    memset(Block, 0, sizeof(Block));
    v42 = v39;
    if ( v39 > 0xF )
    {
      v85 = (void *)std::string::_Calculate_growth(v39, 15, 0x7FFFFFFFFFFFFFFFLL, v40);
      v80 = (void *)std::allocator<char>::allocate(Block, (char *)v85 + 1);
      Block[0] = v80;
      Block[2] = (void *)v42;
      Block[3] = v85;
      memcpy_0(v80, v34, v42);
      *((_BYTE *)v80 + v42) = 0;
    }
    else
    {
      *(_OWORD *)&Block[2] = v39;
      memcpy_0(Block, v34, v39);
      *((_BYTE *)Block + v42) = 0;
    }
    LOBYTE(v43) = 0;
    google::protobuf::internal::ArenaStringPtr::Set(v36 + 16, v43, Block, v41);
    if ( Block[3] > (void *)0xF )
    {
      v87 = (unsigned __int64)Block[3] + 1;
      v44 = Block[0];
      v85 = Block[0];
      if ( (unsigned __int64)Block[3] + 1 >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(&v85, &v87);
        v44 = v85;
      }
      operator delete(v44);
    }
    v95 = 0;
    v98 = 0;
    v96 = 0;
    v94 = &UIAutomationCoreProto::UiaCoreResponseMsg::`vftable';
    v45 = v86;
    v46 = DoCallWithReturn(
            v86,
            (struct UIAutomationCoreProto::UiaCoreRequestMsg *)v121,
            (struct UIAutomationCoreProto::UiaCoreResponseMsg *)&v94,
            1);
    if ( v46 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x56A,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\localuianodeproxy.cpp",
        (const char *)(unsigned int)v46,
        v83);
    if ( HIDWORD(v98) != 11 || (v47 = 0, v97[7] != 1) )
      v47 = 1;
    if ( v47 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x56D,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\localuianodeproxy.cpp",
        (const char *)0x80040801LL,
        v83);
    v48 = &UIAutomationCoreProto::_StaticMethodResponseMsg_default_instance_;
    if ( HIDWORD(v98) == 11 )
      v48 = v97;
    if ( *((_DWORD *)v48 + 7) == 1 )
      v49 = (UIAutomationCoreProto::GetNodeFromProviderEntryPointResponseMsg *)v48[2];
    else
      v49 = (UIAutomationCoreProto::GetNodeFromProviderEntryPointResponseMsg *)&UIAutomationCoreProto::_GetNodeFromProviderEntryPointResponseMsg_default_instance_;
    v50 = &UIAutomationCoreProto::_ElementRefRetMsg_default_instance_;
    if ( *((_QWORD *)v49 + 2) )
      v50 = (void *)*((_QWORD *)v49 + 2);
    v51 = ProtobufHelper::GetElementBase<UIAutomationCoreProto::ElementRefRetMsg>(&v106, v50, v45);
    ElementCompletionInfo = ProtobufHelper::GetElementCompletionInfo(&v99, v50, v45);
    v122 = *(_DWORD *)v51;
    v123 = *(struct IUnknown **)(v51 + 8);
    if ( v123 )
      ((void (__fastcall *)(struct IUnknown *))v123->lpVtbl->AddRef)(v123);
    v124 = *(_BYTE *)(v51 + 16);
    v125 = *(GUID *)(v51 + 20);
    v126 = 0;
    v128 = 0;
    if ( *(_BYTE *)(v51 + 88) )
      std::_Optional_construct_base<CrossMachinePlaceholderInfo>::_Construct<CrossMachinePlaceholderInfo const &>(
        v127,
        v51 + 48);
    v53 = *(const unsigned __int16 **)(v51 + 40);
    if ( v53 && (int)HrSysAllocString(v53, &v126) < 0 )
      v125 = GUID_NULL;
    v129 = 0;
    ElementRefRet::StoreRuntimeIdCopy(&v122, v51 + 96);
    v131 = 0;
    if ( *(_BYTE *)(ElementCompletionInfo + 104) )
    {
      ElementCompletionInfo::ElementCompletionInfo(v130, ElementCompletionInfo);
      v131 = 1;
    }
    if ( v105 )
      ElementCompletionInfo::~ElementCompletionInfo((ElementCompletionInfo *)&v99);
    if ( psa )
      SafeArrayDestroy(psa);
    if ( v112 )
      CrossMachinePlaceholderInfo::`scalar deleting destructor'((CrossMachinePlaceholderInfo *)v111, v54);
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v107);
    v114 = 0;
    v56 = 0;
    if ( v131 )
    {
      ElementCompletionInfo::ElementCompletionInfo(&v106, v130);
      v114 = 1;
      v56 = 1;
    }
    if ( a15 )
    {
      v57 = *((_BYTE *)a15 + 104);
      if ( v56 )
      {
        if ( v57 )
        {
          ElementCompletionInfo::operator=(a15, &v106);
        }
        else
        {
          ElementCompletionInfo::ElementCompletionInfo(a15, (const struct ElementCompletionInfo *)&v106);
          *((_BYTE *)a15 + 104) = 1;
        }
      }
      else if ( v57 )
      {
        ElementCompletionInfo::`scalar deleting destructor'(a15, v55);
        *((_BYTE *)a15 + 104) = 0;
      }
    }
    std::_Optional_destruct_base<ElementCompletionInfo,0>::~_Optional_destruct_base<ElementCompletionInfo,0>(&v106);
    *(_QWORD *)v84 = 0;
    v115 = v123;
    if ( v123 )
      ((void (__fastcall *)(struct IUnknown *))v123->lpVtbl->AddRef)(v123);
    v116 = v124;
    v117 = v125;
    v118 = 0;
    v120 = 0;
    if ( v128 )
      std::_Optional_construct_base<CrossMachinePlaceholderInfo>::_Construct<CrossMachinePlaceholderInfo const &>(
        v119,
        v127);
    if ( v126 && (int)HrSysAllocString(v126, &v118) < 0 )
      v117 = GUID_NULL;
    memset(v92, 0, sizeof(v92));
    Block[0] = 0;
    LODWORD(Block[1]) = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
    *(_OWORD *)((char *)&Block[1] + 4) = *(_OWORD *)((char *)v92 + 12);
    if ( (v116 & 0x20) != 0 )
    {
      if ( !UIAutomationCoreProto::GetNodeFromProviderEntryPointResponseMsg::_internal_has_cross_machine_connection_info(v49) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x584,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\localuianodeproxy.cpp",
          (const char *)0x8000FFFFLL,
          0);
      v77 = (const struct UIAutomationCoreProto::CrossMachineConnectionInfoMsg *)&UIAutomationCoreProto::_CrossMachineConnectionInfoMsg_default_instance_;
      if ( *((_QWORD *)v49 + 3) )
        v77 = (const struct UIAutomationCoreProto::CrossMachineConnectionInfoMsg *)*((_QWORD *)v49 + 3);
      v78 = CrossMachineConnectionInfo::ReadFromMessage((CrossMachineConnectionInfo *)Block, v77);
      if ( v78 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x586,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\localuianodeproxy.cpp",
          (const char *)(unsigned int)v78,
          0);
      v99 = 0;
      v100.m256i_i8[0] &= 0xC0u;
      *(GUID *)((char *)v100.m256i_i64 + 4) = GUID_NULL;
      v100.m256i_i64[3] = 0;
      v102[32] = 0;
      ElementExtraInfo::operator=(&v115, &v99);
      ElementExtraInfo::~ElementExtraInfo((ElementExtraInfo *)&v99);
      goto LABEL_132;
    }
    LODWORD(v99) = v122;
    v100.m256i_i64[0] = (__int64)v123;
    if ( v123 )
      ((void (__fastcall *)(struct IUnknown *))v123->lpVtbl->AddRef)(v123);
    v100.m256i_i8[8] = v124;
    *(GUID *)((char *)&v100.m256i_u64[1] + 4) = v125;
    v101 = 0;
    v103 = 0;
    if ( v128 )
      std::_Optional_construct_base<CrossMachinePlaceholderInfo>::_Construct<CrossMachinePlaceholderInfo const &>(
        v102,
        v127);
    if ( v126 && (int)HrSysAllocString(v126, &v101) < 0 )
      *(GUID *)((char *)&v100.m256i_u64[1] + 4) = GUID_NULL;
    v104 = 0;
    ElementRefRet::StoreRuntimeIdCopy(&v99, &v129);
    *(_QWORD *)v84 = 0;
    if ( !(_DWORD)v99 )
      goto LABEL_117;
    if ( v45 )
    {
      v59 = (char *)operator new(0x50u, (const struct std::nothrow_t *)std::nothrow);
      if ( v59 )
      {
        v106 = v99;
        v107 = v100.m256i_i64[0];
        if ( v100.m256i_i64[0] )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v100.m256i_i64[0] + 8LL))(v100.m256i_i64[0]);
        v108 = v100.m256i_i8[8];
        v109 = *(GUID *)((char *)&v100.m256i_u64[1] + 4);
        bstrString = 0;
        v112 = 0;
        if ( v103 )
          std::_Optional_construct_base<CrossMachinePlaceholderInfo>::_Construct<CrossMachinePlaceholderInfo const &>(
            v111,
            v102);
        if ( v101 && (int)HrSysAllocString(v101, &bstrString) < 0 )
          v109 = GUID_NULL;
        psa = 0;
        ElementRefRet::StoreRuntimeIdCopy(&v106, &v104);
        *(_QWORD *)v59 = &IUiaNode::`vftable';
        *((_DWORD *)v59 + 2) = 826362197;
        *((_QWORD *)v59 + 2) = &RefcountBase::`vftable';
        *((_DWORD *)v59 + 6) = 1;
        _InterlockedAdd(&dword_18039DE7C, 1u);
        *(_QWORD *)v59 = &LocalUiaNodeProxy::`vftable'{for `IUiaNode'};
        *((_QWORD *)v59 + 2) = &LocalUiaNodeProxy::`vftable'{for `RefcountBase'};
        *((_DWORD *)v59 + 8) = 0;
        *((_QWORD *)v59 + 5) = 0;
        v60 = (SAFEARRAY **)(v59 + 48);
        *((_QWORD *)v59 + 6) = 0;
        *((_QWORD *)v59 + 7) = 0;
        *((_QWORD *)v59 + 8) = 0;
        v59[72] = 0;
        *((_DWORD *)v59 + 8) = v106;
        v61 = *((_QWORD *)v59 + 5);
        *((_QWORD *)v59 + 5) = v45;
        (*(void (__fastcall **)(struct IClientConnection *))(*(_QWORD *)v45 + 8LL))(v45);
        if ( v61 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
        ElementRefRet::TryGetRuntimeIdCopy(&v106, &v88);
        v63 = v88;
        if ( v88 )
        {
          AcquireSRWLockExclusive((PSRWLOCK)v59 + 8);
          if ( v60 != &v88 )
          {
            if ( *v60 )
              wil::details::close_invoke_helper<1,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),tagSAFEARRAY *>::close_reset(*v60);
            *v60 = v63;
            v63 = 0;
          }
          perf_frequency = _Query_perf_frequency();
          perf_counter = _Query_perf_counter();
          if ( perf_frequency == 10000000 )
          {
            v62 = 100 * perf_counter;
          }
          else
          {
            if ( perf_frequency == 24000000 )
            {
              v81 = perf_counter / 24000000;
              v82 = 1000000000 * (perf_counter % 24000000) / 24000000;
            }
            else
            {
              v81 = perf_counter / perf_frequency;
              v82 = 1000000000 * (perf_counter % perf_frequency) / perf_frequency;
            }
            v62 = 1000000000 * v81 + v82;
          }
          *((_QWORD *)v59 + 7) = v62;
          if ( v59 != (char *)-64LL )
            ReleaseSRWLockExclusive((PSRWLOCK)v59 + 8);
          if ( v63 )
            SafeArrayDestroy(v63);
        }
        if ( psa )
          SafeArrayDestroy(psa);
        if ( v112 )
          CrossMachinePlaceholderInfo::`scalar deleting destructor'((CrossMachinePlaceholderInfo *)v111, v62);
        if ( bstrString )
        {
          SysFreeString(bstrString);
          bstrString = 0;
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v107);
        *(_QWORD *)v84 = v59;
LABEL_117:
        if ( v104 )
          SafeArrayDestroy(v104);
        if ( v103 )
          CrossMachinePlaceholderInfo::`scalar deleting destructor'((CrossMachinePlaceholderInfo *)v102, v58);
        if ( v101 )
        {
          SysFreeString(v101);
          v101 = 0;
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v100);
        v67 = 0;
        goto LABEL_124;
      }
      v67 = -2147024882;
      v76 = 50;
    }
    else
    {
      v67 = -2147418113;
      v76 = 48;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v76,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\localuianodeproxy.cpp",
      (const char *)(unsigned int)v67,
      0);
    ElementRefRet::~ElementRefRet((ElementRefRet *)&v99);
LABEL_124:
    if ( v67 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x57C,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\localuianodeproxy.cpp",
        (const char *)(unsigned int)v67,
        v84[0]);
LABEL_132:
    *v89 = *(_QWORD *)v84;
    v68 = v90;
    if ( v90 )
    {
      v66 = (unsigned int)v115;
      if ( *v90 != v115 )
        ATL::AtlComPtrAssign(v90, v115);
      *((_BYTE *)v68 + 8) = v116;
      *(GUID *)((char *)v68 + 12) = v117;
      if ( v118 && (int)HrSysAllocString(v118, (unsigned __int16 **)v68 + 4) < 0 )
        *(GUID *)((char *)v68 + 12) = GUID_NULL;
      if ( v120 )
      {
        std::_Optional_construct_base<CrossMachinePlaceholderInfo>::_Assign<CrossMachinePlaceholderInfo const &>(
          v68 + 5,
          v119);
      }
      else if ( *((_BYTE *)v68 + 80) )
      {
        CrossMachinePlaceholderInfo::`scalar deleting destructor'((CrossMachinePlaceholderInfo *)(v68 + 5), v66);
        *((_BYTE *)v68 + 80) = 0;
      }
    }
    v69 = v91;
    if ( v91 )
    {
      *v91 = *(_OWORD *)Block;
      v69[1] = *(_OWORD *)&Block[2];
    }
    if ( v120 )
      CrossMachinePlaceholderInfo::`scalar deleting destructor'((CrossMachinePlaceholderInfo *)v119, v66);
    if ( v118 )
    {
      SysFreeString(v118);
      v118 = 0;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v115);
    std::_Optional_destruct_base<ElementCompletionInfo,0>::~_Optional_destruct_base<ElementCompletionInfo,0>(v130);
    if ( v129 )
      SafeArrayDestroy(v129);
    if ( v128 )
      CrossMachinePlaceholderInfo::`scalar deleting destructor'((CrossMachinePlaceholderInfo *)v127, v70);
    if ( v126 )
    {
      SysFreeString(v126);
      v126 = 0;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v123);
    v94 = &UIAutomationCoreProto::UiaCoreResponseMsg::`vftable';
    v71 = v95;
    v72 = v95;
    if ( (v95 & 1) != 0 )
      v73 = *(_QWORD *)(v95 & 0xFFFFFFFFFFFFFFFCuLL);
    else
      v73 = v95 & 0xFFFFFFFFFFFFFFFCuLL;
    if ( !v73 )
    {
      if ( HIDWORD(v98) )
      {
        UIAutomationCoreProto::UiaCoreResponseMsg::clear_payload((UIAutomationCoreProto::UiaCoreResponseMsg *)&v94);
        v72 = v95;
        v71 = v95;
      }
      if ( (v71 & 1) != 0 )
      {
        google::protobuf::internal::InternalMetadata::DeleteOutOfLineHelper<std::string>(&v95);
        v72 = v95;
        v71 = v95;
      }
    }
    if ( (v72 & 2) != 0 )
    {
      v79 = (google::protobuf::Arena *)(v72 & 0xFFFFFFFFFFFFFFFCuLL);
      if ( (v71 & 1) != 0 )
        v79 = *(google::protobuf::Arena **)v79;
      if ( v79 )
        google::protobuf::Arena::`scalar deleting destructor'(v79, 1u);
    }
    UIAutomationCoreProto::UiaCoreRequestMsg::~UiaCoreRequestMsg((UIAutomationCoreProto::UiaCoreRequestMsg *)v121);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x5A0,
                           (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\localuianodeproxy.cpp",
                           v74);
  }
  return result;
}

```

## disassembly

```asm
0x18004f144  mov     [rsp+arg_10], rbx
0x18004f149  mov     [rsp+arg_18], rsi
0x18004f14e  push    rdi
0x18004f14f  push    r12
0x18004f151  push    r13
0x18004f153  push    r14
0x18004f155  push    r15
0x18004f157  sub     rsp, 330h
0x18004f15e  mov     rax, cs:__security_cookie
0x18004f165  xor     rax, rsp
0x18004f168  mov     [rsp+358h+var_38], rax
0x18004f170  mov     r12b, r9b
0x18004f173  mov     r13b, r8b
0x18004f176  mov     r14, rdx
0x18004f179  mov     [rsp+358h+var_328], rcx
0x18004f17e  mov     rax, [rsp+358h+arg_60]
0x18004f186  mov     [rsp+358h+var_308], rax
0x18004f18b  mov     rcx, [rsp+358h+arg_58]
0x18004f193  mov     [rsp+358h+var_310], rcx
0x18004f198  mov     rax, [rsp+358h+arg_68]
0x18004f1a0  mov     [rsp+358h+var_300], rax
0x18004f1a5  mov     r15, [rsp+358h+arg_70]
0x18004f1ad  xor     ebx, ebx
0x18004f1af  mov     [rcx], rbx
0x18004f1b2  mov     [rsp+358h+var_1B0], bl
0x18004f1b9  test    r15, r15
0x18004f1bc  jz      short loc_18004F1C8
0x18004f1be  cmp     [r15+68h], bl
0x18004f1c2  jnz     loc_18004FDDB
0x18004f1c8  lea     rcx, [rsp+358h+var_218]
0x18004f1d0  call    ??1?$_Optional_destruct_base@UElementCompletionInfo@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<ElementCompletionInfo,0>::~_Optional_destruct_base<ElementCompletionInfo,0>(void)
0x18004f1d5  mov     [rsp+358h+var_140], rbx
0x18004f1dd  mov     [rsp+358h+var_128], rbx
0x18004f1e5  xor     eax, eax
0x18004f1e7  mov     [rsp+358h+var_138], rax
0x18004f1ef  lea     rax, ??_7UiaCoreRequestMsg@UIAutomationCoreProto@@6B@; const UIAutomationCoreProto::UiaCoreRequestMsg::`vftable'
0x18004f1f6  mov     [rsp+358h+var_148], rax
0x18004f1fe  lea     rcx, [rsp+358h+var_148]; this
0x18004f206  call    ?_internal_mutable_static_method_request@UiaCoreRequestMsg@UIAutomationCoreProto@@AEAAPEAVStaticMethodRequestMsg@2@XZ; UIAutomationCoreProto::UiaCoreRequestMsg::_internal_mutable_static_method_request(void)
0x18004f20b  mov     rbx, rax
0x18004f20e  cmp     dword ptr [rax+24h], 0Bh
0x18004f212  jz      loc_18004FED4
0x18004f218  mov     rcx, rax; this
0x18004f21b  call    ?clear_request_payload@StaticMethodRequestMsg@UIAutomationCoreProto@@QEAAXXZ; UIAutomationCoreProto::StaticMethodRequestMsg::clear_request_payload(void)
0x18004f220  mov     dword ptr [rbx+24h], 0Bh
0x18004f227  mov     rcx, [rbx+8]
0x18004f22b  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18004f22f  mov     edi, 1
0x18004f234  test    [rbx+8], dil
0x18004f238  jnz     loc_18004FE5B
0x18004f23e  call    ??$CreateMaybeMessage@VGetNodeFromProviderEntryPointRequestMsg@UIAutomationCoreProto@@$$V@Arena@protobuf@google@@CAPEAVGetNodeFromProviderEntryPointRequestMsg@UIAutomationCoreProto@@PEAV012@@Z; google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::GetNodeFromProviderEntryPointRequestMsg,>(google::protobuf::Arena *)
0x18004f243  mov     [rbx+18h], rax
0x18004f247  mov     rbx, [rbx+18h]
0x18004f24b  mov     rax, [rbx+10h]
0x18004f24f  lea     rsi, [rbx+8]
0x18004f253  test    rax, rax
0x18004f256  jnz     short loc_18004F271
0x18004f258  mov     rcx, [rsi]
0x18004f25b  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18004f25f  test    [rsi], dil
0x18004f262  jnz     loc_18004FE2C
0x18004f268  call    ??$CreateMaybeMessage@VProviderEntryPointMsg@UIAutomationCoreProto@@$$V@Arena@protobuf@google@@CAPEAVProviderEntryPointMsg@UIAutomationCoreProto@@PEAV012@@Z; google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::ProviderEntryPointMsg,>(google::protobuf::Arena *)
0x18004f26d  mov     [rbx+10h], rax
0x18004f271  mov     rdx, rax; struct UIAutomationCoreProto::ProviderEntryPointMsg *
0x18004f274  mov     rcx, r14; this
0x18004f277  call    ?WriteToMessage@ProviderEntryPoint@@QEBAJPEAVProviderEntryPointMsg@UIAutomationCoreProto@@@Z; ProviderEntryPoint::WriteToMessage(UIAutomationCoreProto::ProviderEntryPointMsg *)
0x18004f27c  mov     rcx, [rsp+358h]; this
0x18004f284  test    eax, eax
0x18004f286  jns     short loc_18004F29C
0x18004f288  mov     r9d, eax; char *
0x18004f28b  lea     r8, aOnecoreWindows_78; "onecore\\windows\\accessibletech\\uiaut"...
0x18004f292  mov     edx, 553h; void *
0x18004f297  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f29c  mov     [rbx+38h], r13b
0x18004f2a0  mov     [rbx+39h], r12b
0x18004f2a4  mov     eax, [rsp+358h+arg_20]
0x18004f2ab  mov     [rbx+30h], eax
0x18004f2ae  mov     eax, [rsp+358h+arg_28]
0x18004f2b5  mov     [rbx+34h], eax
0x18004f2b8  mov     eax, [rsp+358h+arg_30]
0x18004f2bf  mov     [rbx+3Ch], eax
0x18004f2c2  mov     eax, [rsp+358h+arg_38]
0x18004f2c9  mov     [rbx+40h], eax
0x18004f2cc  mov     rdx, [rbx+18h]
0x18004f2d0  test    rdx, rdx
0x18004f2d3  jnz     short loc_18004F2F1
0x18004f2d5  mov     rcx, [rsi]
0x18004f2d8  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18004f2dc  test    [rsi], dil
0x18004f2df  jnz     loc_18004FE63
0x18004f2e5  call    ??$CreateMaybeMessage@VInProcProxyRequestMsg@UIAutomationCoreProto@@$$V@Arena@protobuf@google@@CAPEAVInProcProxyRequestMsg@UIAutomationCoreProto@@PEAV012@@Z; google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::InProcProxyRequestMsg,>(google::protobuf::Arena *)
0x18004f2ea  mov     rdx, rax
0x18004f2ed  mov     [rbx+18h], rax
0x18004f2f1  mov     r8, [rsp+358h+arg_40]
0x18004f2f9  mov     ecx, [r8]
0x18004f2fc  test    ecx, ecx
0x18004f2fe  jnz     loc_18004F41A
0x18004f304  xor     eax, eax
0x18004f306  mov     [rdx+10h], eax
0x18004f309  mov     eax, [r8+4]
0x18004f30d  mov     [rdx+14h], eax
0x18004f310  mov     eax, [r8+8]
0x18004f314  mov     [rdx+18h], eax
0x18004f317  mov     eax, [r8+0Ch]
0x18004f31b  mov     [rdx+1Ch], eax
0x18004f31e  mov     rcx, [rbx+20h]
0x18004f322  test    rcx, rcx
0x18004f325  jnz     short loc_18004F343
0x18004f327  mov     rcx, [rsi]
0x18004f32a  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18004f32e  test    [rsi], dil
0x18004f331  jnz     loc_18004FE53
0x18004f337  call    ??$CreateMaybeMessage@VTimeoutDataMsg@UIAutomationCoreProto@@$$V@Arena@protobuf@google@@CAPEAVTimeoutDataMsg@UIAutomationCoreProto@@PEAV012@@Z; google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::TimeoutDataMsg,>(google::protobuf::Arena *)
0x18004f33c  mov     rcx, rax
0x18004f33f  mov     [rbx+20h], rax
0x18004f343  mov     al, [rsp+358h+arg_48]
0x18004f34a  mov     [rcx+10h], al
0x18004f34d  mov     eax, [rsp+358h+arg_4C]
0x18004f354  mov     [rcx+14h], eax
0x18004f357  cmp     [rsp+358h+arg_50], 0
0x18004f35f  setnz   al
0x18004f362  mov     [rbx+3Ah], al
0x18004f365  mov     ecx, cs:_tls_index
0x18004f36b  mov     rax, gs:58h
0x18004f374  mov     edx, 58h ; 'X'
0x18004f379  mov     rax, [rax+rcx*8]
0x18004f37d  mov     ecx, [rdx+rax]
0x18004f380  cmp     cs:dword_1803A33E8, ecx
0x18004f386  jg      loc_18004FF79
0x18004f38c  mov     eax, cs:dword_1803A33F0
0x18004f392  mov     [rbx+44h], eax
0x18004f395  lea     r13, Src
0x18004f39c  cmp     cs:qword_1803A3410, 7
0x18004f3a4  cmova   r13, cs:Src
0x18004f3ac  mov     r12, cs:qword_1803A3408
0x18004f3b3  mov     r14, [rbx+28h]
0x18004f3b7  test    r14, r14
0x18004f3ba  jnz     short loc_18004F3D8
0x18004f3bc  mov     rcx, [rsi]
0x18004f3bf  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18004f3c3  test    [rsi], dil
0x18004f3c6  jnz     loc_18004FE34
0x18004f3cc  call    ??$CreateMaybeMessage@VWstringMsg@UIAutomationCoreProto@@$$V@Arena@protobuf@google@@CAPEAVWstringMsg@UIAutomationCoreProto@@PEAV012@@Z; google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::WstringMsg,>(google::protobuf::Arena *)
0x18004f3d1  mov     r14, rax
0x18004f3d4  mov     [rbx+28h], rax
0x18004f3d8  mov     eax, r12d
0x18004f3db  add     rax, rax
0x18004f3de  mov     edx, 0FFFFFFFFh
0x18004f3e3  cmp     rax, rdx
0x18004f3e6  mov     ecx, eax
0x18004f3e8  jbe     short loc_18004F3EC
0x18004f3ea  mov     ecx, edx
0x18004f3ec  cmp     rdx, rax
0x18004f3ef  sbb     r9d, r9d
0x18004f3f2  and     r9d, 80070216h; char *
0x18004f3f9  mov     r10, [rsp+358h]
0x18004f401  cmp     rax, rdx
0x18004f404  jbe     short loc_18004F42A
0x18004f406  lea     r8, aOnecoreWindows_122; "onecore\\windows\\accessibletech\\uiaut"...
0x18004f40d  mov     edx, 2Eh ; '.'; void *
0x18004f412  mov     rcx, r10; this
0x18004f415  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f41a  sub     ecx, 1
0x18004f41d  jnz     loc_18004FDEC
0x18004f423  mov     eax, edi
0x18004f425  jmp     loc_18004F306
0x18004f42a  mov     rsi, [r14+8]
0x18004f42e  and     rsi, 0FFFFFFFFFFFFFFFCh
0x18004f432  test    [r14+8], dil
0x18004f436  jnz     loc_18004FE3C
0x18004f43c  xorps   xmm0, xmm0
0x18004f43f  movups  xmmword ptr [rsp+358h+Block], xmm0
0x18004f447  xorps   xmm1, xmm1
0x18004f44a  movdqu  [rsp+358h+var_2C8], xmm1
0x18004f453  mov     ebx, ecx
0x18004f455  cmp     ecx, 0Fh
0x18004f458  ja      loc_18004FFBC
0x18004f45e  mov     qword ptr [rsp+358h+var_2C8], rbx
0x18004f466  mov     qword ptr [rsp+358h+var_2C8+8], 0Fh
0x18004f472  mov     r8d, ebx; Size
0x18004f475  mov     rdx, r13; Src
0x18004f478  lea     rcx, [rsp+358h+Block]; void *
0x18004f480  call    memcpy_0
0x18004f485  xor     r13d, r13d
0x18004f488  mov     byte ptr [rsp+rbx+358h+Block], r13b
0x18004f490  mov     dl, r13b
0x18004f493  lea     rcx, [r14+10h]
0x18004f497  mov     r9, rsi
0x18004f49a  lea     r8, [rsp+358h+Block]
0x18004f4a2  call    ?Set@ArenaStringPtr@internal@protobuf@google@@QEAAXUEmptyDefault@1234@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAVArena@34@@Z; google::protobuf::internal::ArenaStringPtr::Set(google::protobuf::internal::ArenaStringPtr::EmptyDefault,std::string const &,google::protobuf::Arena *)
0x18004f4a7  nop
0x18004f4a8  mov     rdx, qword ptr [rsp+358h+var_2C8+8]
0x18004f4b0  cmp     rdx, 0Fh
0x18004f4b4  jbe     short loc_18004F4DD
0x18004f4b6  inc     rdx
0x18004f4b9  mov     [rsp+358h+var_320], rdx
0x18004f4be  mov     rcx, [rsp+358h+Block]; Block
0x18004f4c6  mov     [rsp+358h+var_330], rcx
0x18004f4cb  cmp     rdx, 1000h
0x18004f4d2  jnb     loc_180050023
0x18004f4d8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004f4dd  mov     [rsp+358h+var_2B0], r13
0x18004f4e5  mov     [rsp+358h+var_298], 0
0x18004f4f1  mov     [rsp+358h+var_2A8], r13d
0x18004f4f9  lea     rax, ??_7UiaCoreResponseMsg@UIAutomationCoreProto@@6B@; const UIAutomationCoreProto::UiaCoreResponseMsg::`vftable'
0x18004f500  mov     [rsp+358h+var_2B8], rax
0x18004f508  mov     r9b, dil; bool
0x18004f50b  lea     r8, [rsp+358h+var_2B8]; struct UIAutomationCoreProto::UiaCoreResponseMsg *
0x18004f513  lea     rdx, [rsp+358h+var_148]; struct UIAutomationCoreProto::UiaCoreRequestMsg *
0x18004f51b  mov     r12, [rsp+358h+var_328]
0x18004f520  mov     rcx, r12; struct IClientConnection *
0x18004f523  call    ?DoCallWithReturn@@YAJPEAVIClientConnection@@AEAVUiaCoreRequestMsg@UIAutomationCoreProto@@AEAVUiaCoreResponseMsg@3@_N@Z; DoCallWithReturn(IClientConnection *,UIAutomationCoreProto::UiaCoreRequestMsg &,UIAutomationCoreProto::UiaCoreResponseMsg &,bool)
0x18004f528  mov     rcx, [rsp+358h]; this
0x18004f530  test    eax, eax
0x18004f532  jns     short loc_18004F548
0x18004f534  mov     r9d, eax; char *
0x18004f537  lea     r8, aOnecoreWindows_78; "onecore\\windows\\accessibletech\\uiaut"...
0x18004f53e  mov     edx, 56Ah; void *
0x18004f543  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f548  mov     rcx, [rsp+358h+var_2A0]
0x18004f550  cmp     dword ptr [rsp+358h+var_298+4], 0Bh
0x18004f558  jz      loc_18004FB68
0x18004f55e  mov     al, dil
0x18004f561  mov     r10, [rsp+358h]
0x18004f569  test    al, al
0x18004f56b  jnz     loc_18004FE07
0x18004f571  lea     rax, ?_StaticMethodResponseMsg_default_instance_@UIAutomationCoreProto@@3UStaticMethodResponseMsgDefaultTypeInternal@1@A; UIAutomationCoreProto::StaticMethodResponseMsgDefaultTypeInternal UIAutomationCoreProto::_StaticMethodResponseMsg_default_instance_
0x18004f578  cmp     dword ptr [rsp+358h+var_298+4], 0Bh
0x18004f580  cmovz   rax, rcx
0x18004f584  cmp     [rax+1Ch], edi
0x18004f587  jnz     loc_18004FB54
0x18004f58d  mov     r14, [rax+10h]
0x18004f591  lea     rsi, ?_ElementRefRetMsg_default_instance_@UIAutomationCoreProto@@3UElementRefRetMsgDefaultTypeInternal@1@A; UIAutomationCoreProto::ElementRefRetMsgDefaultTypeInternal UIAutomationCoreProto::_ElementRefRetMsg_default_instance_
0x18004f598  cmp     [r14+10h], r13
0x18004f59c  cmovnz  rsi, [r14+10h]
0x18004f5a1  mov     r8, r12
0x18004f5a4  mov     rdx, rsi
0x18004f5a7  lea     rcx, [rsp+358h+var_218]
0x18004f5af  call    ??$GetElementBase@VElementRefRetMsg@UIAutomationCoreProto@@@ProtobufHelper@@SA?AUElementRefRet@@AEBVElementRefRetMsg@UIAutomationCoreProto@@PEAVIClientConnection@@@Z; ProtobufHelper::GetElementBase<UIAutomationCoreProto::ElementRefRetMsg>(UIAutomationCoreProto::ElementRefRetMsg const &,IClientConnection *)
0x18004f5b4  mov     rbx, rax
0x18004f5b7  mov     r8, r12
0x18004f5ba  mov     rdx, rsi
0x18004f5bd  lea     rcx, [rsp+358h+var_288]
0x18004f5c5  call    ?GetElementCompletionInfo@ProtobufHelper@@SA?AV?$optional@UElementCompletionInfo@@@std@@AEBVElementRefRetMsg@UIAutomationCoreProto@@PEAVIClientConnection@@@Z; ProtobufHelper::GetElementCompletionInfo(UIAutomationCoreProto::ElementRefRetMsg const &,IClientConnection *)
0x18004f5ca  mov     rsi, rax
0x18004f5cd  mov     ecx, [rbx]
0x18004f5cf  mov     [rsp+358h+var_118], ecx
0x18004f5d6  mov     rdx, [rbx+8]
0x18004f5da  mov     [rsp+358h+var_110], rdx
0x18004f5e2  test    rdx, rdx
0x18004f5e5  jz      short loc_18004F5F7
0x18004f5e7  mov     rcx, [rdx]
0x18004f5ea  mov     rax, [rcx+8]
0x18004f5ee  mov     rcx, rdx
0x18004f5f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f5f6  nop
0x18004f5f7  mov     al, [rbx+10h]
0x18004f5fa  mov     [rsp+358h+var_108], al
0x18004f601  movups  xmm0, xmmword ptr [rbx+14h]
0x18004f605  movdqu  [rsp+358h+var_104], xmm0
0x18004f60e  mov     [rsp+358h+var_F0], r13
0x18004f616  lea     rdx, [rbx+30h]
0x18004f61a  mov     [rsp+358h+var_C0], r13b
0x18004f622  cmp     [rdx+28h], r13b
0x18004f626  jnz     loc_180050041
0x18004f62c  mov     rcx, [rbx+28h]; unsigned __int16 *
0x18004f630  test    rcx, rcx
0x18004f633  jnz     loc_180050053
0x18004f639  mov     [rsp+358h+var_B8], r13
0x18004f641  lea     rdx, [rbx+60h]
0x18004f645  lea     rcx, [rsp+358h+var_118]
0x18004f64d  call    ?StoreRuntimeIdCopy@ElementRefRet@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUtagSAFEARRAY@@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; ElementRefRet::StoreRuntimeIdCopy(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t>>> const &)
0x18004f652  mov     [rsp+358h+var_48], r13b
0x18004f65a  cmp     [rsi+68h], r13b
0x18004f65e  jz      short loc_18004F678
0x18004f660  mov     rdx, rsi
0x18004f663  lea     rcx, [rsp+358h+var_B0]
0x18004f66b  call    ??0ElementCompletionInfo@@QEAA@$$QEAU0@@Z; ElementCompletionInfo::ElementCompletionInfo(ElementCompletionInfo &&)
0x18004f670  mov     [rsp+358h+var_48], dil
0x18004f678  cmp     [rsp+358h+var_220], r13b
0x18004f680  jz      short loc_18004F690
0x18004f682  lea     rcx, [rsp+358h+var_288]; this
0x18004f68a  call    ??1ElementCompletionInfo@@QEAA@XZ; ElementCompletionInfo::~ElementCompletionInfo(void)
0x18004f68f  nop
0x18004f690  mov     rcx, [rsp+358h+psa]; psa
0x18004f698  test    rcx, rcx
0x18004f69b  jz      short loc_18004F6A3
0x18004f69d  call    cs:__imp_SafeArrayDestroy
0x18004f6a3  cmp     [rsp+358h+var_1C0], r13b
0x18004f6ab  jnz     loc_18005007D
0x18004f6b1  mov     rcx, [rsp+358h+bstrString]; bstrString
0x18004f6b9  test    rcx, rcx
0x18004f6bc  jz      short loc_18004F6CC
0x18004f6be  call    cs:__imp_SysFreeString
0x18004f6c4  mov     [rsp+358h+bstrString], r13
0x18004f6cc  lea     rcx, [rsp+358h+var_210]
0x18004f6d4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004f6d9  nop
0x18004f6da  mov     [rsp+358h+var_1B0], r13b
0x18004f6e2  mov     cl, r13b
  ... truncated ...
```
