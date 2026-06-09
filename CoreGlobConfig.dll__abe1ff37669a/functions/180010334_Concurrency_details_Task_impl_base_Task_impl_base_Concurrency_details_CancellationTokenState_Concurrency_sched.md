# Concurrency::details::_Task_impl_base::_Task_impl_base(Concurrency::details::_CancellationTokenState *,Concurrency::scheduler_ptr)

- ea: `0x180010334`
- end: `0x180010437`
- name: `??0_Task_impl_base@details@Concurrency@@QEAA@PEAV_CancellationTokenState@12@Uscheduler_ptr@2@@Z`
- size: `259`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000c964`

## callees

- `0x18000f958`
- `0x180010290`
- `0x18001030c`
- `0x180010334`
- `0x180010754`
- `0x18001cc40`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_Task_impl_base::_Task_impl_base(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD *v6; // r8
  __int64 v7; // r8
  std::condition_variable *v8; // r9
  __int64 v9; // r9
  int v10; // edx
  __int64 v11; // r9
  __int64 v12; // rcx
  __int64 v13; // r8
  std::_Ref_count_base *v14; // rcx
  __int64 v15; // r9
  std::_Ref_count_base *v16; // rcx
  std::_Ref_count_base *v18[5]; // [rsp+20h] [rbp-28h] BYREF

  *(_WORD *)(a1 + 12) = 0;
  *(_QWORD *)a1 = &Concurrency::details::_Task_impl_base::`vftable';
  *(_DWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  std::_Mutex_base::_Mutex_base((std::_Mutex_base *)(a1 + 32), a2);
  *(_QWORD *)(a1 + 112) = 0;
  *(_QWORD *)(a1 + 128) = 0;
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
    v18,
    v6);
  v18[2] = *(std::_Ref_count_base **)(v7 + 16);
  std::condition_variable::condition_variable(v8);
  std::_Mutex_base::_Mutex_base((std::_Mutex_base *)(v9 + 72), v10);
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
    (_QWORD *)(v11 + 152),
    v18);
  *(_QWORD *)(v12 + 16) = v13;
  v14 = v18[1];
  *(_DWORD *)(v15 + 176) = 0;
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
  Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack((Concurrency::details::_TaskCreationCallstack *)(a1 + 320));
  *(_QWORD *)(a1 + 352) = a1;
  *(_WORD *)(a1 + 360) = 0;
  *(_QWORD *)(a1 + 120) = a2;
  if ( a2 != 2 )
    _InterlockedIncrement((volatile signed __int32 *)(a2 + 8));
  v16 = *(std::_Ref_count_base **)(a3 + 8);
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
  return a1;
}

```

## disassembly

```asm
0x180010334  mov     [rsp+arg_0], rbx
0x180010339  mov     [rsp+arg_8], rsi
0x18001033e  push    rdi
0x18001033f  sub     rsp, 40h
0x180010343  mov     word ptr [rcx+0Ch], 0
0x180010349  lea     rax, ??_7_Task_impl_base@details@Concurrency@@6B@; const Concurrency::details::_Task_impl_base::`vftable'
0x180010350  mov     [rcx], rax
0x180010353  mov     rbx, rcx
0x180010356  mov     dword ptr [rcx+8], 0
0x18001035d  mov     rsi, r8
0x180010360  mov     qword ptr [rcx+10h], 0
0x180010368  mov     rdi, rdx
0x18001036b  mov     qword ptr [rcx+18h], 0
0x180010373  add     rcx, 20h ; ' '; this
0x180010377  call    ??0_Mutex_base@std@@QEAA@H@Z; std::_Mutex_base::_Mutex_base(int)
0x18001037c  mov     rdx, r8
0x18001037f  mov     qword ptr [rbx+70h], 0
0x180010387  lea     rcx, [rsp+48h+var_28]
0x18001038c  mov     qword ptr [rbx+80h], 0
0x180010397  lea     r9, [rbx+88h]
0x18001039e  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x1800103a3  mov     r8, [r8+10h]
0x1800103a7  mov     rcx, r9; this
0x1800103aa  mov     [rsp+48h+var_18], r8
0x1800103af  call    ??0condition_variable@std@@QEAA@XZ; std::condition_variable::condition_variable(void)
0x1800103b4  lea     rcx, [r9+48h]; this
0x1800103b8  call    ??0_Mutex_base@std@@QEAA@H@Z; std::_Mutex_base::_Mutex_base(int)
0x1800103bd  lea     rcx, [r9+98h]
0x1800103c4  lea     rdx, [rsp+48h+var_28]
0x1800103c9  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x1800103ce  mov     [rcx+10h], r8
0x1800103d2  mov     rcx, [rsp+48h+var_20]; this
0x1800103d7  mov     dword ptr [r9+0B0h], 0
0x1800103e2  test    rcx, rcx
0x1800103e5  jz      short loc_1800103EC
0x1800103e7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800103ec  lea     rcx, [rbx+140h]; this
0x1800103f3  call    ??0_TaskCreationCallstack@details@Concurrency@@QEAA@XZ; Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(void)
0x1800103f8  mov     [rbx+160h], rbx
0x1800103ff  mov     word ptr [rbx+168h], 0
0x180010408  mov     [rbx+78h], rdi
0x18001040c  cmp     rdi, 2
0x180010410  jz      short loc_180010416
0x180010412  lock inc dword ptr [rdi+8]
0x180010416  mov     rcx, [rsi+8]; this
0x18001041a  test    rcx, rcx
0x18001041d  jz      short loc_180010424
0x18001041f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180010424  mov     rsi, [rsp+48h+arg_8]
0x180010429  mov     rax, rbx
0x18001042c  mov     rbx, [rsp+48h+arg_0]
0x180010431  add     rsp, 40h
0x180010435  pop     rdi
0x180010436  retn
```
