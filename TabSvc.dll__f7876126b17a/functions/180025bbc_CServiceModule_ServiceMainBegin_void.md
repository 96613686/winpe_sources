# CServiceModule::ServiceMainBegin(void)

- ea: `0x180025bbc`
- end: `0x180026383`
- name: `?ServiceMainBegin@CServiceModule@@QEAAHXZ`
- size: `1991`
- prototype: `__int64 __fastcall(CServiceModule *__hidden this)`
- caller_count: `1`
- callee_count: `35`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180025ae0`

## callees

- `0x180001008`
- `0x1800010f8`
- `0x180001ec0`
- `0x180001f24`
- `0x180010fc0`
- `0x1800110e0`
- `0x180011400`
- `0x1800117c0`
- `0x180011ae0`
- `0x180012060`
- `0x180012dc0`
- `0x180013080`
- `0x180013b64`
- `0x180014700`
- `0x180014890`
- `0x180015630`
- `0x1800194b0`
- `0x18001a174`
- `0x18001a674`
- `0x18001a6c0`
- `0x18001a760`
- `0x18001bbe0`
- `0x18001bc04`
- `0x18001c04c`
- `0x18001f934`
- `0x180025bbc`
- `0x18002638c`
- `0x180026fa8`
- `0x180027c38`
- `0x180028674`
- `0x18002b3a8`
- `0x18002b404`
- `0x18002b4cc`
- `0x18002b6bc`
- `0x180031010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18002617d`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18002617d`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x180025fb5`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x180025fb5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180025f0f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180025f0f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180026199`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180026199`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025cbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025de6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025f33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026063`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025cbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025de6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025f33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026063`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025ee2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025f87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025ee2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025f87`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180025c99`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180025c99`
- `USER32!RegisterDeviceNotificationW` at `0x18002603f`
- `USER32!RegisterDeviceNotificationW` at `0x18002603f`
- `HID!HidD_GetHidGuid` at `0x18002602b`
- `HID!HidD_GetHidGuid` at `0x18002602b`

## string_xrefs

- `0x180025c92`: `TextInputManagementService`
- `0x1800261cd`: `TextInputManagementService`
- `0x180025c17`: `PENSERVICE_CServiceModule::ServiceMainBegin`
- `0x180025d02`: `RegisterServiceCtrlHandlerEx failed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_BOOL8 __fastcall CServiceModule::ServiceMainBegin(CServiceModule *this)
{
  struct _GUID *v1; // rcx
  unsigned __int64 v2; // r8
  int v3; // r14d
  __int64 v4; // rcx
  char LastError; // al
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  HANDLE SystemEvent; // rax
  char v11; // al
  int SecurityDescriptor; // esi
  const unsigned __int16 *v13; // rdx
  char v14; // al
  const unsigned __int16 *v15; // rdx
  unsigned int v16; // r8d
  const unsigned __int16 *v17; // rax
  const struct std::nothrow_t *v18; // rdx
  unsigned __int16 *v19; // rbx
  unsigned __int16 *v20; // rcx
  unsigned int v21; // r8d
  const unsigned __int16 *v22; // rax
  const struct std::nothrow_t *v23; // rdx
  unsigned __int16 *v24; // rdi
  unsigned __int16 *v25; // rcx
  HANDLE v26; // rax
  char v27; // al
  const struct std::nothrow_t *v28; // rdx
  const struct std::nothrow_t *v29; // rdx
  CServiceModule *v30; // rcx
  HDEVNOTIFY v31; // rax
  char v32; // al
  __int64 v33; // rdx
  __int64 v34; // r8
  unsigned int v35; // r9d
  const wchar_t *v36; // rax
  unsigned int v37; // ebx
  struct _GUID *v38; // r8
  unsigned int v39; // r9d
  int v40; // eax
  CServiceModule *v41; // rcx
  int BacklightServer; // eax
  void *v43; // rdx
  __int64 v44; // r8
  __int64 v45; // r8
  __int64 v46; // r9
  struct _GUID *v47; // rax
  unsigned __int64 v48; // r8
  __int64 v49; // rcx
  __int64 v50; // r8
  __int64 v51; // r9
  int v52[2]; // [rsp+20h] [rbp-69h]
  HLOCAL hMem; // [rsp+40h] [rbp-49h] BYREF
  const unsigned __int16 *v54; // [rsp+48h] [rbp-41h] BYREF
  void *Block[2]; // [rsp+50h] [rbp-39h] BYREF
  __int16 v56; // [rsp+60h] [rbp-29h]
  const unsigned __int16 *v57; // [rsp+68h] [rbp-21h]
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+70h] [rbp-19h] BYREF
  __int64 v59; // [rsp+88h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v1 = WPP_GLOBAL_Control;
  v2 = *(_QWORD *)WPP_GLOBAL_Control[3].Data4;
  v3 = 1;
  if ( v2 )
  {
    PrivateTraceEvent(WPP_GLOBAL_Control, 0x611u, v2, 1u);
    v1 = WPP_GLOBAL_Control;
  }
  if ( v1 != (struct _GUID *)&WPP_GLOBAL_Control && (v1[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&v1[1].Data1,
      123,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::ServiceMainBegin");
  if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v4,
      (int)byte_18003950D);
  dword_180041244 = 2;
  LODWORD(qword_18004124C) = 0;
  qword_180041254 = 0;
  hRecipient = RegisterServiceCtrlHandlerExW(L"TextInputManagementService", CServiceModule::ServiceHandler, 0);
  if ( !hRecipient )
  {
    if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_sd(
        *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
        124,
        (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
        (unsigned int)"PENSERVICE_CServiceModule::ServiceMainBegin",
        LastError);
    }
    if ( (unsigned int)dword_1800411A8 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
      {
        hMem = "RegisterServiceCtrlHandlerEx failed.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v6,
          (unsigned __int8 *)byte_18003A7C3,
          v7,
          v8,
          (const unsigned __int16 **)&hMem);
      }
    }
    return 0;
  }
  CServiceModule::SetServiceStatusHelper((CServiceModule *)&_Module, 4u);
  SystemEvent = CreateSystemEvent((LPCWSTR *)off_180032730);
  qword_1800412D8 = (__int64)SystemEvent;
  if ( !SystemEvent )
  {
    if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
    {
      v11 = GetLastError();
      WPP_SF_sd(
        *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
        125,
        (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
        (unsigned int)"PENSERVICE_CServiceModule::ServiceMainBegin",
        v11);
    }
    SecurityDescriptor = -2147467259;
    goto LABEL_79;
  }
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
  {
    v52[1] = HIDWORD(SystemEvent);
    WPP_SF_sq(*(_QWORD *)&WPP_GLOBAL_Control[1].Data1, 126);
  }
  qword_1800412E0 = (__int64)CreateSystemEvent((LPCWSTR *)off_180032740);
  if ( !qword_1800412E0
    && WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
  {
    v14 = GetLastError();
    WPP_SF_sd(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      127,
      (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      (unsigned int)"PENSERVICE_CServiceModule::ServiceMainBegin",
      v14);
  }
  Block[0] = 0;
  Block[1] = 0;
  v56 = 0;
  SecurityDescriptor = StringSd::SetOwner((StringSd *)Block, v13);
  if ( SecurityDescriptor < 0
    || (SecurityDescriptor = StringSd::SetGroup((StringSd *)Block, v15), SecurityDescriptor < 0) )
  {
LABEL_34:
    operator delete(Block[0]);
    goto LABEL_84;
  }
  v17 = StringAce::Allow((StringAce *)L"SY", (const unsigned __int16 *)2, v16);
  v19 = (unsigned __int16 *)v17;
  v54 = v17;
  if ( !v17 )
  {
    SecurityDescriptor = -2147024882;
    v20 = 0;
LABEL_33:
    operator delete(v20, v18);
    goto LABEL_34;
  }
  SecurityDescriptor = StringSd::AddDaclAce((StringSd *)Block, v17);
  if ( SecurityDescriptor < 0 )
  {
LABEL_39:
    v20 = v19;
    goto LABEL_33;
  }
  v22 = StringAce::Allow((StringAce *)L"WD", (const unsigned __int16 *)0x100000, v21);
  v24 = (unsigned __int16 *)v22;
  v57 = v22;
  if ( !v22 )
  {
    SecurityDescriptor = -2147024882;
    v25 = 0;
LABEL_38:
    operator delete(v25, v23);
    goto LABEL_39;
  }
  SecurityDescriptor = StringSd::AddDaclAce((StringSd *)Block, v22);
  if ( SecurityDescriptor < 0 )
  {
LABEL_41:
    v25 = v24;
    goto LABEL_38;
  }
  hMem = 0;
  SecurityDescriptor = StringSd::GetSecurityDescriptor((LPCWSTR *)Block, &hMem);
  if ( SecurityDescriptor < 0 )
  {
    LocalFree(hMem);
    goto LABEL_41;
  }
  *(_QWORD *)&EventAttributes.nLength = 24;
  *(_QWORD *)&EventAttributes.bInheritHandle = 0;
  EventAttributes.lpSecurityDescriptor = hMem;
  v26 = CreateEventW(&EventAttributes, 1, 0, L"Global\\TabletHardwarePresent");
  qword_1800412C8 = (__int64)v26;
  if ( v26 )
  {
    if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    {
      v52[1] = HIDWORD(v26);
      WPP_SF_sq(*(_QWORD *)&WPP_GLOBAL_Control[1].Data1, 129);
    }
  }
  else if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
  {
    v27 = GetLastError();
    WPP_SF_sd(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      128,
      (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      (unsigned int)"PENSERVICE_CServiceModule::ServiceMainBegin",
      v27);
  }
  LocalFree(hMem);
  operator delete(v24, v28);
  operator delete(v19, v29);
  operator delete(Block[0]);
  hMem = OpenMutexW(1u, 0, L"Global\\Windows.Machine.OOBE");
  dword_180041274 = hMem != 0;
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_sd(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      130,
      (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      (unsigned int)"PENSERVICE_CServiceModule::ServiceMainBegin",
      hMem != 0);
  SH<void *,SH_HANDLE>::Reset(&hMem);
  CServiceModule::CreateAdjustedProcessToken(v30);
  *(_OWORD *)&EventAttributes.lpSecurityDescriptor = 0;
  v59 = 0;
  EventAttributes.nLength = 32;
  *(&EventAttributes.nLength + 1) = 5;
  HidD_GetHidGuid((LPGUID)((char *)&EventAttributes.lpSecurityDescriptor + 4));
  v31 = RegisterDeviceNotificationW(hRecipient, &EventAttributes, 1u);
  *(&TokenHandle + 1) = v31;
  if ( v31 )
  {
    if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    {
      v52[1] = HIDWORD(v31);
      WPP_SF_sq(*(_QWORD *)&WPP_GLOBAL_Control[1].Data1, 132);
    }
  }
  else if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
  {
    v32 = GetLastError();
    WPP_SF_sd(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      131,
      (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      (unsigned int)"PENSERVICE_CServiceModule::ServiceMainBegin",
      v32);
  }
  UpdateVersionString();
  CServiceModule::UpdateHardwarePresenceStatus((CServiceModule *)&_Module);
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
  {
    v36 = L"PRESENT";
    if ( !byte_180041270 )
      v36 = L"not present";
    WPP_SF_sS(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      133,
      (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      (unsigned int)"PENSERVICE_CServiceModule::ServiceMainBegin",
      (__int64)v36);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(
                          (wil::details *)`wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl'::`2'::impl,
                          v33,
                          v34,
                          v35) )
  {
    if ( !byte_180041270 && !byte_180041271 )
      v3 = 0;
  }
  else
  {
    v3 = (unsigned __int8)byte_180041270;
  }
  v37 = CServiceModule::_EnableDisablePenProcessTypes((const struct _GUID *)&_Module, v3);
  CServiceModule::StartEnabledPenProcesses(&_Module);
  CServiceModule::_CheckLicense((CServiceModule *)&_Module, v37, v38, v39);
  LODWORD(v54) = 0;
  v52[0] = 0;
  qword_1800412A8 = _o__beginthreadex(0, 0, CServiceModule::MonitorThreadProc, 0, *(_QWORD *)v52, &v54);
  if ( qword_1800412A8 )
    WaitForSingleObject(qword_1800412B0, 0xFFFFFFFF);
  if ( _Module )
  {
    v40 = (*(__int64 (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned __int8), void *, int))(_Module + 192LL))(
            &WaitHandle,
            L"TextInputManagementService",
            qword_180041290,
            CServiceModule::ServiceStopCallback,
            &_Module,
            24);
    if ( v40 )
    {
      if ( v40 > 0 )
        SecurityDescriptor = (unsigned __int16)v40 | 0x80070000;
      else
        SecurityDescriptor = v40;
    }
  }
  else
  {
    SecurityDescriptor = -2147418113;
  }
LABEL_79:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_KBBLS_55832275>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_KBBLS_55832275>::GetImpl'::`2'::impl) )
  {
    if ( SecurityDescriptor >= 0 )
    {
      BacklightServer = CServiceModule::_TryLoadBacklightServer(v41);
      if ( BacklightServer < 0 )
        wil::details::in1diag3::_Log_Hr(retaddr, v43, v44, (const char *)(unsigned int)BacklightServer);
      goto LABEL_93;
    }
LABEL_84:
    if ( qword_1800412A8 )
      CServiceModule::ServiceMainEnd((CServiceModule *)&_Module);
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch>::GetImpl'::`2'::impl) )
    {
      v41 = (CServiceModule *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
        WPP_SF_s(
          *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
          134,
          WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
          "PENSERVICE_CServiceModule::ServiceMainBegin");
      if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
      {
        LODWORD(v54) = SecurityDescriptor;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)v41,
          (int)&dword_1800392CC,
          v45,
          v46,
          (__int64)&v54);
      }
    }
    goto LABEL_93;
  }
  if ( SecurityDescriptor < 0 )
    goto LABEL_84;
LABEL_93:
  v47 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
  {
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      135,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::ServiceMainBegin");
    v47 = WPP_GLOBAL_Control;
  }
  v48 = *(_QWORD *)v47[3].Data4;
  if ( v48 )
    PrivateTraceEvent((const struct _GUID *)v41, 0x611u, v48, 2u);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch>::GetImpl'::`2'::impl)
    && (unsigned int)dword_1800411A8 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
  {
    LODWORD(v54) = dword_180041274;
    LODWORD(hMem) = SecurityDescriptor;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v49,
      (int)&unk_18003A4C0,
      v50,
      v51,
      (__int64)&hMem,
      (__int64)&v54);
  }
  return SecurityDescriptor >= 0;
}

```

## disassembly

```asm
0x180025bbc  push    rbp
0x180025bbe  push    rbx
0x180025bbf  push    rsi
0x180025bc0  push    rdi
0x180025bc1  push    r12
0x180025bc3  push    r13
0x180025bc5  push    r14
0x180025bc7  push    r15
0x180025bc9  lea     rbp, [rsp-1Fh]
0x180025bce  sub     rsp, 0A8h
0x180025bd5  mov     rax, cs:__security_cookie
0x180025bdc  xor     rax, rsp
0x180025bdf  mov     [rbp+57h+var_50], rax
0x180025be3  mov     rcx, cs:WPP_GLOBAL_Control; struct _GUID *
0x180025bea  mov     r8, [rcx+38h]; unsigned __int64
0x180025bee  mov     r14d, 1
0x180025bf4  xor     r15d, r15d
0x180025bf7  test    r8, r8
0x180025bfa  jz      short loc_180025C10
0x180025bfc  mov     r9b, r14b; unsigned __int8
0x180025bff  mov     edx, 611h; unsigned int
0x180025c04  call    ?PrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; PrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x180025c09  mov     rcx, cs:WPP_GLOBAL_Control
0x180025c10  lea     r12, WPP_GLOBAL_Control
0x180025c17  lea     r13, aPenserviceCser_12; "PENSERVICE_CServiceModule::ServiceMainB"...
0x180025c1e  cmp     rcx, r12
0x180025c21  jz      short loc_180025C41
0x180025c23  test    byte ptr [rcx+1Ch], 10h
0x180025c27  jz      short loc_180025C41
0x180025c29  mov     edx, 7Bh ; '{'
0x180025c2e  mov     r9, r13
0x180025c31  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180025c38  mov     rcx, [rcx+10h]
0x180025c3c  call    WPP_SF_s
0x180025c41  mov     eax, cs:dword_1800411A8
0x180025c47  mov     ebx, 4000000h
0x180025c4c  cmp     eax, 5
0x180025c4f  jbe     short loc_180025C6F
0x180025c51  mov     edx, ebx
0x180025c53  lea     rcx, dword_1800411A8
0x180025c5a  call    _tlgKeywordOn
0x180025c5f  test    al, al
0x180025c61  jz      short loc_180025C6F
0x180025c63  lea     rdx, byte_18003950D
0x180025c6a  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180025c6f  mov     edi, 2
0x180025c74  mov     cs:dword_180041244, edi
0x180025c7a  mov     dword ptr cs:qword_18004124C, r15d
0x180025c81  mov     cs:qword_180041254, r15
0x180025c88  xor     r8d, r8d; lpContext
0x180025c8b  lea     rdx, ?ServiceHandler@CServiceModule@@SAKKKPEAX0@Z; lpHandlerProc
0x180025c92  lea     rcx, ServiceName; "TextInputManagementService"
0x180025c99  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180025c9f  mov     cs:hRecipient, rax
0x180025ca6  test    rax, rax
0x180025ca9  jnz     short loc_180025D29
0x180025cab  mov     rax, cs:WPP_GLOBAL_Control
0x180025cb2  cmp     rax, r12
0x180025cb5  jz      short loc_180025CE4
0x180025cb7  test    byte ptr [rax+1Ch], 4
0x180025cbb  jz      short loc_180025CE4
0x180025cbd  call    cs:__imp_GetLastError
0x180025cc3  lea     edx, [rdi+7Ah]
0x180025cc6  mov     [rsp+0E0h+var_C0], eax
0x180025cca  mov     r9, r13
0x180025ccd  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180025cd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180025cdb  mov     rcx, [rcx+10h]
0x180025cdf  call    WPP_SF_sd
0x180025ce4  mov     eax, cs:dword_1800411A8
0x180025cea  cmp     eax, 5
0x180025ced  jbe     short loc_180025D22
0x180025cef  mov     rdx, rbx
0x180025cf2  lea     rcx, dword_1800411A8
0x180025cf9  call    _tlgKeywordOn
0x180025cfe  test    al, al
0x180025d00  jz      short loc_180025D22
0x180025d02  lea     rax, aRegisterservic_0; "RegisterServiceCtrlHandlerEx failed."
0x180025d09  mov     [rbp+57h+hMem], rax
0x180025d0d  lea     rax, [rbp+57h+hMem]
0x180025d11  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180025d16  lea     rdx, byte_18003A7C3
0x180025d1d  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180025d22  xor     eax, eax
0x180025d24  jmp     loc_180026363
0x180025d29  mov     edx, 4; unsigned int
0x180025d2e  lea     rcx, ?_Module@@3VCServiceModule@@A; this
0x180025d35  call    ?SetServiceStatusHelper@CServiceModule@@QEAAXK@Z; CServiceModule::SetServiceStatusHelper(ulong)
0x180025d3a  lea     rcx, off_180032730; struct SystemEventInfo *
0x180025d41  call    ?CreateSystemEvent@@YAPEAXPEBUSystemEventInfo@@@Z; CreateSystemEvent(SystemEventInfo const *)
0x180025d46  mov     cs:qword_1800412D8, rax
0x180025d4d  test    rax, rax
0x180025d50  jnz     short loc_180025D97
0x180025d52  mov     rax, cs:WPP_GLOBAL_Control
0x180025d59  cmp     rax, r12
0x180025d5c  jz      short loc_180025D8D
0x180025d5e  test    byte ptr [rax+1Ch], 4
0x180025d62  jz      short loc_180025D8D
0x180025d64  call    cs:__imp_GetLastError
0x180025d6a  mov     edx, 7Dh ; '}'
0x180025d6f  mov     [rsp+0E0h+var_C0], eax
0x180025d73  mov     r9, r13
0x180025d76  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180025d7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d84  mov     rcx, [rcx+10h]
0x180025d88  call    WPP_SF_sd
0x180025d8d  mov     esi, 80004005h
0x180025d92  jmp     loc_1800261FA
0x180025d97  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d9e  cmp     rcx, r12
0x180025da1  jz      short loc_180025DBC
0x180025da3  test    byte ptr [rcx+1Ch], 10h
0x180025da7  jz      short loc_180025DBC
0x180025da9  mov     edx, 7Eh ; '~'
0x180025dae  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180025db3  mov     rcx, [rcx+10h]
0x180025db7  call    WPP_SF_sq
0x180025dbc  lea     rcx, off_180032740; struct SystemEventInfo *
0x180025dc3  call    ?CreateSystemEvent@@YAPEAXPEBUSystemEventInfo@@@Z; CreateSystemEvent(SystemEventInfo const *)
0x180025dc8  mov     cs:qword_1800412E0, rax
0x180025dcf  test    rax, rax
0x180025dd2  jnz     short loc_180025E0F
0x180025dd4  mov     rax, cs:WPP_GLOBAL_Control
0x180025ddb  cmp     rax, r12
0x180025dde  jz      short loc_180025E0F
0x180025de0  test    byte ptr [rax+1Ch], 4
0x180025de4  jz      short loc_180025E0F
0x180025de6  call    cs:__imp_GetLastError
0x180025dec  mov     edx, 7Fh
0x180025df1  mov     [rsp+0E0h+var_C0], eax
0x180025df5  mov     r9, r13
0x180025df8  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180025dff  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e06  mov     rcx, [rcx+10h]
0x180025e0a  call    WPP_SF_sd
0x180025e0f  mov     [rbp+57h+Block], r15
0x180025e13  mov     [rbp+57h+var_88], r15
0x180025e17  mov     [rbp+57h+var_80], r15w
0x180025e1c  lea     rcx, [rbp+57h+Block]; this
0x180025e20  call    ?SetOwner@StringSd@@QEAAJPEBG@Z; StringSd::SetOwner(ushort const *)
0x180025e25  mov     esi, eax
0x180025e27  test    eax, eax
0x180025e29  js      short loc_180025E61
0x180025e2b  lea     rcx, [rbp+57h+Block]; this
0x180025e2f  call    ?SetGroup@StringSd@@QEAAJPEBG@Z; StringSd::SetGroup(ushort const *)
0x180025e34  mov     esi, eax
0x180025e36  test    eax, eax
0x180025e38  js      short loc_180025E61
0x180025e3a  mov     edx, edi; unsigned __int16 *
0x180025e3c  lea     rcx, aSy; "SY"
0x180025e43  call    ?Allow@StringAce@@YAPEAGPEBGK@Z; StringAce::Allow(ushort const *,ulong)
0x180025e48  mov     rbx, rax
0x180025e4b  mov     [rbp+57h+var_98], rax
0x180025e4f  test    rax, rax
0x180025e52  jnz     short loc_180025E6F
0x180025e54  mov     esi, 8007000Eh
0x180025e59  xor     ecx, ecx; void *
0x180025e5b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180025e60  nop
0x180025e61  mov     rcx, [rbp+57h+Block]; Block
0x180025e65  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025e6a  jmp     loc_180026234
0x180025e6f  mov     rdx, rbx; unsigned __int16 *
0x180025e72  lea     rcx, [rbp+57h+Block]; this
0x180025e76  call    ?AddDaclAce@StringSd@@QEAAJPEBG@Z; StringSd::AddDaclAce(ushort const *)
0x180025e7b  mov     esi, eax
0x180025e7d  test    eax, eax
0x180025e7f  js      short loc_180025EAB
0x180025e81  mov     edx, 100000h; unsigned __int16 *
0x180025e86  lea     rcx, aWd; "WD"
0x180025e8d  call    ?Allow@StringAce@@YAPEAGPEBGK@Z; StringAce::Allow(ushort const *,ulong)
0x180025e92  mov     rdi, rax
0x180025e95  mov     [rbp+57h+var_78], rax
0x180025e99  test    rax, rax
0x180025e9c  jnz     short loc_180025EB0
0x180025e9e  mov     esi, 8007000Eh
0x180025ea3  xor     ecx, ecx; void *
0x180025ea5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180025eaa  nop
0x180025eab  mov     rcx, rbx
0x180025eae  jmp     short loc_180025E5B
0x180025eb0  mov     rdx, rdi; unsigned __int16 *
0x180025eb3  lea     rcx, [rbp+57h+Block]; this
0x180025eb7  call    ?AddDaclAce@StringSd@@QEAAJPEBG@Z; StringSd::AddDaclAce(ushort const *)
0x180025ebc  mov     esi, eax
0x180025ebe  test    eax, eax
0x180025ec0  jns     short loc_180025EC7
0x180025ec2  mov     rcx, rdi
0x180025ec5  jmp     short loc_180025EA5
0x180025ec7  mov     [rbp+57h+hMem], r15
0x180025ecb  lea     rdx, [rbp+57h+hMem]; void **
0x180025ecf  lea     rcx, [rbp+57h+Block]; this
0x180025ed3  call    ?GetSecurityDescriptor@StringSd@@QEAAJPEAPEAX@Z; StringSd::GetSecurityDescriptor(void * *)
0x180025ed8  mov     esi, eax
0x180025eda  test    eax, eax
0x180025edc  jns     short loc_180025EEA
0x180025ede  mov     rcx, [rbp+57h+hMem]; hMem
0x180025ee2  call    cs:__imp_LocalFree
0x180025ee8  jmp     short loc_180025EC2
0x180025eea  mov     qword ptr [rbp+57h+EventAttributes.nLength], 18h
0x180025ef2  mov     qword ptr [rbp+57h+EventAttributes.bInheritHandle], r15
0x180025ef6  mov     rax, [rbp+57h+hMem]
0x180025efa  mov     [rbp+57h+EventAttributes.lpSecurityDescriptor], rax
0x180025efe  lea     r9, Name; "Global\\TabletHardwarePresent"
0x180025f05  xor     r8d, r8d; bInitialState
0x180025f08  mov     edx, r14d; bManualReset
0x180025f0b  lea     rcx, [rbp+57h+EventAttributes]; lpEventAttributes
0x180025f0f  call    cs:__imp_CreateEventW
0x180025f15  mov     cs:qword_1800412C8, rax
0x180025f1c  test    rax, rax
0x180025f1f  jnz     short loc_180025F5E
0x180025f21  mov     rax, cs:WPP_GLOBAL_Control
0x180025f28  cmp     rax, r12
0x180025f2b  jz      short loc_180025F83
0x180025f2d  test    byte ptr [rax+1Ch], 4
0x180025f31  jz      short loc_180025F83
0x180025f33  call    cs:__imp_GetLastError
0x180025f39  mov     edx, 80h
0x180025f3e  mov     [rsp+0E0h+var_C0], eax
0x180025f42  mov     r9, r13
0x180025f45  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180025f4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180025f53  mov     rcx, [rcx+10h]
0x180025f57  call    WPP_SF_sd
0x180025f5c  jmp     short loc_180025F83
0x180025f5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180025f65  cmp     rcx, r12
0x180025f68  jz      short loc_180025F83
0x180025f6a  test    byte ptr [rcx+1Ch], 10h
0x180025f6e  jz      short loc_180025F83
0x180025f70  mov     edx, 81h
0x180025f75  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180025f7a  mov     rcx, [rcx+10h]
0x180025f7e  call    WPP_SF_sq
0x180025f83  mov     rcx, [rbp+57h+hMem]; hMem
0x180025f87  call    cs:__imp_LocalFree
0x180025f8d  nop
0x180025f8e  mov     rcx, rdi; void *
0x180025f91  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180025f96  nop
0x180025f97  mov     rcx, rbx; void *
0x180025f9a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180025f9f  nop
0x180025fa0  mov     rcx, [rbp+57h+Block]; Block
0x180025fa4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025fa9  lea     r8, aGlobalWindowsM; "Global\\Windows.Machine.OOBE"
0x180025fb0  xor     edx, edx; bInheritHandle
0x180025fb2  mov     ecx, r14d; dwDesiredAccess
0x180025fb5  call    cs:__imp_OpenMutexW
0x180025fbb  mov     [rbp+57h+hMem], rax
0x180025fbf  mov     r8d, r15d
0x180025fc2  test    rax, rax
0x180025fc5  setnz   r8b
0x180025fc9  mov     cs:dword_180041274, r8d
0x180025fd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180025fd7  cmp     rcx, r12
0x180025fda  jz      short loc_180025FFF
0x180025fdc  test    byte ptr [rcx+1Ch], 10h
0x180025fe0  jz      short loc_180025FFF
0x180025fe2  mov     edx, 82h
0x180025fe7  mov     [rsp+0E0h+var_C0], r8d
0x180025fec  mov     r9, r13
0x180025fef  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180025ff6  mov     rcx, [rcx+10h]
0x180025ffa  call    WPP_SF_sd
0x180025fff  lea     rcx, [rbp+57h+hMem]
0x180026003  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x180026008  call    ?CreateAdjustedProcessToken@CServiceModule@@QEAAHXZ; CServiceModule::CreateAdjustedProcessToken(void)
0x18002600d  xorps   xmm0, xmm0
0x180026010  movdqu  xmmword ptr [rbp+57h+EventAttributes.lpSecurityDescriptor], xmm0
0x180026015  mov     [rbp+57h+var_58], r15
0x180026019  mov     [rbp+57h+EventAttributes.nLength], 20h ; ' '
0x180026020  mov     dword ptr [rbp+57h+EventAttributes+4], 5
0x180026027  lea     rcx, [rbp+57h+EventAttributes.lpSecurityDescriptor+4]; HidGuid
0x18002602b  call    cs:__imp_HidD_GetHidGuid
0x180026031  mov     r8d, r14d; Flags
0x180026034  lea     rdx, [rbp+57h+EventAttributes]; NotificationFilter
0x180026038  mov     rcx, cs:hRecipient; hRecipient
0x18002603f  call    cs:__imp_RegisterDeviceNotificationW
0x180026045  mov     qword ptr cs:TokenHandle+8, rax
0x18002604c  test    rax, rax
0x18002604f  jnz     short loc_18002608E
0x180026051  mov     rax, cs:WPP_GLOBAL_Control
0x180026058  cmp     rax, r12
0x18002605b  jz      short loc_1800260B3
0x18002605d  test    byte ptr [rax+1Ch], 4
0x180026061  jz      short loc_1800260B3
0x180026063  call    cs:__imp_GetLastError
0x180026069  mov     edx, 83h
0x18002606e  mov     [rsp+0E0h+var_C0], eax
0x180026072  mov     r9, r13
0x180026075  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18002607c  mov     rcx, cs:WPP_GLOBAL_Control
0x180026083  mov     rcx, [rcx+10h]
0x180026087  call    WPP_SF_sd
0x18002608c  jmp     short loc_1800260B3
0x18002608e  mov     rcx, cs:WPP_GLOBAL_Control
0x180026095  cmp     rcx, r12
0x180026098  jz      short loc_1800260B3
0x18002609a  test    byte ptr [rcx+1Ch], 10h
  ... truncated ...
```
