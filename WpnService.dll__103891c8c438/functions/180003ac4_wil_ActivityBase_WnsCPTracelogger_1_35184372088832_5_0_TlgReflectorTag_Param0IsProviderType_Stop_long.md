# wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180003ac4`
- end: `0x180003baf`
- name: `?Stop@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `235`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180003320`
- `0x180020b74`

## callees

- `0x180003ac4`
- `0x18000d830`
- `0x18000e720`
- `0x18000f270`
- `0x18000f2f0`
- `0x180011860`
- `0x180018430`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003b06`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003b06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003b47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003b47`

## pseudocode

```c
void __fastcall wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  char v2; // di
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v8; // r8
  PSRWLOCK SRWLock; // [rsp+50h] [rbp+8h] BYREF
  DWORD v10; // [rsp+58h] [rbp+10h] BYREF
  __int64 v11; // [rsp+60h] [rbp+18h] BYREF

  v10 = 0;
  wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v2 = wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WnsCPTracelogger,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         0,
         &v10);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v2 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v3 = WnsCPTracelogger::Provider();
    v6 = (__int64)v3;
    if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x200000000000LL, v4, v5) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v8 = a1[34];
      v10 = CurrentThreadId;
      LODWORD(SRWLock) = 0;
      v11 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (unsigned __int8 *)&word_18003FE4E,
        (const GUID *)(v8 + 8),
        0,
        (__int64)&v11,
        (__int64)&SRWLock,
        (__int64)&v10);
    }
  }
  wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x180003ac4  mov     rax, rsp
0x180003ac7  mov     [rax+20h], rbx
0x180003acb  mov     [rax+10h], edx
0x180003ace  push    rdi
0x180003acf  sub     rsp, 40h
0x180003ad3  lea     rdx, [rax+8]
0x180003ad7  mov     dword ptr [rax+10h], 0
0x180003ade  mov     rbx, rcx
0x180003ae1  call    ?LockExclusive@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180003ae6  mov     rcx, [rbx+110h]
0x180003aed  lea     r8, [rsp+48h+arg_8]
0x180003af2  xor     edx, edx
0x180003af4  call    ?SetStopResult@?$ActivityData@VWnsCPTracelogger@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WnsCPTracelogger,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x180003af9  mov     rcx, [rsp+48h+SRWLock]; SRWLock
0x180003afe  mov     dil, al
0x180003b01  test    rcx, rcx
0x180003b04  jz      short loc_180003B0C
0x180003b06  call    cs:__imp_ReleaseSRWLockExclusive
0x180003b0c  test    dil, dil
0x180003b0f  jz      short loc_180003B22
0x180003b11  mov     rax, [rbx]
0x180003b14  mov     rcx, rbx
0x180003b17  mov     rax, [rax+8]
0x180003b1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b20  jmp     short loc_180003B9D
0x180003b22  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x180003b27  mov     rdi, rax
0x180003b2a  mov     ecx, [rax]
0x180003b2c  cmp     ecx, 5
0x180003b2f  jbe     short loc_180003B9D
0x180003b31  mov     rdx, 200000000000h
0x180003b3b  mov     rcx, rax
0x180003b3e  call    _tlgKeywordOn
0x180003b43  test    al, al
0x180003b45  jz      short loc_180003B9D
0x180003b47  call    cs:__imp_GetCurrentThreadId
0x180003b4d  mov     r8, [rbx+110h]
0x180003b54  lea     rdx, word_18003FE4E
0x180003b5b  mov     [rsp+48h+arg_8], eax
0x180003b5f  add     r8, 8
0x180003b63  lea     rax, [rsp+48h+arg_8]
0x180003b68  mov     dword ptr [rsp+48h+SRWLock], 0
0x180003b70  mov     [rsp+48h+var_18], rax
0x180003b75  xor     r9d, r9d
0x180003b78  lea     rax, [rsp+48h+SRWLock]
0x180003b7d  mov     [rsp+48h+arg_10], 1000000h
0x180003b86  mov     [rsp+48h+var_20], rax
0x180003b8b  mov     rcx, rdi
0x180003b8e  lea     rax, [rsp+48h+arg_10]
0x180003b93  mov     [rsp+48h+var_28], rax
0x180003b98  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180003b9d  mov     rcx, rbx
0x180003ba0  mov     rbx, [rsp+48h+arg_18]
0x180003ba5  add     rsp, 40h
0x180003ba9  pop     rdi
0x180003baa  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
