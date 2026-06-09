# wil::ActivityBase<CortanaSearchTelemetryLogging,0,0,5,33554432,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18003d758`
- end: `0x18003d827`
- name: `?Stop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$0A@$0A@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `207`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18003aed0`
- `0x18003c0e0`

## callees

- `0x1800019ec`
- `0x18003a900`
- `0x18003bf74`
- `0x18003c234`
- `0x18003c9b8`
- `0x18003d458`
- `0x18003d758`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003d7c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003d7c2`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<CortanaSearchTelemetryLogging,0,0,5,33554432,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  char v2; // bl
  const struct _tlgProvider_t *v3; // rax
  int v4; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v6; // r8
  int v7; // r9d
  DWORD v9; // [rsp+40h] [rbp-28h] BYREF
  __int64 v10; // [rsp+48h] [rbp-20h] BYREF
  __int64 v11[3]; // [rsp+50h] [rbp-18h] BYREF

  v9 = 0;
  v10 = 0;
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v10);
  v2 = wil::ActivityBase<CortanaSearchTelemetryLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CortanaSearchTelemetryLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         0,
         &v9);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  if ( v2 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v3 = CortanaSearchTelemetryLogging::Provider();
    v4 = (int)v3;
    if ( *(_DWORD *)v3 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v6 = a1[34];
      v9 = CurrentThreadId;
      LODWORD(v10) = 0;
      v11[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v4,
        (unsigned int)byte_180110FC9,
        v6 + 8,
        v7,
        (__int64)v11,
        (__int64)&v10,
        (__int64)&v9);
    }
  }
  return wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x18003d758  mov     rax, rsp
0x18003d75b  mov     [rax+10h], rbx
0x18003d75f  push    rdi
0x18003d760  sub     rsp, 60h
0x18003d764  lea     rdx, [rax-20h]
0x18003d768  mov     dword ptr [rax-28h], 0
0x18003d76f  mov     rdi, rcx
0x18003d772  mov     qword ptr [rax-20h], 0
0x18003d77a  call    ?LockExclusive@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003d77f  mov     rcx, [rdi+110h]
0x18003d786  lea     r8, [rsp+68h+var_28]
0x18003d78b  xor     edx, edx
0x18003d78d  call    ?SetStopResult@?$ActivityData@VCortanaSearchTelemetryLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<CortanaSearchTelemetryLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CortanaSearchTelemetryLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18003d792  lea     rcx, [rsp+68h+var_20]
0x18003d797  mov     bl, al
0x18003d799  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003d79e  test    bl, bl
0x18003d7a0  jz      short loc_18003D7B3
0x18003d7a2  mov     rax, [rdi]
0x18003d7a5  mov     rcx, rdi
0x18003d7a8  mov     rax, [rax+8]
0x18003d7ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d7b1  jmp     short loc_18003D815
0x18003d7b3  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x18003d7b8  mov     rbx, rax
0x18003d7bb  mov     ecx, [rax]
0x18003d7bd  cmp     ecx, 5
0x18003d7c0  jbe     short loc_18003D815
0x18003d7c2  call    cs:__imp_GetCurrentThreadId
0x18003d7c8  mov     r8, [rdi+110h]
0x18003d7cf  lea     rdx, byte_180110FC9
0x18003d7d6  mov     [rsp+68h+var_28], eax
0x18003d7da  add     r8, 8
0x18003d7de  lea     rax, [rsp+68h+var_28]
0x18003d7e3  mov     dword ptr [rsp+68h+var_20], 0
0x18003d7eb  mov     [rsp+68h+var_38], rax
0x18003d7f0  mov     rcx, rbx
0x18003d7f3  lea     rax, [rsp+68h+var_20]
0x18003d7f8  mov     [rsp+68h+var_18], 1000000h
0x18003d801  mov     [rsp+68h+var_40], rax
0x18003d806  lea     rax, [rsp+68h+var_18]
0x18003d80b  mov     [rsp+68h+var_48], rax
0x18003d810  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003d815  mov     rcx, rdi
0x18003d818  mov     rbx, [rsp+68h+arg_8]
0x18003d81d  add     rsp, 60h
0x18003d821  pop     rdi
0x18003d822  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
