# CDevice::QueueProcessingWorkCB_0062(D3D10DDI_HRTDEVICE,void (*)(void *),void (*)(void *),void *)

- ea: `0x18005d950`
- end: `0x18005dac9`
- name: `?QueueProcessingWorkCB_0062@CDevice@@SAJUD3D10DDI_HRTDEVICE@@P6AXPEAX@Z21@Z`
- size: `377`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callees

- `0x18000ac4c`
- `0x18000b920`
- `0x180012c2c`
- `0x18005d950`
- `0x18005dad0`
- `0x1800ea66c`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18005d9bd`
- `msvcp_win!_Mtx_unlock` at `0x18005da00`
- `msvcp_win!_Mtx_unlock` at `0x18005d9bd`
- `msvcp_win!_Mtx_unlock` at `0x18005da00`
- `ntdll!RtlIsCriticalSectionLockedByThread` at `0x18005da80`
- `ntdll!RtlIsCriticalSectionLockedByThread` at `0x18005da80`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDevice::QueueProcessingWorkCB_0062(
        __int64 a1,
        __int64 (__fastcall *a2)(),
        __int64 (__fastcall *a3)(),
        _QWORD *a4)
{
  __int64 (__fastcall *v6)(); // rbx
  __int64 v7; // rdi
  __int64 v8; // rbx
  _QWORD *v10; // rax
  __int64 (__fastcall *v11)(); // [rsp+30h] [rbp-48h] BYREF
  __int64 (__fastcall *v12)(); // [rsp+38h] [rbp-40h]
  _QWORD *v13; // [rsp+40h] [rbp-38h]
  _QWORD *v14; // [rsp+80h] [rbp+8h] BYREF
  __int64 (__fastcall *v15)(); // [rsp+88h] [rbp+10h]

  v15 = a2;
  v6 = a2;
  v7 = *(_QWORD *)(a1 + 24);
  std::_Mutex_base::lock((std::_Mutex_base *)(v7 + 6752));
  if ( *(_DWORD *)(v7 + 444) && (unsigned int)(*(_DWORD *)(v7 + 7176) - 2) > 1 )
  {
    std::_Mutex_base::lock((std::_Mutex_base *)(v7 + 6992));
    v8 = *(_QWORD *)(v7 + 7144);
    _Mtx_unlock((_Mtx_t)(v7 + 6992));
    if ( !(_DWORD)v8 && !RtlIsCriticalSectionLockedByThread(NtCurrentPeb()->LoaderLock) )
    {
      v14 = (_QWORD *)*(unsigned int *)(v7 + 7168);
      BackgroundTaskScheduler::Scheduler::SetSchedulingMode(v7 + 6832, v14);
    }
    v6 = v15;
  }
  if ( dword_180324AF4
    && (qword_180324AE0 & 0x8000000000000008uLL) != 0
    && (qword_180324AE8 & 0x8000000000000008uLL) == qword_180324AE8 )
  {
    v10 = operator new(0x20u);
    if ( v10 )
    {
      *v10 = v7;
      v10[1] = v6;
      v10[2] = a3;
      v10[3] = a4;
    }
    v14 = v10;
    v11 = lambda_2992f94a70ae81749f305bfb70c390e6_::_lambda_invoker_cdecl_;
    v12 = lambda_c1290d2bb50a45f62c5f182b0cda5d55_::_lambda_invoker_cdecl_;
    v13 = v10;
    BackgroundTaskScheduler::Scheduler::QueueTask(v7 + 6832, &v11);
    v14 = 0;
    std::unique_ptr__CDevice::QueueProcessingWorkCB_0062_::_2_::RTContext_std::default_delete__CDevice::QueueProcessingWorkCB_0062_::_2_::RTContext___::_unique_ptr__CDevice::QueueProcessingWorkCB_0062_::_2_::RTContext_std::default_delete__CDevice::QueueProcessingWorkCB_0062_::_2_::RTContext___(&v14);
  }
  else
  {
    v11 = v6;
    v12 = a3;
    v13 = a4;
    BackgroundTaskScheduler::Scheduler::QueueTask(v7 + 6832, &v11);
  }
  _Mtx_unlock((_Mtx_t)(v7 + 6752));
  return 0;
}

```

## disassembly

```asm
0x18005d950  mov     rax, rsp
0x18005d953  mov     [rax+18h], rbx
0x18005d957  mov     [rax+20h], rsi
0x18005d95b  mov     [rax+10h], rdx
0x18005d95f  push    rdi
0x18005d960  push    r12
0x18005d962  push    r13
0x18005d964  push    r14
0x18005d966  push    r15
0x18005d968  sub     rsp, 50h
0x18005d96c  mov     r12, r9
0x18005d96f  mov     r13, r8
0x18005d972  mov     rbx, rdx
0x18005d975  mov     rdi, [rcx+18h]
0x18005d979  lea     rsi, [rdi+1A60h]
0x18005d980  mov     [rax-58h], rsi
0x18005d984  mov     rcx, rsi; this
0x18005d987  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18005d98c  nop
0x18005d98d  cmp     dword ptr [rdi+1BCh], 0
0x18005d994  jz      short loc_18005D9D3
0x18005d996  mov     eax, [rdi+1C08h]
0x18005d99c  sub     eax, 2
0x18005d99f  cmp     eax, 1
0x18005d9a2  jbe     short loc_18005D9D3
0x18005d9a4  lea     r15, [rdi+1B50h]
0x18005d9ab  mov     rcx, r15; this
0x18005d9ae  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18005d9b3  mov     rbx, [rdi+1BE8h]
0x18005d9ba  mov     rcx, r15; _Mtx_t
0x18005d9bd  call    cs:__imp__Mtx_unlock
0x18005d9c3  test    ebx, ebx
0x18005d9c5  jz      loc_18005DA70
0x18005d9cb  mov     rbx, [rsp+78h+arg_8]
0x18005d9d3  cmp     cs:dword_180324AF4, 0
0x18005d9da  jnz     short loc_18005DA23
0x18005d9dc  mov     [rsp+78h+var_48], rbx
0x18005d9e1  mov     [rsp+78h+var_40], r13
0x18005d9e6  mov     [rsp+78h+var_38], r12
0x18005d9eb  lea     rcx, [rdi+1AB0h]
0x18005d9f2  lea     rdx, [rsp+78h+var_48]
0x18005d9f7  call    ?QueueTask@Scheduler@BackgroundTaskScheduler@@QEAAXUTask@2@@Z; BackgroundTaskScheduler::Scheduler::QueueTask(BackgroundTaskScheduler::Task)
0x18005d9fc  nop
0x18005d9fd  mov     rcx, rsi; _Mtx_t
0x18005da00  call    cs:__imp__Mtx_unlock
0x18005da06  nop
0x18005da07  xor     eax, eax
0x18005da09  lea     r11, [rsp+78h+var_28]
0x18005da0e  mov     rbx, [r11+40h]
0x18005da12  mov     rsi, [r11+48h]
0x18005da16  mov     rsp, r11
0x18005da19  pop     r15
0x18005da1b  pop     r14
0x18005da1d  pop     r13
0x18005da1f  pop     r12
0x18005da21  pop     rdi
0x18005da22  retn
0x18005da23  mov     rdx, 8000000000000008h
0x18005da2d  test    cs:qword_180324AE0, rdx
0x18005da34  jz      short loc_18005D9DC
0x18005da36  mov     rax, cs:qword_180324AE8
0x18005da3d  and     rax, rdx
0x18005da40  cmp     rax, cs:qword_180324AE8
0x18005da47  jnz     short loc_18005D9DC
0x18005da49  mov     ecx, 20h ; ' '; dwBytes
0x18005da4e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005da53  test    rax, rax
0x18005da56  jz      loc_180235A96
0x18005da5c  mov     [rax], rdi
0x18005da5f  mov     [rax+8], rbx
0x18005da63  mov     [rax+10h], r13
0x18005da67  mov     [rax+18h], r12
0x18005da6b  jmp     loc_180235A96
0x18005da70  mov     rcx, gs:60h
0x18005da79  mov     rcx, [rcx+110h]; CriticalSection
0x18005da80  call    cs:__imp_RtlIsCriticalSectionLockedByThread
0x18005da86  test    eax, eax
0x18005da88  jnz     loc_18005D9CB
0x18005da8e  mov     eax, [rdi+1C00h]
0x18005da94  mov     dword ptr [rsp+78h+arg_0], eax
0x18005da9b  mov     dword ptr [rsp+78h+arg_0+4], 0
0x18005daa6  mov     rdx, [rsp+78h+arg_0]
0x18005daae  lea     rcx, [rdi+1AB0h]
0x18005dab5  call    ?SetSchedulingMode@Scheduler@BackgroundTaskScheduler@@QEAAXUSchedulingMode@2@@Z; BackgroundTaskScheduler::Scheduler::SetSchedulingMode(BackgroundTaskScheduler::SchedulingMode)
0x18005daba  jmp     loc_18005D9CB
0x18005dabf  mov     eax, 8007000Eh
0x18005dac4  jmp     loc_18005DA09
0x180235a96  mov     [rsp+78h+arg_0], rax
0x180235a9e  lea     rcx, _lambda_2992f94a70ae81749f305bfb70c390e6____lambda_invoker_cdecl_
0x180235aa5  mov     [rsp+78h+var_48], rcx
0x180235aaa  lea     rcx, _lambda_c1290d2bb50a45f62c5f182b0cda5d55____lambda_invoker_cdecl_
0x180235ab1  mov     [rsp+78h+var_40], rcx
0x180235ab6  mov     [rsp+78h+var_38], rax
0x180235abb  lea     rcx, [rdi+1AB0h]
0x180235ac2  lea     rdx, [rsp+78h+var_48]
0x180235ac7  call    ?QueueTask@Scheduler@BackgroundTaskScheduler@@QEAAXUTask@2@@Z; BackgroundTaskScheduler::Scheduler::QueueTask(BackgroundTaskScheduler::Task)
0x180235acc  mov     [rsp+78h+arg_0], 0
0x180235ad8  lea     rcx, [rsp+78h+arg_0]
0x180235ae0  call    std__unique_ptr__CDevice__QueueProcessingWorkCB_0062____2___RTContext_std__default_delete__CDevice__QueueProcessingWorkCB_0062____2___RTContext______unique_ptr__CDevice__QueueProcessingWorkCB_0062____2___RTContext_std__default_delete__CDevice__QueueProcessingWorkCB_0062____2___RTContext___
0x180235ae5  nop
0x180235ae6  jmp     loc_18005D9FD
```
