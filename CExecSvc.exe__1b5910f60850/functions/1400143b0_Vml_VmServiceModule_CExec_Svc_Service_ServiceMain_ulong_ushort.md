# Vml::VmServiceModule<CExec::Svc::Service>::ServiceMain(ulong,ushort * *)

- ea: `0x1400143b0`
- end: `0x140014495`
- name: `?ServiceMain@?$VmServiceModule@VService@Svc@CExec@@@Vml@@CAXKPEAPEAG@Z`
- size: `229`
- prototype: `void()`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x140009490`
- `0x14000f1ac`
- `0x14000f278`
- `0x1400141b4`
- `0x1400143b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400143f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140014411`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400143f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140014411`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140014443`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140014443`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140014459`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400143d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400143d4`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14001443a`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14001443a`

## string_xrefs

- `0x140014483`: `onecore\vm\common\vml\VmModules.h`
- `0x140014470`: `A derivative of VmModuleBase has not been constructed!\n   This usually occurs because a portion of the VML has been\n   used in a component that is not built from one of the VML\n   module classes.\n`

## pseudocode

```c
void Vml::VmServiceModule<CExec::Svc::Service>::ServiceMain()
{
  char *v0; // rbx
  int v1; // esi
  const char *v2; // r9
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  char *v5; // [rsp+58h] [rbp+20h]

  try
  {
    v0 = (char *)Vml::VmModuleBase::gm_ModuleBase;
    if ( !Vml::VmModuleBase::gm_ModuleBase )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(2) )
        VmlDebugTrace(
          2,
          L"A derivative of VmModuleBase has not been constructed!\n"
           "   This usually occurs because a portion of the VML has been\n"
           "   used in a component that is not built from one of the VML\n"
           "   module classes.\n");
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xA9,
        (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
        v3);
    }
    v1 = 0;
    v5 = (char *)Vml::VmModuleBase::gm_ModuleBase;
    *((_DWORD *)v0 + 20) = GetCurrentThreadId();
    Vml::VmExeModule<CExec::Svc::Service>::Run(v0);
  }
  catch ( ... )
  {
    v1 = wil::details::in1diag3::Log_CaughtException(
           retaddr,
           (void *)0xC61,
           (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
           v2);
    v0 = v5;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)v0 + 1);
  if ( *((_DWORD *)v0 + 27) != 1 && *((_QWORD *)v0 + 17) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)v0 + 1);
    if ( *((_DWORD *)v0 + 27) != 1 )
      *(_QWORD *)(v0 + 124) = 0;
    *((_DWORD *)v0 + 27) = 1;
    *((_DWORD *)v0 + 29) = v1;
    SetServiceStatus(*((SERVICE_STATUS_HANDLE *)v0 + 17), (LPSERVICE_STATUS)(v0 + 104));
    LeaveCriticalSection((LPCRITICAL_SECTION)v0 + 1);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)v0 + 1);
}

```

## disassembly

```asm
0x1400143b0  mov     [rsp+arg_0], rbx
0x1400143b5  push    rsi
0x1400143b6  push    rdi
0x1400143b7  push    r14
0x1400143b9  sub     rsp, 20h
0x1400143bd  mov     rbx, cs:?gm_ModuleBase@VmModuleBase@Vml@@1PEAV12@EA; Vml::VmModuleBase * Vml::VmModuleBase::gm_ModuleBase
0x1400143c4  test    rbx, rbx
0x1400143c7  jz      loc_140014460
0x1400143cd  xor     esi, esi
0x1400143cf  mov     [rsp+38h+arg_18], rbx
0x1400143d4  call    cs:__imp_GetCurrentThreadId
0x1400143da  mov     [rbx+50h], eax
0x1400143dd  mov     rcx, rbx; lpContext
0x1400143e0  call    ?Run@?$VmExeModule@VService@Svc@CExec@@@Vml@@QEAAHH@Z; Vml::VmExeModule<CExec::Svc::Service>::Run(int)
0x1400143e5  nop
0x1400143e6  jmp     short loc_1400143F1
0x1400143e8  mov     esi, [rsp+38h+arg_10]
0x1400143ec  mov     rbx, [rsp+38h+arg_18]
0x1400143f1  lea     rdi, [rbx+28h]
0x1400143f5  mov     rcx, rdi; lpCriticalSection
0x1400143f8  call    cs:__imp_EnterCriticalSection
0x1400143fe  cmp     dword ptr [rbx+6Ch], 1
0x140014402  jz      short loc_140014449
0x140014404  cmp     qword ptr [rbx+88h], 0
0x14001440c  jz      short loc_140014449
0x14001440e  mov     rcx, rdi; lpCriticalSection
0x140014411  call    cs:__imp_EnterCriticalSection
0x140014417  cmp     dword ptr [rbx+6Ch], 1
0x14001441b  jz      short loc_140014425
0x14001441d  mov     qword ptr [rbx+7Ch], 0
0x140014425  mov     dword ptr [rbx+6Ch], 1
0x14001442c  mov     [rbx+74h], esi
0x14001442f  lea     rdx, [rbx+68h]; lpServiceStatus
0x140014433  mov     rcx, [rbx+88h]; hServiceStatus
0x14001443a  call    cs:__imp_SetServiceStatus
0x140014440  mov     rcx, rdi; lpCriticalSection
0x140014443  call    cs:__imp_LeaveCriticalSection
0x140014449  mov     rcx, rdi
0x14001444c  mov     rbx, [rsp+38h+arg_0]
0x140014451  add     rsp, 20h
0x140014455  pop     r14
0x140014457  pop     rdi
0x140014458  pop     rsi
0x140014459  jmp     cs:__imp_LeaveCriticalSection
0x140014460  mov     ebx, 2
0x140014465  mov     ecx, ebx
0x140014467  call    VmlIsDebugTraceEnabled
0x14001446c  test    eax, eax
0x14001446e  jz      short loc_14001447E
0x140014470  lea     rdx, aADerivativeOfV; "A derivative of VmModuleBase has not be"...
0x140014477  mov     ecx, ebx
0x140014479  call    VmlDebugTrace
0x14001447e  mov     rcx, [rsp+38h]; this
0x140014483  lea     r8, aOnecoreVmCommo; "onecore\\vm\\common\\vml\\VmModules.h"
0x14001448a  mov     edx, 0A9h; void *
0x14001448f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
