# PnpManagerBase::Teardown(void)

- ea: `0x1800752e0`
- end: `0x18007534c`
- name: `?Teardown@PnpManagerBase@@UEAAXXZ`
- size: `108`
- prototype: `void __fastcall(PnpManagerBase *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180075290`

## callees

- `0x18000f9f0`
- `0x1800752e0`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180075306`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180075306`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18007532c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18007532c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180075345`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180075337`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180075337`

## string_xrefs

- `0x180075319`: `onecoreuap\drivers\mobilepc\sensors\convergence\common\pnpmanager\pnpmanager.cpp`

## pseudocode

```c
void __fastcall PnpManagerBase::Teardown(PnpManagerBase *this)
{
  struct _TP_WORK *ThreadpoolWork; // rax
  const char *v3; // r9
  struct _TP_WORK *v4; // rbx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  (*(void (__fastcall **)(PnpManagerBase *))(*(_QWORD *)this + 24LL))(this);
  ThreadpoolWork = CreateThreadpoolWork(
                     Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::GeneratedStateMachines::DeManagementServerSettingStateMachine<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingImpl<4>>::EvtLogTransitionThunk,
                     0,
                     (PTP_CALLBACK_ENVIRON)(*((_QWORD *)this + 8) + 16LL));
  v4 = ThreadpoolWork;
  if ( !ThreadpoolWork )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\sensors\\convergence\\common\\pnpmanager\\pnpmanager.cpp",
      v3);
  SubmitThreadpoolWork(ThreadpoolWork);
  WaitForThreadpoolWorkCallbacks(v4, 0);
  CloseThreadpoolWork(v4);
}

```

## disassembly

```asm
0x1800752e0  push    rbx
0x1800752e2  sub     rsp, 20h
0x1800752e6  mov     rax, [rcx]
0x1800752e9  mov     rbx, rcx
0x1800752ec  mov     rax, [rax+18h]
0x1800752f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800752f5  mov     r8, [rbx+40h]
0x1800752f9  lea     rcx, ?EvtLogTransitionThunk@?$DeManagementServerSettingStateMachine@V?$DeManagementServerSettingImpl@$03@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@@GeneratedStateMachines@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@CAXPEAXW4TransitionType@SmFx@@GGG@Z; pfnwk
0x180075300  add     r8, 10h; pcbe
0x180075304  xor     edx, edx; pv
0x180075306  call    cs:__imp_CreateThreadpoolWork
0x18007530c  mov     rbx, rax
0x18007530f  test    rax, rax
0x180075312  jnz     short loc_180075329
0x180075314  mov     rcx, [rsp+28h]; this
0x180075319  lea     r8, aOnecoreuapDriv_32; "onecoreuap\\drivers\\mobilepc\\sensors"...
0x180075320  lea     edx, [rax+2Fh]; void *
0x180075323  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180075329  mov     rcx, rbx; pwk
0x18007532c  call    cs:__imp_SubmitThreadpoolWork
0x180075332  xor     edx, edx; fCancelPendingCallbacks
0x180075334  mov     rcx, rbx; pwk
0x180075337  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18007533d  mov     rcx, rbx
0x180075340  add     rsp, 20h
0x180075344  pop     rbx
0x180075345  jmp     cs:__imp_CloseThreadpoolWork
```
