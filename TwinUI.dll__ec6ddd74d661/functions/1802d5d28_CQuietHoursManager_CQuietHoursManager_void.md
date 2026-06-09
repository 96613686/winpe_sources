# CQuietHoursManager::~CQuietHoursManager(void)

- ea: `0x1802d5d28`
- end: `0x1802d5e4e`
- name: `??1CQuietHoursManager@@EEAA@XZ`
- size: `294`
- prototype: `void __fastcall(CQuietHoursManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1802d5ec0`

## callees

- `0x1802d5cfc`
- `0x1802d5d28`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1802d5d83`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1802d5db3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1802d5de3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1802d5e18`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1802d5d83`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1802d5db3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1802d5de3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1802d5e18`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1802d5d96`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1802d5dc6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1802d5df6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1802d5e2b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1802d5d96`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1802d5dc6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1802d5df6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1802d5e2b`

## pseudocode

```c
void __fastcall CQuietHoursManager::~CQuietHoursManager(CQuietHoursManager *this)
{
  struct _TP_TIMER *v2; // rcx
  struct _TP_TIMER *v3; // rcx
  struct _TP_TIMER *v4; // rcx

  *(_QWORD *)this = &CQuietHoursManager::`vftable'{for `Microsoft::WRL::Details::Selector<CImmersiveShellComponentWithGITSite,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CImmersiveShellComponentWithGITSite>,IQuietHoursPolicy,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 5) = &CQuietHoursManager::`vftable'{for `IImmersiveShellComponent'};
  *((_QWORD *)this + 6) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CImmersiveShellComponentWithGITSite,IQuietHoursPolicy,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IServiceProvider>'};
  *((_QWORD *)this + 13) = &CQuietHoursManager::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IQuietHoursPolicy,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CImmersiveShellComponentWithGITSite>,IQuietHoursPolicy,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 14) = &CQuietHoursManager::`vftable'{for `IImmersiveWindowMessageNotification'};
  *((_QWORD *)this + 15) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CImmersiveShellComponentWithGITSite,IQuietHoursPolicy,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 25);
  if ( v2 )
  {
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 25));
  }
  v3 = (struct _TP_TIMER *)*((_QWORD *)this + 26);
  if ( v3 )
  {
    WaitForThreadpoolTimerCallbacks(v3, 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 26));
  }
  v4 = (struct _TP_TIMER *)*((_QWORD *)this + 27);
  if ( v4 )
  {
    WaitForThreadpoolTimerCallbacks(v4, 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 27));
  }
  if ( *((_QWORD *)this + 27) )
  {
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 28), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 28));
  }
  *((_DWORD *)this + 39) = -1073741823;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CImmersiveShellComponentWithGITSite>,IQuietHoursPolicy,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase>::~ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CImmersiveShellComponentWithGITSite>,IQuietHoursPolicy,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x1802d5d28  push    rbx
0x1802d5d2a  sub     rsp, 20h
0x1802d5d2e  lea     rax, ??_7CQuietHoursManager@@6B?$Selector@VCImmersiveShellComponentWithGITSite@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VCImmersiveShellComponentWithGITSite@@@Details@23@UIQuietHoursPolicy@@UIImmersiveWindowMessageNotification@@VFtmBase@23@@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@@; const CQuietHoursManager::`vftable'{for `Microsoft::WRL::Details::Selector<CImmersiveShellComponentWithGITSite,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CImmersiveShellComponentWithGITSite>,IQuietHoursPolicy,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase>>'}
0x1802d5d35  mov     rbx, rcx
0x1802d5d38  mov     [rcx], rax
0x1802d5d3b  lea     rax, ??_7CQuietHoursManager@@6BIImmersiveShellComponent@@@; const CQuietHoursManager::`vftable'{for `IImmersiveShellComponent'}
0x1802d5d42  mov     [rcx+28h], rax
0x1802d5d46  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VCImmersiveShellComponentWithGITSite@@UIQuietHoursPolicy@@UIImmersiveWindowMessageNotification@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIServiceProvider@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CImmersiveShellComponentWithGITSite,IQuietHoursPolicy,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IServiceProvider>'}
0x1802d5d4d  mov     [rcx+30h], rax
0x1802d5d51  lea     rax, ??_7CQuietHoursManager@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIQuietHoursPolicy@@UIImmersiveWindowMessageNotification@@VFtmBase@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VCImmersiveShellComponentWithGITSite@@@Details@23@UIQuietHoursPolicy@@UIImmersiveWindowMessageNotification@@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const CQuietHoursManager::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IQuietHoursPolicy,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CImmersiveShellComponentWithGITSite>,IQuietHoursPolicy,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase>>'}
0x1802d5d58  mov     [rcx+68h], rax
0x1802d5d5c  lea     rax, ??_7CQuietHoursManager@@6BIImmersiveWindowMessageNotification@@@; const CQuietHoursManager::`vftable'{for `IImmersiveWindowMessageNotification'}
0x1802d5d63  mov     [rcx+70h], rax
0x1802d5d67  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VCImmersiveShellComponentWithGITSite@@UIQuietHoursPolicy@@UIImmersiveWindowMessageNotification@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CImmersiveShellComponentWithGITSite,IQuietHoursPolicy,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1802d5d6e  mov     [rcx+78h], rax
0x1802d5d72  mov     rcx, [rcx+0C8h]; pti
0x1802d5d79  test    rcx, rcx
0x1802d5d7c  jz      short loc_1802D5DA2
0x1802d5d7e  mov     edx, 1; fCancelPendingCallbacks
0x1802d5d83  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1802d5d8a  nop     dword ptr [rax+rax+00h]
0x1802d5d8f  mov     rcx, [rbx+0C8h]; pti
0x1802d5d96  call    cs:__imp_CloseThreadpoolTimer
0x1802d5d9d  nop     dword ptr [rax+rax+00h]
0x1802d5da2  mov     rcx, [rbx+0D0h]; pti
0x1802d5da9  test    rcx, rcx
0x1802d5dac  jz      short loc_1802D5DD2
0x1802d5dae  mov     edx, 1; fCancelPendingCallbacks
0x1802d5db3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1802d5dba  nop     dword ptr [rax+rax+00h]
0x1802d5dbf  mov     rcx, [rbx+0D0h]; pti
0x1802d5dc6  call    cs:__imp_CloseThreadpoolTimer
0x1802d5dcd  nop     dword ptr [rax+rax+00h]
0x1802d5dd2  mov     rcx, [rbx+0D8h]; pti
0x1802d5dd9  test    rcx, rcx
0x1802d5ddc  jz      short loc_1802D5E02
0x1802d5dde  mov     edx, 1; fCancelPendingCallbacks
0x1802d5de3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1802d5dea  nop     dword ptr [rax+rax+00h]
0x1802d5def  mov     rcx, [rbx+0D8h]; pti
0x1802d5df6  call    cs:__imp_CloseThreadpoolTimer
0x1802d5dfd  nop     dword ptr [rax+rax+00h]
0x1802d5e02  cmp     qword ptr [rbx+0D8h], 0
0x1802d5e0a  jz      short loc_1802D5E37
0x1802d5e0c  mov     rcx, [rbx+0E0h]; pti
0x1802d5e13  mov     edx, 1; fCancelPendingCallbacks
0x1802d5e18  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1802d5e1f  nop     dword ptr [rax+rax+00h]
0x1802d5e24  mov     rcx, [rbx+0E0h]; pti
0x1802d5e2b  call    cs:__imp_CloseThreadpoolTimer
0x1802d5e32  nop     dword ptr [rax+rax+00h]
0x1802d5e37  mov     rcx, rbx; this
0x1802d5e3a  mov     dword ptr [rbx+9Ch], 0C0000001h
0x1802d5e44  add     rsp, 20h
0x1802d5e48  pop     rbx
0x1802d5e49  jmp     ??1?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VCImmersiveShellComponentWithGITSite@@@Details@23@UIQuietHoursPolicy@@UIImmersiveWindowMessageNotification@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CImmersiveShellComponentWithGITSite>,IQuietHoursPolicy,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase>::~ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CImmersiveShellComponentWithGITSite>,IQuietHoursPolicy,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase>(void)
```
