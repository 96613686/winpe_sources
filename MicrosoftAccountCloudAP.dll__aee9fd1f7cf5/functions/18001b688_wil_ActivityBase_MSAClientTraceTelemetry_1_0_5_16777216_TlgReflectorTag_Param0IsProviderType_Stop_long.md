# wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18001b688`
- end: `0x18001b74f`
- name: `?Stop@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001ad0c`

## callees

- `0x180001b18`
- `0x18000862c`
- `0x18001a878`
- `0x18001a89c`
- `0x18001acec`
- `0x18001af98`
- `0x18001b4c0`
- `0x18001b688`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b6ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b6ea`

## pseudocode

```c
void __fastcall wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  char v2; // bl
  const struct _tlgProvider_t *v3; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v5; // r8
  __int64 v6; // r9
  RTL_SRWLOCK *v7; // [rsp+50h] [rbp+8h] BYREF
  DWORD v8; // [rsp+58h] [rbp+10h] BYREF
  __int64 v9; // [rsp+60h] [rbp+18h] BYREF

  v8 = 0;
  wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v7);
  v2 = wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         0,
         &v8);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v7);
  if ( v2 )
  {
    wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
      a1,
      v8);
  }
  else
  {
    v3 = MSAClientTraceTelemetry::Provider();
    if ( *(_DWORD *)v3 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v5 = a1[34];
      v8 = CurrentThreadId;
      LODWORD(v7) = 0;
      v9 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v3,
        (__int64)&byte_180044FBF,
        v5 + 8,
        v6,
        (__int64)&v9,
        (__int64)&v7,
        (__int64)&v8);
    }
  }
  wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x18001b688  mov     rax, rsp
0x18001b68b  mov     [rax+20h], rbx
0x18001b68f  mov     [rax+10h], edx
0x18001b692  push    rdi
0x18001b693  sub     rsp, 40h
0x18001b697  lea     rdx, [rax+8]
0x18001b69b  mov     dword ptr [rax+10h], 0
0x18001b6a2  mov     rdi, rcx
0x18001b6a5  call    ?LockExclusive@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001b6aa  mov     rcx, [rdi+110h]
0x18001b6b1  lea     r8, [rsp+48h+arg_8]
0x18001b6b6  xor     edx, edx
0x18001b6b8  call    ?SetStopResult@?$ActivityData@VMSAClientTraceTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18001b6bd  lea     rcx, [rsp+48h+arg_0]
0x18001b6c2  mov     bl, al
0x18001b6c4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001b6c9  test    bl, bl
0x18001b6cb  jz      short loc_18001B6DB
0x18001b6cd  mov     edx, [rsp+48h+arg_8]
0x18001b6d1  mov     rcx, rdi
0x18001b6d4  call    ?ReportStopActivity@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x18001b6d9  jmp     short loc_18001B73D
0x18001b6db  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x18001b6e0  mov     rbx, rax
0x18001b6e3  mov     ecx, [rax]
0x18001b6e5  cmp     ecx, 5
0x18001b6e8  jbe     short loc_18001B73D
0x18001b6ea  call    cs:__imp_GetCurrentThreadId
0x18001b6f0  mov     r8, [rdi+110h]
0x18001b6f7  lea     rdx, byte_180044FBF
0x18001b6fe  mov     [rsp+48h+arg_8], eax
0x18001b702  add     r8, 8
0x18001b706  lea     rax, [rsp+48h+arg_8]
0x18001b70b  mov     dword ptr [rsp+48h+arg_0], 0
0x18001b713  mov     [rsp+48h+var_18], rax
0x18001b718  mov     rcx, rbx
0x18001b71b  lea     rax, [rsp+48h+arg_0]
0x18001b720  mov     [rsp+48h+arg_10], 1000000h
0x18001b729  mov     [rsp+48h+var_20], rax
0x18001b72e  lea     rax, [rsp+48h+arg_10]
0x18001b733  mov     [rsp+48h+var_28], rax
0x18001b738  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001b73d  mov     rcx, rdi
0x18001b740  mov     rbx, [rsp+48h+arg_18]
0x18001b745  add     rsp, 40h
0x18001b749  pop     rdi
0x18001b74a  jmp     ?IgnoreCurrentThread@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
