# AAMTraceProvider::BackgroundActivation::StartActivity(unsigned __int64)

- ea: `0x180013670`
- end: `0x180013891`
- name: `?StartActivity@BackgroundActivation@AAMTraceProvider@@QEAAX_K@Z`
- size: `545`
- prototype: `void __fastcall(AAMTraceProvider::BackgroundActivation *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180011ad0`

## callees

- `0x180013670`
- `0x180024840`
- `0x18002f010`
- `0x18005ae90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800136c8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800136e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001373d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800136c8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800136e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001373d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800136b2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800136b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001377a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001377a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001385d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001385d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180013720`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180013720`

## pseudocode

```c
void __fastcall AAMTraceProvider::BackgroundActivation::StartActivity(
        AAMTraceProvider::BackgroundActivation *this,
        __int64 a2)
{
  RTL_SRWLOCK *v2; // rbx
  RTL_SRWLOCK *v5; // rbx
  __int64 v6; // rsi
  __int64 v7; // rcx
  __int64 v8; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v10; // r8
  const GUID *v11; // r9
  PSRWLOCK v12; // [rsp+38h] [rbp-61h] BYREF
  __int64 v13; // [rsp+40h] [rbp-59h] BYREF
  __int64 v14; // [rsp+48h] [rbp-51h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-39h] BYREF
  __int16 *v17; // [rsp+70h] [rbp-29h]
  int v18; // [rsp+78h] [rbp-21h]
  int v19; // [rsp+7Ch] [rbp-1Dh]
  __int64 *v20; // [rsp+80h] [rbp-19h]
  __int64 v21; // [rsp+88h] [rbp-11h]
  PSRWLOCK *v22; // [rsp+90h] [rbp-9h]
  __int64 v23; // [rsp+98h] [rbp-1h]
  __int64 *v24; // [rsp+A0h] [rbp+7h]
  __int64 v25; // [rsp+A8h] [rbp+Fh]

  v2 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
  if ( v2 )
  {
    v5 = v2 + 33;
    AcquireSRWLockExclusive(v5);
  }
  else
  {
    v12 = 0;
    v5 = 0;
  }
  v6 = *((_QWORD *)this + 34);
  v7 = *((_QWORD *)AAMTraceProvider::Instance() + 1);
  if ( *(_DWORD *)v7 > 5u && (*(_QWORD *)(v7 + 16) & 1) != 0 && (*(_QWORD *)(v7 + 24) & 1LL) == *(_QWORD *)(v7 + 24) )
    EventActivityIdControl(3u, (LPGUID)(v6 + 8));
  else
    *(_OWORD *)(v6 + 8) = 0;
  *(_DWORD *)v6 = 1;
  if ( v5 )
    ReleaseSRWLockExclusive(v5);
  v8 = *((_QWORD *)AAMTraceProvider::Instance() + 1);
  if ( *(_DWORD *)v8 > 5u && (*(_QWORD *)(v8 + 16) & 1) != 0 && (*(_QWORD *)(v8 + 24) & 1LL) == *(_QWORD *)(v8 + 24) )
  {
    v13 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v10 = *((_QWORD *)this + 34);
    LODWORD(v12) = CurrentThreadId;
    v14 = 0;
    if ( !*(_BYTE *)(v10 + 4)
      || (v11 = (const GUID *)(v10 + 24), !*(_DWORD *)(v10 + 24))
      && !*(_DWORD *)(v10 + 28)
      && !*(_DWORD *)(v10 + 32)
      && !*(_DWORD *)(v10 + 36) )
    {
      v11 = 0;
    }
    v25 = 8;
    v24 = &v13;
    v23 = 4;
    v22 = &v12;
    v21 = 8;
    v20 = &v14;
    *(_DWORD *)&EventDescriptor.Level = 261;
    UserData.Ptr = *(_QWORD *)(v8 + 8);
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 1;
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    v17 = &word_1800B741E;
    UserData.Reserved = 2;
    v18 = 81;
    v19 = 1;
    EventWriteTransfer(*(_QWORD *)(v8 + 32), &EventDescriptor, (LPCGUID)(v10 + 8), v11, 5u, &UserData);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((AAMTraceProvider::BackgroundActivation *)((char *)this + 288));
}

```

## disassembly

```asm
0x180013670  push    rbp
0x180013672  push    rbx
0x180013673  push    rsi
0x180013674  push    rdi
0x180013675  push    r14
0x180013677  push    r15
0x180013679  lea     rbp, [rsp-2Fh]
0x18001367e  sub     rsp, 0C8h
0x180013685  mov     rax, cs:__security_cookie
0x18001368c  xor     rax, rsp
0x18001368f  mov     [rbp+57h+var_40], rax
0x180013693  mov     rbx, [rcx+118h]
0x18001369a  xor     r15d, r15d
0x18001369d  mov     r14, rdx
0x1800136a0  mov     rdi, rcx
0x1800136a3  test    rbx, rbx
0x1800136a6  jz      short loc_1800136D0
0x1800136a8  add     rbx, 108h
0x1800136af  mov     rcx, rbx; SRWLock
0x1800136b2  call    cs:__imp_AcquireSRWLockExclusive
0x1800136b8  lea     rax, [rbp+57h+SRWLock]
0x1800136bc  mov     [rax], r15
0x1800136bf  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800136c3  test    rcx, rcx
0x1800136c6  jz      short loc_1800136E9
0x1800136c8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800136ce  jmp     short loc_1800136E9
0x1800136d0  lea     rax, [rbp+57h+var_B8]
0x1800136d4  mov     [rax], r15
0x1800136d7  mov     rcx, [rbp+57h+var_B8]; SRWLock
0x1800136db  test    rcx, rcx
0x1800136de  jz      short loc_1800136E6
0x1800136e0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800136e6  mov     rbx, r15
0x1800136e9  mov     rsi, [rdi+110h]
0x1800136f0  call    ?Instance@AAMTraceProvider@@KAPEAV1@XZ; AAMTraceProvider::Instance(void)
0x1800136f5  mov     rcx, [rax+8]
0x1800136f9  mov     eax, [rcx]
0x1800136fb  cmp     eax, 5
0x1800136fe  jbe     short loc_180013728
0x180013700  mov     rdx, [rcx+18h]
0x180013704  mov     rax, [rcx+10h]
0x180013708  test    al, 1
0x18001370a  jz      short loc_180013728
0x18001370c  mov     rax, rdx
0x18001370f  and     eax, 1
0x180013712  cmp     rax, rdx
0x180013715  jnz     short loc_180013728
0x180013717  lea     rdx, [rsi+8]; ActivityId
0x18001371b  mov     ecx, 3; ControlCode
0x180013720  call    cs:__imp_EventActivityIdControl
0x180013726  jmp     short loc_18001372F
0x180013728  xorps   xmm0, xmm0
0x18001372b  movups  xmmword ptr [rsi+8], xmm0
0x18001372f  mov     dword ptr [rsi], 1
0x180013735  test    rbx, rbx
0x180013738  jz      short loc_180013743
0x18001373a  mov     rcx, rbx; SRWLock
0x18001373d  call    cs:__imp_ReleaseSRWLockExclusive
0x180013743  call    ?Instance@AAMTraceProvider@@KAPEAV1@XZ; AAMTraceProvider::Instance(void)
0x180013748  mov     rbx, [rax+8]
0x18001374c  mov     eax, [rbx]
0x18001374e  cmp     eax, 5
0x180013751  jbe     loc_180013863
0x180013757  mov     rcx, [rbx+18h]
0x18001375b  mov     rax, [rbx+10h]
0x18001375f  test    al, 1
0x180013761  jz      loc_180013863
0x180013767  mov     rax, rcx
0x18001376a  and     eax, 1
0x18001376d  cmp     rax, rcx
0x180013770  jnz     loc_180013863
0x180013776  mov     [rbp+57h+var_B0], r14
0x18001377a  call    cs:__imp_GetCurrentThreadId
0x180013780  mov     r8, [rdi+110h]
0x180013787  mov     dword ptr [rbp+57h+var_B8], eax
0x18001378a  mov     [rbp+57h+var_A8], r15
0x18001378e  cmp     [r8+4], r15b
0x180013792  jz      short loc_1800137B0
0x180013794  cmp     [r8+18h], r15d
0x180013798  lea     r9, [r8+18h]
0x18001379c  jnz     short loc_1800137B3
0x18001379e  cmp     [r9+4], r15d
0x1800137a2  jnz     short loc_1800137B3
0x1800137a4  cmp     [r9+8], r15d
0x1800137a8  jnz     short loc_1800137B3
0x1800137aa  cmp     [r9+0Ch], r15d
0x1800137ae  jnz     short loc_1800137B3
0x1800137b0  mov     r9, r15; RelatedActivityId
0x1800137b3  mov     [rbp+57h+var_48], 8
0x1800137bb  lea     rax, [rbp+57h+var_B0]
0x1800137bf  mov     [rbp+57h+var_50], rax
0x1800137c3  lea     rcx, _TraceLoggingMetadata
0x1800137ca  mov     [rbp+57h+var_58], 4
0x1800137d2  lea     rax, [rbp+57h+var_B8]
0x1800137d6  mov     [rbp+57h+var_60], rax
0x1800137da  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x1800137de  lea     rax, [rbp+57h+var_A8]
0x1800137e2  mov     [rbp+57h+var_68], 8
0x1800137ea  mov     [rbp+57h+var_70], rax
0x1800137ee  add     r8, 8; ActivityId
0x1800137f2  movzx   eax, cs:word_1800B7414
0x1800137f9  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x1800137fc  mov     rax, [rbx+8]
0x180013800  mov     [rbp+57h+var_90.Ptr], rax
0x180013804  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18001380b  mov     [rbp+57h+EventDescriptor.Keyword], 1
0x180013813  movzx   eax, word ptr [rax]
0x180013816  mov     [rbp+57h+var_90.Size], eax
0x180013819  lea     rax, word_1800B741E
0x180013820  mov     [rbp+57h+var_80], rax
0x180013824  lea     rax, _TraceLoggingMetadataEnd
0x18001382b  sub     eax, ecx
0x18001382d  mov     dword ptr [rbp+57h+var_90.0Ch], 2
0x180013834  mov     [rbp+57h+var_78], 51h ; 'Q'
0x18001383b  mov     [rbp+57h+var_74], 1
0x180013842  mov     dword ptr [rbp+57h+SRWLock], eax
0x180013845  mov     eax, dword ptr [rbp+57h+SRWLock]
0x180013848  mov     rcx, [rbx+20h]; RegHandle
0x18001384c  lea     rax, [rbp+57h+var_90]
0x180013850  mov     [rsp+0F0h+UserData], rax; UserData
0x180013855  mov     [rsp+0F0h+UserDataCount], 5; UserDataCount
0x18001385d  call    cs:__imp_EventWriteTransfer
0x180013863  lea     rcx, [rdi+120h]; this
0x18001386a  cmp     [rcx+18h], r15d
0x18001386e  jnz     short loc_180013875
0x180013870  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180013875  mov     rcx, [rbp+57h+var_40]
0x180013879  xor     rcx, rsp; StackCookie
0x18001387c  call    __security_check_cookie
0x180013881  add     rsp, 0C8h
0x180013888  pop     r15
0x18001388a  pop     r14
0x18001388c  pop     rdi
0x18001388d  pop     rsi
0x18001388e  pop     rbx
0x18001388f  pop     rbp
0x180013890  retn
```
