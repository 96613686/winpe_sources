# wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180019f30`
- end: `0x18001a006`
- name: `?Stop@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `214`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18001b3e0`
- `0x18001b6e0`
- `0x18001fb70`
- `0x180020010`
- `0x1800202f0`
- `0x1800203b0`

## callees

- `0x18000133c`
- `0x180001acc`
- `0x180011488`
- `0x180015bf0`
- `0x18001608c`
- `0x180016fcc`
- `0x1800194f4`
- `0x180019f30`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019fa8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019fa8`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1,
        unsigned int a2)
{
  char v4; // bl
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  __int64 v7; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  DWORD v12; // [rsp+60h] [rbp+8h] BYREF
  RTL_SRWLOCK *v13; // [rsp+70h] [rbp+18h] BYREF
  __int64 v14; // [rsp+78h] [rbp+20h] BYREF

  v12 = 0;
  wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v13);
  v4 = wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CoreGlobConfigTraceLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         a2,
         &v12);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
  if ( v4 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v5 = CoreGlobConfigTraceLogging::Provider();
    v7 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL, v6) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v9 = a1[34];
      v12 = CurrentThreadId;
      LODWORD(v13) = a2;
      v14 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (__int64)&unk_18002AA78,
        v9 + 8,
        v10,
        (__int64)&v14,
        (__int64)&v13,
        (__int64)&v12);
    }
  }
  return wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x180019f30  push    rbx
0x180019f32  push    rsi
0x180019f33  push    rdi
0x180019f34  sub     rsp, 40h
0x180019f38  mov     esi, edx
0x180019f3a  mov     [rsp+58h+arg_0], 0
0x180019f42  lea     rdx, [rsp+58h+arg_10]
0x180019f47  mov     rdi, rcx
0x180019f4a  call    ?LockExclusive@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180019f4f  mov     rcx, [rdi+110h]
0x180019f56  lea     r8, [rsp+58h+arg_0]
0x180019f5b  mov     edx, esi
0x180019f5d  call    ?SetStopResult@?$ActivityData@VCoreGlobConfigTraceLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CoreGlobConfigTraceLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x180019f62  lea     rcx, [rsp+58h+arg_10]
0x180019f67  mov     bl, al
0x180019f69  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180019f6e  test    bl, bl
0x180019f70  jz      short loc_180019F83
0x180019f72  mov     rax, [rdi]
0x180019f75  mov     rcx, rdi
0x180019f78  mov     rax, [rax+8]
0x180019f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f81  jmp     short loc_180019FF7
0x180019f83  call    ?Provider@CoreGlobConfigTraceLogging@@SAPEBU_tlgProvider_t@@XZ; CoreGlobConfigTraceLogging::Provider(void)
0x180019f88  mov     rbx, rax
0x180019f8b  mov     ecx, [rax]
0x180019f8d  cmp     ecx, 5
0x180019f90  jbe     short loc_180019FF7
0x180019f92  mov     rdx, 200000000000h
0x180019f9c  mov     rcx, rax
0x180019f9f  call    _tlgKeywordOn
0x180019fa4  test    al, al
0x180019fa6  jz      short loc_180019FF7
0x180019fa8  call    cs:__imp_GetCurrentThreadId
0x180019fae  mov     r8, [rdi+110h]
0x180019fb5  lea     rdx, unk_18002AA78
0x180019fbc  mov     [rsp+58h+arg_0], eax
0x180019fc0  add     r8, 8
0x180019fc4  lea     rax, [rsp+58h+arg_0]
0x180019fc9  mov     dword ptr [rsp+58h+arg_10], esi
0x180019fcd  mov     [rsp+58h+var_28], rax
0x180019fd2  mov     rcx, rbx
0x180019fd5  lea     rax, [rsp+58h+arg_10]
0x180019fda  mov     [rsp+58h+arg_18], 1000000h
0x180019fe3  mov     [rsp+58h+var_30], rax
0x180019fe8  lea     rax, [rsp+58h+arg_18]
0x180019fed  mov     [rsp+58h+var_38], rax
0x180019ff2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180019ff7  mov     rcx, rdi
0x180019ffa  add     rsp, 40h
0x180019ffe  pop     rdi
0x180019fff  pop     rsi
0x18001a000  pop     rbx
0x18001a001  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
