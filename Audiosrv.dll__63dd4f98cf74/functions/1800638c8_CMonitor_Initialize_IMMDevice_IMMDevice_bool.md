# CMonitor::Initialize(IMMDevice *,IMMDevice *,bool &)

- ea: `0x1800638c8`
- end: `0x18006414e`
- name: `?Initialize@CMonitor@@QEAAJPEAUIMMDevice@@0AEA_N@Z`
- size: `2182`
- prototype: `__int64 __fastcall(CMonitor *__hidden this, struct IMMDevice *, struct IMMDevice *, bool *)`
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800635dc`
- `0x18012a2c4`

## callees

- `0x18000ae1c`
- `0x1800364c4`
- `0x18003840c`
- `0x1800638c8`
- `0x180071f50`
- `0x1800b38d4`
- `0x1800cd8d0`
- `0x1800e5330`
- `0x1800e7a64`
- `0x1800e7b40`
- `0x1800e7cc0`
- `0x18012c488`
- `0x18012c5c4`
- `0x18012c604`
- `0x18012cfd8`
- `0x18012da8c`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800639a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800639a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800639f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800639f3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800639e1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800639e1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180063e24`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180063e86`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180063e24`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180063e86`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180063e72`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180063e72`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CMonitor::Initialize(GUID *this, struct IMMDevice *a2, struct IMMDevice *a3, bool *a4)
{
  bool *v4; // r14
  _QWORD *v8; // rcx
  PTP_WORK ThreadpoolWork; // rax
  signed int LastError; // eax
  int v12; // ebx
  unsigned __int8 *Data4; // r12
  GUID *v14; // r13
  int v15; // eax
  void (__fastcall ***v16)(_QWORD, GUID *, __int64 *); // r9
  __int64 v17; // rcx
  __int64 v18; // [rsp+30h] [rbp-59h] BYREF
  __int64 v19; // [rsp+38h] [rbp-51h] BYREF
  bool *v20; // [rsp+40h] [rbp-49h]
  __int64 v21; // [rsp+48h] [rbp-41h] BYREF
  int v22; // [rsp+50h] [rbp-39h] BYREF
  GUID *v23; // [rsp+58h] [rbp-31h] BYREF
  __int64 v24; // [rsp+60h] [rbp-29h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+68h] [rbp-21h] BYREF
  char v26; // [rsp+70h] [rbp-19h]
  __m256i pvar; // [rsp+78h] [rbp-11h] BYREF

  v4 = a4;
  v20 = a4;
  v21 = 0;
  v22 = 0;
  lpCriticalSection = (LPCRITICAL_SECTION)&this[2];
  v26 = 0;
  ATL::CCritSecLock::Lock((ATL::CCritSecLock *)&lpCriticalSection);
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids, this);
    v8 = WPP_GLOBAL_Control;
  }
  if ( !*(_DWORD *)this[4].Data4 || *(_DWORD *)this[4].Data4 == 6 )
  {
    *v4 = 1;
    *(_DWORD *)this[4].Data4 = 1;
    ThreadpoolWork = CreateThreadpoolWork(CMonitor::TerminateMonitorInWorkerThread, this, 0);
    *(_QWORD *)this[12].Data4 = ThreadpoolWork;
    if ( !ThreadpoolWork )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids,
          (unsigned int)v12);
      }
      if ( v12 >= 0 )
        goto LABEL_63;
      goto LABEL_58;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_qq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids,
        this,
        ThreadpoolWork);
    }
    v12 = ((__int64 (__fastcall *)(struct IMMDevice *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
            a2,
            &GUID_1be09788_6894_4089_8586_9a2a6c265ac5,
            &v21);
    if ( v12 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v21 + 24LL))(v21, &v22);
      if ( v12 >= 0 )
      {
        Data4 = this[6].Data4;
        v12 = ((__int64 (__fastcall *)(struct IMMDevice *, GUID *, __int64))a2->lpVtbl->Activate)(
                a2,
                &IID_IAudioClient,
                1);
        if ( v12 >= 0 )
        {
          v14 = this + 10;
          v12 = ((__int64 (__fastcall *)(struct IMMDevice *, GUID *, __int64))a3->lpVtbl->Activate)(
                  a3,
                  &IID_IAudioClient,
                  1);
          if ( v12 >= 0 )
          {
            ATL::CComQIPtr<IAudioClient2,&__s_GUID const _GUID_726778cd_f60a_4eda_82de_e47610cd78aa>::CComQIPtr<IAudioClient2,&__s_GUID const _GUID_726778cd_f60a_4eda_82de_e47610cd78aa>(
              &v19,
              *(_QWORD *)Data4);
            if ( !v19 )
              goto LABEL_40;
            memset((char *)pvar.m256i_i64 + 4, 0, 28);
            pvar.m256i_i32[0] = 32;
            pvar.m256i_i32[2] = *(_DWORD *)&this[5].Data2;
            pvar.m256i_i32[5] = *(_DWORD *)this[5].Data4 != 0;
            v12 = (*(__int64 (__fastcall **)(__int64, __m256i *))(*(_QWORD *)v19 + 128LL))(v19, &pvar);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              WPP_SF_dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                14,
                WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids,
                *(unsigned int *)&this[5].Data2,
                v12);
            }
            if ( v12 >= 0 )
            {
LABEL_40:
              ATL::CComQIPtr<IAudioClient2,&__s_GUID const _GUID_726778cd_f60a_4eda_82de_e47610cd78aa>::CComQIPtr<IAudioClient2,&__s_GUID const _GUID_726778cd_f60a_4eda_82de_e47610cd78aa>(
                &v18,
                *(_QWORD *)&v14->Data1);
              if ( !v18 )
                goto LABEL_47;
              memset((char *)pvar.m256i_i64 + 4, 0, 28);
              pvar.m256i_i32[0] = 32;
              pvar.m256i_i32[2] = this[5].Data1;
              v12 = (*(__int64 (__fastcall **)(__int64, __m256i *))(*(_QWORD *)v18 + 128LL))(v18, &pvar);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
              {
                WPP_SF_dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  15,
                  WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids,
                  this[5].Data1,
                  v12);
              }
              if ( v12 >= 0 )
              {
LABEL_47:
                wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v18);
                wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v19);
                *v4 = 0;
                v15 = CMonitor::MuteInputLineControls(a2, a3);
                if ( v15 < 0
                  && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    16,
                    WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids,
                    (unsigned int)v15);
                }
                v12 = ((__int64 (__fastcall *)(struct IMMDevice *, GUID *))a2->lpVtbl->GetId)(a2, &this[6]);
                if ( v12 >= 0 )
                {
                  v12 = ((__int64 (__fastcall *)(struct IMMDevice *, unsigned __int8 *))a3->lpVtbl->GetId)(
                          a3,
                          this[9].Data4);
                  if ( v12 >= 0 )
                  {
                    v12 = (*(__int64 (__fastcall **)(_QWORD, GUID *))(**(_QWORD **)Data4 + 64LL))(
                            *(_QWORD *)Data4,
                            this + 7);
                    if ( v12 >= 0 )
                    {
                      v18 = 0;
                      memset(&pvar, 0, 24);
                      v12 = ((__int64 (__fastcall *)(struct IMMDevice *, _QWORD, __int64 *))a2->lpVtbl->OpenPropertyStore)(
                              a2,
                              0,
                              &v18);
                      if ( v12 < 0 )
                        goto LABEL_56;
                      memset(&pvar, 0, 24);
                      v12 = (*(__int64 (__fastcall **)(__int64, __int64 *, __m256i *))(*(_QWORD *)v18 + 40LL))(
                              v18,
                              PKEY_MonitorPauseOnBattery,
                              &pvar);
                      if ( v12 < 0 )
                        goto LABEL_56;
                      if ( pvar.m256i_i16[0] == 11 )
                        this[4].Data4[5] = pvar.m256i_i16[4] == 0xFFFF;
                      PropVariantClear((PROPVARIANT *)&pvar);
                      memset(&pvar, 0, 24);
                      v12 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, __m256i *))(*(_QWORD *)v18 + 40LL))(
                              v18,
                              &PKEY_AudioEndpoint_GUID,
                              &pvar);
                      if ( v12 < 0
                        || pvar.m256i_i16[0] == 31
                        && (v12 = CLSIDFromString((LPCOLESTR)pvar.m256i_i64[1], this + 8), v12 < 0) )
                      {
LABEL_56:
                        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v18);
                      }
                      else
                      {
                        PropVariantClear((PROPVARIANT *)&pvar);
                        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v18);
                        v24 = 0;
                        ATL::CComQIPtr<IAudioClientInternal,&__s_GUID const _GUID_59ea7369_26c3_4eb9_a3bb_4f7d9b0b6ccb>::CComQIPtr<IAudioClientInternal,&__s_GUID const _GUID_59ea7369_26c3_4eb9_a3bb_4f7d9b0b6ccb>(
                          &v19,
                          *(_QWORD *)Data4);
                        v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v19 + 48LL))(
                                v19,
                                *(_QWORD *)&this[7].Data1,
                                0,
                                &v24);
                        if ( v12 < 0
                          || (v12 = (*(__int64 (__fastcall **)(_QWORD, GUID *, unsigned __int8 *))(**(_QWORD **)Data4
                                                                                                 + 112LL))(
                                      *(_QWORD *)Data4,
                                      &GUID_f4b1a599_7266_4319_a8ca_e70acb11e8cd,
                                      this[7].Data4),
                              v12 < 0)
                          || (v23 = this,
                              LODWORD(v18) = 1,
                              v12 = Microsoft::WRL::Details::MakeAndInitialize<CMonitor::CMonitorNotification,CMonitor::CMonitorNotification,enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,CMonitor *>(
                                      &this[9],
                                      &v18,
                                      &v23),
                              v12 < 0)
                          || (wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v19),
                              ATL::CComQIPtr<IAudioClientInternal,&__s_GUID const _GUID_59ea7369_26c3_4eb9_a3bb_4f7d9b0b6ccb>::CComQIPtr<IAudioClientInternal,&__s_GUID const _GUID_59ea7369_26c3_4eb9_a3bb_4f7d9b0b6ccb>(
                                &v19,
                                *(_QWORD *)&v14->Data1),
                              v12 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v19 + 56LL))(
                                      v19,
                                      this + 8,
                                      v24),
                              v12 < 0) )
                        {
                          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v19);
                        }
                        else
                        {
                          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v19);
                          v12 = (*(__int64 (__fastcall **)(_QWORD, GUID *, unsigned __int8 *))(**(_QWORD **)&this[10].Data1
                                                                                             + 112LL))(
                                  *(_QWORD *)&this[10].Data1,
                                  &GUID_f4b1a599_7266_4319_a8ca_e70acb11e8cd,
                                  this[10].Data4);
                          if ( v12 >= 0 )
                          {
                            v16 = *(void (__fastcall ****)(_QWORD, GUID *, __int64 *))this[10].Data4;
                            v17 = 0;
                            v19 = 0;
                            if ( v16 )
                            {
                              (**v16)(v16, &GUID_1167b081_0746_45f0_9ecd_97cc50de3a1f, &v19);
                              v17 = v19;
                            }
                            v18 = 0;
                            memset(&pvar, 0, 24);
                            v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 168LL))(v17, &v18);
                            if ( v12 < 0
                              || (pvar.m256i_i16[0] = 11,
                                  pvar.m256i_i16[4] = -1,
                                  v12 = (*(__int64 (__fastcall **)(__int64, __int64 *, __m256i *))(*(_QWORD *)v18 + 48LL))(
                                          v18,
                                          PKEY_AudioSession_IsCaptureMonitorSession,
                                          &pvar),
                                  v12 < 0)
                              || (memset(&pvar, 0, 24),
                                  pvar.m256i_i16[0] = 31,
                                  pvar.m256i_i64[1] = *(_QWORD *)&this[6].Data1,
                                  v12 = (*(__int64 (__fastcall **)(__int64, __int64 *, __m256i *))(*(_QWORD *)v18 + 48LL))(
                                          v18,
                                          PKEY_AudioSession_CaptureMonitorEndpointId,
                                          &pvar),
                                  v12 < 0) )
                            {
                              wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v18);
                              wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v19);
                            }
                            else
                            {
                              wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v18);
                              wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v19);
                              v23 = this;
                              LODWORD(v18) = 0;
                              v12 = Microsoft::WRL::Details::MakeAndInitialize<CMonitor::CMonitorNotification,CMonitor::CMonitorNotification,enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,CMonitor *>(
                                      &this[11],
                                      &v18,
                                      &v23);
                              if ( v12 >= 0 )
                              {
                                v12 = CMonitor::SetSessionTitleAndIcon((CMonitor *)this, a2);
                                if ( v12 >= 0 )
                                {
                                  v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)this[7].Data4 + 80LL))(
                                          *(_QWORD *)this[7].Data4,
                                          *(_QWORD *)&this[9].Data1);
                                  if ( v12 >= 0 )
                                  {
                                    v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)this[10].Data4 + 80LL))(
                                            *(_QWORD *)this[10].Data4,
                                            *(_QWORD *)&this[11].Data1);
                                    if ( v12 >= 0 )
                                    {
                                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
                                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                                      {
                                        WPP_SF_(
                                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                                          17,
                                          WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids);
                                      }
                                      *(_DWORD *)this[4].Data4 = 2;
                                      this[4].Data4[4] = 0;
                                      goto LABEL_63;
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                    v4 = v20;
                  }
                }
                goto LABEL_58;
              }
              wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v18);
            }
            wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v19);
          }
        }
      }
    }
LABEL_58:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids, this, v12);
    }
    this[4].Data4[4] = 1;
    *(_DWORD *)this[4].Data4 = *v4 ? 7 : 0;
LABEL_63:
    ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)&lpCriticalSection);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v21);
    return (unsigned int)v12;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x800000) != 0 && *((_BYTE *)v8 + 25) >= 2u )
    WPP_SF_(v8[2], 11, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids);
  *v4 = 0;
  if ( v26 )
    LeaveCriticalSection(lpCriticalSection);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800638c8  push    rbp
0x1800638ca  push    rbx
0x1800638cb  push    rsi
0x1800638cc  push    rdi
0x1800638cd  push    r12
0x1800638cf  push    r13
0x1800638d1  push    r14
0x1800638d3  push    r15
0x1800638d5  lea     rbp, [rsp-1Fh]
0x1800638da  sub     rsp, 0A8h
0x1800638e1  mov     rax, cs:__security_cookie
0x1800638e8  xor     rax, rsp
0x1800638eb  mov     [rbp+57h+var_48], rax
0x1800638ef  mov     r14, r9
0x1800638f2  mov     [rbp+57h+var_A0], r9
0x1800638f6  mov     rsi, r8
0x1800638f9  mov     r15, rdx
0x1800638fc  mov     rdi, rcx
0x1800638ff  xor     r13d, r13d
0x180063902  mov     [rbp+57h+var_98], r13
0x180063906  mov     [rbp+57h+var_90], r13d
0x18006390a  lea     rax, [rcx+20h]
0x18006390e  mov     [rbp+57h+lpCriticalSection], rax
0x180063912  mov     [rbp+57h+var_70], r13b
0x180063916  lea     rcx, [rbp+57h+lpCriticalSection]; this
0x18006391a  call    ?Lock@CCritSecLock@ATL@@QEAAXXZ; ATL::CCritSecLock::Lock(void)
0x18006391f  nop
0x180063920  lea     rbx, WPP_GLOBAL_Control
0x180063927  mov     rcx, cs:WPP_GLOBAL_Control
0x18006392e  cmp     rcx, rbx
0x180063931  jz      short loc_180063960
0x180063933  test    dword ptr [rcx+1Ch], 800000h
0x18006393a  jz      short loc_180063960
0x18006393c  cmp     byte ptr [rcx+19h], 4
0x180063940  jb      short loc_180063960
0x180063942  lea     edx, [r13+0Ah]
0x180063946  mov     r9, rdi
0x180063949  lea     r8, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids
0x180063950  mov     rcx, [rcx+10h]
0x180063954  call    WPP_SF_q
0x180063959  mov     rcx, cs:WPP_GLOBAL_Control
0x180063960  cmp     [rdi+48h], r13d
0x180063964  jz      short loc_1800639C9
0x180063966  cmp     dword ptr [rdi+48h], 6
0x18006396a  jz      short loc_1800639C9
0x18006396c  cmp     rcx, rbx
0x18006396f  jz      short loc_180063995
0x180063971  test    dword ptr [rcx+1Ch], 800000h
0x180063978  jz      short loc_180063995
0x18006397a  cmp     byte ptr [rcx+19h], 2
0x18006397e  jb      short loc_180063995
0x180063980  mov     edx, 0Bh
0x180063985  lea     r8, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids
0x18006398c  mov     rcx, [rcx+10h]
0x180063990  call    WPP_SF_
0x180063995  mov     [r14], r13b
0x180063998  cmp     [rbp+57h+var_70], r13b
0x18006399c  jz      short loc_1800639A9
0x18006399e  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x1800639a2  call    cs:__imp_LeaveCriticalSection
0x1800639a8  nop
0x1800639a9  mov     rcx, [rbp+57h+var_98]
0x1800639ad  test    rcx, rcx
0x1800639b0  jz      short loc_1800639BF
0x1800639b2  mov     rax, [rcx]
0x1800639b5  mov     rax, [rax+10h]
0x1800639b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800639be  nop
0x1800639bf  mov     eax, 80004005h
0x1800639c4  jmp     loc_180063DB8
0x1800639c9  mov     byte ptr [r14], 1
0x1800639cd  mov     dword ptr [rdi+48h], 1
0x1800639d4  xor     r8d, r8d; pcbe
0x1800639d7  mov     rdx, rdi; pv
0x1800639da  lea     rcx, ?TerminateMonitorInWorkerThread@CMonitor@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800639e1  call    cs:__imp_CreateThreadpoolWork
0x1800639e7  mov     [rdi+0C8h], rax
0x1800639ee  test    rax, rax
0x1800639f1  jnz     short loc_180063A4F
0x1800639f3  call    cs:__imp_GetLastError
0x1800639f9  mov     ebx, eax
0x1800639fb  test    eax, eax
0x1800639fd  jle     short loc_180063A08
0x1800639ff  movzx   ebx, ax
0x180063a02  or      ebx, 80070000h
0x180063a08  mov     rcx, cs:WPP_GLOBAL_Control
0x180063a0f  lea     rdx, WPP_GLOBAL_Control
0x180063a16  cmp     rcx, rdx
0x180063a19  jz      short loc_180063A42
0x180063a1b  test    dword ptr [rcx+1Ch], 800000h
0x180063a22  jz      short loc_180063A42
0x180063a24  cmp     byte ptr [rcx+19h], 2
0x180063a28  jb      short loc_180063A42
0x180063a2a  mov     edx, 0Ch
0x180063a2f  mov     r9d, ebx
0x180063a32  lea     r8, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids
0x180063a39  mov     rcx, [rcx+10h]
0x180063a3d  call    WPP_SF_d
0x180063a42  test    ebx, ebx
0x180063a44  js      loc_180063D54
0x180063a4a  jmp     loc_180063DA3
0x180063a4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180063a56  cmp     rcx, rbx
0x180063a59  jz      short loc_180063A87
0x180063a5b  test    dword ptr [rcx+1Ch], 800000h
0x180063a62  jz      short loc_180063A87
0x180063a64  cmp     byte ptr [rcx+19h], 4
0x180063a68  jb      short loc_180063A87
0x180063a6a  mov     edx, 0Dh
0x180063a6f  mov     [rsp+0E0h+var_C0], rax
0x180063a74  mov     r9, rdi
0x180063a77  lea     r8, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids
0x180063a7e  mov     rcx, [rcx+10h]
0x180063a82  call    WPP_SF_qq
0x180063a87  mov     rax, [r15]
0x180063a8a  lea     r8, [rbp+57h+var_98]
0x180063a8e  lea     rdx, _GUID_1be09788_6894_4089_8586_9a2a6c265ac5
0x180063a95  mov     rcx, r15
0x180063a98  mov     rax, [rax]
0x180063a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063aa0  mov     ebx, eax
0x180063aa2  test    eax, eax
0x180063aa4  js      loc_180063D54
0x180063aaa  mov     rcx, [rbp+57h+var_98]
0x180063aae  mov     rax, [rcx]
0x180063ab1  lea     rdx, [rbp+57h+var_90]
0x180063ab5  mov     rax, [rax+18h]
0x180063ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063abe  mov     ebx, eax
0x180063ac0  test    eax, eax
0x180063ac2  js      loc_180063D54
0x180063ac8  lea     r12, [rdi+68h]
0x180063acc  mov     rax, [r15]
0x180063acf  mov     [rsp+0E0h+var_C0], r12
0x180063ad4  xor     r9d, r9d
0x180063ad7  lea     r8d, [r9+1]
0x180063adb  lea     rdx, IID_IAudioClient
0x180063ae2  mov     rcx, r15
0x180063ae5  mov     rax, [rax+18h]
0x180063ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063aee  mov     ebx, eax
0x180063af0  test    eax, eax
0x180063af2  js      loc_180063D54
0x180063af8  lea     r13, [rdi+0A0h]
0x180063aff  mov     rax, [rsi]
0x180063b02  mov     [rsp+0E0h+var_C0], r13
0x180063b07  xor     r9d, r9d
0x180063b0a  lea     r8d, [r9+1]
0x180063b0e  lea     rdx, IID_IAudioClient
0x180063b15  mov     rcx, rsi
0x180063b18  mov     rax, [rax+18h]
0x180063b1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063b21  mov     ebx, eax
0x180063b23  test    eax, eax
0x180063b25  js      loc_180063D54
0x180063b2b  mov     rdx, [r12]
0x180063b2f  lea     rcx, [rbp+57h+var_A8]
0x180063b33  call    ??0?$CComQIPtr@UIAudioClient2@@$1?_GUID_726778cd_f60a_4eda_82de_e47610cd78aa@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IAudioClient2,&__s_GUID const _GUID_726778cd_f60a_4eda_82de_e47610cd78aa>::CComQIPtr<IAudioClient2,&__s_GUID const _GUID_726778cd_f60a_4eda_82de_e47610cd78aa>(IUnknown *)
0x180063b38  nop
0x180063b39  mov     rcx, [rbp+57h+var_A8]
0x180063b3d  test    rcx, rcx
0x180063b40  jz      loc_180063BCF
0x180063b46  xorps   xmm0, xmm0
0x180063b49  movups  xmmword ptr [rbp+57h+pvar+4], xmm0
0x180063b4d  movups  xmmword ptr [rbp-1], xmm0
0x180063b51  mov     dword ptr [rbp+57h+pvar], 20h ; ' '
0x180063b58  mov     eax, [rdi+54h]
0x180063b5b  mov     dword ptr [rbp+57h+pvar+8], eax
0x180063b5e  xor     eax, eax
0x180063b60  cmp     [rdi+58h], eax
0x180063b63  setnz   al
0x180063b66  mov     [rbp+57h+var_54], eax
0x180063b69  mov     rax, [rcx]
0x180063b6c  lea     rdx, [rbp+57h+pvar]
0x180063b70  mov     rax, [rax+80h]
0x180063b77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063b7c  mov     ebx, eax
0x180063b7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180063b85  lea     rax, WPP_GLOBAL_Control
0x180063b8c  cmp     rcx, rax
0x180063b8f  jz      short loc_180063BBD
0x180063b91  test    dword ptr [rcx+1Ch], 800000h
0x180063b98  jz      short loc_180063BBD
0x180063b9a  cmp     byte ptr [rcx+19h], 3
0x180063b9e  jb      short loc_180063BBD
0x180063ba0  mov     edx, 0Eh
0x180063ba5  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x180063ba9  mov     r9d, [rdi+54h]
0x180063bad  lea     r8, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids
0x180063bb4  mov     rcx, [rcx+10h]
0x180063bb8  call    WPP_SF_dd
0x180063bbd  test    ebx, ebx
0x180063bbf  jns     short loc_180063BCF
0x180063bc1  lea     rcx, [rbp+57h+var_A8]
0x180063bc5  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180063bca  jmp     loc_180063D54
0x180063bcf  mov     rdx, [r13+0]
0x180063bd3  lea     rcx, [rbp+57h+var_B0]
0x180063bd7  call    ??0?$CComQIPtr@UIAudioClient2@@$1?_GUID_726778cd_f60a_4eda_82de_e47610cd78aa@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IAudioClient2,&__s_GUID const _GUID_726778cd_f60a_4eda_82de_e47610cd78aa>::CComQIPtr<IAudioClient2,&__s_GUID const _GUID_726778cd_f60a_4eda_82de_e47610cd78aa>(IUnknown *)
0x180063bdc  nop
0x180063bdd  mov     rcx, [rbp+57h+var_B0]
0x180063be1  test    rcx, rcx
0x180063be4  jz      short loc_180063C64
0x180063be6  xorps   xmm0, xmm0
0x180063be9  movups  xmmword ptr [rbp+57h+pvar+4], xmm0
0x180063bed  movups  xmmword ptr [rbp-1], xmm0
0x180063bf1  mov     dword ptr [rbp+57h+pvar], 20h ; ' '
0x180063bf8  mov     eax, [rdi+50h]
0x180063bfb  mov     dword ptr [rbp+57h+pvar+8], eax
0x180063bfe  mov     rax, [rcx]
0x180063c01  lea     rdx, [rbp+57h+pvar]
0x180063c05  mov     rax, [rax+80h]
0x180063c0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063c11  mov     ebx, eax
0x180063c13  mov     rcx, cs:WPP_GLOBAL_Control
0x180063c1a  lea     rax, WPP_GLOBAL_Control
0x180063c21  cmp     rcx, rax
0x180063c24  jz      short loc_180063C52
0x180063c26  test    dword ptr [rcx+1Ch], 800000h
0x180063c2d  jz      short loc_180063C52
0x180063c2f  cmp     byte ptr [rcx+19h], 3
0x180063c33  jb      short loc_180063C52
0x180063c35  mov     edx, 0Fh
0x180063c3a  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x180063c3e  mov     r9d, [rdi+50h]
0x180063c42  lea     r8, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids
0x180063c49  mov     rcx, [rcx+10h]
0x180063c4d  call    WPP_SF_dd
0x180063c52  test    ebx, ebx
0x180063c54  jns     short loc_180063C64
0x180063c56  lea     rcx, [rbp+57h+var_B0]
0x180063c5a  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180063c5f  jmp     loc_180063BC1
0x180063c64  lea     rcx, [rbp+57h+var_B0]
0x180063c68  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180063c6d  nop
0x180063c6e  lea     rcx, [rbp+57h+var_A8]
0x180063c72  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180063c77  mov     byte ptr [r14], 0
0x180063c7b  mov     rdx, rsi; struct IMMDevice *
0x180063c7e  mov     rcx, r15; struct IMMDevice *
0x180063c81  call    ?MuteInputLineControls@CMonitor@@CAJPEAUIMMDevice@@0@Z; CMonitor::MuteInputLineControls(IMMDevice *,IMMDevice *)
0x180063c86  test    eax, eax
0x180063c88  jns     short loc_180063CC4
0x180063c8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180063c91  lea     rdx, WPP_GLOBAL_Control
0x180063c98  cmp     rcx, rdx
0x180063c9b  jz      short loc_180063CC4
0x180063c9d  test    dword ptr [rcx+1Ch], 800000h
0x180063ca4  jz      short loc_180063CC4
0x180063ca6  cmp     byte ptr [rcx+19h], 2
0x180063caa  jb      short loc_180063CC4
0x180063cac  mov     edx, 10h
0x180063cb1  mov     r9d, eax
0x180063cb4  lea     r8, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids
0x180063cbb  mov     rcx, [rcx+10h]
0x180063cbf  call    WPP_SF_d
0x180063cc4  mov     rax, [r15]
0x180063cc7  lea     rdx, [rdi+60h]
0x180063ccb  mov     rcx, r15
0x180063cce  mov     rax, [rax+28h]
0x180063cd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063cd7  mov     ebx, eax
0x180063cd9  test    eax, eax
0x180063cdb  js      short loc_180063D54
0x180063cdd  mov     rax, [rsi]
0x180063ce0  lea     rdx, [rdi+98h]
0x180063ce7  mov     rcx, rsi
0x180063cea  mov     rax, [rax+28h]
0x180063cee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063cf3  mov     ebx, eax
0x180063cf5  test    eax, eax
0x180063cf7  js      short loc_180063D54
0x180063cf9  mov     rcx, [r12]
0x180063cfd  mov     rax, [rcx]
0x180063d00  lea     rdx, [rdi+70h]
0x180063d04  mov     rax, [rax+40h]
0x180063d08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063d0d  mov     ebx, eax
0x180063d0f  test    eax, eax
0x180063d11  js      short loc_180063D50
0x180063d13  mov     [rbp+57h+var_B0], 0
0x180063d1b  xorps   xmm0, xmm0
0x180063d1e  xor     eax, eax
0x180063d20  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180063d24  mov     [rbp-1], rax
0x180063d28  mov     rax, [r15]
0x180063d2b  lea     r8, [rbp+57h+var_B0]
0x180063d2f  xor     edx, edx
0x180063d31  mov     rcx, r15
0x180063d34  mov     rax, [rax+20h]
0x180063d38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063d3d  mov     ebx, eax
0x180063d3f  test    eax, eax
0x180063d41  jns     loc_180063DD8
0x180063d47  lea     rcx, [rbp+57h+var_B0]
0x180063d4b  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180063d50  mov     r14, [rbp+57h+var_A0]
0x180063d54  mov     rcx, cs:WPP_GLOBAL_Control
0x180063d5b  lea     rax, WPP_GLOBAL_Control
  ... truncated ...
```
