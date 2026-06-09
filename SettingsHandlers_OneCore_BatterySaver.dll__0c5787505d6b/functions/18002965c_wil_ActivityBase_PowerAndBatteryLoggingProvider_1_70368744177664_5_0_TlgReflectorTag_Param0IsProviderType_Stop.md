# wil::ActivityBase<PowerAndBatteryLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18002965c`
- end: `0x18002973c`
- name: `?Stop@?$ActivityBase@VPowerAndBatteryLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `224`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180028920`
- `0x180043830`
- `0x1800439a8`
- `0x180043b90`

## callees

- `0x1800014ac`
- `0x180001c3c`
- `0x18000b508`
- `0x180022e60`
- `0x18002418c`
- `0x180025840`
- `0x1800288c0`
- `0x18002965c`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800296d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800296d7`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<PowerAndBatteryLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  char v2; // bl
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  __int64 v5; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v7; // r8
  __int64 v8; // r9
  RTL_SRWLOCK *v10; // [rsp+50h] [rbp+8h] BYREF
  DWORD v11; // [rsp+58h] [rbp+10h] BYREF
  __int64 v12; // [rsp+60h] [rbp+18h] BYREF

  v11 = 0;
  wil::ActivityBase<PowerAndBatteryLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v10);
  v2 = wil::ActivityBase<PowerAndBatteryLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<PowerAndBatteryLoggingProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         0,
         &v11);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  if ( v2 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v3 = PowerAndBatteryLoggingProvider::Provider();
    v5 = (__int64)v3;
    if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x400000000000LL, v4) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v7 = a1[34];
      v11 = CurrentThreadId;
      LODWORD(v10) = 0;
      v12 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v5,
        (__int64)&dword_18005A56C,
        v7 + 8,
        v8,
        (__int64)&v12,
        (__int64)&v10,
        (__int64)&v11);
    }
  }
  return wil::ActivityBase<PowerAndBatteryLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x18002965c  mov     rax, rsp
0x18002965f  mov     [rax+20h], rbx
0x180029663  mov     [rax+10h], edx
0x180029666  push    rdi
0x180029667  sub     rsp, 40h
0x18002966b  lea     rdx, [rax+8]
0x18002966f  mov     dword ptr [rax+10h], 0
0x180029676  mov     rdi, rcx
0x180029679  call    ?LockExclusive@?$ActivityBase@VPowerAndBatteryLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PowerAndBatteryLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002967e  mov     rcx, [rdi+110h]
0x180029685  lea     r8, [rsp+48h+arg_8]
0x18002968a  xor     edx, edx
0x18002968c  call    ?SetStopResult@?$ActivityData@VPowerAndBatteryLoggingProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPowerAndBatteryLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<PowerAndBatteryLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<PowerAndBatteryLoggingProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x180029691  lea     rcx, [rsp+48h+arg_0]
0x180029696  mov     bl, al
0x180029698  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002969d  test    bl, bl
0x18002969f  jz      short loc_1800296B2
0x1800296a1  mov     rax, [rdi]
0x1800296a4  mov     rcx, rdi
0x1800296a7  mov     rax, [rax+8]
0x1800296ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296b0  jmp     short loc_18002972A
0x1800296b2  call    ?Provider@PowerAndBatteryLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PowerAndBatteryLoggingProvider::Provider(void)
0x1800296b7  mov     rbx, rax
0x1800296ba  mov     ecx, [rax]
0x1800296bc  cmp     ecx, 5
0x1800296bf  jbe     short loc_18002972A
0x1800296c1  mov     rdx, 400000000000h
0x1800296cb  mov     rcx, rax
0x1800296ce  call    _tlgKeywordOn
0x1800296d3  test    al, al
0x1800296d5  jz      short loc_18002972A
0x1800296d7  call    cs:__imp_GetCurrentThreadId
0x1800296dd  mov     r8, [rdi+110h]
0x1800296e4  lea     rdx, dword_18005A56C
0x1800296eb  mov     [rsp+48h+arg_8], eax
0x1800296ef  add     r8, 8
0x1800296f3  lea     rax, [rsp+48h+arg_8]
0x1800296f8  mov     dword ptr [rsp+48h+arg_0], 0
0x180029700  mov     [rsp+48h+var_18], rax
0x180029705  mov     rcx, rbx
0x180029708  lea     rax, [rsp+48h+arg_0]
0x18002970d  mov     [rsp+48h+arg_10], 1000000h
0x180029716  mov     [rsp+48h+var_20], rax
0x18002971b  lea     rax, [rsp+48h+arg_10]
0x180029720  mov     [rsp+48h+var_28], rax
0x180029725  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002972a  mov     rcx, rdi
0x18002972d  mov     rbx, [rsp+48h+arg_18]
0x180029732  add     rsp, 40h
0x180029736  pop     rdi
0x180029737  jmp     ?IgnoreCurrentThread@?$ActivityBase@VPowerAndBatteryLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PowerAndBatteryLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
