# WaasMedic::TelemetryProvider::AddProtectedTaskActivity::StartActivity(ushort const *)

- ea: `0x18003aa64`
- end: `0x18003abe5`
- name: `?StartActivity@AddProtectedTaskActivity@TelemetryProvider@WaasMedic@@QEAAXPEBG@Z`
- size: `385`
- prototype: `void __fastcall(WaasMedic::TelemetryProvider::AddProtectedTaskActivity *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x180039e40`

## callees

- `0x180003574`
- `0x18000acc0`
- `0x18000d04c`
- `0x18001575c`
- `0x18003aa64`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003aae3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003aae3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ab1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003abc5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ab1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003abc5`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18003aac4`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18003aac4`

## pseudocode

```c
void __fastcall WaasMedic::TelemetryProvider::AddProtectedTaskActivity::StartActivity(
        WaasMedic::TelemetryProvider::AddProtectedTaskActivity *this,
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
        (unsigned int)word_180093FCA,
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
0x18003aa64  mov     [rsp+arg_8], rbx
0x18003aa69  push    rsi
0x18003aa6a  push    rdi
0x18003aa6b  push    r14
0x18003aa6d  sub     rsp, 40h
0x18003aa71  mov     rsi, rdx
0x18003aa74  mov     rbx, rcx
0x18003aa77  lea     rdx, [rsp+58h+SRWLock]
0x18003aa7c  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003aa81  mov     rdi, [rbx+110h]
0x18003aa88  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x18003aa8d  mov     r14, 200000000000h
0x18003aa97  mov     r8, [rax+8]
0x18003aa9b  mov     eax, [r8]
0x18003aa9e  cmp     eax, 5
0x18003aaa1  jbe     short loc_18003AACC
0x18003aaa3  mov     rcx, [r8+18h]
0x18003aaa7  mov     rax, [r8+10h]
0x18003aaab  test    r14, rax
0x18003aaae  jz      short loc_18003AACC
0x18003aab0  mov     rax, rcx
0x18003aab3  and     rax, r14
0x18003aab6  cmp     rax, rcx
0x18003aab9  jnz     short loc_18003AACC
0x18003aabb  lea     rdx, [rdi+8]; ActivityId
0x18003aabf  mov     ecx, 3; ControlCode
0x18003aac4  call    cs:__imp_EventActivityIdControl
0x18003aaca  jmp     short loc_18003AAD3
0x18003aacc  xorps   xmm0, xmm0
0x18003aacf  movups  xmmword ptr [rdi+8], xmm0
0x18003aad3  mov     rcx, [rsp+58h+SRWLock]; SRWLock
0x18003aad8  mov     dword ptr [rdi], 1
0x18003aade  test    rcx, rcx
0x18003aae1  jz      short loc_18003AAE9
0x18003aae3  call    cs:__imp_ReleaseSRWLockExclusive
0x18003aae9  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x18003aaee  mov     rdi, [rax+8]
0x18003aaf2  mov     eax, [rdi]
0x18003aaf4  cmp     eax, 5
0x18003aaf7  jbe     loc_18003AB92
0x18003aafd  mov     rcx, [rdi+18h]
0x18003ab01  mov     rax, [rdi+10h]
0x18003ab05  test    r14, rax
0x18003ab08  jz      loc_18003AB92
0x18003ab0e  mov     rax, rcx
0x18003ab11  and     rax, r14
0x18003ab14  cmp     rax, rcx
0x18003ab17  jnz     short loc_18003AB92
0x18003ab19  mov     [rsp+58h+arg_10], rsi
0x18003ab1e  call    cs:__imp_GetCurrentThreadId
0x18003ab24  mov     r8, [rbx+110h]
0x18003ab2b  mov     dword ptr [rsp+58h+SRWLock], eax
0x18003ab2f  mov     [rsp+58h+arg_18], 1000000h
0x18003ab38  cmp     byte ptr [r8+4], 0
0x18003ab3d  jz      short loc_18003AB5E
0x18003ab3f  lea     r9, [r8+18h]
0x18003ab43  cmp     dword ptr [r9], 0
0x18003ab47  jnz     short loc_18003AB61
0x18003ab49  cmp     dword ptr [r9+4], 0
0x18003ab4e  jnz     short loc_18003AB61
0x18003ab50  cmp     dword ptr [r9+8], 0
0x18003ab55  jnz     short loc_18003AB61
0x18003ab57  cmp     dword ptr [r9+0Ch], 0
0x18003ab5c  jnz     short loc_18003AB61
0x18003ab5e  xor     r9d, r9d
0x18003ab61  lea     rax, [rsp+58h+arg_10]
0x18003ab66  add     r8, 8
0x18003ab6a  mov     [rsp+58h+var_28], rax
0x18003ab6f  lea     rdx, word_180093FCA
0x18003ab76  lea     rax, [rsp+58h+SRWLock]
0x18003ab7b  mov     rcx, rdi
0x18003ab7e  mov     [rsp+58h+var_30], rax
0x18003ab83  lea     rax, [rsp+58h+arg_18]
0x18003ab88  mov     [rsp+58h+var_38], rax
0x18003ab8d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18003ab92  cmp     dword ptr [rbx+138h], 0
0x18003ab99  jnz     short loc_18003ABD7
0x18003ab9b  add     rbx, 120h
0x18003aba2  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18003abaa  jz      short loc_18003ABD0
0x18003abac  mov     dl, 1
0x18003abae  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18003abb3  mov     [rbx], rax
0x18003abb6  test    rax, rax
0x18003abb9  jz      short loc_18003ABD7
0x18003abbb  mov     rcx, [rax]
0x18003abbe  mov     [rbx+10h], rcx
0x18003abc2  mov     [rax], rbx
0x18003abc5  call    cs:__imp_GetCurrentThreadId
0x18003abcb  mov     [rbx+18h], eax
0x18003abce  jmp     short loc_18003ABD7
0x18003abd0  mov     qword ptr [rbx], 0
0x18003abd7  mov     rbx, [rsp+58h+arg_8]
0x18003abdc  add     rsp, 40h
0x18003abe0  pop     r14
0x18003abe2  pop     rdi
0x18003abe3  pop     rsi
0x18003abe4  retn
```
