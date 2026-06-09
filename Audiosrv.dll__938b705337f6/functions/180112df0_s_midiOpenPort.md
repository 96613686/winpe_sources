# s_midiOpenPort

- ea: `0x180112df0`
- end: `0x180113111`
- name: `s_midiOpenPort`
- size: `801`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x1800128bc`
- `0x18001b3d0`
- `0x1800c015c`
- `0x1800cfd9c`
- `0x1800d0764`
- `0x1800d8458`
- `0x1800d8530`
- `0x1800d87e4`
- `0x1800d8800`
- `0x1800dc3e4`
- `0x1800dc604`
- `0x1800dc628`
- `0x180112df0`
- `0x18013a358`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011303a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011303a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180113056`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180113056`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801130a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801130bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801130a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801130bb`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180113082`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180113082`
- `RPCRT4!RpcImpersonateClient` at `0x180113019`
- `RPCRT4!RpcImpersonateClient` at `0x180113019`
- `RPCRT4!RpcRevertToSelf` at `0x180113095`
- `RPCRT4!RpcRevertToSelf` at `0x180113095`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180112ff5`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180112ff5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18011302c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18011302c`
- `ksuser!KsCreatePin2` at `0x180112fd1`
- `ksuser!KsCreatePin2` at `0x180112fd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801130c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801130c4`

## string_xrefs

- `0x180112e8f`: `s_midiOpenPort`
- `0x180112edb`: `s_midiOpenPort`
- `0x1801130d1`: `s_midiOpenPort`

## pseudocode

```c
__int64 __fastcall s_midiOpenPort(RPC_BINDING_HANDLE BindingHandle, unsigned __int16 *a2, HANDLE *a3)
{
  unsigned __int16 *v3; // r14
  const unsigned __int16 *v5; // rbx
  __int64 v7; // rsi
  void *v8; // rax
  void *v9; // r15
  struct _FILETIME v10; // rbx
  void *v11; // rax
  void *v12; // r15
  struct _FILETIME v13; // rbx
  signed int v14; // edi
  int KsMidiDeviceInfo; // eax
  unsigned int v16; // edx
  int v17; // eax
  char *v18; // r15
  HRESULT v19; // eax
  RPC_STATUS v20; // eax
  signed int LastError; // eax
  void *v22; // rbx
  HANDLE CurrentProcess; // rax
  unsigned __int16 *v25; // [rsp+40h] [rbp-99h] BYREF
  HANDLE FilterHandle; // [rsp+48h] [rbp-91h] BYREF
  void *ConnectionHandle; // [rsp+50h] [rbp-89h] BYREF
  HANDLE TargetHandle; // [rsp+58h] [rbp-81h] BYREF
  __int64 v29; // [rsp+60h] [rbp-79h] BYREF
  __int64 v30; // [rsp+68h] [rbp-71h] BYREF
  $58C2C1BF6568EE28BD9B872E6BA03976 Connect; // [rsp+70h] [rbp-69h] BYREF
  int v32; // [rsp+B8h] [rbp-21h]
  __int64 v33; // [rsp+BCh] [rbp-1Dh]
  int v34; // [rsp+C4h] [rbp-15h]
  GUID v35; // [rsp+C8h] [rbp-11h]
  GUID v36; // [rsp+D8h] [rbp-1h]
  GUID v37; // [rsp+E8h] [rbp+Fh]
  unsigned int v39; // [rsp+150h] [rbp+77h] BYREF
  unsigned int Pid; // [rsp+158h] [rbp+7Fh] BYREF

  v3 = 0;
  v5 = a2;
  v25 = 0;
  v39 = 0;
  v7 = -1;
  ConnectionHandle = 0;
  FilterHandle = (HANDLE)-1LL;
  memset_0(&Connect, 0, 0x88u);
  Pid = 0;
  TargetHandle = (HANDLE)-1LL;
  v30 = 0;
  v29 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl'::`2'::impl) )
  {
    v8 = operator new[](0x38u, (const struct std::nothrow_t *)&std::nothrow);
    v9 = v8;
    if ( v8 )
    {
      v10 = g_AudioHealthMonitor;
      AudioSrvTelemetryProvider::Instance();
      v8 = (void *)CWatchdogTimer<1>::CWatchdogTimer<1>(v9, v10);
      v5 = a2;
    }
    std::unique_ptr<CWatchdogTimer<1>>::reset(&v30, v8);
  }
  else
  {
    v11 = operator new[](0x38u, (const struct std::nothrow_t *)&std::nothrow);
    v12 = v11;
    if ( v11 )
    {
      v13 = g_AudioHealthMonitor;
      AudioSrvTelemetryProvider::Instance();
      v11 = (void *)CWatchdogTimer_Old<1>::CWatchdogTimer_Old<1>(v12, v13);
      v5 = a2;
    }
    std::unique_ptr<CWatchdogTimer_Old<1>>::reset(&v29, v11);
  }
  if ( a3 )
  {
    KsMidiDeviceInfo = GetKsMidiDeviceInfo(v5, &v25, &v39);
    v3 = v25;
    v14 = KsMidiDeviceInfo;
    if ( KsMidiDeviceInfo >= 0 )
    {
      v17 = FilterInstantiate2(v25, v16, &FilterHandle);
      v18 = (char *)FilterHandle;
      v14 = v17;
      if ( v17 >= 0 )
      {
        *(&Connect.PinId + 1) = 0;
        Connect.Interface.Set = GUID_1a8766a0_62ce_11cf_a5d6_28db04c10000;
        v33 = 0;
        v34 = 0;
        Connect.Medium.Set = GUID_4747b320_62ce_11cf_a5d6_28db04c10000;
        Connect.PinId = v39;
        *(&Connect.Interface.Alignment + 2) = 0;
        *(&Connect.Medium.Alignment + 2) = 0;
        v35 = GUID_e725d360_62cc_11cf_a5d6_28db04c10000;
        Connect.PinToHandle = 0;
        Connect.Priority.PriorityClass = 0x40000000;
        Connect.Priority.PrioritySubClass = 0x40000000;
        v37 = GUID_0f6417d6_c318_11d0_a43f_00a0c9223196;
        v32 = 64;
        v36 = GUID_1d262760_e957_11cf_a5d6_28db04c10000;
        v19 = KsCreatePin2(FilterHandle, &Connect, 0xC0000000, &ConnectionHandle);
        v14 = v19;
        if ( v19 > 0 )
          v14 = (unsigned __int16)v19 | 0x80070000;
        if ( v14 >= 0 )
        {
          v20 = I_RpcBindingInqLocalClientPID(BindingHandle, &Pid);
          if ( v20 )
          {
            if ( v20 > 0 )
              v14 = (unsigned __int16)v20 | 0x80070000;
            else
              v14 = v20;
          }
          else if ( !RpcImpersonateClient(BindingHandle) )
          {
            v7 = (__int64)OpenProcess(0x40u, 0, Pid);
            if ( v7
              && (v22 = ConnectionHandle,
                  CurrentProcess = GetCurrentProcess(),
                  DuplicateHandle(CurrentProcess, v22, (HANDLE)v7, &TargetHandle, 0xC0000000, 0, 1u)) )
            {
              *a3 = TargetHandle;
            }
            else
            {
              LastError = GetLastError();
              v14 = LastError;
              if ( LastError > 0 )
                v14 = (unsigned __int16)LastError | 0x80070000;
            }
            RpcRevertToSelf();
          }
        }
      }
      if ( (unsigned __int64)(v18 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v18);
      if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle((HANDLE)v7);
    }
  }
  else
  {
    v14 = -2147467261;
  }
  CoTaskMemFree(v3);
  if ( v14 < 0 )
    AudSrvTraceLoggingErrorHelper("s_midiOpenPort", 0xD7u, v14);
  std::unique_ptr<CWatchdogTimer_Old<1>>::~unique_ptr<CWatchdogTimer_Old<1>>(&v29);
  std::unique_ptr<CWatchdogTimer<1>>::~unique_ptr<CWatchdogTimer<1>>(&v30);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180112df0  mov     [rsp-8+arg_0], rbx
0x180112df5  mov     [rsp-8+arg_8], rdx
0x180112dfa  push    rbp
0x180112dfb  push    rsi
0x180112dfc  push    rdi
0x180112dfd  push    r12
0x180112dff  push    r13
0x180112e01  push    r14
0x180112e03  push    r15
0x180112e05  lea     rbp, [rsp-27h]
0x180112e0a  sub     rsp, 100h
0x180112e11  xor     r14d, r14d
0x180112e14  mov     r12, r8
0x180112e17  mov     rbx, rdx
0x180112e1a  mov     [rsp+130h+var_F0], r14
0x180112e1f  mov     r13, rcx
0x180112e22  mov     [rbp+57h+arg_10], r14d
0x180112e26  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180112e2a  mov     [rsp+130h+ConnectionHandle], r14
0x180112e2f  xor     edx, edx; Val
0x180112e31  mov     [rsp+130h+FilterHandle], rsi
0x180112e36  mov     r8d, 88h; Size
0x180112e3c  lea     rcx, [rbp+57h+Connect]; void *
0x180112e40  call    memset_0
0x180112e45  mov     [rbp+57h+Pid], r14d
0x180112e49  mov     [rsp+130h+TargetHandle], rsi
0x180112e4e  mov     [rbp+57h+var_C8], r14
0x180112e52  mov     [rbp+57h+var_D0], r14
0x180112e56  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio> `wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl(void)'::`2'::impl
0x180112e5d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(void)
0x180112e62  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180112e69  lea     ecx, [rsi+39h]; unsigned __int64
0x180112e6c  test    al, al
0x180112e6e  jz      short loc_180112EBC
0x180112e70  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180112e75  mov     r15, rax
0x180112e78  test    rax, rax
0x180112e7b  jz      short loc_180112EAE
0x180112e7d  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x180112e84  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x180112e8a  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x180112e8f  lea     r9, aSMidiopenport; "s_midiOpenPort"
0x180112e96  mov     qword ptr [rsp+130h+dwDesiredAccess], rbx; pftDueTime
0x180112e9b  mov     r8d, edi
0x180112e9e  mov     rcx, r15; pv
0x180112ea1  mov     rdx, [rax+8]
0x180112ea5  call    ??0?$CWatchdogTimer@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@_N@Z; CWatchdogTimer<1>::CWatchdogTimer<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *,bool)
0x180112eaa  mov     rbx, [rbp+57h+arg_8]
0x180112eae  mov     rdx, rax
0x180112eb1  lea     rcx, [rbp+57h+var_C8]
0x180112eb5  call    ?reset@?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer@$00@@@Z; std::unique_ptr<CWatchdogTimer<1>>::reset(CWatchdogTimer<1> *)
0x180112eba  jmp     short loc_180112F06
0x180112ebc  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180112ec1  mov     r15, rax
0x180112ec4  test    rax, rax
0x180112ec7  jz      short loc_180112EFA
0x180112ec9  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x180112ed0  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x180112ed6  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x180112edb  lea     r9, aSMidiopenport; "s_midiOpenPort"
0x180112ee2  mov     qword ptr [rsp+130h+dwDesiredAccess], rbx; pftDueTime
0x180112ee7  mov     r8d, edi
0x180112eea  mov     rcx, r15; pv
0x180112eed  mov     rdx, [rax+8]
0x180112ef1  call    ??0?$CWatchdogTimer_Old@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@@Z; CWatchdogTimer_Old<1>::CWatchdogTimer_Old<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *)
0x180112ef6  mov     rbx, [rbp+57h+arg_8]
0x180112efa  mov     rdx, rax
0x180112efd  lea     rcx, [rbp+57h+var_D0]
0x180112f01  call    ?reset@?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer_Old@$00@@@Z; std::unique_ptr<CWatchdogTimer_Old<1>>::reset(CWatchdogTimer_Old<1> *)
0x180112f06  test    r12, r12
0x180112f09  jnz     short loc_180112F15
0x180112f0b  mov     edi, 80004003h
0x180112f10  jmp     loc_1801130C1
0x180112f15  lea     r8, [rbp+57h+arg_10]; unsigned int *
0x180112f19  mov     rcx, rbx; unsigned __int16 *
0x180112f1c  lea     rdx, [rsp+130h+var_F0]; unsigned __int16 **
0x180112f21  call    ?GetKsMidiDeviceInfo@@YAJPEBGPEAPEAGPEAI@Z; GetKsMidiDeviceInfo(ushort const *,ushort * *,uint *)
0x180112f26  mov     r14, [rsp+130h+var_F0]
0x180112f2b  xor     ebx, ebx
0x180112f2d  mov     edi, eax
0x180112f2f  test    eax, eax
0x180112f31  js      loc_1801130C1
0x180112f37  lea     r8, [rsp+130h+FilterHandle]; void **
0x180112f3c  mov     rcx, r14; unsigned __int16 *
0x180112f3f  call    ?FilterInstantiate2@@YAJPEBGKPEAPEAX@Z; FilterInstantiate2(ushort const *,ulong,void * *)
0x180112f44  mov     r15, [rsp+130h+FilterHandle]
0x180112f49  mov     edi, eax
0x180112f4b  test    eax, eax
0x180112f4d  js      loc_18011309B
0x180112f53  movups  xmm0, xmmword ptr cs:_GUID_1a8766a0_62ce_11cf_a5d6_28db04c10000.Data1
0x180112f5a  xor     eax, eax
0x180112f5c  lea     r9, [rsp+130h+ConnectionHandle]; ConnectionHandle
0x180112f61  movups  xmm1, xmmword ptr cs:_GUID_1d262760_e957_11cf_a5d6_28db04c10000.Data1
0x180112f68  mov     dword ptr [rbp+57h+Connect+34h], eax
0x180112f6b  mov     r8d, 0C0000000h; DesiredAccess
0x180112f71  movdqu  xmmword ptr [rbp+57h+Connect.Interface], xmm0
0x180112f76  mov     [rbp+57h+var_74], rax
0x180112f7a  lea     rdx, [rbp+57h+Connect]; Connect
0x180112f7e  movups  xmm0, xmmword ptr cs:_GUID_4747b320_62ce_11cf_a5d6_28db04c10000.Data1
0x180112f85  mov     [rbp+57h+var_6C], eax
0x180112f88  mov     rcx, r15; FilterHandle
0x180112f8b  mov     eax, [rbp+57h+arg_10]
0x180112f8e  movdqu  xmmword ptr [rbp+57h+Connect.Medium], xmm0
0x180112f93  mov     [rbp+57h+Connect.PinId], eax
0x180112f96  mov     eax, 40000000h
0x180112f9b  movups  xmm0, xmmword ptr cs:_GUID_e725d360_62cc_11cf_a5d6_28db04c10000.Data1
0x180112fa2  mov     qword ptr [rbp+57h+Connect.Interface+10h], rbx
0x180112fa6  mov     qword ptr [rbp+57h+Connect.Medium+10h], rbx
0x180112faa  movdqu  [rbp+57h+var_68], xmm0
0x180112faf  mov     [rbp+57h+Connect.PinToHandle], rbx
0x180112fb3  movups  xmm0, xmmword ptr cs:_GUID_0f6417d6_c318_11d0_a43f_00a0c9223196.Data1
0x180112fba  mov     [rbp+57h+Connect.Priority.PriorityClass], eax
0x180112fbd  mov     [rbp+57h+Connect.Priority.PrioritySubClass], eax
0x180112fc0  movdqu  [rbp+57h+var_48], xmm0
0x180112fc5  mov     [rbp+57h+var_78], 40h ; '@'
0x180112fcc  movdqu  [rbp+57h+var_58], xmm1
0x180112fd1  call    cs:__imp_KsCreatePin2
0x180112fd7  mov     edi, eax
0x180112fd9  test    eax, eax
0x180112fdb  jle     short loc_180112FE6
0x180112fdd  movzx   edi, ax
0x180112fe0  or      edi, 80070000h
0x180112fe6  test    edi, edi
0x180112fe8  js      loc_18011309B
0x180112fee  lea     rdx, [rbp+57h+Pid]; Pid
0x180112ff2  mov     rcx, r13; Binding
0x180112ff5  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180112ffb  test    eax, eax
0x180112ffd  jz      short loc_180113016
0x180112fff  jg      short loc_180113008
0x180113001  mov     edi, eax
0x180113003  jmp     loc_18011309B
0x180113008  movzx   edi, ax
0x18011300b  or      edi, 80070000h
0x180113011  jmp     loc_18011309B
0x180113016  mov     rcx, r13; BindingHandle
0x180113019  call    cs:__imp_RpcImpersonateClient
0x18011301f  test    eax, eax
0x180113021  jnz     short loc_18011309B
0x180113023  mov     r8d, [rbp+57h+Pid]; dwProcessId
0x180113027  lea     ecx, [rax+40h]; dwDesiredAccess
0x18011302a  xor     edx, edx; bInheritHandle
0x18011302c  call    cs:__imp_OpenProcess
0x180113032  mov     rsi, rax
0x180113035  test    rax, rax
0x180113038  jnz     short loc_180113051
0x18011303a  call    cs:__imp_GetLastError
0x180113040  mov     edi, eax
0x180113042  test    eax, eax
0x180113044  jle     short loc_180113095
0x180113046  movzx   edi, ax
0x180113049  or      edi, 80070000h
0x18011304f  jmp     short loc_180113095
0x180113051  mov     rbx, [rsp+130h+ConnectionHandle]
0x180113056  call    cs:__imp_GetCurrentProcess
0x18011305c  mov     [rsp+130h+dwOptions], 1; dwOptions
0x180113064  lea     r9, [rsp+130h+TargetHandle]; lpTargetHandle
0x180113069  mov     rcx, rax; hSourceProcessHandle
0x18011306c  mov     [rsp+130h+bInheritHandle], 0; bInheritHandle
0x180113074  mov     r8, rsi; hTargetProcessHandle
0x180113077  mov     [rsp+130h+dwDesiredAccess], 0C0000000h; dwDesiredAccess
0x18011307f  mov     rdx, rbx; hSourceHandle
0x180113082  call    cs:__imp_DuplicateHandle
0x180113088  test    eax, eax
0x18011308a  jz      short loc_18011303A
0x18011308c  mov     rax, [rsp+130h+TargetHandle]
0x180113091  mov     [r12], rax
0x180113095  call    cs:__imp_RpcRevertToSelf
0x18011309b  lea     rax, [r15-1]
0x18011309f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801130a3  ja      short loc_1801130AE
0x1801130a5  mov     rcx, r15; hObject
0x1801130a8  call    cs:__imp_CloseHandle
0x1801130ae  lea     rax, [rsi-1]
0x1801130b2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801130b6  ja      short loc_1801130C1
0x1801130b8  mov     rcx, rsi; hObject
0x1801130bb  call    cs:__imp_CloseHandle
0x1801130c1  mov     rcx, r14; pv
0x1801130c4  call    cs:__imp_CoTaskMemFree
0x1801130ca  test    edi, edi
0x1801130cc  jns     short loc_1801130E2
0x1801130ce  mov     r8d, edi; int
0x1801130d1  lea     rcx, aSMidiopenport_0; "s_midiOpenPort"
0x1801130d8  mov     edx, 0D7h; unsigned int
0x1801130dd  call    ?AudSrvTraceLoggingErrorHelper@@YAXPEBDIJ@Z; AudSrvTraceLoggingErrorHelper(char const *,uint,long)
0x1801130e2  lea     rcx, [rbp+57h+var_D0]
0x1801130e6  call    ??1?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWatchdogTimer_Old<1>>::~unique_ptr<CWatchdogTimer_Old<1>>(void)
0x1801130eb  lea     rcx, [rbp+57h+var_C8]
0x1801130ef  call    ??1?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWatchdogTimer<1>>::~unique_ptr<CWatchdogTimer<1>>(void)
0x1801130f4  mov     rbx, [rsp+130h+arg_0]
0x1801130fc  mov     eax, edi
0x1801130fe  add     rsp, 100h
0x180113105  pop     r15
0x180113107  pop     r14
0x180113109  pop     r13
0x18011310b  pop     r12
0x18011310d  pop     rdi
0x18011310e  pop     rsi
0x18011310f  pop     rbp
0x180113110  retn
```
