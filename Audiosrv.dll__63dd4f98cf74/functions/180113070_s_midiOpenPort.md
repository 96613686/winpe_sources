# s_midiOpenPort

- ea: `0x180113070`
- end: `0x180113391`
- name: `s_midiOpenPort`
- size: `801`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, unsigned __int16 *, HANDLE *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180012a0c`
- `0x18001b520`
- `0x1800be60c`
- `0x1800cddac`
- `0x1800ce774`
- `0x1800d6468`
- `0x1800d6540`
- `0x1800d67f4`
- `0x1800d6810`
- `0x1800da3f4`
- `0x1800da614`
- `0x1800da638`
- `0x180113070`
- `0x18013a5e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801132ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801132ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801132d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801132d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180113328`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011333b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180113328`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011333b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180113302`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180113302`
- `RPCRT4!RpcImpersonateClient` at `0x180113299`
- `RPCRT4!RpcImpersonateClient` at `0x180113299`
- `RPCRT4!RpcRevertToSelf` at `0x180113315`
- `RPCRT4!RpcRevertToSelf` at `0x180113315`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180113275`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180113275`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1801132ac`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1801132ac`
- `ksuser!KsCreatePin2` at `0x180113251`
- `ksuser!KsCreatePin2` at `0x180113251`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180113344`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180113344`

## string_xrefs

- `0x18011310f`: `s_midiOpenPort`
- `0x18011315b`: `s_midiOpenPort`
- `0x180113351`: `s_midiOpenPort`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl'::`2'::impl) )
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
0x180113070  mov     [rsp-8+arg_0], rbx
0x180113075  mov     [rsp-8+arg_8], rdx
0x18011307a  push    rbp
0x18011307b  push    rsi
0x18011307c  push    rdi
0x18011307d  push    r12
0x18011307f  push    r13
0x180113081  push    r14
0x180113083  push    r15
0x180113085  lea     rbp, [rsp-27h]
0x18011308a  sub     rsp, 100h
0x180113091  xor     r14d, r14d
0x180113094  mov     r12, r8
0x180113097  mov     rbx, rdx
0x18011309a  mov     [rsp+130h+var_F0], r14
0x18011309f  mov     r13, rcx
0x1801130a2  mov     [rbp+57h+arg_10], r14d
0x1801130a6  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1801130aa  mov     [rsp+130h+ConnectionHandle], r14
0x1801130af  xor     edx, edx; Val
0x1801130b1  mov     [rsp+130h+FilterHandle], rsi
0x1801130b6  mov     r8d, 88h; Size
0x1801130bc  lea     rcx, [rbp+57h+Connect]; void *
0x1801130c0  call    memset_0
0x1801130c5  mov     [rbp+57h+Pid], r14d
0x1801130c9  mov     [rsp+130h+TargetHandle], rsi
0x1801130ce  mov     [rbp+57h+var_C8], r14
0x1801130d2  mov     [rbp+57h+var_D0], r14
0x1801130d6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio> `wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl(void)'::`2'::impl
0x1801130dd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(void)
0x1801130e2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801130e9  lea     ecx, [rsi+39h]; unsigned __int64
0x1801130ec  test    al, al
0x1801130ee  jz      short loc_18011313C
0x1801130f0  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1801130f5  mov     r15, rax
0x1801130f8  test    rax, rax
0x1801130fb  jz      short loc_18011312E
0x1801130fd  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x180113104  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x18011310a  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x18011310f  lea     r9, aSMidiopenport; "s_midiOpenPort"
0x180113116  mov     qword ptr [rsp+130h+dwDesiredAccess], rbx; pftDueTime
0x18011311b  mov     r8d, edi
0x18011311e  mov     rcx, r15; pv
0x180113121  mov     rdx, [rax+8]
0x180113125  call    ??0?$CWatchdogTimer@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@_N@Z; CWatchdogTimer<1>::CWatchdogTimer<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *,bool)
0x18011312a  mov     rbx, [rbp+57h+arg_8]
0x18011312e  mov     rdx, rax
0x180113131  lea     rcx, [rbp+57h+var_C8]
0x180113135  call    ?reset@?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer@$00@@@Z; std::unique_ptr<CWatchdogTimer<1>>::reset(CWatchdogTimer<1> *)
0x18011313a  jmp     short loc_180113186
0x18011313c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180113141  mov     r15, rax
0x180113144  test    rax, rax
0x180113147  jz      short loc_18011317A
0x180113149  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x180113150  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x180113156  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x18011315b  lea     r9, aSMidiopenport; "s_midiOpenPort"
0x180113162  mov     qword ptr [rsp+130h+dwDesiredAccess], rbx; pftDueTime
0x180113167  mov     r8d, edi
0x18011316a  mov     rcx, r15; pv
0x18011316d  mov     rdx, [rax+8]
0x180113171  call    ??0?$CWatchdogTimer_Old@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@@Z; CWatchdogTimer_Old<1>::CWatchdogTimer_Old<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *)
0x180113176  mov     rbx, [rbp+57h+arg_8]
0x18011317a  mov     rdx, rax
0x18011317d  lea     rcx, [rbp+57h+var_D0]
0x180113181  call    ?reset@?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer_Old@$00@@@Z; std::unique_ptr<CWatchdogTimer_Old<1>>::reset(CWatchdogTimer_Old<1> *)
0x180113186  test    r12, r12
0x180113189  jnz     short loc_180113195
0x18011318b  mov     edi, 80004003h
0x180113190  jmp     loc_180113341
0x180113195  lea     r8, [rbp+57h+arg_10]; unsigned int *
0x180113199  mov     rcx, rbx; unsigned __int16 *
0x18011319c  lea     rdx, [rsp+130h+var_F0]; unsigned __int16 **
0x1801131a1  call    ?GetKsMidiDeviceInfo@@YAJPEBGPEAPEAGPEAI@Z; GetKsMidiDeviceInfo(ushort const *,ushort * *,uint *)
0x1801131a6  mov     r14, [rsp+130h+var_F0]
0x1801131ab  xor     ebx, ebx
0x1801131ad  mov     edi, eax
0x1801131af  test    eax, eax
0x1801131b1  js      loc_180113341
0x1801131b7  lea     r8, [rsp+130h+FilterHandle]; void **
0x1801131bc  mov     rcx, r14; unsigned __int16 *
0x1801131bf  call    ?FilterInstantiate2@@YAJPEBGKPEAPEAX@Z; FilterInstantiate2(ushort const *,ulong,void * *)
0x1801131c4  mov     r15, [rsp+130h+FilterHandle]
0x1801131c9  mov     edi, eax
0x1801131cb  test    eax, eax
0x1801131cd  js      loc_18011331B
0x1801131d3  movups  xmm0, xmmword ptr cs:_GUID_1a8766a0_62ce_11cf_a5d6_28db04c10000.Data1
0x1801131da  xor     eax, eax
0x1801131dc  lea     r9, [rsp+130h+ConnectionHandle]; ConnectionHandle
0x1801131e1  movups  xmm1, xmmword ptr cs:_GUID_1d262760_e957_11cf_a5d6_28db04c10000.Data1
0x1801131e8  mov     dword ptr [rbp+57h+Connect+34h], eax
0x1801131eb  mov     r8d, 0C0000000h; DesiredAccess
0x1801131f1  movdqu  xmmword ptr [rbp+57h+Connect.Interface], xmm0
0x1801131f6  mov     [rbp+57h+var_74], rax
0x1801131fa  lea     rdx, [rbp+57h+Connect]; Connect
0x1801131fe  movups  xmm0, xmmword ptr cs:_GUID_4747b320_62ce_11cf_a5d6_28db04c10000.Data1
0x180113205  mov     [rbp+57h+var_6C], eax
0x180113208  mov     rcx, r15; FilterHandle
0x18011320b  mov     eax, [rbp+57h+arg_10]
0x18011320e  movdqu  xmmword ptr [rbp+57h+Connect.Medium], xmm0
0x180113213  mov     [rbp+57h+Connect.PinId], eax
0x180113216  mov     eax, 40000000h
0x18011321b  movups  xmm0, xmmword ptr cs:_GUID_e725d360_62cc_11cf_a5d6_28db04c10000.Data1
0x180113222  mov     qword ptr [rbp+57h+Connect.Interface+10h], rbx
0x180113226  mov     qword ptr [rbp+57h+Connect.Medium+10h], rbx
0x18011322a  movdqu  [rbp+57h+var_68], xmm0
0x18011322f  mov     [rbp+57h+Connect.PinToHandle], rbx
0x180113233  movups  xmm0, xmmword ptr cs:_GUID_0f6417d6_c318_11d0_a43f_00a0c9223196.Data1
0x18011323a  mov     [rbp+57h+Connect.Priority.PriorityClass], eax
0x18011323d  mov     [rbp+57h+Connect.Priority.PrioritySubClass], eax
0x180113240  movdqu  [rbp+57h+var_48], xmm0
0x180113245  mov     [rbp+57h+var_78], 40h ; '@'
0x18011324c  movdqu  [rbp+57h+var_58], xmm1
0x180113251  call    cs:__imp_KsCreatePin2
0x180113257  mov     edi, eax
0x180113259  test    eax, eax
0x18011325b  jle     short loc_180113266
0x18011325d  movzx   edi, ax
0x180113260  or      edi, 80070000h
0x180113266  test    edi, edi
0x180113268  js      loc_18011331B
0x18011326e  lea     rdx, [rbp+57h+Pid]; Pid
0x180113272  mov     rcx, r13; Binding
0x180113275  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18011327b  test    eax, eax
0x18011327d  jz      short loc_180113296
0x18011327f  jg      short loc_180113288
0x180113281  mov     edi, eax
0x180113283  jmp     loc_18011331B
0x180113288  movzx   edi, ax
0x18011328b  or      edi, 80070000h
0x180113291  jmp     loc_18011331B
0x180113296  mov     rcx, r13; BindingHandle
0x180113299  call    cs:__imp_RpcImpersonateClient
0x18011329f  test    eax, eax
0x1801132a1  jnz     short loc_18011331B
0x1801132a3  mov     r8d, [rbp+57h+Pid]; dwProcessId
0x1801132a7  lea     ecx, [rax+40h]; dwDesiredAccess
0x1801132aa  xor     edx, edx; bInheritHandle
0x1801132ac  call    cs:__imp_OpenProcess
0x1801132b2  mov     rsi, rax
0x1801132b5  test    rax, rax
0x1801132b8  jnz     short loc_1801132D1
0x1801132ba  call    cs:__imp_GetLastError
0x1801132c0  mov     edi, eax
0x1801132c2  test    eax, eax
0x1801132c4  jle     short loc_180113315
0x1801132c6  movzx   edi, ax
0x1801132c9  or      edi, 80070000h
0x1801132cf  jmp     short loc_180113315
0x1801132d1  mov     rbx, [rsp+130h+ConnectionHandle]
0x1801132d6  call    cs:__imp_GetCurrentProcess
0x1801132dc  mov     [rsp+130h+dwOptions], 1; dwOptions
0x1801132e4  lea     r9, [rsp+130h+TargetHandle]; lpTargetHandle
0x1801132e9  mov     rcx, rax; hSourceProcessHandle
0x1801132ec  mov     [rsp+130h+bInheritHandle], 0; bInheritHandle
0x1801132f4  mov     r8, rsi; hTargetProcessHandle
0x1801132f7  mov     [rsp+130h+dwDesiredAccess], 0C0000000h; dwDesiredAccess
0x1801132ff  mov     rdx, rbx; hSourceHandle
0x180113302  call    cs:__imp_DuplicateHandle
0x180113308  test    eax, eax
0x18011330a  jz      short loc_1801132BA
0x18011330c  mov     rax, [rsp+130h+TargetHandle]
0x180113311  mov     [r12], rax
0x180113315  call    cs:__imp_RpcRevertToSelf
0x18011331b  lea     rax, [r15-1]
0x18011331f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180113323  ja      short loc_18011332E
0x180113325  mov     rcx, r15; hObject
0x180113328  call    cs:__imp_CloseHandle
0x18011332e  lea     rax, [rsi-1]
0x180113332  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180113336  ja      short loc_180113341
0x180113338  mov     rcx, rsi; hObject
0x18011333b  call    cs:__imp_CloseHandle
0x180113341  mov     rcx, r14; pv
0x180113344  call    cs:__imp_CoTaskMemFree
0x18011334a  test    edi, edi
0x18011334c  jns     short loc_180113362
0x18011334e  mov     r8d, edi; int
0x180113351  lea     rcx, aSMidiopenport_0; "s_midiOpenPort"
0x180113358  mov     edx, 0D7h; unsigned int
0x18011335d  call    ?AudSrvTraceLoggingErrorHelper@@YAXPEBDIJ@Z; AudSrvTraceLoggingErrorHelper(char const *,uint,long)
0x180113362  lea     rcx, [rbp+57h+var_D0]
0x180113366  call    ??1?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWatchdogTimer_Old<1>>::~unique_ptr<CWatchdogTimer_Old<1>>(void)
0x18011336b  lea     rcx, [rbp+57h+var_C8]
0x18011336f  call    ??1?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWatchdogTimer<1>>::~unique_ptr<CWatchdogTimer<1>>(void)
0x180113374  mov     rbx, [rsp+130h+arg_0]
0x18011337c  mov     eax, edi
0x18011337e  add     rsp, 100h
0x180113385  pop     r15
0x180113387  pop     r14
0x180113389  pop     r13
0x18011338b  pop     r12
0x18011338d  pop     rdi
0x18011338e  pop     rsi
0x18011338f  pop     rbp
0x180113390  retn
```
