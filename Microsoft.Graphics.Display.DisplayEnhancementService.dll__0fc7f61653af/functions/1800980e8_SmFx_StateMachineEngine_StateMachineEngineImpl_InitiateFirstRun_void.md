# SmFx::StateMachineEngine::StateMachineEngineImpl::InitiateFirstRun(void)

- ea: `0x1800980e8`
- end: `0x18009819f`
- name: `?InitiateFirstRun@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAAXXZ`
- size: `183`
- prototype: `void __fastcall(SmFx::StateMachineEngine::StateMachineEngineImpl *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180097fd0`

## callees

- `0x1800978e0`
- `0x1800979c0`
- `0x1800980e8`
- `0x180098454`
- `0x1800987f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180098126`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180098126`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098104`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098173`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098104`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098173`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098117`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098117`

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
0x1800980e8  mov     [rsp+arg_0], rbx
0x1800980ed  mov     [rsp+arg_8], rsi
0x1800980f2  push    rdi
0x1800980f3  sub     rsp, 30h
0x1800980f7  lea     rsi, [rcx+3D0h]
0x1800980fe  mov     rbx, rcx
0x180098101  mov     rcx, rsi; lpCriticalSection
0x180098104  call    cs:__imp_EnterCriticalSection
0x18009810a  mov     rcx, rsi; lpCriticalSection
0x18009810d  mov     dword ptr [rbx+3CCh], 2
0x180098117  call    cs:__imp_LeaveCriticalSection
0x18009811d  xor     edi, edi
0x18009811f  mov     [rbx+3C6h], di
0x180098126  call    cs:__imp_GetCurrentThreadId
0x18009812c  mov     rcx, rbx
0x18009812f  mov     [rsp+38h+var_18], 6
0x180098138  mov     [rbx+3C8h], eax
0x18009813e  mov     rax, [rbx+378h]
0x180098145  movzx   edx, byte ptr [rax]
0x180098148  mov     rax, [rax+8]
0x18009814c  lea     rdx, [rax+rdx*2]
0x180098150  mov     [rsp+38h+var_10], rdx
0x180098155  lea     rdx, [rsp+38h+var_18]
0x18009815a  call    ?ExecuteEventAction@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAA?AW4EngineState@123@AEBUEVENT_ACTION@123@@Z; SmFx::StateMachineEngine::StateMachineEngineImpl::ExecuteEventAction(SmFx::StateMachineEngine::StateMachineEngineImpl::EVENT_ACTION const &)
0x18009815f  mov     edi, eax
0x180098161  cmp     eax, 2
0x180098164  jnz     short loc_180098170
0x180098166  mov     rcx, rbx
0x180098169  call    ?ExecuteCurrentState@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAA?AW4EngineState@123@XZ; SmFx::StateMachineEngine::StateMachineEngineImpl::ExecuteCurrentState(void)
0x18009816e  mov     edi, eax
0x180098170  mov     rcx, rsi; lpCriticalSection
0x180098173  call    cs:__imp_EnterCriticalSection
0x180098179  mov     rcx, rbx; this
0x18009817c  cmp     edi, 1
0x18009817f  jnz     short loc_180098188
0x180098181  call    ?ProcessEventQueue@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAAXXZ; SmFx::StateMachineEngine::StateMachineEngineImpl::ProcessEventQueue(void)
0x180098186  jmp     short loc_18009818F
0x180098188  mov     edx, edi
0x18009818a  call    ?UpdateEngineState@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAAXW4EngineState@123@@Z; SmFx::StateMachineEngine::StateMachineEngineImpl::UpdateEngineState(SmFx::StateMachineEngine::StateMachineEngineImpl::EngineState)
0x18009818f  mov     rbx, [rsp+38h+arg_0]
0x180098194  mov     rsi, [rsp+38h+arg_8]
0x180098199  add     rsp, 30h
0x18009819d  pop     rdi
0x18009819e  retn
```
