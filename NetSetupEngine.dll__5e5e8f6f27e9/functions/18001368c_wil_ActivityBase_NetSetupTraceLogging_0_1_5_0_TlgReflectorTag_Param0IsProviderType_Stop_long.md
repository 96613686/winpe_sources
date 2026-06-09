# wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18001368c`
- end: `0x18001376f`
- name: `?Stop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `227`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180011e54`
- `0x180014324`
- `0x1800274f0`
- `0x180027b90`
- `0x18002d580`
- `0x180038b30`
- `0x18004e450`
- `0x180076b18`

## callees

- `0x180001860`
- `0x18000e54c`
- `0x18001368c`
- `0x180033720`
- `0x18003aeb8`
- `0x18003b9e8`
- `0x180046ed0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800136ce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800136ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001370a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001370a`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
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
  wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(a1, &SRWLock);
  v2 = wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<NetSetupTraceLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
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
    if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 1, v4, v5) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v9 = a1[34];
      v13 = CurrentThreadId;
      LODWORD(SRWLock) = 0;
      v14 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (int)byte_1800B1871,
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
0x18001368c  mov     rax, rsp
0x18001368f  mov     [rax+20h], rbx
0x180013693  mov     [rax+10h], edx
0x180013696  push    rdi
0x180013697  sub     rsp, 40h
0x18001369b  lea     rdx, [rax+8]
0x18001369f  mov     dword ptr [rax+10h], 0
0x1800136a6  mov     rbx, rcx
0x1800136a9  call    ?LockExclusive@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800136ae  mov     rcx, [rbx+110h]
0x1800136b5  lea     r8, [rsp+48h+arg_8]
0x1800136ba  xor     edx, edx
0x1800136bc  call    ?SetStopResult@?$ActivityData@VNetSetupTraceLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<NetSetupTraceLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x1800136c1  mov     rcx, [rsp+48h+SRWLock]; SRWLock
0x1800136c6  mov     dil, al
0x1800136c9  test    rcx, rcx
0x1800136cc  jz      short loc_1800136D4
0x1800136ce  call    cs:__imp_ReleaseSRWLockExclusive
0x1800136d4  test    dil, dil
0x1800136d7  jz      short loc_1800136EA
0x1800136d9  mov     rax, [rbx]
0x1800136dc  mov     rcx, rbx
0x1800136df  mov     rax, [rax+8]
0x1800136e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800136e8  jmp     short loc_18001375D
0x1800136ea  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x1800136ef  mov     rdi, rax
0x1800136f2  mov     ecx, [rax]
0x1800136f4  cmp     ecx, 5
0x1800136f7  jbe     short loc_18001375D
0x1800136f9  mov     edx, 1
0x1800136fe  mov     rcx, rax
0x180013701  call    _tlgKeywordOn
0x180013706  test    al, al
0x180013708  jz      short loc_18001375D
0x18001370a  call    cs:__imp_GetCurrentThreadId
0x180013710  mov     r8, [rbx+110h]
0x180013717  lea     rdx, byte_1800B1871
0x18001371e  mov     [rsp+48h+arg_8], eax
0x180013722  add     r8, 8
0x180013726  lea     rax, [rsp+48h+arg_8]
0x18001372b  mov     dword ptr [rsp+48h+SRWLock], 0
0x180013733  mov     [rsp+48h+var_18], rax
0x180013738  mov     rcx, rdi
0x18001373b  lea     rax, [rsp+48h+SRWLock]
0x180013740  mov     [rsp+48h+arg_10], 1000000h
0x180013749  mov     [rsp+48h+var_20], rax
0x18001374e  lea     rax, [rsp+48h+arg_10]
0x180013753  mov     [rsp+48h+var_28], rax
0x180013758  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001375d  mov     rcx, rbx
0x180013760  mov     rbx, [rsp+48h+arg_18]
0x180013765  add     rsp, 40h
0x180013769  pop     rdi
0x18001376a  jmp     ?IgnoreCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
