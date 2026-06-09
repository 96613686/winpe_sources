# wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18000ee00`
- end: `0x18000eec0`
- name: `?Stop@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `192`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000d810`
- `0x180017f50`

## callees

- `0x180001730`
- `0x18000d404`
- `0x18000df18`
- `0x18000dfec`
- `0x18000e62c`
- `0x18000e970`
- `0x18000ee00`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ee62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ee62`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1,
        unsigned int a2)
{
  char v4; // bl
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  const struct _tlgProvider_t *v8; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v10; // r8
  __int64 v11; // r9
  DWORD v13; // [rsp+60h] [rbp+8h] BYREF
  RTL_SRWLOCK *v14; // [rsp+70h] [rbp+18h] BYREF
  __int64 v15; // [rsp+78h] [rbp+20h] BYREF

  v13 = 0;
  wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v14);
  v4 = wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::System::SysAdminTraceLoggingProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         a2,
         &v13);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v14);
  if ( v4 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v8 = Windows::System::SysAdminTraceLoggingProvider::Provider();
    if ( *(_DWORD *)v8 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v10 = a1[34];
      v13 = CurrentThreadId;
      LODWORD(v14) = a2;
      v15 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v8,
        (__int64)byte_180038D81,
        v10 + 8,
        v11,
        (__int64)&v15,
        (__int64)&v14,
        (__int64)&v13);
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
0x18000ee00  push    rbx
0x18000ee02  push    rsi
0x18000ee03  push    rdi
0x18000ee04  sub     rsp, 40h
0x18000ee08  mov     esi, edx
0x18000ee0a  mov     [rsp+58h+arg_0], 0
0x18000ee12  lea     rdx, [rsp+58h+arg_10]
0x18000ee17  mov     rdi, rcx
0x18000ee1a  call    ?LockExclusive@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000ee1f  mov     rcx, [rdi+110h]
0x18000ee26  lea     r8, [rsp+58h+arg_0]
0x18000ee2b  mov     edx, esi
0x18000ee2d  call    ?SetStopResult@?$ActivityData@VSysAdminTraceLoggingProvider@System@Windows@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::System::SysAdminTraceLoggingProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18000ee32  lea     rcx, [rsp+58h+arg_10]
0x18000ee37  mov     bl, al
0x18000ee39  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000ee3e  test    bl, bl
0x18000ee40  jz      short loc_18000EE53
0x18000ee42  mov     rax, [rdi]
0x18000ee45  mov     rcx, rdi
0x18000ee48  mov     rax, [rax+8]
0x18000ee4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee51  jmp     short loc_18000EEB1
0x18000ee53  call    ?Provider@SysAdminTraceLoggingProvider@System@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::System::SysAdminTraceLoggingProvider::Provider(void)
0x18000ee58  mov     rbx, rax
0x18000ee5b  mov     ecx, [rax]
0x18000ee5d  cmp     ecx, 5
0x18000ee60  jbe     short loc_18000EEB1
0x18000ee62  call    cs:__imp_GetCurrentThreadId
0x18000ee68  mov     r8, [rdi+110h]
0x18000ee6f  lea     rdx, byte_180038D81
0x18000ee76  mov     [rsp+58h+arg_0], eax
0x18000ee7a  add     r8, 8
0x18000ee7e  lea     rax, [rsp+58h+arg_0]
0x18000ee83  mov     dword ptr [rsp+58h+arg_10], esi
0x18000ee87  mov     [rsp+58h+var_28], rax
0x18000ee8c  mov     rcx, rbx
0x18000ee8f  lea     rax, [rsp+58h+arg_10]
0x18000ee94  mov     [rsp+58h+arg_18], 1000000h
0x18000ee9d  mov     [rsp+58h+var_30], rax
0x18000eea2  lea     rax, [rsp+58h+arg_18]
0x18000eea7  mov     [rsp+58h+var_38], rax
0x18000eeac  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000eeb1  mov     rcx, rdi
0x18000eeb4  add     rsp, 40h
0x18000eeb8  pop     rdi
0x18000eeb9  pop     rsi
0x18000eeba  pop     rbx
0x18000eebb  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
