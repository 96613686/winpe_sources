# Concurrency::details::_AsyncTaskGeneratorThunk__lambda_b9654745adfaedd88133fd01f810f6ba___::_AsyncTaskGeneratorThunk__lambda_b9654745adfaedd88133fd01f810f6ba___

- ea: `0x1800d299c`
- end: `0x1800d2b53`
- name: `Concurrency::details::_AsyncTaskGeneratorThunk__lambda_b9654745adfaedd88133fd01f810f6ba___::_AsyncTaskGeneratorThunk__lambda_b9654745adfaedd88133fd01f810f6ba___`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x1800d243c`

## callees

- `0x180005e50`
- `0x18003a724`
- `0x18003feb4`
- `0x180081484`
- `0x1800816fc`
- `0x18008f9a4`
- `0x1800d299c`
- `0x1800fb010`

## import_xrefs

- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x1800d2b29`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x1800d2b29`
- `wincorlib!??0Object@Platform@@QE$AAA@XZ` at `0x1800d29c0`
- `wincorlib!??0Object@Platform@@QE$AAA@XZ` at `0x1800d29c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall Concurrency::details::_AsyncTaskGeneratorThunk__lambda_b9654745adfaedd88133fd01f810f6ba___::_AsyncTaskGeneratorThunk__lambda_b9654745adfaedd88133fd01f810f6ba___(
        _QWORD *a1,
        _QWORD *a2,
        const struct Concurrency::details::_TaskCreationCallstack *a3)
{
  _QWORD *v6; // r14
  _QWORD *v7; // rbx
  __int64 pExceptionObject; // [rsp+58h] [rbp+10h] BYREF
  __int64 Exception; // [rsp+68h] [rbp+20h]

  v6 = a1 + 1;
  v7 = a1 + 4;
  Platform::Object::Object(a1 + 4);
  *v6 = &___7___AsyncInfoBase_U___AsyncAttributes_XPE_AAU__IVectorView_PE_AAUISettingResultItem_Search_ConstraintIndex_Cortana___Collections_Foundation_Windows__U___TaskTypeTraits_V__task_PE_AAU__IVectorView_PE_AAUISettingResultItem_Search_ConstraintIndex_Cortana___Collections_Foundation_Windows___Concurrency___0A__details_Concurrency___00_0A__details_Concurrency___00_details_Concurrency__6B__I___AsyncInfoBase_U___AsyncAttributes_XPE_AAU__IVectorView_PE_AAUISettingResultItem_Search_ConstraintIndex_Cortana___Collections_Foundation_Windows__U___TaskTypeTraits_V__task_PE_AAU__IVectorView_PE_AAUISettingResultItem_Search_ConstraintIndex_Cortana___Collections_Foundation_Windows___Concurrency___0A__details_Concurrency___00_0A__details_Concurrency___00PublicNonVirtuals_12__;
  v6[1] = &Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *> __gc *,Concurrency::details::_TaskTypeTraits<Concurrency::task<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *> __gc *>,0>,1,0>,1>::`vftable'{for `Platform::Object's `Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *> __gc *>'};
  v6[2] = &Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *> __gc *,Concurrency::details::_TaskTypeTraits<Concurrency::task<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *> __gc *>,0>,1,0>,1>::`vftable'{for `Windows::Foundation::IAsyncInfo'};
  *v7 = &Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *> __gc *,Concurrency::details::_TaskTypeTraits<Concurrency::task<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *> __gc *>,0>,1,0>,1>::`vftable'{for `Platform::Object'};
  v6[4] = 0;
  v6[5] = 0;
  *((_DWORD *)v6 + 12) = -1;
  *((_DWORD *)v6 + 13) = 0;
  *((_DWORD *)v6 + 15) = 0;
  *((_DWORD *)v6 + 16) = 0;
  *((_DWORD *)v6 + 14) = _InterlockedIncrement(&dword_18013E6D8);
  v6[1] = &Concurrency::details::_AsyncProgressBase<Concurrency::details::_AsyncAttributes<void,Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *> __gc *,Concurrency::details::_TaskTypeTraits<Concurrency::task<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *> __gc *>,0>,1,0>,0,1>::`vftable'{for `Platform::Object's `Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *> __gc *>'};
  v6[2] = &Concurrency::details::_AsyncProgressBase<Concurrency::details::_AsyncAttributes<void,Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *> __gc *,Concurrency::details::_TaskTypeTraits<Concurrency::task<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *> __gc *>,0>,1,0>,0,1>::`vftable'{for `Windows::Foundation::IAsyncInfo'};
  *v7 = &Concurrency::details::_AsyncProgressBase<Concurrency::details::_AsyncAttributes<void,Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *> __gc *,Concurrency::details::_TaskTypeTraits<Concurrency::task<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *> __gc *>,0>,1,0>,0,1>::`vftable'{for `Platform::Object'};
  *a1 = &off_18013A260;
  *v6 = off_18013A0E0;
  a1[2] = off_18013A150;
  a1[3] = off_18013A1B0;
  a1[4] = off_18013A230;
  a1[11] = off_18013A028;
  a1[12] = off_18013A050;
  __abi_FTMWeakRefData::__abi_FTMWeakRefData(a1 + 23);
  a1[13] = 0;
  a1[14] = 0;
  Concurrency::cancellation_token_source::cancellation_token_source((Concurrency::cancellation_token_source *)(a1 + 15));
  Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(
    (Concurrency::details::_TaskCreationCallstack *)(a1 + 16),
    a3);
  a1[20] = __abi_winrt_ptr_ctor(*a2);
  a1[21] = a2[1];
  a1[22] = a2[2];
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
0x1800d299c  mov     [rsp+arg_0], rcx
0x1800d29a1  push    rbx
0x1800d29a2  push    rsi
0x1800d29a3  push    rdi
0x1800d29a4  push    r14
0x1800d29a6  push    r15
0x1800d29a8  sub     rsp, 20h
0x1800d29ac  mov     rdi, r8
0x1800d29af  mov     rsi, rdx
0x1800d29b2  mov     r15, rcx
0x1800d29b5  lea     r14, [rcx+8]
0x1800d29b9  lea     rbx, [r14+18h]
0x1800d29bd  mov     rcx, rbx
0x1800d29c0  call    cs:__imp_??0Object@Platform@@QE$AAA@XZ; Platform::Object::Object(void)
0x1800d29c6  lea     rax, ??_7?$_AsyncInfoBase@U?$_AsyncAttributes@XPE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@U?$_TaskTypeTraits@V?$task@PE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@@Concurrency@@$0A@@details@Concurrency@@$00$0A@@details@Concurrency@@$00@details@Concurrency@@6B__I?$_AsyncInfoBase@U?$_AsyncAttributes@XPE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@U?$_TaskTypeTraits@V?$task@PE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@@Concurrency@@$0A@@details@Concurrency@@$00$0A@@details@Concurrency@@$00PublicNonVirtuals@12@@
0x1800d29cd  mov     [r14], rax
0x1800d29d0  lea     rax, ??_7?$_AsyncInfoBase@U?$_AsyncAttributes@XPE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@U?$_TaskTypeTraits@V?$task@PE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@@Concurrency@@$0A@@details@Concurrency@@$00$0A@@details@Concurrency@@$00@details@Concurrency@@6BObject@Platform@@?$IAsyncOperation@PE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@@Foundation@Windows@@@; const Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem *> *,Concurrency::details::_TaskTypeTraits<Concurrency::task<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem *> *>,0>,1,0>,1>::`vftable'{for `Platform::Object's `Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem *> *>'}
0x1800d29d7  mov     [r14+8], rax
0x1800d29db  lea     rax, ??_7?$_AsyncInfoBase@U?$_AsyncAttributes@XPE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@U?$_TaskTypeTraits@V?$task@PE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@@Concurrency@@$0A@@details@Concurrency@@$00$0A@@details@Concurrency@@$00@details@Concurrency@@6BIAsyncInfo@Foundation@Windows@@@; const Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem *> *,Concurrency::details::_TaskTypeTraits<Concurrency::task<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem *> *>,0>,1,0>,1>::`vftable'{for `Windows::Foundation::IAsyncInfo'}
0x1800d29e2  mov     [r14+10h], rax
0x1800d29e6  lea     rax, ??_7?$_AsyncInfoBase@U?$_AsyncAttributes@XPE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@U?$_TaskTypeTraits@V?$task@PE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@@Concurrency@@$0A@@details@Concurrency@@$00$0A@@details@Concurrency@@$00@details@Concurrency@@6BObject@Platform@@@; const Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem *> *,Concurrency::details::_TaskTypeTraits<Concurrency::task<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem *> *>,0>,1,0>,1>::`vftable'{for `Platform::Object'}
0x1800d29ed  mov     [rbx], rax
0x1800d29f0  mov     qword ptr [r14+20h], 0
0x1800d29f8  mov     qword ptr [r14+28h], 0
0x1800d2a00  mov     dword ptr [r14+30h], 0FFFFFFFFh
0x1800d2a08  mov     dword ptr [r14+34h], 0
0x1800d2a10  mov     dword ptr [r14+3Ch], 0
0x1800d2a18  mov     dword ptr [r14+40h], 0
0x1800d2a20  mov     eax, 1
0x1800d2a25  lock xadd cs:dword_18013E6D8, eax
0x1800d2a2d  inc     eax
0x1800d2a2f  mov     [r14+38h], eax
0x1800d2a33  lea     rax, ??_7?$_AsyncProgressBase@U?$_AsyncAttributes@XPE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@U?$_TaskTypeTraits@V?$task@PE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@@Concurrency@@$0A@@details@Concurrency@@$00$0A@@details@Concurrency@@$0A@$00@details@Concurrency@@6BObject@Platform@@?$IAsyncOperation@PE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@@Foundation@Windows@@@; const Concurrency::details::_AsyncProgressBase<Concurrency::details::_AsyncAttributes<void,Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem *> *,Concurrency::details::_TaskTypeTraits<Concurrency::task<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem *> *>,0>,1,0>,0,1>::`vftable'{for `Platform::Object's `Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem *> *>'}
0x1800d2a3a  mov     [r14+8], rax
0x1800d2a3e  lea     rax, ??_7?$_AsyncProgressBase@U?$_AsyncAttributes@XPE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@U?$_TaskTypeTraits@V?$task@PE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@@Concurrency@@$0A@@details@Concurrency@@$00$0A@@details@Concurrency@@$0A@$00@details@Concurrency@@6BIAsyncInfo@Foundation@Windows@@@; const Concurrency::details::_AsyncProgressBase<Concurrency::details::_AsyncAttributes<void,Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem *> *,Concurrency::details::_TaskTypeTraits<Concurrency::task<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem *> *>,0>,1,0>,0,1>::`vftable'{for `Windows::Foundation::IAsyncInfo'}
0x1800d2a45  mov     [r14+10h], rax
0x1800d2a49  lea     rax, ??_7?$_AsyncProgressBase@U?$_AsyncAttributes@XPE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@U?$_TaskTypeTraits@V?$task@PE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@@Concurrency@@$0A@@details@Concurrency@@$00$0A@@details@Concurrency@@$0A@$00@details@Concurrency@@6BObject@Platform@@@; const Concurrency::details::_AsyncProgressBase<Concurrency::details::_AsyncAttributes<void,Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem *> *,Concurrency::details::_TaskTypeTraits<Concurrency::task<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem *> *>,0>,1,0>,0,1>::`vftable'{for `Platform::Object'}
0x1800d2a50  mov     [rbx], rax
0x1800d2a53  lea     rax, off_18013A260
0x1800d2a5a  mov     [r15], rax
0x1800d2a5d  lea     rax, off_18013A0E0
0x1800d2a64  mov     [r14], rax
0x1800d2a67  lea     rax, off_18013A150
0x1800d2a6e  mov     [r15+10h], rax
0x1800d2a72  lea     rax, off_18013A1B0
0x1800d2a79  mov     [r15+18h], rax
0x1800d2a7d  lea     rax, off_18013A230
0x1800d2a84  mov     [r15+20h], rax
0x1800d2a88  lea     rax, off_18013A028
0x1800d2a8f  mov     [r15+58h], rax
0x1800d2a93  lea     rax, off_18013A050
0x1800d2a9a  mov     [r15+60h], rax
0x1800d2a9e  lea     rcx, [r15+0B8h]
0x1800d2aa5  call    ??0__abi_FTMWeakRefData@@QEAA@PE$AAVObject@Platform@@W4CallbackContext@2@@Z; __abi_FTMWeakRefData::__abi_FTMWeakRefData(Platform::Object *,Platform::CallbackContext)
0x1800d2aaa  nop
0x1800d2aab  mov     qword ptr [r15+68h], 0
0x1800d2ab3  mov     qword ptr [r15+70h], 0
0x1800d2abb  lea     rcx, [r15+78h]; this
0x1800d2abf  call    ??0cancellation_token_source@Concurrency@@QEAA@XZ; Concurrency::cancellation_token_source::cancellation_token_source(void)
0x1800d2ac4  nop
0x1800d2ac5  lea     rcx, [r15+80h]; this
0x1800d2acc  mov     rdx, rdi; struct Concurrency::details::_TaskCreationCallstack *
0x1800d2acf  call    ??0_TaskCreationCallstack@details@Concurrency@@QEAA@AEBV012@@Z; Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(Concurrency::details::_TaskCreationCallstack const &)
0x1800d2ad4  nop
0x1800d2ad5  mov     rcx, [rsi]
0x1800d2ad8  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800d2add  mov     [r15+0A0h], rax
0x1800d2ae4  mov     rax, [rsi+8]
0x1800d2ae8  mov     [r15+0A8h], rax
0x1800d2aef  mov     rax, [rsi+10h]
0x1800d2af3  mov     [r15+0B0h], rax
0x1800d2afa  xor     edx, edx
0x1800d2afc  mov     rcx, r14
0x1800d2aff  call    ?_TransitionToState@?$_AsyncInfoBase@U?$_AsyncAttributes@XXU?$_TaskTypeTraits@V?$task@X@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00@details@Concurrency@@AE$AAA_NW4_AsyncStatusInternal@23@@Z; Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,void,Concurrency::details::_TaskTypeTraits<Concurrency::task<void>,0>,0,0>,1>::_TransitionToState(Concurrency::details::_AsyncStatusInternal)
0x1800d2b04  test    al, al
0x1800d2b06  jz      short loc_1800D2B24
0x1800d2b08  mov     rax, [r14]
0x1800d2b0b  mov     rax, [rax+58h]
0x1800d2b0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2b14  nop
0x1800d2b15  mov     rax, r15
0x1800d2b18  add     rsp, 20h
0x1800d2b1c  pop     r15
0x1800d2b1e  pop     r14
0x1800d2b20  pop     rdi
0x1800d2b21  pop     rsi
0x1800d2b22  pop     rbx
0x1800d2b23  retn
0x1800d2b24  mov     ecx, 8000000Dh
0x1800d2b29  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x1800d2b2f  mov     [rsp+48h+arg_18], rax
0x1800d2b34  mov     rcx, rax
0x1800d2b37  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800d2b3c  mov     [rsp+48h+pExceptionObject], rax
0x1800d2b41  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x1800d2b48  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800d2b4d  call    _CxxThrowException_0
```
