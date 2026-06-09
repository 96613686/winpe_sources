# wil::ActivityBase<WnsCPTracelogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18000cd88`
- end: `0x18000ce73`
- name: `?Stop@?$ActivityBase@VWnsCPTracelogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `235`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18000b720`

## callees

- `0x18000cd88`
- `0x18000d7b0`
- `0x18000d830`
- `0x18000f2f0`
- `0x1800117fc`
- `0x180017c30`
- `0x180018430`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cdca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cdca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ce0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ce0b`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<WnsCPTracelogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  char v2; // di
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  PSRWLOCK SRWLock; // [rsp+50h] [rbp+8h] BYREF
  DWORD v12; // [rsp+58h] [rbp+10h] BYREF
  __int64 v13; // [rsp+60h] [rbp+18h] BYREF

  v12 = 0;
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(a1, &SRWLock);
  v2 = wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ServiceHostLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         0,
         &v12);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v2 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v6 = WnsCPTracelogger::Provider();
    v7 = (__int64)v6;
    if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL, v4, v5) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v9 = a1[34];
      v12 = CurrentThreadId;
      LODWORD(SRWLock) = 0;
      v13 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (unsigned __int8 *)byte_180040F6B,
        (const GUID *)(v9 + 8),
        0,
        (__int64)&v13,
        (__int64)&SRWLock,
        (__int64)&v12);
    }
  }
  return wil::ActivityBase<WnsCPTracelogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
           a1,
           v3,
           v4,
           v5);
}

```

## disassembly

```asm
0x18000cd88  mov     rax, rsp
0x18000cd8b  mov     [rax+20h], rbx
0x18000cd8f  mov     [rax+10h], edx
0x18000cd92  push    rdi
0x18000cd93  sub     rsp, 40h
0x18000cd97  lea     rdx, [rax+8]
0x18000cd9b  mov     dword ptr [rax+10h], 0
0x18000cda2  mov     rbx, rcx
0x18000cda5  call    ?LockExclusive@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000cdaa  mov     rcx, [rbx+110h]
0x18000cdb1  lea     r8, [rsp+48h+arg_8]
0x18000cdb6  xor     edx, edx
0x18000cdb8  call    ?SetStopResult@?$ActivityData@VServiceHostLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ServiceHostLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18000cdbd  mov     rcx, [rsp+48h+SRWLock]; SRWLock
0x18000cdc2  mov     dil, al
0x18000cdc5  test    rcx, rcx
0x18000cdc8  jz      short loc_18000CDD0
0x18000cdca  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cdd0  test    dil, dil
0x18000cdd3  jz      short loc_18000CDE6
0x18000cdd5  mov     rax, [rbx]
0x18000cdd8  mov     rcx, rbx
0x18000cddb  mov     rax, [rax+8]
0x18000cddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cde4  jmp     short loc_18000CE61
0x18000cde6  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18000cdeb  mov     rdi, rax
0x18000cdee  mov     ecx, [rax]
0x18000cdf0  cmp     ecx, 5
0x18000cdf3  jbe     short loc_18000CE61
0x18000cdf5  mov     rdx, 400000000000h
0x18000cdff  mov     rcx, rax
0x18000ce02  call    _tlgKeywordOn
0x18000ce07  test    al, al
0x18000ce09  jz      short loc_18000CE61
0x18000ce0b  call    cs:__imp_GetCurrentThreadId
0x18000ce11  mov     r8, [rbx+110h]
0x18000ce18  lea     rdx, byte_180040F6B
0x18000ce1f  mov     [rsp+48h+arg_8], eax
0x18000ce23  add     r8, 8
0x18000ce27  lea     rax, [rsp+48h+arg_8]
0x18000ce2c  mov     dword ptr [rsp+48h+SRWLock], 0
0x18000ce34  mov     [rsp+48h+var_18], rax
0x18000ce39  xor     r9d, r9d
0x18000ce3c  lea     rax, [rsp+48h+SRWLock]
0x18000ce41  mov     [rsp+48h+arg_10], 1000000h
0x18000ce4a  mov     [rsp+48h+var_20], rax
0x18000ce4f  mov     rcx, rdi
0x18000ce52  lea     rax, [rsp+48h+arg_10]
0x18000ce57  mov     [rsp+48h+var_28], rax
0x18000ce5c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000ce61  mov     rcx, rbx
0x18000ce64  mov     rbx, [rsp+48h+arg_18]
0x18000ce69  add     rsp, 40h
0x18000ce6d  pop     rdi
0x18000ce6e  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
