# wil::details::event_watcher_state::~event_watcher_state(void)

- ea: `0x180005144`
- end: `0x1800051c5`
- name: `??1event_watcher_state@details@wil@@QEAA@XZ`
- size: `129`
- prototype: `void __fastcall(wil::details::event_watcher_state *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1800042fc`
- `0x1800047f0`
- `0x180004e34`
- `0x180004fa4`
- `0x180007594`

## callees

- `0x180005144`
- `0x1800071e4`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180005165`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180005165`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180005173`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180005173`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000517c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000517c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000518b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000518b`

## pseudocode

```c
void __fastcall wil::details::event_watcher_state::~event_watcher_state(wil::details::event_watcher_state *this)
{
  struct _TP_WAIT *v1; // rdi
  void *v3; // rcx
  unsigned int v4; // r8d
  const char *v5; // r9
  __int64 v6; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = (struct _TP_WAIT *)*((_QWORD *)this + 16);
  if ( v1 )
  {
    SetThreadpoolWait(*((PTP_WAIT *)this + 16), 0, 0);
    WaitForThreadpoolWaitCallbacks(v1, 1);
    CloseThreadpoolWait(v1);
  }
  v3 = (void *)*((_QWORD *)this + 15);
  if ( v3 && !CloseHandle(v3) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v4, v5);
  v6 = *((_QWORD *)this + 14);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 24LL))(v6);
}

```

## disassembly

```asm
0x180005144  mov     [rsp+arg_0], rbx
0x180005149  push    rdi
0x18000514a  sub     rsp, 20h
0x18000514e  mov     rdi, [rcx+80h]
0x180005155  mov     rbx, rcx
0x180005158  test    rdi, rdi
0x18000515b  jz      short loc_180005182
0x18000515d  xor     r8d, r8d; pftTimeout
0x180005160  xor     edx, edx; h
0x180005162  mov     rcx, rdi; pwa
0x180005165  call    cs:__imp_SetThreadpoolWait
0x18000516b  mov     edx, 1; fCancelPendingCallbacks
0x180005170  mov     rcx, rdi; pwa
0x180005173  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180005179  mov     rcx, rdi; pwa
0x18000517c  call    cs:__imp_CloseThreadpoolWait
0x180005182  mov     rcx, [rbx+78h]; hObject
0x180005186  test    rcx, rcx
0x180005189  jz      short loc_180005195
0x18000518b  call    cs:__imp_CloseHandle
0x180005191  test    eax, eax
0x180005193  jz      short loc_1800051B5
0x180005195  mov     rcx, [rbx+70h]
0x180005199  test    rcx, rcx
0x18000519c  jz      short loc_1800051AA
0x18000519e  mov     rax, [rcx]
0x1800051a1  mov     rax, [rax+18h]
0x1800051a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051aa  mov     rbx, [rsp+28h+arg_0]
0x1800051af  add     rsp, 20h
0x1800051b3  pop     rdi
0x1800051b4  retn
0x1800051b5  mov     rcx, [rsp+28h]; this
0x1800051ba  mov     edx, 0A0Bh; void *
0x1800051bf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
