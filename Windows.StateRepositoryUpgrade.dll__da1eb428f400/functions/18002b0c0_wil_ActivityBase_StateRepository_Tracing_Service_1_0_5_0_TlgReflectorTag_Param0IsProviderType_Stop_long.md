# wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18002b0c0`
- end: `0x18002b187`
- name: `?Stop@?$ActivityBase@VService@Tracing@StateRepository@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x18002a7f0`

## callees

- `0x180002160`
- `0x18000c984`
- `0x18000f460`
- `0x18002a938`
- `0x18002a95c`
- `0x18002ad24`
- `0x18002af70`
- `0x18002b0c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b122`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b122`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  char v2; // bl
  const struct _tlgProvider_t *v3; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v5; // r8
  int v6; // r9d
  int v8; // [rsp+50h] [rbp+8h] BYREF
  DWORD v9; // [rsp+58h] [rbp+10h] BYREF
  __int64 v10; // [rsp+60h] [rbp+18h] BYREF

  v9 = 0;
  wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v8);
  v2 = wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StateRepository::Tracing::Service,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         0,
         &v9);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v8);
  if ( v2 )
  {
    wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
      a1,
      v9);
  }
  else
  {
    v3 = StateRepository::Tracing::Service::Provider();
    if ( *(_DWORD *)v3 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v5 = a1[34];
      v9 = CurrentThreadId;
      v8 = 0;
      v10 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v3,
        (unsigned int)byte_180046049,
        v5 + 8,
        v6,
        (__int64)&v10,
        (__int64)&v8,
        (__int64)&v9);
    }
  }
  return wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x18002b0c0  mov     rax, rsp
0x18002b0c3  mov     [rax+20h], rbx
0x18002b0c7  mov     [rax+10h], edx
0x18002b0ca  push    rdi
0x18002b0cb  sub     rsp, 40h
0x18002b0cf  lea     rdx, [rax+8]
0x18002b0d3  mov     dword ptr [rax+10h], 0
0x18002b0da  mov     rdi, rcx
0x18002b0dd  call    ?LockExclusive@?$ActivityBase@VService@Tracing@StateRepository@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002b0e2  mov     rcx, [rdi+110h]
0x18002b0e9  lea     r8, [rsp+48h+arg_8]
0x18002b0ee  xor     edx, edx
0x18002b0f0  call    ?SetStopResult@?$ActivityData@VService@Tracing@StateRepository@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VService@Tracing@StateRepository@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StateRepository::Tracing::Service,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18002b0f5  lea     rcx, [rsp+48h+arg_0]
0x18002b0fa  mov     bl, al
0x18002b0fc  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002b101  test    bl, bl
0x18002b103  jz      short loc_18002B113
0x18002b105  mov     edx, [rsp+48h+arg_8]
0x18002b109  mov     rcx, rdi
0x18002b10c  call    ?ReportStopActivity@?$ActivityBase@VService@Tracing@StateRepository@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x18002b111  jmp     short loc_18002B175
0x18002b113  call    ?Provider@Service@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Service::Provider(void)
0x18002b118  mov     rbx, rax
0x18002b11b  mov     ecx, [rax]
0x18002b11d  cmp     ecx, 5
0x18002b120  jbe     short loc_18002B175
0x18002b122  call    cs:__imp_GetCurrentThreadId
0x18002b128  mov     r8, [rdi+110h]
0x18002b12f  lea     rdx, byte_180046049
0x18002b136  mov     [rsp+48h+arg_8], eax
0x18002b13a  add     r8, 8
0x18002b13e  lea     rax, [rsp+48h+arg_8]
0x18002b143  mov     [rsp+48h+arg_0], 0
0x18002b14b  mov     [rsp+48h+var_18], rax
0x18002b150  mov     rcx, rbx
0x18002b153  lea     rax, [rsp+48h+arg_0]
0x18002b158  mov     [rsp+48h+arg_10], 1000000h
0x18002b161  mov     [rsp+48h+var_20], rax
0x18002b166  lea     rax, [rsp+48h+arg_10]
0x18002b16b  mov     [rsp+48h+var_28], rax
0x18002b170  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002b175  mov     rcx, rdi
0x18002b178  mov     rbx, [rsp+48h+arg_18]
0x18002b17d  add     rsp, 40h
0x18002b181  pop     rdi
0x18002b182  jmp     ?IgnoreCurrentThread@?$ActivityBase@VService@Tracing@StateRepository@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
