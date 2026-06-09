# Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)

- ea: `0x18001d12c`
- end: `0x18001d1be`
- name: `?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z`
- size: `146`
- prototype: `void __fastcall(Concurrency::details::_Task_impl_base *this, char)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18001c644`
- `0x18001d26c`

## callees

- `0x18001d12c`
- `0x18001d84c`
- `0x18001e88c`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18001d15b`
- `msvcp_win!_Mtx_unlock` at `0x18001d16a`
- `msvcp_win!_Mtx_unlock` at `0x18001d1a0`
- `msvcp_win!_Mtx_unlock` at `0x18001d15b`
- `msvcp_win!_Mtx_unlock` at `0x18001d16a`
- `msvcp_win!_Mtx_unlock` at `0x18001d1a0`
- `msvcp_win!_Cnd_broadcast` at `0x18001d196`
- `msvcp_win!_Cnd_broadcast` at `0x18001d196`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18001d12c  mov     [rsp+arg_0], rbx
0x18001d131  mov     [rsp+arg_8], rsi
0x18001d136  push    rdi
0x18001d137  sub     rsp, 20h
0x18001d13b  lea     rdi, [rcx+20h]
0x18001d13f  mov     [rcx+170h], dl
0x18001d145  mov     rbx, rcx
0x18001d148  mov     rcx, rdi; this
0x18001d14b  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18001d150  mov     eax, [rbx+8]
0x18001d153  mov     rcx, rdi; _Mtx_t
0x18001d156  cmp     eax, 4
0x18001d159  jnz     short loc_18001D163
0x18001d15b  call    cs:__imp__Mtx_unlock
0x18001d161  jmp     short loc_18001D1AE
0x18001d163  mov     dword ptr [rbx+8], 3
0x18001d16a  call    cs:__imp__Mtx_unlock
0x18001d170  lea     rdi, [rbx+88h]
0x18001d177  lea     rcx, [rdi+48h]; this
0x18001d17b  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18001d180  cmp     dword ptr [rdi+0B0h], 2
0x18001d187  jge     short loc_18001D193
0x18001d189  mov     dword ptr [rdi+0B0h], 2
0x18001d193  mov     rcx, rdi; _Cnd_t
0x18001d196  call    cs:__imp__Cnd_broadcast
0x18001d19c  lea     rcx, [rdi+48h]; _Mtx_t
0x18001d1a0  call    cs:__imp__Mtx_unlock
0x18001d1a6  mov     rcx, rbx; this
0x18001d1a9  call    ?_RunTaskContinuations@_Task_impl_base@details@Concurrency@@QEAAXXZ; Concurrency::details::_Task_impl_base::_RunTaskContinuations(void)
0x18001d1ae  mov     rbx, [rsp+28h+arg_0]
0x18001d1b3  mov     rsi, [rsp+28h+arg_8]
0x18001d1b8  add     rsp, 20h
0x18001d1bc  pop     rdi
0x18001d1bd  retn
```
