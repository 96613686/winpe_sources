# SmFx::StateMachineEngine::StateMachineEngineImpl::WorkerCallback(void)

- ea: `0x180098874`
- end: `0x180098947`
- name: `?WorkerCallback@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAAXXZ`
- size: `211`
- prototype: `void __fastcall(SmFx::StateMachineEngine::StateMachineEngineImpl *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180097550`

## callees

- `0x1800978e0`
- `0x1800979c0`
- `0x180098454`
- `0x1800987f4`
- `0x180098874`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800988b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800988b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098890`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800988ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009891b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098890`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800988ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009891b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800988a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800988a9`

## pseudocode

```c
void __fastcall SmFx::StateMachineEngine::StateMachineEngineImpl::WorkerCallback(
        SmFx::StateMachineEngine::StateMachineEngineImpl *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  int v3; // ebx
  int v4; // ebx
  SmFx::StateMachineEngine::StateMachineEngineImpl *v5; // rcx
  int v6; // ebx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 976);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 976));
  v3 = *((_DWORD *)this + 243);
  *((_DWORD *)this + 243) = 2;
  LeaveCriticalSection(v1);
  *((_WORD *)this + 483) = 1;
  *((_DWORD *)this + 242) = GetCurrentThreadId();
  v4 = v3 - 3;
  if ( v4 )
  {
    if ( v4 != 1 )
      return;
    SmFx::StateMachineEngine::StateMachineEngineImpl::ExecuteEventAction(this, (char *)this + 944);
    *((_OWORD *)this + 59) = 0;
    EnterCriticalSection(v1);
    v5 = this;
    goto LABEL_5;
  }
  SmFx::StateMachineEngine::StateMachineEngineImpl::ExecuteEventAction(this, (char *)this + 944);
  *((_OWORD *)this + 59) = 0;
  v6 = SmFx::StateMachineEngine::StateMachineEngineImpl::ExecuteCurrentState(this);
  EnterCriticalSection(v1);
  v5 = this;
  if ( v6 == 1 )
  {
LABEL_5:
    SmFx::StateMachineEngine::StateMachineEngineImpl::ProcessEventQueue(v5);
    return;
  }
  SmFx::StateMachineEngine::StateMachineEngineImpl::UpdateEngineState((__int64)this, v6);
}

```

## disassembly

```asm
0x180098874  mov     [rsp+arg_0], rbx
0x180098879  mov     [rsp+arg_8], rsi
0x18009887e  push    rdi
0x18009887f  sub     rsp, 20h
0x180098883  lea     rsi, [rcx+3D0h]
0x18009888a  mov     rdi, rcx
0x18009888d  mov     rcx, rsi; lpCriticalSection
0x180098890  call    cs:__imp_EnterCriticalSection
0x180098896  mov     ebx, [rdi+3CCh]
0x18009889c  mov     rcx, rsi; lpCriticalSection
0x18009889f  mov     dword ptr [rdi+3CCh], 2
0x1800988a9  call    cs:__imp_LeaveCriticalSection
0x1800988af  mov     word ptr [rdi+3C6h], 1
0x1800988b8  call    cs:__imp_GetCurrentThreadId
0x1800988be  mov     [rdi+3C8h], eax
0x1800988c4  sub     ebx, 3
0x1800988c7  jz      short loc_1800988F5
0x1800988c9  cmp     ebx, 1
0x1800988cc  jnz     short loc_180098937
0x1800988ce  lea     rbx, [rdi+3B0h]
0x1800988d5  mov     rcx, rdi
0x1800988d8  mov     rdx, rbx
0x1800988db  call    ?ExecuteEventAction@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAA?AW4EngineState@123@AEBUEVENT_ACTION@123@@Z; SmFx::StateMachineEngine::StateMachineEngineImpl::ExecuteEventAction(SmFx::StateMachineEngine::StateMachineEngineImpl::EVENT_ACTION const &)
0x1800988e0  xorps   xmm0, xmm0
0x1800988e3  mov     rcx, rsi; lpCriticalSection
0x1800988e6  movdqu  xmmword ptr [rbx], xmm0
0x1800988ea  call    cs:__imp_EnterCriticalSection
0x1800988f0  mov     rcx, rdi
0x1800988f3  jmp     short loc_180098929
0x1800988f5  lea     rbx, [rdi+3B0h]
0x1800988fc  mov     rcx, rdi
0x1800988ff  mov     rdx, rbx
0x180098902  call    ?ExecuteEventAction@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAA?AW4EngineState@123@AEBUEVENT_ACTION@123@@Z; SmFx::StateMachineEngine::StateMachineEngineImpl::ExecuteEventAction(SmFx::StateMachineEngine::StateMachineEngineImpl::EVENT_ACTION const &)
0x180098907  xorps   xmm0, xmm0
0x18009890a  mov     rcx, rdi
0x18009890d  movdqu  xmmword ptr [rbx], xmm0
0x180098911  call    ?ExecuteCurrentState@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAA?AW4EngineState@123@XZ; SmFx::StateMachineEngine::StateMachineEngineImpl::ExecuteCurrentState(void)
0x180098916  mov     rcx, rsi; lpCriticalSection
0x180098919  mov     ebx, eax
0x18009891b  call    cs:__imp_EnterCriticalSection
0x180098921  mov     rcx, rdi; this
0x180098924  cmp     ebx, 1
0x180098927  jnz     short loc_180098930
0x180098929  call    ?ProcessEventQueue@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAAXXZ; SmFx::StateMachineEngine::StateMachineEngineImpl::ProcessEventQueue(void)
0x18009892e  jmp     short loc_180098937
0x180098930  mov     edx, ebx
0x180098932  call    ?UpdateEngineState@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAAXW4EngineState@123@@Z; SmFx::StateMachineEngine::StateMachineEngineImpl::UpdateEngineState(SmFx::StateMachineEngine::StateMachineEngineImpl::EngineState)
0x180098937  mov     rbx, [rsp+28h+arg_0]
0x18009893c  mov     rsi, [rsp+28h+arg_8]
0x180098941  add     rsp, 20h
0x180098945  pop     rdi
0x180098946  retn
```
