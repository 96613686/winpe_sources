# CWindowsPolicyManager::RuntimeClassInitialize(void)

- ea: `0x180030408`
- end: `0x18003071e`
- name: `?RuntimeClassInitialize@CWindowsPolicyManager@@QEAAJXZ`
- size: `790`
- prototype: `__int64 __fastcall(CWindowsPolicyManager *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180043320`

## callees

- `0x18000a384`
- `0x18000f4e0`
- `0x18002acfc`
- `0x18002b25c`
- `0x180030408`
- `0x180031960`
- `0x1800327f8`
- `0x18003a5fc`
- `0x18003d00c`
- `0x1800403e0`
- `0x1800421f8`
- `0x18004313c`
- `0x1800431ec`
- `0x180043274`
- `0x180043938`
- `0x180044df0`
- `0x180048180`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800304b0`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800304b0`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18003046c`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18003046c`
- `POWRPROF!PowerSettingRegisterNotification` at `0x180030667`
- `POWRPROF!PowerSettingRegisterNotification` at `0x180030667`
- `POWRPROF!GetPwrCapabilities` at `0x18003062f`
- `POWRPROF!GetPwrCapabilities` at `0x18003062f`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_GetPolicy` at `0x1800306ae`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_GetPolicy` at `0x1800306ae`

## string_xrefs

- `0x1800306a0`: `ConfigureAudioOnLockScreen`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWindowsPolicyManager::RuntimeClassInitialize(CWindowsPolicyManager *this)
{
  int v2; // eax
  int v3; // edi
  const char *v5; // r9
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  DWORD v16; // eax
  int Policy; // eax
  DWORD dwCreationFlags; // [rsp+20h] [rbp-59h]
  DWORD dwCreationFlagsa; // [rsp+20h] [rbp-59h]
  CApplicationManager *v20; // [rsp+30h] [rbp-49h] BYREF
  _QWORD Recipient[2]; // [rsp+38h] [rbp-41h] BYREF
  __int64 v22; // [rsp+48h] [rbp-31h] BYREF
  _DWORD v23[4]; // [rsp+50h] [rbp-29h] BYREF
  _SYSTEM_POWER_CAPABILITIES spc; // [rsp+60h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v2 = InitializeAudioThreadpool();
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11E,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\windowspolicymanager.cpp",
      (const char *)(unsigned int)v2,
      dwCreationFlags);
    return (unsigned int)v3;
  }
  g_WorkerEventPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 0);
  if ( !g_WorkerEventPort )
  {
    v6 = 289;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v6,
             (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\windowspolicymanager.cpp",
             v5);
  }
  g_EventWorkerThreadHandle = CreateThread(0, 0, EventWorkerThread, 0, 0, 0);
  if ( !g_EventWorkerThreadHandle )
  {
    v6 = 292;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v6,
             (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\windowspolicymanager.cpp",
             v5);
  }
  TS_ServiceStart();
  v20 = 0;
  v3 = Microsoft::WRL::Details::MakeAndInitialize<CApplicationManager,CApplicationManager,>(&v20);
  if ( v3 < 0 )
  {
    v7 = 297;
    goto LABEL_11;
  }
  v8 = (__int64 *)Microsoft::WRL::Details::Make<CStreamClassPolicyManager,>(Recipient);
  v9 = *v8;
  *v8 = 0;
  v10 = g_StreamClassPolicyManager;
  g_StreamClassPolicyManager = v9;
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  v11 = Recipient[0];
  if ( Recipient[0] )
  {
    Recipient[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  if ( !g_StreamClassPolicyManager )
  {
    v12 = 300;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\windowspolicymanager.cpp",
      (const char *)0x8007000ELL,
      dwCreationFlagsa);
    if ( v20 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release();
    return 2147942414LL;
  }
  v13 = (__int64 *)Microsoft::WRL::Details::Make<CPlaybackManager,>(Recipient);
  v14 = *v13;
  *v13 = 0;
  v15 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = v14;
  if ( v15 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ISessionInternalEvents>::Release();
  if ( Recipient[0] )
  {
    Recipient[0] = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ISessionInternalEvents>::Release();
  }
  if ( !*((_QWORD *)this + 4) )
  {
    v12 = 303;
    goto LABEL_25;
  }
  wil::com_ptr_t<CDuckingManager,wil::err_returncode_policy>::reset((char *)this + 40);
  v3 = Microsoft::WRL::Details::MakeAndInitialize<CDuckingManager,CDuckingManager,>((char *)this + 40);
  if ( v3 < 0 )
  {
    v7 = 305;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\windowspolicymanager.cpp",
      (const char *)(unsigned int)v3,
      dwCreationFlagsa);
    if ( v20 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release();
    return (unsigned int)v3;
  }
  g_DuckingManager = (struct CDuckingManager *)*((_QWORD *)this + 5);
  g_ApplicationManager = v20;
  g_PlaybackManager = (struct CPlaybackManager *)*((_QWORD *)this + 4);
  memset_0(&spc, 0, sizeof(spc));
  if ( GetPwrCapabilities(&spc) )
  {
    if ( spc.spare2[2] )
    {
      Recipient[0] = LowPowerEpochNotificationCallback;
      Recipient[1] = 0;
      v16 = PowerSettingRegisterNotification(&GUID_LOW_POWER_EPOCH, 2u, Recipient, &g_hLowPowerEpochNotificationHandle);
      if ( v16 )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x142,
          (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\windowspolicymanager.cpp",
          (const char *)v16,
          dwCreationFlagsa);
    }
  }
  v23[0] = 1;
  v23[1] = 2;
  v22 = 0;
  Policy = PolicyManager_GetPolicy(L"AboveLock", L"ConfigureAudioOnLockScreen", v23, &v22);
  if ( Policy >= 0 )
  {
    if ( *(_DWORD *)(v22 + 8) == 1 )
    {
      if ( *(_DWORD *)(v22 + 16) == 1 )
      {
        *((_DWORD *)this + 13) |= 1u;
      }
      else if ( *(_DWORD *)(v22 + 16) == 2 )
      {
        *((_DWORD *)this + 13) |= 3u;
      }
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x148,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\windowspolicymanager.cpp",
      (const char *)(unsigned int)Policy,
      dwCreationFlagsa);
  }
  wil::details::unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&long PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&long PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>(&v22);
  return 0;
}

```

## disassembly

```asm
0x180030408  mov     [rsp-8+arg_8], rbx
0x18003040d  mov     [rsp-8+arg_10], rsi
0x180030412  push    rbp
0x180030413  push    rdi
0x180030414  push    r14
0x180030416  lea     rbp, [rsp-47h]
0x18003041b  sub     rsp, 0C0h
0x180030422  mov     rax, cs:__security_cookie
0x180030429  xor     rax, rsp
0x18003042c  mov     [rbp+57h+var_20], rax
0x180030430  mov     rbx, rcx
0x180030433  call    ?InitializeAudioThreadpool@@YAJXZ; InitializeAudioThreadpool(void)
0x180030438  mov     edi, eax
0x18003043a  xor     r14d, r14d
0x18003043d  test    eax, eax
0x18003043f  jns     short loc_180030460
0x180030441  mov     rcx, [rbp+5Fh]; this
0x180030445  mov     r9d, eax; char *
0x180030448  lea     r8, aClientcoreMult_2; "clientcore\\multimedia\\audiocore\\serv"...
0x18003044f  mov     edx, 11Eh; void *
0x180030454  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030459  mov     eax, edi
0x18003045b  jmp     loc_1800306FA
0x180030460  xor     r9d, r9d; NumberOfConcurrentThreads
0x180030463  xor     r8d, r8d; CompletionKey
0x180030466  xor     edx, edx; ExistingCompletionPort
0x180030468  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x18003046c  call    cs:__imp_CreateIoCompletionPort
0x180030472  mov     cs:?g_WorkerEventPort@@3PEAXEA, rax; void * g_WorkerEventPort
0x180030479  test    rax, rax
0x18003047c  jnz     short loc_180030498
0x18003047e  mov     edx, 121h; void *
0x180030483  lea     r8, aClientcoreMult_2; "clientcore\\multimedia\\audiocore\\serv"...
0x18003048a  mov     rcx, [rbp+5Fh]; this
0x18003048e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180030493  jmp     loc_1800306FA
0x180030498  mov     [rsp+0D0h+lpThreadId], r14; lpThreadId
0x18003049d  mov     [rsp+0D0h+dwCreationFlags], r14d; int
0x1800304a2  xor     r9d, r9d; lpParameter
0x1800304a5  lea     r8, ?EventWorkerThread@@YAKPEAX@Z; lpStartAddress
0x1800304ac  xor     edx, edx; dwStackSize
0x1800304ae  xor     ecx, ecx; lpThreadAttributes
0x1800304b0  call    cs:__imp_CreateThread
0x1800304b6  mov     cs:?g_EventWorkerThreadHandle@@3PEAXEA, rax; void * g_EventWorkerThreadHandle
0x1800304bd  test    rax, rax
0x1800304c0  jnz     short loc_1800304C9
0x1800304c2  mov     edx, 124h
0x1800304c7  jmp     short loc_180030483
0x1800304c9  call    ?TS_ServiceStart@@YAXXZ; TS_ServiceStart(void)
0x1800304ce  nop
0x1800304cf  mov     [rbp+57h+var_A0], r14
0x1800304d3  lea     rcx, [rbp+57h+var_A0]
0x1800304d7  call    ??$MakeAndInitialize@VCApplicationManager@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCApplicationManager@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CApplicationManager,CApplicationManager,>(CApplicationManager * *)
0x1800304dc  mov     edi, eax
0x1800304de  test    eax, eax
0x1800304e0  jns     short loc_180030512
0x1800304e2  mov     edx, 129h; void *
0x1800304e7  lea     r8, aClientcoreMult_2; "clientcore\\multimedia\\audiocore\\serv"...
0x1800304ee  mov     r9d, edi; char *
0x1800304f1  mov     rcx, [rbp+5Fh]; this
0x1800304f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800304fa  nop
0x1800304fb  mov     rcx, [rbp+57h+var_A0]
0x1800304ff  test    rcx, rcx
0x180030502  jz      loc_180030459
0x180030508  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18003050d  jmp     loc_180030459
0x180030512  lea     rcx, [rbp+57h+Recipient]
0x180030516  call    ??$Make@VCStreamClassPolicyManager@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCStreamClassPolicyManager@@@12@XZ; Microsoft::WRL::Details::Make<CStreamClassPolicyManager,>(void)
0x18003051b  mov     rdx, [rax]
0x18003051e  mov     [rax], r14
0x180030521  mov     rcx, cs:?g_StreamClassPolicyManager@@3V?$com_ptr_t@VCStreamClassPolicyManager@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<CStreamClassPolicyManager,wil::err_returncode_policy> g_StreamClassPolicyManager
0x180030528  mov     cs:?g_StreamClassPolicyManager@@3V?$com_ptr_t@VCStreamClassPolicyManager@@Uerr_returncode_policy@wil@@@wil@@A, rdx; wil::com_ptr_t<CStreamClassPolicyManager,wil::err_returncode_policy> g_StreamClassPolicyManager
0x18003052f  test    rcx, rcx
0x180030532  jz      short loc_180030541
0x180030534  mov     rax, [rcx]
0x180030537  mov     rax, [rax+10h]
0x18003053b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030540  nop
0x180030541  mov     rcx, [rbp+57h+Recipient]
0x180030545  test    rcx, rcx
0x180030548  jz      short loc_18003055B
0x18003054a  mov     [rbp+57h+Recipient], r14
0x18003054e  mov     rax, [rcx]
0x180030551  mov     rax, [rax+10h]
0x180030555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003055a  nop
0x18003055b  cmp     cs:?g_StreamClassPolicyManager@@3V?$com_ptr_t@VCStreamClassPolicyManager@@Uerr_returncode_policy@wil@@@wil@@A, r14; wil::com_ptr_t<CStreamClassPolicyManager,wil::err_returncode_policy> g_StreamClassPolicyManager
0x180030562  jnz     short loc_18003056B
0x180030564  mov     edx, 12Ch
0x180030569  jmp     short loc_1800305A9
0x18003056b  lea     rcx, [rbp+57h+Recipient]
0x18003056f  call    ??$Make@VCPlaybackManager@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCPlaybackManager@@@12@XZ; Microsoft::WRL::Details::Make<CPlaybackManager,>(void)
0x180030574  mov     rdx, [rax]
0x180030577  mov     [rax], r14
0x18003057a  mov     rcx, [rbx+20h]
0x18003057e  mov     [rbx+20h], rdx
0x180030582  test    rcx, rcx
0x180030585  jz      short loc_18003058C
0x180030587  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UISessionInternalEvents@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ISessionInternalEvents>::Release(void)
0x18003058c  mov     rcx, [rbp+57h+Recipient]
0x180030590  test    rcx, rcx
0x180030593  jz      short loc_18003059E
0x180030595  mov     [rbp+57h+Recipient], r14
0x180030599  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UISessionInternalEvents@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ISessionInternalEvents>::Release(void)
0x18003059e  cmp     [rbx+20h], r14
0x1800305a2  jnz     short loc_1800305D8
0x1800305a4  mov     edx, 12Fh; void *
0x1800305a9  mov     r9d, 8007000Eh; char *
0x1800305af  lea     r8, aClientcoreMult_2; "clientcore\\multimedia\\audiocore\\serv"...
0x1800305b6  mov     rcx, [rbp+5Fh]; this
0x1800305ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800305bf  nop
0x1800305c0  mov     rcx, [rbp+57h+var_A0]
0x1800305c4  test    rcx, rcx
0x1800305c7  jz      short loc_1800305CE
0x1800305c9  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x1800305ce  mov     eax, 8007000Eh
0x1800305d3  jmp     loc_1800306FA
0x1800305d8  lea     rsi, [rbx+28h]
0x1800305dc  mov     rcx, rsi
0x1800305df  call    ?reset@?$com_ptr_t@VCDuckingManager@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<CDuckingManager,wil::err_returncode_policy>::reset(void)
0x1800305e4  mov     rcx, rsi
0x1800305e7  call    ??$MakeAndInitialize@VCDuckingManager@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCDuckingManager@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CDuckingManager,CDuckingManager,>(CDuckingManager * *)
0x1800305ec  mov     edi, eax
0x1800305ee  test    eax, eax
0x1800305f0  jns     short loc_1800305FC
0x1800305f2  mov     edx, 131h
0x1800305f7  jmp     loc_1800304E7
0x1800305fc  mov     rax, [rsi]
0x1800305ff  mov     cs:?g_DuckingManager@@3PEAVCDuckingManager@@EA, rax; CDuckingManager * g_DuckingManager
0x180030606  mov     rax, [rbp+57h+var_A0]
0x18003060a  mov     cs:?g_ApplicationManager@@3PEAVCApplicationManager@@EA, rax; CApplicationManager * g_ApplicationManager
0x180030611  mov     rax, [rbx+20h]
0x180030615  mov     cs:?g_PlaybackManager@@3PEAVCPlaybackManager@@EA, rax; CPlaybackManager * g_PlaybackManager
0x18003061c  xor     edx, edx; Val
0x18003061e  lea     r8d, [rdx+4Ch]; Size
0x180030622  lea     rcx, [rbp+57h+spc]; void *
0x180030626  call    memset_0
0x18003062b  lea     rcx, [rbp+57h+spc]; lpspc
0x18003062f  call    cs:__imp_GetPwrCapabilities
0x180030635  mov     esi, 2
0x18003063a  test    al, al
0x18003063c  jz      short loc_180030689
0x18003063e  cmp     [rbp+57h+spc.spare2+2], r14b
0x180030642  jz      short loc_180030689
0x180030644  lea     rax, ?LowPowerEpochNotificationCallback@@YAKPEAXK0@Z; LowPowerEpochNotificationCallback(void *,ulong,void *)
0x18003064b  mov     [rbp+57h+Recipient], rax
0x18003064f  mov     [rbp+57h+var_90], r14
0x180030653  lea     r9, ?g_hLowPowerEpochNotificationHandle@@3PEAXEA; RegistrationHandle
0x18003065a  lea     r8, [rbp+57h+Recipient]; Recipient
0x18003065e  mov     edx, esi; Flags
0x180030660  lea     rcx, GUID_LOW_POWER_EPOCH; SettingGuid
0x180030667  call    cs:__imp_PowerSettingRegisterNotification
0x18003066d  mov     rcx, [rbp+5Fh]; this
0x180030671  test    eax, eax
0x180030673  jz      short loc_180030689
0x180030675  mov     r9d, eax; char *
0x180030678  lea     r8, aClientcoreMult_2; "clientcore\\multimedia\\audiocore\\serv"...
0x18003067f  mov     edx, 142h; void *
0x180030684  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180030689  mov     edi, 1
0x18003068e  mov     [rbp+57h+var_80], edi
0x180030691  mov     [rbp+57h+var_7C], esi
0x180030694  mov     [rbp+57h+var_88], r14
0x180030698  lea     r9, [rbp+57h+var_88]
0x18003069c  lea     r8, [rbp+57h+var_80]
0x1800306a0  lea     rdx, aConfigureaudio; "ConfigureAudioOnLockScreen"
0x1800306a7  lea     rcx, aAbovelock; "AboveLock"
0x1800306ae  call    cs:__imp_PolicyManager_GetPolicy
0x1800306b4  mov     rcx, [rbp+5Fh]; this
0x1800306b8  test    eax, eax
0x1800306ba  jns     short loc_1800306D2
0x1800306bc  mov     r9d, eax; char *
0x1800306bf  lea     r8, aClientcoreMult_2; "clientcore\\multimedia\\audiocore\\serv"...
0x1800306c6  mov     edx, 148h; void *
0x1800306cb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800306d0  jmp     short loc_1800306EE
0x1800306d2  mov     rax, [rbp+57h+var_88]
0x1800306d6  cmp     [rax+8], edi
0x1800306d9  jnz     short loc_1800306EE
0x1800306db  cmp     [rax+10h], edi
0x1800306de  jnz     short loc_1800306E5
0x1800306e0  or      [rbx+34h], edi
0x1800306e3  jmp     short loc_1800306EE
0x1800306e5  cmp     [rax+10h], esi
0x1800306e8  jnz     short loc_1800306EE
0x1800306ea  or      dword ptr [rbx+34h], 3
0x1800306ee  lea     rcx, [rbp+57h+var_88]
0x1800306f2  call    ??1?$unique_storage@U?$resource_policy@PEAUPMPolicyRetrievedInfo@@P6AJPEAU1@@Z$1?PolicyManager_FreeGetPolicyData@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>(void)
0x1800306f7  nop
0x1800306f8  xor     eax, eax
0x1800306fa  mov     rcx, [rbp+57h+var_20]
0x1800306fe  xor     rcx, rsp; StackCookie
0x180030701  call    __security_check_cookie
0x180030706  lea     r11, [rsp+0D0h+var_10]
0x18003070e  mov     rbx, [r11+28h]
0x180030712  mov     rsi, [r11+30h]
0x180030716  mov     rsp, r11
0x180030719  pop     r14
0x18003071b  pop     rdi
0x18003071c  pop     rbp
0x18003071d  retn
```
