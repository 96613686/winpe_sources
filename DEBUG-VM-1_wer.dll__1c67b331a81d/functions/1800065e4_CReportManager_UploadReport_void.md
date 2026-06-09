# CReportManager::UploadReport(void)

- ea: `0x1800065e4`
- end: `0x180006c2d`
- name: `?UploadReport@CReportManager@@AEAAJXZ`
- size: `1609`
- prototype: `__int64 __fastcall(CReportManager *__hidden this)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003285c`

## callees

- `0x180004bb4`
- `0x18000647c`
- `0x180006510`
- `0x1800065e4`
- `0x18000716c`
- `0x180007e10`
- `0x180008388`
- `0x180009ad4`
- `0x18000bc10`
- `0x18000dad0`
- `0x18001b280`
- `0x18001e870`
- `0x18001fe24`
- `0x1800275e8`
- `0x18002c1d0`
- `0x180035054`
- `0x18003afa0`
- `0x18003bf14`
- `0x180046fcc`
- `0x1800499e4`
- `0x18004bc2c`
- `0x180051fa4`
- `0x1800699b0`
- `0x1800720ec`
- `0x180072c2c`
- `0x1800ad010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800068a9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800068a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800068ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800068ea`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800066ac`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800066ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800066c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800066c3`
- `UMPDC!Pdcv2ActivationClientUnregister` at `0x18000688b`
- `UMPDC!Pdcv2ActivationClientUnregister` at `0x18000688b`
- `UMPDC!Pdcv2ActivationClientDeactivate` at `0x180006871`
- `UMPDC!Pdcv2ActivationClientDeactivate` at `0x180006871`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CReportManager::UploadReport(CReportManager *this)
{
  __int64 v2; // rbx
  int v3; // r14d
  __int64 v4; // rcx
  DWORD LastError; // eax
  int v6; // eax
  signed int v7; // ebx
  unsigned int v8; // r14d
  CReport *v9; // rcx
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  unsigned int v15; // edx
  int v16; // eax
  __int64 v17; // rcx
  int v18; // r9d
  unsigned int v19; // ebx
  wchar_t *v20; // rcx
  wchar_t *v22; // rcx
  __int64 v23; // r9
  int v24; // r14d
  CReport *v25; // rcx
  __int64 v26; // rcx
  int WatsonCab; // eax
  wchar_t *v28; // rcx
  __int64 v29; // rdx
  CReport *v30; // rcx
  int v31; // eax
  int StorePath; // eax
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // r8
  wchar_t *v36; // rbx
  int v37; // eax
  HANDLE hObject[2]; // [rsp+30h] [rbp-69h] BYREF
  __int64 v39; // [rsp+40h] [rbp-59h]
  void *v40[2]; // [rsp+48h] [rbp-51h] BYREF
  __int64 v41; // [rsp+58h] [rbp-41h] BYREF
  __int64 v42; // [rsp+60h] [rbp-39h]
  int v43; // [rsp+70h] [rbp-29h]
  char v44; // [rsp+78h] [rbp-21h]
  __int128 v45; // [rsp+80h] [rbp-19h] BYREF
  __int64 v46; // [rsp+90h] [rbp-9h]
  _BYTE v47[32]; // [rsp+98h] [rbp-1h] BYREF
  int v48; // [rsp+B8h] [rbp+1Fh]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+100h] [rbp+67h] BYREF
  wchar_t *v50; // [rsp+108h] [rbp+6Fh] BYREF

  *(_OWORD *)v40 = 0;
  SystemTimeAsFileTime = 0;
  v2 = *((_QWORD *)this + 1);
  v3 = *(_DWORD *)(v2 + 6616);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v47);
  v45 = 0;
  v46 = 0;
  v48 = 0;
  v50 = 0;
  if ( v2 && (v4 = *((_QWORD *)this + 33)) != 0 )
  {
    *(_QWORD *)&v45 = v2;
    *((_QWORD *)&v45 + 1) = *(_QWORD *)this;
    v46 = v4;
    CDataCollection::AddReportMetadata((CDataCollection *)&v45);
  }
  else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids);
  }
  hObject[0] = 0;
  v39 = 0;
  hObject[1] = CreateEventW(0, 0, 0, 0);
  if ( (unsigned __int64)hObject[1] + 1 <= 1 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids);
    LastError = GetLastError();
    v6 = ERROR_HR_FROM_WIN32(LastError);
    goto LABEL_12;
  }
  v8 = v3 & 0x2000000;
  hObject[0] = this;
  v9 = (CReport *)*((_QWORD *)this + 1);
  if ( v8 )
  {
    if ( (unsigned int)CReport::GetUploadShouldBypassPowerThrottling(v9) || !(unsigned int)WerpIsOnBattery() )
    {
      if ( (unsigned int)CReport::GetUploadShouldBypassNetworkCostThrottling(*((CReport **)this + 1))
        || !(unsigned int)UtilIsNetworkRestricted() )
      {
        v11 = 1;
        goto LABEL_29;
      }
      *((_DWORD *)this + 34) = 3;
      *(_DWORD *)(*((_QWORD *)this + 1) + 5960LL) |= 0x8000u;
      if ( *(_DWORD *)(*((_QWORD *)this + 1) + 46680LL) != 1 )
        goto LABEL_22;
    }
    else
    {
      *((_DWORD *)this + 34) = 3;
      *(_DWORD *)(*((_QWORD *)this + 1) + 5960LL) |= 0x4000u;
      if ( *(_DWORD *)(*((_QWORD *)this + 1) + 46680LL) != 1 )
LABEL_22:
        MicrosoftTelemetryAssertTriggeredNoArgs(v13, v12, v14);
    }
    v7 = 1769476;
    goto LABEL_53;
  }
  v10 = CReport::RemoveFilesByFlagMask(v9, 1u);
  if ( v10 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids,
      (unsigned int)v10);
  v11 = 0;
LABEL_29:
  *((_DWORD *)this + 34) = v11;
  v15 = 120;
  if ( *(_DWORD *)(*((_QWORD *)this + 1) + 5872LL) != 4 )
    v15 = 60;
  PdcNetworkActivation::PdcNetworkActivation((PdcNetworkActivation *)&v41, v15);
  v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 (__fastcall *)(struct TRANSPORT_CALLBACK_PARAM *, void *), HANDLE *))(**((_QWORD **)this + 2) + 16LL))(
          *((_QWORD *)this + 2),
          *((_QWORD *)this + 1),
          CReportManager::Static_TransportCallback,
          hObject);
  v7 = v16;
  if ( v16 < 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids,
        (unsigned int)v16);
    if ( v41 )
    {
      if ( v44 && (int)Pdcv2ActivationClientDeactivate(v42) >= 0 )
      {
        v42 = 0;
        v43 = 0;
        v44 = 0;
      }
      Pdcv2ActivationClientUnregister(v41);
    }
    goto LABEL_53;
  }
  *(_DWORD *)(*((_QWORD *)this + 1) + 6624LL) = 2;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v17 = *((_QWORD *)this + 1);
  *(struct _FILETIME *)(v17 + 600) = SystemTimeAsFileTime;
  v40[0] = *((void **)this + 33);
  v40[1] = hObject[1];
  v19 = UtilMsgWaitForMultipleObjects((const wchar_t *)v17, 2u, v40, v18, v8);
  if ( v19 == -1 )
    GetLastError();
  PdcNetworkActivation::~PdcNetworkActivation((PdcNetworkActivation *)&v41);
  if ( !v19 )
    goto LABEL_47;
  if ( v19 != 1 )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control )
    {
LABEL_51:
      CReportManager::HandleCancellation(this);
      v7 = -2145681407;
      if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 56LL))(*((_QWORD *)this + 3)) == 5 )
        v7 = 1769472;
      goto LABEL_53;
    }
    if ( (WPP_GLOBAL_Control[14] & 4) == 0 )
    {
LABEL_48:
      if ( v20 != (wchar_t *)&WPP_GLOBAL_Control && (v20[14] & 4) != 0 )
        WPP_SF_(*((_QWORD *)v20 + 2), 23, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids);
      goto LABEL_51;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids, v19);
LABEL_47:
    v20 = WPP_GLOBAL_Control;
    goto LABEL_48;
  }
  v22 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids);
    v22 = WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)this + 34) == 3 || (v23 = *((unsigned int *)this + 28), (_DWORD)v23 == 1769476) )
  {
    v24 = 0;
    *((_DWORD *)this + 58) = 5;
    v25 = (CReport *)*((_QWORD *)this + 1);
    if ( !*((_DWORD *)v25 + 11670) && (unsigned int)CReport::ContainsConfidentialFiles(v25)
      || (unsigned __int8)IsXerTransportEventUploadCompletePresent(v25)
      && (v26 = *((_QWORD *)this + 1), *(_DWORD *)(v26 + 6024))
      && CRegSetting::GetDwordData((CRegSetting *)(v26 + 51680))
      || (WatsonCab = CReportManager::CreateWatsonCab(this, 0), WatsonCab >= 0) )
    {
      WatsonCab = CReportManager::SubmitReportToQueue(this, 0);
      if ( WatsonCab == 1769477 )
      {
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids, 1769477);
        goto LABEL_80;
      }
      if ( WatsonCab >= 0 )
        goto LABEL_105;
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      {
LABEL_89:
        v30 = (CReport *)*((_QWORD *)this + 1);
        if ( *((_DWORD *)v30 + 11670) )
        {
          StorePath = CReport::GetStorePath(v30, (const wchar_t **)&v50);
          v36 = v50;
          if ( StorePath < 0 || !v50 )
            MicrosoftTelemetryAssertTriggeredNoArgs(v34, v33, v35);
          v37 = CReport::SaveTemporaryAttachedFiles(*((CReport **)this + 1), v36);
          if ( v37 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              30,
              WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids,
              (unsigned int)v37);
          goto LABEL_105;
        }
        v31 = CReportManager::SubmitReportToQueue(this, 2u);
        v7 = v31;
        if ( v31 != 1769477 )
        {
          if ( v31 < 0 )
          {
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                29,
                WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids,
                (unsigned int)v31);
            goto LABEL_53;
          }
LABEL_105:
          v7 = v24 + 1769476;
          goto LABEL_53;
        }
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids);
LABEL_80:
        v24 = 1;
        goto LABEL_105;
      }
      v29 = 26;
    }
    else
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_89;
      v29 = 27;
    }
    WPP_SF_d(*((_QWORD *)v28 + 2), v29, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids, (unsigned int)WatsonCab);
    goto LABEL_89;
  }
  v6 = 1769483;
  if ( (_DWORD)v23 == 1769483 || (v7 = *((_DWORD *)this + 29), v7 == 1769483) )
  {
LABEL_12:
    v7 = v6;
    goto LABEL_53;
  }
  if ( (int)v23 < 0 )
  {
    v7 = -2145681407;
    if ( (_DWORD)v23 != -2145681407 )
    {
      if ( v22 != (wchar_t *)&WPP_GLOBAL_Control && (v22[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)v22 + 2), 31, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids, v23);
      v7 = -2145681406;
    }
  }
  else if ( v7 != -2147024323 && v7 != -2147024865 )
  {
    v7 = ((v7 >> 31) & 0xFFFFFFF5) + 1769484;
  }
LABEL_53:
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hObject[1]);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v47);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800065e4  mov     [rsp-8+arg_10], rbx
0x1800065e9  push    rbp
0x1800065ea  push    rsi
0x1800065eb  push    rdi
0x1800065ec  push    r12
0x1800065ee  push    r13
0x1800065f0  push    r14
0x1800065f2  push    r15
0x1800065f4  lea     rbp, [rsp-27h]
0x1800065f9  sub     rsp, 0C0h
0x180006600  mov     rdi, rcx
0x180006603  xorps   xmm0, xmm0
0x180006606  movups  xmmword ptr [rbp+57h+var_A8], xmm0
0x18000660a  xor     r15d, r15d
0x18000660d  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r15
0x180006611  mov     rbx, [rcx+8]
0x180006615  mov     r14d, [rbx+19D8h]
0x18000661c  lea     rcx, [rbp+57h+var_58]; void *
0x180006620  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180006625  xorps   xmm0, xmm0
0x180006628  movdqa  [rbp+57h+var_70], xmm0
0x18000662d  mov     [rbp+57h+var_60], r15
0x180006631  mov     [rbp+57h+var_38], r15d
0x180006635  mov     [rbp+57h+arg_8], r15
0x180006639  lea     r12d, [r15+1]
0x18000663d  lea     r13, WPP_GLOBAL_Control
0x180006644  test    rbx, rbx
0x180006647  jz      short loc_18000666F
0x180006649  mov     rcx, [rdi+108h]
0x180006650  test    rcx, rcx
0x180006653  jz      short loc_18000666F
0x180006655  mov     qword ptr [rbp+57h+var_70], rbx
0x180006659  mov     rax, [rdi]
0x18000665c  mov     qword ptr [rbp+57h+var_70+8], rax
0x180006660  mov     [rbp+57h+var_60], rcx
0x180006664  lea     rcx, [rbp+57h+var_70]; this
0x180006668  call    ?AddReportMetadata@CDataCollection@@QEAAJXZ; CDataCollection::AddReportMetadata(void)
0x18000666d  jmp     short loc_180006696
0x18000666f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006676  cmp     rcx, r13
0x180006679  jz      short loc_180006696
0x18000667b  test    [rcx+1Ch], r12b
0x18000667f  jz      short loc_180006696
0x180006681  mov     edx, 83h
0x180006686  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18000668d  mov     rcx, [rcx+10h]
0x180006691  call    WPP_SF_
0x180006696  xorps   xmm0, xmm0
0x180006699  movdqu  xmmword ptr [rbp+57h+hObject], xmm0
0x18000669e  mov     [rbp+57h+var_B0], r15
0x1800066a2  xor     r9d, r9d; lpName
0x1800066a5  xor     r8d, r8d; bInitialState
0x1800066a8  xor     edx, edx; bManualReset
0x1800066aa  xor     ecx, ecx; lpEventAttributes
0x1800066ac  call    cs:__imp_CreateEventW
0x1800066b2  mov     rcx, [rbp+57h+hObject+8]; hObject
0x1800066b6  mov     [rbp+57h+hObject+8], rax
0x1800066ba  lea     rdx, [rcx+1]
0x1800066be  cmp     rdx, r12
0x1800066c1  jbe     short loc_1800066CD
0x1800066c3  call    cs:__imp_CloseHandle
0x1800066c9  mov     rax, [rbp+57h+hObject+8]
0x1800066cd  inc     rax
0x1800066d0  cmp     rax, r12
0x1800066d3  ja      short loc_180006710
0x1800066d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066dc  cmp     rcx, r13
0x1800066df  jz      short loc_1800066FC
0x1800066e1  test    [rcx+1Ch], r12b
0x1800066e5  jz      short loc_1800066FC
0x1800066e7  mov     edx, 13h
0x1800066ec  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x1800066f3  mov     rcx, [rcx+10h]
0x1800066f7  call    WPP_SF_
0x1800066fc  call    cs:__imp_GetLastError
0x180006702  mov     ecx, eax; unsigned int
0x180006704  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180006709  mov     ebx, eax
0x18000670b  jmp     loc_180006978
0x180006710  lea     rsi, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x180006717  and     r14d, 2000000h
0x18000671e  mov     [rbp+57h+hObject], rdi
0x180006722  mov     rcx, [rdi+8]; this
0x180006726  jnz     short loc_18000675F
0x180006728  call    ?RemoveFilesByFlagMask@CReport@@QEAAJK@Z; CReport::RemoveFilesByFlagMask(ulong)
0x18000672d  test    eax, eax
0x18000672f  jns     short loc_180006757
0x180006731  mov     rcx, cs:WPP_GLOBAL_Control
0x180006738  cmp     rcx, r13
0x18000673b  jz      short loc_180006757
0x18000673d  test    [rcx+1Ch], r12b
0x180006741  jz      short loc_180006757
0x180006743  mov     edx, 14h
0x180006748  mov     r9d, eax
0x18000674b  mov     r8, rsi
0x18000674e  mov     rcx, [rcx+10h]
0x180006752  call    WPP_SF_d
0x180006757  mov     eax, r15d
0x18000675a  jmp     loc_1800067E6
0x18000675f  call    ?GetUploadShouldBypassPowerThrottling@CReport@@QEBAHXZ; CReport::GetUploadShouldBypassPowerThrottling(void)
0x180006764  test    eax, eax
0x180006766  jnz     short loc_1800067A3
0x180006768  call    WerpIsOnBattery
0x18000676d  test    eax, eax
0x18000676f  jz      short loc_1800067A3
0x180006771  mov     dword ptr [rdi+88h], 3
0x18000677b  mov     rax, [rdi+8]
0x18000677f  bts     dword ptr [rax+1748h], 0Eh
0x180006787  mov     rax, [rdi+8]
0x18000678b  cmp     [rax+0B658h], r12d
0x180006792  jz      short loc_180006799
0x180006794  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180006799  mov     ebx, 1B0004h
0x18000679e  jmp     loc_180006978
0x1800067a3  mov     rcx, [rdi+8]; this
0x1800067a7  call    ?GetUploadShouldBypassNetworkCostThrottling@CReport@@QEBAHXZ; CReport::GetUploadShouldBypassNetworkCostThrottling(void)
0x1800067ac  test    eax, eax
0x1800067ae  jnz     short loc_1800067E3
0x1800067b0  call    ?UtilIsNetworkRestricted@@YAHXZ; UtilIsNetworkRestricted(void)
0x1800067b5  test    eax, eax
0x1800067b7  jz      short loc_1800067E3
0x1800067b9  mov     dword ptr [rdi+88h], 3
0x1800067c3  mov     rax, [rdi+8]
0x1800067c7  bts     dword ptr [rax+1748h], 0Fh
0x1800067cf  mov     rax, [rdi+8]
0x1800067d3  cmp     [rax+0B658h], r12d
0x1800067da  jz      short loc_180006799
0x1800067dc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800067e1  jmp     short loc_180006799
0x1800067e3  mov     eax, r12d
0x1800067e6  mov     [rdi+88h], eax
0x1800067ec  mov     rax, [rdi+8]
0x1800067f0  mov     edx, 78h ; 'x'
0x1800067f5  lea     ecx, [rdx-3Ch]
0x1800067f8  cmp     dword ptr [rax+16F0h], 4
0x1800067ff  cmovnz  edx, ecx; unsigned int
0x180006802  lea     rcx, [rbp+57h+var_98]; this
0x180006806  call    ??0PdcNetworkActivation@@QEAA@K@Z; PdcNetworkActivation::PdcNetworkActivation(ulong)
0x18000680b  nop
0x18000680c  mov     rcx, [rdi+10h]
0x180006810  mov     rax, [rcx]
0x180006813  mov     [rsp+0F0h+var_D0], r14d; unsigned int
0x180006818  lea     r9, [rbp+57h+hObject]
0x18000681c  lea     r8, ?Static_TransportCallback@CReportManager@@SAJPEAUTRANSPORT_CALLBACK_PARAM@@PEAX@Z; CReportManager::Static_TransportCallback(TRANSPORT_CALLBACK_PARAM *,void *)
0x180006823  mov     rdx, [rdi+8]
0x180006827  mov     rax, [rax+10h]
0x18000682b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006830  mov     ebx, eax
0x180006832  test    eax, eax
0x180006834  jns     short loc_180006896
0x180006836  mov     rcx, cs:WPP_GLOBAL_Control
0x18000683d  cmp     rcx, r13
0x180006840  jz      short loc_18000685D
0x180006842  test    [rcx+1Ch], r12b
0x180006846  jz      short loc_18000685D
0x180006848  mov     edx, 15h
0x18000684d  mov     r9d, eax
0x180006850  mov     r8, rsi
0x180006853  mov     rcx, [rcx+10h]
0x180006857  call    WPP_SF_d
0x18000685c  nop
0x18000685d  cmp     [rbp+57h+var_98], r15
0x180006861  jz      loc_180006978
0x180006867  cmp     [rbp+57h+var_78], r15b
0x18000686b  jz      short loc_180006887
0x18000686d  mov     rcx, [rbp+57h+var_90]
0x180006871  call    cs:__imp_Pdcv2ActivationClientDeactivate
0x180006877  test    eax, eax
0x180006879  js      short loc_180006887
0x18000687b  mov     [rbp+57h+var_90], r15
0x18000687f  mov     [rbp+57h+var_80], r15d
0x180006883  mov     [rbp+57h+var_78], r15b
0x180006887  mov     rcx, [rbp+57h+var_98]
0x18000688b  call    cs:__imp_Pdcv2ActivationClientUnregister
0x180006891  jmp     loc_180006978
0x180006896  mov     rax, [rdi+8]
0x18000689a  mov     ebx, 2
0x18000689f  mov     [rax+19E0h], ebx
0x1800068a5  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800068a9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800068af  mov     rcx, [rdi+8]; wchar_t *
0x1800068b3  mov     eax, [rbp+57h+SystemTimeAsFileTime.dwHighDateTime]
0x1800068b6  mov     [rcx+25Ch], eax
0x1800068bc  mov     eax, [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x1800068bf  mov     [rcx+258h], eax
0x1800068c5  mov     rax, [rdi+108h]
0x1800068cc  mov     [rbp+57h+var_A8], rax
0x1800068d0  mov     rax, [rbp+57h+hObject+8]
0x1800068d4  mov     [rbp+57h+var_A8+8], rax
0x1800068d8  lea     r8, [rbp+57h+var_A8]; void **
0x1800068dc  mov     edx, ebx; unsigned int
0x1800068de  call    ?UtilMsgWaitForMultipleObjects@@YAKPEB_WKQEAPEAXHK@Z; UtilMsgWaitForMultipleObjects(wchar_t const *,ulong,void * * const,int,ulong)
0x1800068e3  mov     ebx, eax
0x1800068e5  cmp     eax, 0FFFFFFFFh
0x1800068e8  jnz     short loc_1800068F1
0x1800068ea  call    cs:__imp_GetLastError
0x1800068f0  nop
0x1800068f1  lea     rcx, [rbp+57h+var_98]; this
0x1800068f5  call    ??1PdcNetworkActivation@@QEAA@XZ; PdcNetworkActivation::~PdcNetworkActivation(void)
0x1800068fa  test    ebx, ebx
0x1800068fc  jz      short loc_18000692D
0x1800068fe  cmp     ebx, 1
0x180006901  jz      loc_1800069A8
0x180006907  mov     rcx, cs:WPP_GLOBAL_Control
0x18000690e  cmp     rcx, r13
0x180006911  jz      short loc_180006950
0x180006913  test    byte ptr [rcx+1Ch], 4
0x180006917  jz      short loc_180006934
0x180006919  mov     edx, 16h
0x18000691e  mov     r9d, ebx
0x180006921  mov     r8, rsi
0x180006924  mov     rcx, [rcx+10h]
0x180006928  call    WPP_SF_d
0x18000692d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006934  cmp     rcx, r13
0x180006937  jz      short loc_180006950
0x180006939  test    byte ptr [rcx+1Ch], 4
0x18000693d  jz      short loc_180006950
0x18000693f  mov     edx, 17h
0x180006944  mov     r8, rsi
0x180006947  mov     rcx, [rcx+10h]
0x18000694b  call    WPP_SF_
0x180006950  mov     rcx, rdi; this
0x180006953  call    ?HandleCancellation@CReportManager@@AEAAJXZ; CReportManager::HandleCancellation(void)
0x180006958  mov     rcx, [rdi+18h]
0x18000695c  mov     rax, [rcx]
0x18000695f  mov     rax, [rax+38h]
0x180006963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006968  mov     ebx, 801B8001h
0x18000696d  mov     ecx, 1B0000h
0x180006972  cmp     eax, 5
0x180006975  cmovz   ebx, ecx
0x180006978  lea     rcx, [rbp+57h+hObject+8]
0x18000697c  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180006981  nop
0x180006982  lea     rcx, [rbp+57h+var_58]; void *
0x180006986  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18000698b  mov     eax, ebx
0x18000698d  mov     rbx, [rsp+0F0h+arg_10]
0x180006995  add     rsp, 0C0h
0x18000699c  pop     r15
0x18000699e  pop     r14
0x1800069a0  pop     r13
0x1800069a2  pop     r12
0x1800069a4  pop     rdi
0x1800069a5  pop     rsi
0x1800069a6  pop     rbp
0x1800069a7  retn
0x1800069a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800069af  cmp     rcx, r13
0x1800069b2  jz      short loc_1800069D2
0x1800069b4  test    byte ptr [rcx+1Ch], 4
0x1800069b8  jz      short loc_1800069D2
0x1800069ba  mov     edx, 18h
0x1800069bf  mov     r8, rsi
0x1800069c2  mov     rcx, [rcx+10h]
0x1800069c6  call    WPP_SF_
0x1800069cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800069d2  cmp     dword ptr [rdi+88h], 3
0x1800069d9  jz      loc_180006A66
0x1800069df  mov     r9d, [rdi+70h]
0x1800069e3  mov     ebx, 1B0004h
0x1800069e8  cmp     r9d, ebx
0x1800069eb  jz      short loc_180006A66
0x1800069ed  lea     eax, [rbx+7]
0x1800069f0  cmp     r9d, eax
0x1800069f3  jz      loc_180006709
0x1800069f9  mov     ebx, [rdi+74h]
0x1800069fc  cmp     ebx, eax
0x1800069fe  jz      loc_180006709
0x180006a04  test    r9d, r9d
0x180006a07  js      short loc_180006A32
0x180006a09  cmp     ebx, 8007023Dh
0x180006a0f  jz      loc_180006978
0x180006a15  cmp     ebx, 8007001Fh
0x180006a1b  jz      loc_180006978
0x180006a21  sar     ebx, 1Fh
0x180006a24  and     ebx, 0FFFFFFF5h
0x180006a27  add     ebx, 1B000Ch
0x180006a2d  jmp     loc_180006978
0x180006a32  mov     ebx, 801B8001h
0x180006a37  cmp     r9d, ebx
0x180006a3a  jz      loc_180006978
0x180006a40  cmp     rcx, r13
0x180006a43  jz      short loc_180006A5C
0x180006a45  test    [rcx+1Ch], r12b
0x180006a49  jz      short loc_180006A5C
0x180006a4b  mov     edx, 1Fh
0x180006a50  mov     r8, rsi
0x180006a53  mov     rcx, [rcx+10h]
0x180006a57  call    WPP_SF_d
0x180006a5c  mov     ebx, 801B8002h
0x180006a61  jmp     loc_180006978
0x180006a66  mov     r14d, r15d
0x180006a69  mov     dword ptr [rdi+0E8h], 5
0x180006a73  mov     rcx, [rdi+8]; this
0x180006a77  mov     ebx, 1B0005h
0x180006a7c  cmp     [rcx+0B658h], r15d
0x180006a83  jnz     short loc_180006A8E
0x180006a85  call    ?ContainsConfidentialFiles@CReport@@QEAAHXZ; CReport::ContainsConfidentialFiles(void)
  ... truncated ...
```
