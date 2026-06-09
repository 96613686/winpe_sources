# DynamicManagementProvider::RaiseToastActivity::StartActivityWithCorrelationVector(char const *)

- ea: `0x14003bad8`
- end: `0x14003bbd6`
- name: `?StartActivityWithCorrelationVector@RaiseToastActivity@DynamicManagementProvider@@QEAAXPEBD@Z`
- size: `254`
- prototype: `void __fastcall(DynamicManagementProvider::RaiseToastActivity *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400390d8`

## callees

- `0x1400030b0`
- `0x1400133c4`
- `0x1400183fc`
- `0x14003abc4`
- `0x14003bad8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003bb2d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003bb2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003bb47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003bb47`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14003bb0e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14003bb0e`

## pseudocode

```c
void __fastcall DynamicManagementProvider::RaiseToastActivity::StartActivityWithCorrelationVector(
        DynamicManagementProvider::RaiseToastActivity *this,
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
      (__int64)byte_14006FAD1,
      v7 + 8,
      v8,
      (__int64)&v11,
      (__int64)&SRWLock,
      &v10);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (DynamicManagementProvider::RaiseToastActivity *)((char *)this + 288),
      v5);
}

```

## disassembly

```asm
0x14003bad8  push    rbx
0x14003bada  push    rsi
0x14003badb  push    rdi
0x14003badc  sub     rsp, 40h
0x14003bae0  mov     rsi, rdx
0x14003bae3  mov     rbx, rcx
0x14003bae6  lea     rdx, [rsp+58h+SRWLock]
0x14003baeb  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14003baf0  mov     rdi, [rbx+110h]
0x14003baf7  call    ?Provider@DynamoProvider@@SAPEBU_tlgProvider_t@@XZ; DynamoProvider::Provider(void)
0x14003bafc  mov     r8d, [rax]
0x14003baff  cmp     r8d, 5
0x14003bb03  jbe     short loc_14003BB16
0x14003bb05  lea     rdx, [rdi+8]; ActivityId
0x14003bb09  mov     ecx, 3; ControlCode
0x14003bb0e  call    cs:__imp_EventActivityIdControl
0x14003bb14  jmp     short loc_14003BB1D
0x14003bb16  xorps   xmm0, xmm0
0x14003bb19  movups  xmmword ptr [rdi+8], xmm0
0x14003bb1d  mov     dword ptr [rdi], 1
0x14003bb23  mov     rcx, [rsp+58h+SRWLock]; SRWLock
0x14003bb28  test    rcx, rcx
0x14003bb2b  jz      short loc_14003BB33
0x14003bb2d  call    cs:__imp_ReleaseSRWLockExclusive
0x14003bb33  call    ?Provider@DynamoProvider@@SAPEBU_tlgProvider_t@@XZ; DynamoProvider::Provider(void)
0x14003bb38  mov     rdi, rax
0x14003bb3b  mov     ecx, [rax]
0x14003bb3d  cmp     ecx, 5
0x14003bb40  jbe     short loc_14003BBBB
0x14003bb42  mov     [rsp+58h+arg_10], rsi
0x14003bb47  call    cs:__imp_GetCurrentThreadId
0x14003bb4d  mov     dword ptr [rsp+58h+SRWLock], eax
0x14003bb51  mov     [rsp+58h+arg_18], 0
0x14003bb5a  mov     r8, [rbx+110h]
0x14003bb61  cmp     byte ptr [r8+4], 0
0x14003bb66  jz      short loc_14003BB87
0x14003bb68  lea     r9, [r8+18h]
0x14003bb6c  cmp     dword ptr [r9], 0
0x14003bb70  jnz     short loc_14003BB8A
0x14003bb72  cmp     dword ptr [r9+4], 0
0x14003bb77  jnz     short loc_14003BB8A
0x14003bb79  cmp     dword ptr [r9+8], 0
0x14003bb7e  jnz     short loc_14003BB8A
0x14003bb80  cmp     dword ptr [r9+0Ch], 0
0x14003bb85  jnz     short loc_14003BB8A
0x14003bb87  xor     r9d, r9d
0x14003bb8a  add     r8, 8
0x14003bb8e  lea     rax, [rsp+58h+arg_10]
0x14003bb93  mov     [rsp+58h+var_28], rax
0x14003bb98  lea     rax, [rsp+58h+SRWLock]
0x14003bb9d  mov     [rsp+58h+var_30], rax
0x14003bba2  lea     rax, [rsp+58h+arg_18]
0x14003bba7  mov     [rsp+58h+var_38], rax
0x14003bbac  lea     rdx, byte_14006FAD1
0x14003bbb3  mov     rcx, rdi
0x14003bbb6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14003bbbb  lea     rcx, [rbx+120h]; this
0x14003bbc2  cmp     dword ptr [rcx+18h], 0
0x14003bbc6  jnz     short loc_14003BBCE
0x14003bbc8  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x14003bbcd  nop
0x14003bbce  add     rsp, 40h
0x14003bbd2  pop     rdi
0x14003bbd3  pop     rsi
0x14003bbd4  pop     rbx
0x14003bbd5  retn
```
