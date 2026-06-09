# azure::storage::core::timer_handler::stop_timer(void)

- ea: `0x1800774f0`
- end: `0x18007761d`
- name: `?stop_timer@timer_handler@core@storage@azure@@QEAAXXZ`
- size: `301`
- prototype: `void __fastcall(azure::storage::core::timer_handler *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800767b0`
- `0x180076d20`

## callees

- `0x180055990`
- `0x1800774f0`
- `0x1800a9d65`
- `0x1800a9d71`
- `0x1800a9d7d`
- `0x180191010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077560`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077560`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180077551`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180077575`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180077551`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180077575`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall azure::storage::core::timer_handler::stop_timer(azure::storage::core::timer_handler *this)
{
  char *v2; // rbx
  HANDLE *v3; // rdi
  char *v4; // rcx
  volatile signed __int32 *v5; // rdi

  v2 = (char *)this + 80;
  if ( Mtx_lock_0((azure::storage::core::timer_handler *)((char *)this + 80)) )
  {
    std::_Throw_Cpp_error(5);
    JUMPOUT(0x18007761CLL);
  }
  if ( *((_DWORD *)v2 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)v2 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  if ( *((_BYTE *)this + 176) )
  {
    v3 = (HANDLE *)*((_QWORD *)this + 20);
    if ( v3 )
    {
      if ( !DeleteTimerQueueTimer(0, *v3, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
      {
        while ( GetLastError() != 997 && !DeleteTimerQueueTimer(0, *v3, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
          ;
      }
      v4 = (char *)this + 64;
      if ( !*(_BYTE *)(*((_QWORD *)this + 8) + 112LL) && !*(_BYTE *)(*(_QWORD *)v4 + 113LL) )
        pplx::task_completion_event<unsigned __int64>::_CancelInternal(v4);
      *((_QWORD *)this + 20) = 0;
      v5 = (volatile signed __int32 *)*((_QWORD *)this + 21);
      *((_QWORD *)this + 21) = 0;
      if ( v5 )
      {
        if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
          if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
        }
      }
    }
  }
  Mtx_unlock_0((_Mtx_t)v2);
}

```

## disassembly

```asm
0x1800774f0  push    rbx
0x1800774f2  push    rbp
0x1800774f3  push    rsi
0x1800774f4  push    rdi
0x1800774f5  sub     rsp, 28h
0x1800774f9  mov     rsi, rcx
0x1800774fc  lea     rbx, [rcx+50h]
0x180077500  mov     [rsp+48h+arg_0], rbx
0x180077505  mov     rcx, rbx; _Mtx_t
0x180077508  call    _Mtx_lock_0
0x18007750d  test    eax, eax
0x18007750f  jnz     loc_180077612
0x180077515  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18007751c  jz      loc_180077600
0x180077522  movzx   eax, byte ptr [rsi+0B0h]
0x180077529  nop
0x18007752a  test    al, al
0x18007752c  jz      loc_1800775F0
0x180077532  mov     rdi, [rsi+0A0h]
0x180077539  test    rdi, rdi
0x18007753c  jz      loc_1800775F0
0x180077542  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x180077549  mov     r8, rbp; CompletionEvent
0x18007754c  mov     rdx, [rdi]; Timer
0x18007754f  xor     ecx, ecx; TimerQueue
0x180077551  call    cs:__imp_DeleteTimerQueueTimer
0x180077557  test    eax, eax
0x180077559  jnz     short loc_18007757F
0x18007755b  nop     dword ptr [rax+rax+00h]
0x180077560  call    cs:__imp_GetLastError
0x180077566  cmp     eax, 3E5h
0x18007756b  jz      short loc_18007757F
0x18007756d  mov     r8, rbp; CompletionEvent
0x180077570  mov     rdx, [rdi]; Timer
0x180077573  xor     ecx, ecx; TimerQueue
0x180077575  call    cs:__imp_DeleteTimerQueueTimer
0x18007757b  test    eax, eax
0x18007757d  jz      short loc_180077560
0x18007757f  lea     rcx, [rsi+40h]
0x180077583  mov     rax, [rcx]
0x180077586  movzx   edx, byte ptr [rax+70h]
0x18007758a  nop
0x18007758b  test    dl, dl
0x18007758d  jnz     short loc_1800775A0
0x18007758f  mov     rax, [rcx]
0x180077592  movzx   edx, byte ptr [rax+71h]
0x180077596  nop
0x180077597  test    dl, dl
0x180077599  jnz     short loc_1800775A0
0x18007759b  call    ?_CancelInternal@?$task_completion_event@_K@pplx@@AEBA_NXZ; pplx::task_completion_event<unsigned __int64>::_CancelInternal(void)
0x1800775a0  xor     eax, eax
0x1800775a2  mov     [rsi+0A0h], rax
0x1800775a9  mov     rdi, [rsi+0A8h]
0x1800775b0  mov     [rsi+0A8h], rax
0x1800775b7  test    rdi, rdi
0x1800775ba  jz      short loc_1800775F0
0x1800775bc  mov     eax, ebp
0x1800775be  lock xadd [rdi+8], eax
0x1800775c3  cmp     eax, 1
0x1800775c6  jnz     short loc_1800775F0
0x1800775c8  mov     rax, [rdi]
0x1800775cb  mov     rcx, rdi
0x1800775ce  mov     rax, [rax]
0x1800775d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800775d6  lock xadd [rdi+0Ch], ebp
0x1800775db  cmp     ebp, 1
0x1800775de  jnz     short loc_1800775F0
0x1800775e0  mov     rax, [rdi]
0x1800775e3  mov     rcx, rdi
0x1800775e6  mov     rax, [rax+8]
0x1800775ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800775ef  nop
0x1800775f0  mov     rcx, rbx; _Mtx_t
0x1800775f3  add     rsp, 28h
0x1800775f7  pop     rdi
0x1800775f8  pop     rsi
0x1800775f9  pop     rbp
0x1800775fa  pop     rbx
0x1800775fb  jmp     _Mtx_unlock_0
0x180077600  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x180077607  mov     ecx, 6; int
0x18007760c  call    ?_Throw_Cpp_error@std@@YAXH@Z_0; std::_Throw_Cpp_error(int)
0x180077611  int     3; Trap to Debugger
0x180077612  mov     ecx, 5; int
0x180077617  call    ?_Throw_Cpp_error@std@@YAXH@Z_0; std::_Throw_Cpp_error(int)
```
