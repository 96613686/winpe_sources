# wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18000892c`
- end: `0x180008a70`
- name: `?Stop@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `324`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `15`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x180004e30`
- `0x180004f40`
- `0x180005050`
- `0x1800052f0`
- `0x180005400`
- `0x180007c30`
- `0x180009a60`
- `0x18001613c`
- `0x1800173f4`
- `0x1800178e0`
- `0x18001ae40`
- `0x18001fb70`
- `0x180020000`
- `0x180020308`
- `0x180023090`

## callees

- `0x1800012bc`
- `0x180002c48`
- `0x18000478c`
- `0x180006fcc`
- `0x180007088`
- `0x18000892c`
- `0x18000907c`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800089d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800089d4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000897e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000897e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 a1,
        int a2)
{
  __int64 v4; // rax
  int v5; // edi
  int v6; // edi
  __int64 v7; // rdi
  __int64 v8; // r9
  const struct wil::FailureInfo *v9; // rdx
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C8h] BYREF
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v12; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE v13[160]; // [rsp+60h] [rbp-A8h] BYREF

  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v4 = *(_QWORD *)(a1 + 272);
  v5 = *(_DWORD *)(v4 + 248);
  if ( v5 < 1 )
  {
    memset_0(v13, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v13, v9);
  }
  if ( *(int *)(v4 + 72) >= 0 )
    *(_DWORD *)(v4 + 72) = a2;
  v6 = v5 - 1;
  *(_DWORD *)(v4 + 248) = v6;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v6 )
  {
    v7 = *((_QWORD *)CmAgentTraceProvider::Instance() + 1);
    if ( *(_DWORD *)v7 > 5u
      && (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v7 + 24) & 0x400000000000LL) == *(_QWORD *)(v7 + 24) )
    {
      CurrentThreadId = GetCurrentThreadId();
      LODWORD(SRWLock) = a2;
      v12 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (__int64)&word_180043216,
        *(_QWORD *)(a1 + 272) + 8LL,
        v8,
        (__int64)&v12,
        (__int64)&SRWLock,
        (__int64)&CurrentThreadId);
    }
  }
  else
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  }
  if ( *(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
}

```

## disassembly

```asm
0x18000892c  mov     [rsp+arg_8], rbx
0x180008931  mov     [rsp+arg_10], rsi
0x180008936  push    rdi
0x180008937  sub     rsp, 100h
0x18000893e  mov     esi, edx
0x180008940  mov     rbx, rcx
0x180008943  lea     rdx, [rsp+108h+SRWLock]
0x180008948  call    ?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000894d  mov     rax, [rbx+110h]
0x180008954  mov     edi, [rax+0F8h]
0x18000895a  cmp     edi, 1
0x18000895d  jl      loc_180008A53
0x180008963  cmp     dword ptr [rax+48h], 0
0x180008967  jl      short loc_18000896C
0x180008969  mov     [rax+48h], esi
0x18000896c  dec     edi
0x18000896e  mov     [rax+0F8h], edi
0x180008974  mov     rcx, [rsp+108h+SRWLock]; SRWLock
0x180008979  test    rcx, rcx
0x18000897c  jz      short loc_18000898A
0x18000897e  call    cs:__imp_ReleaseSRWLockExclusive
0x180008985  nop     dword ptr [rax+rax+00h]
0x18000898a  test    edi, edi
0x18000898c  jnz     short loc_1800089A2
0x18000898e  mov     rax, [rbx]
0x180008991  mov     rcx, rbx
0x180008994  mov     rax, [rax+8]
0x180008998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000899d  jmp     loc_180008A2A
0x1800089a2  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x1800089a7  mov     rdi, [rax+8]
0x1800089ab  mov     eax, [rdi]
0x1800089ad  cmp     eax, 5
0x1800089b0  jbe     short loc_180008A2A
0x1800089b2  mov     rcx, [rdi+18h]
0x1800089b6  mov     rax, [rdi+10h]
0x1800089ba  mov     rdx, 400000000000h
0x1800089c4  test    rdx, rax
0x1800089c7  jz      short loc_180008A2A
0x1800089c9  mov     rax, rcx
0x1800089cc  and     rax, rdx
0x1800089cf  cmp     rax, rcx
0x1800089d2  jnz     short loc_180008A2A
0x1800089d4  call    cs:__imp_GetCurrentThreadId
0x1800089db  nop     dword ptr [rax+rax+00h]
0x1800089e0  mov     [rsp+108h+var_C8], eax
0x1800089e4  mov     dword ptr [rsp+108h+SRWLock], esi
0x1800089e8  mov     [rsp+108h+var_B8], 1000000h
0x1800089f1  mov     r8, [rbx+110h]
0x1800089f8  add     r8, 8
0x1800089fc  lea     rax, [rsp+108h+var_C8]
0x180008a01  mov     [rsp+108h+var_D8], rax
0x180008a06  lea     rax, [rsp+108h+SRWLock]
0x180008a0b  mov     [rsp+108h+var_E0], rax
0x180008a10  lea     rax, [rsp+108h+var_B8]
0x180008a15  mov     [rsp+108h+var_E8], rax
0x180008a1a  lea     rdx, word_180043216
0x180008a21  mov     rcx, rdi
0x180008a24  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180008a29  nop
0x180008a2a  lea     rcx, [rbx+120h]; this
0x180008a31  cmp     dword ptr [rcx+18h], 0
0x180008a35  jz      short loc_180008A3D
0x180008a37  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180008a3c  nop
0x180008a3d  lea     r11, [rsp+108h+var_8]
0x180008a45  mov     rbx, [r11+18h]
0x180008a49  mov     rsi, [r11+20h]
0x180008a4d  mov     rsp, r11
0x180008a50  pop     rdi
0x180008a51  retn
0x180008a53  xor     edx, edx; Val
0x180008a55  mov     r8d, 98h; Size
0x180008a5b  lea     rcx, [rsp+108h+var_A8]; void *
0x180008a60  call    memset_0
0x180008a65  lea     rcx, [rsp+108h+var_A8]; this
0x180008a6a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
