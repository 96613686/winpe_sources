# ServiceMain(ulong,ushort * *)

- ea: `0x180038f10`
- end: `0x18003933b`
- name: `?ServiceMain@@YAJKPEAPEAG@Z`
- size: `1067`
- prototype: `__int64 __fastcall(int, LPCWSTR *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18002a928`
- `0x18002e81c`
- `0x1800384a0`
- `0x180038ce0`
- `0x180038f10`
- `0x180039528`
- `0x180039564`
- `0x1800395b0`
- `0x180039624`
- `0x180039768`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038f9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038f9e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003931b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003931b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180039126`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003915f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180039126`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003915f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039003`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003903c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039099`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800390d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003916d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039003`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003903c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039099`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800390d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003916d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800392ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800392c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800392ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800392c8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800392a8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800392a8`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x180038ff9`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x180039032`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x18003908f`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x180038ff9`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x180039032`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x18003908f`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800390c4`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800390c4`

## string_xrefs

- `0x1800392e3`: `Failed to uninitialize service. hr = 0x%08x`
- `0x1800390eb`: `Failed to register service handler function with SCM. hr = 0x%08x`
- `0x180039110`: `Failed to update service status to start pending. hr = 0x%08x`
- `0x1800391dc`: `** Service starting **`
- `0x180039149`: `Failed to create shutdown event. hr = 0x%08x`
- `0x180039182`: `Failed to create COM registration event. hr = 0x%08x`
- `0x180039236`: `Failed to initialize service. hr = 0x%08x`
- `0x18003925b`: `Failed to update service status to started. hr = 0x%08x`
- `0x18003920f`: `WaaSMedic service module version: %ws`
- `0x180039267`: `WaaSMedic service is now running.`
- `0x180039303`: `Stopping the service since initialization/execution failed. hr = 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ServiceMain(int a1, LPCWSTR *a2)
{
  char v4; // r15
  HANDLE EventW; // rdi
  HANDLE v6; // r14
  unsigned int v7; // ebx
  signed int v8; // eax
  signed int LastError; // eax
  const unsigned __int16 *v10; // rdx
  signed int v11; // eax
  signed int v12; // eax
  int updated; // eax
  signed int v14; // eax
  signed int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  HANDLE WaitHandle[2]; // [rsp+40h] [rbp-10h] BYREF
  int v22; // [rsp+90h] [rbp+40h] BYREF
  int v23; // [rsp+A0h] [rbp+50h] BYREF
  int v24; // [rsp+A8h] [rbp+58h] BYREF

  ServiceStatus.dwServiceType = 32;
  WaitHandle[0] = 0;
  ::WaitHandle = 0;
  hObject = 0;
  hEvent = 0;
  ServiceStatus.dwCurrentState = 1;
  v4 = 0;
  *(_QWORD *)&ServiceStatus.dwControlsAccepted = 1;
  EventW = 0;
  v6 = 0;
  hServiceStatus = 0;
  dword_1800A568C = 0;
  dword_1800A5690 = 0;
  *(_QWORD *)&ServiceStatus.dwServiceSpecificExitCode = 0;
  ServiceStatus.dwWaitHint = 30000;
  v22 = 0;
  EnterCriticalSection(&gcsServiceMain);
  if ( !a1 )
  {
    v7 = -2147024809;
    goto LABEL_45;
  }
  if ( !qword_1800A56A0 )
  {
    v7 = -2147418113;
    goto LABEL_45;
  }
  EnableLogging();
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicDllLoadWithACGEnabled>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WaaSMedicDllLoadWithACGEnabled>::GetImpl'::`2'::impl) )
  {
    v23 = 1;
    if ( (unsigned int)SetProcessMitigationPolicy(16, &v23, 4) )
    {
      v24 = 1;
      if ( (unsigned int)SetProcessMitigationPolicy(2, &v24, 4) )
        goto LABEL_22;
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      LogLevelW(2u, L"Failed to set dynamic code execution mitigation policy options: 0x%08x", v7);
    }
    else
    {
      v8 = GetLastError();
      v7 = v8;
      if ( v8 > 0 )
        v7 = (unsigned __int16)v8 | 0x80070000;
      LogLevelW(2u, L"Failed to set image mitigation policy options: 0x%08x", v7);
    }
    if ( (v7 & 0x80000000) != 0 )
    {
      v10 = L"Failed to enable mitigations. hr = 0x%08x";
LABEL_16:
      LogLevelW(2u, v10, v7);
      goto LABEL_45;
    }
  }
  else
  {
    v22 |= 1u;
    if ( !(unsigned int)SetProcessMitigationPolicy(16, &v22, 4) )
    {
      v11 = GetLastError();
      v7 = v11;
      if ( v11 > 0 )
        v7 = (unsigned __int16)v11 | 0x80070000;
      v10 = L"Failed to set image mitigation policy options: 0x%08x";
      goto LABEL_16;
    }
  }
LABEL_22:
  hServiceStatus = RegisterServiceCtrlHandlerExW(*a2, ServiceHandler, 0);
  if ( !hServiceStatus )
  {
    v12 = GetLastError();
    v7 = v12;
    if ( v12 > 0 )
      v7 = (unsigned __int16)v12 | 0x80070000;
    v10 = L"Failed to register service handler function with SCM. hr = 0x%08x";
    goto LABEL_16;
  }
  updated = UpdateServiceStatus(2u, 0, 0x7530u);
  v7 = updated;
  if ( updated < 0 )
  {
    LogLevelW(2u, L"Failed to update service status to start pending. hr = 0x%08x", (unsigned int)updated);
    goto LABEL_45;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  if ( !EventW )
  {
    v14 = GetLastError();
    v7 = v14;
    if ( v14 > 0 )
      v7 = (unsigned __int16)v14 | 0x80070000;
    v10 = L"Failed to create shutdown event. hr = 0x%08x";
    goto LABEL_16;
  }
  v6 = CreateEventW(0, 0, 0, 0);
  if ( !v6 )
  {
    v15 = GetLastError();
    v7 = v15;
    if ( v15 > 0 )
      v7 = (unsigned __int16)v15 | 0x80070000;
    v10 = L"Failed to create COM registration event. hr = 0x%08x";
    goto LABEL_16;
  }
  v16 = (*(__int64 (__fastcall **)(HANDLE *, LPCWSTR, HANDLE, __int64 (__fastcall *)(), _QWORD, int))(qword_1800A56A0 + 192))(
          WaitHandle,
          *a2,
          EventW,
          StopService,
          0,
          8);
  v7 = v16;
  if ( v16 )
  {
    if ( v16 > 0 )
      v7 = (unsigned __int16)v16 | 0x80070000;
    v10 = L"Failed to register stop callback handler. hr = 0x%08x";
    goto LABEL_16;
  }
  LogLevelW(4u, L"** Service starting **");
  LogLevelW(5u, L"Will output verbose output.");
  WaasMedic::MiscUtil::PopulateClientVersionString();
  LogLevelW(4u, L"WaaSMedic service module version: %ws", &gc_pszVersionString);
  hEvent = v6;
  v6 = 0;
  v17 = InitializeService(EventW);
  v7 = v17;
  if ( v17 >= 0 )
  {
    v4 = 1;
    v18 = UpdateServiceStatus(4u, 0, 0);
    v7 = v18;
    if ( v18 >= 0 )
    {
      LogLevelW(4u, L"WaaSMedic service is now running.");
      SvcAddRef();
      SvcRelease();
      hObject = EventW;
      EventW = 0;
      ::WaitHandle = WaitHandle[0];
      WaitHandle[0] = 0;
    }
    else
    {
      LogLevelW(2u, L"Failed to update service status to started. hr = 0x%08x", (unsigned int)v18);
    }
  }
  else
  {
    LogLevelW(2u, L"Failed to initialize service. hr = 0x%08x", (unsigned int)v17);
  }
LABEL_45:
  if ( WaitHandle[0] )
  {
    UnregisterWaitEx(WaitHandle[0], (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    WaitHandle[0] = 0;
  }
  if ( EventW )
    CloseHandle(EventW);
  if ( v6 )
    CloseHandle(v6);
  if ( (v7 & 0x80000000) != 0 )
  {
    if ( v4 )
    {
      v19 = UninitializeService();
      if ( v19 < 0 )
        LogLevelW(2u, L"Failed to uninitialize service. hr = 0x%08x", (unsigned int)v19);
    }
    UpdateServiceStatus(1u, v7, 0);
    LogLevelW(4u, L"Stopping the service since initialization/execution failed. hr = 0x%08x", v7);
  }
  LeaveCriticalSection(&gcsServiceMain);
  return v7;
}

```

## disassembly

```asm
0x180038f10  mov     [rsp-38h+arg_8], rbx
0x180038f15  push    rbp
0x180038f16  push    rsi
0x180038f17  push    rdi
0x180038f18  push    r12
0x180038f1a  push    r13
0x180038f1c  push    r14
0x180038f1e  push    r15
0x180038f20  mov     rbp, rsp
0x180038f23  sub     rsp, 50h
0x180038f27  xor     r12d, r12d
0x180038f2a  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x180038f34  mov     ebx, ecx
0x180038f36  mov     [rbp+WaitHandle], r12
0x180038f3a  lea     rcx, ?gcsServiceMain@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180038f41  mov     cs:WaitHandle, r12
0x180038f48  mov     rsi, rdx
0x180038f4b  mov     cs:hObject, r12
0x180038f52  lea     eax, [r12+1]
0x180038f57  mov     cs:hEvent, r12
0x180038f5e  mov     cs:ServiceStatus.dwCurrentState, eax
0x180038f64  mov     r15b, r12b
0x180038f67  mov     qword ptr cs:ServiceStatus.dwControlsAccepted, rax
0x180038f6e  mov     edi, r12d
0x180038f71  mov     r14d, r12d
0x180038f74  mov     cs:hServiceStatus, r12
0x180038f7b  mov     cs:dword_1800A568C, r12d
0x180038f82  mov     cs:dword_1800A5690, r12d
0x180038f89  mov     qword ptr cs:ServiceStatus.dwServiceSpecificExitCode, r12
0x180038f90  mov     cs:ServiceStatus.dwWaitHint, 7530h
0x180038f9a  mov     [rbp+arg_0], r12d
0x180038f9e  call    cs:__imp_EnterCriticalSection
0x180038fa4  lea     r13d, [r12+2]
0x180038fa9  test    ebx, ebx
0x180038fab  jnz     short loc_180038FB7
0x180038fad  mov     ebx, 80070057h
0x180038fb2  jmp     loc_18003929B
0x180038fb7  cmp     cs:qword_1800A56A0, r12
0x180038fbe  jnz     short loc_180038FCA
0x180038fc0  mov     ebx, 8000FFFFh
0x180038fc5  jmp     loc_18003929B
0x180038fca  call    ?EnableLogging@@YAXXZ; EnableLogging(void)
0x180038fcf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WaaSMedicDllLoadWithACGEnabled@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WaaSMedicDllLoadWithACGEnabled@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicDllLoadWithACGEnabled> `wil::Feature<__WilFeatureTraits_Feature_WaaSMedicDllLoadWithACGEnabled>::GetImpl(void)'::`2'::impl
0x180038fd6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WaaSMedicDllLoadWithACGEnabled@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicDllLoadWithACGEnabled>::__private_IsEnabled(void)
0x180038fdb  mov     ecx, 10h
0x180038fe0  test    al, al
0x180038fe2  jz      loc_180039081
0x180038fe8  lea     ebx, [rcx-0Ch]
0x180038feb  mov     [rbp+arg_10], 1
0x180038ff2  mov     r8d, ebx
0x180038ff5  lea     rdx, [rbp+arg_10]
0x180038ff9  call    cs:__imp_SetProcessMitigationPolicy
0x180038fff  test    eax, eax
0x180039001  jnz     short loc_180039021
0x180039003  call    cs:__imp_GetLastError
0x180039009  mov     ebx, eax
0x18003900b  test    eax, eax
0x18003900d  jle     short loc_180039018
0x18003900f  movzx   ebx, ax
0x180039012  or      ebx, 80070000h
0x180039018  lea     rdx, aFailedToSetIma; "Failed to set image mitigation policy o"...
0x18003901f  jmp     short loc_180039058
0x180039021  mov     r8, rbx
0x180039024  mov     [rbp+arg_18], 1
0x18003902b  lea     rdx, [rbp+arg_18]
0x18003902f  mov     ecx, r13d
0x180039032  call    cs:__imp_SetProcessMitigationPolicy
0x180039038  test    eax, eax
0x18003903a  jnz     short loc_1800390B7
0x18003903c  call    cs:__imp_GetLastError
0x180039042  mov     ebx, eax
0x180039044  test    eax, eax
0x180039046  jle     short loc_180039051
0x180039048  movzx   ebx, ax
0x18003904b  or      ebx, 80070000h
0x180039051  lea     rdx, aFailedToSetDyn; "Failed to set dynamic code execution mi"...
0x180039058  mov     al, r13b
0x18003905b  mov     r8d, ebx
0x18003905e  movzx   ecx, al; unsigned __int8
0x180039061  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180039066  test    ebx, ebx
0x180039068  jns     short loc_1800390B7
0x18003906a  lea     rdx, aFailedToEnable; "Failed to enable mitigations. hr = 0x%0"...
0x180039071  mov     r8d, ebx
0x180039074  mov     ecx, r13d; unsigned __int8
0x180039077  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003907c  jmp     loc_18003929B
0x180039081  or      [rbp+arg_0], 1
0x180039085  lea     rdx, [rbp+arg_0]
0x180039089  mov     r8d, 4
0x18003908f  call    cs:__imp_SetProcessMitigationPolicy
0x180039095  test    eax, eax
0x180039097  jnz     short loc_1800390B7
0x180039099  call    cs:__imp_GetLastError
0x18003909f  mov     ebx, eax
0x1800390a1  test    eax, eax
0x1800390a3  jle     short loc_1800390AE
0x1800390a5  movzx   ebx, ax
0x1800390a8  or      ebx, 80070000h
0x1800390ae  lea     rdx, aFailedToSetIma; "Failed to set image mitigation policy o"...
0x1800390b5  jmp     short loc_180039071
0x1800390b7  mov     rcx, [rsi]; lpServiceName
0x1800390ba  lea     rdx, ServiceHandler; lpHandlerProc
0x1800390c1  xor     r8d, r8d; lpContext
0x1800390c4  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800390ca  mov     cs:hServiceStatus, rax
0x1800390d1  test    rax, rax
0x1800390d4  jnz     short loc_1800390F7
0x1800390d6  call    cs:__imp_GetLastError
0x1800390dc  mov     ebx, eax
0x1800390de  test    eax, eax
0x1800390e0  jle     short loc_1800390EB
0x1800390e2  movzx   ebx, ax
0x1800390e5  or      ebx, 80070000h
0x1800390eb  lea     rdx, aFailedToRegist_4; "Failed to register service handler func"...
0x1800390f2  jmp     loc_180039071
0x1800390f7  xor     edx, edx; unsigned int
0x1800390f9  mov     r8d, 7530h; unsigned int
0x1800390ff  mov     ecx, r13d; unsigned int
0x180039102  call    ?UpdateServiceStatus@@YAJKKK@Z; UpdateServiceStatus(ulong,ulong,ulong)
0x180039107  mov     ebx, eax
0x180039109  test    eax, eax
0x18003910b  jns     short loc_18003911C
0x18003910d  mov     r8d, eax
0x180039110  lea     rdx, aFailedToUpdate; "Failed to update service status to star"...
0x180039117  jmp     loc_180039074
0x18003911c  xor     r9d, r9d; lpName
0x18003911f  xor     r8d, r8d; bInitialState
0x180039122  xor     edx, edx; bManualReset
0x180039124  xor     ecx, ecx; lpEventAttributes
0x180039126  call    cs:__imp_CreateEventW
0x18003912c  mov     rdi, rax
0x18003912f  test    rax, rax
0x180039132  jnz     short loc_180039155
0x180039134  call    cs:__imp_GetLastError
0x18003913a  mov     ebx, eax
0x18003913c  test    eax, eax
0x18003913e  jle     short loc_180039149
0x180039140  movzx   ebx, ax
0x180039143  or      ebx, 80070000h
0x180039149  lea     rdx, aFailedToCreate_8; "Failed to create shutdown event. hr = 0"...
0x180039150  jmp     loc_180039071
0x180039155  xor     r9d, r9d; lpName
0x180039158  xor     r8d, r8d; bInitialState
0x18003915b  xor     edx, edx; bManualReset
0x18003915d  xor     ecx, ecx; lpEventAttributes
0x18003915f  call    cs:__imp_CreateEventW
0x180039165  mov     r14, rax
0x180039168  test    rax, rax
0x18003916b  jnz     short loc_18003918E
0x18003916d  call    cs:__imp_GetLastError
0x180039173  mov     ebx, eax
0x180039175  test    eax, eax
0x180039177  jle     short loc_180039182
0x180039179  movzx   ebx, ax
0x18003917c  or      ebx, 80070000h
0x180039182  lea     rdx, aFailedToCreate_14; "Failed to create COM registration event"...
0x180039189  jmp     loc_180039071
0x18003918e  mov     rax, cs:qword_1800A56A0
0x180039195  lea     r9, StopService
0x18003919c  mov     rdx, [rsi]
0x18003919f  lea     rcx, [rbp+WaitHandle]
0x1800391a3  mov     [rsp+50h+var_28], 8
0x1800391ab  mov     r8, rdi
0x1800391ae  mov     [rsp+50h+var_30], r12
0x1800391b3  mov     rax, [rax+0C0h]
0x1800391ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800391bf  mov     ebx, eax
0x1800391c1  test    eax, eax
0x1800391c3  jz      short loc_1800391DC
0x1800391c5  jle     short loc_1800391D0
0x1800391c7  movzx   ebx, ax
0x1800391ca  or      ebx, 80070000h
0x1800391d0  lea     rdx, aFailedToRegist_2; "Failed to register stop callback handle"...
0x1800391d7  jmp     loc_180039071
0x1800391dc  lea     rdx, aServiceStartin; "** Service starting **"
0x1800391e3  mov     ecx, 4; unsigned __int8
0x1800391e8  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800391ed  lea     rdx, aWillOutputVerb; "Will output verbose output."
0x1800391f4  mov     ecx, 5; unsigned __int8
0x1800391f9  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800391fe  call    ?PopulateClientVersionString@MiscUtil@WaasMedic@@SAJXZ; WaasMedic::MiscUtil::PopulateClientVersionString(void)
0x180039203  lea     r8, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x18003920a  mov     ecx, 4; unsigned __int8
0x18003920f  lea     rdx, aWaasmedicServi_3; "WaaSMedic service module version: %ws"
0x180039216  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003921b  mov     cs:hEvent, r14
0x180039222  mov     rcx, rdi; void *
0x180039225  mov     r14, r12
0x180039228  call    ?InitializeService@@YAJPEAX@Z; InitializeService(void *)
0x18003922d  mov     ebx, eax
0x18003922f  test    eax, eax
0x180039231  jns     short loc_180039242
0x180039233  mov     r8d, eax
0x180039236  lea     rdx, aFailedToInitia_0; "Failed to initialize service. hr = 0x%0"...
0x18003923d  jmp     loc_180039074
0x180039242  xor     edx, edx; unsigned int
0x180039244  xor     r8d, r8d; unsigned int
0x180039247  mov     r15b, 1
0x18003924a  lea     ecx, [rdx+4]; unsigned int
0x18003924d  call    ?UpdateServiceStatus@@YAJKKK@Z; UpdateServiceStatus(ulong,ulong,ulong)
0x180039252  mov     ebx, eax
0x180039254  test    eax, eax
0x180039256  jns     short loc_180039267
0x180039258  mov     r8d, eax
0x18003925b  lea     rdx, aFailedToUpdate_1; "Failed to update service status to star"...
0x180039262  jmp     loc_180039074
0x180039267  lea     rdx, aWaasmedicServi_1; "WaaSMedic service is now running."
0x18003926e  mov     ecx, 4; unsigned __int8
0x180039273  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180039278  call    ?SvcAddRef@@YAJXZ; SvcAddRef(void)
0x18003927d  call    ?SvcRelease@@YAJXZ; SvcRelease(void)
0x180039282  mov     rax, [rbp+WaitHandle]
0x180039286  mov     cs:hObject, rdi
0x18003928d  mov     rdi, r12
0x180039290  mov     cs:WaitHandle, rax
0x180039297  mov     [rbp+WaitHandle], r12
0x18003929b  mov     rcx, [rbp+WaitHandle]; WaitHandle
0x18003929f  test    rcx, rcx
0x1800392a2  jz      short loc_1800392B2
0x1800392a4  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800392a8  call    cs:__imp_UnregisterWaitEx
0x1800392ae  mov     [rbp+WaitHandle], r12
0x1800392b2  test    rdi, rdi
0x1800392b5  jz      short loc_1800392C0
0x1800392b7  mov     rcx, rdi; hObject
0x1800392ba  call    cs:__imp_CloseHandle
0x1800392c0  test    r14, r14
0x1800392c3  jz      short loc_1800392CE
0x1800392c5  mov     rcx, r14; hObject
0x1800392c8  call    cs:__imp_CloseHandle
0x1800392ce  test    ebx, ebx
0x1800392d0  jns     short loc_180039314
0x1800392d2  test    r15b, r15b
0x1800392d5  jz      short loc_1800392F2
0x1800392d7  call    ?UninitializeService@@YAJXZ; UninitializeService(void)
0x1800392dc  test    eax, eax
0x1800392de  jns     short loc_1800392F2
0x1800392e0  mov     r8d, eax
0x1800392e3  lea     rdx, aFailedToUninit; "Failed to uninitialize service. hr = 0x"...
0x1800392ea  mov     ecx, r13d; unsigned __int8
0x1800392ed  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800392f2  xor     r8d, r8d; unsigned int
0x1800392f5  mov     edx, ebx; unsigned int
0x1800392f7  lea     ecx, [r8+1]; unsigned int
0x1800392fb  call    ?UpdateServiceStatus@@YAJKKK@Z; UpdateServiceStatus(ulong,ulong,ulong)
0x180039300  mov     r8d, ebx
0x180039303  lea     rdx, aStoppingTheSer; "Stopping the service since initializati"...
0x18003930a  mov     ecx, 4; unsigned __int8
0x18003930f  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180039314  lea     rcx, ?gcsServiceMain@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003931b  call    cs:__imp_LeaveCriticalSection
0x180039321  mov     eax, ebx
0x180039323  mov     rbx, [rsp+50h+arg_8]
0x18003932b  add     rsp, 50h
0x18003932f  pop     r15
0x180039331  pop     r14
0x180039333  pop     r13
0x180039335  pop     r12
0x180039337  pop     rdi
0x180039338  pop     rsi
0x180039339  pop     rbp
0x18003933a  retn
```
