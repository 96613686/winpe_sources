# Concurrency::details::_Task_impl_base::_Wait(void)

- ea: `0x1800244b0`
- end: `0x1800245a6`
- name: `?_Wait@_Task_impl_base@details@Concurrency@@QEAA?AW4task_group_status@3@XZ`
- size: `246`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001e0a4`
- `0x180023590`
- `0x180024460`

## callees

- `0x18001d9e0`
- `0x18001e230`
- `0x180023dec`
- `0x1800244b0`

## import_xrefs

- `msvcp_win!_Cnd_wait` at `0x1800244e5`
- `msvcp_win!_Cnd_wait` at `0x180024522`
- `msvcp_win!_Cnd_wait` at `0x18002456a`
- `msvcp_win!_Cnd_wait` at `0x1800244e5`
- `msvcp_win!_Cnd_wait` at `0x180024522`
- `msvcp_win!_Cnd_wait` at `0x18002456a`

## pseudocode

```c
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
    std::unique_lock<std::mutex>::~unique_lock<std::mutex>((__int64)v8);
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
    std::unique_lock<std::mutex>::~unique_lock<std::mutex>((__int64)v8);
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
0x1800244b0  mov     [rsp+arg_0], rcx
0x1800244b5  push    rbx
0x1800244b6  push    rsi
0x1800244b7  push    rdi
0x1800244b8  sub     rsp, 30h
0x1800244bc  mov     rdi, rcx
0x1800244bf  xor     ebx, ebx
0x1800244c1  cmp     [rcx+0Ch], bl
0x1800244c4  jz      short loc_1800244F9
0x1800244c6  lea     rsi, [rcx+88h]
0x1800244cd  lea     rdx, [rsi+48h]
0x1800244d1  lea     rcx, [rsp+48h+var_28]
0x1800244d6  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x1800244db  jmp     short loc_1800244EB
0x1800244dd  mov     rdx, [rsp+48h+var_28]; _Mtx_t
0x1800244e2  mov     rcx, rsi; _Cnd_t
0x1800244e5  call    cs:__imp__Cnd_wait
0x1800244eb  cmp     dword ptr [rsi+0B0h], 2
0x1800244f2  jl      short loc_1800244DD
0x1800244f4  jmp     loc_180024579
0x1800244f9  lea     rsi, [rcx+88h]
0x180024500  mov     [rsp+48h+arg_8], rsi
0x180024505  lea     rdx, [rsi+48h]
0x180024509  mov     [rsp+48h+arg_10], rdx
0x18002450e  lea     rcx, [rsp+48h+var_28]
0x180024513  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x180024518  jmp     short loc_180024528
0x18002451a  mov     rdx, [rsp+48h+var_28]; _Mtx_t
0x18002451f  mov     rcx, rsi; _Cnd_t
0x180024522  call    cs:__imp__Cnd_wait
0x180024528  cmp     dword ptr [rsi+0B0h], 2
0x18002452f  jl      short loc_18002451A
0x180024531  lea     rcx, [rsp+48h+var_28]
0x180024536  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18002453b  nop
0x18002453c  jmp     short loc_180024547
0x18002453e  jmp     short $+2
0x180024540  mov     rdi, [rsp+48h+arg_0]
0x180024545  xor     ebx, ebx
0x180024547  cmp     [rdi+0Dh], bl
0x18002454a  jz      short loc_180024583
0x18002454c  mov     rsi, [rsp+48h+arg_8]
0x180024551  mov     rdx, [rsp+48h+arg_10]
0x180024556  lea     rcx, [rsp+48h+var_28]
0x18002455b  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x180024560  jmp     short loc_180024570
0x180024562  mov     rdx, [rsp+48h+var_28]; _Mtx_t
0x180024567  mov     rcx, rsi; _Cnd_t
0x18002456a  call    cs:__imp__Cnd_wait
0x180024570  cmp     dword ptr [rsi+0B0h], 2
0x180024577  jl      short loc_180024562
0x180024579  lea     rcx, [rsp+48h+var_28]
0x18002457e  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x180024583  mov     rcx, [rdi+10h]; this
0x180024587  test    rcx, rcx
0x18002458a  jz      short loc_180024592
0x18002458c  call    ?_RethrowUserException@_ExceptionHolder@details@Concurrency@@QEAAXXZ; Concurrency::details::_ExceptionHolder::_RethrowUserException(void)
0x180024592  mov     ecx, [rdi+8]
0x180024595  cmp     ecx, 4
0x180024598  setz    bl
0x18002459b  lea     eax, [rbx+1]
0x18002459e  add     rsp, 30h
0x1800245a2  pop     rdi
0x1800245a3  pop     rsi
0x1800245a4  pop     rbx
0x1800245a5  retn
```
