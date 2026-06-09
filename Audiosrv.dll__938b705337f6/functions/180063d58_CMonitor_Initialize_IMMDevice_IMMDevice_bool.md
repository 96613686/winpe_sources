# CMonitor::Initialize(IMMDevice *,IMMDevice *,bool &)

- ea: `0x180063d58`
- end: `0x1800645de`
- name: `?Initialize@CMonitor@@QEAAJPEAUIMMDevice@@0AEA_N@Z`
- size: `2182`
- prototype: `__int64 __fastcall(CMonitor *__hidden this, struct IMMDevice *, struct IMMDevice *, bool *)`
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180063a6c`
- `0x18012a074`

## callees

- `0x18000accc`
- `0x180036364`
- `0x1800382ac`
- `0x180063d58`
- `0x180072450`
- `0x1800b55c4`
- `0x1800cf8c0`
- `0x1800e5ab0`
- `0x1800e81e4`
- `0x1800e82c0`
- `0x1800e8440`
- `0x18012c238`
- `0x18012c374`
- `0x18012c3b4`
- `0x18012cd88`
- `0x18012d83c`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063e32`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063e32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063e83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063e83`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180063e71`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180063e71`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800642b4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180064316`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800642b4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180064316`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180064302`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180064302`

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
  unsigned __int8 *v18; // [rsp+20h] [rbp-69h]
  __int64 v19; // [rsp+30h] [rbp-59h] BYREF
  __int64 v20; // [rsp+38h] [rbp-51h] BYREF
  bool *v21; // [rsp+40h] [rbp-49h]
  __int64 v22; // [rsp+48h] [rbp-41h] BYREF
  int v23; // [rsp+50h] [rbp-39h] BYREF
  GUID *v24; // [rsp+58h] [rbp-31h] BYREF
  __int64 v25; // [rsp+60h] [rbp-29h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+68h] [rbp-21h] BYREF
  char v27; // [rsp+70h] [rbp-19h]
  __m256i pvar; // [rsp+78h] [rbp-11h] BYREF

  v4 = a4;
  v21 = a4;
  v22 = 0;
  v23 = 0;
  lpCriticalSection = (LPCRITICAL_SECTION)&this[2];
  v27 = 0;
  ATL::CCritSecLock::Lock((ATL::CCritSecLock *)&lpCriticalSection);
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids, this);
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
          &WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids,
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
      HIDWORD(v18) = HIDWORD(ThreadpoolWork);
      WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids);
    }
    v12 = ((__int64 (__fastcall *)(struct IMMDevice *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
            a2,
            &GUID_1be09788_6894_4089_8586_9a2a6c265ac5,
            &v22);
    if ( v12 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 24LL))(v22, &v23);
      if ( v12 >= 0 )
      {
        Data4 = this[6].Data4;
        v18 = this[6].Data4;
        v12 = ((__int64 (__fastcall *)(struct IMMDevice *, GUID *, __int64))a2->lpVtbl->Activate)(
                a2,
                &IID_IAudioClient,
                1);
        if ( v12 >= 0 )
        {
          v14 = this + 10;
          v18 = (unsigned __int8 *)&this[10];
          v12 = ((__int64 (__fastcall *)(struct IMMDevice *, GUID *, __int64))a3->lpVtbl->Activate)(
                  a3,
                  &IID_IAudioClient,
                  1);
          if ( v12 >= 0 )
          {
            ATL::CComQIPtr<IAudioClient2,&__s_GUID const _GUID_726778cd_f60a_4eda_82de_e47610cd78aa>::CComQIPtr<IAudioClient2,&__s_GUID const _GUID_726778cd_f60a_4eda_82de_e47610cd78aa>(
              &v20,
              *(_QWORD *)Data4);
            if ( !v20 )
              goto LABEL_40;
            memset((char *)pvar.m256i_i64 + 4, 0, 28);
            pvar.m256i_i32[0] = 32;
            pvar.m256i_i32[2] = *(_DWORD *)&this[5].Data2;
            pvar.m256i_i32[5] = *(_DWORD *)this[5].Data4 != 0;
            v12 = (*(__int64 (__fastcall **)(__int64, __m256i *))(*(_QWORD *)v20 + 128LL))(v20, &pvar);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids);
            }
            if ( v12 >= 0 )
            {
LABEL_40:
              ATL::CComQIPtr<IAudioClient2,&__s_GUID const _GUID_726778cd_f60a_4eda_82de_e47610cd78aa>::CComQIPtr<IAudioClient2,&__s_GUID const _GUID_726778cd_f60a_4eda_82de_e47610cd78aa>(
                &v19,
                *(_QWORD *)&v14->Data1);
              if ( !v19 )
                goto LABEL_47;
              memset((char *)pvar.m256i_i64 + 4, 0, 28);
              pvar.m256i_i32[0] = 32;
              pvar.m256i_i32[2] = this[5].Data1;
              v12 = (*(__int64 (__fastcall **)(__int64, __m256i *))(*(_QWORD *)v19 + 128LL))(v19, &pvar);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
              {
                WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids);
              }
              if ( v12 >= 0 )
              {
LABEL_47:
                wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v19);
                wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v20);
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
                    &WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids,
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
                      v19 = 0;
                      memset(&pvar, 0, 24);
                      v12 = ((__int64 (__fastcall *)(struct IMMDevice *, _QWORD, __int64 *))a2->lpVtbl->OpenPropertyStore)(
                              a2,
                              0,
                              &v19);
                      if ( v12 < 0 )
                        goto LABEL_56;
                      memset(&pvar, 0, 24);
                      v12 = (*(__int64 (__fastcall **)(__int64, void *, __m256i *))(*(_QWORD *)v19 + 40LL))(
                              v19,
                              &PKEY_MonitorPauseOnBattery,
                              &pvar);
                      if ( v12 < 0 )
                        goto LABEL_56;
                      if ( pvar.m256i_i16[0] == 11 )
                        this[4].Data4[5] = pvar.m256i_i16[4] == 0xFFFF;
                      PropVariantClear((PROPVARIANT *)&pvar);
                      memset(&pvar, 0, 24);
                      v12 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, __m256i *))(*(_QWORD *)v19 + 40LL))(
                              v19,
                              &PKEY_AudioEndpoint_GUID,
                              &pvar);
                      if ( v12 < 0
                        || pvar.m256i_i16[0] == 31
                        && (v12 = CLSIDFromString((LPCOLESTR)pvar.m256i_i64[1], this + 8), v12 < 0) )
                      {
LABEL_56:
                        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v19);
                      }
                      else
                      {
                        PropVariantClear((PROPVARIANT *)&pvar);
                        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v19);
                        v25 = 0;
                        ATL::CComQIPtr<IAudioClientInternal,&__s_GUID const _GUID_59ea7369_26c3_4eb9_a3bb_4f7d9b0b6ccb>::CComQIPtr<IAudioClientInternal,&__s_GUID const _GUID_59ea7369_26c3_4eb9_a3bb_4f7d9b0b6ccb>(
                          &v20,
                          *(_QWORD *)Data4);
                        v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v20 + 48LL))(
                                v20,
                                *(_QWORD *)&this[7].Data1,
                                0,
                                &v25);
                        if ( v12 < 0
                          || (v12 = (*(__int64 (__fastcall **)(_QWORD, GUID *, unsigned __int8 *))(**(_QWORD **)Data4
                                                                                                 + 112LL))(
                                      *(_QWORD *)Data4,
                                      &GUID_f4b1a599_7266_4319_a8ca_e70acb11e8cd,
                                      this[7].Data4),
                              v12 < 0)
                          || (v24 = this,
                              LODWORD(v19) = 1,
                              v12 = Microsoft::WRL::Details::MakeAndInitialize<CMonitor::CMonitorNotification,CMonitor::CMonitorNotification,enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,CMonitor *>(
                                      &this[9],
                                      &v19,
                                      &v24),
                              v12 < 0)
                          || (wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v20),
                              ATL::CComQIPtr<IAudioClientInternal,&__s_GUID const _GUID_59ea7369_26c3_4eb9_a3bb_4f7d9b0b6ccb>::CComQIPtr<IAudioClientInternal,&__s_GUID const _GUID_59ea7369_26c3_4eb9_a3bb_4f7d9b0b6ccb>(
                                &v20,
                                *(_QWORD *)&v14->Data1),
                              v12 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v20 + 56LL))(
                                      v20,
                                      this + 8,
                                      v25),
                              v12 < 0) )
                        {
                          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v20);
                        }
                        else
                        {
                          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v20);
                          v12 = (*(__int64 (__fastcall **)(_QWORD, GUID *, unsigned __int8 *))(**(_QWORD **)&this[10].Data1
                                                                                             + 112LL))(
                                  *(_QWORD *)&this[10].Data1,
                                  &GUID_f4b1a599_7266_4319_a8ca_e70acb11e8cd,
                                  this[10].Data4);
                          if ( v12 >= 0 )
                          {
                            v16 = *(void (__fastcall ****)(_QWORD, GUID *, __int64 *))this[10].Data4;
                            v17 = 0;
                            v20 = 0;
                            if ( v16 )
                            {
                              (**v16)(v16, &GUID_1167b081_0746_45f0_9ecd_97cc50de3a1f, &v20);
                              v17 = v20;
                            }
                            v19 = 0;
                            memset(&pvar, 0, 24);
                            v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 168LL))(v17, &v19);
                            if ( v12 < 0
                              || (pvar.m256i_i16[0] = 11,
                                  pvar.m256i_i16[4] = -1,
                                  v12 = (*(__int64 (__fastcall **)(__int64, void *, __m256i *))(*(_QWORD *)v19 + 48LL))(
                                          v19,
                                          &PKEY_AudioSession_IsCaptureMonitorSession,
                                          &pvar),
                                  v12 < 0)
                              || (memset(&pvar, 0, 24),
                                  pvar.m256i_i16[0] = 31,
                                  pvar.m256i_i64[1] = *(_QWORD *)&this[6].Data1,
                                  v12 = (*(__int64 (__fastcall **)(__int64, void *, __m256i *))(*(_QWORD *)v19 + 48LL))(
                                          v19,
                                          &PKEY_AudioSession_CaptureMonitorEndpointId,
                                          &pvar),
                                  v12 < 0) )
                            {
                              wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v19);
                              wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v20);
                            }
                            else
                            {
                              wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v19);
                              wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v20);
                              v24 = this;
                              LODWORD(v19) = 0;
                              v12 = Microsoft::WRL::Details::MakeAndInitialize<CMonitor::CMonitorNotification,CMonitor::CMonitorNotification,enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,CMonitor *>(
                                      &this[11],
                                      &v19,
                                      &v24);
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
                                          &WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids);
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
                    v4 = v21;
                  }
                }
                goto LABEL_58;
              }
              wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v19);
            }
            wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v20);
          }
        }
      }
    }
LABEL_58:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LODWORD(v18) = v12;
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids, this, v18);
    }
    this[4].Data4[4] = 1;
    *(_DWORD *)this[4].Data4 = *v4 ? 7 : 0;
LABEL_63:
    ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)&lpCriticalSection);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v22);
    return (unsigned int)v12;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x800000) != 0 && *((_BYTE *)v8 + 25) >= 2u )
    WPP_SF_(v8[2], 11, &WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids);
  *v4 = 0;
  if ( v27 )
    LeaveCriticalSection(lpCriticalSection);
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180063d58  push    rbp
0x180063d5a  push    rbx
0x180063d5b  push    rsi
0x180063d5c  push    rdi
0x180063d5d  push    r12
0x180063d5f  push    r13
0x180063d61  push    r14
0x180063d63  push    r15
0x180063d65  lea     rbp, [rsp-1Fh]
0x180063d6a  sub     rsp, 0A8h
0x180063d71  mov     rax, cs:__security_cookie
0x180063d78  xor     rax, rsp
0x180063d7b  mov     [rbp+57h+var_48], rax
0x180063d7f  mov     r14, r9
0x180063d82  mov     [rbp+57h+var_A0], r9
0x180063d86  mov     rsi, r8
0x180063d89  mov     r15, rdx
0x180063d8c  mov     rdi, rcx
0x180063d8f  xor     r13d, r13d
0x180063d92  mov     [rbp+57h+var_98], r13
0x180063d96  mov     [rbp+57h+var_90], r13d
0x180063d9a  lea     rax, [rcx+20h]
0x180063d9e  mov     [rbp+57h+lpCriticalSection], rax
0x180063da2  mov     [rbp+57h+var_70], r13b
0x180063da6  lea     rcx, [rbp+57h+lpCriticalSection]; this
0x180063daa  call    ?Lock@CCritSecLock@ATL@@QEAAXXZ; ATL::CCritSecLock::Lock(void)
0x180063daf  nop
0x180063db0  lea     rbx, WPP_GLOBAL_Control
0x180063db7  mov     rcx, cs:WPP_GLOBAL_Control
0x180063dbe  cmp     rcx, rbx
0x180063dc1  jz      short loc_180063DF0
0x180063dc3  test    dword ptr [rcx+1Ch], 800000h
0x180063dca  jz      short loc_180063DF0
0x180063dcc  cmp     byte ptr [rcx+19h], 4
0x180063dd0  jb      short loc_180063DF0
0x180063dd2  lea     edx, [r13+0Ah]
0x180063dd6  mov     r9, rdi
0x180063dd9  lea     r8, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids
0x180063de0  mov     rcx, [rcx+10h]
0x180063de4  call    WPP_SF_q
0x180063de9  mov     rcx, cs:WPP_GLOBAL_Control
0x180063df0  cmp     [rdi+48h], r13d
0x180063df4  jz      short loc_180063E59
0x180063df6  cmp     dword ptr [rdi+48h], 6
0x180063dfa  jz      short loc_180063E59
0x180063dfc  cmp     rcx, rbx
0x180063dff  jz      short loc_180063E25
0x180063e01  test    dword ptr [rcx+1Ch], 800000h
0x180063e08  jz      short loc_180063E25
0x180063e0a  cmp     byte ptr [rcx+19h], 2
0x180063e0e  jb      short loc_180063E25
0x180063e10  mov     edx, 0Bh
0x180063e15  lea     r8, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids
0x180063e1c  mov     rcx, [rcx+10h]
0x180063e20  call    WPP_SF_
0x180063e25  mov     [r14], r13b
0x180063e28  cmp     [rbp+57h+var_70], r13b
0x180063e2c  jz      short loc_180063E39
0x180063e2e  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x180063e32  call    cs:__imp_LeaveCriticalSection
0x180063e38  nop
0x180063e39  mov     rcx, [rbp+57h+var_98]
0x180063e3d  test    rcx, rcx
0x180063e40  jz      short loc_180063E4F
0x180063e42  mov     rax, [rcx]
0x180063e45  mov     rax, [rax+10h]
0x180063e49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063e4e  nop
0x180063e4f  mov     eax, 80004005h
0x180063e54  jmp     loc_180064248
0x180063e59  mov     byte ptr [r14], 1
0x180063e5d  mov     dword ptr [rdi+48h], 1
0x180063e64  xor     r8d, r8d; pcbe
0x180063e67  mov     rdx, rdi; pv
0x180063e6a  lea     rcx, ?TerminateMonitorInWorkerThread@CMonitor@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180063e71  call    cs:__imp_CreateThreadpoolWork
0x180063e77  mov     [rdi+0C8h], rax
0x180063e7e  test    rax, rax
0x180063e81  jnz     short loc_180063EDF
0x180063e83  call    cs:__imp_GetLastError
0x180063e89  mov     ebx, eax
0x180063e8b  test    eax, eax
0x180063e8d  jle     short loc_180063E98
0x180063e8f  movzx   ebx, ax
0x180063e92  or      ebx, 80070000h
0x180063e98  mov     rcx, cs:WPP_GLOBAL_Control
0x180063e9f  lea     rdx, WPP_GLOBAL_Control
0x180063ea6  cmp     rcx, rdx
0x180063ea9  jz      short loc_180063ED2
0x180063eab  test    dword ptr [rcx+1Ch], 800000h
0x180063eb2  jz      short loc_180063ED2
0x180063eb4  cmp     byte ptr [rcx+19h], 2
0x180063eb8  jb      short loc_180063ED2
0x180063eba  mov     edx, 0Ch
0x180063ebf  mov     r9d, ebx
0x180063ec2  lea     r8, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids
0x180063ec9  mov     rcx, [rcx+10h]
0x180063ecd  call    WPP_SF_d
0x180063ed2  test    ebx, ebx
0x180063ed4  js      loc_1800641E4
0x180063eda  jmp     loc_180064233
0x180063edf  mov     rcx, cs:WPP_GLOBAL_Control
0x180063ee6  cmp     rcx, rbx
0x180063ee9  jz      short loc_180063F17
0x180063eeb  test    dword ptr [rcx+1Ch], 800000h
0x180063ef2  jz      short loc_180063F17
0x180063ef4  cmp     byte ptr [rcx+19h], 4
0x180063ef8  jb      short loc_180063F17
0x180063efa  mov     edx, 0Dh
0x180063eff  mov     [rsp+0E0h+var_C0], rax
0x180063f04  mov     r9, rdi
0x180063f07  lea     r8, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids
0x180063f0e  mov     rcx, [rcx+10h]
0x180063f12  call    WPP_SF_qq
0x180063f17  mov     rax, [r15]
0x180063f1a  lea     r8, [rbp+57h+var_98]
0x180063f1e  lea     rdx, _GUID_1be09788_6894_4089_8586_9a2a6c265ac5
0x180063f25  mov     rcx, r15
0x180063f28  mov     rax, [rax]
0x180063f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063f30  mov     ebx, eax
0x180063f32  test    eax, eax
0x180063f34  js      loc_1800641E4
0x180063f3a  mov     rcx, [rbp+57h+var_98]
0x180063f3e  mov     rax, [rcx]
0x180063f41  lea     rdx, [rbp+57h+var_90]
0x180063f45  mov     rax, [rax+18h]
0x180063f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063f4e  mov     ebx, eax
0x180063f50  test    eax, eax
0x180063f52  js      loc_1800641E4
0x180063f58  lea     r12, [rdi+68h]
0x180063f5c  mov     rax, [r15]
0x180063f5f  mov     [rsp+0E0h+var_C0], r12
0x180063f64  xor     r9d, r9d
0x180063f67  lea     r8d, [r9+1]
0x180063f6b  lea     rdx, IID_IAudioClient
0x180063f72  mov     rcx, r15
0x180063f75  mov     rax, [rax+18h]
0x180063f79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063f7e  mov     ebx, eax
0x180063f80  test    eax, eax
0x180063f82  js      loc_1800641E4
0x180063f88  lea     r13, [rdi+0A0h]
0x180063f8f  mov     rax, [rsi]
0x180063f92  mov     [rsp+0E0h+var_C0], r13
0x180063f97  xor     r9d, r9d
0x180063f9a  lea     r8d, [r9+1]
0x180063f9e  lea     rdx, IID_IAudioClient
0x180063fa5  mov     rcx, rsi
0x180063fa8  mov     rax, [rax+18h]
0x180063fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063fb1  mov     ebx, eax
0x180063fb3  test    eax, eax
0x180063fb5  js      loc_1800641E4
0x180063fbb  mov     rdx, [r12]
0x180063fbf  lea     rcx, [rbp+57h+var_A8]
0x180063fc3  call    ??0?$CComQIPtr@UIAudioClient2@@$1?_GUID_726778cd_f60a_4eda_82de_e47610cd78aa@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IAudioClient2,&__s_GUID const _GUID_726778cd_f60a_4eda_82de_e47610cd78aa>::CComQIPtr<IAudioClient2,&__s_GUID const _GUID_726778cd_f60a_4eda_82de_e47610cd78aa>(IUnknown *)
0x180063fc8  nop
0x180063fc9  mov     rcx, [rbp+57h+var_A8]
0x180063fcd  test    rcx, rcx
0x180063fd0  jz      loc_18006405F
0x180063fd6  xorps   xmm0, xmm0
0x180063fd9  movups  xmmword ptr [rbp+57h+pvar+4], xmm0
0x180063fdd  movups  xmmword ptr [rbp-1], xmm0
0x180063fe1  mov     dword ptr [rbp+57h+pvar], 20h ; ' '
0x180063fe8  mov     eax, [rdi+54h]
0x180063feb  mov     dword ptr [rbp+57h+pvar+8], eax
0x180063fee  xor     eax, eax
0x180063ff0  cmp     [rdi+58h], eax
0x180063ff3  setnz   al
0x180063ff6  mov     [rbp+57h+var_54], eax
0x180063ff9  mov     rax, [rcx]
0x180063ffc  lea     rdx, [rbp+57h+pvar]
0x180064000  mov     rax, [rax+80h]
0x180064007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006400c  mov     ebx, eax
0x18006400e  mov     rcx, cs:WPP_GLOBAL_Control
0x180064015  lea     rax, WPP_GLOBAL_Control
0x18006401c  cmp     rcx, rax
0x18006401f  jz      short loc_18006404D
0x180064021  test    dword ptr [rcx+1Ch], 800000h
0x180064028  jz      short loc_18006404D
0x18006402a  cmp     byte ptr [rcx+19h], 3
0x18006402e  jb      short loc_18006404D
0x180064030  mov     edx, 0Eh
0x180064035  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x180064039  mov     r9d, [rdi+54h]
0x18006403d  lea     r8, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids
0x180064044  mov     rcx, [rcx+10h]
0x180064048  call    WPP_SF_dd
0x18006404d  test    ebx, ebx
0x18006404f  jns     short loc_18006405F
0x180064051  lea     rcx, [rbp+57h+var_A8]
0x180064055  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18006405a  jmp     loc_1800641E4
0x18006405f  mov     rdx, [r13+0]
0x180064063  lea     rcx, [rbp+57h+var_B0]
0x180064067  call    ??0?$CComQIPtr@UIAudioClient2@@$1?_GUID_726778cd_f60a_4eda_82de_e47610cd78aa@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IAudioClient2,&__s_GUID const _GUID_726778cd_f60a_4eda_82de_e47610cd78aa>::CComQIPtr<IAudioClient2,&__s_GUID const _GUID_726778cd_f60a_4eda_82de_e47610cd78aa>(IUnknown *)
0x18006406c  nop
0x18006406d  mov     rcx, [rbp+57h+var_B0]
0x180064071  test    rcx, rcx
0x180064074  jz      short loc_1800640F4
0x180064076  xorps   xmm0, xmm0
0x180064079  movups  xmmword ptr [rbp+57h+pvar+4], xmm0
0x18006407d  movups  xmmword ptr [rbp-1], xmm0
0x180064081  mov     dword ptr [rbp+57h+pvar], 20h ; ' '
0x180064088  mov     eax, [rdi+50h]
0x18006408b  mov     dword ptr [rbp+57h+pvar+8], eax
0x18006408e  mov     rax, [rcx]
0x180064091  lea     rdx, [rbp+57h+pvar]
0x180064095  mov     rax, [rax+80h]
0x18006409c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800640a1  mov     ebx, eax
0x1800640a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800640aa  lea     rax, WPP_GLOBAL_Control
0x1800640b1  cmp     rcx, rax
0x1800640b4  jz      short loc_1800640E2
0x1800640b6  test    dword ptr [rcx+1Ch], 800000h
0x1800640bd  jz      short loc_1800640E2
0x1800640bf  cmp     byte ptr [rcx+19h], 3
0x1800640c3  jb      short loc_1800640E2
0x1800640c5  mov     edx, 0Fh
0x1800640ca  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x1800640ce  mov     r9d, [rdi+50h]
0x1800640d2  lea     r8, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids
0x1800640d9  mov     rcx, [rcx+10h]
0x1800640dd  call    WPP_SF_dd
0x1800640e2  test    ebx, ebx
0x1800640e4  jns     short loc_1800640F4
0x1800640e6  lea     rcx, [rbp+57h+var_B0]
0x1800640ea  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800640ef  jmp     loc_180064051
0x1800640f4  lea     rcx, [rbp+57h+var_B0]
0x1800640f8  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800640fd  nop
0x1800640fe  lea     rcx, [rbp+57h+var_A8]
0x180064102  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180064107  mov     byte ptr [r14], 0
0x18006410b  mov     rdx, rsi; struct IMMDevice *
0x18006410e  mov     rcx, r15; struct IMMDevice *
0x180064111  call    ?MuteInputLineControls@CMonitor@@CAJPEAUIMMDevice@@0@Z; CMonitor::MuteInputLineControls(IMMDevice *,IMMDevice *)
0x180064116  test    eax, eax
0x180064118  jns     short loc_180064154
0x18006411a  mov     rcx, cs:WPP_GLOBAL_Control
0x180064121  lea     rdx, WPP_GLOBAL_Control
0x180064128  cmp     rcx, rdx
0x18006412b  jz      short loc_180064154
0x18006412d  test    dword ptr [rcx+1Ch], 800000h
0x180064134  jz      short loc_180064154
0x180064136  cmp     byte ptr [rcx+19h], 2
0x18006413a  jb      short loc_180064154
0x18006413c  mov     edx, 10h
0x180064141  mov     r9d, eax
0x180064144  lea     r8, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids
0x18006414b  mov     rcx, [rcx+10h]
0x18006414f  call    WPP_SF_d
0x180064154  mov     rax, [r15]
0x180064157  lea     rdx, [rdi+60h]
0x18006415b  mov     rcx, r15
0x18006415e  mov     rax, [rax+28h]
0x180064162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064167  mov     ebx, eax
0x180064169  test    eax, eax
0x18006416b  js      short loc_1800641E4
0x18006416d  mov     rax, [rsi]
0x180064170  lea     rdx, [rdi+98h]
0x180064177  mov     rcx, rsi
0x18006417a  mov     rax, [rax+28h]
0x18006417e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064183  mov     ebx, eax
0x180064185  test    eax, eax
0x180064187  js      short loc_1800641E4
0x180064189  mov     rcx, [r12]
0x18006418d  mov     rax, [rcx]
0x180064190  lea     rdx, [rdi+70h]
0x180064194  mov     rax, [rax+40h]
0x180064198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006419d  mov     ebx, eax
0x18006419f  test    eax, eax
0x1800641a1  js      short loc_1800641E0
0x1800641a3  mov     [rbp+57h+var_B0], 0
0x1800641ab  xorps   xmm0, xmm0
0x1800641ae  xor     eax, eax
0x1800641b0  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x1800641b4  mov     [rbp-1], rax
0x1800641b8  mov     rax, [r15]
0x1800641bb  lea     r8, [rbp+57h+var_B0]
0x1800641bf  xor     edx, edx
0x1800641c1  mov     rcx, r15
0x1800641c4  mov     rax, [rax+20h]
0x1800641c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800641cd  mov     ebx, eax
0x1800641cf  test    eax, eax
0x1800641d1  jns     loc_180064268
0x1800641d7  lea     rcx, [rbp+57h+var_B0]
0x1800641db  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800641e0  mov     r14, [rbp+57h+var_A0]
0x1800641e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800641eb  lea     rax, WPP_GLOBAL_Control
  ... truncated ...
```
