# wil::ActivityBase<RemoteSessionTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18001f5ec`
- end: `0x18001f6c2`
- name: `?Stop@?$ActivityBase@VRemoteSessionTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `214`
- prototype: ``
- caller_count: `11`
- callee_count: `8`
- tags: ``

## callers

- `0x180011de0`
- `0x180014840`
- `0x18001f310`
- `0x18001f4a0`
- `0x18001fea0`
- `0x180049570`
- `0x18004ad00`
- `0x18004b000`
- `0x18004b370`
- `0x18004b500`
- `0x18004c060`

## callees

- `0x180001900`
- `0x18000192c`
- `0x18001a9e8`
- `0x18001f5ec`
- `0x18001fcf0`
- `0x18004a360`
- `0x18004d080`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f664`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f664`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f623`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f623`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<RemoteSessionTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1,
        unsigned int a2)
{
  char v4; // di
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  __int64 v12; // r9
  DWORD v14; // [rsp+60h] [rbp+8h] BYREF
  PSRWLOCK SRWLock; // [rsp+70h] [rbp+18h] BYREF
  __int64 v16; // [rsp+78h] [rbp+20h] BYREF

  wil::ActivityBase<RemoteSessionTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v4 = wil::ActivityBase<RemoteSessionTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<RemoteSessionTraceProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         a2,
         &v14);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v4 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v8 = RemoteSessionTraceProvider::Provider();
    v9 = (__int64)v8;
    if ( *(_DWORD *)v8 > 5u && (unsigned __int8)tlgKeywordOn(v8, 0x400000000000LL, v6) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v11 = a1[34];
      v14 = CurrentThreadId;
      LODWORD(SRWLock) = a2;
      v16 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (__int64)&unk_1800A1420,
        v11 + 8,
        v12,
        (__int64)&v16,
        (__int64)&SRWLock,
        (__int64)&v14);
    }
  }
  return wil::ActivityBase<RemoteSessionTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
           a1,
           v5,
           v6,
           v7);
}

```

## disassembly

```asm
0x18001f5ec  push    rbx
0x18001f5ee  push    rsi
0x18001f5ef  push    rdi
0x18001f5f0  sub     rsp, 40h
0x18001f5f4  mov     esi, edx
0x18001f5f6  mov     rbx, rcx
0x18001f5f9  lea     rdx, [rsp+58h+SRWLock]
0x18001f5fe  call    ?LockExclusive@?$ActivityBase@VRemoteSessionTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<RemoteSessionTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001f603  mov     rcx, [rbx+110h]
0x18001f60a  lea     r8, [rsp+58h+arg_0]
0x18001f60f  mov     edx, esi
0x18001f611  call    ?SetStopResult@?$ActivityData@VRemoteSessionTraceProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VRemoteSessionTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<RemoteSessionTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<RemoteSessionTraceProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18001f616  mov     rcx, [rsp+58h+SRWLock]; SRWLock
0x18001f61b  mov     dil, al
0x18001f61e  test    rcx, rcx
0x18001f621  jz      short loc_18001F629
0x18001f623  call    cs:__imp_ReleaseSRWLockExclusive
0x18001f629  test    dil, dil
0x18001f62c  jz      short loc_18001F63F
0x18001f62e  mov     rax, [rbx]
0x18001f631  mov     rcx, rbx
0x18001f634  mov     rax, [rax+8]
0x18001f638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f63d  jmp     short loc_18001F6B3
0x18001f63f  call    ?Provider@RemoteSessionTraceProvider@@SAPEBU_tlgProvider_t@@XZ; RemoteSessionTraceProvider::Provider(void)
0x18001f644  mov     rdi, rax
0x18001f647  mov     ecx, [rax]
0x18001f649  cmp     ecx, 5
0x18001f64c  jbe     short loc_18001F6B3
0x18001f64e  mov     rdx, 400000000000h
0x18001f658  mov     rcx, rax
0x18001f65b  call    _tlgKeywordOn
0x18001f660  test    al, al
0x18001f662  jz      short loc_18001F6B3
0x18001f664  call    cs:__imp_GetCurrentThreadId
0x18001f66a  mov     r8, [rbx+110h]
0x18001f671  lea     rdx, unk_1800A1420
0x18001f678  mov     [rsp+58h+arg_0], eax
0x18001f67c  add     r8, 8
0x18001f680  lea     rax, [rsp+58h+arg_0]
0x18001f685  mov     dword ptr [rsp+58h+SRWLock], esi
0x18001f689  mov     [rsp+58h+var_28], rax
0x18001f68e  mov     rcx, rdi
0x18001f691  lea     rax, [rsp+58h+SRWLock]
0x18001f696  mov     [rsp+58h+arg_18], 1000000h
0x18001f69f  mov     [rsp+58h+var_30], rax
0x18001f6a4  lea     rax, [rsp+58h+arg_18]
0x18001f6a9  mov     [rsp+58h+var_38], rax
0x18001f6ae  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001f6b3  mov     rcx, rbx
0x18001f6b6  add     rsp, 40h
0x18001f6ba  pop     rdi
0x18001f6bb  pop     rsi
0x18001f6bc  pop     rbx
0x18001f6bd  jmp     ?IgnoreCurrentThread@?$ActivityBase@VRemoteSessionTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<RemoteSessionTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
