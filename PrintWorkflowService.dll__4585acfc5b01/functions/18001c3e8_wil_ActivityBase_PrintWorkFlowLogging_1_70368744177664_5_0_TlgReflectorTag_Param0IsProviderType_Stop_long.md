# wil::ActivityBase<PrintWorkFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18001c3e8`
- end: `0x18001c4cb`
- name: `?Stop@?$ActivityBase@VPrintWorkFlowLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `227`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18001ae40`
- `0x18001b100`
- `0x18001dc60`
- `0x18001faa0`

## callees

- `0x1800014bc`
- `0x180001e70`
- `0x18000a074`
- `0x18001b0d4`
- `0x18001b5a8`
- `0x18001b9fc`
- `0x18001c018`
- `0x18001c3e8`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c463`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c463`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<PrintWorkFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
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
  int v11; // [rsp+50h] [rbp+8h] BYREF
  DWORD v12; // [rsp+58h] [rbp+10h] BYREF
  __int64 v13; // [rsp+60h] [rbp+18h] BYREF

  v12 = 0;
  wil::ActivityBase<PrintWorkFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v11);
  v2 = wil::ActivityBase<PrintWorkFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<PrintWorkFlowLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
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
    v6 = PrintWorkFlowLogging::Provider();
    v7 = (__int64)v6;
    if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v9 = a1[34];
      v12 = CurrentThreadId;
      v11 = 0;
      v13 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (__int64)byte_180070553,
        v9 + 8,
        0,
        (__int64)&v13,
        (__int64)&v11,
        (__int64)&v12);
    }
  }
  return wil::ActivityBase<PrintWorkFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
           a1,
           v3,
           v4,
           v5);
}

```

## disassembly

```asm
0x18001c3e8  mov     rax, rsp
0x18001c3eb  mov     [rax+20h], rbx
0x18001c3ef  mov     [rax+10h], edx
0x18001c3f2  push    rdi
0x18001c3f3  sub     rsp, 40h
0x18001c3f7  lea     rdx, [rax+8]
0x18001c3fb  mov     dword ptr [rax+10h], 0
0x18001c402  mov     rdi, rcx
0x18001c405  call    ?LockExclusive@?$ActivityBase@VPrintWorkFlowLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PrintWorkFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001c40a  mov     rcx, [rdi+110h]
0x18001c411  lea     r8, [rsp+48h+arg_8]
0x18001c416  xor     edx, edx
0x18001c418  call    ?SetStopResult@?$ActivityData@VPrintWorkFlowLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPrintWorkFlowLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<PrintWorkFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<PrintWorkFlowLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18001c41d  lea     rcx, [rsp+48h+arg_0]
0x18001c422  mov     bl, al
0x18001c424  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001c429  test    bl, bl
0x18001c42b  jz      short loc_18001C43E
0x18001c42d  mov     rax, [rdi]
0x18001c430  mov     rcx, rdi
0x18001c433  mov     rax, [rax+8]
0x18001c437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c43c  jmp     short loc_18001C4B9
0x18001c43e  call    ?Provider@PrintWorkFlowLogging@@SAPEBU_tlgProvider_t@@XZ; PrintWorkFlowLogging::Provider(void)
0x18001c443  mov     rbx, rax
0x18001c446  mov     ecx, [rax]
0x18001c448  cmp     ecx, 5
0x18001c44b  jbe     short loc_18001C4B9
0x18001c44d  mov     rdx, 400000000000h
0x18001c457  mov     rcx, rax
0x18001c45a  call    _tlgKeywordOn
0x18001c45f  test    al, al
0x18001c461  jz      short loc_18001C4B9
0x18001c463  call    cs:__imp_GetCurrentThreadId
0x18001c469  mov     r8, [rdi+110h]
0x18001c470  lea     rdx, byte_180070553
0x18001c477  mov     [rsp+48h+arg_8], eax
0x18001c47b  add     r8, 8
0x18001c47f  lea     rax, [rsp+48h+arg_8]
0x18001c484  mov     [rsp+48h+arg_0], 0
0x18001c48c  mov     [rsp+48h+var_18], rax
0x18001c491  xor     r9d, r9d
0x18001c494  lea     rax, [rsp+48h+arg_0]
0x18001c499  mov     [rsp+48h+arg_10], 1000000h
0x18001c4a2  mov     [rsp+48h+var_20], rax
0x18001c4a7  mov     rcx, rbx
0x18001c4aa  lea     rax, [rsp+48h+arg_10]
0x18001c4af  mov     [rsp+48h+var_28], rax
0x18001c4b4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001c4b9  mov     rcx, rdi
0x18001c4bc  mov     rbx, [rsp+48h+arg_18]
0x18001c4c1  add     rsp, 40h
0x18001c4c5  pop     rdi
0x18001c4c6  jmp     ?IgnoreCurrentThread@?$ActivityBase@VPrintWorkFlowLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PrintWorkFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
