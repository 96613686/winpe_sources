# ?Close@?QIAsyncInfo@Foundation@Windows@@?$_AsyncInfoBase@U?$_AsyncAttributes@XPE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@U?$_TaskTypeTraits@V?$task@PE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@@Concurrency@@$0A@@details@Concurrency@@$00$0A@@details@Concurrency@@$00@details@Concurrency@@UE$AAAXXZ

- ea: `0x1800869d8`
- end: `0x180086a31`
- name: `?Close@?QIAsyncInfo@Foundation@Windows@@?$_AsyncInfoBase@U?$_AsyncAttributes@XPE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@U?$_TaskTypeTraits@V?$task@PE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@@Concurrency@@$0A@@details@Concurrency@@$00$0A@@details@Concurrency@@$00@details@Concurrency@@UE$AAAXXZ`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180086a40`

## callees

- `0x180005e50`
- `0x18003feb4`
- `0x1800869d8`
- `0x18008f9a4`
- `0x1800fb010`

## import_xrefs

- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x180086a07`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x180086a07`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _Close__QIAsyncInfo_Foundation_Windows_____AsyncInfoBase_U___AsyncAttributes_XPE_AAU__IVectorView_PE_AAUISettingResultItem_Search_ConstraintIndex_Cortana___Collections_Foundation_Windows__U___TaskTypeTraits_V__task_PE_AAU__IVectorView_PE_AAUISettingResultItem_Search_ConstraintIndex_Cortana___Collections_Foundation_Windows___Concurrency___0A__details_Concurrency___00_0A__details_Concurrency___00_details_Concurrency__UE_AAAXXZ(
        __int64 a1)
{
  int v1; // edx
  unsigned int *v2; // rcx
  __int64 result; // rax
  __int64 pExceptionObject; // [rsp+38h] [rbp+10h] BYREF
  __int64 Exception; // [rsp+40h] [rbp+18h]

  if ( (unsigned __int8)Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,void,Concurrency::details::_TaskTypeTraits<Concurrency::task<void>,0>,0,0>,1>::_TransitionToState(
                          a1,
                          5) )
    return (*(__int64 (__fastcall **)(unsigned int *))(*(_QWORD *)v2 + 96LL))(v2);
  result = v2[12];
  if ( (_DWORD)result != v1 )
  {
    Exception = Platform::Exception::CreateException(2147483661LL);
    pExceptionObject = __abi_winrt_ptr_ctor(Exception);
    throw (Platform::Exception **)&pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x1800869d8  sub     rsp, 28h
0x1800869dc  mov     edx, 5
0x1800869e1  call    ?_TransitionToState@?$_AsyncInfoBase@U?$_AsyncAttributes@XXU?$_TaskTypeTraits@V?$task@X@Concurrency@@$0A@@details@Concurrency@@$0A@$0A@@details@Concurrency@@$00@details@Concurrency@@AE$AAA_NW4_AsyncStatusInternal@23@@Z; Concurrency::details::_AsyncInfoBase<Concurrency::details::_AsyncAttributes<void,void,Concurrency::details::_TaskTypeTraits<Concurrency::task<void>,0>,0,0>,1>::_TransitionToState(Concurrency::details::_AsyncStatusInternal)
0x1800869e6  test    al, al
0x1800869e8  jz      short loc_1800869FB
0x1800869ea  mov     rax, [rcx]
0x1800869ed  mov     rax, [rax+60h]
0x1800869f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800869f6  add     rsp, 28h
0x1800869fa  retn
0x1800869fb  mov     eax, [rcx+30h]
0x1800869fe  cmp     eax, edx
0x180086a00  jz      short loc_1800869F6
0x180086a02  mov     ecx, 8000000Dh
0x180086a07  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x180086a0d  mov     [rsp+28h+arg_10], rax
0x180086a12  mov     rcx, rax
0x180086a15  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x180086a1a  mov     [rsp+28h+pExceptionObject], rax
0x180086a1f  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x180086a26  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180086a2b  call    _CxxThrowException_0
```
