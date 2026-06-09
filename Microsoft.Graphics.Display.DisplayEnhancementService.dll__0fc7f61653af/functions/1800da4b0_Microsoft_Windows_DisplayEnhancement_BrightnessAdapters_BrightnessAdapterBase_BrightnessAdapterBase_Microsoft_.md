# Microsoft::Windows::DisplayEnhancement::BrightnessAdapters::BrightnessAdapterBase::BrightnessAdapterBase(Microsoft::Windows::DisplayEnhancement::Foundation::MonitorAdapterTargetId,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::BrightnessCapabilityWrapper> const &,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingsGroup>)

- ea: `0x1800da4b0`
- end: `0x1800da5ce`
- name: `??0BrightnessAdapterBase@BrightnessAdapters@DisplayEnhancement@Windows@Microsoft@@QEAA@UMonitorAdapterTargetId@Foundation@234@AEBV?$shared_ptr@VBrightnessCapabilityWrapper@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@V?$shared_ptr@VDeManagementServerSettingsGroup@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@@8@@Z`
- size: `286`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800d8088`
- `0x1800da5d4`

## callees

- `0x180008ae8`
- `0x18000f778`
- `0x180011fe8`
- `0x1800753fc`
- `0x1800da4b0`
- `0x1800dc634`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da57c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da591`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da57c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da591`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800da574`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800da574`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800da550`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800da550`

## string_xrefs

- `0x1800da5a8`: `Microsoft.Graphics.Display.DisplayEnhancementService.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char *__fastcall Microsoft::Windows::DisplayEnhancement::BrightnessAdapters::BrightnessAdapterBase::BrightnessAdapterBase(
        char *pv,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  _QWORD *v6; // r8
  _QWORD *v7; // rax
  PTP_TIMER *v8; // rbx
  PTP_TIMER ThreadpoolTimer; // rax
  signed int LastError; // eax
  unsigned int v11; // ebx
  signed int v12; // eax
  std::_Ref_count_base *v13; // rcx
  struct _FILETIME pftDueTime; // [rsp+48h] [rbp+10h] BYREF
  __int64 v16; // [rsp+58h] [rbp+20h]

  v16 = a4;
  *(_QWORD *)pv = &Microsoft::Windows::DisplayEnhancement::BrightnessAdapters::BrightnessAdapterBase::`vftable';
  pv[8] = 0;
  *(_QWORD *)(pv + 12) = *(_QWORD *)a2;
  *((_DWORD *)pv + 5) = *(_DWORD *)(a2 + 8);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<unsigned char>>::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<unsigned char>>(
    pv + 24,
    a4);
  pv[40] = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 8LL))(*v6) != 0;
  *((_QWORD *)pv + 6) = 0;
  *((_QWORD *)pv + 7) = 0;
  *((_QWORD *)pv + 8) = 0;
  v7 = std::_Allocate<16,std::_Default_allocate_traits>(0x38u);
  *v7 = v7;
  v7[1] = v7;
  *((_QWORD *)pv + 7) = v7;
  v8 = (PTP_TIMER *)(pv + 72);
  *((_QWORD *)pv + 9) = 0;
  pftDueTime = (struct _FILETIME)-20000000LL;
  if ( pv[40] )
  {
    ThreadpoolTimer = CreateThreadpoolTimer(
                        Microsoft::Windows::DisplayEnhancement::BrightnessAdapters::BrightnessAdapterBase::OnInitialBrightnessSetTimerCallback,
                        pv,
                        0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,1>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      pv + 72,
      ThreadpoolTimer);
    if ( *v8 )
    {
      SetThreadpoolTimer(*v8, &pftDueTime, 0, 0);
    }
    else
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      v12 = GetLastError();
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      MicrosoftTelemetryAssertTriggeredArgs(
        "Microsoft.Graphics.Display.DisplayEnhancementService.dll",
        (unsigned int)v12,
        v11);
    }
  }
  v13 = *(std::_Ref_count_base **)(a4 + 8);
  if ( v13 )
    std::_Ref_count_base::_Decref(v13);
  return pv;
}

```

## disassembly

```asm
0x1800da4b0  mov     [rsp+arg_18], r9
0x1800da4b5  mov     [rsp+arg_0], rcx
0x1800da4ba  push    rbx
0x1800da4bb  push    rsi
0x1800da4bc  push    rdi
0x1800da4bd  sub     rsp, 20h
0x1800da4c1  mov     rsi, r9
0x1800da4c4  mov     rdi, rcx
0x1800da4c7  lea     rax, ??_7BrightnessAdapterBase@BrightnessAdapters@DisplayEnhancement@Windows@Microsoft@@6B@; const Microsoft::Windows::DisplayEnhancement::BrightnessAdapters::BrightnessAdapterBase::`vftable'
0x1800da4ce  mov     [rcx], rax
0x1800da4d1  mov     byte ptr [rcx+8], 0
0x1800da4d5  movsd   xmm0, qword ptr [rdx]
0x1800da4d9  movsd   qword ptr [rcx+0Ch], xmm0
0x1800da4de  mov     eax, [rdx+8]
0x1800da4e1  mov     [rcx+14h], eax
0x1800da4e4  add     rcx, 18h
0x1800da4e8  mov     rdx, r9
0x1800da4eb  call    ??0?$shared_ptr@V?$OEMSetting@E@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>>::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>> const &)
0x1800da4f0  nop
0x1800da4f1  mov     rcx, [r8]
0x1800da4f4  mov     rax, [rcx]
0x1800da4f7  mov     rax, [rax+8]
0x1800da4fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da500  test    eax, eax
0x1800da502  setnz   al
0x1800da505  mov     [rdi+28h], al
0x1800da508  xor     eax, eax
0x1800da50a  mov     [rdi+30h], rax
0x1800da50e  mov     [rdi+38h], rax
0x1800da512  mov     [rdi+40h], rax
0x1800da516  lea     ecx, [rax+38h]
0x1800da519  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800da51e  mov     [rax], rax
0x1800da521  mov     [rax+8], rax
0x1800da525  mov     [rdi+38h], rax
0x1800da529  lea     rbx, [rdi+48h]
0x1800da52d  mov     qword ptr [rbx], 0
0x1800da534  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], 0FFFFFFFFFECED300h
0x1800da53d  cmp     byte ptr [rdi+28h], 0
0x1800da541  jz      short loc_1800DA5B5
0x1800da543  xor     r8d, r8d; pcbe
0x1800da546  mov     rdx, rdi; pv
0x1800da549  lea     rcx, ?OnInitialBrightnessSetTimerCallback@BrightnessAdapterBase@BrightnessAdapters@DisplayEnhancement@Windows@Microsoft@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800da550  call    cs:__imp_CreateThreadpoolTimer
0x1800da556  mov     rdx, rax
0x1800da559  mov     rcx, rbx
0x1800da55c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$00@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,1>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800da561  mov     rcx, [rbx]; pti
0x1800da564  test    rcx, rcx
0x1800da567  jz      short loc_1800DA57C
0x1800da569  xor     r9d, r9d; msWindowLength
0x1800da56c  xor     r8d, r8d; msPeriod
0x1800da56f  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1800da574  call    cs:__imp_SetThreadpoolTimer
0x1800da57a  jmp     short loc_1800DA5B5
0x1800da57c  call    cs:__imp_GetLastError
0x1800da582  mov     ebx, eax
0x1800da584  test    eax, eax
0x1800da586  jle     short loc_1800DA591
0x1800da588  movzx   ebx, ax
0x1800da58b  or      ebx, 80070000h
0x1800da591  call    cs:__imp_GetLastError
0x1800da597  test    eax, eax
0x1800da599  jle     short loc_1800DA5A3
0x1800da59b  movzx   eax, ax
0x1800da59e  or      eax, 80070000h
0x1800da5a3  mov     r8d, ebx
0x1800da5a6  mov     edx, eax
0x1800da5a8  lea     rcx, aMicrosoftGraph_0; "Microsoft.Graphics.Display.DisplayEnhan"...
0x1800da5af  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800da5b4  nop
0x1800da5b5  mov     rcx, [rsi+8]; this
0x1800da5b9  test    rcx, rcx
0x1800da5bc  jz      short loc_1800DA5C3
0x1800da5be  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800da5c3  mov     rax, rdi
0x1800da5c6  add     rsp, 20h
0x1800da5ca  pop     rdi
0x1800da5cb  pop     rsi
0x1800da5cc  pop     rbx
0x1800da5cd  retn
```
