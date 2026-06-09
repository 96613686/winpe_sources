# AIFabricTraceLogger::SessionManagerBrokerRegisterStagedAIFabricPackagesActivity::StartActivity(wchar_t const *)

- ea: `0x18007ad68`
- end: `0x18007ae65`
- name: `?StartActivity@SessionManagerBrokerRegisterStagedAIFabricPackagesActivity@AIFabricTraceLogger@@QEAAXPEB_W@Z`
- size: `253`
- prototype: `void __fastcall(AIFabricTraceLogger::SessionManagerBrokerRegisterStagedAIFabricPackagesActivity *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18007a7fc`

## callees

- `0x1800039b0`
- `0x18004b8f4`
- `0x1800625bc`
- `0x180065380`
- `0x18007ad68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007adbd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007adbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007add7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007add7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18007ad9e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18007ad9e`

## pseudocode

```c
void __fastcall AIFabricTraceLogger::SessionManagerBrokerRegisterStagedAIFabricPackagesActivity::StartActivity(
        AIFabricTraceLogger::SessionManagerBrokerRegisterStagedAIFabricPackagesActivity *this,
        const wchar_t *a2)
{
  __int64 v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  __int64 v6; // rdx
  const struct _tlgProvider_t *v7; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  PSRWLOCK SRWLock; // [rsp+60h] [rbp+8h] BYREF
  const wchar_t *v12; // [rsp+70h] [rbp+18h] BYREF
  __int64 v13; // [rsp+78h] [rbp+20h] BYREF

  wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v4 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)AIFabricTraceLogger::Provider() <= 5u )
    *(_OWORD *)(v4 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v4 + 8));
  v5 = SRWLock;
  *(_DWORD *)v4 = 1;
  if ( v5 )
    ReleaseSRWLockExclusive(v5);
  v7 = AIFabricTraceLogger::Provider();
  if ( *(_DWORD *)v7 > 5u )
  {
    v12 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v9 = *((_QWORD *)this + 34);
    LODWORD(SRWLock) = CurrentThreadId;
    v13 = 0;
    if ( !*(_BYTE *)(v9 + 4)
      || (v10 = v9 + 24, !*(_DWORD *)(v9 + 24))
      && !*(_DWORD *)(v9 + 28)
      && !*(_DWORD *)(v9 + 32)
      && !*(_DWORD *)(v9 + 36) )
    {
      v10 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
      (__int64)v7,
      (__int64)byte_18009E8E3,
      v9 + 8,
      v10,
      (__int64)&v13,
      (__int64)&SRWLock,
      &v12);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (AIFabricTraceLogger::SessionManagerBrokerRegisterStagedAIFabricPackagesActivity *)((char *)this + 288),
      v6);
}

```

## disassembly

```asm
0x18007ad68  push    rbx
0x18007ad6a  push    rsi
0x18007ad6b  push    rdi
0x18007ad6c  sub     rsp, 40h
0x18007ad70  mov     rsi, rdx
0x18007ad73  mov     rbx, rcx
0x18007ad76  lea     rdx, [rsp+58h+SRWLock]
0x18007ad7b  call    ?LockExclusive@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18007ad80  mov     rdi, [rbx+110h]
0x18007ad87  call    ?Provider@AIFabricTraceLogger@@SAPEBU_tlgProvider_t@@XZ; AIFabricTraceLogger::Provider(void)
0x18007ad8c  mov     r8d, [rax]
0x18007ad8f  cmp     r8d, 5
0x18007ad93  jbe     short loc_18007ADA6
0x18007ad95  lea     rdx, [rdi+8]; ActivityId
0x18007ad99  mov     ecx, 3; ControlCode
0x18007ad9e  call    cs:__imp_EventActivityIdControl
0x18007ada4  jmp     short loc_18007ADAD
0x18007ada6  xorps   xmm0, xmm0
0x18007ada9  movups  xmmword ptr [rdi+8], xmm0
0x18007adad  mov     rcx, [rsp+58h+SRWLock]; SRWLock
0x18007adb2  mov     dword ptr [rdi], 1
0x18007adb8  test    rcx, rcx
0x18007adbb  jz      short loc_18007ADC3
0x18007adbd  call    cs:__imp_ReleaseSRWLockExclusive
0x18007adc3  call    ?Provider@AIFabricTraceLogger@@SAPEBU_tlgProvider_t@@XZ; AIFabricTraceLogger::Provider(void)
0x18007adc8  mov     rdi, rax
0x18007adcb  mov     ecx, [rax]
0x18007adcd  cmp     ecx, 5
0x18007add0  jbe     short loc_18007AE4B
0x18007add2  mov     [rsp+58h+arg_10], rsi
0x18007add7  call    cs:__imp_GetCurrentThreadId
0x18007addd  mov     r8, [rbx+110h]
0x18007ade4  mov     dword ptr [rsp+58h+SRWLock], eax
0x18007ade8  mov     [rsp+58h+arg_18], 0
0x18007adf1  cmp     byte ptr [r8+4], 0
0x18007adf6  jz      short loc_18007AE17
0x18007adf8  lea     r9, [r8+18h]
0x18007adfc  cmp     dword ptr [r9], 0
0x18007ae00  jnz     short loc_18007AE1A
0x18007ae02  cmp     dword ptr [r9+4], 0
0x18007ae07  jnz     short loc_18007AE1A
0x18007ae09  cmp     dword ptr [r9+8], 0
0x18007ae0e  jnz     short loc_18007AE1A
0x18007ae10  cmp     dword ptr [r9+0Ch], 0
0x18007ae15  jnz     short loc_18007AE1A
0x18007ae17  xor     r9d, r9d
0x18007ae1a  lea     rax, [rsp+58h+arg_10]
0x18007ae1f  add     r8, 8
0x18007ae23  mov     [rsp+58h+var_28], rax
0x18007ae28  lea     rdx, byte_18009E8E3
0x18007ae2f  lea     rax, [rsp+58h+SRWLock]
0x18007ae34  mov     rcx, rdi
0x18007ae37  mov     [rsp+58h+var_30], rax
0x18007ae3c  lea     rax, [rsp+58h+arg_18]
0x18007ae41  mov     [rsp+58h+var_38], rax
0x18007ae46  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x18007ae4b  lea     rcx, [rbx+120h]; this
0x18007ae52  cmp     dword ptr [rcx+18h], 0
0x18007ae56  jnz     short loc_18007AE5D
0x18007ae58  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18007ae5d  add     rsp, 40h
0x18007ae61  pop     rdi
0x18007ae62  pop     rsi
0x18007ae63  pop     rbx
0x18007ae64  retn
```
