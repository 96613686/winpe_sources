# WaaSRemediationAgent::LaunchRemediationThread(void *)

- ea: `0x18005f8e0`
- end: `0x18005f9f9`
- name: `?LaunchRemediationThread@WaaSRemediationAgent@@SAKPEAX@Z`
- size: `281`
- prototype: `unsigned int __fastcall(void *lpParameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18002e81c`
- `0x18005200c`
- `0x18005f8e0`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005f960`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005f960`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005f99b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005f99b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005f942`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005f9b1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005f942`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005f9b1`

## string_xrefs

- `0x18005f983`: `Failed to execute Waas medic launch remediation on a thread. hr = 0x%08x`
- `0x18005f92b`: `Failed to QI on WaaSRemediation agent interface. hr = 0x%08x`
- `0x18005f948`: `WaaSRemediationAgent now launching Waas Medic remediation on a thread.`
- `0x18005f9ba`: `WaaSRemediationAgent completed Waas Medic remediation on a thread. hr = 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WaaSRemediationAgent::LaunchRemediationThread(HANDLE *lpParameter)
{
  __int64 (__fastcall ***v2)(HANDLE, GUID *, __int64 *); // rcx
  int v3; // eax
  unsigned int v4; // ebx
  unsigned int *v5; // r8
  __int64 v6; // r9
  int v7; // eax
  __int64 v8; // rcx
  __int64 v10; // [rsp+40h] [rbp+8h] BYREF

  v10 = 0;
  if ( !lpParameter || (v2 = (__int64 (__fastcall ***)(HANDLE, GUID *, __int64 *))*lpParameter) == 0 )
  {
    v4 = -2147467261;
    if ( !lpParameter )
      goto LABEL_10;
    goto LABEL_9;
  }
  v3 = (**v2)(v2, &IID_IUnknown, &v10);
  v4 = v3;
  if ( v3 < 0 )
  {
    LogLevelW(2u, L"Failed to QI on WaaSRemediation agent interface. hr = 0x%08x", (unsigned int)v3);
LABEL_9:
    SetEvent(lpParameter[2]);
    goto LABEL_10;
  }
  SetEvent(lpParameter[2]);
  LogLevelW(4u, L"WaaSRemediationAgent now launching Waas Medic remediation on a thread.");
  EnterCriticalSection(&stru_1800A43C8);
  v7 = WaaSRemediationAgent::ExecuteProcOnThread(
         (LPTHREAD_START_ROUTINE)WaasMedic::CWaasMedic::LaunchRemediation,
         lpParameter,
         v5,
         v6,
         1);
  v4 = v7;
  if ( v7 < 0 )
    LogLevelW(2u, L"Failed to execute Waas medic launch remediation on a thread. hr = 0x%08x", (unsigned int)v7);
  LeaveCriticalSection(&stru_1800A43C8);
LABEL_10:
  LogLevelW(4u, L"WaaSRemediationAgent completed Waas Medic remediation on a thread. hr = 0x%08x", v4);
  v8 = v10;
  if ( v10 )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  return v4;
}

```

## disassembly

```asm
0x18005f8e0  mov     [rsp+arg_8], rbx
0x18005f8e5  push    rdi
0x18005f8e6  sub     rsp, 30h
0x18005f8ea  mov     rdi, rcx
0x18005f8ed  mov     [rsp+38h+arg_0], 0
0x18005f8f6  test    rcx, rcx
0x18005f8f9  jz      loc_18005F9A3
0x18005f8ff  mov     rcx, [rcx]
0x18005f902  test    rcx, rcx
0x18005f905  jz      loc_18005F9A3
0x18005f90b  mov     rax, [rcx]
0x18005f90e  lea     r8, [rsp+38h+arg_0]
0x18005f913  lea     rdx, IID_IUnknown
0x18005f91a  mov     rax, [rax]
0x18005f91d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f922  mov     ebx, eax
0x18005f924  test    eax, eax
0x18005f926  jns     short loc_18005F93E
0x18005f928  mov     r8d, eax
0x18005f92b  lea     rdx, aFailedToQiOnWa_0; "Failed to QI on WaaSRemediation agent i"...
0x18005f932  mov     ecx, 2; unsigned __int8
0x18005f937  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005f93c  jmp     short loc_18005F9AD
0x18005f93e  mov     rcx, [rdi+10h]; hEvent
0x18005f942  call    cs:__imp_SetEvent
0x18005f948  lea     rdx, aWaasremediatio_4; "WaaSRemediationAgent now launching Waas"...
0x18005f94f  mov     ecx, 4; unsigned __int8
0x18005f954  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005f959  lea     rcx, stru_1800A43C8; lpCriticalSection
0x18005f960  call    cs:__imp_EnterCriticalSection
0x18005f966  mov     [rsp+38h+var_18], 1; bool
0x18005f96b  mov     rdx, rdi; lpParameter
0x18005f96e  lea     rcx, ?LaunchRemediation@CWaasMedic@WaasMedic@@SAKPEAX@Z; lpStartAddress
0x18005f975  call    ?ExecuteProcOnThread@WaaSRemediationAgent@@CAKP6AKPEAX@Z0PEAKK_N@Z; WaaSRemediationAgent::ExecuteProcOnThread(ulong (*)(void *),void *,ulong *,ulong,bool)
0x18005f97a  mov     ebx, eax
0x18005f97c  test    eax, eax
0x18005f97e  jns     short loc_18005F994
0x18005f980  mov     r8d, eax
0x18005f983  lea     rdx, aFailedToExecut; "Failed to execute Waas medic launch rem"...
0x18005f98a  mov     ecx, 2; unsigned __int8
0x18005f98f  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005f994  lea     rcx, stru_1800A43C8; lpCriticalSection
0x18005f99b  call    cs:__imp_LeaveCriticalSection
0x18005f9a1  jmp     short loc_18005F9B7
0x18005f9a3  mov     ebx, 80004003h
0x18005f9a8  test    rdi, rdi
0x18005f9ab  jz      short loc_18005F9B7
0x18005f9ad  mov     rcx, [rdi+10h]; hEvent
0x18005f9b1  call    cs:__imp_SetEvent
0x18005f9b7  mov     r8d, ebx
0x18005f9ba  lea     rdx, aWaasremediatio_5; "WaaSRemediationAgent completed Waas Med"...
0x18005f9c1  mov     ecx, 4; unsigned __int8
0x18005f9c6  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005f9cb  nop
0x18005f9cc  mov     rcx, [rsp+38h+arg_0]
0x18005f9d1  test    rcx, rcx
0x18005f9d4  jz      short loc_18005F9EC
0x18005f9d6  mov     [rsp+38h+arg_0], 0
0x18005f9df  mov     rax, [rcx]
0x18005f9e2  mov     rax, [rax+10h]
0x18005f9e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f9eb  nop
0x18005f9ec  mov     eax, ebx
0x18005f9ee  mov     rbx, [rsp+38h+arg_8]
0x18005f9f3  add     rsp, 30h
0x18005f9f7  pop     rdi
0x18005f9f8  retn
```
