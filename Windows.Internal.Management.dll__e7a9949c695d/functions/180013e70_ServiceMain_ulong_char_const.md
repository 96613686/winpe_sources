# ServiceMain(ulong,char * * const)

- ea: `0x180013e70`
- end: `0x180013fe0`
- name: `?ServiceMain@@YAXKQEAPEAD@Z`
- size: `368`
- prototype: `void __fastcall(__int64, char **const)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000e778`
- `0x180013e70`
- `0x180013fe8`
- `0x180014088`
- `0x18001410c`
- `0x1800141a0`
- `0x180069fa8`

## import_xrefs

- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180013f00`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180013f00`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180013fa5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180013fa5`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180013ee6`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180013ee6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013eb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013eb4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013fbc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013fbc`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180013f18`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180013f18`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerA` at `0x180013ea2`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerA` at `0x180013ea2`
- `dmEnrollEngine!EnrollEngineInitialize` at `0x180013f30`
- `dmEnrollEngine!EnrollEngineInitialize` at `0x180013f30`

## string_xrefs

- `0x180013fcf`: `ServiceMain`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
    v2 = EnrollEngineInitialize(1, 0, &qword_1800FB5A0);
    if ( v2 < 0 )
    {
LABEL_12:
      LastError = v2;
      goto LABEL_3;
    }
    v6 = Microsoft::WRL::Details::OutOfProcModuleBase<Microsoft::WRL::Details::DefaultModule<2>>::Create();
    v2 = Microsoft::WRL::Details::RegisterObjects<2>(v6);
    if ( v2 >= 0 )
      dword_1800FB590 = 1;
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
0x180013e70  push    rbx
0x180013e72  sub     rsp, 20h
0x180013e76  xorps   xmm0, xmm0
0x180013e79  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x180013e83  xor     ebx, ebx
0x180013e85  lea     rdx, ?ServiceHandler@@YAXK@Z; lpHandlerProc
0x180013e8c  lea     rcx, ServiceName; "DmEnrollmentSvc"
0x180013e93  mov     qword ptr cs:ServiceStatus.dwCheckPoint, rbx
0x180013e9a  movdqu  xmmword ptr cs:ServiceStatus.dwCurrentState, xmm0
0x180013ea2  call    cs:__imp_RegisterServiceCtrlHandlerA
0x180013ea8  mov     cs:hServiceStatus, rax
0x180013eaf  test    rax, rax
0x180013eb2  jnz     short loc_180013ECE
0x180013eb4  call    cs:__imp_GetLastError
0x180013eba  mov     edx, eax; unsigned int
0x180013ebc  xor     r8d, r8d; unsigned int
0x180013ebf  mov     ecx, 1; unsigned int
0x180013ec4  call    ?UpdateServiceStatus@@YAXKKK@Z; UpdateServiceStatus(ulong,ulong,ulong)
0x180013ec9  jmp     loc_180013FB0
0x180013ece  xor     edx, edx; unsigned int
0x180013ed0  lea     ecx, [rdx+2]; unsigned int
0x180013ed3  lea     r8d, [rdx+0Ah]; unsigned int
0x180013ed7  call    ?UpdateServiceStatus@@YAXKKK@Z; UpdateServiceStatus(ulong,ulong,ulong)
0x180013edc  xor     r9d, r9d; lpName
0x180013edf  xor     r8d, r8d; bInitialState
0x180013ee2  xor     edx, edx; bManualReset
0x180013ee4  xor     ecx, ecx; lpEventAttributes
0x180013ee6  call    cs:__imp_CreateEventA
0x180013eec  mov     cs:hObject, rax
0x180013ef3  test    rax, rax
0x180013ef6  jz      short loc_180013EB4
0x180013ef8  mov     edx, 64h ; 'd'
0x180013efd  mov     rcx, rax
0x180013f00  call    cs:__imp_CoRegisterServerShutdownDelay
0x180013f06  mov     ebx, eax
0x180013f08  mov     ecx, 1
0x180013f0d  test    eax, eax
0x180013f0f  jns     short loc_180013F18
0x180013f11  xor     r8d, r8d
0x180013f14  mov     edx, eax
0x180013f16  jmp     short loc_180013EC4
0x180013f18  call    cs:__imp_RoInitialize
0x180013f1e  mov     ebx, eax
0x180013f20  test    eax, eax
0x180013f22  js      short loc_180013F59
0x180013f24  xor     edx, edx
0x180013f26  lea     r8, qword_1800FB5A0
0x180013f2d  lea     ecx, [rdx+1]
0x180013f30  call    cs:__imp_EnrollEngineInitialize
0x180013f36  mov     ebx, eax
0x180013f38  test    eax, eax
0x180013f3a  js      short loc_180013F6B
0x180013f3c  call    ?Create@?$OutOfProcModuleBase@V?$DefaultModule@$01@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@SAAEAV?$DefaultModule@$01@234@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<Microsoft::WRL::Details::DefaultModule<2>>::Create(void)
0x180013f41  mov     rcx, rax
0x180013f44  call    ??$RegisterObjects@$01@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBG@Z; Microsoft::WRL::Details::RegisterObjects<2>(Microsoft::WRL::Details::ModuleBase *,ushort const *)
0x180013f49  mov     ebx, eax
0x180013f4b  test    eax, eax
0x180013f4d  js      short loc_180013F59
0x180013f4f  mov     cs:dword_1800FB590, 1
0x180013f59  mov     edx, ebx; int
0x180013f5b  lea     rcx, aWindowsInterna_5; "Windows::Internal::Management::Enrollme"...
0x180013f62  call    ?Write@EnrollmentLogging@@SAXPEBGJ@Z; EnrollmentLogging::Write(ushort const *,long)
0x180013f67  test    ebx, ebx
0x180013f69  jns     short loc_180013F72
0x180013f6b  mov     edx, ebx
0x180013f6d  jmp     loc_180013EBC
0x180013f72  call    ?SetGlobalComSettings@@YAJXZ; SetGlobalComSettings(void)
0x180013f77  xor     r8d, r8d; unsigned int
0x180013f7a  mov     ebx, eax
0x180013f7c  test    eax, eax
0x180013f7e  jns     short loc_180013F87
0x180013f80  mov     edx, eax
0x180013f82  jmp     loc_180013EBF
0x180013f87  xor     edx, edx; unsigned int
0x180013f89  mov     cs:ServiceStatus.dwControlsAccepted, 1
0x180013f93  lea     ecx, [rdx+4]; unsigned int
0x180013f96  call    ?UpdateServiceStatus@@YAXKKK@Z; UpdateServiceStatus(ulong,ulong,ulong)
0x180013f9b  mov     rcx, cs:hObject; hHandle
0x180013fa2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180013fa5  call    cs:__imp_WaitForSingleObject
0x180013fab  call    ?StopService@@YAXXZ; StopService(void)
0x180013fb0  mov     rcx, cs:hObject; hObject
0x180013fb7  test    rcx, rcx
0x180013fba  jz      short loc_180013FCD
0x180013fbc  call    cs:__imp_CloseHandle
0x180013fc2  mov     cs:hObject, 0
0x180013fcd  mov     edx, ebx; int
0x180013fcf  lea     rcx, aServicemain_0; "ServiceMain"
0x180013fd6  add     rsp, 20h
0x180013fda  pop     rbx
0x180013fdb  jmp     ?Write@EnrollmentLogging@@SAXPEBGJ@Z; EnrollmentLogging::Write(ushort const *,long)
```
