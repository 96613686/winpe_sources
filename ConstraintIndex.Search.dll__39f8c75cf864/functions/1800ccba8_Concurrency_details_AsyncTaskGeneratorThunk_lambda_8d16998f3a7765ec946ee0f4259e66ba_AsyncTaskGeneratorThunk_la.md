# Concurrency::details::_AsyncTaskGeneratorThunk__lambda_8d16998f3a7765ec946ee0f4259e66ba___::_AsyncTaskGeneratorThunk__lambda_8d16998f3a7765ec946ee0f4259e66ba___

- ea: `0x1800ccba8`
- end: `0x1800ccd5a`
- name: `Concurrency::details::_AsyncTaskGeneratorThunk__lambda_8d16998f3a7765ec946ee0f4259e66ba___::_AsyncTaskGeneratorThunk__lambda_8d16998f3a7765ec946ee0f4259e66ba___`
- size: `434`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x1800cbf5c`

## callees

- `0x180005e50`
- `0x18003a724`
- `0x18003feb4`
- `0x180081484`
- `0x1800816fc`
- `0x18008f9a4`
- `0x1800cc834`
- `0x1800ccba8`
- `0x1800fb010`

## import_xrefs

- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x1800ccd30`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x1800ccd30`
- `wincorlib!??0Object@Platform@@QE$AAA@XZ` at `0x1800ccbd4`
- `wincorlib!??0Object@Platform@@QE$AAA@XZ` at `0x1800ccbd4`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall Concurrency::details::_AsyncTaskGeneratorThunk__lambda_8d16998f3a7765ec946ee0f4259e66ba___::_AsyncTaskGeneratorThunk__lambda_8d16998f3a7765ec946ee0f4259e66ba___(
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
  *v6 = &___7___AsyncInfoBase_U___AsyncAttributes_XPE_AAVString_Platform__U___TaskTypeTraits_V__task_PE_AAVString_Platform___Concurrency___0A__details_Concurrency___0A__0A__details_Concurrency___00_details_Concurrency__6B__I___AsyncInfoBase_U___AsyncAttributes_XPE_AAVString_Platform__U___TaskTypeTraits_V__task_PE_AAVString_Platform___Concurrency___0A__details_Concurrency___0A__0A__details_Concurrency___00PublicNonVirtuals_12__;
  v6[1] = &Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,Platform::String __gc *,Concurrency::details::_TaskTypeTraits<Concurrency::task<Platform::String __gc *>,0>,0,0>,1>::`vftable'{for `Platform::Object's `Windows::Foundation::IAsyncOperation<Platform::String __gc *>'};
  v6[2] = &Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,Platform::String __gc *,Concurrency::details::_TaskTypeTraits<Concurrency::task<Platform::String __gc *>,0>,0,0>,1>::`vftable'{for `Windows::Foundation::IAsyncInfo'};
  *v7 = &Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,Platform::String __gc *,Concurrency::details::_TaskTypeTraits<Concurrency::task<Platform::String __gc *>,0>,0,0>,1>::`vftable'{for `Platform::Object'};
  v6[4] = 0;
  v6[5] = 0;
  *((_DWORD *)v6 + 12) = -1;
  *((_DWORD *)v6 + 13) = 0;
  *((_DWORD *)v6 + 15) = 0;
  *((_DWORD *)v6 + 16) = 0;
  *((_DWORD *)v6 + 14) = _InterlockedIncrement(&dword_18013E6D8);
  v6[1] = &Concurrency::details::_AsyncProgressBase<Concurrency::details::_AsyncAttributes<void,Platform::String __gc *,Concurrency::details::_TaskTypeTraits<Concurrency::task<Platform::String __gc *>,0>,0,0>,0,1>::`vftable'{for `Platform::Object's `Windows::Foundation::IAsyncOperation<Platform::String __gc *>'};
  v6[2] = &Concurrency::details::_AsyncProgressBase<Concurrency::details::_AsyncAttributes<void,Platform::String __gc *,Concurrency::details::_TaskTypeTraits<Concurrency::task<Platform::String __gc *>,0>,0,0>,0,1>::`vftable'{for `Windows::Foundation::IAsyncInfo'};
  *v7 = &Concurrency::details::_AsyncProgressBase<Concurrency::details::_AsyncAttributes<void,Platform::String __gc *,Concurrency::details::_TaskTypeTraits<Concurrency::task<Platform::String __gc *>,0>,0,0>,0,1>::`vftable'{for `Platform::Object'};
  *a1 = &off_1801393C0;
  *v6 = off_1801393F0;
  a1[2] = off_180139288;
  a1[3] = off_1801392E8;
  a1[4] = off_180139368;
  a1[11] = off_180139398;
  a1[12] = off_180139178;
  __abi_FTMWeakRefData::__abi_FTMWeakRefData(a1 + 63);
  a1[13] = 0;
  a1[14] = 0;
  Concurrency::cancellation_token_source::cancellation_token_source((Concurrency::cancellation_token_source *)(a1 + 15));
  Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(
    (Concurrency::details::_TaskCreationCallstack *)(a1 + 16),
    a3);
  lambda_8d16998f3a7765ec946ee0f4259e66ba_::_lambda_8d16998f3a7765ec946ee0f4259e66ba_(a1 + 20, a2);
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
0x1800ccba8  mov     [rsp+arg_8], rbx
0x1800ccbad  mov     [rsp+arg_10], rsi
0x1800ccbb2  mov     [rsp+arg_0], rcx
0x1800ccbb7  push    rdi
0x1800ccbb8  push    r14
0x1800ccbba  push    r15
0x1800ccbbc  sub     rsp, 30h
0x1800ccbc0  mov     rdi, r8
0x1800ccbc3  mov     rsi, rdx
0x1800ccbc6  mov     r15, rcx
0x1800ccbc9  lea     r14, [rcx+8]
0x1800ccbcd  lea     rbx, [r14+18h]
0x1800ccbd1  mov     rcx, rbx
0x1800ccbd4  call    cs:__imp_??0Object@Platform@@QE$AAA@XZ; Platform::Object::Object(void)
0x1800ccbda  lea     rax, ??_7?$_AsyncInfoBase@U?$_AsyncAttributes@XPE$AAVString@Platform@@U?$_TaskTypeTraits@V?$task@PE$AAVString@Platform@@@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00@details@Concurrency@@6B__I?$_AsyncInfoBase@U?$_AsyncAttributes@XPE$AAVString@Platform@@U?$_TaskTypeTraits@V?$task@PE$AAVString@Platform@@@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00PublicNonVirtuals@12@@
0x1800ccbe1  mov     [r14], rax
0x1800ccbe4  lea     rax, ??_7?$_AsyncInfoBase@U?$_AsyncAttributes@XPE$AAVString@Platform@@U?$_TaskTypeTraits@V?$task@PE$AAVString@Platform@@@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00@details@Concurrency@@6BObject@Platform@@?$IAsyncOperation@PE$AAVString@Platform@@@Foundation@Windows@@@; const Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,Platform::String *,Concurrency::details::_TaskTypeTraits<Concurrency::task<Platform::String *>,0>,0,0>,1>::`vftable'{for `Platform::Object's `Windows::Foundation::IAsyncOperation<Platform::String *>'}
0x1800ccbeb  mov     [r14+8], rax
0x1800ccbef  lea     rax, ??_7?$_AsyncInfoBase@U?$_AsyncAttributes@XPE$AAVString@Platform@@U?$_TaskTypeTraits@V?$task@PE$AAVString@Platform@@@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00@details@Concurrency@@6BIAsyncInfo@Foundation@Windows@@@; const Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,Platform::String *,Concurrency::details::_TaskTypeTraits<Concurrency::task<Platform::String *>,0>,0,0>,1>::`vftable'{for `Windows::Foundation::IAsyncInfo'}
0x1800ccbf6  mov     [r14+10h], rax
0x1800ccbfa  lea     rax, ??_7?$_AsyncInfoBase@U?$_AsyncAttributes@XPE$AAVString@Platform@@U?$_TaskTypeTraits@V?$task@PE$AAVString@Platform@@@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00@details@Concurrency@@6BObject@Platform@@@; const Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,Platform::String *,Concurrency::details::_TaskTypeTraits<Concurrency::task<Platform::String *>,0>,0,0>,1>::`vftable'{for `Platform::Object'}
0x1800ccc01  mov     [rbx], rax
0x1800ccc04  mov     qword ptr [r14+20h], 0
0x1800ccc0c  mov     qword ptr [r14+28h], 0
0x1800ccc14  mov     dword ptr [r14+30h], 0FFFFFFFFh
0x1800ccc1c  mov     dword ptr [r14+34h], 0
0x1800ccc24  mov     dword ptr [r14+3Ch], 0
0x1800ccc2c  mov     dword ptr [r14+40h], 0
0x1800ccc34  mov     eax, 1
0x1800ccc39  lock xadd cs:dword_18013E6D8, eax
0x1800ccc41  inc     eax
0x1800ccc43  mov     [r14+38h], eax
0x1800ccc47  lea     rax, ??_7?$_AsyncProgressBase@U?$_AsyncAttributes@XPE$AAVString@Platform@@U?$_TaskTypeTraits@V?$task@PE$AAVString@Platform@@@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$0A@$00@details@Concurrency@@6BObject@Platform@@?$IAsyncOperation@PE$AAVString@Platform@@@Foundation@Windows@@@; const Concurrency::details::_AsyncProgressBase<Concurrency::details::_AsyncAttributes<void,Platform::String *,Concurrency::details::_TaskTypeTraits<Concurrency::task<Platform::String *>,0>,0,0>,0,1>::`vftable'{for `Platform::Object's `Windows::Foundation::IAsyncOperation<Platform::String *>'}
0x1800ccc4e  mov     [r14+8], rax
0x1800ccc52  lea     rax, ??_7?$_AsyncProgressBase@U?$_AsyncAttributes@XPE$AAVString@Platform@@U?$_TaskTypeTraits@V?$task@PE$AAVString@Platform@@@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$0A@$00@details@Concurrency@@6BIAsyncInfo@Foundation@Windows@@@; const Concurrency::details::_AsyncProgressBase<Concurrency::details::_AsyncAttributes<void,Platform::String *,Concurrency::details::_TaskTypeTraits<Concurrency::task<Platform::String *>,0>,0,0>,0,1>::`vftable'{for `Windows::Foundation::IAsyncInfo'}
0x1800ccc59  mov     [r14+10h], rax
0x1800ccc5d  lea     rax, ??_7?$_AsyncProgressBase@U?$_AsyncAttributes@XPE$AAVString@Platform@@U?$_TaskTypeTraits@V?$task@PE$AAVString@Platform@@@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$0A@$00@details@Concurrency@@6BObject@Platform@@@; const Concurrency::details::_AsyncProgressBase<Concurrency::details::_AsyncAttributes<void,Platform::String *,Concurrency::details::_TaskTypeTraits<Concurrency::task<Platform::String *>,0>,0,0>,0,1>::`vftable'{for `Platform::Object'}
0x1800ccc64  mov     [rbx], rax
0x1800ccc67  lea     rax, off_1801393C0
0x1800ccc6e  mov     [r15], rax
0x1800ccc71  lea     rax, off_1801393F0
0x1800ccc78  mov     [r14], rax
0x1800ccc7b  lea     rax, off_180139288
0x1800ccc82  mov     [r15+10h], rax
0x1800ccc86  lea     rax, off_1801392E8
0x1800ccc8d  mov     [r15+18h], rax
0x1800ccc91  lea     rax, off_180139368
0x1800ccc98  mov     [r15+20h], rax
0x1800ccc9c  lea     rax, off_180139398
0x1800ccca3  mov     [r15+58h], rax
0x1800ccca7  lea     rax, off_180139178
0x1800cccae  mov     [r15+60h], rax
0x1800cccb2  lea     rcx, [r15+1F8h]
0x1800cccb9  call    ??0__abi_FTMWeakRefData@@QEAA@PE$AAVObject@Platform@@W4CallbackContext@2@@Z; __abi_FTMWeakRefData::__abi_FTMWeakRefData(Platform::Object *,Platform::CallbackContext)
0x1800cccbe  nop
0x1800cccbf  mov     qword ptr [r15+68h], 0
0x1800cccc7  mov     qword ptr [r15+70h], 0
0x1800ccccf  lea     rcx, [r15+78h]; this
0x1800cccd3  call    ??0cancellation_token_source@Concurrency@@QEAA@XZ; Concurrency::cancellation_token_source::cancellation_token_source(void)
0x1800cccd8  nop
0x1800cccd9  lea     rcx, [r15+80h]; this
0x1800ccce0  mov     rdx, rdi; struct Concurrency::details::_TaskCreationCallstack *
0x1800ccce3  call    ??0_TaskCreationCallstack@details@Concurrency@@QEAA@AEBV012@@Z; Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(Concurrency::details::_TaskCreationCallstack const &)
0x1800ccce8  nop
0x1800ccce9  lea     rcx, [r15+0A0h]
0x1800cccf0  mov     rdx, rsi
0x1800cccf3  call    _lambda_8d16998f3a7765ec946ee0f4259e66ba____lambda_8d16998f3a7765ec946ee0f4259e66ba_
0x1800cccf8  nop
0x1800cccf9  xor     edx, edx
0x1800cccfb  mov     rcx, r14
0x1800cccfe  call    ?_TransitionToState@?$_AsyncInfoBase@U?$_AsyncAttributes@XXU?$_TaskTypeTraits@V?$task@X@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00@details@Concurrency@@AE$AAA_NW4_AsyncStatusInternal@23@@Z; Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,void,Concurrency::details::_TaskTypeTraits<Concurrency::task<void>,0>,0,0>,1>::_TransitionToState(Concurrency::details::_AsyncStatusInternal)
0x1800ccd03  test    al, al
0x1800ccd05  jz      short loc_1800CCD2B
0x1800ccd07  mov     rax, [r14]
0x1800ccd0a  mov     rax, [rax+58h]
0x1800ccd0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ccd13  nop
0x1800ccd14  mov     rax, r15
0x1800ccd17  mov     rbx, [rsp+48h+arg_8]
0x1800ccd1c  mov     rsi, [rsp+48h+arg_10]
0x1800ccd21  add     rsp, 30h
0x1800ccd25  pop     r15
0x1800ccd27  pop     r14
0x1800ccd29  pop     rdi
0x1800ccd2a  retn
0x1800ccd2b  mov     ecx, 8000000Dh
0x1800ccd30  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x1800ccd36  mov     [rsp+48h+var_28], rax
0x1800ccd3b  mov     rcx, rax
0x1800ccd3e  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800ccd43  mov     [rsp+48h+pExceptionObject], rax
0x1800ccd48  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x1800ccd4f  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800ccd54  call    _CxxThrowException_0
```
