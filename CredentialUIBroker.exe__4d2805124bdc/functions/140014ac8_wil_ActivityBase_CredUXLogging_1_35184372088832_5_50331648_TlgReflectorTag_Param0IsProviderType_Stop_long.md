# wil::ActivityBase<CredUXLogging,1,35184372088832,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x140014ac8`
- end: `0x140014ba8`
- name: `?Stop@?$ActivityBase@VCredUXLogging@@$00$0CAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `224`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400111ac`

## callees

- `0x1400023e0`
- `0x140002f8c`
- `0x140009158`
- `0x14000e620`
- `0x14000ed00`
- `0x140011a60`
- `0x140014458`
- `0x140014ac8`
- `0x14001f010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140014b43`
- `KERNEL32!GetCurrentThreadId` at `0x140014b43`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<CredUXLogging,1,35184372088832,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(
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
  __int64 v10; // r9
  RTL_SRWLOCK *v12; // [rsp+50h] [rbp+8h] BYREF
  DWORD v13; // [rsp+58h] [rbp+10h] BYREF
  __int64 v14; // [rsp+60h] [rbp+18h] BYREF

  v13 = 0;
  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v12);
  v2 = wil::ActivityBase<CredUXLogging,1,35184372088832,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CredUXLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         0,
         &v13);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  if ( v2 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v6 = CredUXLogging::Provider();
    v7 = (__int64)v6;
    if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x200000000000LL, v4, v5) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v9 = a1[34];
      v13 = CurrentThreadId;
      LODWORD(v12) = 0;
      v14 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (__int64)byte_14002495B,
        v9 + 8,
        v10,
        (__int64)&v14,
        (__int64)&v12,
        (__int64)&v13);
    }
  }
  return wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
           a1,
           v3,
           v4,
           v5);
}

```

## disassembly

```asm
0x140014ac8  mov     rax, rsp
0x140014acb  mov     [rax+20h], rbx
0x140014acf  mov     [rax+10h], edx
0x140014ad2  push    rdi
0x140014ad3  sub     rsp, 40h
0x140014ad7  lea     rdx, [rax+8]
0x140014adb  mov     dword ptr [rax+10h], 0
0x140014ae2  mov     rdi, rcx
0x140014ae5  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140014aea  mov     rcx, [rdi+110h]
0x140014af1  lea     r8, [rsp+48h+arg_8]
0x140014af6  xor     edx, edx
0x140014af8  call    ?SetStopResult@?$ActivityData@VCredUXLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VCredUXLogging@@$00$0CAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<CredUXLogging,1,35184372088832,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CredUXLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x140014afd  lea     rcx, [rsp+48h+arg_0]
0x140014b02  mov     bl, al
0x140014b04  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140014b09  test    bl, bl
0x140014b0b  jz      short loc_140014B1E
0x140014b0d  mov     rax, [rdi]
0x140014b10  mov     rcx, rdi
0x140014b13  mov     rax, [rax+8]
0x140014b17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014b1c  jmp     short loc_140014B96
0x140014b1e  call    ?Provider@CredUXLogging@@SAPEBU_tlgProvider_t@@XZ; CredUXLogging::Provider(void)
0x140014b23  mov     rbx, rax
0x140014b26  mov     ecx, [rax]
0x140014b28  cmp     ecx, 5
0x140014b2b  jbe     short loc_140014B96
0x140014b2d  mov     rdx, 200000000000h
0x140014b37  mov     rcx, rax
0x140014b3a  call    _tlgKeywordOn
0x140014b3f  test    al, al
0x140014b41  jz      short loc_140014B96
0x140014b43  call    cs:__imp_GetCurrentThreadId
0x140014b49  mov     r8, [rdi+110h]
0x140014b50  lea     rdx, byte_14002495B
0x140014b57  mov     [rsp+48h+arg_8], eax
0x140014b5b  add     r8, 8
0x140014b5f  lea     rax, [rsp+48h+arg_8]
0x140014b64  mov     dword ptr [rsp+48h+arg_0], 0
0x140014b6c  mov     [rsp+48h+var_18], rax
0x140014b71  mov     rcx, rbx
0x140014b74  lea     rax, [rsp+48h+arg_0]
0x140014b79  mov     [rsp+48h+arg_10], 1000000h
0x140014b82  mov     [rsp+48h+var_20], rax
0x140014b87  lea     rax, [rsp+48h+arg_10]
0x140014b8c  mov     [rsp+48h+var_28], rax
0x140014b91  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140014b96  mov     rcx, rdi
0x140014b99  mov     rbx, [rsp+48h+arg_18]
0x140014b9e  add     rsp, 40h
0x140014ba2  pop     rdi
0x140014ba3  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCredUIBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
