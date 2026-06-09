# SmFx::StateMachineEngine::StateMachineEngineImpl::UpdateEngineState(SmFx::StateMachineEngine::StateMachineEngineImpl::EngineState)

- ea: `0x1800987f4`
- end: `0x18009886d`
- name: `?UpdateEngineState@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAAXW4EngineState@123@@Z`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800980e8`
- `0x180098454`
- `0x180098874`

## callees

- `0x180097704`
- `0x180097f74`
- `0x1800987f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009881e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098831`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009884f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009881e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098831`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009884f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18009885c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18009885c`

## pseudocode

```c
void __fastcall SmFx::StateMachineEngine::StateMachineEngineImpl::UpdateEngineState(__int64 a1, int a2)
{
  unsigned __int16 CurrentStateIndex; // bx
  LPCRITICAL_SECTION v4; // r8

  *(_DWORD *)(a1 + 972) = a2;
  if ( (unsigned int)(a2 - 3) <= 1 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 976));
    SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 1024));
  }
  else if ( a2 == 5 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 976));
  }
  else
  {
    CurrentStateIndex = SmFx::StateMachineEngine::StateMachineEngineImpl::GetCurrentStateIndex((SmFx::StateMachineEngine::StateMachineEngineImpl *)a1);
    LeaveCriticalSection(v4);
    if ( !CurrentStateIndex )
      SmFx::StateMachineEngine::StateMachineEngineImpl::Destroy(
        (SmFx::StateMachineEngine::StateMachineEngineImpl *)a1,
        1);
  }
}

```

## disassembly

```asm
0x1800987f4  mov     [rsp+arg_0], rbx
0x1800987f9  push    rdi
0x1800987fa  sub     rsp, 20h
0x1800987fe  lea     eax, [rdx-3]
0x180098801  mov     [rcx+3CCh], edx
0x180098807  mov     rdi, rcx
0x18009880a  cmp     eax, 1
0x18009880d  jbe     short loc_180098848
0x18009880f  lea     r8, [rcx+3D0h]
0x180098816  cmp     edx, 5
0x180098819  jnz     short loc_180098826
0x18009881b  mov     rcx, r8; lpCriticalSection
0x18009881e  call    cs:__imp_LeaveCriticalSection
0x180098824  jmp     short loc_180098862
0x180098826  call    ?GetCurrentStateIndex@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEBAGXZ; SmFx::StateMachineEngine::StateMachineEngineImpl::GetCurrentStateIndex(void)
0x18009882b  mov     rcx, r8; lpCriticalSection
0x18009882e  movzx   ebx, ax
0x180098831  call    cs:__imp_LeaveCriticalSection
0x180098837  test    bx, bx
0x18009883a  jnz     short loc_180098862
0x18009883c  mov     dl, 1; bool
0x18009883e  mov     rcx, rdi; this
0x180098841  call    ?Destroy@StateMachineEngineImpl@StateMachineEngine@SmFx@@QEAAX_N@Z; SmFx::StateMachineEngine::StateMachineEngineImpl::Destroy(bool)
0x180098846  jmp     short loc_180098862
0x180098848  add     rcx, 3D0h; lpCriticalSection
0x18009884f  call    cs:__imp_LeaveCriticalSection
0x180098855  mov     rcx, [rdi+400h]; pwk
0x18009885c  call    cs:__imp_SubmitThreadpoolWork
0x180098862  mov     rbx, [rsp+28h+arg_0]
0x180098867  add     rsp, 20h
0x18009886b  pop     rdi
0x18009886c  retn
```
