# wil::ActivityBase<CortanaSearchTelemetryLogging,1,70368744177664,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x1800cf6e8`
- end: `0x1800cf7d6`
- name: `?Stop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$0EAAAAAAAAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800cd570`

## callees

- `0x1800019ec`
- `0x18000243c`
- `0x18003a900`
- `0x18003bf74`
- `0x18003c234`
- `0x18003c9b8`
- `0x18003d458`
- `0x1800cf6e8`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cf76e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cf76e`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<CortanaSearchTelemetryLogging,1,70368744177664,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1,
        unsigned int a2)
{
  char v4; // bl
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  int v8; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v10; // r8
  int v11; // r9d
  DWORD v13; // [rsp+40h] [rbp-28h] BYREF
  __int64 v14; // [rsp+48h] [rbp-20h] BYREF
  __int64 v15; // [rsp+50h] [rbp-18h] BYREF

  v13 = 0;
  v14 = 0;
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v14);
  v4 = wil::ActivityBase<CortanaSearchTelemetryLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CortanaSearchTelemetryLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
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
    v5 = CortanaSearchTelemetryLogging::Provider();
    v8 = (int)v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL, v6, v7) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v10 = a1[34];
      v13 = CurrentThreadId;
      LODWORD(v14) = a2;
      v15 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v8,
        (unsigned int)byte_1801149E3,
        v10 + 8,
        v11,
        (__int64)&v15,
        (__int64)&v14,
        (__int64)&v13);
    }
  }
  return wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x1800cf6e8  mov     rax, rsp
0x1800cf6eb  mov     [rax+10h], rbx
0x1800cf6ef  mov     [rax+18h], rsi
0x1800cf6f3  push    rdi
0x1800cf6f4  sub     rsp, 60h
0x1800cf6f8  mov     esi, edx
0x1800cf6fa  mov     dword ptr [rax-28h], 0
0x1800cf701  lea     rdx, [rax-20h]
0x1800cf705  mov     qword ptr [rax-20h], 0
0x1800cf70d  mov     rdi, rcx
0x1800cf710  call    ?LockExclusive@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800cf715  mov     rcx, [rdi+110h]
0x1800cf71c  lea     r8, [rsp+68h+var_28]
0x1800cf721  mov     edx, esi
0x1800cf723  call    ?SetStopResult@?$ActivityData@VCortanaSearchTelemetryLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<CortanaSearchTelemetryLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CortanaSearchTelemetryLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x1800cf728  lea     rcx, [rsp+68h+var_20]
0x1800cf72d  mov     bl, al
0x1800cf72f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800cf734  test    bl, bl
0x1800cf736  jz      short loc_1800CF749
0x1800cf738  mov     rax, [rdi]
0x1800cf73b  mov     rcx, rdi
0x1800cf73e  mov     rax, [rax+8]
0x1800cf742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf747  jmp     short loc_1800CF7BD
0x1800cf749  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x1800cf74e  mov     rbx, rax
0x1800cf751  mov     ecx, [rax]
0x1800cf753  cmp     ecx, 5
0x1800cf756  jbe     short loc_1800CF7BD
0x1800cf758  mov     rdx, 400000000000h
0x1800cf762  mov     rcx, rax
0x1800cf765  call    _tlgKeywordOn
0x1800cf76a  test    al, al
0x1800cf76c  jz      short loc_1800CF7BD
0x1800cf76e  call    cs:__imp_GetCurrentThreadId
0x1800cf774  mov     r8, [rdi+110h]
0x1800cf77b  lea     rdx, byte_1801149E3
0x1800cf782  mov     [rsp+68h+var_28], eax
0x1800cf786  add     r8, 8
0x1800cf78a  lea     rax, [rsp+68h+var_28]
0x1800cf78f  mov     dword ptr [rsp+68h+var_20], esi
0x1800cf793  mov     [rsp+68h+var_38], rax
0x1800cf798  mov     rcx, rbx
0x1800cf79b  lea     rax, [rsp+68h+var_20]
0x1800cf7a0  mov     [rsp+68h+var_18], 1000000h
0x1800cf7a9  mov     [rsp+68h+var_40], rax
0x1800cf7ae  lea     rax, [rsp+68h+var_18]
0x1800cf7b3  mov     [rsp+68h+var_48], rax
0x1800cf7b8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800cf7bd  mov     rcx, rdi
0x1800cf7c0  lea     r11, [rsp+68h+var_8]
0x1800cf7c5  mov     rbx, [r11+18h]
0x1800cf7c9  mov     rsi, [r11+20h]
0x1800cf7cd  mov     rsp, r11
0x1800cf7d0  pop     rdi
0x1800cf7d1  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
