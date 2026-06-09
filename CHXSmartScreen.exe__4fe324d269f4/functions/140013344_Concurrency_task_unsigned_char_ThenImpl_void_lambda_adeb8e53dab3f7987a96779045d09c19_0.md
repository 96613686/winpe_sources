# Concurrency::task_unsigned_char_::_ThenImpl_void__lambda_adeb8e53dab3f7987a96779045d09c19____0

- ea: `0x140013344`
- end: `0x1400134b8`
- name: `Concurrency::task_unsigned_char_::_ThenImpl_void__lambda_adeb8e53dab3f7987a96779045d09c19____0`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x140013080`

## callees

- `0x1400017a0`
- `0x140003330`
- `0x140012fdc`
- `0x140013344`
- `0x140014460`
- `0x14001471c`
- `0x140015024`
- `0x14001b8f4`
- `0x14001cee8`
- `0x140035010`

## string_xrefs

- `0x140013495`: `then() cannot be called on a default constructed task.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall Concurrency::task_unsigned_char_::_ThenImpl_void__lambda_adeb8e53dab3f7987a96779045d09c19____0(
        Concurrency::details::_Task_impl_base **a1,
        _QWORD *a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v9; // rbx
  Concurrency::details::_Task_impl_base *v10; // rbx
  struct Concurrency::details::_ContinuationTaskHandleBase *v11; // rax
  volatile signed __int32 *v12; // rbx
  _BYTE v14[16]; // [rsp+38h] [rbp-70h] BYREF
  __int64 v15; // [rsp+48h] [rbp-60h]
  _BYTE pExceptionObject[64]; // [rsp+50h] [rbp-58h] BYREF

  if ( !*a1 )
  {
    pplx::invalid_operation::invalid_operation(
      (pplx::invalid_operation *)pExceptionObject,
      "then() cannot be called on a default constructed task.");
    throw (pplx::invalid_operation *)pExceptionObject;
  }
  v9 = 2;
  if ( a4 )
    v9 = a4;
  *(_OWORD *)a2 = 0;
  *a2 = 0;
  a2[1] = 0;
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::_Resetp<Concurrency::details::_Task_impl<unsigned char>>(a2);
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
    v14,
    a6);
  v15 = *(_QWORD *)(a6 + 16);
  Concurrency::task<void>::_CreateImpl(a2, v9, v14);
  *(_BYTE *)(*a2 + 20LL) = *((_BYTE *)*a1 + 20) != 0;
  *(_BYTE *)(*a2 + 21LL) = 0;
  *(_BYTE *)(*a2 + 22LL) = 0;
  v10 = *a1;
  v11 = (struct Concurrency::details::_ContinuationTaskHandleBase *)operator new(0x58u);
  if ( v11 )
    v11 = (struct Concurrency::details::_ContinuationTaskHandleBase *)Concurrency::task_unsigned_char_::_ContinuationTaskHandle_void_void__lambda_adeb8e53dab3f7987a96779045d09c19__std::integral_constant_bool_1__Concurrency::details::_TypeSelectorNoAsync_::_ContinuationTaskHandle_void_void__lambda_adeb8e53dab3f7987a96779045d09c19__std::integral_constant_bool_1__Concurrency::details::_TypeSelectorNoAsync_(
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
0x140013344  mov     rax, rsp
0x140013347  mov     [rax+18h], rbx
0x14001334b  mov     [rax+20h], rbp
0x14001334f  mov     [rax+10h], rdx
0x140013353  push    rsi
0x140013354  push    rdi
0x140013355  push    r14
0x140013357  sub     rsp, 90h
0x14001335e  mov     rbp, r8
0x140013361  mov     rdi, rdx
0x140013364  mov     rsi, rcx
0x140013367  mov     dword ptr [rax-78h], 0
0x14001336e  cmp     qword ptr [rcx], 0
0x140013372  jz      loc_140013495
0x140013378  mov     ebx, 2
0x14001337d  test    r9, r9
0x140013380  cmovnz  rbx, r9
0x140013384  xorps   xmm0, xmm0
0x140013387  movups  xmmword ptr [rdx], xmm0
0x14001338a  mov     qword ptr [rdx], 0
0x140013391  mov     qword ptr [rdx+8], 0
0x140013399  mov     rcx, rdx
0x14001339c  call    ??$_Resetp@U?$_Task_impl@E@details@Concurrency@@@?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@AEAAXPEAU?$_Task_impl@E@details@Concurrency@@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::_Resetp<Concurrency::details::_Task_impl<uchar>>(Concurrency::details::_Task_impl<uchar> *)
0x1400133a1  mov     [rsp+0A8h+var_78], 1
0x1400133a9  mov     r14, [rsp+0A8h+arg_28]
0x1400133b1  mov     rdx, r14
0x1400133b4  lea     rcx, [rsp+0A8h+var_70]
0x1400133b9  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x1400133be  mov     rax, [r14+10h]
0x1400133c2  mov     [rsp+0A8h+var_60], rax
0x1400133c7  lea     r8, [rsp+0A8h+var_70]
0x1400133cc  mov     rdx, rbx
0x1400133cf  mov     rcx, rdi
0x1400133d2  call    ?_CreateImpl@?$task@X@Concurrency@@QEAAXPEAV_CancellationTokenState@details@pplx@@Uscheduler_ptr@2@@Z; Concurrency::task<void>::_CreateImpl(pplx::details::_CancellationTokenState *,Concurrency::scheduler_ptr)
0x1400133d7  mov     rax, [rsi]
0x1400133da  cmp     byte ptr [rax+14h], 0
0x1400133de  setnz   cl
0x1400133e1  mov     rax, [rdi]
0x1400133e4  mov     [rax+14h], cl
0x1400133e7  mov     rax, [rdi]
0x1400133ea  mov     byte ptr [rax+15h], 0
0x1400133ee  mov     rax, [rdi]
0x1400133f1  mov     byte ptr [rax+16h], 0
0x1400133f5  mov     rbx, [rsi]
0x1400133f8  mov     ecx, 58h ; 'X'; Size
0x1400133fd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140013402  mov     [rsp+0A8h+arg_0], rax
0x14001340a  test    rax, rax
0x14001340d  jz      short loc_14001342E
0x14001340f  mov     rcx, [rsp+0A8h+arg_20]
0x140013417  mov     [rsp+0A8h+var_88], rcx
0x14001341c  mov     r9, rbp
0x14001341f  mov     r8, rdi
0x140013422  mov     rdx, rsi
0x140013425  mov     rcx, rax
0x140013428  call    Concurrency__task_unsigned_char____ContinuationTaskHandle_void_void__lambda_adeb8e53dab3f7987a96779045d09c19__std__integral_constant_bool_1__Concurrency__details___TypeSelectorNoAsync____ContinuationTaskHandle_void_void__lambda_adeb8e53dab3f7987a96779045d09c19__std__integral_constant_bool_1__Concurrency__details___TypeSelectorNoAsync_
0x14001342d  nop
0x14001342e  mov     rdx, rax; struct Concurrency::details::_ContinuationTaskHandleBase *
0x140013431  mov     rcx, rbx; this
0x140013434  call    ?_ScheduleContinuation@_Task_impl_base@details@Concurrency@@QEAAXPEAU_ContinuationTaskHandleBase@23@@Z; Concurrency::details::_Task_impl_base::_ScheduleContinuation(Concurrency::details::_ContinuationTaskHandleBase *)
0x140013439  nop
0x14001343a  mov     rbx, [r14+8]
0x14001343e  test    rbx, rbx
0x140013441  jz      short loc_14001347A
0x140013443  or      esi, 0FFFFFFFFh
0x140013446  mov     eax, esi
0x140013448  lock xadd [rbx+8], eax
0x14001344d  add     eax, esi
0x14001344f  jnz     short loc_14001347A
0x140013451  mov     rax, [rbx]
0x140013454  mov     rcx, rbx
0x140013457  mov     rax, [rax]
0x14001345a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001345f  mov     eax, esi
0x140013461  lock xadd [rbx+0Ch], eax
0x140013466  add     eax, esi
0x140013468  jnz     short loc_14001347A
0x14001346a  mov     rax, [rbx]
0x14001346d  mov     rcx, rbx
0x140013470  mov     rax, [rax+8]
0x140013474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013479  nop
0x14001347a  mov     rax, rdi
0x14001347d  lea     r11, [rsp+0A8h+var_18]
0x140013485  mov     rbx, [r11+30h]
0x140013489  mov     rbp, [r11+38h]
0x14001348d  mov     rsp, r11
0x140013490  pop     r14
0x140013492  pop     rdi
0x140013493  pop     rsi
0x140013494  retn
0x140013495  lea     rdx, aThenCannotBeCa; "then() cannot be called on a default co"...
0x14001349c  lea     rcx, [rsp+0A8h+pExceptionObject]; this
0x1400134a1  call    ??0invalid_operation@pplx@@QEAA@PEBD@Z; pplx::invalid_operation::invalid_operation(char const *)
0x1400134a6  lea     rdx, _TI2?AVinvalid_operation@pplx@@; pThrowInfo
0x1400134ad  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x1400134b2  call    _CxxThrowException_0
```
