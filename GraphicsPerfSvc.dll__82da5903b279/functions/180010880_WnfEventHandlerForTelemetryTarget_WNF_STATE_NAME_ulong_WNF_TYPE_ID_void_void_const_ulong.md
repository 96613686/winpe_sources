# WnfEventHandlerForTelemetryTarget(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)

- ea: `0x180010880`
- end: `0x180010cea`
- name: `?WnfEventHandlerForTelemetryTarget@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z`
- size: `1130`
- prototype: `__int64 __fastcall(struct _WNF_STATE_NAME, int, struct _WNF_TYPE_ID *, void *, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001010`
- `0x1800018ac`
- `0x180003ab0`
- `0x180005c6c`
- `0x18000768c`
- `0x18000cd2c`
- `0x18000d67c`
- `0x18000d778`
- `0x18000e138`
- `0x18000e3e4`
- `0x18000e77c`
- `0x18000e79c`
- `0x18000f7a8`
- `0x18000f87c`
- `0x1800107b0`
- `0x180010880`
- `0x180011598`
- `0x180013ad0`
- `0x180019c6c`
- `0x1800271dc`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010a08`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010a08`
- `api-ms-win-shcore-thread-l1-1-0!GetProcessReference` at `0x1800108de`
- `api-ms-win-shcore-thread-l1-1-0!GetProcessReference` at `0x1800108de`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800109af`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800109af`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800109e3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800109e3`

## string_xrefs

- `0x18001092c`: `onecoreuap\windows\directx\dxg\gpm\service\service.cpp`

## pseudocode

```c
__int64 __fastcall WnfEventHandlerForTelemetryTarget(
        struct _WNF_STATE_NAME a1,
        int a2,
        struct _WNF_TYPE_ID *a3,
        void *a4,
        unsigned int *a5,
        unsigned int a6)
{
  unsigned int v6; // ebx
  int ProcessReference; // edi
  unsigned int v8; // edi
  __int64 *v9; // rax
  __int64 v10; // r8
  __int64 v11; // rdi
  std::_Ref_count_base *v12; // rsi
  __int64 v13; // rax
  unsigned int v14; // r15d
  void (__fastcall *v15)(__int64, _QWORD, __int64); // r9
  __int64 v16; // r10
  const struct _tlgProvider_t *v17; // r14
  int v18; // r8d
  int v19; // r9d
  const char *dwOptions; // [rsp+20h] [rbp-4C8h]
  const char *samDesired; // [rsp+28h] [rbp-4C0h]
  unsigned int v23; // [rsp+70h] [rbp-478h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-470h] BYREF
  struct _GUID v25; // [rsp+80h] [rbp-468h] BYREF
  BYTE Data[8]; // [rsp+90h] [rbp-458h] BYREF
  int v27; // [rsp+98h] [rbp-450h] BYREF
  int v28; // [rsp+9Ch] [rbp-44Ch] BYREF
  unsigned int v29; // [rsp+A0h] [rbp-448h] BYREF
  void ***v30; // [rsp+A8h] [rbp-440h] BYREF
  __int64 v31; // [rsp+B0h] [rbp-438h] BYREF
  __int64 v32; // [rsp+B8h] [rbp-430h] BYREF
  __int64 v33; // [rsp+C0h] [rbp-428h] BYREF
  int v34; // [rsp+C8h] [rbp-420h]
  __int64 v35; // [rsp+D0h] [rbp-418h] BYREF
  struct _RTL_CRITICAL_SECTION *v36; // [rsp+D8h] [rbp-410h] BYREF
  _QWORD v37[2]; // [rsp+E0h] [rbp-408h] BYREF
  _BYTE v38[80]; // [rsp+F0h] [rbp-3F8h] BYREF
  char v39[144]; // [rsp+140h] [rbp-3A8h] BYREF
  char v40[80]; // [rsp+1D0h] [rbp-318h] BYREF
  char v41[144]; // [rsp+220h] [rbp-2C8h] BYREF
  char v42[80]; // [rsp+2B0h] [rbp-238h] BYREF
  char v43[144]; // [rsp+300h] [rbp-1E8h] BYREF
  char v44[80]; // [rsp+390h] [rbp-158h] BYREF
  char v45[144]; // [rsp+3E0h] [rbp-108h] BYREF
  char v46[80]; // [rsp+470h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4E8h] [rbp+0h]

  *(_DWORD *)Data = a2;
  gpm::TraceProvider::WatchCurrentThread(v38, "WnfEventHandler");
  v6 = 0;
  v31 = 0;
  ProcessReference = GetProcessReference(&v31);
  v25 = GUID_NULL;
  if ( ProcessReference >= 0 )
  {
    TelemetrySink::LogDiagnostic(
      (TelemetrySink *)&g::TelemetrySink,
      L"Wnf for telemetry target process ID received",
      &v25);
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    if ( !RegCreateKeyExW(HKEY_CURRENT_USER, L"SOFTWARE\\Microsoft\\Direct3D", 0, 0, 0, 0x20006u, 0, &hKey, 0) )
      RegSetValueExW(hKey, L"LastTelemetryChangeStamp", 0, 4u, Data, 4u);
    if ( a6 == 4 )
    {
      v8 = *a5;
      v23 = *a5;
      EnterCriticalSection(&g::ShutdownCritsect);
      try
      {
        v36 = &g::ShutdownCritsect;
        if ( g::spTraceConsumer && !PresentTraceConsumerCore::IsProcessTrackedForTelemetry(g::spTraceConsumer, v8) )
        {
          v30 = &g::TelemetrySink;
          v9 = (__int64 *)std::make_shared<TelemetryEventConsumer,unsigned long &,TelemetrySink *>(&v25, &v23, &v30);
          v11 = *v9;
          v37[0] = *v9;
          v12 = (std::_Ref_count_base *)v9[1];
          v37[1] = v12;
          *v9 = 0;
          v9[1] = 0;
          if ( *(_QWORD *)v25.Data4 )
            std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)v25.Data4);
          if ( v11 )
          {
            v13 = std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(
                    &v33,
                    v37,
                    v10,
                    *(_QWORD *)(*(_QWORD *)g::spTraceConsumer + 40LL));
            v14 = v23;
            v15(v16, v23, v13);
            v17 = gpm::TraceProvider::Provider();
            if ( *(_DWORD *)v17 > 5u )
            {
              if ( (unsigned __int8)tlgKeywordOn(v17, 1) )
              {
                v23 = *(_DWORD *)(PresentTraceConsumerCore::GetCounters(g::spTraceConsumer, v45) + 84);
                v27 = *(_DWORD *)(PresentTraceConsumerCore::GetCounters(g::spTraceConsumer, v43) + 80);
                v33 = PresentTraceConsumerCore::GetCounters(g::spTraceConsumer, v41) + 20;
                v34 = 20;
                *(_QWORD *)&v25.Data1 = PresentTraceConsumerCore::GetCounters(g::spTraceConsumer, v39);
                *(_DWORD *)v25.Data4 = 20;
                v28 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 152LL))(v11);
                v35 = v11;
                v29 = v14;
                LODWORD(v30) = 1;
                v32 = 0x1000000;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperPtrSize,_tlgWrapperPtrSize,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                  (_DWORD)v17,
                  (unsigned int)&unk_180039CD0,
                  v18,
                  v19,
                  (__int64)&v32,
                  (__int64)&v30,
                  (__int64)&v29,
                  (__int64)&v35,
                  (__int64)&v28,
                  (__int64)&v25,
                  (__int64)&v33,
                  (__int64)&v27,
                  (__int64)&v23);
                std::string::_Tidy_deallocate(v40);
                std::string::_Tidy_deallocate(v42);
                std::string::_Tidy_deallocate(v44);
                std::string::_Tidy_deallocate(v46);
              }
            }
          }
          if ( v12 )
            std::_Ref_count_base::_Decref(v12);
        }
        wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v36);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtExceptionMsg(
          retaddr,
          (void *)0x105,
          (unsigned int)"onecoreuap\\windows\\directx\\dxg\\gpm\\service\\service.cpp",
          "Exception thrown while adding Present Consumer.",
          dwOptions);
        v6 = 0;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  else
  {
    TelemetrySink::LogDiagnostic(
      (TelemetrySink *)&g::TelemetrySink,
      L"Wnf for telemetry target process ID failed to get GetProcessReference",
      &v25);
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0xD0,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\gpm\\service\\service.cpp",
      (const char *)(unsigned int)ProcessReference,
      (int)"Wnf for telemetry target process ID failed to get GetProcessReference",
      samDesired);
    MicrosoftTelemetryAssertTriggeredArgs(
      "Wnf for telemetry target process ID failed to get GetProcessReference",
      (unsigned int)ProcessReference,
      0);
    v6 = -1073741823;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v38);
  return v6;
}

```

## disassembly

```asm
0x180010880  mov     [rsp+arg_0], rbx
0x180010885  mov     [rsp+arg_10], rsi
0x18001088a  push    rdi
0x18001088b  push    r14
0x18001088d  push    r15
0x18001088f  sub     rsp, 4D0h
0x180010896  mov     rax, cs:__security_cookie
0x18001089d  xor     rax, rsp
0x1800108a0  mov     [rsp+4E8h+var_28], rax
0x1800108a8  mov     dword ptr [rsp+4E8h+Data], edx
0x1800108af  mov     r14, [rsp+4E8h+arg_20]
0x1800108b7  lea     rdx, aWnfeventhandle; "WnfEventHandler"
0x1800108be  lea     rcx, [rsp+4E8h+var_3F8]
0x1800108c6  call    ?WatchCurrentThread@TraceProvider@gpm@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; gpm::TraceProvider::WatchCurrentThread(char const *)
0x1800108cb  nop
0x1800108cc  xor     ebx, ebx
0x1800108ce  mov     [rsp+4E8h+var_438], rbx
0x1800108d6  lea     rcx, [rsp+4E8h+var_438]
0x1800108de  call    cs:__imp_GetProcessReference
0x1800108e4  mov     edi, eax
0x1800108e6  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800108ed  lea     r8, [rsp+4E8h+var_468]; struct _GUID
0x1800108f5  movdqu  xmmword ptr [rsp+4E8h+var_468.Data1], xmm0
0x1800108fe  test    eax, eax
0x180010900  jns     short loc_180010954
0x180010902  lea     rdx, aWnfForTelemetr_1; "Wnf for telemetry target process ID fai"...
0x180010909  lea     rcx, ?TelemetrySink@g@@3U0@A; this
0x180010910  call    ?LogDiagnostic@TelemetrySink@@UEAAXPEBGU_GUID@@@Z; TelemetrySink::LogDiagnostic(ushort const *,_GUID)
0x180010915  mov     rcx, [rsp+4E8h]; this
0x18001091d  lea     rbx, aWnfForTelemetr_0; "Wnf for telemetry target process ID fai"...
0x180010924  mov     qword ptr [rsp+4E8h+dwOptions], rbx; int
0x180010929  mov     r9d, edi; char *
0x18001092c  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\directx\\dxg\\gpm"...
0x180010933  mov     edx, 0D0h; void *
0x180010938  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001093d  xor     r8d, r8d
0x180010940  mov     edx, edi
0x180010942  mov     rcx, rbx
0x180010945  call    MicrosoftTelemetryAssertTriggeredArgs
0x18001094a  mov     ebx, 0C0000001h
0x18001094f  jmp     loc_180010CA4
0x180010954  lea     rdx, aWnfForTelemetr; "Wnf for telemetry target process ID rec"...
0x18001095b  lea     rsi, ?TelemetrySink@g@@3U0@A; TelemetrySink g::TelemetrySink
0x180010962  mov     rcx, rsi; this
0x180010965  call    ?LogDiagnostic@TelemetrySink@@UEAAXPEBGU_GUID@@@Z; TelemetrySink::LogDiagnostic(ushort const *,_GUID)
0x18001096a  mov     [rsp+4E8h+hKey], rbx
0x18001096f  xor     edx, edx
0x180010971  lea     rcx, [rsp+4E8h+hKey]
0x180010976  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001097b  mov     [rsp+4E8h+lpdwDisposition], rbx; lpdwDisposition
0x180010980  lea     rax, [rsp+4E8h+hKey]
0x180010985  mov     [rsp+4E8h+phkResult], rax; phkResult
0x18001098a  mov     [rsp+4E8h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18001098f  mov     [rsp+4E8h+samDesired], 20006h; samDesired
0x180010997  mov     [rsp+4E8h+dwOptions], ebx; dwOptions
0x18001099b  xor     r9d, r9d; lpClass
0x18001099e  xor     r8d, r8d; Reserved
0x1800109a1  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Direct3D"
0x1800109a8  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800109af  call    cs:__imp_RegCreateKeyExW
0x1800109b5  test    eax, eax
0x1800109b7  jnz     short loc_1800109E9
0x1800109b9  mov     [rsp+4E8h+samDesired], 4; cbData
0x1800109c1  lea     rax, [rsp+4E8h+Data]
0x1800109c9  mov     qword ptr [rsp+4E8h+dwOptions], rax; lpData
0x1800109ce  mov     r9d, 4; dwType
0x1800109d4  xor     r8d, r8d; Reserved
0x1800109d7  lea     rdx, ValueName; "LastTelemetryChangeStamp"
0x1800109de  mov     rcx, [rsp+4E8h+hKey]; hKey
0x1800109e3  call    cs:__imp_RegSetValueExW
0x1800109e9  cmp     [rsp+4E8h+arg_28], 4
0x1800109f1  jnz     loc_180010C99
0x1800109f7  mov     edi, [r14]
0x1800109fa  mov     [rsp+4E8h+var_478], edi
0x1800109fe  lea     r14, ?ShutdownCritsect@g@@3Vcritical_section@wil@@A; wil::critical_section g::ShutdownCritsect
0x180010a05  mov     rcx, r14; lpCriticalSection
0x180010a08  call    cs:__imp_EnterCriticalSection
0x180010a0e  mov     [rsp+4E8h+var_410], r14
0x180010a16  mov     rcx, cs:?spTraceConsumer@g@@3V?$shared_ptr@UServiceTraceConsumer@@@std@@A; this
0x180010a1d  test    rcx, rcx
0x180010a20  jz      loc_180010C87
0x180010a26  mov     edx, edi; unsigned int
0x180010a28  call    ?IsProcessTrackedForTelemetry@PresentTraceConsumerCore@@QEAA_NK@Z; PresentTraceConsumerCore::IsProcessTrackedForTelemetry(ulong)
0x180010a2d  test    al, al
0x180010a2f  jnz     loc_180010C87
0x180010a35  mov     [rsp+4E8h+var_440], rsi
0x180010a3d  lea     r8, [rsp+4E8h+var_440]
0x180010a45  lea     rdx, [rsp+4E8h+var_478]
0x180010a4a  lea     rcx, [rsp+4E8h+var_468]
0x180010a52  call    ??$make_shared@UTelemetryEventConsumer@@AEAKPEAUTelemetrySink@@@std@@YA?AV?$shared_ptr@UTelemetryEventConsumer@@@0@AEAK$$QEAPEAUTelemetrySink@@@Z; std::make_shared<TelemetryEventConsumer,ulong &,TelemetrySink *>(ulong &,TelemetrySink * &&)
0x180010a57  mov     rdi, [rax]
0x180010a5a  mov     [rsp+4E8h+var_408], rdi
0x180010a62  mov     rsi, [rax+8]
0x180010a66  mov     [rsp+4E8h+var_400], rsi
0x180010a6e  mov     [rax], rbx
0x180010a71  mov     [rax+8], rbx
0x180010a75  mov     rcx, qword ptr [rsp+4E8h+var_468.Data4]; this
0x180010a7d  test    rcx, rcx
0x180010a80  jz      short loc_180010A87
0x180010a82  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180010a87  test    rdi, rdi
0x180010a8a  jz      loc_180010C79
0x180010a90  mov     r10, cs:?spTraceConsumer@g@@3V?$shared_ptr@UServiceTraceConsumer@@@std@@A; std::shared_ptr<ServiceTraceConsumer> g::spTraceConsumer
0x180010a97  mov     rax, [r10]
0x180010a9a  mov     r9, [rax+28h]
0x180010a9e  lea     rdx, [rsp+4E8h+var_408]
0x180010aa6  lea     rcx, [rsp+4E8h+var_428]
0x180010aae  call    ??0?$shared_ptr@UPresentEvent@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(std::shared_ptr<PresentEvent> const &)
0x180010ab3  mov     r8, rax
0x180010ab6  mov     r15d, [rsp+4E8h+var_478]
0x180010abb  mov     edx, r15d
0x180010abe  mov     rcx, r10
0x180010ac1  mov     rax, r9
0x180010ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ac9  call    ?Provider@TraceProvider@gpm@@SAPEBU_tlgProvider_t@@XZ; gpm::TraceProvider::Provider(void)
0x180010ace  mov     r14, rax
0x180010ad1  mov     eax, [rax]
0x180010ad3  cmp     eax, 5
0x180010ad6  jbe     loc_180010C79
0x180010adc  mov     edx, 1
0x180010ae1  mov     rcx, r14
0x180010ae4  call    _tlgKeywordOn
0x180010ae9  test    al, al
0x180010aeb  jz      loc_180010C79
0x180010af1  lea     rdx, [rsp+4E8h+var_108]
0x180010af9  mov     rcx, cs:?spTraceConsumer@g@@3V?$shared_ptr@UServiceTraceConsumer@@@std@@A; std::shared_ptr<ServiceTraceConsumer> g::spTraceConsumer
0x180010b00  call    ?GetCounters@PresentTraceConsumerCore@@QEAA?AUCounters@1@XZ; PresentTraceConsumerCore::GetCounters(void)
0x180010b05  nop
0x180010b06  mov     eax, [rax+54h]
0x180010b09  mov     [rsp+4E8h+var_478], eax
0x180010b0d  lea     rdx, [rsp+4E8h+var_1E8]
0x180010b15  mov     rcx, cs:?spTraceConsumer@g@@3V?$shared_ptr@UServiceTraceConsumer@@@std@@A; std::shared_ptr<ServiceTraceConsumer> g::spTraceConsumer
0x180010b1c  call    ?GetCounters@PresentTraceConsumerCore@@QEAA?AUCounters@1@XZ; PresentTraceConsumerCore::GetCounters(void)
0x180010b21  nop
0x180010b22  mov     eax, [rax+50h]
0x180010b25  mov     [rsp+4E8h+var_450], eax
0x180010b2c  lea     rdx, [rsp+4E8h+var_2C8]
0x180010b34  mov     rcx, cs:?spTraceConsumer@g@@3V?$shared_ptr@UServiceTraceConsumer@@@std@@A; std::shared_ptr<ServiceTraceConsumer> g::spTraceConsumer
0x180010b3b  call    ?GetCounters@PresentTraceConsumerCore@@QEAA?AUCounters@1@XZ; PresentTraceConsumerCore::GetCounters(void)
0x180010b40  nop
0x180010b41  add     rax, 14h
0x180010b45  mov     [rsp+4E8h+var_428], rax
0x180010b4d  mov     [rsp+4E8h+var_420], 14h
0x180010b58  lea     rdx, [rsp+4E8h+var_3A8]
0x180010b60  mov     rcx, cs:?spTraceConsumer@g@@3V?$shared_ptr@UServiceTraceConsumer@@@std@@A; std::shared_ptr<ServiceTraceConsumer> g::spTraceConsumer
0x180010b67  call    ?GetCounters@PresentTraceConsumerCore@@QEAA?AUCounters@1@XZ; PresentTraceConsumerCore::GetCounters(void)
0x180010b6c  mov     qword ptr [rsp+4E8h+var_468.Data1], rax
0x180010b74  mov     dword ptr [rsp+4E8h+var_468.Data4], 14h
0x180010b7f  mov     rax, [rdi]
0x180010b82  mov     rcx, rdi
0x180010b85  mov     rax, [rax+98h]
0x180010b8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b91  mov     [rsp+4E8h+var_44C], eax
0x180010b98  mov     [rsp+4E8h+var_418], rdi
0x180010ba0  mov     [rsp+4E8h+var_448], r15d
0x180010ba8  mov     dword ptr [rsp+4E8h+var_440], 1
0x180010bb3  mov     [rsp+4E8h+var_430], 1000000h
0x180010bbf  lea     rax, [rsp+4E8h+var_478]
0x180010bc4  mov     [rsp+4E8h+var_488], rax
0x180010bc9  lea     rax, [rsp+4E8h+var_450]
0x180010bd1  mov     [rsp+4E8h+var_490], rax
0x180010bd6  lea     rax, [rsp+4E8h+var_428]
0x180010bde  mov     [rsp+4E8h+var_498], rax
0x180010be3  lea     rax, [rsp+4E8h+var_468]
0x180010beb  mov     [rsp+4E8h+var_4A0], rax
0x180010bf0  lea     rax, [rsp+4E8h+var_44C]
0x180010bf8  mov     [rsp+4E8h+lpdwDisposition], rax
0x180010bfd  lea     rax, [rsp+4E8h+var_418]
0x180010c05  mov     [rsp+4E8h+phkResult], rax
0x180010c0a  lea     rax, [rsp+4E8h+var_448]
0x180010c12  mov     [rsp+4E8h+lpSecurityAttributes], rax
0x180010c17  lea     rax, [rsp+4E8h+var_440]
0x180010c1f  mov     qword ptr [rsp+4E8h+samDesired], rax
0x180010c24  lea     rax, [rsp+4E8h+var_430]
0x180010c2c  mov     qword ptr [rsp+4E8h+dwOptions], rax
0x180010c31  lea     rdx, unk_180039CD0
0x180010c38  mov     rcx, r14
0x180010c3b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U1@U2@U_tlgWrapperPtrSize@@U3@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@434AEBU_tlgWrapperPtrSize@@544@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperPtrSize,_tlgWrapperPtrSize,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperPtrSize const &,_tlgWrapperPtrSize const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180010c40  nop
0x180010c41  lea     rcx, [rsp+4E8h+var_318]
0x180010c49  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180010c4e  nop
0x180010c4f  lea     rcx, [rsp+4E8h+var_238]
0x180010c57  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180010c5c  nop
0x180010c5d  lea     rcx, [rsp+4E8h+var_158]
0x180010c65  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180010c6a  nop
0x180010c6b  lea     rcx, [rsp+4E8h+var_78]
0x180010c73  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180010c78  nop
0x180010c79  test    rsi, rsi
0x180010c7c  jz      short loc_180010C87
0x180010c7e  mov     rcx, rsi; this
0x180010c81  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180010c86  nop
0x180010c87  lea     rcx, [rsp+4E8h+var_410]
0x180010c8f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180010c94  nop
0x180010c95  jmp     short loc_180010C99
0x180010c97  xor     ebx, ebx
0x180010c99  lea     rcx, [rsp+4E8h+hKey]
0x180010c9e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180010ca3  nop
0x180010ca4  lea     rcx, [rsp+4E8h+var_438]
0x180010cac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010cb1  nop
0x180010cb2  lea     rcx, [rsp+4E8h+var_3F8]; this
0x180010cba  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x180010cbf  mov     eax, ebx
0x180010cc1  mov     rcx, [rsp+4E8h+var_28]
0x180010cc9  xor     rcx, rsp; StackCookie
0x180010ccc  call    __security_check_cookie
0x180010cd1  lea     r11, [rsp+4E8h+var_18]
0x180010cd9  mov     rbx, [r11+20h]
0x180010cdd  mov     rsi, [r11+30h]
0x180010ce1  mov     rsp, r11
0x180010ce4  pop     r15
0x180010ce6  pop     r14
0x180010ce8  pop     rdi
0x180010ce9  retn
```
