# wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180023efc`
- end: `0x180023fdd`
- name: `?Stop@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `225`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18001fab0`

## callees

- `0x18000f270`
- `0x18000f2f0`
- `0x1800117fc`
- `0x180017104`
- `0x1800172bc`
- `0x180018430`
- `0x180023efc`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023f3b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023f3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023f7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023f7c`

## pseudocode

```c
void __fastcall wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1,
        unsigned int a2)
{
  char v4; // di
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v10; // r8
  DWORD v11; // [rsp+60h] [rbp+8h] BYREF
  PSRWLOCK SRWLock; // [rsp+70h] [rbp+18h] BYREF
  __int64 v13; // [rsp+78h] [rbp+20h] BYREF

  v11 = 0;
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v4 = wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ServiceHostLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         a2,
         &v11);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v4 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v5 = ServiceHostLogging::Provider();
    v8 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL, v6, v7) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v10 = a1[34];
      v11 = CurrentThreadId;
      LODWORD(SRWLock) = a2;
      v13 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v8,
        (unsigned __int8 *)word_18003CBD2,
        (const GUID *)(v10 + 8),
        0,
        (__int64)&v13,
        (__int64)&SRWLock,
        (__int64)&v11);
    }
  }
  wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x180023efc  push    rbx
0x180023efe  push    rsi
0x180023eff  push    rdi
0x180023f00  sub     rsp, 40h
0x180023f04  mov     esi, edx
0x180023f06  mov     [rsp+58h+arg_0], 0
0x180023f0e  lea     rdx, [rsp+58h+SRWLock]
0x180023f13  mov     rbx, rcx
0x180023f16  call    ?LockExclusive@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180023f1b  mov     rcx, [rbx+110h]
0x180023f22  lea     r8, [rsp+58h+arg_0]
0x180023f27  mov     edx, esi
0x180023f29  call    ?SetStopResult@?$ActivityData@VServiceHostLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ServiceHostLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x180023f2e  mov     rcx, [rsp+58h+SRWLock]; SRWLock
0x180023f33  mov     dil, al
0x180023f36  test    rcx, rcx
0x180023f39  jz      short loc_180023F41
0x180023f3b  call    cs:__imp_ReleaseSRWLockExclusive
0x180023f41  test    dil, dil
0x180023f44  jz      short loc_180023F57
0x180023f46  mov     rax, [rbx]
0x180023f49  mov     rcx, rbx
0x180023f4c  mov     rax, [rax+8]
0x180023f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f55  jmp     short loc_180023FCE
0x180023f57  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x180023f5c  mov     rdi, rax
0x180023f5f  mov     ecx, [rax]
0x180023f61  cmp     ecx, 5
0x180023f64  jbe     short loc_180023FCE
0x180023f66  mov     rdx, 400000000000h
0x180023f70  mov     rcx, rax
0x180023f73  call    _tlgKeywordOn
0x180023f78  test    al, al
0x180023f7a  jz      short loc_180023FCE
0x180023f7c  call    cs:__imp_GetCurrentThreadId
0x180023f82  mov     r8, [rbx+110h]
0x180023f89  lea     rdx, word_18003CBD2
0x180023f90  mov     [rsp+58h+arg_0], eax
0x180023f94  add     r8, 8
0x180023f98  lea     rax, [rsp+58h+arg_0]
0x180023f9d  mov     dword ptr [rsp+58h+SRWLock], esi
0x180023fa1  mov     [rsp+58h+var_28], rax
0x180023fa6  xor     r9d, r9d
0x180023fa9  lea     rax, [rsp+58h+SRWLock]
0x180023fae  mov     [rsp+58h+arg_18], 1000000h
0x180023fb7  mov     [rsp+58h+var_30], rax
0x180023fbc  mov     rcx, rdi
0x180023fbf  lea     rax, [rsp+58h+arg_18]
0x180023fc4  mov     [rsp+58h+var_38], rax
0x180023fc9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180023fce  mov     rcx, rbx
0x180023fd1  add     rsp, 40h
0x180023fd5  pop     rdi
0x180023fd6  pop     rsi
0x180023fd7  pop     rbx
0x180023fd8  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
