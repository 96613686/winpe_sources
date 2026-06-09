# WaasMedic::TelemetryProvider::RemoveProtectedTaskActivity::StartActivity(ushort const *)

- ea: `0x18003abec`
- end: `0x18003ad6d`
- name: `?StartActivity@RemoveProtectedTaskActivity@TelemetryProvider@WaasMedic@@QEAAXPEBG@Z`
- size: `385`
- prototype: `void __fastcall(WaasMedic::TelemetryProvider::RemoveProtectedTaskActivity *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x18003a7d0`

## callees

- `0x180003574`
- `0x18000acc0`
- `0x18000d04c`
- `0x18001575c`
- `0x18003abec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003ac6b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003ac6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003aca6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ad4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003aca6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ad4d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18003ac4c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18003ac4c`

## pseudocode

```c
void __fastcall WaasMedic::TelemetryProvider::RemoveProtectedTaskActivity::StartActivity(
        WaasMedic::TelemetryProvider::RemoveProtectedTaskActivity *this,
        const unsigned __int16 *a2)
{
  __int64 v4; // rdi
  __int64 v5; // r8
  RTL_SRWLOCK *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  int v12; // r9d
  char *v13; // rbx
  _QWORD *Local; // rax
  PSRWLOCK SRWLock; // [rsp+60h] [rbp+8h] BYREF
  const unsigned __int16 *v16; // [rsp+70h] [rbp+18h] BYREF
  __int64 v17; // [rsp+78h] [rbp+20h] BYREF

  wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v4 = *((_QWORD *)this + 34);
  v5 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
  if ( *(_DWORD *)v5 > 5u
    && (*(_QWORD *)(v5 + 16) & 0x200000000000LL) != 0
    && (*(_QWORD *)(v5 + 24) & 0x200000000000LL) == *(_QWORD *)(v5 + 24) )
  {
    EventActivityIdControl(3u, (LPGUID)(v4 + 8));
  }
  else
  {
    *(_OWORD *)(v4 + 8) = 0;
  }
  v6 = SRWLock;
  *(_DWORD *)v4 = 1;
  if ( v6 )
    ReleaseSRWLockExclusive(v6);
  v9 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
  if ( *(_DWORD *)v9 > 5u )
  {
    v8 = *(_QWORD *)(v9 + 24);
    if ( (*(_QWORD *)(v9 + 16) & 0x200000000000LL) != 0 && (v8 & 0x200000000000LL) == v8 )
    {
      v16 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v11 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v17 = 0x1000000;
      if ( !*(_BYTE *)(v11 + 4)
        || (v12 = v11 + 24, !*(_DWORD *)(v11 + 24))
        && !*(_DWORD *)(v11 + 28)
        && !*(_DWORD *)(v11 + 32)
        && !*(_DWORD *)(v11 + 36) )
      {
        v12 = 0;
      }
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v9,
        (unsigned int)&dword_180093F6C,
        v11 + 8,
        v12,
        (__int64)&v17,
        (__int64)&SRWLock,
        (__int64)&v16);
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v13 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      LOBYTE(v7) = 1;
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v8,
                          v7);
      *(_QWORD *)v13 = Local;
      if ( Local )
      {
        *((_QWORD *)v13 + 2) = *Local;
        *Local = v13;
        *((_DWORD *)v13 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v13 = 0;
    }
  }
}

```

## disassembly

```asm
0x18003abec  mov     [rsp+arg_8], rbx
0x18003abf1  push    rsi
0x18003abf2  push    rdi
0x18003abf3  push    r14
0x18003abf5  sub     rsp, 40h
0x18003abf9  mov     rsi, rdx
0x18003abfc  mov     rbx, rcx
0x18003abff  lea     rdx, [rsp+58h+SRWLock]
0x18003ac04  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003ac09  mov     rdi, [rbx+110h]
0x18003ac10  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x18003ac15  mov     r14, 200000000000h
0x18003ac1f  mov     r8, [rax+8]
0x18003ac23  mov     eax, [r8]
0x18003ac26  cmp     eax, 5
0x18003ac29  jbe     short loc_18003AC54
0x18003ac2b  mov     rcx, [r8+18h]
0x18003ac2f  mov     rax, [r8+10h]
0x18003ac33  test    r14, rax
0x18003ac36  jz      short loc_18003AC54
0x18003ac38  mov     rax, rcx
0x18003ac3b  and     rax, r14
0x18003ac3e  cmp     rax, rcx
0x18003ac41  jnz     short loc_18003AC54
0x18003ac43  lea     rdx, [rdi+8]; ActivityId
0x18003ac47  mov     ecx, 3; ControlCode
0x18003ac4c  call    cs:__imp_EventActivityIdControl
0x18003ac52  jmp     short loc_18003AC5B
0x18003ac54  xorps   xmm0, xmm0
0x18003ac57  movups  xmmword ptr [rdi+8], xmm0
0x18003ac5b  mov     rcx, [rsp+58h+SRWLock]; SRWLock
0x18003ac60  mov     dword ptr [rdi], 1
0x18003ac66  test    rcx, rcx
0x18003ac69  jz      short loc_18003AC71
0x18003ac6b  call    cs:__imp_ReleaseSRWLockExclusive
0x18003ac71  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x18003ac76  mov     rdi, [rax+8]
0x18003ac7a  mov     eax, [rdi]
0x18003ac7c  cmp     eax, 5
0x18003ac7f  jbe     loc_18003AD1A
0x18003ac85  mov     rcx, [rdi+18h]
0x18003ac89  mov     rax, [rdi+10h]
0x18003ac8d  test    r14, rax
0x18003ac90  jz      loc_18003AD1A
0x18003ac96  mov     rax, rcx
0x18003ac99  and     rax, r14
0x18003ac9c  cmp     rax, rcx
0x18003ac9f  jnz     short loc_18003AD1A
0x18003aca1  mov     [rsp+58h+arg_10], rsi
0x18003aca6  call    cs:__imp_GetCurrentThreadId
0x18003acac  mov     r8, [rbx+110h]
0x18003acb3  mov     dword ptr [rsp+58h+SRWLock], eax
0x18003acb7  mov     [rsp+58h+arg_18], 1000000h
0x18003acc0  cmp     byte ptr [r8+4], 0
0x18003acc5  jz      short loc_18003ACE6
0x18003acc7  lea     r9, [r8+18h]
0x18003accb  cmp     dword ptr [r9], 0
0x18003accf  jnz     short loc_18003ACE9
0x18003acd1  cmp     dword ptr [r9+4], 0
0x18003acd6  jnz     short loc_18003ACE9
0x18003acd8  cmp     dword ptr [r9+8], 0
0x18003acdd  jnz     short loc_18003ACE9
0x18003acdf  cmp     dword ptr [r9+0Ch], 0
0x18003ace4  jnz     short loc_18003ACE9
0x18003ace6  xor     r9d, r9d
0x18003ace9  lea     rax, [rsp+58h+arg_10]
0x18003acee  add     r8, 8
0x18003acf2  mov     [rsp+58h+var_28], rax
0x18003acf7  lea     rdx, dword_180093F6C
0x18003acfe  lea     rax, [rsp+58h+SRWLock]
0x18003ad03  mov     rcx, rdi
0x18003ad06  mov     [rsp+58h+var_30], rax
0x18003ad0b  lea     rax, [rsp+58h+arg_18]
0x18003ad10  mov     [rsp+58h+var_38], rax
0x18003ad15  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18003ad1a  cmp     dword ptr [rbx+138h], 0
0x18003ad21  jnz     short loc_18003AD5F
0x18003ad23  add     rbx, 120h
0x18003ad2a  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18003ad32  jz      short loc_18003AD58
0x18003ad34  mov     dl, 1
0x18003ad36  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18003ad3b  mov     [rbx], rax
0x18003ad3e  test    rax, rax
0x18003ad41  jz      short loc_18003AD5F
0x18003ad43  mov     rcx, [rax]
0x18003ad46  mov     [rbx+10h], rcx
0x18003ad4a  mov     [rax], rbx
0x18003ad4d  call    cs:__imp_GetCurrentThreadId
0x18003ad53  mov     [rbx+18h], eax
0x18003ad56  jmp     short loc_18003AD5F
0x18003ad58  mov     qword ptr [rbx], 0
0x18003ad5f  mov     rbx, [rsp+58h+arg_8]
0x18003ad64  add     rsp, 40h
0x18003ad68  pop     r14
0x18003ad6a  pop     rdi
0x18003ad6b  pop     rsi
0x18003ad6c  retn
```
