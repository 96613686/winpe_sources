# wil::ActivityBase<CortanaSearchTelemetryLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180098ae8`
- end: `0x180098bcd`
- name: `?Stop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180096a68`

## callees

- `0x1800019ec`
- `0x18000243c`
- `0x18003a900`
- `0x18003bf74`
- `0x18003c234`
- `0x18003c9b8`
- `0x18003d458`
- `0x180098ae8`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180098b68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180098b68`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<CortanaSearchTelemetryLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  char v2; // bl
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  __int64 v5; // r9
  int v6; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v8; // r8
  int v9; // r9d
  DWORD v11; // [rsp+40h] [rbp-28h] BYREF
  __int64 v12; // [rsp+48h] [rbp-20h] BYREF
  __int64 v13[3]; // [rsp+50h] [rbp-18h] BYREF

  v11 = 0;
  v12 = 0;
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v12);
  v2 = wil::ActivityBase<CortanaSearchTelemetryLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CortanaSearchTelemetryLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         0,
         &v11);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  if ( v2 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v3 = CortanaSearchTelemetryLogging::Provider();
    v6 = (int)v3;
    if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x200000000000LL, v4, v5) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v8 = a1[34];
      v11 = CurrentThreadId;
      LODWORD(v12) = 0;
      v13[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (unsigned int)&unk_180112E18,
        v8 + 8,
        v9,
        (__int64)v13,
        (__int64)&v12,
        (__int64)&v11);
    }
  }
  return wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x180098ae8  mov     rax, rsp
0x180098aeb  mov     [rax+10h], rbx
0x180098aef  push    rdi
0x180098af0  sub     rsp, 60h
0x180098af4  lea     rdx, [rax-20h]
0x180098af8  mov     dword ptr [rax-28h], 0
0x180098aff  mov     rdi, rcx
0x180098b02  mov     qword ptr [rax-20h], 0
0x180098b0a  call    ?LockExclusive@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180098b0f  mov     rcx, [rdi+110h]
0x180098b16  lea     r8, [rsp+68h+var_28]
0x180098b1b  xor     edx, edx
0x180098b1d  call    ?SetStopResult@?$ActivityData@VCortanaSearchTelemetryLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<CortanaSearchTelemetryLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CortanaSearchTelemetryLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x180098b22  lea     rcx, [rsp+68h+var_20]
0x180098b27  mov     bl, al
0x180098b29  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180098b2e  test    bl, bl
0x180098b30  jz      short loc_180098B43
0x180098b32  mov     rax, [rdi]
0x180098b35  mov     rcx, rdi
0x180098b38  mov     rax, [rax+8]
0x180098b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098b41  jmp     short loc_180098BBB
0x180098b43  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x180098b48  mov     rbx, rax
0x180098b4b  mov     ecx, [rax]
0x180098b4d  cmp     ecx, 5
0x180098b50  jbe     short loc_180098BBB
0x180098b52  mov     rdx, 200000000000h
0x180098b5c  mov     rcx, rax
0x180098b5f  call    _tlgKeywordOn
0x180098b64  test    al, al
0x180098b66  jz      short loc_180098BBB
0x180098b68  call    cs:__imp_GetCurrentThreadId
0x180098b6e  mov     r8, [rdi+110h]
0x180098b75  lea     rdx, unk_180112E18
0x180098b7c  mov     [rsp+68h+var_28], eax
0x180098b80  add     r8, 8
0x180098b84  lea     rax, [rsp+68h+var_28]
0x180098b89  mov     dword ptr [rsp+68h+var_20], 0
0x180098b91  mov     [rsp+68h+var_38], rax
0x180098b96  mov     rcx, rbx
0x180098b99  lea     rax, [rsp+68h+var_20]
0x180098b9e  mov     [rsp+68h+var_18], 1000000h
0x180098ba7  mov     [rsp+68h+var_40], rax
0x180098bac  lea     rax, [rsp+68h+var_18]
0x180098bb1  mov     [rsp+68h+var_48], rax
0x180098bb6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180098bbb  mov     rcx, rdi
0x180098bbe  mov     rbx, [rsp+68h+arg_8]
0x180098bc3  add     rsp, 60h
0x180098bc7  pop     rdi
0x180098bc8  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
