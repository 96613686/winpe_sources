# WaaSRemediationAgent::~WaaSRemediationAgent(void)

- ea: `0x180047750`
- end: `0x1800478c5`
- name: `??1WaaSRemediationAgent@@UEAA@XZ`
- size: `373`
- prototype: `void __fastcall(WaaSRemediationAgent *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180048e80`

## callees

- `0x180005584`
- `0x18002e81c`
- `0x180039564`
- `0x180047750`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800478be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800477cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800477cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047879`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047879`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047895`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047895`

## string_xrefs

- `0x1800477b4`: `Uninitializing WaaS Remediation agent. Waiting for the lock..`
- `0x1800477d2`: `Uninitializing WaaS Remediation agent. Acquired the lock!`

## pseudocode

```c
void __fastcall WaaSRemediationAgent::~WaaSRemediationAgent(WaaSRemediationAgent *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  char *v6; // rcx

  *(_QWORD *)this = &WaaSRemediationAgent::`vftable'{for `IWaaSRemediation'};
  *((_QWORD *)this + 1) = &WaaSRemediationAgent::`vftable'{for `IWaaSRemediationEx2'};
  *((_QWORD *)this + 2) = &WaaSRemediationAgent::`vftable'{for `ITaskHandler'};
  *((_QWORD *)this + 3) = &WaaSRemediationAgent::`vftable'{for `ITaskCompletionCallback'};
  *((_QWORD *)this + 4) = &WaaSRemediationAgent::`vftable'{for `IWaaSInPlaceUpgrade'};
  *((_QWORD *)this + 5) = &WaaSRemediationAgent::`vftable'{for `IWaaSDeviceFeatureEvaluation'};
  *((_QWORD *)this + 6) = &WaaSRemediationAgent::`vftable'{for `IWaaSGeneralizeImage'};
  *((_QWORD *)this + 7) = &WaaSRemediationAgent::`vftable'{for `IWaaSGeneralizeDeviceFeatures'};
  LogLevelW(4u, L"Uninitializing WaaS Remediation agent. Waiting for the lock..");
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  LogLevelW(4u, L"Uninitializing WaaS Remediation agent. Acquired the lock!");
  if ( *((_BYTE *)this + 128) )
  {
    *(_WORD *)((char *)this + 129) = 0;
    v2 = *((_QWORD *)this + 18);
    if ( v2 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
      *((_QWORD *)this + 18) = 0;
    }
    *((_BYTE *)this + 128) = 0;
  }
  v3 = *((_QWORD *)this + 8);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = (void *)*((_QWORD *)this + 19);
  if ( v4 )
  {
    operator delete(v4, (const struct std::nothrow_t *)0x90);
    *((_QWORD *)this + 19) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 20);
  if ( v5 )
  {
    operator delete(v5, (const struct std::nothrow_t *)0x90);
    *((_QWORD *)this + 20) = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  SvcRelease();
  v6 = (char *)*((_QWORD *)this + 24);
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 9) = &WaasMedic::CLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
}

```

## disassembly

```asm
0x180047750  mov     [rsp+arg_0], rbx
0x180047755  push    rdi
0x180047756  sub     rsp, 20h
0x18004775a  mov     rbx, rcx
0x18004775d  lea     rax, ??_7WaaSRemediationAgent@@6BIWaaSRemediation@@@; const WaaSRemediationAgent::`vftable'{for `IWaaSRemediation'}
0x180047764  mov     [rcx], rax
0x180047767  lea     rax, ??_7WaaSRemediationAgent@@6BIWaaSRemediationEx2@@@; const WaaSRemediationAgent::`vftable'{for `IWaaSRemediationEx2'}
0x18004776e  mov     [rcx+8], rax
0x180047772  lea     rax, ??_7WaaSRemediationAgent@@6BITaskHandler@@@; const WaaSRemediationAgent::`vftable'{for `ITaskHandler'}
0x180047779  mov     [rcx+10h], rax
0x18004777d  lea     rax, ??_7WaaSRemediationAgent@@6BITaskCompletionCallback@@@; const WaaSRemediationAgent::`vftable'{for `ITaskCompletionCallback'}
0x180047784  mov     [rcx+18h], rax
0x180047788  lea     rax, ??_7WaaSRemediationAgent@@6BIWaaSInPlaceUpgrade@@@; const WaaSRemediationAgent::`vftable'{for `IWaaSInPlaceUpgrade'}
0x18004778f  mov     [rcx+20h], rax
0x180047793  lea     rax, ??_7WaaSRemediationAgent@@6BIWaaSDeviceFeatureEvaluation@@@; const WaaSRemediationAgent::`vftable'{for `IWaaSDeviceFeatureEvaluation'}
0x18004779a  mov     [rcx+28h], rax
0x18004779e  lea     rax, ??_7WaaSRemediationAgent@@6BIWaaSGeneralizeImage@@@; const WaaSRemediationAgent::`vftable'{for `IWaaSGeneralizeImage'}
0x1800477a5  mov     [rcx+30h], rax
0x1800477a9  lea     rax, ??_7WaaSRemediationAgent@@6BIWaaSGeneralizeDeviceFeatures@@@; const WaaSRemediationAgent::`vftable'{for `IWaaSGeneralizeDeviceFeatures'}
0x1800477b0  mov     [rcx+38h], rax
0x1800477b4  lea     rdx, aUninitializing; "Uninitializing WaaS Remediation agent. "...
0x1800477bb  mov     ecx, 4; unsigned __int8
0x1800477c0  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800477c5  lea     rdi, [rbx+58h]
0x1800477c9  mov     rcx, rdi; lpCriticalSection
0x1800477cc  call    cs:__imp_EnterCriticalSection
0x1800477d2  lea     rdx, aUninitializing_0; "Uninitializing WaaS Remediation agent. "...
0x1800477d9  mov     ecx, 4; unsigned __int8
0x1800477de  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800477e3  cmp     byte ptr [rbx+80h], 0
0x1800477ea  jz      short loc_18004781F
0x1800477ec  mov     word ptr [rbx+81h], 0
0x1800477f5  mov     rcx, [rbx+90h]
0x1800477fc  test    rcx, rcx
0x1800477ff  jz      short loc_180047818
0x180047801  mov     rax, [rcx]
0x180047804  mov     rax, [rax+10h]
0x180047808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004780d  mov     qword ptr [rbx+90h], 0
0x180047818  mov     byte ptr [rbx+80h], 0
0x18004781f  mov     rcx, [rbx+40h]
0x180047823  test    rcx, rcx
0x180047826  jz      short loc_180047834
0x180047828  mov     rax, [rcx]
0x18004782b  mov     rax, [rax+10h]
0x18004782f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047834  mov     rcx, [rbx+98h]; void *
0x18004783b  test    rcx, rcx
0x18004783e  jz      short loc_180047855
0x180047840  mov     edx, 90h; struct std::nothrow_t *
0x180047845  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004784a  mov     qword ptr [rbx+98h], 0
0x180047855  mov     rcx, [rbx+0A0h]; void *
0x18004785c  test    rcx, rcx
0x18004785f  jz      short loc_180047876
0x180047861  mov     edx, 90h; struct std::nothrow_t *
0x180047866  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004786b  mov     qword ptr [rbx+0A0h], 0
0x180047876  mov     rcx, rdi; lpCriticalSection
0x180047879  call    cs:__imp_LeaveCriticalSection
0x18004787f  call    ?SvcRelease@@YAJXZ; SvcRelease(void)
0x180047884  mov     rcx, [rbx+0C0h]; hObject
0x18004788b  lea     rax, [rcx-1]
0x18004788f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180047893  ja      short loc_18004789B
0x180047895  call    cs:__imp_CloseHandle
0x18004789b  mov     qword ptr [rbx+0C0h], 0
0x1800478a6  lea     rax, ??_7CLock@WaasMedic@@6B@; const WaasMedic::CLock::`vftable'
0x1800478ad  mov     [rbx+48h], rax
0x1800478b1  mov     rcx, rdi
0x1800478b4  mov     rbx, [rsp+28h+arg_0]
0x1800478b9  add     rsp, 20h
0x1800478bd  pop     rdi
0x1800478be  jmp     cs:__imp_DeleteCriticalSection
```
