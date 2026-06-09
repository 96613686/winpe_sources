# TraceLog::Providers::Reliability::NamedCallContextActivity::StartActivity(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180037188`
- end: `0x18003730a`
- name: `?StartActivity@NamedCallContextActivity@Reliability@Providers@TraceLog@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `386`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800368a4`

## callees

- `0x1800010fc`
- `0x1800060a0`
- `0x18002ae34`
- `0x18002bbb8`
- `0x180036d18`
- `0x180037188`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037221`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037221`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800371fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800371fe`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800371dd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800371dd`

## pseudocode

```c
void __fastcall TraceLog::Providers::Reliability::NamedCallContextActivity::StartActivity(__int64 a1, const WCHAR *a2)
{
  __int64 v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  __int64 v6; // rdx
  const struct _tlgProvider_t *v7; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  const GUID *v10; // r9
  __int64 v11; // rax
  int v12; // eax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-29h] BYREF
  __int64 v14; // [rsp+38h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+40h] [rbp-19h] BYREF
  __int64 *v16; // [rsp+60h] [rbp+7h]
  __int64 v17; // [rsp+68h] [rbp+Fh]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp+17h]
  __int64 v19; // [rsp+78h] [rbp+1Fh]
  const WCHAR *v20; // [rsp+80h] [rbp+27h]
  int v21; // [rsp+88h] [rbp+2Fh]
  int v22; // [rsp+8Ch] [rbp+33h]

  wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v4 = *(_QWORD *)(a1 + 272);
  if ( *(_DWORD *)TraceLog::Providers::Reliability::Provider() <= 4u )
    *(_OWORD *)(v4 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v4 + 8));
  v5 = SRWLock;
  *(_DWORD *)v4 = 1;
  if ( v5 )
    ReleaseSRWLockExclusive(v5);
  v7 = TraceLog::Providers::Reliability::Provider();
  if ( *(_DWORD *)v7 > 4u )
  {
    if ( *((_QWORD *)a2 + 3) > 7u )
      a2 = *(const WCHAR **)a2;
    CurrentThreadId = GetCurrentThreadId();
    v9 = *(_QWORD *)(a1 + 272);
    LODWORD(SRWLock) = CurrentThreadId;
    v14 = 0x1000000;
    if ( !*(_BYTE *)(v9 + 4)
      || (v10 = (const GUID *)(v9 + 24), !*(_DWORD *)(v9 + 24))
      && !*(_DWORD *)(v9 + 28)
      && !*(_DWORD *)(v9 + 32)
      && !*(_DWORD *)(v9 + 36) )
    {
      v10 = 0;
    }
    if ( a2 )
    {
      v11 = -1;
      do
        ++v11;
      while ( a2[v11] );
      v12 = 2 * v11 + 2;
    }
    else
    {
      a2 = &SubKey;
      v12 = 2;
    }
    v21 = v12;
    v20 = a2;
    p_SRWLock = &SRWLock;
    v22 = 0;
    v16 = &v14;
    v19 = 4;
    v17 = 8;
    tlgWriteTransfer_EventWriteTransfer(
      (__int64)v7,
      (unsigned __int8 *)&unk_1800D55A8,
      (const GUID *)(v9 + 8),
      v10,
      5u,
      &v15);
  }
  if ( !*(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (wil::details::ThreadFailureCallbackHolder *)(a1 + 288),
      v6);
}

```

## disassembly

```asm
0x180037188  mov     [rsp-8+arg_8], rbx
0x18003718d  mov     [rsp-8+arg_10], rsi
0x180037192  push    rbp
0x180037193  push    rdi
0x180037194  push    r14
0x180037196  lea     rbp, [rsp-47h]
0x18003719b  sub     rsp, 0A0h
0x1800371a2  mov     rax, cs:__security_cookie
0x1800371a9  xor     rax, rsp
0x1800371ac  mov     [rbp+57h+var_20], rax
0x1800371b0  mov     rbx, rdx
0x1800371b3  mov     rsi, rcx
0x1800371b6  lea     rdx, [rbp+57h+SRWLock]
0x1800371ba  call    ?LockExclusive@?$ActivityBase@VSyncLogger@Internal@Sync@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800371bf  mov     rdi, [rsi+110h]
0x1800371c6  call    ?Provider@Reliability@Providers@TraceLog@@SAPEBU_tlgProvider_t@@XZ; TraceLog::Providers::Reliability::Provider(void)
0x1800371cb  mov     r8d, [rax]
0x1800371ce  cmp     r8d, 4
0x1800371d2  jbe     short loc_1800371E5
0x1800371d4  lea     rdx, [rdi+8]; ActivityId
0x1800371d8  mov     ecx, 3; ControlCode
0x1800371dd  call    cs:__imp_EventActivityIdControl
0x1800371e3  jmp     short loc_1800371EC
0x1800371e5  xorps   xmm0, xmm0
0x1800371e8  movups  xmmword ptr [rdi+8], xmm0
0x1800371ec  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800371f0  xor     r14d, r14d
0x1800371f3  mov     dword ptr [rdi], 1
0x1800371f9  test    rcx, rcx
0x1800371fc  jz      short loc_180037204
0x1800371fe  call    cs:__imp_ReleaseSRWLockExclusive
0x180037204  call    ?Provider@Reliability@Providers@TraceLog@@SAPEBU_tlgProvider_t@@XZ; TraceLog::Providers::Reliability::Provider(void)
0x180037209  mov     rdi, rax
0x18003720c  mov     ecx, [rax]
0x18003720e  cmp     ecx, 4
0x180037211  jbe     loc_1800372D4
0x180037217  cmp     qword ptr [rbx+18h], 7
0x18003721c  jbe     short loc_180037221
0x18003721e  mov     rbx, [rbx]
0x180037221  call    cs:__imp_GetCurrentThreadId
0x180037227  mov     r8, [rsi+110h]
0x18003722e  mov     dword ptr [rbp+57h+SRWLock], eax
0x180037231  mov     [rbp+57h+var_78], 1000000h
0x180037239  cmp     [r8+4], r14b
0x18003723d  jz      short loc_18003725A
0x18003723f  lea     r9, [r8+18h]
0x180037243  cmp     [r9], r14d
0x180037246  jnz     short loc_18003725D
0x180037248  cmp     [r9+4], r14d
0x18003724c  jnz     short loc_18003725D
0x18003724e  cmp     [r9+8], r14d
0x180037252  jnz     short loc_18003725D
0x180037254  cmp     [r9+0Ch], r14d
0x180037258  jnz     short loc_18003725D
0x18003725a  mov     r9, r14
0x18003725d  test    rbx, rbx
0x180037260  jz      short loc_180037279
0x180037262  or      rax, 0FFFFFFFFFFFFFFFFh
0x180037266  inc     rax
0x180037269  cmp     [rbx+rax*2], r14w
0x18003726e  jnz     short loc_180037266
0x180037270  lea     eax, ds:2[rax*2]
0x180037277  jmp     short loc_180037285
0x180037279  lea     rbx, SubKey
0x180037280  mov     eax, 2
0x180037285  mov     [rbp+57h+var_28], eax
0x180037288  lea     rdx, unk_1800D55A8
0x18003728f  lea     rax, [rbp+57h+SRWLock]
0x180037293  mov     [rbp+57h+var_30], rbx
0x180037297  mov     [rbp+57h+var_40], rax
0x18003729b  add     r8, 8
0x18003729f  lea     rax, [rbp+57h+var_78]
0x1800372a3  mov     [rbp+57h+var_24], r14d
0x1800372a7  mov     [rbp+57h+var_50], rax
0x1800372ab  mov     rcx, rdi
0x1800372ae  lea     rax, [rbp+57h+var_70]
0x1800372b2  mov     [rbp+57h+var_38], 4
0x1800372ba  mov     [rsp+0B0h+var_88], rax
0x1800372bf  mov     [rsp+0B0h+var_90], 5
0x1800372c7  mov     [rbp+57h+var_48], 8
0x1800372cf  call    _tlgWriteTransfer_EventWriteTransfer
0x1800372d4  lea     rcx, [rsi+120h]; this
0x1800372db  cmp     [rcx+18h], r14d
0x1800372df  jnz     short loc_1800372E6
0x1800372e1  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800372e6  mov     rcx, [rbp+57h+var_20]
0x1800372ea  xor     rcx, rsp; StackCookie
0x1800372ed  call    __security_check_cookie
0x1800372f2  lea     r11, [rsp+0B0h+var_10]
0x1800372fa  mov     rbx, [r11+28h]
0x1800372fe  mov     rsi, [r11+30h]
0x180037302  mov     rsp, r11
0x180037305  pop     r14
0x180037307  pop     rdi
0x180037308  pop     rbp
0x180037309  retn
```
