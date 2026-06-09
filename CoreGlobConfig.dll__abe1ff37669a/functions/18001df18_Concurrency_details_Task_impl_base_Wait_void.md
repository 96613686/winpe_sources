# Concurrency::details::_Task_impl_base::_Wait(void)

- ea: `0x18001df18`
- end: `0x18001e00e`
- name: `?_Wait@_Task_impl_base@details@Concurrency@@QEAA?AW4task_group_status@3@XZ`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001279c`

## callees

- `0x18000f98c`
- `0x1800112e0`
- `0x18001d7d0`
- `0x18001df18`

## import_xrefs

- `msvcp_win!_Cnd_wait` at `0x18001df4d`
- `msvcp_win!_Cnd_wait` at `0x18001df8a`
- `msvcp_win!_Cnd_wait` at `0x18001dfd2`
- `msvcp_win!_Cnd_wait` at `0x18001df4d`
- `msvcp_win!_Cnd_wait` at `0x18001df8a`
- `msvcp_win!_Cnd_wait` at `0x18001dfd2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Concurrency::details::_Task_impl_base::_Wait(__int64 a1)
{
  __int64 v1; // rdi
  int v2; // ebx
  __int64 v3; // rsi
  __int64 v4; // rsi
  Concurrency::details::_ExceptionHolder *v5; // rcx
  const struct std::exception_ptr *v7; // rax
  _Mtx_t v8[5]; // [rsp+20h] [rbp-28h] BYREF
  _Cnd_t v10; // [rsp+58h] [rbp+10h]
  __int64 v11; // [rsp+60h] [rbp+18h]

  v1 = a1;
  v2 = 0;
  if ( *(_BYTE *)(a1 + 12) )
  {
    v3 = a1 + 136;
    std::unique_lock<std::mutex>::unique_lock<std::mutex>(v8, a1 + 208);
    while ( *(int *)(v3 + 176) < 2 )
      _Cnd_wait((_Cnd_t)v3, v8[0]);
LABEL_13:
    std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v8);
    goto LABEL_14;
  }
  try
  {
    v4 = a1 + 136;
    v10 = (_Cnd_t)(a1 + 136);
    v11 = a1 + 208;
    std::unique_lock<std::mutex>::unique_lock<std::mutex>(v8, a1 + 208);
    while ( *(int *)(v4 + 176) < 2 )
      _Cnd_wait((_Cnd_t)v4, v8[0]);
    std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v8);
  }
  catch ( Concurrency::details::_Interruption_exception )
  {
    v1 = a1;
    v2 = 0;
  }
  catch ( Concurrency::task_canceled )
  {
    v1 = a1;
    v2 = 0;
  }
  catch ( ... )
  {
    if ( !*(_QWORD *)(a1 + 16) )
    {
      v7 = (const struct std::exception_ptr *)std::current_exception(v8);
      Concurrency::details::_Task_impl_base::_CancelWithException((Concurrency::details::_Task_impl_base *)a1, v7);
      __ExceptionPtrDestroy(v8);
    }
    Concurrency::details::_ExceptionHolder::_RethrowUserException(*(Concurrency::details::_ExceptionHolder **)(a1 + 16));
  }
  if ( *(_BYTE *)(v1 + 13) )
  {
    std::unique_lock<std::mutex>::unique_lock<std::mutex>(v8, v11);
    while ( *((int *)v10 + 44) < 2 )
      _Cnd_wait(v10, v8[0]);
    goto LABEL_13;
  }
LABEL_14:
  v5 = *(Concurrency::details::_ExceptionHolder **)(v1 + 16);
  if ( v5 )
    Concurrency::details::_ExceptionHolder::_RethrowUserException(v5);
  LOBYTE(v2) = *(_DWORD *)(v1 + 8) == 4;
  return (unsigned int)(v2 + 1);
}

```

## disassembly

```asm
0x18001df18  mov     [rsp+arg_0], rcx
0x18001df1d  push    rbx
0x18001df1e  push    rsi
0x18001df1f  push    rdi
0x18001df20  sub     rsp, 30h
0x18001df24  mov     rdi, rcx
0x18001df27  xor     ebx, ebx
0x18001df29  cmp     [rcx+0Ch], bl
0x18001df2c  jz      short loc_18001DF61
0x18001df2e  lea     rsi, [rcx+88h]
0x18001df35  lea     rdx, [rsi+48h]
0x18001df39  lea     rcx, [rsp+48h+var_28]
0x18001df3e  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18001df43  jmp     short loc_18001DF53
0x18001df45  mov     rdx, [rsp+48h+var_28]; _Mtx_t
0x18001df4a  mov     rcx, rsi; _Cnd_t
0x18001df4d  call    cs:__imp__Cnd_wait
0x18001df53  cmp     dword ptr [rsi+0B0h], 2
0x18001df5a  jl      short loc_18001DF45
0x18001df5c  jmp     loc_18001DFE1
0x18001df61  lea     rsi, [rcx+88h]
0x18001df68  mov     [rsp+48h+arg_8], rsi
0x18001df6d  lea     rdx, [rsi+48h]
0x18001df71  mov     [rsp+48h+arg_10], rdx
0x18001df76  lea     rcx, [rsp+48h+var_28]
0x18001df7b  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18001df80  jmp     short loc_18001DF90
0x18001df82  mov     rdx, [rsp+48h+var_28]; _Mtx_t
0x18001df87  mov     rcx, rsi; _Cnd_t
0x18001df8a  call    cs:__imp__Cnd_wait
0x18001df90  cmp     dword ptr [rsi+0B0h], 2
0x18001df97  jl      short loc_18001DF82
0x18001df99  lea     rcx, [rsp+48h+var_28]
0x18001df9e  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18001dfa3  nop
0x18001dfa4  jmp     short loc_18001DFAF
0x18001dfa6  jmp     short $+2
0x18001dfa8  mov     rdi, [rsp+48h+arg_0]
0x18001dfad  xor     ebx, ebx
0x18001dfaf  cmp     [rdi+0Dh], bl
0x18001dfb2  jz      short loc_18001DFEB
0x18001dfb4  mov     rsi, [rsp+48h+arg_8]
0x18001dfb9  mov     rdx, [rsp+48h+arg_10]
0x18001dfbe  lea     rcx, [rsp+48h+var_28]
0x18001dfc3  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18001dfc8  jmp     short loc_18001DFD8
0x18001dfca  mov     rdx, [rsp+48h+var_28]; _Mtx_t
0x18001dfcf  mov     rcx, rsi; _Cnd_t
0x18001dfd2  call    cs:__imp__Cnd_wait
0x18001dfd8  cmp     dword ptr [rsi+0B0h], 2
0x18001dfdf  jl      short loc_18001DFCA
0x18001dfe1  lea     rcx, [rsp+48h+var_28]
0x18001dfe6  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18001dfeb  mov     rcx, [rdi+10h]; this
0x18001dfef  test    rcx, rcx
0x18001dff2  jz      short loc_18001DFFA
0x18001dff4  call    ?_RethrowUserException@_ExceptionHolder@details@Concurrency@@QEAAXXZ; Concurrency::details::_ExceptionHolder::_RethrowUserException(void)
0x18001dffa  mov     ecx, [rdi+8]
0x18001dffd  cmp     ecx, 4
0x18001e000  setz    bl
0x18001e003  lea     eax, [rbx+1]
0x18001e006  add     rsp, 30h
0x18001e00a  pop     rdi
0x18001e00b  pop     rsi
0x18001e00c  pop     rbx
0x18001e00d  retn
```
