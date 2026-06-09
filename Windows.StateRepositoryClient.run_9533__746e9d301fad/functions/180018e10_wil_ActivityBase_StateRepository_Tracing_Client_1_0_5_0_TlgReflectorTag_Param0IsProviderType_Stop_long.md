# wil::ActivityBase<StateRepository::Tracing::Client,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180018e10`
- end: `0x180018ed7`
- name: `?Stop@?$ActivityBase@VClient@Tracing@StateRepository@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180018468`

## callees

- `0x180001f24`
- `0x18000719c`
- `0x180009530`
- `0x1800185d4`
- `0x1800185f8`
- `0x1800189b4`
- `0x180018c00`
- `0x180018e10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018e72`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018e72`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<StateRepository::Tracing::Client,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  char v2; // bl
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  const struct _tlgProvider_t *v6; // rax
  int v7; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  int v10; // r9d
  int v12; // [rsp+50h] [rbp+8h] BYREF
  DWORD v13; // [rsp+58h] [rbp+10h] BYREF
  __int64 v14; // [rsp+60h] [rbp+18h] BYREF

  v13 = 0;
  wil::ActivityBase<StateRepository::Tracing::Client,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v12);
  v2 = wil::ActivityBase<StateRepository::Tracing::Client,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StateRepository::Tracing::Client,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         0,
         &v13);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  if ( v2 )
  {
    wil::ActivityBase<StateRepository::Tracing::Client,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
      a1,
      v13);
  }
  else
  {
    v6 = StateRepository::Tracing::Client::Provider();
    v7 = (int)v6;
    if ( *(_DWORD *)v6 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v9 = a1[34];
      v13 = CurrentThreadId;
      v12 = 0;
      v14 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (unsigned int)&unk_180030170,
        v9 + 8,
        v10,
        (__int64)&v14,
        (__int64)&v12,
        (__int64)&v13);
    }
  }
  return wil::ActivityBase<StateRepository::Tracing::Client,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
           a1,
           v3,
           v4,
           v5);
}

```

## disassembly

```asm
0x180018e10  mov     rax, rsp
0x180018e13  mov     [rax+20h], rbx
0x180018e17  mov     [rax+10h], edx
0x180018e1a  push    rdi
0x180018e1b  sub     rsp, 40h
0x180018e1f  lea     rdx, [rax+8]
0x180018e23  mov     dword ptr [rax+10h], 0
0x180018e2a  mov     rdi, rcx
0x180018e2d  call    ?LockExclusive@?$ActivityBase@VClient@Tracing@StateRepository@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StateRepository::Tracing::Client,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180018e32  mov     rcx, [rdi+110h]
0x180018e39  lea     r8, [rsp+48h+arg_8]
0x180018e3e  xor     edx, edx
0x180018e40  call    ?SetStopResult@?$ActivityData@VClient@Tracing@StateRepository@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VClient@Tracing@StateRepository@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<StateRepository::Tracing::Client,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StateRepository::Tracing::Client,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x180018e45  lea     rcx, [rsp+48h+arg_0]
0x180018e4a  mov     bl, al
0x180018e4c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180018e51  test    bl, bl
0x180018e53  jz      short loc_180018E63
0x180018e55  mov     edx, [rsp+48h+arg_8]
0x180018e59  mov     rcx, rdi
0x180018e5c  call    ?ReportStopActivity@?$ActivityBase@VClient@Tracing@StateRepository@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<StateRepository::Tracing::Client,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x180018e61  jmp     short loc_180018EC5
0x180018e63  call    ?Provider@Client@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Client::Provider(void)
0x180018e68  mov     rbx, rax
0x180018e6b  mov     ecx, [rax]
0x180018e6d  cmp     ecx, 5
0x180018e70  jbe     short loc_180018EC5
0x180018e72  call    cs:__imp_GetCurrentThreadId
0x180018e78  mov     r8, [rdi+110h]
0x180018e7f  lea     rdx, unk_180030170
0x180018e86  mov     [rsp+48h+arg_8], eax
0x180018e8a  add     r8, 8
0x180018e8e  lea     rax, [rsp+48h+arg_8]
0x180018e93  mov     [rsp+48h+arg_0], 0
0x180018e9b  mov     [rsp+48h+var_18], rax
0x180018ea0  mov     rcx, rbx
0x180018ea3  lea     rax, [rsp+48h+arg_0]
0x180018ea8  mov     [rsp+48h+arg_10], 1000000h
0x180018eb1  mov     [rsp+48h+var_20], rax
0x180018eb6  lea     rax, [rsp+48h+arg_10]
0x180018ebb  mov     [rsp+48h+var_28], rax
0x180018ec0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180018ec5  mov     rcx, rdi
0x180018ec8  mov     rbx, [rsp+48h+arg_18]
0x180018ecd  add     rsp, 40h
0x180018ed1  pop     rdi
0x180018ed2  jmp     ?IgnoreCurrentThread@?$ActivityBase@VClient@Tracing@StateRepository@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<StateRepository::Tracing::Client,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
