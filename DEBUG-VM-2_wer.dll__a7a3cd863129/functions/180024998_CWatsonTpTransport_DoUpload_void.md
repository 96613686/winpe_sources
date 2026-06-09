# CWatsonTpTransport::DoUpload(void)

- ea: `0x180024998`
- end: `0x180025565`
- name: `?DoUpload@CWatsonTpTransport@@AEAAJXZ`
- size: `3021`
- prototype: `__int64 __fastcall(CWatsonTpTransport *__hidden this)`
- caller_count: `1`
- callee_count: `42`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004c210`

## callees

- `0x180004bb4`
- `0x18000bc10`
- `0x18000bc2c`
- `0x18000dad0`
- `0x18001fe24`
- `0x180024998`
- `0x18002556c`
- `0x180025594`
- `0x1800255d8`
- `0x18002cf08`
- `0x180039d00`
- `0x180039d84`
- `0x18003bf14`
- `0x18003c24c`
- `0x18003df8c`
- `0x18003f364`
- `0x18004485c`
- `0x180047cc4`
- `0x1800489f0`
- `0x180048ee4`
- `0x18004ae6c`
- `0x18004c774`
- `0x18004c7c0`
- `0x180051f50`
- `0x180070aa4`
- `0x18007209c`
- `0x180073680`
- `0x180086c88`
- `0x180086e00`
- `0x180087154`
- `0x1800872e8`
- `0x180087724`
- `0x180087ee8`
- `0x180088a28`
- `0x180088b70`
- `0x180088ea8`
- `0x18008ab58`
- `0x18008f31c`
- `0x18008f354`
- `0x18008f39c`
- `0x18008f3d0`
- `0x1800ac010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800254c2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800254df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800254fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800254c2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800254df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800254fc`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180024d5d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180025363`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180024d5d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180025363`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180024cbf`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800252d1`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180024cbf`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800252d1`
- `ext-ms-win-wer-xbox-l1-2-1!XerHitRequestResponse` at `0x180024e48`
- `ext-ms-win-wer-xbox-l1-2-1!XerHitRequestResponse` at `0x180024e48`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CWatsonTpTransport::DoUpload(CWatsonTpTransport *this)
{
  __int64 v2; // r14
  int DeviceTicketHeader; // ebx
  int v4; // eax
  wchar_t *v5; // rcx
  __int64 v6; // rdx
  int v7; // eax
  wchar_t *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  BOOL v11; // r13d
  int UploadCab; // eax
  __int64 v13; // rbx
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  wchar_t *v17; // rcx
  _DWORD *v18; // rbx
  int *v19; // r9
  wchar_t *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rdx
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  struct CReportCabStream *v27; // r13
  void *v28; // rbx
  unsigned __int64 v29; // rax
  int v30; // eax
  wchar_t *v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // r9
  int v34; // eax
  const wchar_t *v35; // rbx
  unsigned __int64 v36; // rax
  int v37; // ebx
  void *v38; // rax
  _QWORD v40[3]; // [rsp+80h] [rbp-80h] BYREF
  struct CReportCabStream *v41; // [rsp+98h] [rbp-68h] BYREF
  wchar_t *v42; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t *v43; // [rsp+A8h] [rbp-58h]
  char v44; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v45[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v46[32]; // [rsp+E0h] [rbp-20h] BYREF
  LPVOID lpMem[2]; // [rsp+100h] [rbp+0h] BYREF
  char v48; // [rsp+110h] [rbp+10h] BYREF
  void **v49; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v50[24]; // [rsp+128h] [rbp+28h] BYREF
  void **v51; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v52[24]; // [rsp+148h] [rbp+48h] BYREF
  wchar_t *v53[2]; // [rsp+160h] [rbp+60h] BYREF
  char v54; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v55[32]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v56[848]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v57[32]; // [rsp+4F0h] [rbp+3F0h] BYREF
  _BYTE v58[912]; // [rsp+510h] [rbp+410h] BYREF
  BOOL v59; // [rsp+8B0h] [rbp+7B0h]
  __int64 v60; // [rsp+8B8h] [rbp+7B8h] BYREF
  int v61; // [rsp+8C0h] [rbp+7C0h] BYREF
  __int64 v62; // [rsp+8C8h] [rbp+7C8h] BYREF

  v2 = *((_QWORD *)this + 6);
  CTpRequestMessage::CTpRequestMessage((CTpRequestMessage *)v55);
  v51 = &CTpResponseMessage::`vftable';
  utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(v52);
  CTpRequestMessage::CTpRequestMessage((CTpRequestMessage *)v57);
  v49 = &CTpResponseMessage::`vftable';
  utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(v50);
  utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(v40);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v53);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v42);
  v62 = 0;
  LODWORD(v60) = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpMem);
  v61 = 2;
  v41 = 0;
  DeviceTicketHeader = CTransport::EventTransportBegin(this, (struct CReport *)v2, *((void **)this + 5));
  if ( DeviceTicketHeader < 0 )
    goto LABEL_163;
  if ( (int)MachineId::GetMachineId((__int64)v53) >= 0 )
  {
    v4 = CTpRequestMessage::SetMachineId((CTpRequestMessage *)v55, v53[0]);
    DeviceTicketHeader = v4;
    if ( v4 < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v6 = 59;
LABEL_7:
        WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids, (unsigned int)v4);
        goto LABEL_163;
      }
      goto LABEL_163;
    }
  }
  v4 = OsInformation::Copy((OsInformation *)v56, (const struct OsInformation *)(*((_QWORD *)this + 6) + 6032LL));
  DeviceTicketHeader = v4;
  if ( v4 >= 0 )
  {
    v4 = OsInformation::Copy((OsInformation *)v58, (const struct OsInformation *)(*((_QWORD *)this + 6) + 6032LL));
    DeviceTicketHeader = v4;
    if ( v4 < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v6 = 61;
        goto LABEL_7;
      }
      goto LABEL_163;
    }
    v7 = CTpRequestMessage::SetCommercialInfo(
           v55,
           *(unsigned int *)(*((_QWORD *)this + 6) + 51912LL),
           *(unsigned int *)(*((_QWORD *)this + 6) + 51916LL),
           *((_QWORD *)this + 6) + 51920LL);
    DeviceTicketHeader = v7;
    if ( v7 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_163;
      v9 = 62;
LABEL_20:
      v10 = (unsigned int)v7;
LABEL_21:
      WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids, v10);
      goto LABEL_163;
    }
    v7 = CTpRequestMessage::SetCommercialInfo(
           v57,
           *(unsigned int *)(*((_QWORD *)this + 6) + 51912LL),
           *(unsigned int *)(*((_QWORD *)this + 6) + 51916LL),
           *((_QWORD *)this + 6) + 51920LL);
    DeviceTicketHeader = v7;
    if ( v7 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_163;
      v9 = 63;
      goto LABEL_20;
    }
    v11 = 0;
    v59 = 0;
    CTpLogger::StartSession((CWatsonTpTransport *)((char *)this + 80), L"watson");
    if ( *((_DWORD *)this + 14) )
    {
      UploadCab = CWatsonTpTransport::LoadResumeState(this, &v42, &v62);
      DeviceTicketHeader = UploadCab;
      if ( UploadCab < 0 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_163;
        v9 = 77;
        goto LABEL_31;
      }
      if ( v42 == v43 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v25, v24, v26);
      if ( !v62 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v25, v24, v26);
      v8 = WPP_GLOBAL_Control;
      goto LABEL_109;
    }
    UploadCab = CWatsonTpTransport::PrepareEventRequest((struct CReport *)v2, (struct CTpRequestMessage *)v55);
    DeviceTicketHeader = UploadCab;
    if ( UploadCab < 0 )
    {
      *(_DWORD *)(v2 + 5960) |= 0x60u;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_163;
      v9 = 64;
LABEL_31:
      v10 = (unsigned int)UploadCab;
      goto LABEL_21;
    }
    DeviceTicketHeader = CTransport::GetDeviceTicketHeader(lpMem, *((_QWORD *)this + 5));
    if ( DeviceTicketHeader < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 2) == 0 )
        goto LABEL_163;
      v9 = 65;
LABEL_36:
      v10 = (unsigned int)DeviceTicketHeader;
      goto LABEL_21;
    }
    v13 = *(_QWORD *)(v2 + 52056);
    if ( v13 )
    {
      v11 = ImpersonateLoggedOnUser(*(HANDLE *)(v2 + 52056));
      v59 = v11;
    }
    DeviceTicketHeader = CTpTransport::DoExchange(
                           (struct CTpRequestMessage *)v55,
                           0,
                           (CTpResponseMessage *)&v51,
                           (__int64)off_1800AE818,
                           (struct ITpCallbacks *)(((unsigned __int64)this + 32) & -(__int64)(this != 0)),
                           0,
                           0,
                           v13,
                           *((void **)this + 5),
                           (CWatsonTpTransport *)((char *)this + 80),
                           (wchar_t *)L"s1event",
                           0,
                           (wchar_t *)lpMem[0],
                           0,
                           *(_DWORD *)(v2 + 52052));
    if ( v11 )
    {
      RevertToSelf();
      v59 = 0;
    }
    if ( DeviceTicketHeader < 0 )
    {
      *(_DWORD *)(v2 + 5960) |= 0x60u;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_163;
      v9 = 66;
      goto LABEL_36;
    }
    v14 = CReport::AddStateParam((CReport *)v2, L"Transport.DoneStage1", L"1");
    if ( v14 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        67,
        WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids,
        (unsigned int)v14);
    UploadCab = CWatsonTpTransport::ParseEventResponse(
                  (CTpResponseMessage *)&v51,
                  (CResponse *)(v2 + 8),
                  (struct CDataRequest *)v40,
                  (__int64)&v62,
                  (__int64)&v60);
    DeviceTicketHeader = UploadCab;
    if ( UploadCab < 0 )
    {
      *(_DWORD *)(v2 + 5960) |= 0x60u;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_163;
      v9 = 68;
      goto LABEL_31;
    }
    if ( (unsigned __int8)IsXerHitRequestResponsePresent() )
      XerHitRequestResponse(*(_QWORD *)(v2 + 8));
    CWatsonTpTransport::SetLegacyTokensFromCollectCommand(
      (const struct CDataRequest *)v40,
      (struct CResponse *)(v2 + 8));
    if ( *(_DWORD *)(v2 + 46680) == 2 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids);
      MicrosoftTelemetryAssertTriggeredNoArgs(v17, v15, v16);
      DeviceTicketHeader = -2147467263;
      goto LABEL_163;
    }
    v18 = (_DWORD *)(v2 + 6616);
    if ( *(_DWORD *)(v2 + 364) )
    {
      *v18 |= 0x100u;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids);
    }
    if ( (unsigned int)CDataRequest::IsBypassDataThrottling((CDataRequest *)v40) )
      *v18 |= 0x800u;
    if ( (_DWORD)v60 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids);
      goto LABEL_70;
    }
    if ( *(_DWORD *)(v2 + 252) )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_77;
      v21 = 72;
LABEL_76:
      WPP_SF_(*((_QWORD *)v20 + 2), v21, WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids);
LABEL_77:
      CReport::ThrottleCurrentEvent((CReport *)v2, *(_DWORD *)(v2 + 252));
LABEL_70:
      *(_DWORD *)(v2 + 5960) |= 0x2000u;
LABEL_71:
      DeviceTicketHeader = 1769483;
      goto LABEL_163;
    }
    if ( !(-286331153 * (unsigned int)((__int64)(v40[1] - v40[0]) >> 3)) )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_162;
      v22 = 73;
      goto LABEL_161;
    }
    DeviceTicketHeader = CTransport::EventDataRequest(
                           this,
                           (struct CDataRequest *)v40,
                           *((void **)this + 5),
                           v19,
                           (enum TRANSPORT_SECONDLEVEL_USER_RESPONSE *)&v61);
    if ( DeviceTicketHeader < 0 )
      goto LABEL_163;
    v23 = CWatsonTpTransport::SaveResumeState(this, &v42, v62);
    DeviceTicketHeader = v23;
    if ( v23 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 2) == 0 )
        goto LABEL_88;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        74,
        WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids,
        (unsigned int)v23);
    }
    v8 = WPP_GLOBAL_Control;
LABEL_88:
    if ( v61 == 1 )
    {
      if ( DeviceTicketHeader >= 0 || v8 == (wchar_t *)&WPP_GLOBAL_Control || (v8[14] & 1) == 0 )
        goto LABEL_163;
      v9 = 75;
      goto LABEL_36;
    }
    if ( v61 == 3 )
    {
      if ( v8 != (wchar_t *)&WPP_GLOBAL_Control && (v8[14] & 4) != 0 )
        WPP_SF_(*((_QWORD *)v8 + 2), (unsigned int)(v61 + 73), WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids);
      *(_DWORD *)(v2 + 5960) |= 0x1000u;
      goto LABEL_71;
    }
    if ( v61 )
    {
      DeviceTicketHeader = -2145681407;
      goto LABEL_163;
    }
LABEL_109:
    if ( v42 == v43 )
    {
      if ( v8 == (wchar_t *)&WPP_GLOBAL_Control || (v8[14] & 2) == 0 )
        goto LABEL_162;
      v22 = 78;
      goto LABEL_161;
    }
    UploadCab = CTransport::EventGetUploadCab(this, &v41, *((void **)this + 5), 0);
    DeviceTicketHeader = UploadCab;
    if ( UploadCab < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_163;
      v9 = 79;
      goto LABEL_31;
    }
    v27 = v41;
    if ( !v41 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 2) == 0 )
        goto LABEL_162;
      v22 = 86;
LABEL_161:
      WPP_SF_(*((_QWORD *)v8 + 2), v22, WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids);
      goto LABEL_162;
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v46);
    CTpResponseMessage::CTpResponseMessage((CTpResponseMessage *)v45);
    v28 = (void *)*((_QWORD *)this + 5);
    v29 = (*(__int64 (__fastcall **)(struct CReportCabStream *))(*(_QWORD *)v27 + 32LL))(v27);
    v30 = CTransport::EventUploadStart(this, v29, v28);
    DeviceTicketHeader = v30;
    if ( v30 >= 0 )
    {
      v34 = CWatsonTpTransport::UploadToAzure(
              this,
              v27,
              v42,
              (const wchar_t *)lpMem[0],
              (const struct CDataRequest *)v40);
      DeviceTicketHeader = v34;
      if ( v34 >= 0 )
      {
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids);
        goto LABEL_124;
      }
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          81,
          WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids,
          (unsigned int)v34);
      v35 = L"zip";
      if ( !*((_DWORD *)v27 + 4) )
        v35 = L"cab";
      v36 = (*(__int64 (__fastcall **)(struct CReportCabStream *))(*(_QWORD *)v27 + 32LL))(v27);
      v30 = CWatsonTpTransport::PrepareCabUploadRequest(
              (struct CReport *)v2,
              (struct CResponse *)(v2 + 8),
              v42,
              v36,
              v35,
              (const struct CDataRequest *)v40,
              (struct CTpRequestMessage *)v57);
      DeviceTicketHeader = v30;
      if ( v30 >= 0 )
      {
        v37 = 0;
        if ( (unsigned int)CSettings::IsUploadOnFreeNetworksOnly((CSettings *)(*((_QWORD *)this + 6) + 46688LL))
          && !(unsigned int)CReport::GetUploadShouldBypassNetworkCostThrottling(*((CReport **)this + 6)) )
        {
          v37 = 2;
        }
        v38 = *(void **)(v2 + 52056);
        v60 = (__int64)v38;
        if ( v38 )
          v59 = ImpersonateLoggedOnUser(v38);
        DeviceTicketHeader = CTpTransport::DoExchange(
                               (struct CTpRequestMessage *)v57,
                               v27,
                               (CTpResponseMessage *)&v49,
                               (__int64)off_1800AE818,
                               (struct ITpCallbacks *)(((unsigned __int64)this + 32) & -(__int64)(this != 0)),
                               v37,
                               0,
                               v60,
                               *((void **)this + 5),
                               (CWatsonTpTransport *)((char *)this + 80),
                               (wchar_t *)L"cab-upload",
                               0,
                               (wchar_t *)lpMem[0],
                               0,
                               0);
        if ( v59 )
          RevertToSelf();
        if ( DeviceTicketHeader >= 0 )
        {
          DeviceTicketHeader = CWatsonTpTransport::ParseCabUploadResponse(
                                 (struct CTpResponseMessage *)&v49,
                                 (struct CResponse *)(v2 + 8),
                                 (int *)&v60);
          CTransport::EventCabUploadComplete(this, DeviceTicketHeader);
          if ( DeviceTicketHeader >= 0 )
          {
            CWatsonTpTransport::ForgetResumeState(this);
            CTpResponseMessage::~CTpResponseMessage((CTpResponseMessage *)v45);
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v46);
            if ( *(_DWORD *)(v2 + 252) )
            {
              v20 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
                goto LABEL_77;
              v21 = 87;
              goto LABEL_76;
            }
LABEL_162:
            DeviceTicketHeader = 0;
            goto LABEL_163;
          }
          *(_DWORD *)(v2 + 5960) |= 0x180u;
          v31 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          {
LABEL_124:
            CTpResponseMessage::~CTpResponseMessage((CTpResponseMessage *)v45);
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v46);
            goto LABEL_163;
          }
          v32 = 85;
        }
        else
        {
          CTransport::EventCabUploadComplete(this, DeviceTicketHeader);
          *(_DWORD *)(v2 + 5960) |= 0x180u;
          v31 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
            goto LABEL_124;
          v32 = 84;
        }
        v33 = (unsigned int)DeviceTicketHeader;
LABEL_123:
        WPP_SF_d(*((_QWORD *)v31 + 2), v32, WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids, v33);
        goto LABEL_124;
      }
      *(_DWORD *)(v2 + 5960) |= 0x180u;
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_124;
      v32 = 83;
    }
    else
    {
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_124;
      v32 = 80;
    }
    v33 = (unsigned int)v30;
    goto LABEL_123;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v6 = 60;
    goto LABEL_7;
  }
LABEL_163:
  CTransport::EventTransportFinish(this, DeviceTicketHeader);
  if ( lpMem[0] != &v48 )
    HeapFree(g_hWerheap, 0, lpMem[0]);
  if ( v42 != (wchar_t *)&v44 )
    HeapFree(g_hWerheap, 0, v42);
  if ( (char *)v53[0] != &v54 )
    HeapFree(g_hWerheap, 0, v53[0]);
  utl::vector<RequestToken,utl::allocator<RequestToken>>::_Uninit(v40);
  v49 = &CTpResponseMessage::`vftable';
  utl::vector<utl::unique_ptr<CTpRequestSection,utl::default_delete<CTpRequestSection>>,utl::allocator<utl::unique_ptr<CTpRequestSection,utl::default_delete<CTpRequestSection>>>>::_Uninit(v50);
  v49 = &CTpMessage::`vftable';
  CTpRequestMessage::~CTpRequestMessage((CTpRequestMessage *)v57);
  v51 = &CTpResponseMessage::`vftable';
  utl::vector<utl::unique_ptr<CTpRequestSection,utl::default_delete<CTpRequestSection>>,utl::allocator<utl::unique_ptr<CTpRequestSection,utl::default_delete<CTpRequestSection>>>>::_Uninit(v52);
  v51 = &CTpMessage::`vftable';
  CTpRequestMessage::~CTpRequestMessage((CTpRequestMessage *)v55);
  return (unsigned int)DeviceTicketHeader;
}

```

## disassembly

```asm
0x180024998  push    rbp
0x18002499a  push    rbx
0x18002499b  push    rsi
0x18002499c  push    rdi
0x18002499d  push    r12
0x18002499f  push    r13
0x1800249a1  push    r14
0x1800249a3  push    r15
0x1800249a5  lea     rbp, [rsp-768h]
0x1800249ad  sub     rsp, 868h
0x1800249b4  mov     r15, rcx
0x1800249b7  mov     r14, [rcx+30h]
0x1800249bb  lea     rcx, [rbp+7A0h+var_720]; this
0x1800249c2  call    ??0CTpRequestMessage@@QEAA@XZ; CTpRequestMessage::CTpRequestMessage(void)
0x1800249c7  nop
0x1800249c8  lea     rsi, ??_7CTpResponseMessage@@6B@; const CTpResponseMessage::`vftable'
0x1800249cf  mov     [rbp+7A0h+var_760], rsi
0x1800249d3  lea     rcx, [rbp+7A0h+var_758]
0x1800249d7  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(void)
0x1800249dc  nop
0x1800249dd  lea     rcx, [rbp+7A0h+var_3B0]; this
0x1800249e4  call    ??0CTpRequestMessage@@QEAA@XZ; CTpRequestMessage::CTpRequestMessage(void)
0x1800249e9  nop
0x1800249ea  mov     [rbp+7A0h+var_780], rsi
0x1800249ee  lea     rcx, [rbp+7A0h+var_778]
0x1800249f2  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(void)
0x1800249f7  nop
0x1800249f8  lea     rcx, [rbp+7A0h+var_820]
0x1800249fc  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(void)
0x180024a01  nop
0x180024a02  lea     rcx, [rbp+7A0h+var_740]; void *
0x180024a06  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180024a0b  nop
0x180024a0c  lea     rcx, [rbp+7A0h+var_800]; void *
0x180024a10  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180024a15  nop
0x180024a16  xor     edi, edi
0x180024a18  mov     [rbp+7A0h+arg_18], rdi
0x180024a1f  mov     dword ptr [rbp+7A0h+arg_8], edi
0x180024a25  lea     rcx, [rbp+7A0h+lpMem]; void *
0x180024a29  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180024a2e  nop
0x180024a2f  mov     [rbp+7A0h+arg_10], 2
0x180024a39  mov     [rbp+7A0h+var_808], rdi
0x180024a3d  mov     r8, [r15+28h]; void *
0x180024a41  mov     rdx, r14; struct CReport *
0x180024a44  mov     rcx, r15; this
0x180024a47  call    ?EventTransportBegin@CTransport@@IEAAJPEAVCReport@@PEAX@Z; CTransport::EventTransportBegin(CReport *,void *)
0x180024a4c  mov     ebx, eax
0x180024a4e  test    eax, eax
0x180024a50  js      loc_1800254A1
0x180024a56  lea     rcx, [rbp+7A0h+var_740]; __int64
0x180024a5a  call    ?GetMachineId@MachineId@@SAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; MachineId::GetMachineId(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180024a5f  test    eax, eax
0x180024a61  js      short loc_180024AB7
0x180024a63  mov     rdx, [rbp+7A0h+var_740]; wchar_t *
0x180024a67  lea     rcx, [rbp+7A0h+var_720]; this
0x180024a6e  call    ?SetMachineId@CTpRequestMessage@@QEAAJPEB_W@Z; CTpRequestMessage::SetMachineId(wchar_t const *)
0x180024a73  mov     ebx, eax
0x180024a75  test    eax, eax
0x180024a77  jns     short loc_180024AB7
0x180024a79  lea     rdi, WPP_GLOBAL_Control
0x180024a80  mov     rcx, cs:WPP_GLOBAL_Control
0x180024a87  cmp     rcx, rdi
0x180024a8a  jz      loc_1800254A1
0x180024a90  test    byte ptr [rcx+1Ch], 1
0x180024a94  jz      loc_1800254A1
0x180024a9a  mov     edx, 3Bh ; ';'
0x180024a9f  mov     r9d, eax
0x180024aa2  lea     r8, WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids
0x180024aa9  mov     rcx, [rcx+10h]
0x180024aad  call    WPP_SF_d
0x180024ab2  jmp     loc_18002549A
0x180024ab7  mov     rdx, [r15+30h]
0x180024abb  mov     esi, 1790h
0x180024ac0  add     rdx, rsi; struct OsInformation *
0x180024ac3  lea     rcx, [rbp+7A0h+var_700]; this
0x180024aca  call    ?Copy@OsInformation@@QEAAJAEBV1@@Z; OsInformation::Copy(OsInformation const &)
0x180024acf  mov     ebx, eax
0x180024ad1  test    eax, eax
0x180024ad3  jns     short loc_180024AFD
0x180024ad5  lea     rdi, WPP_GLOBAL_Control
0x180024adc  mov     rcx, cs:WPP_GLOBAL_Control
0x180024ae3  cmp     rcx, rdi
0x180024ae6  jz      loc_18002549A
0x180024aec  test    byte ptr [rcx+1Ch], 1
0x180024af0  jz      loc_18002549A
0x180024af6  mov     edx, 3Ch ; '<'
0x180024afb  jmp     short loc_180024A9F
0x180024afd  mov     rdx, [r15+30h]
0x180024b01  add     rdx, rsi; struct OsInformation *
0x180024b04  lea     rcx, [rbp+7A0h+var_390]; this
0x180024b0b  call    ?Copy@OsInformation@@QEAAJAEBV1@@Z; OsInformation::Copy(OsInformation const &)
0x180024b10  mov     ebx, eax
0x180024b12  test    eax, eax
0x180024b14  jns     short loc_180024B41
0x180024b16  lea     rdi, WPP_GLOBAL_Control
0x180024b1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180024b24  cmp     rcx, rdi
0x180024b27  jz      loc_18002549A
0x180024b2d  test    byte ptr [rcx+1Ch], 1
0x180024b31  jz      loc_18002549A
0x180024b37  mov     edx, 3Dh ; '='
0x180024b3c  jmp     loc_180024A9F
0x180024b41  mov     rdx, [r15+30h]
0x180024b45  lea     r9, [rdx+0CAD0h]
0x180024b4c  mov     r8d, [rdx+0CACCh]
0x180024b53  mov     edx, [rdx+0CAC8h]
0x180024b59  lea     rcx, [rbp+7A0h+var_720]
0x180024b60  call    ?SetCommercialInfo@CTpRequestMessage@@QEAAJHHAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CTpRequestMessage::SetCommercialInfo(int,int,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &)
0x180024b65  mov     ebx, eax
0x180024b67  test    eax, eax
0x180024b69  jns     short loc_180024BA9
0x180024b6b  lea     rdi, WPP_GLOBAL_Control
0x180024b72  mov     rcx, cs:WPP_GLOBAL_Control
0x180024b79  cmp     rcx, rdi
0x180024b7c  jz      loc_18002549A
0x180024b82  test    byte ptr [rcx+1Ch], 1
0x180024b86  jz      loc_18002549A
0x180024b8c  mov     edx, 3Eh ; '>'
0x180024b91  mov     r9d, eax
0x180024b94  lea     r8, WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids
0x180024b9b  mov     rcx, [rcx+10h]
0x180024b9f  call    WPP_SF_d
0x180024ba4  jmp     loc_18002549A
0x180024ba9  mov     rdx, [r15+30h]
0x180024bad  lea     r9, [rdx+0CAD0h]
0x180024bb4  mov     r8d, [rdx+0CACCh]
0x180024bbb  mov     edx, [rdx+0CAC8h]
0x180024bc1  lea     rcx, [rbp+7A0h+var_3B0]
0x180024bc8  call    ?SetCommercialInfo@CTpRequestMessage@@QEAAJHHAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CTpRequestMessage::SetCommercialInfo(int,int,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &)
0x180024bcd  mov     ebx, eax
0x180024bcf  test    eax, eax
0x180024bd1  jns     short loc_180024BFB
0x180024bd3  lea     rdi, WPP_GLOBAL_Control
0x180024bda  mov     rcx, cs:WPP_GLOBAL_Control
0x180024be1  cmp     rcx, rdi
0x180024be4  jz      loc_18002549A
0x180024bea  test    byte ptr [rcx+1Ch], 1
0x180024bee  jz      loc_18002549A
0x180024bf4  mov     edx, 3Fh ; '?'
0x180024bf9  jmp     short loc_180024B91
0x180024bfb  lea     r12, [r14+8]
0x180024bff  mov     r13d, edi
0x180024c02  mov     [rbp+7A0h+arg_0], edi
0x180024c08  lea     rcx, [r15+50h]; this
0x180024c0c  lea     rdx, aWatson_0; "watson"
0x180024c13  call    ?StartSession@CTpLogger@@QEAAJPEB_W@Z; CTpLogger::StartSession(wchar_t const *)
0x180024c18  lea     rdi, WPP_GLOBAL_Control
0x180024c1f  lea     rsi, WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids
0x180024c26  cmp     [r15+38h], r13d
0x180024c2a  jnz     loc_180025073
0x180024c30  lea     rdx, [rbp+7A0h+var_720]; this
0x180024c37  mov     rcx, r14; struct CReport *
0x180024c3a  call    ?PrepareEventRequest@CWatsonTpTransport@@CAJPEAVCReport@@PEAVCTpRequestMessage@@@Z; CWatsonTpTransport::PrepareEventRequest(CReport *,CTpRequestMessage *)
0x180024c3f  mov     ebx, eax
0x180024c41  test    eax, eax
0x180024c43  jns     short loc_180024C77
0x180024c45  or      dword ptr [r14+1748h], 60h
0x180024c4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180024c54  cmp     rcx, rdi
0x180024c57  jz      loc_18002549A
0x180024c5d  test    byte ptr [rcx+1Ch], 1
0x180024c61  jz      loc_18002549A
0x180024c67  mov     edx, 40h ; '@'
0x180024c6c  mov     r9d, eax
0x180024c6f  mov     r8, rsi
0x180024c72  jmp     loc_180024B9B
0x180024c77  mov     rdx, [r15+28h]
0x180024c7b  lea     rcx, [rbp+7A0h+lpMem]
0x180024c7f  call    ?GetDeviceTicketHeader@CTransport@@KAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAX@Z; CTransport::GetDeviceTicketHeader(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,void *)
0x180024c84  mov     ebx, eax
0x180024c86  test    eax, eax
0x180024c88  jns     short loc_180024CB0
0x180024c8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180024c91  cmp     rcx, rdi
0x180024c94  jz      loc_18002549A
0x180024c9a  mov     eax, 2
0x180024c9f  test    [rcx+1Ch], al
0x180024ca2  jz      loc_18002549A
0x180024ca8  lea     edx, [rax+3Fh]
0x180024cab  mov     r9d, ebx
0x180024cae  jmp     short loc_180024C6F
0x180024cb0  mov     rbx, [r14+0CB58h]
0x180024cb7  test    rbx, rbx
0x180024cba  jz      short loc_180024CCE
0x180024cbc  mov     rcx, rbx; hToken
0x180024cbf  call    cs:__imp_ImpersonateLoggedOnUser
0x180024cc5  mov     r13d, eax
0x180024cc8  mov     [rbp+7A0h+arg_0], eax
0x180024cce  mov     r8, [rbp+7A0h+lpMem]
0x180024cd2  mov     rcx, r15
0x180024cd5  lea     rdx, [r15+20h]
0x180024cd9  neg     rcx
0x180024cdc  sbb     r9, r9
0x180024cdf  and     r9, rdx
0x180024ce2  mov     ecx, [r14+0CB54h]
0x180024ce9  mov     [rsp+8A0h+var_830], ecx; int
0x180024ced  mov     [rsp+8A0h+var_838], 0; __int64
0x180024cf6  mov     [rsp+8A0h+var_840], r8; __int64
0x180024cfb  mov     qword ptr [rsp+8A0h+var_848], 0; int
0x180024d04  lea     rax, aS1event; "s1event"
0x180024d0b  mov     [rsp+8A0h+var_850], rax; __int64
0x180024d10  lea     rax, [r15+50h]
0x180024d14  mov     [rsp+8A0h+var_858], rax; __int64
0x180024d19  mov     rax, [r15+28h]
0x180024d1d  mov     [rsp+8A0h+var_860], rax; __int64
0x180024d22  mov     [rsp+8A0h+var_868], rbx; __int64
0x180024d27  mov     [rsp+8A0h+var_870], 0; int
0x180024d30  mov     dword ptr [rsp+8A0h+var_878], 0; int
0x180024d38  mov     [rsp+8A0h+var_880], r9; struct ITpCallbacks *
0x180024d3d  lea     r9, off_1800AE818
0x180024d44  lea     r8, [rbp+7A0h+var_760]
0x180024d48  xor     edx, edx
0x180024d4a  lea     rcx, [rbp+7A0h+var_720]; this
0x180024d51  call    ?DoExchange@CTpTransport@@SAJPEAVCTpRequestMessage@@PEAUIWerByteStream@@PEAVCTpResponseMessage@@PEBQ6AJPEB_WPEAV?$unique_ptr@VITpCommand@@U?$default_delete@VITpCommand@@@utl@@@utl@@@ZPEAUITpCallbacks@@K3PEAX7PEAVCTpLogger@@3PEAUISequentialStream@@3PEAUWINHTTP_TIMEOUTS@@K@Z; CTpTransport::DoExchange(CTpRequestMessage *,IWerByteStream *,CTpResponseMessage *,long (*const *)(wchar_t const *,utl::unique_ptr<ITpCommand,utl::default_delete<ITpCommand>> *),ITpCallbacks *,ulong,wchar_t const *,void *,void *,CTpLogger *,wchar_t const *,ISequentialStream *,wchar_t const *,WINHTTP_TIMEOUTS *,ulong)
0x180024d56  mov     ebx, eax
0x180024d58  test    r13d, r13d
0x180024d5b  jz      short loc_180024D6D
0x180024d5d  call    cs:__imp_RevertToSelf
0x180024d63  mov     [rbp+7A0h+arg_0], 0
0x180024d6d  test    ebx, ebx
0x180024d6f  jns     short loc_180024D9D
0x180024d71  or      dword ptr [r14+1748h], 60h
0x180024d79  mov     rcx, cs:WPP_GLOBAL_Control
0x180024d80  cmp     rcx, rdi
0x180024d83  jz      loc_18002549A
0x180024d89  test    byte ptr [rcx+1Ch], 1
0x180024d8d  jz      loc_18002549A
0x180024d93  mov     edx, 42h ; 'B'
0x180024d98  jmp     loc_180024CAB
0x180024d9d  lea     r8, a1; "1"
0x180024da4  lea     rdx, aTransportDones; "Transport.DoneStage1"
0x180024dab  mov     rcx, r14; this
0x180024dae  call    ?AddStateParam@CReport@@QEAAJPEB_W0@Z; CReport::AddStateParam(wchar_t const *,wchar_t const *)
0x180024db3  test    eax, eax
0x180024db5  jns     short loc_180024DDD
0x180024db7  mov     rcx, cs:WPP_GLOBAL_Control
0x180024dbe  cmp     rcx, rdi
0x180024dc1  jz      short loc_180024DDD
0x180024dc3  test    byte ptr [rcx+1Ch], 2
0x180024dc7  jz      short loc_180024DDD
0x180024dc9  mov     edx, 43h ; 'C'
0x180024dce  mov     r9d, eax
0x180024dd1  mov     r8, rsi
0x180024dd4  mov     rcx, [rcx+10h]
0x180024dd8  call    WPP_SF_d
0x180024ddd  lea     rax, [rbp+7A0h+arg_8]
0x180024de4  mov     [rsp+8A0h+var_878], rax; __int64
0x180024de9  lea     rax, [rbp+7A0h+arg_18]
0x180024df0  mov     [rsp+8A0h+var_880], rax; __int64
0x180024df5  lea     r9, [rbp+7A0h+var_800]
0x180024df9  lea     r8, [rbp+7A0h+var_820]; struct CDataRequest *
0x180024dfd  mov     rdx, r12; CResponse *
0x180024e00  lea     rcx, [rbp+7A0h+var_760]; this
0x180024e04  call    ?ParseEventResponse@CWatsonTpTransport@@CAJPEAVCTpResponseMessage@@PEAVCResponse@@PEAVCDataRequest@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEA_KPEAH@Z; CWatsonTpTransport::ParseEventResponse(CTpResponseMessage *,CResponse *,CDataRequest *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,unsigned __int64 *,int *)
0x180024e09  mov     ebx, eax
0x180024e0b  test    eax, eax
0x180024e0d  jns     short loc_180024E3B
0x180024e0f  or      dword ptr [r14+1748h], 60h
0x180024e17  mov     rcx, cs:WPP_GLOBAL_Control
0x180024e1e  cmp     rcx, rdi
0x180024e21  jz      loc_18002549A
0x180024e27  test    byte ptr [rcx+1Ch], 1
0x180024e2b  jz      loc_18002549A
0x180024e31  mov     edx, 44h ; 'D'
0x180024e36  jmp     loc_180024C6C
0x180024e3b  call    IsXerHitRequestResponsePresent
0x180024e40  test    al, al
0x180024e42  jz      short loc_180024E4E
0x180024e44  mov     rcx, [r12]
0x180024e48  call    cs:__imp_XerHitRequestResponse
0x180024e4e  mov     rdx, r12; struct CResponse *
0x180024e51  lea     rcx, [rbp+7A0h+var_820]; this
0x180024e55  call    ?SetLegacyTokensFromCollectCommand@CWatsonTpTransport@@CAXPEBVCDataRequest@@PEAVCResponse@@@Z; CWatsonTpTransport::SetLegacyTokensFromCollectCommand(CDataRequest const *,CResponse *)
0x180024e5a  cmp     dword ptr [r14+0B658h], 2
0x180024e62  jnz     short loc_180024E96
0x180024e64  mov     rcx, cs:WPP_GLOBAL_Control
0x180024e6b  cmp     rcx, rdi
0x180024e6e  jz      short loc_180024E87
0x180024e70  test    byte ptr [rcx+1Ch], 4
0x180024e74  jz      short loc_180024E87
0x180024e76  mov     edx, 45h ; 'E'
0x180024e7b  mov     r8, rsi
0x180024e7e  mov     rcx, [rcx+10h]
0x180024e82  call    WPP_SF_
0x180024e87  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180024e8c  mov     ebx, 80004001h
0x180024e91  jmp     loc_18002549A
0x180024e96  lea     rbx, [r14+19D8h]
0x180024e9d  cmp     dword ptr [r12+164h], 0
0x180024ea6  jz      short loc_180024ECF
0x180024ea8  bts     dword ptr [rbx], 8
0x180024eac  mov     rcx, cs:WPP_GLOBAL_Control
0x180024eb3  cmp     rcx, rdi
0x180024eb6  jz      short loc_180024ECF
0x180024eb8  test    byte ptr [rcx+1Ch], 4
0x180024ebc  jz      short loc_180024ECF
0x180024ebe  mov     edx, 46h ; 'F'
0x180024ec3  mov     r8, rsi
  ... truncated ...
```
