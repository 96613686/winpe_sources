# wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x1800890e0`
- end: `0x1800891b0`
- name: `?Stop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `208`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180084140`
- `0x180084c64`
- `0x180085530`
- `0x1800c0894`
- `0x1800c3d60`
- `0x1800c6298`
- `0x1800c809c`

## callees

- `0x1800019ec`
- `0x18000243c`
- `0x18003a900`
- `0x18003bf74`
- `0x18003c234`
- `0x18003c9b8`
- `0x18003d458`
- `0x1800889f0`
- `0x1800890e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180089157`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180089157`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 a1,
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
  __int64 v15[3]; // [rsp+50h] [rbp-18h] BYREF

  v13 = 0;
  v14 = 0;
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v14);
  v4 = wil::ActivityBase<CortanaSearchTelemetryLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CortanaSearchTelemetryLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         *(_QWORD *)(a1 + 272),
         a2,
         &v13);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v14);
  if ( v4 )
  {
    wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
      a1,
      v13);
  }
  else
  {
    v5 = CortanaSearchTelemetryLogging::Provider();
    v8 = (int)v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 1, v6, v7) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v10 = *(_QWORD *)(a1 + 272);
      v13 = CurrentThreadId;
      LODWORD(v14) = a2;
      v15[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v8,
        (unsigned int)word_1801121D2,
        v10 + 8,
        v11,
        (__int64)v15,
        (__int64)&v14,
        (__int64)&v13);
    }
  }
  return wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x1800890e0  push    rbp
0x1800890e2  push    rbx
0x1800890e3  push    rsi
0x1800890e4  push    rdi
0x1800890e5  mov     rbp, rsp
0x1800890e8  sub     rsp, 68h
0x1800890ec  mov     esi, edx
0x1800890ee  mov     [rbp+var_28], 0
0x1800890f5  lea     rdx, [rbp+var_20]
0x1800890f9  mov     [rbp+var_20], 0
0x180089101  mov     rdi, rcx
0x180089104  call    ?LockExclusive@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180089109  mov     rcx, [rdi+110h]
0x180089110  lea     r8, [rbp+var_28]
0x180089114  mov     edx, esi
0x180089116  call    ?SetStopResult@?$ActivityData@VCortanaSearchTelemetryLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<CortanaSearchTelemetryLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CortanaSearchTelemetryLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18008911b  lea     rcx, [rbp+var_20]
0x18008911f  mov     bl, al
0x180089121  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180089126  test    bl, bl
0x180089128  jz      short loc_180089137
0x18008912a  mov     edx, [rbp+var_28]
0x18008912d  mov     rcx, rdi
0x180089130  call    ?ReportStopActivity@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x180089135  jmp     short loc_1800891A0
0x180089137  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x18008913c  mov     rbx, rax
0x18008913f  mov     ecx, [rax]
0x180089141  cmp     ecx, 5
0x180089144  jbe     short loc_1800891A0
0x180089146  mov     edx, 1
0x18008914b  mov     rcx, rax
0x18008914e  call    _tlgKeywordOn
0x180089153  test    al, al
0x180089155  jz      short loc_1800891A0
0x180089157  call    cs:__imp_GetCurrentThreadId
0x18008915d  mov     r8, [rdi+110h]
0x180089164  lea     rdx, word_1801121D2
0x18008916b  mov     [rbp+var_28], eax
0x18008916e  add     r8, 8
0x180089172  lea     rax, [rbp+var_28]
0x180089176  mov     dword ptr [rbp+var_20], esi
0x180089179  mov     [rsp+68h+var_38], rax
0x18008917e  mov     rcx, rbx
0x180089181  lea     rax, [rbp+var_20]
0x180089185  mov     [rbp+var_18], 1000000h
0x18008918d  mov     [rsp+68h+var_40], rax
0x180089192  lea     rax, [rbp+var_18]
0x180089196  mov     [rsp+68h+var_48], rax
0x18008919b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800891a0  mov     rcx, rdi
0x1800891a3  add     rsp, 68h
0x1800891a7  pop     rdi
0x1800891a8  pop     rsi
0x1800891a9  pop     rbx
0x1800891aa  pop     rbp
0x1800891ab  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
