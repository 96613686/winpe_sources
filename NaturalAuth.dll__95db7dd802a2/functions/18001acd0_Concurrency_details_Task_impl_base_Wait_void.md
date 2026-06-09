# Concurrency::details::_Task_impl_base::_Wait(void)

- ea: `0x18001acd0`
- end: `0x18001adc6`
- name: `?_Wait@_Task_impl_base@details@Concurrency@@QEAA?AW4task_group_status@3@XZ`
- size: `246`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180012620`
- `0x180018c10`
- `0x18001ac80`

## callees

- `0x180011e50`
- `0x180012aec`
- `0x18001a098`
- `0x18001acd0`

## import_xrefs

- `msvcp_win!_Cnd_wait` at `0x18001ad05`
- `msvcp_win!_Cnd_wait` at `0x18001ad42`
- `msvcp_win!_Cnd_wait` at `0x18001ad8a`
- `msvcp_win!_Cnd_wait` at `0x18001ad05`
- `msvcp_win!_Cnd_wait` at `0x18001ad42`
- `msvcp_win!_Cnd_wait` at `0x18001ad8a`

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
0x18001acd0  mov     [rsp+arg_0], rcx
0x18001acd5  push    rbx
0x18001acd6  push    rsi
0x18001acd7  push    rdi
0x18001acd8  sub     rsp, 30h
0x18001acdc  mov     rdi, rcx
0x18001acdf  xor     ebx, ebx
0x18001ace1  cmp     [rcx+0Ch], bl
0x18001ace4  jz      short loc_18001AD19
0x18001ace6  lea     rsi, [rcx+88h]
0x18001aced  lea     rdx, [rsi+48h]
0x18001acf1  lea     rcx, [rsp+48h+var_28]
0x18001acf6  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18001acfb  jmp     short loc_18001AD0B
0x18001acfd  mov     rdx, [rsp+48h+var_28]; _Mtx_t
0x18001ad02  mov     rcx, rsi; _Cnd_t
0x18001ad05  call    cs:__imp__Cnd_wait
0x18001ad0b  cmp     dword ptr [rsi+0B0h], 2
0x18001ad12  jl      short loc_18001ACFD
0x18001ad14  jmp     loc_18001AD99
0x18001ad19  lea     rsi, [rcx+88h]
0x18001ad20  mov     [rsp+48h+arg_8], rsi
0x18001ad25  lea     rdx, [rsi+48h]
0x18001ad29  mov     [rsp+48h+arg_10], rdx
0x18001ad2e  lea     rcx, [rsp+48h+var_28]
0x18001ad33  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18001ad38  jmp     short loc_18001AD48
0x18001ad3a  mov     rdx, [rsp+48h+var_28]; _Mtx_t
0x18001ad3f  mov     rcx, rsi; _Cnd_t
0x18001ad42  call    cs:__imp__Cnd_wait
0x18001ad48  cmp     dword ptr [rsi+0B0h], 2
0x18001ad4f  jl      short loc_18001AD3A
0x18001ad51  lea     rcx, [rsp+48h+var_28]
0x18001ad56  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18001ad5b  nop
0x18001ad5c  jmp     short loc_18001AD67
0x18001ad5e  jmp     short $+2
0x18001ad60  mov     rdi, [rsp+48h+arg_0]
0x18001ad65  xor     ebx, ebx
0x18001ad67  cmp     [rdi+0Dh], bl
0x18001ad6a  jz      short loc_18001ADA3
0x18001ad6c  mov     rsi, [rsp+48h+arg_8]
0x18001ad71  mov     rdx, [rsp+48h+arg_10]
0x18001ad76  lea     rcx, [rsp+48h+var_28]
0x18001ad7b  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18001ad80  jmp     short loc_18001AD90
0x18001ad82  mov     rdx, [rsp+48h+var_28]; _Mtx_t
0x18001ad87  mov     rcx, rsi; _Cnd_t
0x18001ad8a  call    cs:__imp__Cnd_wait
0x18001ad90  cmp     dword ptr [rsi+0B0h], 2
0x18001ad97  jl      short loc_18001AD82
0x18001ad99  lea     rcx, [rsp+48h+var_28]
0x18001ad9e  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18001ada3  mov     rcx, [rdi+10h]; this
0x18001ada7  test    rcx, rcx
0x18001adaa  jz      short loc_18001ADB2
0x18001adac  call    ?_RethrowUserException@_ExceptionHolder@details@Concurrency@@QEAAXXZ; Concurrency::details::_ExceptionHolder::_RethrowUserException(void)
0x18001adb2  mov     ecx, [rdi+8]
0x18001adb5  cmp     ecx, 4
0x18001adb8  setz    bl
0x18001adbb  lea     eax, [rbx+1]
0x18001adbe  add     rsp, 30h
0x18001adc2  pop     rdi
0x18001adc3  pop     rsi
0x18001adc4  pop     rbx
0x18001adc5  retn
```
