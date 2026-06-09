# RunService(void)

- ea: `0x1800274e8`
- end: `0x180027850`
- name: `?RunService@@YAXXZ`
- size: `872`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180027420`

## callees

- `0x180008938`
- `0x180009034`
- `0x1800274e8`
- `0x180027858`
- `0x18002bf18`
- `0x180046010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800276fa`
- `ntdll!RtlNtStatusToDosError` at `0x1800276fa`
- `ntdll!RtlInitUnicodeString` at `0x1800276b2`
- `ntdll!RtlInitUnicodeString` at `0x1800276b2`
- `ntdll!NtOpenEvent` at `0x1800276ee`
- `ntdll!NtOpenEvent` at `0x1800276ee`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002767c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002767c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180027831`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180045249`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180027831`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180045249`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002756e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027604`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002756e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027604`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002751d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002751d`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800277cf`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800277cf`

## string_xrefs

- `0x1800277dc`: `SetServiceStatus`
- `0x1800276a6`: `\KernelObjects\MaximumCommitCondition`
- `0x18002752b`: `com\complus\src\events\tier2\service.cpp`
- `0x180027692`: `g_hServiceStopEvent = CreateEvent`

## pseudocode

```c
void RunService(void)
{
  HRESULT v0; // eax
  HRESULT Instance; // eax
  int v2; // eax
  HRESULT v3; // eax
  int v4; // esi
  int v5; // eax
  signed int v6; // eax
  struct _SVCHOST_GLOBAL_DATA *v7; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-60h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-50h] BYREF
  LPVOID ppv; // [rsp+B0h] [rbp+8h] BYREF
  struct IEvtlogger *v11; // [rsp+B8h] [rbp+10h] BYREF

  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  v0 = CoInitializeEx(0, 0);
  if ( v0 < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier2\\service.cpp", 0xC2u, 0x11u, v0);
  Instance = CoCreateInstance(&CLSID_ContextSwitcher, 0, 1u, &IID_IContextCallback, &g_pServiceContextCallBack);
  if ( Instance < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier2\\service.cpp", 0xC5u, 0x11u, Instance);
  v2 = (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall *)(struct tagComCallData *), _QWORD, GUID *, int, _QWORD))(*(_QWORD *)g_pServiceContextCallBack + 24LL))(
         g_pServiceContextCallBack,
         SetupClassFactory,
         0,
         &IID_IContextCallback,
         5,
         0);
  if ( v2 < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier2\\service.cpp", 0xC8u, 0x11u, v2);
  ppv = 0;
  v3 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv);
  if ( v3 < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier2\\service.cpp", 0xCCu, 0x11u, v3);
  v4 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 5, 1);
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v4 < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier2\\service.cpp", 0xD0u, 0x11u, v4);
  g_hServiceStopEvent = CreateEventW(0, 0, 0, 0);
  if ( !g_hServiceStopEvent )
    InternalError_Win32(
      L"com\\complus\\src\\events\\tier2\\service.cpp",
      0xD3u,
      0x10u,
      L"g_hServiceStopEvent = CreateEvent");
  RtlInitUnicodeString(&DestinationString, L"\\KernelObjects\\MaximumCommitCondition");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = NtOpenEvent(&g_hMaxCommitEvent, 0x100001u, &ObjectAttributes);
  if ( v5 < 0 )
  {
    v6 = RtlNtStatusToDosError(v5);
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    if ( v6 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier2\\service.cpp", 0xE2u, 0x11u, v6);
  }
  v7 = g_pSvchostSharedGlobals;
  if ( !g_pSvchostSharedGlobals )
  {
    InternalError_Win32(
      L"com\\complus\\src\\events\\tier2\\service.cpp",
      0xE5u,
      0x10u,
      L"g_pSvchostSharedGlobals == NULL?");
    v7 = g_pSvchostSharedGlobals;
  }
  if ( (*((unsigned int (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(void *, int), _QWORD, _DWORD))v7
        + 24))(
         &g_hServiceWait,
         L"EventSystem",
         g_hServiceStopEvent,
         StopService,
         0,
         0) )
  {
    InternalError_Win32(
      L"com\\complus\\src\\events\\tier2\\service.cpp",
      0xEDu,
      0x10u,
      L"g_pSvchostSharedGlobals->RegisterStopCallback");
  }
  g_status.dwControlsAccepted = 1;
  g_status.dwCurrentState = 4;
  g_status.dwWin32ExitCode = 0;
  *(_QWORD *)&g_status.dwCheckPoint = 0;
  if ( !SetServiceStatus(g_statusHandle, &g_status) )
    InternalError_Win32(L"com\\complus\\src\\events\\tier2\\service.cpp", 0x172u, 0x11u, L"SetServiceStatus");
  v11 = 0;
  if ( (int)GetESServiceLogger(1, &v11) >= 0 )
  {
    (*(void (__fastcall **)(struct IEvtlogger *))(*(_QWORD *)v11 + 16LL))(v11);
    v11 = 0;
  }
  CoUninitialize();
}

```

## disassembly

```asm
0x1800274e8  mov     rax, rsp
0x1800274eb  mov     [rax+18h], rbx
0x1800274ef  mov     [rax+20h], rsi
0x1800274f3  push    rdi
0x1800274f4  push    r14
0x1800274f6  push    r15
0x1800274f8  sub     rsp, 90h
0x1800274ff  xor     r14d, r14d
0x180027502  mov     [rax-68h], r14d
0x180027506  xorps   xmm0, xmm0
0x180027509  movups  xmmword ptr [rax-50h], xmm0
0x18002750d  movups  xmmword ptr [rax-40h], xmm0
0x180027511  movups  xmmword ptr [rax-30h], xmm0
0x180027515  movups  xmmword ptr [rax-60h], xmm0
0x180027519  xor     edx, edx; dwCoInit
0x18002751b  xor     ecx, ecx; pvReserved
0x18002751d  call    cs:__imp_CoInitializeEx
0x180027523  mov     [rsp+0A8h+var_68], eax
0x180027527  lea     edi, [r14+11h]
0x18002752b  lea     rbx, aComComplusSrcE_8; "com\\complus\\src\\events\\tier2\\servi"...
0x180027532  test    eax, eax
0x180027534  jns     short loc_180027549
0x180027536  mov     r8d, edi; unsigned __int16
0x180027539  mov     r9d, eax; int
0x18002753c  mov     edx, 0C2h; unsigned int
0x180027541  mov     rcx, rbx; unsigned __int16 *
0x180027544  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180027549  lea     rax, ?g_pServiceContextCallBack@@3PEAUIContextCallback@@EA; IContextCallback * g_pServiceContextCallBack
0x180027550  mov     [rsp+0A8h+ppv], rax; ppv
0x180027555  lea     r9, IID_IContextCallback; riid
0x18002755c  mov     r15d, 1
0x180027562  mov     r8d, r15d; dwClsContext
0x180027565  xor     edx, edx; pUnkOuter
0x180027567  lea     rcx, CLSID_ContextSwitcher; rclsid
0x18002756e  call    cs:__imp_CoCreateInstance
0x180027574  mov     [rsp+0A8h+var_68], eax
0x180027578  test    eax, eax
0x18002757a  jns     short loc_18002758F
0x18002757c  mov     r8d, edi; unsigned __int16
0x18002757f  mov     r9d, eax; int
0x180027582  mov     edx, 0C5h; unsigned int
0x180027587  mov     rcx, rbx; unsigned __int16 *
0x18002758a  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18002758f  mov     rcx, cs:?g_pServiceContextCallBack@@3PEAUIContextCallback@@EA; IContextCallback * g_pServiceContextCallBack
0x180027596  mov     rax, [rcx]
0x180027599  mov     [rsp+0A8h+var_80], r14
0x18002759e  mov     esi, 5
0x1800275a3  mov     dword ptr [rsp+0A8h+ppv], esi
0x1800275a7  lea     r9, IID_IContextCallback
0x1800275ae  xor     r8d, r8d
0x1800275b1  lea     rdx, ?SetupClassFactory@@YAJPEAUtagComCallData@@@Z; SetupClassFactory(tagComCallData *)
0x1800275b8  mov     rax, [rax+18h]
0x1800275bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275c1  mov     [rsp+0A8h+var_68], eax
0x1800275c5  test    eax, eax
0x1800275c7  jns     short loc_1800275DC
0x1800275c9  mov     r8d, edi; unsigned __int16
0x1800275cc  mov     r9d, eax; int
0x1800275cf  mov     edx, 0C8h; unsigned int
0x1800275d4  mov     rcx, rbx; unsigned __int16 *
0x1800275d7  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x1800275dc  mov     [rsp+0A8h+arg_0], r14
0x1800275e4  lea     rax, [rsp+0A8h+arg_0]
0x1800275ec  mov     [rsp+0A8h+ppv], rax; ppv
0x1800275f1  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x1800275f8  mov     r8d, r15d; dwClsContext
0x1800275fb  xor     edx, edx; pUnkOuter
0x1800275fd  lea     rcx, CLSID_GlobalOptions; rclsid
0x180027604  call    cs:__imp_CoCreateInstance
0x18002760a  mov     [rsp+0A8h+var_68], eax
0x18002760e  test    eax, eax
0x180027610  jns     short loc_180027625
0x180027612  mov     r8d, edi; unsigned __int16
0x180027615  mov     r9d, eax; int
0x180027618  mov     edx, 0CCh; unsigned int
0x18002761d  mov     rcx, rbx; unsigned __int16 *
0x180027620  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180027625  mov     rcx, [rsp+0A8h+arg_0]
0x18002762d  mov     rax, [rcx]
0x180027630  mov     r8, r15
0x180027633  mov     edx, esi
0x180027635  mov     rax, [rax+18h]
0x180027639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002763e  mov     esi, eax
0x180027640  mov     [rsp+0A8h+var_68], eax
0x180027644  mov     rdx, [rsp+0A8h+arg_0]
0x18002764c  mov     rcx, [rdx]
0x18002764f  mov     rax, [rcx+10h]
0x180027653  mov     rcx, rdx
0x180027656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002765b  test    esi, esi
0x18002765d  jns     short loc_180027672
0x18002765f  mov     r8d, edi; unsigned __int16
0x180027662  mov     r9d, esi; int
0x180027665  mov     edx, 0D0h; unsigned int
0x18002766a  mov     rcx, rbx; unsigned __int16 *
0x18002766d  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180027672  xor     r9d, r9d; lpName
0x180027675  xor     r8d, r8d; bInitialState
0x180027678  xor     edx, edx; bManualReset
0x18002767a  xor     ecx, ecx; lpEventAttributes
0x18002767c  call    cs:__imp_CreateEventW
0x180027682  mov     cs:?g_hServiceStopEvent@@3PEAXEA, rax; void * g_hServiceStopEvent
0x180027689  test    rax, rax
0x18002768c  jnz     short loc_1800276A6
0x18002768e  lea     r8d, [rax+10h]; unsigned __int16
0x180027692  lea     r9, aGHservicestope; "g_hServiceStopEvent = CreateEvent"
0x180027699  mov     edx, 0D3h; unsigned int
0x18002769e  mov     rcx, rbx; unsigned __int16 *
0x1800276a1  call    ?InternalError_Win32@@YA_NPEBGKG0@Z; InternalError_Win32(ushort const *,ulong,ushort,ushort const *)
0x1800276a6  lea     rdx, aKernelobjectsM; "\\KernelObjects\\MaximumCommitCondition"
0x1800276ad  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x1800276b2  call    cs:__imp_RtlInitUnicodeString
0x1800276b8  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x1800276c0  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], r14
0x1800276c5  mov     [rsp+0A8h+ObjectAttributes.Attributes], r14d
0x1800276ca  lea     rax, [rsp+0A8h+DestinationString]
0x1800276cf  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rax
0x1800276d4  xorps   xmm0, xmm0
0x1800276d7  movdqu  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800276dd  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x1800276e2  mov     edx, 100001h; DesiredAccess
0x1800276e7  lea     rcx, ?g_hMaxCommitEvent@@3PEAXEA; EventHandle
0x1800276ee  call    cs:__imp_NtOpenEvent
0x1800276f4  test    eax, eax
0x1800276f6  jns     short loc_180027727
0x1800276f8  mov     ecx, eax; Status
0x1800276fa  call    cs:__imp_RtlNtStatusToDosError
0x180027700  test    eax, eax
0x180027702  jle     short loc_18002770C
0x180027704  movzx   eax, ax
0x180027707  or      eax, 80070000h
0x18002770c  mov     [rsp+0A8h+var_68], eax
0x180027710  test    eax, eax
0x180027712  jns     short loc_180027727
0x180027714  mov     r8d, edi; unsigned __int16
0x180027717  mov     r9d, eax; int
0x18002771a  mov     edx, 0E2h; unsigned int
0x18002771f  mov     rcx, rbx; unsigned __int16 *
0x180027722  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180027727  mov     rax, cs:?g_pSvchostSharedGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_pSvchostSharedGlobals
0x18002772e  test    rax, rax
0x180027731  jnz     short loc_180027752
0x180027733  lea     r8d, [rax+10h]; unsigned __int16
0x180027737  lea     r9, aGPsvchostshare_0; "g_pSvchostSharedGlobals == NULL?"
0x18002773e  mov     edx, 0E5h; unsigned int
0x180027743  mov     rcx, rbx; unsigned __int16 *
0x180027746  call    ?InternalError_Win32@@YA_NPEBGKG0@Z; InternalError_Win32(ushort const *,ulong,ushort,ushort const *)
0x18002774b  mov     rax, cs:?g_pSvchostSharedGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_pSvchostSharedGlobals
0x180027752  mov     dword ptr [rsp+0A8h+var_80], r14d
0x180027757  mov     [rsp+0A8h+ppv], r14
0x18002775c  lea     r9, ?StopService@@YAXPEAXH@Z; StopService(void *,int)
0x180027763  mov     r8, cs:?g_hServiceStopEvent@@3PEAXEA; void * g_hServiceStopEvent
0x18002776a  lea     rdx, SourceString; "EventSystem"
0x180027771  lea     rcx, ?g_hServiceWait@@3PEAXEA; void * g_hServiceWait
0x180027778  mov     rax, [rax+0C0h]
0x18002777f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027784  test    eax, eax
0x180027786  jz      short loc_1800277A2
0x180027788  mov     r8d, 10h; unsigned __int16
0x18002778e  lea     r9, aGPsvchostshare; "g_pSvchostSharedGlobals->RegisterStopCa"...
0x180027795  mov     edx, 0EDh; unsigned int
0x18002779a  mov     rcx, rbx; unsigned __int16 *
0x18002779d  call    ?InternalError_Win32@@YA_NPEBGKG0@Z; InternalError_Win32(ushort const *,ulong,ushort,ushort const *)
0x1800277a2  mov     cs:?g_status@@3U_SERVICE_STATUS@@A.dwControlsAccepted, r15d; _SERVICE_STATUS g_status ...
0x1800277a9  mov     cs:?g_status@@3U_SERVICE_STATUS@@A.dwCurrentState, 4; _SERVICE_STATUS g_status ...
0x1800277b3  mov     cs:?g_status@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, r14d; _SERVICE_STATUS g_status ...
0x1800277ba  mov     qword ptr cs:?g_status@@3U_SERVICE_STATUS@@A.dwCheckPoint, r14; _SERVICE_STATUS g_status ...
0x1800277c1  lea     rdx, ?g_status@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x1800277c8  mov     rcx, cs:?g_statusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x1800277cf  call    cs:__imp_SetServiceStatus
0x1800277d5  test    eax, eax
0x1800277d7  jnz     short loc_1800277F0
0x1800277d9  mov     r8d, edi; unsigned __int16
0x1800277dc  lea     r9, aSetservicestat_0; "SetServiceStatus"
0x1800277e3  mov     edx, 172h; unsigned int
0x1800277e8  mov     rcx, rbx; unsigned __int16 *
0x1800277eb  call    ?InternalError_Win32@@YA_NPEBGKG0@Z; InternalError_Win32(ushort const *,ulong,ushort,ushort const *)
0x1800277f0  mov     [rsp+0A8h+arg_8], r14
0x1800277f8  lea     rdx, [rsp+0A8h+arg_8]; struct IEvtlogger **
0x180027800  mov     ecx, r15d; int
0x180027803  call    ?GetESServiceLogger@@YAJHPEAPEAUIEvtlogger@@@Z; GetESServiceLogger(int,IEvtlogger * *)
0x180027808  mov     [rsp+0A8h+var_68], eax
0x18002780c  test    eax, eax
0x18002780e  js      short loc_18002782C
0x180027810  mov     rcx, [rsp+0A8h+arg_8]
0x180027818  mov     rax, [rcx]
0x18002781b  mov     rax, [rax+10h]
0x18002781f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027824  mov     [rsp+0A8h+arg_8], r14
0x18002782c  mov     [rsp+0A8h+var_68], r14d
0x180027831  call    cs:__imp_CoUninitialize
0x180027837  lea     r11, [rsp+0A8h+var_18]
0x18002783f  mov     rbx, [r11+30h]
0x180027843  mov     rsi, [r11+38h]
0x180027847  mov     rsp, r11
0x18002784a  pop     r15
0x18002784c  pop     r14
0x18002784e  pop     rdi
0x18002784f  retn
0x180045232  push    rbp
0x180045234  sub     rsp, 40h
0x180045238  mov     rbp, rdx
0x18004523b  cmp     dword ptr [rbp+40h], 0
0x18004523f  jge     short loc_180045249
0x180045241  xor     ecx, ecx; int
0x180045243  call    ?CleanupService@@YAXH@Z; CleanupService(int)
0x180045248  nop
0x180045249  call    cs:__imp_CoUninitialize
0x18004524f  nop
0x180045250  add     rsp, 40h
0x180045254  pop     rbp
0x180045255  retn
```
