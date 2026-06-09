# wil::ActivityBase<CodeIntegrity::Management::Telemetry::ManageCIProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x1800150c8`
- end: `0x1800151a8`
- name: `?Stop@?$ActivityBase@VManageCIProvider@Telemetry@Management@CodeIntegrity@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `224`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800128f0`
- `0x180014d20`

## callees

- `0x1800019bc`
- `0x180002054`
- `0x18000a398`
- `0x1800137d4`
- `0x18001481c`
- `0x180014ce4`
- `0x180014e80`
- `0x1800150c8`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015143`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015143`

## pseudocode

```c
void __fastcall wil::ActivityBase<CodeIntegrity::Management::Telemetry::ManageCIProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  char v2; // bl
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  __int64 v5; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v7; // r8
  __int64 v8; // r9
  RTL_SRWLOCK *v9; // [rsp+50h] [rbp+8h] BYREF
  DWORD v10; // [rsp+58h] [rbp+10h] BYREF
  __int64 v11; // [rsp+60h] [rbp+18h] BYREF

  v10 = 0;
  wil::ActivityBase<CodeIntegrity::Management::Telemetry::ManageCIProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v9);
  v2 = wil::ActivityBase<CodeIntegrity::Management::Telemetry::ManageCIProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CodeIntegrity::Management::Telemetry::ManageCIProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         0,
         &v10);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  if ( v2 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v3 = CodeIntegrity::Management::Telemetry::ManageCIProvider::Provider();
    v5 = (__int64)v3;
    if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x400000000000LL, v4) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v7 = a1[34];
      v10 = CurrentThreadId;
      LODWORD(v9) = 0;
      v11 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v5,
        (__int64)word_180031632,
        v7 + 8,
        v8,
        (__int64)&v11,
        (__int64)&v9,
        (__int64)&v10);
    }
  }
  wil::ActivityBase<CodeIntegrity::Management::Telemetry::ManageCIProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x1800150c8  mov     rax, rsp
0x1800150cb  mov     [rax+20h], rbx
0x1800150cf  mov     [rax+10h], edx
0x1800150d2  push    rdi
0x1800150d3  sub     rsp, 40h
0x1800150d7  lea     rdx, [rax+8]
0x1800150db  mov     dword ptr [rax+10h], 0
0x1800150e2  mov     rdi, rcx
0x1800150e5  call    ?LockExclusive@?$ActivityBase@VManageCIProvider@Telemetry@Management@CodeIntegrity@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CodeIntegrity::Management::Telemetry::ManageCIProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800150ea  mov     rcx, [rdi+110h]
0x1800150f1  lea     r8, [rsp+48h+arg_8]
0x1800150f6  xor     edx, edx
0x1800150f8  call    ?SetStopResult@?$ActivityData@VManageCIProvider@Telemetry@Management@CodeIntegrity@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VManageCIProvider@Telemetry@Management@CodeIntegrity@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<CodeIntegrity::Management::Telemetry::ManageCIProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CodeIntegrity::Management::Telemetry::ManageCIProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x1800150fd  lea     rcx, [rsp+48h+arg_0]
0x180015102  mov     bl, al
0x180015104  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180015109  test    bl, bl
0x18001510b  jz      short loc_18001511E
0x18001510d  mov     rax, [rdi]
0x180015110  mov     rcx, rdi
0x180015113  mov     rax, [rax+8]
0x180015117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001511c  jmp     short loc_180015196
0x18001511e  call    ?Provider@ManageCIProvider@Telemetry@Management@CodeIntegrity@@SAPEBU_tlgProvider_t@@XZ; CodeIntegrity::Management::Telemetry::ManageCIProvider::Provider(void)
0x180015123  mov     rbx, rax
0x180015126  mov     ecx, [rax]
0x180015128  cmp     ecx, 5
0x18001512b  jbe     short loc_180015196
0x18001512d  mov     rdx, 400000000000h
0x180015137  mov     rcx, rax
0x18001513a  call    _tlgKeywordOn
0x18001513f  test    al, al
0x180015141  jz      short loc_180015196
0x180015143  call    cs:__imp_GetCurrentThreadId
0x180015149  mov     r8, [rdi+110h]
0x180015150  lea     rdx, word_180031632
0x180015157  mov     [rsp+48h+arg_8], eax
0x18001515b  add     r8, 8
0x18001515f  lea     rax, [rsp+48h+arg_8]
0x180015164  mov     dword ptr [rsp+48h+arg_0], 0
0x18001516c  mov     [rsp+48h+var_18], rax
0x180015171  mov     rcx, rbx
0x180015174  lea     rax, [rsp+48h+arg_0]
0x180015179  mov     [rsp+48h+arg_10], 1000000h
0x180015182  mov     [rsp+48h+var_20], rax
0x180015187  lea     rax, [rsp+48h+arg_10]
0x18001518c  mov     [rsp+48h+var_28], rax
0x180015191  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180015196  mov     rcx, rdi
0x180015199  mov     rbx, [rsp+48h+arg_18]
0x18001519e  add     rsp, 40h
0x1800151a2  pop     rdi
0x1800151a3  jmp     ?IgnoreCurrentThread@?$ActivityBase@VManageCIProvider@Telemetry@Management@CodeIntegrity@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CodeIntegrity::Management::Telemetry::ManageCIProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
