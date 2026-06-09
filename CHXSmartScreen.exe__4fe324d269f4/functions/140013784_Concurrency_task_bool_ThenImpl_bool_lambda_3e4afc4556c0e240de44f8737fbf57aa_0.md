# Concurrency::task_bool_::_ThenImpl_bool__lambda_3e4afc4556c0e240de44f8737fbf57aa____0

- ea: `0x140013784`
- end: `0x1400138fa`
- name: `Concurrency::task_bool_::_ThenImpl_bool__lambda_3e4afc4556c0e240de44f8737fbf57aa____0`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x1400134c0`

## callees

- `0x1400017a0`
- `0x140003330`
- `0x140012fdc`
- `0x140013784`
- `0x1400145c4`
- `0x14001471c`
- `0x140015024`
- `0x14001b8f4`
- `0x14001cee8`
- `0x140035010`

## string_xrefs

- `0x1400138d7`: `then() cannot be called on a default constructed task.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall Concurrency::task_bool_::_ThenImpl_bool__lambda_3e4afc4556c0e240de44f8737fbf57aa____0(
        Concurrency::details::_Task_impl_base **a1,
        _QWORD *a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v6; // rbx
  Concurrency::details::_Task_impl_base *v10; // rbx
  struct Concurrency::details::_ContinuationTaskHandleBase *v11; // rax
  volatile signed __int32 *v12; // rbx
  _BYTE v14[16]; // [rsp+38h] [rbp-70h] BYREF
  __int64 v15; // [rsp+48h] [rbp-60h]
  _BYTE pExceptionObject[64]; // [rsp+50h] [rbp-58h] BYREF

  v6 = a4;
  if ( !*a1 )
  {
    pplx::invalid_operation::invalid_operation(
      (pplx::invalid_operation *)pExceptionObject,
      "then() cannot be called on a default constructed task.");
    throw (pplx::invalid_operation *)pExceptionObject;
  }
  if ( !a4 )
    v6 = *((_QWORD *)*a1 + 14);
  *(_OWORD *)a2 = 0;
  *a2 = 0;
  a2[1] = 0;
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::_Resetp<Concurrency::details::_Task_impl<unsigned char>>(a2);
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
    v14,
    a6);
  v15 = *(_QWORD *)(a6 + 16);
  Concurrency::task<void>::_CreateImpl(a2, v6, v14);
  *(_BYTE *)(*a2 + 20LL) = *((_BYTE *)*a1 + 20) != 0;
  *(_BYTE *)(*a2 + 21LL) = 0;
  *(_BYTE *)(*a2 + 22LL) = 0;
  v10 = *a1;
  v11 = (struct Concurrency::details::_ContinuationTaskHandleBase *)operator new(0x60u);
  if ( v11 )
    v11 = (struct Concurrency::details::_ContinuationTaskHandleBase *)Concurrency::task_bool_::_ContinuationTaskHandle_bool_void__lambda_3e4afc4556c0e240de44f8737fbf57aa__std::integral_constant_bool_0__Concurrency::details::_TypeSelectorNoAsync_::_ContinuationTaskHandle_bool_void__lambda_3e4afc4556c0e240de44f8737fbf57aa__std::integral_constant_bool_0__Concurrency::details::_TypeSelectorNoAsync_(
                                                                        (_DWORD)v11,
                                                                        (_DWORD)a1,
                                                                        (_DWORD)a2,
                                                                        a3,
                                                                        a5);
  Concurrency::details::_Task_impl_base::_ScheduleContinuation(v10, v11);
  v12 = *(volatile signed __int32 **)(a6 + 8);
  if ( v12 )
  {
    if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x140013784  mov     rax, rsp
0x140013787  mov     [rax+18h], rbx
0x14001378b  mov     [rax+20h], rbp
0x14001378f  mov     [rax+10h], rdx
0x140013793  push    rsi
0x140013794  push    rdi
0x140013795  push    r14
0x140013797  sub     rsp, 90h
0x14001379e  mov     rbx, r9
0x1400137a1  mov     r14, r8
0x1400137a4  mov     rdi, rdx
0x1400137a7  mov     rsi, rcx
0x1400137aa  mov     dword ptr [rax-78h], 0
0x1400137b1  mov     rax, [rcx]
0x1400137b4  test    rax, rax
0x1400137b7  jz      loc_1400138D7
0x1400137bd  test    rbx, rbx
0x1400137c0  jnz     short loc_1400137C6
0x1400137c2  mov     rbx, [rax+70h]
0x1400137c6  xorps   xmm0, xmm0
0x1400137c9  movups  xmmword ptr [rdx], xmm0
0x1400137cc  mov     qword ptr [rdx], 0
0x1400137d3  mov     qword ptr [rdx+8], 0
0x1400137db  mov     rcx, rdi
0x1400137de  call    ??$_Resetp@U?$_Task_impl@E@details@Concurrency@@@?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@AEAAXPEAU?$_Task_impl@E@details@Concurrency@@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::_Resetp<Concurrency::details::_Task_impl<uchar>>(Concurrency::details::_Task_impl<uchar> *)
0x1400137e3  mov     [rsp+0A8h+var_78], 1
0x1400137eb  mov     rbp, [rsp+0A8h+arg_28]
0x1400137f3  mov     rdx, rbp
0x1400137f6  lea     rcx, [rsp+0A8h+var_70]
0x1400137fb  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x140013800  mov     rax, [rbp+10h]
0x140013804  mov     [rsp+0A8h+var_60], rax
0x140013809  lea     r8, [rsp+0A8h+var_70]
0x14001380e  mov     rdx, rbx
0x140013811  mov     rcx, rdi
0x140013814  call    ?_CreateImpl@?$task@X@Concurrency@@QEAAXPEAV_CancellationTokenState@details@pplx@@Uscheduler_ptr@2@@Z; Concurrency::task<void>::_CreateImpl(pplx::details::_CancellationTokenState *,Concurrency::scheduler_ptr)
0x140013819  mov     rax, [rsi]
0x14001381c  cmp     byte ptr [rax+14h], 0
0x140013820  setnz   cl
0x140013823  mov     rax, [rdi]
0x140013826  mov     [rax+14h], cl
0x140013829  mov     rax, [rdi]
0x14001382c  mov     byte ptr [rax+15h], 0
0x140013830  mov     rax, [rdi]
0x140013833  mov     byte ptr [rax+16h], 0
0x140013837  mov     rbx, [rsi]
0x14001383a  mov     ecx, 60h ; '`'; Size
0x14001383f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140013844  mov     [rsp+0A8h+arg_0], rax
0x14001384c  test    rax, rax
0x14001384f  jz      short loc_140013870
0x140013851  mov     rcx, [rsp+0A8h+arg_20]
0x140013859  mov     [rsp+0A8h+var_88], rcx
0x14001385e  mov     r9, r14
0x140013861  mov     r8, rdi
0x140013864  mov     rdx, rsi
0x140013867  mov     rcx, rax
0x14001386a  call    Concurrency__task_bool____ContinuationTaskHandle_bool_void__lambda_3e4afc4556c0e240de44f8737fbf57aa__std__integral_constant_bool_0__Concurrency__details___TypeSelectorNoAsync____ContinuationTaskHandle_bool_void__lambda_3e4afc4556c0e240de44f8737fbf57aa__std__integral_constant_bool_0__Concurrency__details___TypeSelectorNoAsync_
0x14001386f  nop
0x140013870  mov     rdx, rax; struct Concurrency::details::_ContinuationTaskHandleBase *
0x140013873  mov     rcx, rbx; this
0x140013876  call    ?_ScheduleContinuation@_Task_impl_base@details@Concurrency@@QEAAXPEAU_ContinuationTaskHandleBase@23@@Z; Concurrency::details::_Task_impl_base::_ScheduleContinuation(Concurrency::details::_ContinuationTaskHandleBase *)
0x14001387b  nop
0x14001387c  mov     rbx, [rbp+8]
0x140013880  test    rbx, rbx
0x140013883  jz      short loc_1400138BC
0x140013885  or      esi, 0FFFFFFFFh
0x140013888  mov     eax, esi
0x14001388a  lock xadd [rbx+8], eax
0x14001388f  add     eax, esi
0x140013891  jnz     short loc_1400138BC
0x140013893  mov     rax, [rbx]
0x140013896  mov     rcx, rbx
0x140013899  mov     rax, [rax]
0x14001389c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400138a1  mov     eax, esi
0x1400138a3  lock xadd [rbx+0Ch], eax
0x1400138a8  add     eax, esi
0x1400138aa  jnz     short loc_1400138BC
0x1400138ac  mov     rax, [rbx]
0x1400138af  mov     rcx, rbx
0x1400138b2  mov     rax, [rax+8]
0x1400138b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400138bb  nop
0x1400138bc  mov     rax, rdi
0x1400138bf  lea     r11, [rsp+0A8h+var_18]
0x1400138c7  mov     rbx, [r11+30h]
0x1400138cb  mov     rbp, [r11+38h]
0x1400138cf  mov     rsp, r11
0x1400138d2  pop     r14
0x1400138d4  pop     rdi
0x1400138d5  pop     rsi
0x1400138d6  retn
0x1400138d7  lea     rdx, aThenCannotBeCa; "then() cannot be called on a default co"...
0x1400138de  lea     rcx, [rsp+0A8h+pExceptionObject]; this
0x1400138e3  call    ??0invalid_operation@pplx@@QEAA@PEBD@Z; pplx::invalid_operation::invalid_operation(char const *)
0x1400138e8  lea     rdx, _TI2?AVinvalid_operation@pplx@@; pThrowInfo
0x1400138ef  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x1400138f4  call    _CxxThrowException_0
```
