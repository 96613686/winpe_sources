# ServiceMain(ulong,ushort * *)

- ea: `0x1800091c0`
- end: `0x180009582`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `962`
- prototype: `void __fastcall(__int64, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180004170`
- `0x18000584c`
- `0x180005f9c`
- `0x180007430`
- `0x1800091c0`
- `0x18000a7d0`
- `0x18000a7f8`
- `0x18000a838`
- `0x18000a918`
- `0x18001e730`
- `0x18001e770`
- `0x18001e8d4`
- `0x18001ec98`
- `0x180021710`
- `0x180021a18`
- `0x180046010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180009299`
- `ntdll!RtlAllocateHeap` at `0x180009299`
- `ntdll!RtlPublishWnfStateData` at `0x180009545`
- `ntdll!RtlPublishWnfStateData` at `0x180009545`
- `ntdll!RtlFreeHeap` at `0x1800092ff`
- `ntdll!RtlFreeHeap` at `0x18000938c`
- `ntdll!RtlFreeHeap` at `0x1800092ff`
- `ntdll!RtlFreeHeap` at `0x18000938c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000936b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000936b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800093f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800093f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800092e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800093bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800092e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800093bb`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180009338`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180009338`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800093a5`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800093a5`
- `RPCRT4!RpcBindingVectorFree` at `0x18000950f`
- `RPCRT4!RpcBindingVectorFree` at `0x18000950f`
- `combase!__imp_CoGetSharedServiceId` at `0x18000945b`
- `combase!__imp_CoGetSharedServiceId` at `0x18000945b`
- `ext-ms-win-ntuser-misc-l1-1-0!UnregisterDeviceNotification` at `0x1800092cc`
- `ext-ms-win-ntuser-misc-l1-1-0!UnregisterDeviceNotification` at `0x1800092cc`
- `ext-ms-win-ntuser-misc-l1-1-0!RegisterDeviceNotificationW` at `0x1800093e7`
- `ext-ms-win-ntuser-misc-l1-1-0!RegisterDeviceNotificationW` at `0x1800093e7`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, unsigned __int16 **a2)
{
  int SharedServiceId; // ebp
  NaturalAuthTraceLogging *v3; // rcx
  HANDLE *Heap; // rax
  HANDLE *v5; // rsi
  unsigned int LastError; // edi
  unsigned int v7; // r8d
  HANDLE v8; // rcx
  HANDLE EventW; // rax
  struct SERVICE_STATUS_HANDLE__ *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rdi
  unsigned int v13; // eax
  _OWORD NotificationFilter[2]; // [rsp+40h] [rbp-68h] BYREF

  SharedServiceId = 0;
  memset(NotificationFilter, 0, sizeof(NotificationFilter));
  qword_18005F728 = 0;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_WPP_GUID;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  WPP_MAIN_CB = 0;
  qword_18005F730 = 1;
  WppInitUm(a1, a2);
  v3 = (NaturalAuthTraceLogging *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_2da9a8550d1e32063426f0effd98d727_Traceguids);
  *(_QWORD *)&g_ssService.dwCurrentState = 2;
  g_ssService.dwServiceType = 32;
  *(_QWORD *)&g_ssService.dwWin32ExitCode = 0;
  *(_QWORD *)&g_ssService.dwCheckPoint = 0;
  NaturalAuthTraceLogging::Initialize(v3);
  Heap = (HANDLE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x10u);
  v5 = Heap;
  if ( !Heap )
  {
    LastError = 14;
    goto LABEL_6;
  }
  *(_OWORD *)Heap = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  v5[1] = EventW;
  if ( !EventW )
    goto LABEL_16;
  g_hssService = RegisterServiceCtrlHandlerExW(L"NaturalAuthentication", NApServiceCtrlHandler, EventW);
  if ( !g_hssService )
  {
    CloseHandle(v5[1]);
LABEL_16:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
    goto LABEL_21;
  }
  if ( (unsigned __int8)IsUnregisterDeviceNotificationPresent() )
  {
    *(_QWORD *)&NotificationFilter[0] = 0x500000020LL;
    g_hDeviceNotification = RegisterDeviceNotificationW(g_hssService, NotificationFilter, 5u);
    if ( !g_hDeviceNotification )
    {
LABEL_21:
      LastError = GetLastError();
      if ( !LastError )
        goto LABEL_14;
      goto LABEL_6;
    }
  }
  LastError = NAPluginManagerInitialize(v10);
  if ( LastError )
    goto LABEL_6;
  v11 = Microsoft::WRL::Details::OutOfProcModuleBase<NaturalAuthServiceModule>::Create();
  if ( !*(_QWORD *)(v11 + 8) )
  {
    byte_18005FD78 = 1;
    qword_18005FD60 = (__int64)off_180047198;
    byte_18005FD68 = 0;
    *(_QWORD *)(v11 + 8) = &qword_18005FD60;
  }
  v12 = Microsoft::WRL::Details::OutOfProcModuleBase<NaturalAuthServiceModule>::Create();
  SharedServiceId = CoGetSharedServiceId(v12 + 16);
  if ( SharedServiceId >= 0 )
    SharedServiceId = Microsoft::WRL::Details::RegisterObjects<2>(v12);
  if ( SharedServiceId < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_2da9a8550d1e32063426f0effd98d727_Traceguids,
        (unsigned int)SharedServiceId);
    LastError = 1359;
    goto LABEL_6;
  }
  LastError = NAEnableRpcInterface(qword_1800481A0, 0);
  if ( LastError )
  {
LABEL_6:
    NAPluginManagerUninitialize();
    if ( g_hDeviceNotification && (unsigned __int8)IsUnregisterDeviceNotificationPresent() )
    {
      UnregisterDeviceNotification(g_hDeviceNotification);
      g_hDeviceNotification = 0;
    }
    if ( v5 )
    {
      v8 = v5[1];
      if ( v8 )
        CloseHandle(v8);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
    }
    g_ssService.dwWin32ExitCode = LastError;
    g_ssService.dwCurrentState = 1;
    NaturalAuthTraceLogging::Cleanup((NaturalAuthTraceLogging *)(unsigned int)SharedServiceId, LastError, v7);
    WppCleanupUm();
    goto LABEL_14;
  }
  LastError = (*((__int64 (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned __int8), HANDLE *, int))g_pSvchostSharedGlobals
               + 24))(
                v5,
                L"NaturalAuthentication",
                v5[1],
                NApStopCallback,
                v5,
                24);
  if ( LastError )
  {
    NADisableRpcInterface(qword_1800481A0);
    RpcBindingVectorFree(&g_pBindingVector);
    g_pBindingVector = 0;
    goto LABEL_6;
  }
  g_ssService.dwControlsAccepted = 135;
  g_ssService.dwCurrentState = 4;
  v13 = RtlPublishWnfStateData(WNF_NASV_SERVICE_RUNNING, 0, 0, 0, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_2da9a8550d1e32063426f0effd98d727_Traceguids, v13);
LABEL_14:
  *(_QWORD *)&g_ssService.dwCheckPoint = 0;
  SetServiceStatus(g_hssService, &g_ssService);
}

```

## disassembly

```asm
0x1800091c0  push    rbx
0x1800091c2  push    rbp
0x1800091c3  push    rsi
0x1800091c4  push    rdi
0x1800091c5  push    r13
0x1800091c7  push    r14
0x1800091c9  sub     rsp, 78h
0x1800091cd  mov     rax, cs:__security_cookie
0x1800091d4  xor     rax, rsp
0x1800091d7  mov     [rsp+0A8h+var_48], rax
0x1800091dc  mov     rbx, cs:WNF_NASV_SERVICE_RUNNING
0x1800091e3  xorps   xmm0, xmm0
0x1800091e6  xor     r14d, r14d
0x1800091e9  mov     ebp, r14d
0x1800091ec  movups  [rsp+0A8h+NotificationFilter], xmm0
0x1800091f1  movups  [rsp+0A8h+var_58], xmm0
0x1800091f6  lea     rax, WPP_ThisDir_CTLGUID_WPP_GUID
0x1800091fd  mov     cs:qword_18005F728, r14
0x180009204  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18000920b  lea     rax, WPP_MAIN_CB
0x180009212  mov     cs:WPP_GLOBAL_Control, rax
0x180009219  mov     cs:WPP_MAIN_CB, r14
0x180009220  mov     cs:qword_18005F730, 1
0x18000922b  call    WppInitUm
0x180009230  mov     rcx, cs:WPP_GLOBAL_Control
0x180009237  lea     r13, WPP_GLOBAL_Control
0x18000923e  cmp     rcx, r13
0x180009241  jz      short loc_18000925D
0x180009243  test    byte ptr [rcx+1Ch], 4
0x180009247  jz      short loc_18000925D
0x180009249  mov     rcx, [rcx+10h]
0x18000924d  lea     edx, [r14+0Ah]
0x180009251  lea     r8, WPP_2da9a8550d1e32063426f0effd98d727_Traceguids
0x180009258  call    WPP_SF_
0x18000925d  mov     edi, 20h ; ' '
0x180009262  mov     qword ptr cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwCurrentState, 2; _SERVICE_STATUS g_ssService ...
0x18000926d  mov     cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwServiceType, edi; _SERVICE_STATUS g_ssService ...
0x180009273  mov     qword ptr cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, r14; _SERVICE_STATUS g_ssService ...
0x18000927a  mov     qword ptr cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwCheckPoint, r14; _SERVICE_STATUS g_ssService ...
0x180009281  call    ?Initialize@NaturalAuthTraceLogging@@YAXXZ; NaturalAuthTraceLogging::Initialize(void)
0x180009286  mov     rcx, gs:60h
0x18000928f  lea     r8d, [rdi-10h]; Size
0x180009293  xor     edx, edx; Flags
0x180009295  mov     rcx, [rcx+30h]; HeapHandle
0x180009299  call    cs:__imp_RtlAllocateHeap
0x18000929f  mov     rsi, rax
0x1800092a2  test    rax, rax
0x1800092a5  jnz     loc_180009358
0x1800092ab  lea     edi, [rax+0Eh]
0x1800092ae  call    ?NAPluginManagerUninitialize@@YAXXZ; NAPluginManagerUninitialize(void)
0x1800092b3  cmp     cs:?g_hDeviceNotification@@3PEAXEA, r14; void * g_hDeviceNotification
0x1800092ba  jz      short loc_1800092D9
0x1800092bc  call    IsUnregisterDeviceNotificationPresent
0x1800092c1  test    al, al
0x1800092c3  jz      short loc_1800092D9
0x1800092c5  mov     rcx, cs:?g_hDeviceNotification@@3PEAXEA; Handle
0x1800092cc  call    cs:__imp_UnregisterDeviceNotification
0x1800092d2  mov     cs:?g_hDeviceNotification@@3PEAXEA, r14; void * g_hDeviceNotification
0x1800092d9  test    rsi, rsi
0x1800092dc  jz      short loc_180009305
0x1800092de  mov     rcx, [rsi+8]; hObject
0x1800092e2  test    rcx, rcx
0x1800092e5  jz      short loc_1800092ED
0x1800092e7  call    cs:__imp_CloseHandle
0x1800092ed  mov     rcx, gs:60h
0x1800092f6  mov     r8, rsi; P
0x1800092f9  xor     edx, edx; Flags
0x1800092fb  mov     rcx, [rcx+30h]; HeapHandle
0x1800092ff  call    cs:__imp_RtlFreeHeap
0x180009305  mov     edx, edi; int
0x180009307  mov     cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, edi; _SERVICE_STATUS g_ssService ...
0x18000930d  mov     ecx, ebp; this
0x18000930f  mov     cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwCurrentState, 1; _SERVICE_STATUS g_ssService ...
0x180009319  call    ?Cleanup@NaturalAuthTraceLogging@@YAXJK@Z; NaturalAuthTraceLogging::Cleanup(long,ulong)
0x18000931e  call    WppCleanupUm
0x180009323  mov     rcx, cs:?g_hssService@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x18000932a  lea     rdx, ?g_ssService@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180009331  mov     qword ptr cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwCheckPoint, r14; _SERVICE_STATUS g_ssService ...
0x180009338  call    cs:__imp_SetServiceStatus
0x18000933e  mov     rcx, [rsp+0A8h+var_48]
0x180009343  xor     rcx, rsp; StackCookie
0x180009346  call    __security_check_cookie
0x18000934b  add     rsp, 78h
0x18000934f  pop     r14
0x180009351  pop     r13
0x180009353  pop     rdi
0x180009354  pop     rsi
0x180009355  pop     rbp
0x180009356  pop     rbx
0x180009357  retn
0x180009358  xor     r9d, r9d; lpName
0x18000935b  xorps   xmm0, xmm0
0x18000935e  xor     r8d, r8d; bInitialState
0x180009361  xor     ecx, ecx; lpEventAttributes
0x180009363  movdqu  xmmword ptr [rax], xmm0
0x180009367  lea     edx, [r9+1]; bManualReset
0x18000936b  call    cs:__imp_CreateEventW
0x180009371  mov     [rsi+8], rax
0x180009375  test    rax, rax
0x180009378  jnz     short loc_180009394
0x18000937a  mov     rcx, gs:60h
0x180009383  mov     r8, rsi; P
0x180009386  xor     edx, edx; Flags
0x180009388  mov     rcx, [rcx+30h]; HeapHandle
0x18000938c  call    cs:__imp_RtlFreeHeap
0x180009392  jmp     short loc_1800093F9
0x180009394  mov     r8, rax; lpContext
0x180009397  lea     rdx, ?NApServiceCtrlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x18000939e  lea     rcx, Annotation; "NaturalAuthentication"
0x1800093a5  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800093ab  mov     cs:?g_hssService@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_hssService
0x1800093b2  test    rax, rax
0x1800093b5  jnz     short loc_1800093C3
0x1800093b7  mov     rcx, [rsi+8]; hObject
0x1800093bb  call    cs:__imp_CloseHandle
0x1800093c1  jmp     short loc_18000937A
0x1800093c3  call    IsUnregisterDeviceNotificationPresent
0x1800093c8  test    al, al
0x1800093ca  jz      short loc_18000940E
0x1800093cc  mov     rcx, cs:?g_hssService@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hRecipient
0x1800093d3  lea     rdx, [rsp+0A8h+NotificationFilter]; NotificationFilter
0x1800093d8  mov     r8d, 5; Flags
0x1800093de  mov     dword ptr [rsp+0A8h+NotificationFilter], edi
0x1800093e2  mov     dword ptr [rsp+0A8h+NotificationFilter+4], r8d
0x1800093e7  call    cs:__imp_RegisterDeviceNotificationW
0x1800093ed  mov     cs:?g_hDeviceNotification@@3PEAXEA, rax; void * g_hDeviceNotification
0x1800093f4  test    rax, rax
0x1800093f7  jnz     short loc_18000940E
0x1800093f9  call    cs:__imp_GetLastError
0x1800093ff  mov     edi, eax
0x180009401  test    eax, eax
0x180009403  jz      loc_180009323
0x180009409  jmp     loc_1800092AE
0x18000940e  call    ?NAPluginManagerInitialize@@YAKPEAUSERVICE_STATUS_HANDLE__@@@Z; NAPluginManagerInitialize(SERVICE_STATUS_HANDLE__ *)
0x180009413  mov     edi, eax
0x180009415  test    eax, eax
0x180009417  jnz     loc_1800092AE
0x18000941d  call    ?Create@?$OutOfProcModuleBase@VNaturalAuthServiceModule@@@Details@WRL@Microsoft@@SAAEAVNaturalAuthServiceModule@@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<NaturalAuthServiceModule>::Create(void)
0x180009422  cmp     [rax+8], r14
0x180009426  jnz     short loc_18000944F
0x180009428  lea     rcx, off_180047198
0x18000942f  mov     cs:byte_18005FD78, 1
0x180009436  mov     cs:qword_18005FD60, rcx
0x18000943d  lea     rcx, qword_18005FD60
0x180009444  mov     cs:byte_18005FD68, r14b
0x18000944b  mov     [rax+8], rcx
0x18000944f  call    ?Create@?$OutOfProcModuleBase@VNaturalAuthServiceModule@@@Details@WRL@Microsoft@@SAAEAVNaturalAuthServiceModule@@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<NaturalAuthServiceModule>::Create(void)
0x180009454  mov     rdi, rax
0x180009457  lea     rcx, [rax+10h]
0x18000945b  call    cs:__imp_CoGetSharedServiceId
0x180009461  mov     ebp, eax
0x180009463  test    eax, eax
0x180009465  js      short loc_180009471
0x180009467  mov     rcx, rdi
0x18000946a  call    ??$RegisterObjects@$01@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBG@Z; Microsoft::WRL::Details::RegisterObjects<2>(Microsoft::WRL::Details::ModuleBase *,ushort const *)
0x18000946f  mov     ebp, eax
0x180009471  test    ebp, ebp
0x180009473  jns     short loc_1800094A9
0x180009475  mov     rcx, cs:WPP_GLOBAL_Control
0x18000947c  cmp     rcx, r13
0x18000947f  jz      short loc_18000949F
0x180009481  test    byte ptr [rcx+1Ch], 1
0x180009485  jz      short loc_18000949F
0x180009487  mov     rcx, [rcx+10h]
0x18000948b  lea     r8, WPP_2da9a8550d1e32063426f0effd98d727_Traceguids
0x180009492  mov     edx, 0Bh
0x180009497  mov     r9d, ebp
0x18000949a  call    WPP_SF_d
0x18000949f  mov     edi, 54Fh
0x1800094a4  jmp     loc_1800092AE
0x1800094a9  xor     edx, edx; StringSecurityDescriptor
0x1800094ab  lea     rcx, qword_1800481A0; IfSpec
0x1800094b2  call    ?NAEnableRpcInterface@@YAKPEAXPEBG@Z; NAEnableRpcInterface(void *,ushort const *)
0x1800094b7  mov     edi, eax
0x1800094b9  test    eax, eax
0x1800094bb  jnz     loc_1800092AE
0x1800094c1  mov     rax, cs:?g_pSvchostSharedGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_pSvchostSharedGlobals
0x1800094c8  lea     r9, ?NApStopCallback@@YAXPEAXE@Z; NApStopCallback(void *,uchar)
0x1800094cf  mov     r8, [rsi+8]
0x1800094d3  lea     rdx, Annotation; "NaturalAuthentication"
0x1800094da  mov     [rsp+0A8h+var_80], 18h
0x1800094e2  mov     rcx, rsi
0x1800094e5  mov     [rsp+0A8h+var_88], rsi
0x1800094ea  mov     rax, [rax+0C0h]
0x1800094f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094f6  mov     edi, eax
0x1800094f8  test    eax, eax
0x1800094fa  jz      short loc_180009521
0x1800094fc  lea     rcx, qword_1800481A0; void *
0x180009503  call    ?NADisableRpcInterface@@YAXPEAX@Z; NADisableRpcInterface(void *)
0x180009508  lea     rcx, ?g_pBindingVector@@3PEAU_RPC_BINDING_VECTOR@@EA; BindingVector
0x18000950f  call    cs:__imp_RpcBindingVectorFree
0x180009515  mov     cs:?g_pBindingVector@@3PEAU_RPC_BINDING_VECTOR@@EA, r14; _RPC_BINDING_VECTOR * g_pBindingVector
0x18000951c  jmp     loc_1800092AE
0x180009521  xor     r9d, r9d
0x180009524  mov     cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 87h; _SERVICE_STATUS g_ssService ...
0x18000952e  xor     r8d, r8d
0x180009531  mov     cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwCurrentState, 4; _SERVICE_STATUS g_ssService ...
0x18000953b  xor     edx, edx
0x18000953d  mov     [rsp+0A8h+var_88], r14
0x180009542  mov     rcx, rbx
0x180009545  call    cs:__imp_RtlPublishWnfStateData
0x18000954b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009552  cmp     rcx, r13
0x180009555  jz      loc_180009323
0x18000955b  test    byte ptr [rcx+1Ch], 4
0x18000955f  jz      loc_180009323
0x180009565  mov     rcx, [rcx+10h]
0x180009569  lea     r8, WPP_2da9a8550d1e32063426f0effd98d727_Traceguids
0x180009570  mov     edx, 0Ch
0x180009575  mov     r9d, eax
0x180009578  call    WPP_SF_d
0x18000957d  jmp     loc_180009323
```
