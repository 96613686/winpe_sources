# wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180031724`
- end: `0x1800317fa`
- name: `?Stop@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `214`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18003eb88`
- `0x18003fd4b`

## callees

- `0x180001dc8`
- `0x1800175e0`
- `0x180019e40`
- `0x18001acd0`
- `0x18001edd4`
- `0x1800202bc`
- `0x1800316c4`
- `0x180031724`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003179c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003179c`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
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
  DWORD v13; // [rsp+60h] [rbp+8h] BYREF
  RTL_SRWLOCK *v14; // [rsp+70h] [rbp+18h] BYREF
  __int64 v15; // [rsp+78h] [rbp+20h]

  v13 = 0;
  wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v14);
  v4 = wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WiFiCloudStoreTelemetry,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
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
    v8 = WiFiCloudStoreTelemetry::Provider();
    v9 = (__int64)v8;
    if ( *(_DWORD *)v8 > 5u && (unsigned __int8)tlgKeywordOn(v8, 0x400000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v11 = a1[34];
      v13 = CurrentThreadId;
      LODWORD(v14) = a2;
      v15 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (__int64)byte_180046239,
        v11 + 8);
    }
  }
  return wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
           a1,
           v5,
           v6,
           v7);
}

```

## disassembly

```asm
0x180031724  push    rbx
0x180031726  push    rsi
0x180031727  push    rdi
0x180031728  sub     rsp, 40h
0x18003172c  mov     esi, edx
0x18003172e  mov     [rsp+58h+arg_0], 0
0x180031736  lea     rdx, [rsp+58h+arg_10]
0x18003173b  mov     rdi, rcx
0x18003173e  call    ?LockExclusive@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180031743  mov     rcx, [rdi+110h]
0x18003174a  lea     r8, [rsp+58h+arg_0]
0x18003174f  mov     edx, esi
0x180031751  call    ?SetStopResult@?$ActivityData@VWiFiCloudStoreTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WiFiCloudStoreTelemetry,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x180031756  lea     rcx, [rsp+58h+arg_10]
0x18003175b  mov     bl, al
0x18003175d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180031762  test    bl, bl
0x180031764  jz      short loc_180031777
0x180031766  mov     rax, [rdi]
0x180031769  mov     rcx, rdi
0x18003176c  mov     rax, [rax+8]
0x180031770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031775  jmp     short loc_1800317EB
0x180031777  call    ?Provider@WiFiCloudStoreTelemetry@@SAPEBU_tlgProvider_t@@XZ; WiFiCloudStoreTelemetry::Provider(void)
0x18003177c  mov     rbx, rax
0x18003177f  mov     ecx, [rax]
0x180031781  cmp     ecx, 5
0x180031784  jbe     short loc_1800317EB
0x180031786  mov     rdx, 400000000000h
0x180031790  mov     rcx, rax
0x180031793  call    _tlgKeywordOn
0x180031798  test    al, al
0x18003179a  jz      short loc_1800317EB
0x18003179c  call    cs:__imp_GetCurrentThreadId
0x1800317a2  mov     r8, [rdi+110h]
0x1800317a9  lea     rdx, byte_180046239
0x1800317b0  mov     [rsp+58h+arg_0], eax
0x1800317b4  add     r8, 8
0x1800317b8  lea     rax, [rsp+58h+arg_0]
0x1800317bd  mov     dword ptr [rsp+58h+arg_10], esi
0x1800317c1  mov     [rsp+58h+var_28], rax
0x1800317c6  mov     rcx, rbx
0x1800317c9  lea     rax, [rsp+58h+arg_10]
0x1800317ce  mov     [rsp+58h+arg_18], 1000000h
0x1800317d7  mov     [rsp+58h+var_30], rax
0x1800317dc  lea     rax, [rsp+58h+arg_18]
0x1800317e1  mov     [rsp+58h+var_38], rax
0x1800317e6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800317eb  mov     rcx, rdi
0x1800317ee  add     rsp, 40h
0x1800317f2  pop     rdi
0x1800317f3  pop     rsi
0x1800317f4  pop     rbx
0x1800317f5  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
