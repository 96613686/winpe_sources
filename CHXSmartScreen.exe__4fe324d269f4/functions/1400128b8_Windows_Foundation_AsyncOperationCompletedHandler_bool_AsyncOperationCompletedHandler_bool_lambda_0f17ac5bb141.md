# Windows::Foundation::AsyncOperationCompletedHandler<bool>::AsyncOperationCompletedHandler<bool>(_lambda_0f17ac5bb141cf2bc7352f8cf74b5f7d_,Platform::CallbackContext,bool)

- ea: `0x1400128b8`
- end: `0x1400129f4`
- name: `??$?0V_lambda_0f17ac5bb141cf2bc7352f8cf74b5f7d_@@@?$AsyncOperationCompletedHandler@_N@Foundation@Windows@@QE$AAA@V_lambda_0f17ac5bb141cf2bc7352f8cf74b5f7d_@@W4CallbackContext@Platform@@_N@Z`
- size: `316`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140012518`

## callees

- `0x1400128b8`
- `0x14001471c`
- `0x140035010`

## import_xrefs

- `wincorlib!??0Delegate@Platform@@QE$AAA@XZ` at `0x1400128d9`
- `wincorlib!??0Delegate@Platform@@QE$AAA@XZ` at `0x1400128d9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall Windows::Foundation::AsyncOperationCompletedHandler<bool>::AsyncOperationCompletedHandler<bool>(
        _QWORD *a1,
        __int64 *a2)
{
  _QWORD *v4; // rbx
  volatile signed __int32 *v5; // rdi
  volatile signed __int32 *v6; // rbx
  __int64 v8; // [rsp+20h] [rbp-28h] BYREF
  volatile signed __int32 *v9; // [rsp+28h] [rbp-20h]

  Platform::Delegate::Delegate(a1 + 2);
  *a1 = &Windows::Foundation::AsyncOperationCompletedHandler<bool>::`vftable'{for `__abi_IUnknown'};
  a1[1] = &Windows::Foundation::AsyncOperationCompletedHandler<bool>::`vftable'{for `Platform::Object'};
  a1[2] = &Windows::Foundation::AsyncOperationCompletedHandler<bool>::`vftable';
  a1[4] = -1;
  if ( __abi_module )
    (**(void (__fastcall ***)(struct __abi_Module *))__abi_module)(__abi_module);
  v4 = a1 + 5;
  a1[37] = a1 + 5;
  if ( a1 != (_QWORD *)-40LL )
  {
    std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
      &v8,
      a2);
    *v4 = &Platform::Details::__abi_FunctorCapture<_lambda_0f17ac5bb141cf2bc7352f8cf74b5f7d_,void,Windows::Foundation::IAsyncOperation<bool> __gc *,enum Windows::Foundation::AsyncStatus>::`vftable';
    std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
      a1 + 6,
      &v8);
    v5 = v9;
    if ( v9 )
    {
      if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
        if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
      }
    }
  }
  a1[37] = v4;
  v6 = (volatile signed __int32 *)a2[1];
  if ( v6 )
  {
    if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1400128b8  mov     [rsp+arg_10], rbx
0x1400128bd  mov     [rsp+arg_18], rbp
0x1400128c2  mov     [rsp+arg_8], rdx
0x1400128c7  push    rsi
0x1400128c8  push    rdi
0x1400128c9  push    r14
0x1400128cb  sub     rsp, 30h
0x1400128cf  mov     rbp, rdx
0x1400128d2  mov     rsi, rcx
0x1400128d5  add     rcx, 10h
0x1400128d9  call    cs:__imp_??0Delegate@Platform@@QE$AAA@XZ; Platform::Delegate::Delegate(void)
0x1400128df  lea     rax, ??_7?$AsyncOperationCompletedHandler@_N@Foundation@Windows@@6B__abi_IUnknown@@@; const Windows::Foundation::AsyncOperationCompletedHandler<bool>::`vftable'{for `__abi_IUnknown'}
0x1400128e6  mov     [rsi], rax
0x1400128e9  lea     rax, ??_7?$AsyncOperationCompletedHandler@_N@Foundation@Windows@@6BObject@Platform@@@; const Windows::Foundation::AsyncOperationCompletedHandler<bool>::`vftable'{for `Platform::Object'}
0x1400128f0  mov     [rsi+8], rax
0x1400128f4  lea     rax, ??_7?$AsyncOperationCompletedHandler@_N@Foundation@Windows@@6B@; const Windows::Foundation::AsyncOperationCompletedHandler<bool>::`vftable'
0x1400128fb  mov     [rsi+10h], rax
0x1400128ff  or      r14, 0FFFFFFFFFFFFFFFFh
0x140012903  mov     [rsi+20h], r14
0x140012907  mov     rcx, cs:?__abi_module@@3PEAU__abi_Module@@EA; __abi_Module * __abi_module
0x14001290e  test    rcx, rcx
0x140012911  jz      short loc_14001291E
0x140012913  mov     rax, [rcx]
0x140012916  mov     rax, [rax]
0x140012919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001291e  lea     rbx, [rsi+28h]
0x140012922  mov     [rbx+100h], rbx
0x140012929  test    rbx, rbx
0x14001292c  jz      short loc_140012996
0x14001292e  mov     rdx, rbp
0x140012931  lea     rcx, [rsp+48h+var_28]
0x140012936  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x14001293b  lea     rax, ??_7?$__abi_FunctorCapture@V_lambda_0f17ac5bb141cf2bc7352f8cf74b5f7d_@@XPE$AAU?$IAsyncOperation@_N@Foundation@Windows@@W4AsyncStatus@34@@Details@Platform@@6B@; const Platform::Details::__abi_FunctorCapture<_lambda_0f17ac5bb141cf2bc7352f8cf74b5f7d_,void,Windows::Foundation::IAsyncOperation<bool> *,Windows::Foundation::AsyncStatus>::`vftable'
0x140012942  mov     [rbx], rax
0x140012945  lea     rcx, [rbx+8]
0x140012949  lea     rdx, [rsp+48h+var_28]
0x14001294e  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x140012953  nop
0x140012954  mov     rdi, [rsp+48h+var_20]
0x140012959  test    rdi, rdi
0x14001295c  jz      short loc_140012996
0x14001295e  mov     eax, r14d
0x140012961  lock xadd [rdi+8], eax
0x140012966  add     eax, r14d
0x140012969  jnz     short loc_140012996
0x14001296b  mov     rax, [rdi]
0x14001296e  mov     rcx, rdi
0x140012971  mov     rax, [rax]
0x140012974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012979  mov     eax, r14d
0x14001297c  lock xadd [rdi+0Ch], eax
0x140012981  add     eax, r14d
0x140012984  jnz     short loc_140012996
0x140012986  mov     rax, [rdi]
0x140012989  mov     rcx, rdi
0x14001298c  mov     rax, [rax+8]
0x140012990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012995  nop
0x140012996  mov     [rsi+128h], rbx
0x14001299d  mov     rbx, [rbp+8]
0x1400129a1  test    rbx, rbx
0x1400129a4  jz      short loc_1400129DE
0x1400129a6  mov     eax, r14d
0x1400129a9  lock xadd [rbx+8], eax
0x1400129ae  add     eax, r14d
0x1400129b1  jnz     short loc_1400129DE
0x1400129b3  mov     rax, [rbx]
0x1400129b6  mov     rcx, rbx
0x1400129b9  mov     rax, [rax]
0x1400129bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400129c1  mov     eax, r14d
0x1400129c4  lock xadd [rbx+0Ch], eax
0x1400129c9  add     eax, r14d
0x1400129cc  jnz     short loc_1400129DE
0x1400129ce  mov     rax, [rbx]
0x1400129d1  mov     rcx, rbx
0x1400129d4  mov     rax, [rax+8]
0x1400129d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400129dd  nop
0x1400129de  mov     rax, rsi
0x1400129e1  mov     rbx, [rsp+48h+arg_10]
0x1400129e6  mov     rbp, [rsp+48h+arg_18]
0x1400129eb  add     rsp, 30h
0x1400129ef  pop     r14
0x1400129f1  pop     rdi
0x1400129f2  pop     rsi
0x1400129f3  retn
```
