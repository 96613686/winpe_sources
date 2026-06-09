# ServiceMain(ulong,char * * const)

- ea: `0x180014500`
- end: `0x1800146a0`
- name: `?ServiceMain@@YAXKQEAPEAD@Z`
- size: `416`
- prototype: `void __fastcall(unsigned int, char **const)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000ecdc`
- `0x180014500`
- `0x1800146a8`
- `0x180014750`
- `0x1800147dc`
- `0x18001487c`
- `0x18006b1f4`

## import_xrefs

- `combase!__imp_CoRegisterServerShutdownDelay` at `0x1800145a2`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x1800145a2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180014659`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180014659`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180014582`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180014582`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001454a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001454a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014676`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014676`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800145c0`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800145c0`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerA` at `0x180014532`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerA` at `0x180014532`
- `dmEnrollEngine!EnrollEngineInitialize` at `0x1800145de`
- `dmEnrollEngine!EnrollEngineInitialize` at `0x1800145de`

## string_xrefs

- `0x18001468f`: `ServiceMain`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, char **const a2)
{
  int v2; // ebx
  DWORD LastError; // edx
  HANDLE EventA; // rax
  int v5; // eax
  __int64 v6; // rax
  int v7; // eax

  ServiceStatus.dwServiceType = 32;
  v2 = 0;
  *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
  *(_OWORD *)&ServiceStatus.dwCurrentState = 0;
  hServiceStatus = RegisterServiceCtrlHandlerA("DmEnrollmentSvc", ServiceHandler);
  if ( !hServiceStatus || (UpdateServiceStatus(2u, 0, 0xAu), EventA = CreateEventA(0, 0, 0, 0), (hObject = EventA) == 0) )
  {
    LastError = GetLastError();
LABEL_3:
    UpdateServiceStatus(1u, LastError, 0);
    goto LABEL_16;
  }
  v5 = CoRegisterServerShutdownDelay(EventA, 100);
  v2 = v5;
  if ( v5 < 0 )
  {
    LastError = v5;
    goto LABEL_3;
  }
  v2 = RoInitialize(1);
  if ( v2 >= 0 )
  {
    v2 = EnrollEngineInitialize(1, 0, &qword_1800FF560);
    if ( v2 < 0 )
    {
LABEL_12:
      LastError = v2;
      goto LABEL_3;
    }
    v6 = Microsoft::WRL::Details::OutOfProcModuleBase<Microsoft::WRL::Details::DefaultModule<2>>::Create();
    v2 = Microsoft::WRL::Details::RegisterObjects<2>(v6);
    if ( v2 >= 0 )
      dword_1800FF550 = 1;
  }
  EnrollmentLogging::Write(L"Windows::Internal::Management::Enrollment::EnrollBase::Initialize", v2);
  if ( v2 < 0 )
    goto LABEL_12;
  v7 = SetGlobalComSettings();
  v2 = v7;
  if ( v7 < 0 )
  {
    LastError = v7;
    goto LABEL_3;
  }
  ServiceStatus.dwControlsAccepted = 1;
  UpdateServiceStatus(4u, 0, 0);
  WaitForSingleObject(hObject, 0xFFFFFFFF);
  StopService();
LABEL_16:
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  EnrollmentLogging::Write(L"ServiceMain", v2);
}

```

## disassembly

```asm
0x180014500  push    rbx
0x180014502  sub     rsp, 20h
0x180014506  xorps   xmm0, xmm0
0x180014509  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x180014513  xor     ebx, ebx
0x180014515  lea     rdx, ?ServiceHandler@@YAXK@Z; lpHandlerProc
0x18001451c  lea     rcx, ServiceName; "DmEnrollmentSvc"
0x180014523  mov     qword ptr cs:ServiceStatus.dwCheckPoint, rbx
0x18001452a  movdqu  xmmword ptr cs:ServiceStatus.dwCurrentState, xmm0
0x180014532  call    cs:__imp_RegisterServiceCtrlHandlerA
0x180014539  nop     dword ptr [rax+rax+00h]
0x18001453e  mov     cs:hServiceStatus, rax
0x180014545  test    rax, rax
0x180014548  jnz     short loc_18001456A
0x18001454a  call    cs:__imp_GetLastError
0x180014551  nop     dword ptr [rax+rax+00h]
0x180014556  mov     edx, eax; unsigned int
0x180014558  xor     r8d, r8d; unsigned int
0x18001455b  mov     ecx, 1; unsigned int
0x180014560  call    ?UpdateServiceStatus@@YAXKKK@Z; UpdateServiceStatus(ulong,ulong,ulong)
0x180014565  jmp     loc_18001466A
0x18001456a  xor     edx, edx; unsigned int
0x18001456c  lea     ecx, [rdx+2]; unsigned int
0x18001456f  lea     r8d, [rdx+0Ah]; unsigned int
0x180014573  call    ?UpdateServiceStatus@@YAXKKK@Z; UpdateServiceStatus(ulong,ulong,ulong)
0x180014578  xor     r9d, r9d; lpName
0x18001457b  xor     r8d, r8d; bInitialState
0x18001457e  xor     edx, edx; bManualReset
0x180014580  xor     ecx, ecx; lpEventAttributes
0x180014582  call    cs:__imp_CreateEventA
0x180014589  nop     dword ptr [rax+rax+00h]
0x18001458e  mov     cs:hObject, rax
0x180014595  test    rax, rax
0x180014598  jz      short loc_18001454A
0x18001459a  mov     edx, 64h ; 'd'
0x18001459f  mov     rcx, rax
0x1800145a2  call    cs:__imp_CoRegisterServerShutdownDelay
0x1800145a9  nop     dword ptr [rax+rax+00h]
0x1800145ae  mov     ebx, eax
0x1800145b0  mov     ecx, 1
0x1800145b5  test    eax, eax
0x1800145b7  jns     short loc_1800145C0
0x1800145b9  xor     r8d, r8d
0x1800145bc  mov     edx, eax
0x1800145be  jmp     short loc_180014560
0x1800145c0  call    cs:__imp_RoInitialize
0x1800145c7  nop     dword ptr [rax+rax+00h]
0x1800145cc  mov     ebx, eax
0x1800145ce  test    eax, eax
0x1800145d0  js      short loc_18001460D
0x1800145d2  xor     edx, edx
0x1800145d4  lea     r8, qword_1800FF560
0x1800145db  lea     ecx, [rdx+1]
0x1800145de  call    cs:__imp_EnrollEngineInitialize
0x1800145e5  nop     dword ptr [rax+rax+00h]
0x1800145ea  mov     ebx, eax
0x1800145ec  test    eax, eax
0x1800145ee  js      short loc_18001461F
0x1800145f0  call    ?Create@?$OutOfProcModuleBase@V?$DefaultModule@$01@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@SAAEAV?$DefaultModule@$01@234@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<Microsoft::WRL::Details::DefaultModule<2>>::Create(void)
0x1800145f5  mov     rcx, rax
0x1800145f8  call    ??$RegisterObjects@$01@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBG@Z; Microsoft::WRL::Details::RegisterObjects<2>(Microsoft::WRL::Details::ModuleBase *,ushort const *)
0x1800145fd  mov     ebx, eax
0x1800145ff  test    eax, eax
0x180014601  js      short loc_18001460D
0x180014603  mov     cs:dword_1800FF550, 1
0x18001460d  mov     edx, ebx; int
0x18001460f  lea     rcx, aWindowsInterna_5; "Windows::Internal::Management::Enrollme"...
0x180014616  call    ?Write@EnrollmentLogging@@SAXPEBGJ@Z; EnrollmentLogging::Write(ushort const *,long)
0x18001461b  test    ebx, ebx
0x18001461d  jns     short loc_180014626
0x18001461f  mov     edx, ebx
0x180014621  jmp     loc_180014558
0x180014626  call    ?SetGlobalComSettings@@YAJXZ; SetGlobalComSettings(void)
0x18001462b  xor     r8d, r8d; unsigned int
0x18001462e  mov     ebx, eax
0x180014630  test    eax, eax
0x180014632  jns     short loc_18001463B
0x180014634  mov     edx, eax
0x180014636  jmp     loc_18001455B
0x18001463b  xor     edx, edx; unsigned int
0x18001463d  mov     cs:ServiceStatus.dwControlsAccepted, 1
0x180014647  lea     ecx, [rdx+4]; unsigned int
0x18001464a  call    ?UpdateServiceStatus@@YAXKKK@Z; UpdateServiceStatus(ulong,ulong,ulong)
0x18001464f  mov     rcx, cs:hObject; hHandle
0x180014656  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180014659  call    cs:__imp_WaitForSingleObject
0x180014660  nop     dword ptr [rax+rax+00h]
0x180014665  call    ?StopService@@YAXXZ; StopService(void)
0x18001466a  mov     rcx, cs:hObject; hObject
0x180014671  test    rcx, rcx
0x180014674  jz      short loc_18001468D
0x180014676  call    cs:__imp_CloseHandle
0x18001467d  nop     dword ptr [rax+rax+00h]
0x180014682  mov     cs:hObject, 0
0x18001468d  mov     edx, ebx; int
0x18001468f  lea     rcx, aServicemain_0; "ServiceMain"
0x180014696  add     rsp, 20h
0x18001469a  pop     rbx
0x18001469b  jmp     ?Write@EnrollmentLogging@@SAXPEBGJ@Z; EnrollmentLogging::Write(ushort const *,long)
```
