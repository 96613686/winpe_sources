# wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x1800136d4`
- end: `0x1800137b7`
- name: `?Stop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `227`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180012b2c`
- `0x180012dc8`

## callees

- `0x180001384`
- `0x180001b0c`
- `0x18000a5c4`
- `0x18000db78`
- `0x18000db9c`
- `0x18000e00c`
- `0x18000e408`
- `0x1800136d4`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001374f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001374f`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  char v2; // bl
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  RTL_SRWLOCK *v11; // [rsp+50h] [rbp+8h] BYREF
  DWORD v12; // [rsp+58h] [rbp+10h] BYREF
  __int64 v13; // [rsp+60h] [rbp+18h] BYREF

  v12 = 0;
  wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v11);
  v2 = wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<SharedPCAccountManagerLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         0,
         &v12);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  if ( v2 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v6 = SharedPCAccountManagerLogging::Provider();
    v7 = (__int64)v6;
    if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL, v4, v5) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v9 = a1[34];
      v12 = CurrentThreadId;
      LODWORD(v11) = 0;
      v13 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (__int64)word_18002C882,
        v9 + 8,
        0,
        (__int64)&v13,
        (__int64)&v11,
        (__int64)&v12);
    }
  }
  return wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
           a1,
           v3,
           v4,
           v5);
}

```

## disassembly

```asm
0x1800136d4  mov     rax, rsp
0x1800136d7  mov     [rax+20h], rbx
0x1800136db  mov     [rax+10h], edx
0x1800136de  push    rdi
0x1800136df  sub     rsp, 40h
0x1800136e3  lea     rdx, [rax+8]
0x1800136e7  mov     dword ptr [rax+10h], 0
0x1800136ee  mov     rdi, rcx
0x1800136f1  call    ?LockExclusive@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800136f6  mov     rcx, [rdi+110h]
0x1800136fd  lea     r8, [rsp+48h+arg_8]
0x180013702  xor     edx, edx
0x180013704  call    ?SetStopResult@?$ActivityData@VSharedPCAccountManagerLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<SharedPCAccountManagerLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x180013709  lea     rcx, [rsp+48h+arg_0]
0x18001370e  mov     bl, al
0x180013710  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180013715  test    bl, bl
0x180013717  jz      short loc_18001372A
0x180013719  mov     rax, [rdi]
0x18001371c  mov     rcx, rdi
0x18001371f  mov     rax, [rax+8]
0x180013723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013728  jmp     short loc_1800137A5
0x18001372a  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x18001372f  mov     rbx, rax
0x180013732  mov     ecx, [rax]
0x180013734  cmp     ecx, 5
0x180013737  jbe     short loc_1800137A5
0x180013739  mov     rdx, 400000000000h
0x180013743  mov     rcx, rax
0x180013746  call    _tlgKeywordOn
0x18001374b  test    al, al
0x18001374d  jz      short loc_1800137A5
0x18001374f  call    cs:__imp_GetCurrentThreadId
0x180013755  mov     r8, [rdi+110h]
0x18001375c  lea     rdx, word_18002C882
0x180013763  mov     [rsp+48h+arg_8], eax
0x180013767  add     r8, 8
0x18001376b  lea     rax, [rsp+48h+arg_8]
0x180013770  mov     dword ptr [rsp+48h+arg_0], 0
0x180013778  mov     [rsp+48h+var_18], rax
0x18001377d  xor     r9d, r9d
0x180013780  lea     rax, [rsp+48h+arg_0]
0x180013785  mov     [rsp+48h+arg_10], 1000000h
0x18001378e  mov     [rsp+48h+var_20], rax
0x180013793  mov     rcx, rbx
0x180013796  lea     rax, [rsp+48h+arg_10]
0x18001379b  mov     [rsp+48h+var_28], rax
0x1800137a0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800137a5  mov     rcx, rdi
0x1800137a8  mov     rbx, [rsp+48h+arg_18]
0x1800137ad  add     rsp, 40h
0x1800137b1  pop     rdi
0x1800137b2  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
