# wil::ActivityBase<NetSetupTraceLogging,0,4,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18001b25c`
- end: `0x18001b33f`
- name: `?Stop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$03$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1800193c4`

## callees

- `0x180001860`
- `0x18000e54c`
- `0x18001b25c`
- `0x180033720`
- `0x18003a9a0`
- `0x18003aa44`
- `0x180046ed0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b29e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b29e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b2da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b2da`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<NetSetupTraceLogging,0,4,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  char v2; // di
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  const struct _tlgProvider_t *v6; // rax
  int v7; // edi
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  PSRWLOCK SRWLock; // [rsp+50h] [rbp+8h] BYREF
  DWORD v13; // [rsp+58h] [rbp+10h] BYREF
  __int64 v14; // [rsp+60h] [rbp+18h] BYREF

  v13 = 0;
  wil::ActivityBase<NetSetupTraceLogging,0,4,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(a1, &SRWLock);
  v2 = wil::ActivityBase<NetSetupTraceLogging,0,4,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<NetSetupTraceLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         0,
         &v13);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v2 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v6 = NetSetupTraceLogging::Provider();
    v7 = (int)v6;
    if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 4, v4, v5) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v9 = a1[34];
      v13 = CurrentThreadId;
      LODWORD(SRWLock) = 0;
      v14 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (int)word_1800B1A02,
        v9 + 8,
        v10,
        (__int64)&v14,
        (__int64)&SRWLock,
        (__int64)&v13);
    }
  }
  return wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
           a1,
           v3,
           v4,
           v5);
}

```

## disassembly

```asm
0x18001b25c  mov     rax, rsp
0x18001b25f  mov     [rax+20h], rbx
0x18001b263  mov     [rax+10h], edx
0x18001b266  push    rdi
0x18001b267  sub     rsp, 40h
0x18001b26b  lea     rdx, [rax+8]
0x18001b26f  mov     dword ptr [rax+10h], 0
0x18001b276  mov     rbx, rcx
0x18001b279  call    ?LockExclusive@?$ActivityBase@VNetSetupTraceLogging@@$0A@$03$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<NetSetupTraceLogging,0,4,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001b27e  mov     rcx, [rbx+110h]
0x18001b285  lea     r8, [rsp+48h+arg_8]
0x18001b28a  xor     edx, edx
0x18001b28c  call    ?SetStopResult@?$ActivityData@VNetSetupTraceLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VNetSetupTraceLogging@@$0A@$03$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<NetSetupTraceLogging,0,4,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<NetSetupTraceLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18001b291  mov     rcx, [rsp+48h+SRWLock]; SRWLock
0x18001b296  mov     dil, al
0x18001b299  test    rcx, rcx
0x18001b29c  jz      short loc_18001B2A4
0x18001b29e  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b2a4  test    dil, dil
0x18001b2a7  jz      short loc_18001B2BA
0x18001b2a9  mov     rax, [rbx]
0x18001b2ac  mov     rcx, rbx
0x18001b2af  mov     rax, [rax+8]
0x18001b2b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2b8  jmp     short loc_18001B32D
0x18001b2ba  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x18001b2bf  mov     rdi, rax
0x18001b2c2  mov     ecx, [rax]
0x18001b2c4  cmp     ecx, 5
0x18001b2c7  jbe     short loc_18001B32D
0x18001b2c9  mov     edx, 4
0x18001b2ce  mov     rcx, rax
0x18001b2d1  call    _tlgKeywordOn
0x18001b2d6  test    al, al
0x18001b2d8  jz      short loc_18001B32D
0x18001b2da  call    cs:__imp_GetCurrentThreadId
0x18001b2e0  mov     r8, [rbx+110h]
0x18001b2e7  lea     rdx, word_1800B1A02
0x18001b2ee  mov     [rsp+48h+arg_8], eax
0x18001b2f2  add     r8, 8
0x18001b2f6  lea     rax, [rsp+48h+arg_8]
0x18001b2fb  mov     dword ptr [rsp+48h+SRWLock], 0
0x18001b303  mov     [rsp+48h+var_18], rax
0x18001b308  mov     rcx, rdi
0x18001b30b  lea     rax, [rsp+48h+SRWLock]
0x18001b310  mov     [rsp+48h+arg_10], 1000000h
0x18001b319  mov     [rsp+48h+var_20], rax
0x18001b31e  lea     rax, [rsp+48h+arg_10]
0x18001b323  mov     [rsp+48h+var_28], rax
0x18001b328  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001b32d  mov     rcx, rbx
0x18001b330  mov     rbx, [rsp+48h+arg_18]
0x18001b335  add     rsp, 40h
0x18001b339  pop     rdi
0x18001b33a  jmp     ?IgnoreCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
