# Concurrency::details::_AsyncTaskGeneratorThunk__lambda_1157107cf0b2a02d19dff03d451b4015___::_AsyncTaskGeneratorThunk__lambda_1157107cf0b2a02d19dff03d451b4015___

- ea: `0x18008021c`
- end: `0x1800803ce`
- name: `Concurrency::details::_AsyncTaskGeneratorThunk__lambda_1157107cf0b2a02d19dff03d451b4015___::_AsyncTaskGeneratorThunk__lambda_1157107cf0b2a02d19dff03d451b4015___`
- size: `434`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18007e2a8`

## callees

- `0x180005e50`
- `0x18003a724`
- `0x18003feb4`
- `0x18007fcf8`
- `0x18008021c`
- `0x180081484`
- `0x1800816fc`
- `0x18008f9a4`
- `0x1800fb010`

## import_xrefs

- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x1800803a4`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x1800803a4`
- `wincorlib!??0Object@Platform@@QE$AAA@XZ` at `0x180080248`
- `wincorlib!??0Object@Platform@@QE$AAA@XZ` at `0x180080248`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall Concurrency::details::_AsyncTaskGeneratorThunk__lambda_1157107cf0b2a02d19dff03d451b4015___::_AsyncTaskGeneratorThunk__lambda_1157107cf0b2a02d19dff03d451b4015___(
        _QWORD *a1,
        __int64 a2,
        const struct Concurrency::details::_TaskCreationCallstack *a3)
{
  _QWORD *v6; // r14
  _QWORD *v7; // rbx
  __int64 Exception; // [rsp+20h] [rbp-28h]
  __int64 pExceptionObject; // [rsp+68h] [rbp+20h] BYREF

  v6 = a1 + 1;
  v7 = a1 + 4;
  Platform::Object::Object(a1 + 4);
  *v6 = &___7___AsyncInfoBase_U___AsyncAttributes_X_NU___TaskTypeTraits_V__task__N_Concurrency___0A__details_Concurrency___0A__0A__details_Concurrency___00_details_Concurrency__6B__I___AsyncInfoBase_U___AsyncAttributes_X_NU___TaskTypeTraits_V__task__N_Concurrency___0A__details_Concurrency___0A__0A__details_Concurrency___00PublicNonVirtuals_12__;
  v6[1] = &Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,bool,Concurrency::details::_TaskTypeTraits<Concurrency::task<bool>,0>,0,0>,1>::`vftable'{for `Platform::Object's `Windows::Foundation::IAsyncOperation<bool>'};
  v6[2] = &Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,bool,Concurrency::details::_TaskTypeTraits<Concurrency::task<bool>,0>,0,0>,1>::`vftable'{for `Windows::Foundation::IAsyncInfo'};
  *v7 = &Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,bool,Concurrency::details::_TaskTypeTraits<Concurrency::task<bool>,0>,0,0>,1>::`vftable'{for `Platform::Object'};
  v6[4] = 0;
  v6[5] = 0;
  *((_DWORD *)v6 + 12) = -1;
  *((_DWORD *)v6 + 13) = 0;
  *((_DWORD *)v6 + 15) = 0;
  *((_DWORD *)v6 + 16) = 0;
  *((_DWORD *)v6 + 14) = _InterlockedIncrement(&dword_18013E6D8);
  v6[1] = &Concurrency::details::_AsyncProgressBase<Concurrency::details::_AsyncAttributes<void,bool,Concurrency::details::_TaskTypeTraits<Concurrency::task<bool>,0>,0,0>,0,1>::`vftable'{for `Platform::Object's `Windows::Foundation::IAsyncOperation<bool>'};
  v6[2] = &Concurrency::details::_AsyncProgressBase<Concurrency::details::_AsyncAttributes<void,bool,Concurrency::details::_TaskTypeTraits<Concurrency::task<bool>,0>,0,0>,0,1>::`vftable'{for `Windows::Foundation::IAsyncInfo'};
  *v7 = &Concurrency::details::_AsyncProgressBase<Concurrency::details::_AsyncAttributes<void,bool,Concurrency::details::_TaskTypeTraits<Concurrency::task<bool>,0>,0,0>,0,1>::`vftable'{for `Platform::Object'};
  *a1 = &off_1801335E0;
  *v6 = off_180133510;
  a1[2] = off_180133580;
  a1[3] = off_180133460;
  a1[4] = off_1801334E0;
  a1[11] = off_180133408;
  a1[12] = off_180133430;
  __abi_FTMWeakRefData::__abi_FTMWeakRefData(a1 + 66);
  a1[13] = 0;
  a1[14] = 0;
  Concurrency::cancellation_token_source::cancellation_token_source((Concurrency::cancellation_token_source *)(a1 + 15));
  Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(
    (Concurrency::details::_TaskCreationCallstack *)(a1 + 16),
    a3);
  lambda_1157107cf0b2a02d19dff03d451b4015_::_lambda_1157107cf0b2a02d19dff03d451b4015_(a1 + 20, a2);
  if ( !(unsigned __int8)Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,void,Concurrency::details::_TaskTypeTraits<Concurrency::task<void>,0>,0,0>,1>::_TransitionToState(
                           v6,
                           0) )
  {
    Exception = Platform::Exception::CreateException(2147483661LL);
    pExceptionObject = __abi_winrt_ptr_ctor(Exception);
    throw (Platform::Exception **)&pExceptionObject;
  }
  (*(void (**)(void))(*v6 + 88LL))();
  return a1;
}

```

## disassembly

```asm
0x18008021c  mov     [rsp+arg_8], rbx
0x180080221  mov     [rsp+arg_10], rsi
0x180080226  mov     [rsp+arg_0], rcx
0x18008022b  push    rdi
0x18008022c  push    r14
0x18008022e  push    r15
0x180080230  sub     rsp, 30h
0x180080234  mov     rdi, r8
0x180080237  mov     rsi, rdx
0x18008023a  mov     r15, rcx
0x18008023d  lea     r14, [rcx+8]
0x180080241  lea     rbx, [r14+18h]
0x180080245  mov     rcx, rbx
0x180080248  call    cs:__imp_??0Object@Platform@@QE$AAA@XZ; Platform::Object::Object(void)
0x18008024e  lea     rax, ??_7?$_AsyncInfoBase@U?$_AsyncAttributes@X_NU?$_TaskTypeTraits@V?$task@_N@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00@details@Concurrency@@6B__I?$_AsyncInfoBase@U?$_AsyncAttributes@X_NU?$_TaskTypeTraits@V?$task@_N@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00PublicNonVirtuals@12@@
0x180080255  mov     [r14], rax
0x180080258  lea     rax, ??_7?$_AsyncInfoBase@U?$_AsyncAttributes@X_NU?$_TaskTypeTraits@V?$task@_N@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00@details@Concurrency@@6BObject@Platform@@?$IAsyncOperation@_N@Foundation@Windows@@@; const Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,bool,Concurrency::details::_TaskTypeTraits<Concurrency::task<bool>,0>,0,0>,1>::`vftable'{for `Platform::Object's `Windows::Foundation::IAsyncOperation<bool>'}
0x18008025f  mov     [r14+8], rax
0x180080263  lea     rax, ??_7?$_AsyncInfoBase@U?$_AsyncAttributes@X_NU?$_TaskTypeTraits@V?$task@_N@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00@details@Concurrency@@6BIAsyncInfo@Foundation@Windows@@@; const Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,bool,Concurrency::details::_TaskTypeTraits<Concurrency::task<bool>,0>,0,0>,1>::`vftable'{for `Windows::Foundation::IAsyncInfo'}
0x18008026a  mov     [r14+10h], rax
0x18008026e  lea     rax, ??_7?$_AsyncInfoBase@U?$_AsyncAttributes@X_NU?$_TaskTypeTraits@V?$task@_N@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00@details@Concurrency@@6BObject@Platform@@@; const Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,bool,Concurrency::details::_TaskTypeTraits<Concurrency::task<bool>,0>,0,0>,1>::`vftable'{for `Platform::Object'}
0x180080275  mov     [rbx], rax
0x180080278  mov     qword ptr [r14+20h], 0
0x180080280  mov     qword ptr [r14+28h], 0
0x180080288  mov     dword ptr [r14+30h], 0FFFFFFFFh
0x180080290  mov     dword ptr [r14+34h], 0
0x180080298  mov     dword ptr [r14+3Ch], 0
0x1800802a0  mov     dword ptr [r14+40h], 0
0x1800802a8  mov     eax, 1
0x1800802ad  lock xadd cs:dword_18013E6D8, eax
0x1800802b5  inc     eax
0x1800802b7  mov     [r14+38h], eax
0x1800802bb  lea     rax, ??_7?$_AsyncProgressBase@U?$_AsyncAttributes@X_NU?$_TaskTypeTraits@V?$task@_N@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$0A@$00@details@Concurrency@@6BObject@Platform@@?$IAsyncOperation@_N@Foundation@Windows@@@; const Concurrency::details::_AsyncProgressBase<Concurrency::details::_AsyncAttributes<void,bool,Concurrency::details::_TaskTypeTraits<Concurrency::task<bool>,0>,0,0>,0,1>::`vftable'{for `Platform::Object's `Windows::Foundation::IAsyncOperation<bool>'}
0x1800802c2  mov     [r14+8], rax
0x1800802c6  lea     rax, ??_7?$_AsyncProgressBase@U?$_AsyncAttributes@X_NU?$_TaskTypeTraits@V?$task@_N@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$0A@$00@details@Concurrency@@6BIAsyncInfo@Foundation@Windows@@@; const Concurrency::details::_AsyncProgressBase<Concurrency::details::_AsyncAttributes<void,bool,Concurrency::details::_TaskTypeTraits<Concurrency::task<bool>,0>,0,0>,0,1>::`vftable'{for `Windows::Foundation::IAsyncInfo'}
0x1800802cd  mov     [r14+10h], rax
0x1800802d1  lea     rax, ??_7?$_AsyncProgressBase@U?$_AsyncAttributes@X_NU?$_TaskTypeTraits@V?$task@_N@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$0A@$00@details@Concurrency@@6BObject@Platform@@@; const Concurrency::details::_AsyncProgressBase<Concurrency::details::_AsyncAttributes<void,bool,Concurrency::details::_TaskTypeTraits<Concurrency::task<bool>,0>,0,0>,0,1>::`vftable'{for `Platform::Object'}
0x1800802d8  mov     [rbx], rax
0x1800802db  lea     rax, off_1801335E0
0x1800802e2  mov     [r15], rax
0x1800802e5  lea     rax, off_180133510
0x1800802ec  mov     [r14], rax
0x1800802ef  lea     rax, off_180133580
0x1800802f6  mov     [r15+10h], rax
0x1800802fa  lea     rax, off_180133460
0x180080301  mov     [r15+18h], rax
0x180080305  lea     rax, off_1801334E0
0x18008030c  mov     [r15+20h], rax
0x180080310  lea     rax, off_180133408
0x180080317  mov     [r15+58h], rax
0x18008031b  lea     rax, off_180133430
0x180080322  mov     [r15+60h], rax
0x180080326  lea     rcx, [r15+210h]
0x18008032d  call    ??0__abi_FTMWeakRefData@@QEAA@PE$AAVObject@Platform@@W4CallbackContext@2@@Z; __abi_FTMWeakRefData::__abi_FTMWeakRefData(Platform::Object *,Platform::CallbackContext)
0x180080332  nop
0x180080333  mov     qword ptr [r15+68h], 0
0x18008033b  mov     qword ptr [r15+70h], 0
0x180080343  lea     rcx, [r15+78h]; this
0x180080347  call    ??0cancellation_token_source@Concurrency@@QEAA@XZ; Concurrency::cancellation_token_source::cancellation_token_source(void)
0x18008034c  nop
0x18008034d  lea     rcx, [r15+80h]; this
0x180080354  mov     rdx, rdi; struct Concurrency::details::_TaskCreationCallstack *
0x180080357  call    ??0_TaskCreationCallstack@details@Concurrency@@QEAA@AEBV012@@Z; Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(Concurrency::details::_TaskCreationCallstack const &)
0x18008035c  nop
0x18008035d  lea     rcx, [r15+0A0h]
0x180080364  mov     rdx, rsi
0x180080367  call    _lambda_1157107cf0b2a02d19dff03d451b4015____lambda_1157107cf0b2a02d19dff03d451b4015_
0x18008036c  nop
0x18008036d  xor     edx, edx
0x18008036f  mov     rcx, r14
0x180080372  call    ?_TransitionToState@?$_AsyncInfoBase@U?$_AsyncAttributes@XXU?$_TaskTypeTraits@V?$task@X@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00@details@Concurrency@@AE$AAA_NW4_AsyncStatusInternal@23@@Z; Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,void,Concurrency::details::_TaskTypeTraits<Concurrency::task<void>,0>,0,0>,1>::_TransitionToState(Concurrency::details::_AsyncStatusInternal)
0x180080377  test    al, al
0x180080379  jz      short loc_18008039F
0x18008037b  mov     rax, [r14]
0x18008037e  mov     rax, [rax+58h]
0x180080382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080387  nop
0x180080388  mov     rax, r15
0x18008038b  mov     rbx, [rsp+48h+arg_8]
0x180080390  mov     rsi, [rsp+48h+arg_10]
0x180080395  add     rsp, 30h
0x180080399  pop     r15
0x18008039b  pop     r14
0x18008039d  pop     rdi
0x18008039e  retn
0x18008039f  mov     ecx, 8000000Dh
0x1800803a4  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x1800803aa  mov     [rsp+48h+var_28], rax
0x1800803af  mov     rcx, rax
0x1800803b2  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800803b7  mov     [rsp+48h+pExceptionObject], rax
0x1800803bc  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x1800803c3  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800803c8  call    _CxxThrowException_0
```
