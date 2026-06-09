# SmFx::StateMachineEngine::StateMachineEngineImpl::InitiateFirstRun(void)

- ea: `0x180031d9c`
- end: `0x180031e53`
- name: `?InitiateFirstRun@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAAXXZ`
- size: `183`
- prototype: `void __fastcall(SmFx::StateMachineEngine::StateMachineEngineImpl *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180031c74`

## callees

- `0x1800313bc`
- `0x1800315f0`
- `0x180031d9c`
- `0x180032048`
- `0x1800322e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031db8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031e27`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031db8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031e27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031dcb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031dcb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180031dda`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180031dda`

## pseudocode

```c
void __fastcall SmFx::StateMachineEngine::StateMachineEngineImpl::InitiateFirstRun(
        SmFx::StateMachineEngine::StateMachineEngineImpl *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  int v3; // edi
  _QWORD v4[3]; // [rsp+20h] [rbp-18h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 976);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 976));
  *((_DWORD *)this + 243) = 2;
  LeaveCriticalSection(v1);
  *((_WORD *)this + 483) = 0;
  v4[0] = 6;
  *((_DWORD *)this + 242) = GetCurrentThreadId();
  v4[1] = *(_QWORD *)(*((_QWORD *)this + 111) + 8LL) + 2LL * **((unsigned __int8 **)this + 111);
  v3 = SmFx::StateMachineEngine::StateMachineEngineImpl::ExecuteEventAction(this, v4);
  if ( v3 == 2 )
    v3 = SmFx::StateMachineEngine::StateMachineEngineImpl::ExecuteCurrentState(this);
  EnterCriticalSection(v1);
  if ( v3 == 1 )
    SmFx::StateMachineEngine::StateMachineEngineImpl::ProcessEventQueue(this);
  else
    SmFx::StateMachineEngine::StateMachineEngineImpl::UpdateEngineState((__int64)this, v3);
}

```

## disassembly

```asm
0x180031d9c  mov     [rsp+arg_0], rbx
0x180031da1  mov     [rsp+arg_8], rsi
0x180031da6  push    rdi
0x180031da7  sub     rsp, 30h
0x180031dab  lea     rsi, [rcx+3D0h]
0x180031db2  mov     rbx, rcx
0x180031db5  mov     rcx, rsi; lpCriticalSection
0x180031db8  call    cs:__imp_EnterCriticalSection
0x180031dbe  mov     rcx, rsi; lpCriticalSection
0x180031dc1  mov     dword ptr [rbx+3CCh], 2
0x180031dcb  call    cs:__imp_LeaveCriticalSection
0x180031dd1  xor     edi, edi
0x180031dd3  mov     [rbx+3C6h], di
0x180031dda  call    cs:__imp_GetCurrentThreadId
0x180031de0  mov     rcx, rbx
0x180031de3  mov     [rsp+38h+var_18], 6
0x180031dec  mov     [rbx+3C8h], eax
0x180031df2  mov     rax, [rbx+378h]
0x180031df9  movzx   edx, byte ptr [rax]
0x180031dfc  mov     rax, [rax+8]
0x180031e00  lea     rdx, [rax+rdx*2]
0x180031e04  mov     [rsp+38h+var_10], rdx
0x180031e09  lea     rdx, [rsp+38h+var_18]
0x180031e0e  call    ?ExecuteEventAction@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAA?AW4EngineState@123@AEBUEVENT_ACTION@123@@Z; SmFx::StateMachineEngine::StateMachineEngineImpl::ExecuteEventAction(SmFx::StateMachineEngine::StateMachineEngineImpl::EVENT_ACTION const &)
0x180031e13  mov     edi, eax
0x180031e15  cmp     eax, 2
0x180031e18  jnz     short loc_180031E24
0x180031e1a  mov     rcx, rbx
0x180031e1d  call    ?ExecuteCurrentState@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAA?AW4EngineState@123@XZ; SmFx::StateMachineEngine::StateMachineEngineImpl::ExecuteCurrentState(void)
0x180031e22  mov     edi, eax
0x180031e24  mov     rcx, rsi; lpCriticalSection
0x180031e27  call    cs:__imp_EnterCriticalSection
0x180031e2d  mov     rcx, rbx; this
0x180031e30  cmp     edi, 1
0x180031e33  jnz     short loc_180031E3C
0x180031e35  call    ?ProcessEventQueue@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAAXXZ; SmFx::StateMachineEngine::StateMachineEngineImpl::ProcessEventQueue(void)
0x180031e3a  jmp     short loc_180031E43
0x180031e3c  mov     edx, edi
0x180031e3e  call    ?UpdateEngineState@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAAXW4EngineState@123@@Z; SmFx::StateMachineEngine::StateMachineEngineImpl::UpdateEngineState(SmFx::StateMachineEngine::StateMachineEngineImpl::EngineState)
0x180031e43  mov     rbx, [rsp+38h+arg_0]
0x180031e48  mov     rsi, [rsp+38h+arg_8]
0x180031e4d  add     rsp, 30h
0x180031e51  pop     rdi
0x180031e52  retn
```
