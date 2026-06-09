# Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)

- ea: `0x18002335c`
- end: `0x1800233ee`
- name: `?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z`
- size: `146`
- prototype: `void __fastcall(Concurrency::details::_Task_impl_base *this, char)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800235fc`
- `0x1800236c4`
- `0x18002378c`

## callees

- `0x18002335c`
- `0x180023f64`
- `0x180024834`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18002338b`
- `msvcp_win!_Mtx_unlock` at `0x18002339a`
- `msvcp_win!_Mtx_unlock` at `0x1800233d0`
- `msvcp_win!_Mtx_unlock` at `0x18002338b`
- `msvcp_win!_Mtx_unlock` at `0x18002339a`
- `msvcp_win!_Mtx_unlock` at `0x1800233d0`
- `msvcp_win!_Cnd_broadcast` at `0x1800233c6`
- `msvcp_win!_Cnd_broadcast` at `0x1800233c6`

## pseudocode

```c
void __fastcall Concurrency::details::_Task_impl<unsigned char>::_FinalizeAndRunContinuations(
        Concurrency::details::_Task_impl_base *this,
        char a2)
{
  struct _Mtx_internal_imp_t *v2; // rdi

  v2 = (Concurrency::details::_Task_impl_base *)((char *)this + 32);
  *((_BYTE *)this + 368) = a2;
  std::_Mutex_base::lock((Concurrency::details::_Task_impl_base *)((char *)this + 32));
  if ( *((_DWORD *)this + 2) == 4 )
  {
    _Mtx_unlock(v2);
  }
  else
  {
    *((_DWORD *)this + 2) = 3;
    _Mtx_unlock(v2);
    std::_Mutex_base::lock((Concurrency::details::_Task_impl_base *)((char *)this + 208));
    if ( *((int *)this + 78) < 2 )
      *((_DWORD *)this + 78) = 2;
    _Cnd_broadcast((Concurrency::details::_Task_impl_base *)((char *)this + 136));
    _Mtx_unlock((Concurrency::details::_Task_impl_base *)((char *)this + 208));
    Concurrency::details::_Task_impl_base::_RunTaskContinuations(this);
  }
}

```

## disassembly

```asm
0x18002335c  mov     [rsp+arg_0], rbx
0x180023361  mov     [rsp+arg_8], rsi
0x180023366  push    rdi
0x180023367  sub     rsp, 20h
0x18002336b  lea     rdi, [rcx+20h]
0x18002336f  mov     [rcx+170h], dl
0x180023375  mov     rbx, rcx
0x180023378  mov     rcx, rdi; this
0x18002337b  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180023380  mov     eax, [rbx+8]
0x180023383  mov     rcx, rdi; _Mtx_t
0x180023386  cmp     eax, 4
0x180023389  jnz     short loc_180023393
0x18002338b  call    cs:__imp__Mtx_unlock
0x180023391  jmp     short loc_1800233DE
0x180023393  mov     dword ptr [rbx+8], 3
0x18002339a  call    cs:__imp__Mtx_unlock
0x1800233a0  lea     rdi, [rbx+88h]
0x1800233a7  lea     rcx, [rdi+48h]; this
0x1800233ab  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800233b0  cmp     dword ptr [rdi+0B0h], 2
0x1800233b7  jge     short loc_1800233C3
0x1800233b9  mov     dword ptr [rdi+0B0h], 2
0x1800233c3  mov     rcx, rdi; _Cnd_t
0x1800233c6  call    cs:__imp__Cnd_broadcast
0x1800233cc  lea     rcx, [rdi+48h]; _Mtx_t
0x1800233d0  call    cs:__imp__Mtx_unlock
0x1800233d6  mov     rcx, rbx; this
0x1800233d9  call    ?_RunTaskContinuations@_Task_impl_base@details@Concurrency@@QEAAXXZ; Concurrency::details::_Task_impl_base::_RunTaskContinuations(void)
0x1800233de  mov     rbx, [rsp+28h+arg_0]
0x1800233e3  mov     rsi, [rsp+28h+arg_8]
0x1800233e8  add     rsp, 20h
0x1800233ec  pop     rdi
0x1800233ed  retn
```
