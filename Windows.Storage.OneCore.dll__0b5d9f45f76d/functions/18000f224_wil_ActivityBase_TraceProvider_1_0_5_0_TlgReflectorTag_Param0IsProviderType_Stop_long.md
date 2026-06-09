# wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18000f224`
- end: `0x18000f2e1`
- name: `?Stop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `189`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `24`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000d31c`
- `0x180015a74`
- `0x180016ff8`
- `0x18001702c`
- `0x180017060`
- `0x180017094`
- `0x1800170c8`
- `0x1800170fc`
- `0x180017130`
- `0x180017164`
- `0x180017198`
- `0x1800171cc`
- `0x180017200`
- `0x180020f50`
- `0x180021060`
- `0x180021160`
- `0x1800212c0`
- `0x1800213c0`
- `0x180021500`
- `0x180021610`
- `0x180021710`
- `0x180021820`
- `0x180021920`
- `0x180021a40`

## callees

- `0x180001650`
- `0x180004b18`
- `0x18000e2d8`
- `0x18000e44c`
- `0x18000e964`
- `0x18000ead4`
- `0x18000f0b0`
- `0x18000f224`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f283`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f283`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 a1,
        unsigned int a2)
{
  char v4; // bl
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  const struct _tlgProvider_t *v8; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v10; // r8
  __int64 v11; // r9
  DWORD v13; // [rsp+60h] [rbp+8h] BYREF
  RTL_SRWLOCK *v14; // [rsp+70h] [rbp+18h] BYREF
  __int64 v15; // [rsp+78h] [rbp+20h] BYREF

  v13 = 0;
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(a1, &v14);
  v4 = wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<TraceProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         *(_QWORD *)(a1 + 272),
         a2,
         &v13);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v14);
  if ( v4 )
  {
    wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(a1, v13);
  }
  else
  {
    v8 = TraceProvider::Provider();
    if ( *(_DWORD *)v8 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v10 = *(_QWORD *)(a1 + 272);
      v13 = CurrentThreadId;
      LODWORD(v14) = a2;
      v15 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v8,
        (__int64)word_18002A15A,
        v10 + 8,
        v11,
        (__int64)&v15,
        (__int64)&v14,
        (__int64)&v13);
    }
  }
  return wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
           a1,
           v5,
           v6,
           v7);
}

```

## disassembly

```asm
0x18000f224  push    rbx
0x18000f226  push    rsi
0x18000f227  push    rdi
0x18000f228  sub     rsp, 40h
0x18000f22c  mov     esi, edx
0x18000f22e  mov     [rsp+58h+arg_0], 0
0x18000f236  lea     rdx, [rsp+58h+arg_10]
0x18000f23b  mov     rdi, rcx
0x18000f23e  call    ?LockExclusive@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000f243  mov     rcx, [rdi+110h]
0x18000f24a  lea     r8, [rsp+58h+arg_0]
0x18000f24f  mov     edx, esi
0x18000f251  call    ?SetStopResult@?$ActivityData@VTraceProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<TraceProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18000f256  lea     rcx, [rsp+58h+arg_10]
0x18000f25b  mov     bl, al
0x18000f25d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000f262  test    bl, bl
0x18000f264  jz      short loc_18000F274
0x18000f266  mov     edx, [rsp+58h+arg_0]
0x18000f26a  mov     rcx, rdi
0x18000f26d  call    ?ReportStopActivity@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x18000f272  jmp     short loc_18000F2D2
0x18000f274  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x18000f279  mov     rbx, rax
0x18000f27c  mov     ecx, [rax]
0x18000f27e  cmp     ecx, 5
0x18000f281  jbe     short loc_18000F2D2
0x18000f283  call    cs:__imp_GetCurrentThreadId
0x18000f289  mov     r8, [rdi+110h]
0x18000f290  lea     rdx, word_18002A15A
0x18000f297  mov     [rsp+58h+arg_0], eax
0x18000f29b  add     r8, 8
0x18000f29f  lea     rax, [rsp+58h+arg_0]
0x18000f2a4  mov     dword ptr [rsp+58h+arg_10], esi
0x18000f2a8  mov     [rsp+58h+var_28], rax
0x18000f2ad  mov     rcx, rbx
0x18000f2b0  lea     rax, [rsp+58h+arg_10]
0x18000f2b5  mov     [rsp+58h+arg_18], 1000000h
0x18000f2be  mov     [rsp+58h+var_30], rax
0x18000f2c3  lea     rax, [rsp+58h+arg_18]
0x18000f2c8  mov     [rsp+58h+var_38], rax
0x18000f2cd  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000f2d2  mov     rcx, rdi
0x18000f2d5  add     rsp, 40h
0x18000f2d9  pop     rdi
0x18000f2da  pop     rsi
0x18000f2db  pop     rbx
0x18000f2dc  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
