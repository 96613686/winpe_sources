# wil::ActivityBase<WorkAccessLogger,1,140737488355328,5,33554432,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x1800285c8`
- end: `0x1800286a4`
- name: `?Stop@?$ActivityBase@VWorkAccessLogger@@$00$0IAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `220`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180023db4`
- `0x180023f0c`
- `0x180024238`
- `0x1800266b0`
- `0x1800268e0`
- `0x180026ac0`
- `0x180040288`
- `0x180040734`
- `0x180040c40`
- `0x1800419b0`
- `0x1800421f0`

## callees

- `0x180001e50`
- `0x18000206c`
- `0x180005544`
- `0x18000c4cc`
- `0x180026558`
- `0x1800271c8`
- `0x180027b40`
- `0x1800285c8`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028640`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028640`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<WorkAccessLogger,1,140737488355328,5,33554432,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1,
        unsigned int a2)
{
  char v4; // bl
  const struct _tlgProvider_t *v5; // rax
  int v6; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v8; // r8
  int v9; // r9d
  DWORD v11; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v12; // [rsp+70h] [rbp+18h] BYREF
  __int64 v13; // [rsp+78h] [rbp+20h] BYREF

  v11 = 0;
  wil::ActivityBase<WorkAccessLogger,1,140737488355328,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v12);
  v4 = wil::ActivityBase<WorkAccessLogger,1,140737488355328,5,33554432,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WorkAccessLogger,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         a2,
         &v11);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  if ( v4 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v5 = WorkAccessLogger::Provider();
    v6 = (int)v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x800000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v8 = a1[34];
      v11 = CurrentThreadId;
      v12 = a2;
      v13 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (unsigned int)&dword_18006035C,
        v8 + 8,
        v9,
        (__int64)&v13,
        (__int64)&v12,
        (__int64)&v11);
    }
  }
  return wil::ActivityBase<WorkAccessLogger,1,140737488355328,5,33554432,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x1800285c8  push    rbx
0x1800285ca  push    rsi
0x1800285cb  push    rdi
0x1800285cc  sub     rsp, 40h
0x1800285d0  mov     esi, edx
0x1800285d2  mov     [rsp+58h+arg_0], 0
0x1800285da  lea     rdx, [rsp+58h+arg_10]
0x1800285df  mov     rdi, rcx
0x1800285e2  call    ?LockExclusive@?$ActivityBase@VWorkAccessLogger@@$00$0IAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WorkAccessLogger,1,140737488355328,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800285e7  mov     rcx, [rdi+110h]
0x1800285ee  lea     r8, [rsp+58h+arg_0]
0x1800285f3  mov     edx, esi
0x1800285f5  call    ?SetStopResult@?$ActivityData@VWorkAccessLogger@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VWorkAccessLogger@@$00$0IAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<WorkAccessLogger,1,140737488355328,5,33554432,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WorkAccessLogger,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x1800285fa  lea     rcx, [rsp+58h+arg_10]
0x1800285ff  mov     bl, al
0x180028601  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180028606  test    bl, bl
0x180028608  jz      short loc_18002861B
0x18002860a  mov     rax, [rdi]
0x18002860d  mov     rcx, rdi
0x180028610  mov     rax, [rax+8]
0x180028614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028619  jmp     short loc_180028695
0x18002861b  call    ?Provider@WorkAccessLogger@@SAPEBU_tlgProvider_t@@XZ; WorkAccessLogger::Provider(void)
0x180028620  mov     rbx, rax
0x180028623  mov     ecx, [rax]
0x180028625  cmp     ecx, 5
0x180028628  jbe     short loc_180028695
0x18002862a  mov     rdx, 800000000000h
0x180028634  mov     rcx, rax
0x180028637  call    _tlgKeywordOn
0x18002863c  test    al, al
0x18002863e  jz      short loc_180028695
0x180028640  call    cs:__imp_GetCurrentThreadId
0x180028647  nop     dword ptr [rax+rax+00h]
0x18002864c  mov     r8, [rdi+110h]
0x180028653  lea     rdx, dword_18006035C
0x18002865a  mov     [rsp+58h+arg_0], eax
0x18002865e  add     r8, 8
0x180028662  lea     rax, [rsp+58h+arg_0]
0x180028667  mov     [rsp+58h+arg_10], esi
0x18002866b  mov     [rsp+58h+var_28], rax
0x180028670  mov     rcx, rbx
0x180028673  lea     rax, [rsp+58h+arg_10]
0x180028678  mov     [rsp+58h+arg_18], 1000000h
0x180028681  mov     [rsp+58h+var_30], rax
0x180028686  lea     rax, [rsp+58h+arg_18]
0x18002868b  mov     [rsp+58h+var_38], rax
0x180028690  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180028695  mov     rcx, rdi
0x180028698  add     rsp, 40h
0x18002869c  pop     rdi
0x18002869d  pop     rsi
0x18002869e  pop     rbx
0x18002869f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWorkAccessLogger@@$00$0IAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WorkAccessLogger,1,140737488355328,5,33554432,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
