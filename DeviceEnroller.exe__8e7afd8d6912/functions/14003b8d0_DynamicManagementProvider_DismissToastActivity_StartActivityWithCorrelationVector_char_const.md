# DynamicManagementProvider::DismissToastActivity::StartActivityWithCorrelationVector(char const *)

- ea: `0x14003b8d0`
- end: `0x14003b9ce`
- name: `?StartActivityWithCorrelationVector@DismissToastActivity@DynamicManagementProvider@@QEAAXPEBD@Z`
- size: `254`
- prototype: `void __fastcall(DynamicManagementProvider::DismissToastActivity *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140038ae4`

## callees

- `0x1400030b0`
- `0x1400133c4`
- `0x1400183fc`
- `0x14003abc4`
- `0x14003b8d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003b925`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003b925`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003b93f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003b93f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14003b906`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14003b906`

## pseudocode

```c
void __fastcall DynamicManagementProvider::DismissToastActivity::StartActivityWithCorrelationVector(
        DynamicManagementProvider::DismissToastActivity *this,
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
      (__int64)&byte_1400706EF,
      v7 + 8,
      v8,
      (__int64)&v11,
      (__int64)&SRWLock,
      &v10);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (DynamicManagementProvider::DismissToastActivity *)((char *)this + 288),
      v5);
}

```

## disassembly

```asm
0x14003b8d0  push    rbx
0x14003b8d2  push    rsi
0x14003b8d3  push    rdi
0x14003b8d4  sub     rsp, 40h
0x14003b8d8  mov     rsi, rdx
0x14003b8db  mov     rbx, rcx
0x14003b8de  lea     rdx, [rsp+58h+SRWLock]
0x14003b8e3  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14003b8e8  mov     rdi, [rbx+110h]
0x14003b8ef  call    ?Provider@DynamoProvider@@SAPEBU_tlgProvider_t@@XZ; DynamoProvider::Provider(void)
0x14003b8f4  mov     r8d, [rax]
0x14003b8f7  cmp     r8d, 5
0x14003b8fb  jbe     short loc_14003B90E
0x14003b8fd  lea     rdx, [rdi+8]; ActivityId
0x14003b901  mov     ecx, 3; ControlCode
0x14003b906  call    cs:__imp_EventActivityIdControl
0x14003b90c  jmp     short loc_14003B915
0x14003b90e  xorps   xmm0, xmm0
0x14003b911  movups  xmmword ptr [rdi+8], xmm0
0x14003b915  mov     dword ptr [rdi], 1
0x14003b91b  mov     rcx, [rsp+58h+SRWLock]; SRWLock
0x14003b920  test    rcx, rcx
0x14003b923  jz      short loc_14003B92B
0x14003b925  call    cs:__imp_ReleaseSRWLockExclusive
0x14003b92b  call    ?Provider@DynamoProvider@@SAPEBU_tlgProvider_t@@XZ; DynamoProvider::Provider(void)
0x14003b930  mov     rdi, rax
0x14003b933  mov     ecx, [rax]
0x14003b935  cmp     ecx, 5
0x14003b938  jbe     short loc_14003B9B3
0x14003b93a  mov     [rsp+58h+arg_10], rsi
0x14003b93f  call    cs:__imp_GetCurrentThreadId
0x14003b945  mov     dword ptr [rsp+58h+SRWLock], eax
0x14003b949  mov     [rsp+58h+arg_18], 0
0x14003b952  mov     r8, [rbx+110h]
0x14003b959  cmp     byte ptr [r8+4], 0
0x14003b95e  jz      short loc_14003B97F
0x14003b960  lea     r9, [r8+18h]
0x14003b964  cmp     dword ptr [r9], 0
0x14003b968  jnz     short loc_14003B982
0x14003b96a  cmp     dword ptr [r9+4], 0
0x14003b96f  jnz     short loc_14003B982
0x14003b971  cmp     dword ptr [r9+8], 0
0x14003b976  jnz     short loc_14003B982
0x14003b978  cmp     dword ptr [r9+0Ch], 0
0x14003b97d  jnz     short loc_14003B982
0x14003b97f  xor     r9d, r9d
0x14003b982  add     r8, 8
0x14003b986  lea     rax, [rsp+58h+arg_10]
0x14003b98b  mov     [rsp+58h+var_28], rax
0x14003b990  lea     rax, [rsp+58h+SRWLock]
0x14003b995  mov     [rsp+58h+var_30], rax
0x14003b99a  lea     rax, [rsp+58h+arg_18]
0x14003b99f  mov     [rsp+58h+var_38], rax
0x14003b9a4  lea     rdx, byte_1400706EF
0x14003b9ab  mov     rcx, rdi
0x14003b9ae  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14003b9b3  lea     rcx, [rbx+120h]; this
0x14003b9ba  cmp     dword ptr [rcx+18h], 0
0x14003b9be  jnz     short loc_14003B9C6
0x14003b9c0  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x14003b9c5  nop
0x14003b9c6  add     rsp, 40h
0x14003b9ca  pop     rdi
0x14003b9cb  pop     rsi
0x14003b9cc  pop     rbx
0x14003b9cd  retn
```
