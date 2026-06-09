# wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18000ed24`
- end: `0x18000edfa`
- name: `?Stop@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `214`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000d670`
- `0x18000dab0`
- `0x18000de50`
- `0x180014ce0`
- `0x180018020`

## callees

- `0x180001730`
- `0x180001ebc`
- `0x18000d404`
- `0x18000df18`
- `0x18000dfec`
- `0x18000e62c`
- `0x18000e970`
- `0x18000ed24`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ed9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ed9c`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1,
        unsigned int a2)
{
  char v4; // bl
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  __int64 v12; // r9
  DWORD v14; // [rsp+60h] [rbp+8h] BYREF
  RTL_SRWLOCK *v15; // [rsp+70h] [rbp+18h] BYREF
  __int64 v16; // [rsp+78h] [rbp+20h] BYREF

  v14 = 0;
  wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v15);
  v4 = wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::System::SysAdminTraceLoggingProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         a2,
         &v14);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v15);
  if ( v4 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v8 = Windows::System::SysAdminTraceLoggingProvider::Provider();
    v9 = (__int64)v8;
    if ( *(_DWORD *)v8 > 5u && (unsigned __int8)tlgKeywordOn(v8, 0x200000000000LL, v6, v7) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v11 = a1[34];
      v14 = CurrentThreadId;
      LODWORD(v15) = a2;
      v16 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (__int64)word_180038F12,
        v11 + 8,
        v12,
        (__int64)&v16,
        (__int64)&v15,
        (__int64)&v14);
    }
  }
  return wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
           a1,
           v5,
           v6,
           v7);
}

```

## disassembly

```asm
0x18000ed24  push    rbx
0x18000ed26  push    rsi
0x18000ed27  push    rdi
0x18000ed28  sub     rsp, 40h
0x18000ed2c  mov     esi, edx
0x18000ed2e  mov     [rsp+58h+arg_0], 0
0x18000ed36  lea     rdx, [rsp+58h+arg_10]
0x18000ed3b  mov     rdi, rcx
0x18000ed3e  call    ?LockExclusive@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000ed43  mov     rcx, [rdi+110h]
0x18000ed4a  lea     r8, [rsp+58h+arg_0]
0x18000ed4f  mov     edx, esi
0x18000ed51  call    ?SetStopResult@?$ActivityData@VSysAdminTraceLoggingProvider@System@Windows@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::System::SysAdminTraceLoggingProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18000ed56  lea     rcx, [rsp+58h+arg_10]
0x18000ed5b  mov     bl, al
0x18000ed5d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000ed62  test    bl, bl
0x18000ed64  jz      short loc_18000ED77
0x18000ed66  mov     rax, [rdi]
0x18000ed69  mov     rcx, rdi
0x18000ed6c  mov     rax, [rax+8]
0x18000ed70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed75  jmp     short loc_18000EDEB
0x18000ed77  call    ?Provider@SysAdminTraceLoggingProvider@System@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::System::SysAdminTraceLoggingProvider::Provider(void)
0x18000ed7c  mov     rbx, rax
0x18000ed7f  mov     ecx, [rax]
0x18000ed81  cmp     ecx, 5
0x18000ed84  jbe     short loc_18000EDEB
0x18000ed86  mov     rdx, 200000000000h
0x18000ed90  mov     rcx, rax
0x18000ed93  call    _tlgKeywordOn
0x18000ed98  test    al, al
0x18000ed9a  jz      short loc_18000EDEB
0x18000ed9c  call    cs:__imp_GetCurrentThreadId
0x18000eda2  mov     r8, [rdi+110h]
0x18000eda9  lea     rdx, word_180038F12
0x18000edb0  mov     [rsp+58h+arg_0], eax
0x18000edb4  add     r8, 8
0x18000edb8  lea     rax, [rsp+58h+arg_0]
0x18000edbd  mov     dword ptr [rsp+58h+arg_10], esi
0x18000edc1  mov     [rsp+58h+var_28], rax
0x18000edc6  mov     rcx, rbx
0x18000edc9  lea     rax, [rsp+58h+arg_10]
0x18000edce  mov     [rsp+58h+arg_18], 1000000h
0x18000edd7  mov     [rsp+58h+var_30], rax
0x18000eddc  lea     rax, [rsp+58h+arg_18]
0x18000ede1  mov     [rsp+58h+var_38], rax
0x18000ede6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000edeb  mov     rcx, rdi
0x18000edee  add     rsp, 40h
0x18000edf2  pop     rdi
0x18000edf3  pop     rsi
0x18000edf4  pop     rbx
0x18000edf5  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
