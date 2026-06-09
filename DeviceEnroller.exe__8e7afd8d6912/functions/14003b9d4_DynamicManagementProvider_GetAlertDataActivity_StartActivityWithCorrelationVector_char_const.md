# DynamicManagementProvider::GetAlertDataActivity::StartActivityWithCorrelationVector(char const *)

- ea: `0x14003b9d4`
- end: `0x14003bad2`
- name: `?StartActivityWithCorrelationVector@GetAlertDataActivity@DynamicManagementProvider@@QEAAXPEBD@Z`
- size: `254`
- prototype: `void __fastcall(DynamicManagementProvider::GetAlertDataActivity *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140038c7c`

## callees

- `0x1400030b0`
- `0x1400133c4`
- `0x1400183fc`
- `0x14003abc4`
- `0x14003b9d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003ba29`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003ba29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003ba43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003ba43`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14003ba0a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14003ba0a`

## pseudocode

```c
void __fastcall DynamicManagementProvider::GetAlertDataActivity::StartActivityWithCorrelationVector(
        DynamicManagementProvider::GetAlertDataActivity *this,
        const char *a2)
{
  __int64 v4; // rdi
  __int64 v5; // rdx
  const struct _tlgProvider_t *v6; // rdi
  __int64 v7; // r8
  __int64 v8; // r9
  PSRWLOCK SRWLock; // [rsp+60h] [rbp+8h] BYREF
  const unsigned __int16 *v10; // [rsp+70h] [rbp+18h] BYREF
  __int64 v11; // [rsp+78h] [rbp+20h] BYREF

  wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v4 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)DynamoProvider::Provider() <= 5u )
    *(_OWORD *)(v4 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v4 + 8));
  *(_DWORD *)v4 = 1;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v6 = DynamoProvider::Provider();
  if ( *(_DWORD *)v6 > 5u )
  {
    v10 = (const unsigned __int16 *)a2;
    LODWORD(SRWLock) = GetCurrentThreadId();
    v11 = 0;
    v7 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v7 + 4)
      || (v8 = v7 + 24, !*(_DWORD *)(v7 + 24))
      && !*(_DWORD *)(v7 + 28)
      && !*(_DWORD *)(v7 + 32)
      && !*(_DWORD *)(v7 + 36) )
    {
      v8 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (__int64)v6,
      (__int64)&word_14007079E,
      v7 + 8,
      v8,
      (__int64)&v11,
      (__int64)&SRWLock,
      &v10);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (DynamicManagementProvider::GetAlertDataActivity *)((char *)this + 288),
      v5);
}

```

## disassembly

```asm
0x14003b9d4  push    rbx
0x14003b9d6  push    rsi
0x14003b9d7  push    rdi
0x14003b9d8  sub     rsp, 40h
0x14003b9dc  mov     rsi, rdx
0x14003b9df  mov     rbx, rcx
0x14003b9e2  lea     rdx, [rsp+58h+SRWLock]
0x14003b9e7  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14003b9ec  mov     rdi, [rbx+110h]
0x14003b9f3  call    ?Provider@DynamoProvider@@SAPEBU_tlgProvider_t@@XZ; DynamoProvider::Provider(void)
0x14003b9f8  mov     r8d, [rax]
0x14003b9fb  cmp     r8d, 5
0x14003b9ff  jbe     short loc_14003BA12
0x14003ba01  lea     rdx, [rdi+8]; ActivityId
0x14003ba05  mov     ecx, 3; ControlCode
0x14003ba0a  call    cs:__imp_EventActivityIdControl
0x14003ba10  jmp     short loc_14003BA19
0x14003ba12  xorps   xmm0, xmm0
0x14003ba15  movups  xmmword ptr [rdi+8], xmm0
0x14003ba19  mov     dword ptr [rdi], 1
0x14003ba1f  mov     rcx, [rsp+58h+SRWLock]; SRWLock
0x14003ba24  test    rcx, rcx
0x14003ba27  jz      short loc_14003BA2F
0x14003ba29  call    cs:__imp_ReleaseSRWLockExclusive
0x14003ba2f  call    ?Provider@DynamoProvider@@SAPEBU_tlgProvider_t@@XZ; DynamoProvider::Provider(void)
0x14003ba34  mov     rdi, rax
0x14003ba37  mov     ecx, [rax]
0x14003ba39  cmp     ecx, 5
0x14003ba3c  jbe     short loc_14003BAB7
0x14003ba3e  mov     [rsp+58h+arg_10], rsi
0x14003ba43  call    cs:__imp_GetCurrentThreadId
0x14003ba49  mov     dword ptr [rsp+58h+SRWLock], eax
0x14003ba4d  mov     [rsp+58h+arg_18], 0
0x14003ba56  mov     r8, [rbx+110h]
0x14003ba5d  cmp     byte ptr [r8+4], 0
0x14003ba62  jz      short loc_14003BA83
0x14003ba64  lea     r9, [r8+18h]
0x14003ba68  cmp     dword ptr [r9], 0
0x14003ba6c  jnz     short loc_14003BA86
0x14003ba6e  cmp     dword ptr [r9+4], 0
0x14003ba73  jnz     short loc_14003BA86
0x14003ba75  cmp     dword ptr [r9+8], 0
0x14003ba7a  jnz     short loc_14003BA86
0x14003ba7c  cmp     dword ptr [r9+0Ch], 0
0x14003ba81  jnz     short loc_14003BA86
0x14003ba83  xor     r9d, r9d
0x14003ba86  add     r8, 8
0x14003ba8a  lea     rax, [rsp+58h+arg_10]
0x14003ba8f  mov     [rsp+58h+var_28], rax
0x14003ba94  lea     rax, [rsp+58h+SRWLock]
0x14003ba99  mov     [rsp+58h+var_30], rax
0x14003ba9e  lea     rax, [rsp+58h+arg_18]
0x14003baa3  mov     [rsp+58h+var_38], rax
0x14003baa8  lea     rdx, word_14007079E
0x14003baaf  mov     rcx, rdi
0x14003bab2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14003bab7  lea     rcx, [rbx+120h]; this
0x14003babe  cmp     dword ptr [rcx+18h], 0
0x14003bac2  jnz     short loc_14003BACA
0x14003bac4  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x14003bac9  nop
0x14003baca  add     rsp, 40h
0x14003bace  pop     rdi
0x14003bacf  pop     rsi
0x14003bad0  pop     rbx
0x14003bad1  retn
```
