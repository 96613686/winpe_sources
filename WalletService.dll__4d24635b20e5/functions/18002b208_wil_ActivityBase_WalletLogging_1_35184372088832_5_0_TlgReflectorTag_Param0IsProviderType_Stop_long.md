# wil::ActivityBase<WalletLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18002b208`
- end: `0x18002b2de`
- name: `?Stop@?$ActivityBase@VWalletLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180029890`

## callees

- `0x180001afc`
- `0x180001d1c`
- `0x180005764`
- `0x180027f2c`
- `0x18002a340`
- `0x18002a708`
- `0x18002ae50`
- `0x18002b208`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b280`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b280`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<WalletLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
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
  __int64 v12; // r9
  DWORD v14; // [rsp+60h] [rbp+8h] BYREF
  RTL_SRWLOCK *v15; // [rsp+70h] [rbp+18h] BYREF
  __int64 v16; // [rsp+78h] [rbp+20h] BYREF

  v14 = 0;
  wil::ActivityBase<WalletLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(a1, &v15);
  v4 = wil::ActivityBase<WalletLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WalletLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         a2,
         &v14);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v15);
  if ( v4 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v8 = WalletLogging::Provider();
    v9 = (__int64)v8;
    if ( *(_DWORD *)v8 > 5u && (unsigned __int8)tlgKeywordOn(v8, 0x200000000000LL, v6) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v11 = a1[34];
      v14 = CurrentThreadId;
      LODWORD(v15) = a2;
      v16 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (__int64)word_180062732,
        v11 + 8,
        v12,
        (__int64)&v16,
        (__int64)&v15,
        (__int64)&v14);
    }
  }
  return wil::ActivityBase<WalletLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
           a1,
           v5,
           v6,
           v7);
}

```

## disassembly

```asm
0x18002b208  push    rbx
0x18002b20a  push    rsi
0x18002b20b  push    rdi
0x18002b20c  sub     rsp, 40h
0x18002b210  mov     esi, edx
0x18002b212  mov     [rsp+58h+arg_0], 0
0x18002b21a  lea     rdx, [rsp+58h+arg_10]
0x18002b21f  mov     rdi, rcx
0x18002b222  call    ?LockExclusive@?$ActivityBase@VWalletLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WalletLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002b227  mov     rcx, [rdi+110h]
0x18002b22e  lea     r8, [rsp+58h+arg_0]
0x18002b233  mov     edx, esi
0x18002b235  call    ?SetStopResult@?$ActivityData@VWalletLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VWalletLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<WalletLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WalletLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18002b23a  lea     rcx, [rsp+58h+arg_10]
0x18002b23f  mov     bl, al
0x18002b241  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002b246  test    bl, bl
0x18002b248  jz      short loc_18002B25B
0x18002b24a  mov     rax, [rdi]
0x18002b24d  mov     rcx, rdi
0x18002b250  mov     rax, [rax+8]
0x18002b254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b259  jmp     short loc_18002B2CF
0x18002b25b  call    ?Provider@WalletLogging@@SAPEBU_tlgProvider_t@@XZ; WalletLogging::Provider(void)
0x18002b260  mov     rbx, rax
0x18002b263  mov     ecx, [rax]
0x18002b265  cmp     ecx, 5
0x18002b268  jbe     short loc_18002B2CF
0x18002b26a  mov     rdx, 200000000000h
0x18002b274  mov     rcx, rax
0x18002b277  call    _tlgKeywordOn
0x18002b27c  test    al, al
0x18002b27e  jz      short loc_18002B2CF
0x18002b280  call    cs:__imp_GetCurrentThreadId
0x18002b286  mov     r8, [rdi+110h]
0x18002b28d  lea     rdx, word_180062732
0x18002b294  mov     [rsp+58h+arg_0], eax
0x18002b298  add     r8, 8
0x18002b29c  lea     rax, [rsp+58h+arg_0]
0x18002b2a1  mov     dword ptr [rsp+58h+arg_10], esi
0x18002b2a5  mov     [rsp+58h+var_28], rax
0x18002b2aa  mov     rcx, rbx
0x18002b2ad  lea     rax, [rsp+58h+arg_10]
0x18002b2b2  mov     [rsp+58h+arg_18], 1000000h
0x18002b2bb  mov     [rsp+58h+var_30], rax
0x18002b2c0  lea     rax, [rsp+58h+arg_18]
0x18002b2c5  mov     [rsp+58h+var_38], rax
0x18002b2ca  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002b2cf  mov     rcx, rdi
0x18002b2d2  add     rsp, 40h
0x18002b2d6  pop     rdi
0x18002b2d7  pop     rsi
0x18002b2d8  pop     rbx
0x18002b2d9  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWalletLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WalletLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
