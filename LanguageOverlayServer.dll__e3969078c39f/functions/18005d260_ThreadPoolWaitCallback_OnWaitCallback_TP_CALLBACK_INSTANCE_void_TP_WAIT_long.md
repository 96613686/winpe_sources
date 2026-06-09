# ThreadPoolWaitCallback::_OnWaitCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x18005d260`
- end: `0x18005d2e1`
- name: `?_OnWaitCallback@ThreadPoolWaitCallback@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `129`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18005d234`
- `0x18005d260`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005d2c5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005d2c5`
- `msvcp_win!_Mtx_unlock` at `0x18005d2cf`
- `msvcp_win!_Mtx_unlock` at `0x18005d2cf`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005d289`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005d2ab`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005d289`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005d2ab`
- `msvcp_win!_Mtx_lock` at `0x18005d27a`
- `msvcp_win!_Mtx_lock` at `0x18005d27a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ThreadPoolWaitCallback::_OnWaitCallback(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  void *v5; // rdx

  ThreadPoolWaitCallback::_ExecuteCallback((ThreadPoolWaitCallback *)Context);
  if ( _Mtx_lock((_Mtx_t)(Context + 80)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *((_DWORD *)Context + 39) == 0x7FFFFFFF )
  {
    *((_DWORD *)Context + 39) = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  v5 = (void *)*((_QWORD *)Context + 20);
  if ( v5 )
    SetThreadpoolWait(*((PTP_WAIT *)Context + 1), v5, 0);
  _Mtx_unlock((_Mtx_t)(Context + 80));
}

```

## disassembly

```asm
0x18005d260  mov     [rsp+arg_0], rbx
0x18005d265  push    rdi
0x18005d266  sub     rsp, 20h
0x18005d26a  mov     rdi, rdx
0x18005d26d  mov     rcx, rdx; this
0x18005d270  call    ?_ExecuteCallback@ThreadPoolWaitCallback@@AEAAXXZ; ThreadPoolWaitCallback::_ExecuteCallback(void)
0x18005d275  nop
0x18005d276  lea     rcx, [rdi+50h]; _Mtx_t
0x18005d27a  call    cs:__imp__Mtx_lock
0x18005d280  test    eax, eax
0x18005d282  jz      short loc_18005D290
0x18005d284  mov     ecx, 5
0x18005d289  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18005d28f  int     3; Trap to Debugger
0x18005d290  cmp     dword ptr [rdi+9Ch], 7FFFFFFFh
0x18005d29a  jnz     short loc_18005D2B2
0x18005d29c  mov     dword ptr [rdi+9Ch], 7FFFFFFEh
0x18005d2a6  mov     ecx, 6
0x18005d2ab  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18005d2b1  int     3; Trap to Debugger
0x18005d2b2  mov     rdx, [rdi+0A0h]; h
0x18005d2b9  test    rdx, rdx
0x18005d2bc  jz      short loc_18005D2CB
0x18005d2be  xor     r8d, r8d; pftTimeout
0x18005d2c1  mov     rcx, [rdi+8]; pwa
0x18005d2c5  call    cs:__imp_SetThreadpoolWait
0x18005d2cb  lea     rcx, [rdi+50h]; _Mtx_t
0x18005d2cf  call    cs:__imp__Mtx_unlock
0x18005d2d5  nop
0x18005d2d6  mov     rbx, [rsp+28h+arg_0]
0x18005d2db  add     rsp, 20h
0x18005d2df  pop     rdi
0x18005d2e0  retn
```
