# wil::ActivityBase<CortanaSearchTelemetryLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18009f448`
- end: `0x18009f517`
- name: `?Stop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18009dfe0`

## callees

- `0x1800019ec`
- `0x18003a900`
- `0x18003bf74`
- `0x18003c234`
- `0x18003c9b8`
- `0x18003d458`
- `0x18009f448`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009f4b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009f4b2`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<CortanaSearchTelemetryLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
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
        (unsigned int)word_18011344A,
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
0x18009f448  mov     rax, rsp
0x18009f44b  mov     [rax+10h], rbx
0x18009f44f  push    rdi
0x18009f450  sub     rsp, 60h
0x18009f454  lea     rdx, [rax-20h]
0x18009f458  mov     dword ptr [rax-28h], 0
0x18009f45f  mov     rdi, rcx
0x18009f462  mov     qword ptr [rax-20h], 0
0x18009f46a  call    ?LockExclusive@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18009f46f  mov     rcx, [rdi+110h]
0x18009f476  lea     r8, [rsp+68h+var_28]
0x18009f47b  xor     edx, edx
0x18009f47d  call    ?SetStopResult@?$ActivityData@VCortanaSearchTelemetryLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<CortanaSearchTelemetryLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CortanaSearchTelemetryLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18009f482  lea     rcx, [rsp+68h+var_20]
0x18009f487  mov     bl, al
0x18009f489  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18009f48e  test    bl, bl
0x18009f490  jz      short loc_18009F4A3
0x18009f492  mov     rax, [rdi]
0x18009f495  mov     rcx, rdi
0x18009f498  mov     rax, [rax+8]
0x18009f49c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f4a1  jmp     short loc_18009F505
0x18009f4a3  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x18009f4a8  mov     rbx, rax
0x18009f4ab  mov     ecx, [rax]
0x18009f4ad  cmp     ecx, 5
0x18009f4b0  jbe     short loc_18009F505
0x18009f4b2  call    cs:__imp_GetCurrentThreadId
0x18009f4b8  mov     r8, [rdi+110h]
0x18009f4bf  lea     rdx, word_18011344A
0x18009f4c6  mov     [rsp+68h+var_28], eax
0x18009f4ca  add     r8, 8
0x18009f4ce  lea     rax, [rsp+68h+var_28]
0x18009f4d3  mov     dword ptr [rsp+68h+var_20], 0
0x18009f4db  mov     [rsp+68h+var_38], rax
0x18009f4e0  mov     rcx, rbx
0x18009f4e3  lea     rax, [rsp+68h+var_20]
0x18009f4e8  mov     [rsp+68h+var_18], 1000000h
0x18009f4f1  mov     [rsp+68h+var_40], rax
0x18009f4f6  lea     rax, [rsp+68h+var_18]
0x18009f4fb  mov     [rsp+68h+var_48], rax
0x18009f500  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18009f505  mov     rcx, rdi
0x18009f508  mov     rbx, [rsp+68h+arg_8]
0x18009f50d  add     rsp, 60h
0x18009f511  pop     rdi
0x18009f512  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
