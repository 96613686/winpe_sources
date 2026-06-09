# CRuntimeBroker::Run(void)

- ea: `0x140006260`
- end: `0x14000656f`
- name: `?Run@CRuntimeBroker@@SAJXZ`
- size: `783`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140005770`

## callees

- `0x140006260`
- `0x140006580`
- `0x140006844`
- `0x140008ca4`
- `0x140009d90`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x140006397`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x140006397`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000631e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000631e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006339`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006339`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400062e2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400062e2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140006277`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140006277`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000653a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000653a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000655f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000655f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006289`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006289`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400064a2`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400064a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006547`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006547`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1400064ce`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1400064de`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1400064ee`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1400064ce`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1400064de`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1400064ee`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x1400064b1`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x1400064b1`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x14000646e`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x14000646e`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x1400063cd`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x140006422`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x14000645e`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x1400063cd`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x140006422`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x14000645e`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x14000634c`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x140006519`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x14000634c`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x140006519`

## string_xrefs

- `0x1400062d4`: `SOFTWARE\Microsoft\Ole\Extensions\AppCompat`
- `0x1400062fc`: `RuntimeBrokerIdleExitTimeout`

## pseudocode

```c
__int64 CRuntimeBroker::Run(void)
{
  signed int LastError; // eax
  HRESULT v1; // ebx
  CRuntimeBrokerLifetimeExtensionFactory *v2; // rax
  DWORD v3; // edi
  struct Windows::System::IUserWatcher *v4; // rdi
  HANDLE Handles[2]; // [rsp+30h] [rbp-10h] BYREF
  struct Windows::System::IUserWatcher *Data; // [rsp+60h] [rbp+20h] BYREF
  struct EventRegistrationToken cbData; // [rsp+68h] [rbp+28h] BYREF
  DWORD Type; // [rsp+70h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+38h] BYREF

  CRuntimeBroker::s_hEventShutdown = CreateEventW(0, 1, 0, 0);
  if ( CRuntimeBroker::s_hEventShutdown )
  {
    if ( (unsigned __int8)IsRemoteWinRTActivationPresent() )
      `CRuntimeBroker::Run'::`7'::dwIdleShutdownTimeout = 5000;
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Ole\\Extensions\\AppCompat", 0, 1u, &hKey) )
    {
      Type = 0;
      LODWORD(Data) = 0;
      LODWORD(cbData.value) = 4;
      if ( !RegQueryValueExW(hKey, L"RuntimeBrokerIdleExitTimeout", 0, &Type, (LPBYTE)&Data, (LPDWORD)&cbData) )
        `CRuntimeBroker::Run'::`7'::dwIdleShutdownTimeout = 1000 * (_DWORD)Data;
      RegCloseKey(hKey);
    }
    v1 = CoRegisterServerShutdownDelay(
           CRuntimeBroker::s_hEventShutdown,
           (unsigned int)`CRuntimeBroker::Run'::`7'::dwIdleShutdownTimeout);
    if ( v1 >= 0 )
    {
      Data = 0;
      cbData.value = 0;
      v1 = CRuntimeBroker::CreateLogoffWatcher(&Data, &cbData);
      if ( v1 >= 0 )
      {
        InitOnceExecuteOnce(&InitOnce, DoPerAppBrokerInstancingDefaultForActivationConfigurationCheck, 0, 0);
        if ( !byte_140018770 )
          goto LABEL_38;
        v1 = CoRegisterClassObject(
               &CLSID_PerAppRuntimeBroker,
               &CRuntimeBroker::s_factory,
               4u,
               5u,
               &CRuntimeBroker::s_registrationCookiePerAppRtb);
        if ( v1 >= 0 )
        {
          v2 = (CRuntimeBrokerLifetimeExtensionFactory *)operator new(
                                                           0x20u,
                                                           (const struct std::nothrow_t *)&std::nothrow);
          if ( v2 )
            v2 = CRuntimeBrokerLifetimeExtensionFactory::CRuntimeBrokerLifetimeExtensionFactory(v2);
          g_lifetimeExtensionFactory = v2;
          v1 = CoRegisterClassObject(
                 &CLSID_RuntimeBrokerLifetimeExtension,
                 (LPUNKNOWN)v2,
                 1u,
                 0x11u,
                 &CRuntimeBroker::s_registrationCookieLifetimeExtension);
          if ( v1 >= 0 )
          {
LABEL_38:
            if ( byte_140018608
              || (v1 = CoRegisterClassObject(
                         &CLSID_RuntimeBroker,
                         &CRuntimeBroker::s_factory,
                         4u,
                         5u,
                         &CRuntimeBroker::s_registrationCookieSharedRtb),
                  v1 >= 0) )
            {
              v1 = CoResumeClassObjects();
              if ( v1 >= 0 )
              {
                Handles[0] = CRuntimeBroker::s_hEventShutdown;
                Handles[1] = g_hLowPowerEpoch;
                do
                {
                  do
                  {
                    v3 = WaitForMultipleObjects(2u, Handles, 0, dwMilliseconds);
                    CoFreeUnusedLibrariesEx(0xEA60u, 0);
                  }
                  while ( v3 == 258 );
                }
                while ( v3 == 1 );
                if ( CRuntimeBroker::s_registrationCookieSharedRtb )
                  CoRevokeClassObject(CRuntimeBroker::s_registrationCookieSharedRtb);
                if ( CRuntimeBroker::s_registrationCookiePerAppRtb )
                  CoRevokeClassObject(CRuntimeBroker::s_registrationCookiePerAppRtb);
                if ( CRuntimeBroker::s_registrationCookieLifetimeExtension )
                  CoRevokeClassObject(CRuntimeBroker::s_registrationCookieLifetimeExtension);
              }
            }
          }
        }
      }
      v4 = Data;
      if ( Data && cbData.value )
        (*(void (__fastcall **)(struct Windows::System::IUserWatcher *))(*(_QWORD *)Data + 96LL))(Data);
      CoRegisterServerShutdownDelay(0, 0);
      if ( v4 )
        (*(void (__fastcall **)(struct Windows::System::IUserWatcher *))(*(_QWORD *)v4 + 16LL))(v4);
    }
    AcquireSRWLockExclusive(&CRuntimeBroker::s_ShutdownEventLock);
    CloseHandle(CRuntimeBroker::s_hEventShutdown);
    CRuntimeBroker::s_hEventShutdown = 0;
    ReleaseSRWLockExclusive(&CRuntimeBroker::s_ShutdownEventLock);
  }
  else
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140006260  push    rbp
0x140006262  push    rbx
0x140006263  push    rdi
0x140006264  mov     rbp, rsp
0x140006267  sub     rsp, 40h
0x14000626b  xor     r9d, r9d; lpName
0x14000626e  xor     r8d, r8d; bInitialState
0x140006271  xor     ecx, ecx; lpEventAttributes
0x140006273  lea     edx, [r9+1]; bManualReset
0x140006277  call    cs:__imp_CreateEventW
0x14000627d  mov     cs:?s_hEventShutdown@CRuntimeBroker@@0PEAXEA, rax; void * CRuntimeBroker::s_hEventShutdown
0x140006284  test    rax, rax
0x140006287  jnz     short loc_1400062A7
0x140006289  call    cs:__imp_GetLastError
0x14000628f  mov     ebx, eax
0x140006291  test    eax, eax
0x140006293  jle     loc_140006565
0x140006299  movzx   ebx, ax
0x14000629c  or      ebx, 80070000h
0x1400062a2  jmp     loc_140006565
0x1400062a7  call    IsRemoteWinRTActivationPresent
0x1400062ac  test    al, al
0x1400062ae  jz      short loc_1400062BA
0x1400062b0  mov     cs:?dwIdleShutdownTimeout@?6??Run@CRuntimeBroker@@SAJXZ@4KA, 1388h; ulong `CRuntimeBroker::Run(void)'::`7'::dwIdleShutdownTimeout
0x1400062ba  lea     rax, [rbp+hKey]
0x1400062be  mov     [rbp+hKey], 0
0x1400062c6  mov     r9d, 1; samDesired
0x1400062cc  mov     [rsp+40h+phkResult], rax; phkResult
0x1400062d1  xor     r8d, r8d; ulOptions
0x1400062d4  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Ole\\Extensions\\A"...
0x1400062db  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400062e2  call    cs:__imp_RegOpenKeyExW
0x1400062e8  mov     edi, 4
0x1400062ed  test    eax, eax
0x1400062ef  jnz     short loc_14000633F
0x1400062f1  mov     rcx, [rbp+hKey]; hKey
0x1400062f5  lea     r9, [rbp+Type]; lpType
0x1400062f9  mov     [rbp+Type], eax
0x1400062fc  lea     rdx, aRuntimebrokeri; "RuntimeBrokerIdleExitTimeout"
0x140006303  mov     dword ptr [rbp+Data], eax
0x140006306  xor     r8d, r8d; lpReserved
0x140006309  lea     rax, [rbp+cbData]
0x14000630d  mov     dword ptr [rbp+cbData], edi
0x140006310  mov     [rsp+40h+lpcbData], rax; lpcbData
0x140006315  lea     rax, [rbp+Data]
0x140006319  mov     [rsp+40h+phkResult], rax; lpData
0x14000631e  call    cs:__imp_RegQueryValueExW
0x140006324  test    eax, eax
0x140006326  jnz     short loc_140006335
0x140006328  imul    eax, dword ptr [rbp+Data], 3E8h
0x14000632f  mov     cs:?dwIdleShutdownTimeout@?6??Run@CRuntimeBroker@@SAJXZ@4KA, eax; ulong `CRuntimeBroker::Run(void)'::`7'::dwIdleShutdownTimeout
0x140006335  mov     rcx, [rbp+hKey]; hKey
0x140006339  call    cs:__imp_RegCloseKey
0x14000633f  mov     edx, cs:?dwIdleShutdownTimeout@?6??Run@CRuntimeBroker@@SAJXZ@4KA; ulong `CRuntimeBroker::Run(void)'::`7'::dwIdleShutdownTimeout
0x140006345  mov     rcx, cs:?s_hEventShutdown@CRuntimeBroker@@0PEAXEA; void * CRuntimeBroker::s_hEventShutdown
0x14000634c  call    cs:__imp_CoRegisterServerShutdownDelay
0x140006352  mov     ebx, eax
0x140006354  test    eax, eax
0x140006356  js      loc_140006533
0x14000635c  lea     rdx, [rbp+cbData]; struct EventRegistrationToken *
0x140006360  mov     [rbp+Data], 0
0x140006368  lea     rcx, [rbp+Data]; struct Windows::System::IUserWatcher **
0x14000636c  mov     [rbp+cbData], 0
0x140006374  call    ?CreateLogoffWatcher@CRuntimeBroker@@CAJPEAPEAUIUserWatcher@System@Windows@@PEAUEventRegistrationToken@@@Z; CRuntimeBroker::CreateLogoffWatcher(Windows::System::IUserWatcher * *,EventRegistrationToken *)
0x140006379  mov     ebx, eax
0x14000637b  test    eax, eax
0x14000637d  js      loc_1400064F4
0x140006383  xor     r9d, r9d; Context
0x140006386  lea     rdx, ?DoPerAppBrokerInstancingDefaultForActivationConfigurationCheck@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x14000638d  xor     r8d, r8d; Parameter
0x140006390  lea     rcx, InitOnce; InitOnce
0x140006397  call    cs:__imp_InitOnceExecuteOnce
0x14000639d  cmp     cs:byte_140018770, 0
0x1400063a4  jz      loc_140006432
0x1400063aa  lea     rax, ?s_registrationCookiePerAppRtb@CRuntimeBroker@@0KA; ulong CRuntimeBroker::s_registrationCookiePerAppRtb
0x1400063b1  mov     r9d, 5; flags
0x1400063b7  mov     r8d, edi; dwClsContext
0x1400063ba  mov     [rsp+40h+phkResult], rax; lpdwRegister
0x1400063bf  lea     rdx, ?s_factory@CRuntimeBroker@@0VCFactory@1@A; pUnk
0x1400063c6  lea     rcx, CLSID_PerAppRuntimeBroker; rclsid
0x1400063cd  call    cs:__imp_CoRegisterClassObject
0x1400063d3  mov     ebx, eax
0x1400063d5  test    eax, eax
0x1400063d7  js      loc_1400064F4
0x1400063dd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400063e4  mov     ecx, 20h ; ' '; unsigned __int64
0x1400063e9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400063ee  test    rax, rax
0x1400063f1  jz      short loc_1400063FB
0x1400063f3  mov     rcx, rax; this
0x1400063f6  call    ??0CRuntimeBrokerLifetimeExtensionFactory@@QEAA@XZ; CRuntimeBrokerLifetimeExtensionFactory::CRuntimeBrokerLifetimeExtensionFactory(void)
0x1400063fb  mov     r9d, 11h; flags
0x140006401  mov     cs:?g_lifetimeExtensionFactory@@3PEAVCRuntimeBrokerLifetimeExtensionFactory@@EA, rax; CRuntimeBrokerLifetimeExtensionFactory * g_lifetimeExtensionFactory
0x140006408  lea     rcx, ?s_registrationCookieLifetimeExtension@CRuntimeBroker@@0KA; ulong CRuntimeBroker::s_registrationCookieLifetimeExtension
0x14000640f  mov     rdx, rax; pUnk
0x140006412  mov     [rsp+40h+phkResult], rcx; lpdwRegister
0x140006417  lea     rcx, ?CLSID_RuntimeBrokerLifetimeExtension@@3U_GUID@@B; rclsid
0x14000641e  lea     r8d, [r9-10h]; dwClsContext
0x140006422  call    cs:__imp_CoRegisterClassObject
0x140006428  mov     ebx, eax
0x14000642a  test    eax, eax
0x14000642c  js      loc_1400064F4
0x140006432  cmp     cs:byte_140018608, 0
0x140006439  jnz     short loc_14000646E
0x14000643b  lea     rax, ?s_registrationCookieSharedRtb@CRuntimeBroker@@0KA; ulong CRuntimeBroker::s_registrationCookieSharedRtb
0x140006442  mov     r9d, 5; flags
0x140006448  mov     r8d, edi; dwClsContext
0x14000644b  mov     [rsp+40h+phkResult], rax; lpdwRegister
0x140006450  lea     rdx, ?s_factory@CRuntimeBroker@@0VCFactory@1@A; pUnk
0x140006457  lea     rcx, CLSID_RuntimeBroker; rclsid
0x14000645e  call    cs:__imp_CoRegisterClassObject
0x140006464  mov     ebx, eax
0x140006466  test    eax, eax
0x140006468  js      loc_1400064F4
0x14000646e  call    cs:__imp_CoResumeClassObjects
0x140006474  mov     ebx, eax
0x140006476  test    eax, eax
0x140006478  js      short loc_1400064F4
0x14000647a  mov     rax, cs:?s_hEventShutdown@CRuntimeBroker@@0PEAXEA; void * CRuntimeBroker::s_hEventShutdown
0x140006481  mov     [rbp+Handles], rax
0x140006485  mov     rax, cs:?g_hLowPowerEpoch@@3PEAXEA; void * g_hLowPowerEpoch
0x14000648c  mov     [rbp+var_8], rax
0x140006490  mov     r9d, cs:dwMilliseconds; dwMilliseconds
0x140006497  lea     rdx, [rbp+Handles]; lpHandles
0x14000649b  xor     r8d, r8d; bWaitAll
0x14000649e  lea     ecx, [r8+2]; nCount
0x1400064a2  call    cs:__imp_WaitForMultipleObjects
0x1400064a8  xor     edx, edx; dwReserved
0x1400064aa  mov     ecx, 0EA60h; dwUnloadDelay
0x1400064af  mov     edi, eax
0x1400064b1  call    cs:__imp_CoFreeUnusedLibrariesEx
0x1400064b7  cmp     edi, 102h
0x1400064bd  jz      short loc_140006490
0x1400064bf  cmp     edi, 1
0x1400064c2  jz      short loc_140006490
0x1400064c4  mov     ecx, cs:?s_registrationCookieSharedRtb@CRuntimeBroker@@0KA; dwRegister
0x1400064ca  test    ecx, ecx
0x1400064cc  jz      short loc_1400064D4
0x1400064ce  call    cs:__imp_CoRevokeClassObject
0x1400064d4  mov     ecx, cs:?s_registrationCookiePerAppRtb@CRuntimeBroker@@0KA; dwRegister
0x1400064da  test    ecx, ecx
0x1400064dc  jz      short loc_1400064E4
0x1400064de  call    cs:__imp_CoRevokeClassObject
0x1400064e4  mov     ecx, cs:?s_registrationCookieLifetimeExtension@CRuntimeBroker@@0KA; dwRegister
0x1400064ea  test    ecx, ecx
0x1400064ec  jz      short loc_1400064F4
0x1400064ee  call    cs:__imp_CoRevokeClassObject
0x1400064f4  mov     rdi, [rbp+Data]
0x1400064f8  test    rdi, rdi
0x1400064fb  jz      short loc_140006515
0x1400064fd  mov     rdx, [rbp+cbData]
0x140006501  test    rdx, rdx
0x140006504  jz      short loc_140006515
0x140006506  mov     rax, [rdi]
0x140006509  mov     rcx, rdi
0x14000650c  mov     rax, [rax+60h]
0x140006510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006515  xor     edx, edx
0x140006517  xor     ecx, ecx
0x140006519  call    cs:__imp_CoRegisterServerShutdownDelay
0x14000651f  test    rdi, rdi
0x140006522  jz      short loc_140006533
0x140006524  mov     rax, [rdi]
0x140006527  mov     rcx, rdi
0x14000652a  mov     rax, [rax+10h]
0x14000652e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006533  lea     rcx, ?s_ShutdownEventLock@CRuntimeBroker@@0Vsrwlock@wil@@A; SRWLock
0x14000653a  call    cs:__imp_AcquireSRWLockExclusive
0x140006540  mov     rcx, cs:?s_hEventShutdown@CRuntimeBroker@@0PEAXEA; hObject
0x140006547  call    cs:__imp_CloseHandle
0x14000654d  lea     rcx, ?s_ShutdownEventLock@CRuntimeBroker@@0Vsrwlock@wil@@A; SRWLock
0x140006554  mov     cs:?s_hEventShutdown@CRuntimeBroker@@0PEAXEA, 0; void * CRuntimeBroker::s_hEventShutdown
0x14000655f  call    cs:__imp_ReleaseSRWLockExclusive
0x140006565  mov     eax, ebx
0x140006567  add     rsp, 40h
0x14000656b  pop     rdi
0x14000656c  pop     rbx
0x14000656d  pop     rbp
0x14000656e  retn
```
