# CDesktopManager::DwmEventThreadProc(void *)

- ea: `0x18001d710`
- end: `0x18001deb7`
- name: `?DwmEventThreadProc@CDesktopManager@@CAKPEAX@Z`
- size: `1959`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `21`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180014ea0`
- `0x18001d710`
- `0x18001dec0`
- `0x18001f43c`
- `0x18001f4e0`
- `0x18001f540`
- `0x18003e140`
- `0x18003e614`
- `0x180044e30`
- `0x180050844`
- `0x180061ea8`
- `0x180071474`
- `0x180073af8`
- `0x180075e28`
- `0x180095130`
- `0x18009e4c0`
- `0x1800ae238`
- `0x1800afb50`
- `0x1800b0eac`
- `0x1800b3288`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d8b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d9e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001db29`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001dd92`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d8b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d9e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001db29`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001dd92`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d849`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d849`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d90a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001da0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001db61`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d90a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001da0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001db61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d794`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d794`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db9a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d778`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d840`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d778`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d840`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d761`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d761`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dd46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dd46`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18001d783`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18001d783`
- `ntdll!EtwEventEnabled` at `0x18001d8f9`
- `ntdll!EtwEventEnabled` at `0x18001d8f9`
- `USER32!UnregisterClassW` at `0x18001ddc3`
- `USER32!UnregisterClassW` at `0x18001ddc3`
- `USER32!DispatchMessageW` at `0x18001dc0f`
- `USER32!DispatchMessageW` at `0x18001dc0f`
- `USER32!PeekMessageW` at `0x18001da2d`
- `USER32!PeekMessageW` at `0x18001dc45`
- `USER32!PeekMessageW` at `0x18001da2d`
- `USER32!PeekMessageW` at `0x18001dc45`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x18001d965`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x18001d965`
- `dwmcore!MilCompositionEngine_GetComposedEventId` at `0x18001dc6b`
- `dwmcore!MilCompositionEngine_GetComposedEventId` at `0x18001dc6b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001d7f8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001d7f8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001de80`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001de80`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001dd7b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001dd7b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDesktopManager::DwmEventThreadProc(PVOID Parameter)
{
  int v2; // edi
  bool v3; // r15
  void *v4; // r12
  char v5; // si
  __int64 (*v6)(HWND, unsigned int, unsigned __int64, __int64); // rdx
  const unsigned __int16 *v7; // rcx
  signed int LastError; // eax
  signed int v9; // r13d
  int v10; // eax
  HRESULT v11; // eax
  int Instance; // eax
  const unsigned __int16 *v13; // rdx
  bool v14; // r14
  CDesktopManager *v15; // rcx
  bool v16; // al
  int v17; // r8d
  char v18; // al
  DWORD v19; // r8d
  DWORD v20; // ebx
  bool v21; // di
  DWORD v22; // eax
  int v23; // eax
  int updated; // eax
  int v26; // eax
  signed int v27; // eax
  unsigned int v28; // edx
  CDesktopManager *v29; // rcx
  CDesktopManager *v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rdx
  unsigned int dwFlags; // [rsp+20h] [rbp-E0h]
  bool v34; // [rsp+30h] [rbp-D0h] BYREF
  char v35; // [rsp+31h] [rbp-CFh]
  unsigned __int16 v36; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v37; // [rsp+38h] [rbp-C8h] BYREF
  HRESULT v38; // [rsp+3Ch] [rbp-C4h]
  struct _RTL_CRITICAL_SECTION *v39; // [rsp+40h] [rbp-C0h] BYREF
  LARGE_INTEGER Frequency; // [rsp+48h] [rbp-B8h] BYREF
  union _LARGE_INTEGER v41; // [rsp+50h] [rbp-B0h] BYREF
  void *v42; // [rsp+58h] [rbp-A8h] BYREF
  tagMSG Msg; // [rsp+60h] [rbp-A0h] BYREF
  SC_HANDLE hSCObject[12]; // [rsp+90h] [rbp-70h] BYREF
  HANDLE pHandles[3]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v46[16]; // [rsp+108h] [rbp+8h] BYREF

  v2 = -2147221008;
  v3 = 0;
  v4 = 0;
  v42 = 0;
  v41.QuadPart = 0;
  Frequency.QuadPart = 0;
  v5 = 0;
  v36 = 0;
  hSCObject[0] = 0;
  *((_DWORD *)CDesktopManager::s_pDesktopManagerInstance + 282) = GetCurrentThreadId();
  SetLastError(0);
  if ( !QueryPerformanceFrequency(&Frequency) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    dwFlags = 2153;
LABEL_5:
    if ( v9 >= 0 )
      v9 = -2003304445;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v9, dwFlags, 0);
    goto LABEL_43;
  }
  v10 = CDesktopManager::RegisterWindowClass(v7, v6, &v36);
  v9 = v10;
  if ( v10 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v10, 0x86Bu, 0);
    goto LABEL_43;
  }
  v11 = CoInitializeEx(0, 4u);
  v2 = v11;
  v38 = v11;
  if ( v11 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v11, 0x872u, 0);
    v9 = v2;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v2, 0x873u, 0);
    goto LABEL_43;
  }
  Instance = CAnimationEngine::CreateInstance((struct CAnimationEngine **)CDesktopManager::s_pDesktopManagerInstance + 22);
  v9 = Instance;
  if ( Instance < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, Instance, 0x875u, 0);
    goto LABEL_43;
  }
  if ( (int)CDesktopManager::InitializeComObjects(CDesktopManager::s_pDesktopManagerInstance) < 0 )
    CWaitForService::WaitFor((CWaitForService *)hSCObject, v13);
  SetLastError(0);
  if ( !SetEvent(Parameter) )
  {
    v27 = GetLastError();
    v9 = v27;
    if ( v27 > 0 )
      v9 = (unsigned __int16)v27 | 0x80070000;
    dwFlags = 2177;
    goto LABEL_5;
  }
  v35 = 1;
  v37 = 0;
  while ( 1 )
  {
    if ( !v4 && (int)MilCompositionEngine_GetComposedEventId(&v37) >= 0 )
    {
      OpenComposedEvent(v37, v28, &v42);
      v4 = v42;
    }
    memset(&Msg, 0, sizeof(Msg));
    pHandles[0] = *(HANDLE *)(*((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 7) + 80LL);
    pHandles[1] = *(HANDLE *)(*((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 7) + 88LL);
    pHandles[2] = v4;
    v14 = 0;
    EnterCriticalSection(&CDesktopManager::s_csDwmInstance);
    if ( CDesktopManager::s_pDesktopManagerInstance )
    {
      v16 = CDesktopManager::CheckForActiveAnimations(v15);
      v14 = v16;
      v3 = v4 && *((_BYTE *)CDesktopManager::s_pDesktopManagerInstance + 24) | v16;
      if ( (unsigned __int8)EtwEventEnabled(Microsoft_Windows_Dwm_Udwm_Provider_Context, &UdwmAllAnimationFinished_Info) )
      {
        if ( v14 )
        {
          CDesktopManager::s_fFireAnimationFinished = 1;
        }
        else if ( CDesktopManager::s_fFireAnimationFinished == 1 )
        {
          if ( (Microsoft_Windows_Dwm_UdwmEnableBits & 1) != 0 )
            McGenEventWrite_EtwEventWriteTransfer(
              (unsigned int)&Microsoft_Windows_Dwm_Udwm_Provider_Context,
              (unsigned int)&UdwmAllAnimationFinished_Info,
              v17,
              1,
              (__int64)v46);
          CDesktopManager::s_fFireAnimationFinished = 0;
        }
      }
    }
    LeaveCriticalSection(&CDesktopManager::s_csDwmInstance);
    if ( !v3 && v5 )
    {
      v18 = 1;
      v19 = 64;
LABEL_54:
      v20 = 2;
      v5 = 0;
      goto LABEL_24;
    }
    v18 = 0;
    v19 = 64;
    if ( !v3 )
      goto LABEL_54;
    v20 = 3;
    if ( !v5 )
    {
      v41.QuadPart = -1;
      v5 = 1;
      v19 = 0;
      v21 = 0;
      v34 = 0;
      goto LABEL_27;
    }
LABEL_24:
    v21 = 0;
    v34 = 0;
    if ( v18 )
    {
      v21 = v14;
      goto LABEL_33;
    }
    if ( !v5 )
      v19 = -1;
LABEL_27:
    v22 = MsgWaitForMultipleObjectsEx(v20, pHandles, v19, 0x1CFFu, 6u);
    if ( v22 != v20 )
    {
      if ( v22 < 2 )
      {
        v39 = &CDesktopManager::s_csDwmInstance;
        EnterCriticalSection(&CDesktopManager::s_csDwmInstance);
        v34 = 0;
        v26 = CGraphicsDeviceManager::ValidateDXGIAdapterAndDevice(
                *((CGraphicsDeviceManager **)CDesktopManager::s_pDesktopManagerInstance + 7),
                &v34);
        v9 = v26;
        if ( v26 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v26, 0x90Eu, 0);
          CGuard<CDwmCS>::~CGuard<CDwmCS>(&v39);
          goto LABEL_40;
        }
        v21 = !v34;
        LeaveCriticalSection(&CDesktopManager::s_csDwmInstance);
      }
      else if ( v5 && ((v22 - 2) & 0xFFFFFEFF) == 0 )
      {
        v23 = CDesktopManager::ProcessAnimationTick(&v41, &Frequency, &v34);
        v9 = v23;
        if ( v23 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v23, 0x916u, 0);
          goto LABEL_40;
        }
        v21 = v34;
      }
      goto LABEL_33;
    }
    if ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
      break;
LABEL_33:
    if ( Msg.message == 18 )
      goto LABEL_40;
    if ( v21 )
    {
      v39 = &CDesktopManager::s_csDwmInstance;
      EnterCriticalSection(&CDesktopManager::s_csDwmInstance);
      if ( CDesktopManager::s_pDesktopManagerInstance )
      {
        updated = CWindowList::UpdateScene(*((CWindowList **)CDesktopManager::s_pDesktopManagerInstance + 53));
        v9 = updated;
        if ( updated < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, updated, 0x92Fu, 0);
          CGuard<CDwmCS>::~CGuard<CDwmCS>(&v39);
          goto LABEL_40;
        }
      }
      LeaveCriticalSection(&CDesktopManager::s_csDwmInstance);
    }
  }
  while ( Msg.message != 18 )
  {
    DispatchMessageW(&Msg);
    if ( !Msg.hwnd )
      CDesktopManager::HandleThreadMessage(Msg.message, Msg.wParam, Msg.lParam);
    if ( !PeekMessageW(&Msg, 0, 0, 0, 1u) )
      goto LABEL_33;
  }
LABEL_40:
  if ( v4 )
    CloseHandle(v4);
  v2 = v38;
  v5 = v35;
LABEL_43:
  if ( hSCObject[0] )
  {
    CloseServiceHandle(hSCObject[0]);
    hSCObject[0] = 0;
  }
  if ( v5 )
  {
    v39 = &CDesktopManager::s_csDwmInstance;
    EnterCriticalSection(&CDesktopManager::s_csDwmInstance);
    if ( CDesktopManager::s_pDesktopManagerInstance )
    {
      CDesktopManager::EnableLivePreviewInputHooks(0, 0);
      if ( v36 )
        UnregisterClassW((LPCWSTR)v36, g_hInstance);
      CDesktopManager::AbandonActiveAnimations(v29);
      v30 = CDesktopManager::s_pDesktopManagerInstance;
      v31 = *((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 33);
      if ( v31 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v31 + 16LL))(*((_QWORD *)CDesktopManager::s_pDesktopManagerInstance
                                                                 + 33));
        v30 = CDesktopManager::s_pDesktopManagerInstance;
        *((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 33) = 0;
      }
      v32 = *((_QWORD *)v30 + 34);
      if ( v32 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v32 + 16LL))(*((_QWORD *)v30 + 34));
        v30 = CDesktopManager::s_pDesktopManagerInstance;
        *((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 34) = 0;
      }
      if ( *((_QWORD *)v30 + 22) )
      {
        CAnimationEngine::Cleanup(*((CAnimationEngine **)v30 + 22));
        v30 = CDesktopManager::s_pDesktopManagerInstance;
      }
      if ( *((_QWORD *)v30 + 22) )
      {
        CAnimationEngine::Release(*((CAnimationEngine **)v30 + 22));
        v30 = CDesktopManager::s_pDesktopManagerInstance;
        *((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 22) = 0;
      }
      CDisplayBroker::Shutdown(*((CDisplayBroker **)v30 + 27));
    }
    CGuard<CDwmCS>::~CGuard<CDwmCS>(&v39);
  }
  if ( v2 >= 0 )
    CoUninitialize();
  if ( v9 >= 0 )
    return (unsigned int)v9;
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2003302654, 0x964u, 0);
  return 2291664642LL;
}

```

## disassembly

```asm
0x18001d710  push    rbp
0x18001d712  push    rbx
0x18001d713  push    rsi
0x18001d714  push    rdi
0x18001d715  push    r12
0x18001d717  push    r13
0x18001d719  push    r14
0x18001d71b  push    r15
0x18001d71d  lea     rbp, [rsp-28h]
0x18001d722  sub     rsp, 128h
0x18001d729  mov     rax, cs:__security_cookie
0x18001d730  xor     rax, rsp
0x18001d733  mov     [rbp+60h+var_48], rax
0x18001d737  mov     rbx, rcx
0x18001d73a  mov     edi, 800401F0h
0x18001d73f  xor     r15d, r15d
0x18001d742  mov     r12d, r15d
0x18001d745  mov     [rsp+160h+var_108], r15
0x18001d74a  mov     qword ptr [rsp+160h+var_110], r15
0x18001d74f  mov     qword ptr [rsp+160h+Frequency], r15
0x18001d754  xor     sil, sil
0x18001d757  mov     [rsp+160h+var_12C], r15w
0x18001d75d  mov     [rbp+60h+hSCObject], r15
0x18001d761  call    cs:__imp_GetCurrentThreadId
0x18001d767  mov     ecx, eax
0x18001d769  mov     rax, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18001d770  mov     [rax+468h], ecx
0x18001d776  xor     ecx, ecx; dwErrCode
0x18001d778  call    cs:__imp_SetLastError
0x18001d77e  lea     rcx, [rsp+160h+Frequency]; lpFrequency
0x18001d783  call    cs:__imp_QueryPerformanceFrequency
0x18001d789  lea     r14, ?s_csDwmInstance@CDesktopManager@@2VCDwmCS@@A; CDwmCS CDesktopManager::s_csDwmInstance
0x18001d790  test    eax, eax
0x18001d792  jnz     short loc_18001D7DC
0x18001d794  call    cs:__imp_GetLastError
0x18001d79a  mov     r13d, eax
0x18001d79d  test    eax, eax
0x18001d79f  jle     short loc_18001D7AC
0x18001d7a1  movzx   r13d, ax
0x18001d7a5  or      r13d, 80070000h
0x18001d7ac  mov     [rsp+160h+var_138], r15; void *
0x18001d7b1  mov     [rsp+160h+dwFlags], 869h; unsigned int
0x18001d7b9  test    r13d, r13d
0x18001d7bc  mov     eax, 88980003h
0x18001d7c1  cmovns  r13d, eax
0x18001d7c5  mov     r9d, r13d; int
0x18001d7c8  xor     r8d, r8d; unsigned int
0x18001d7cb  xor     edx, edx; int *
0x18001d7cd  mov     ecx, 14h; unsigned int
0x18001d7d2  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18001d7d7  jmp     loc_18001DA62
0x18001d7dc  lea     r8, [rsp+160h+var_12C]; unsigned __int16 *
0x18001d7e1  call    ?RegisterWindowClass@CDesktopManager@@SAJPEBGP6A_JPEAUHWND__@@I_K_J@ZPEAG@Z; CDesktopManager::RegisterWindowClass(ushort const *,__int64 (*)(HWND__ *,uint,unsigned __int64,__int64),ushort *)
0x18001d7e6  mov     r13d, eax
0x18001d7e9  test    eax, eax
0x18001d7eb  js      loc_18001DD66
0x18001d7f1  mov     edx, 4; dwCoInit
0x18001d7f6  xor     ecx, ecx; pvReserved
0x18001d7f8  call    cs:__imp_CoInitializeEx
0x18001d7fe  mov     edi, eax
0x18001d800  mov     [rsp+160h+var_124], eax
0x18001d804  test    eax, eax
0x18001d806  js      loc_18001DBC4
0x18001d80c  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18001d813  add     rcx, 0B0h; struct CAnimationEngine **
0x18001d81a  call    ?CreateInstance@CAnimationEngine@@SAJPEAPEAV1@@Z; CAnimationEngine::CreateInstance(CAnimationEngine * *)
0x18001d81f  mov     r13d, eax
0x18001d822  test    eax, eax
0x18001d824  js      loc_18001DD51
0x18001d82a  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; this
0x18001d831  call    ?InitializeComObjects@CDesktopManager@@AEAAJXZ; CDesktopManager::InitializeComObjects(void)
0x18001d836  test    eax, eax
0x18001d838  js      loc_18001DC58
0x18001d83e  xor     ecx, ecx; dwErrCode
0x18001d840  call    cs:__imp_SetLastError
0x18001d846  mov     rcx, rbx; hEvent
0x18001d849  call    cs:__imp_SetEvent
0x18001d84f  test    eax, eax
0x18001d851  jz      loc_18001DB9A
0x18001d857  mov     [rsp+160h+var_12F], 1
0x18001d85c  mov     [rsp+160h+var_128], r12d
0x18001d861  lea     rdi, ?s_csDwmInstance@CDesktopManager@@2VCDwmCS@@A; CDwmCS CDesktopManager::s_csDwmInstance
0x18001d868  nop     dword ptr [rax+rax+00000000h]
0x18001d870  test    r12, r12
0x18001d873  jz      loc_18001DC66
0x18001d879  xorps   xmm0, xmm0
0x18001d87c  movups  xmmword ptr [rsp+160h+Msg.hwnd], xmm0
0x18001d881  movups  xmmword ptr [rsp+160h+Msg.wParam], xmm0
0x18001d886  movups  xmmword ptr [rbp+60h+Msg.time], xmm0
0x18001d88a  mov     rdx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18001d891  mov     rax, [rdx+38h]
0x18001d895  mov     rcx, [rax+50h]
0x18001d899  mov     [rbp+60h+pHandles], rcx
0x18001d89d  mov     rax, [rdx+38h]
0x18001d8a1  mov     rcx, [rax+58h]
0x18001d8a5  mov     [rbp+60h+var_68], rcx
0x18001d8a9  mov     [rbp+60h+var_60], r12
0x18001d8ad  xor     r14b, r14b
0x18001d8b0  mov     rcx, rdi; lpCriticalSection
0x18001d8b3  call    cs:__imp_EnterCriticalSection
0x18001d8b9  cmp     cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA, 0; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18001d8c1  jz      short loc_18001D907
0x18001d8c3  call    ?CheckForActiveAnimations@CDesktopManager@@AEAA_NXZ; CDesktopManager::CheckForActiveAnimations(void)
0x18001d8c8  movzx   r14d, al
0x18001d8cc  test    r12, r12
0x18001d8cf  jz      loc_18001DAAC
0x18001d8d5  movzx   edx, al
0x18001d8d8  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18001d8df  or      dl, [rcx+18h]
0x18001d8e2  jz      loc_18001DAAC
0x18001d8e8  mov     r15b, 1
0x18001d8eb  lea     rdx, UdwmAllAnimationFinished_Info
0x18001d8f2  mov     rcx, cs:Microsoft_Windows_Dwm_Udwm_Provider_Context
0x18001d8f9  call    cs:__imp_EtwEventEnabled
0x18001d8ff  test    al, al
0x18001d901  jnz     loc_18001DB02
0x18001d907  mov     rcx, rdi; lpCriticalSection
0x18001d90a  call    cs:__imp_LeaveCriticalSection
0x18001d910  test    r15b, r15b
0x18001d913  jz      loc_18001DAD0
0x18001d919  xor     al, al
0x18001d91b  mov     r8d, 40h ; '@'; dwMilliseconds
0x18001d921  test    r15b, r15b
0x18001d924  jz      loc_18001DAE1
0x18001d92a  mov     ebx, 3
0x18001d92f  test    sil, sil
0x18001d932  jz      loc_18001DAB4
0x18001d938  xor     dil, dil
0x18001d93b  mov     [rsp+160h+var_130], dil
0x18001d940  test    al, al
0x18001d942  jnz     loc_18001DAEE
0x18001d948  test    sil, sil
0x18001d94b  jz      loc_18001DAF7
0x18001d951  mov     [rsp+160h+dwFlags], 6; dwFlags
0x18001d959  mov     r9d, 1CFFh; dwWakeMask
0x18001d95f  lea     rdx, [rbp+60h+pHandles]; pHandles
0x18001d963  mov     ecx, ebx; nCount
0x18001d965  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x18001d96b  cmp     eax, ebx
0x18001d96d  jz      loc_18001DA18
0x18001d973  cmp     eax, 2
0x18001d976  jb      loc_18001DB1A
0x18001d97c  test    sil, sil
0x18001d97f  jz      short loc_18001D9AF
0x18001d981  add     eax, 0FFFFFFFEh
0x18001d984  test    eax, 0FFFFFEFFh
0x18001d989  jnz     short loc_18001D9AF
0x18001d98b  lea     r8, [rsp+160h+var_130]; bool *
0x18001d990  lea     rdx, [rsp+160h+Frequency]; union _LARGE_INTEGER *
0x18001d995  lea     rcx, [rsp+160h+var_110]; union _LARGE_INTEGER *
0x18001d99a  call    ?ProcessAnimationTick@CDesktopManager@@CAJPEAT_LARGE_INTEGER@@0PEA_N@Z; CDesktopManager::ProcessAnimationTick(_LARGE_INTEGER *,_LARGE_INTEGER *,bool *)
0x18001d99f  mov     r13d, eax
0x18001d9a2  test    eax, eax
0x18001d9a4  js      loc_18001DB6C
0x18001d9aa  movzx   edi, [rsp+160h+var_130]
0x18001d9af  lea     r14, ?s_csDwmInstance@CDesktopManager@@2VCDwmCS@@A; CDwmCS CDesktopManager::s_csDwmInstance
0x18001d9b6  cmp     [rsp+160h+Msg.message], 12h
0x18001d9bb  jz      loc_18001DA4D
0x18001d9c1  test    dil, dil
0x18001d9c4  lea     rdi, ?s_csDwmInstance@CDesktopManager@@2VCDwmCS@@A; CDwmCS CDesktopManager::s_csDwmInstance
0x18001d9cb  jz      loc_18001D870
0x18001d9d1  lea     rdi, ?s_csDwmInstance@CDesktopManager@@2VCDwmCS@@A; CDwmCS CDesktopManager::s_csDwmInstance
0x18001d9d8  mov     [rsp+160h+var_120], rdi
0x18001d9dd  mov     rcx, rdi; lpCriticalSection
0x18001d9e0  call    cs:__imp_EnterCriticalSection
0x18001d9e6  nop
0x18001d9e7  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18001d9ee  test    rcx, rcx
0x18001d9f1  jz      short loc_18001DA0A
0x18001d9f3  mov     rcx, [rcx+1A8h]; this
0x18001d9fa  call    ?UpdateScene@CWindowList@@UEAAJXZ; CWindowList::UpdateScene(void)
0x18001d9ff  mov     r13d, eax
0x18001da02  test    eax, eax
0x18001da04  js      loc_18001DD0A
0x18001da0a  mov     rcx, rdi; lpCriticalSection
0x18001da0d  call    cs:__imp_LeaveCriticalSection
0x18001da13  jmp     loc_18001D870
0x18001da18  mov     [rsp+160h+dwFlags], 1; wRemoveMsg
0x18001da20  xor     r9d, r9d; wMsgFilterMax
0x18001da23  xor     r8d, r8d; wMsgFilterMin
0x18001da26  xor     edx, edx; hWnd
0x18001da28  lea     rcx, [rsp+160h+Msg]; lpMsg
0x18001da2d  call    cs:__imp_PeekMessageW
0x18001da33  test    eax, eax
0x18001da35  jz      loc_18001D9AF
0x18001da3b  cmp     [rsp+160h+Msg.message], 12h
0x18001da40  jnz     loc_18001DC0A
0x18001da46  lea     r14, ?s_csDwmInstance@CDesktopManager@@2VCDwmCS@@A; CDwmCS CDesktopManager::s_csDwmInstance
0x18001da4d  xor     r15d, r15d
0x18001da50  test    r12, r12
0x18001da53  jnz     loc_18001DD43
0x18001da59  mov     edi, [rsp+160h+var_124]
0x18001da5d  movzx   esi, [rsp+160h+var_12F]
0x18001da62  mov     rcx, [rbp+60h+hSCObject]; hSCObject
0x18001da66  test    rcx, rcx
0x18001da69  jnz     loc_18001DD7B
0x18001da6f  test    sil, sil
0x18001da72  jnz     loc_18001DD8A
0x18001da78  test    edi, edi
0x18001da7a  jns     loc_18001DE80
0x18001da80  test    r13d, r13d
0x18001da83  js      loc_18001DE8B
0x18001da89  mov     eax, r13d
0x18001da8c  mov     rcx, [rbp+60h+var_48]
0x18001da90  xor     rcx, rsp; StackCookie
0x18001da93  call    __security_check_cookie
0x18001da98  add     rsp, 128h
0x18001da9f  pop     r15
0x18001daa1  pop     r14
0x18001daa3  pop     r13
0x18001daa5  pop     r12
0x18001daa7  pop     rdi
0x18001daa8  pop     rsi
0x18001daa9  pop     rbx
0x18001daaa  pop     rbp
0x18001daab  retn
0x18001daac  xor     r15b, r15b
0x18001daaf  jmp     loc_18001D8EB
0x18001dab4  mov     qword ptr [rsp+160h+var_110], 0FFFFFFFFFFFFFFFFh
0x18001dabd  mov     sil, 1
0x18001dac0  xor     r8d, r8d
0x18001dac3  xor     dil, dil
0x18001dac6  mov     [rsp+160h+var_130], dil
0x18001dacb  jmp     loc_18001D951
0x18001dad0  test    sil, sil
0x18001dad3  jz      loc_18001D919
0x18001dad9  mov     al, 1
0x18001dadb  mov     r8d, 40h ; '@'
0x18001dae1  mov     ebx, 2
0x18001dae6  xor     sil, sil
0x18001dae9  jmp     loc_18001D938
0x18001daee  movzx   edi, r14b
0x18001daf2  jmp     loc_18001D9AF
0x18001daf7  mov     r8d, 0FFFFFFFFh
0x18001dafd  jmp     loc_18001D951
0x18001db02  test    r14b, r14b
0x18001db05  jz      loc_18001DC91
0x18001db0b  mov     cs:?s_fFireAnimationFinished@CDesktopManager@@0HA, 1; int CDesktopManager::s_fFireAnimationFinished
0x18001db15  jmp     loc_18001D907
0x18001db1a  lea     r14, ?s_csDwmInstance@CDesktopManager@@2VCDwmCS@@A; CDwmCS CDesktopManager::s_csDwmInstance
0x18001db21  mov     [rsp+160h+var_120], r14
0x18001db26  mov     rcx, r14; lpCriticalSection
0x18001db29  call    cs:__imp_EnterCriticalSection
0x18001db2f  nop
0x18001db30  mov     [rsp+160h+var_130], 0
0x18001db35  lea     rdx, [rsp+160h+var_130]; bool *
0x18001db3a  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18001db41  mov     rcx, [rcx+38h]; this
0x18001db45  call    ?ValidateDXGIAdapterAndDevice@CGraphicsDeviceManager@@QEAAJPEA_N@Z; CGraphicsDeviceManager::ValidateDXGIAdapterAndDevice(bool *)
0x18001db4a  mov     r13d, eax
0x18001db4d  test    eax, eax
0x18001db4f  js      loc_18001DCD8
0x18001db55  cmp     [rsp+160h+var_130], 0
0x18001db5a  setz    dil
0x18001db5e  mov     rcx, r14; lpCriticalSection
0x18001db61  call    cs:__imp_LeaveCriticalSection
0x18001db67  jmp     loc_18001D9B6
0x18001db6c  xor     r15d, r15d
0x18001db6f  mov     [rsp+160h+var_138], r15; void *
0x18001db74  mov     [rsp+160h+dwFlags], 916h; unsigned int
0x18001db7c  mov     r9d, eax; int
0x18001db7f  xor     r8d, r8d; unsigned int
0x18001db82  xor     edx, edx; int *
0x18001db84  mov     ecx, 14h; unsigned int
0x18001db89  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18001db8e  lea     r14, ?s_csDwmInstance@CDesktopManager@@2VCDwmCS@@A; CDwmCS CDesktopManager::s_csDwmInstance
0x18001db95  jmp     loc_18001DA50
0x18001db9a  call    cs:__imp_GetLastError
0x18001dba0  mov     r13d, eax
0x18001dba3  test    eax, eax
0x18001dba5  jle     short loc_18001DBB2
0x18001dba7  movzx   r13d, ax
0x18001dbab  or      r13d, 80070000h
0x18001dbb2  mov     [rsp+160h+var_138], r15
0x18001dbb7  mov     [rsp+160h+dwFlags], 881h
0x18001dbbf  jmp     loc_18001D7B9
0x18001dbc4  mov     [rsp+160h+var_138], r15; void *
0x18001dbc9  mov     [rsp+160h+dwFlags], 872h; unsigned int
0x18001dbd1  mov     r9d, edi; int
0x18001dbd4  xor     r8d, r8d; unsigned int
0x18001dbd7  xor     edx, edx; int *
0x18001dbd9  mov     ecx, 14h; unsigned int
0x18001dbde  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18001dbe3  mov     r13d, edi
0x18001dbe6  mov     [rsp+160h+var_138], r15; void *
0x18001dbeb  mov     [rsp+160h+dwFlags], 873h; unsigned int
0x18001dbf3  mov     r9d, edi; int
0x18001dbf6  xor     r8d, r8d; unsigned int
0x18001dbf9  xor     edx, edx; int *
0x18001dbfb  mov     ecx, 14h; unsigned int
0x18001dc00  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18001dc05  jmp     loc_18001DA62
0x18001dc0a  lea     rcx, [rsp+160h+Msg]; lpMsg
0x18001dc0f  call    cs:__imp_DispatchMessageW
0x18001dc15  cmp     [rsp+160h+Msg.hwnd], 0
0x18001dc1b  jnz     short loc_18001DC30
0x18001dc1d  mov     r8, [rsp+160h+Msg.lParam]; __int64
0x18001dc22  mov     rdx, [rsp+160h+Msg.wParam]; unsigned __int64
0x18001dc27  mov     ecx, [rsp+160h+Msg.message]; unsigned int
0x18001dc2b  call    ?HandleThreadMessage@CDesktopManager@@CAXI_K_J@Z; CDesktopManager::HandleThreadMessage(uint,unsigned __int64,__int64)
  ... truncated ...
```
