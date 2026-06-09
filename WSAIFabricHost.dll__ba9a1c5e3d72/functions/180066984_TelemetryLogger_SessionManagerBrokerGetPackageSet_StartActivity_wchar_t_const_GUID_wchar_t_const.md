# TelemetryLogger::SessionManagerBrokerGetPackageSet::StartActivity(wchar_t const *,_GUID,wchar_t const *)

- ea: `0x180066984`
- end: `0x180066b7d`
- name: `?StartActivity@SessionManagerBrokerGetPackageSet@TelemetryLogger@@QEAAXPEB_WU_GUID@@0@Z`
- size: `505`
- prototype: `void __fastcall(TelemetryLogger::SessionManagerBrokerGetPackageSet *__hidden this, const wchar_t *, struct _GUID *__struct_ptr, const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800606f0`

## callees

- `0x1800017dc`
- `0x180004ca0`
- `0x180017790`
- `0x18004b8f4`
- `0x1800625bc`
- `0x180066984`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180066a23`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180066a23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180066a5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180066a5d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180066a02`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180066a02`

## pseudocode

```c
void __fastcall TelemetryLogger::SessionManagerBrokerGetPackageSet::StartActivity(
        TelemetryLogger::SessionManagerBrokerGetPackageSet *this,
        const wchar_t *a2,
        struct _GUID *a3,
        const wchar_t *a4)
{
  __int64 v8; // rbx
  __int64 v9; // rdx
  RTL_SRWLOCK *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  const GUID *v15; // r9
  __int64 v16; // rax
  int v17; // edx
  __int64 v18; // rcx
  int v19; // ecx
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-79h] BYREF
  __int64 v21; // [rsp+38h] [rbp-71h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+40h] [rbp-69h] BYREF
  __int64 *v23; // [rsp+60h] [rbp-49h]
  __int64 v24; // [rsp+68h] [rbp-41h]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp-39h]
  __int64 v26; // [rsp+78h] [rbp-31h]
  const wchar_t *v27; // [rsp+80h] [rbp-29h]
  int v28; // [rsp+88h] [rbp-21h]
  int v29; // [rsp+8Ch] [rbp-1Dh]
  struct _GUID *v30; // [rsp+90h] [rbp-19h]
  __int64 v31; // [rsp+98h] [rbp-11h]
  const wchar_t *v32; // [rsp+A0h] [rbp-9h]
  int v33; // [rsp+A8h] [rbp-1h]
  int v34; // [rsp+ACh] [rbp+3h]

  wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v8 = *((_QWORD *)this + 34);
  v9 = *((_QWORD *)TelemetryLogger::Instance() + 1);
  if ( *(_DWORD *)v9 > 5u
    && (*(_QWORD *)(v9 + 16) & 0x200000000000LL) != 0
    && (*(_QWORD *)(v9 + 24) & 0x200000000000LL) == *(_QWORD *)(v9 + 24) )
  {
    EventActivityIdControl(3u, (LPGUID)(v8 + 8));
  }
  else
  {
    *(_OWORD *)(v8 + 8) = 0;
  }
  v10 = SRWLock;
  *(_DWORD *)v8 = 1;
  if ( v10 )
    ReleaseSRWLockExclusive(v10);
  v12 = *((_QWORD *)TelemetryLogger::Instance() + 1);
  if ( *(_DWORD *)v12 > 5u
    && (*(_QWORD *)(v12 + 16) & 0x200000000000LL) != 0
    && (*(_QWORD *)(v12 + 24) & 0x200000000000LL) == *(_QWORD *)(v12 + 24) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v14 = *((_QWORD *)this + 34);
    LODWORD(SRWLock) = CurrentThreadId;
    v21 = 0x1000000;
    if ( !*(_BYTE *)(v14 + 4)
      || (v15 = (const GUID *)(v14 + 24), !*(_DWORD *)(v14 + 24))
      && !*(_DWORD *)(v14 + 28)
      && !*(_DWORD *)(v14 + 32)
      && !*(_DWORD *)(v14 + 36) )
    {
      v15 = 0;
    }
    v16 = -1;
    v17 = 2;
    if ( a4 )
    {
      v18 = -1;
      do
        ++v18;
      while ( a4[v18] );
      v19 = 2 * v18 + 2;
    }
    else
    {
      a4 = &pszText;
      v19 = 2;
    }
    v32 = a4;
    v33 = v19;
    v34 = 0;
    v30 = a3;
    v31 = 16;
    if ( a2 )
    {
      do
        ++v16;
      while ( a2[v16] );
      v17 = 2 * v16 + 2;
    }
    else
    {
      a2 = &pszText;
    }
    v28 = v17;
    p_SRWLock = &SRWLock;
    v27 = a2;
    v23 = &v21;
    v29 = 0;
    v26 = 4;
    v24 = 8;
    tlgWriteTransfer_EventWriteTransfer(v12, (unsigned __int8 *)&unk_18009DB28, (const GUID *)(v14 + 8), v15, 7u, &v22);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (TelemetryLogger::SessionManagerBrokerGetPackageSet *)((char *)this + 288),
      v11);
}

```

## disassembly

```asm
0x180066984  push    rbp
0x180066986  push    rbx
0x180066987  push    rsi
0x180066988  push    rdi
0x180066989  push    r12
0x18006698b  push    r13
0x18006698d  push    r14
0x18006698f  push    r15
0x180066991  lea     rbp, [rsp-1Fh]
0x180066996  sub     rsp, 0C8h
0x18006699d  mov     rax, cs:__security_cookie
0x1800669a4  xor     rax, rsp
0x1800669a7  mov     [rbp+57h+var_50], rax
0x1800669ab  mov     rsi, rdx
0x1800669ae  mov     rdi, r9
0x1800669b1  lea     rdx, [rbp+57h+SRWLock]
0x1800669b5  mov     r15, r8
0x1800669b8  mov     r14, rcx
0x1800669bb  call    ?LockExclusive@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800669c0  mov     rbx, [r14+110h]
0x1800669c7  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x1800669cc  mov     r13, 200000000000h
0x1800669d6  mov     rdx, [rax+8]
0x1800669da  mov     eax, [rdx]
0x1800669dc  cmp     eax, 5
0x1800669df  jbe     short loc_180066A0A
0x1800669e1  mov     rcx, [rdx+18h]
0x1800669e5  mov     rax, [rdx+10h]
0x1800669e9  test    r13, rax
0x1800669ec  jz      short loc_180066A0A
0x1800669ee  mov     rax, rcx
0x1800669f1  and     rax, r13
0x1800669f4  cmp     rax, rcx
0x1800669f7  jnz     short loc_180066A0A
0x1800669f9  lea     rdx, [rbx+8]; ActivityId
0x1800669fd  mov     ecx, 3; ControlCode
0x180066a02  call    cs:__imp_EventActivityIdControl
0x180066a08  jmp     short loc_180066A11
0x180066a0a  xorps   xmm0, xmm0
0x180066a0d  movups  xmmword ptr [rbx+8], xmm0
0x180066a11  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180066a15  xor     r12d, r12d
0x180066a18  mov     dword ptr [rbx], 1
0x180066a1e  test    rcx, rcx
0x180066a21  jz      short loc_180066A29
0x180066a23  call    cs:__imp_ReleaseSRWLockExclusive
0x180066a29  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180066a2e  mov     rbx, [rax+8]
0x180066a32  mov     eax, [rbx]
0x180066a34  cmp     eax, 5
0x180066a37  jbe     loc_180066B4B
0x180066a3d  mov     rcx, [rbx+18h]
0x180066a41  mov     rax, [rbx+10h]
0x180066a45  test    r13, rax
0x180066a48  jz      loc_180066B4B
0x180066a4e  mov     rax, rcx
0x180066a51  and     rax, r13
0x180066a54  cmp     rax, rcx
0x180066a57  jnz     loc_180066B4B
0x180066a5d  call    cs:__imp_GetCurrentThreadId
0x180066a63  mov     r8, [r14+110h]
0x180066a6a  mov     dword ptr [rbp+57h+SRWLock], eax
0x180066a6d  mov     [rbp+57h+var_C8], 1000000h
0x180066a75  cmp     [r8+4], r12b
0x180066a79  jz      short loc_180066A96
0x180066a7b  lea     r9, [r8+18h]
0x180066a7f  cmp     [r9], r12d
0x180066a82  jnz     short loc_180066A99
0x180066a84  cmp     [r9+4], r12d
0x180066a88  jnz     short loc_180066A99
0x180066a8a  cmp     [r9+8], r12d
0x180066a8e  jnz     short loc_180066A99
0x180066a90  cmp     [r9+0Ch], r12d
0x180066a94  jnz     short loc_180066A99
0x180066a96  mov     r9, r12
0x180066a99  or      rax, 0FFFFFFFFFFFFFFFFh
0x180066a9d  mov     edx, 2
0x180066aa2  test    rdi, rdi
0x180066aa5  jz      short loc_180066ABD
0x180066aa7  mov     rcx, rax
0x180066aaa  inc     rcx
0x180066aad  cmp     [rdi+rcx*2], r12w
0x180066ab2  jnz     short loc_180066AAA
0x180066ab4  lea     ecx, ds:2[rcx*2]
0x180066abb  jmp     short loc_180066AC6
0x180066abd  lea     rdi, pszText
0x180066ac4  mov     ecx, edx
0x180066ac6  mov     [rbp+57h+var_60], rdi
0x180066aca  mov     [rbp+57h+var_58], ecx
0x180066acd  mov     [rbp+57h+var_54], r12d
0x180066ad1  mov     [rbp+57h+var_70], r15
0x180066ad5  mov     [rbp+57h+var_68], 10h
0x180066add  test    rsi, rsi
0x180066ae0  jz      short loc_180066AF5
0x180066ae2  inc     rax
0x180066ae5  cmp     [rsi+rax*2], r12w
0x180066aea  jnz     short loc_180066AE2
0x180066aec  lea     edx, ds:2[rax*2]
0x180066af3  jmp     short loc_180066AFC
0x180066af5  lea     rsi, pszText
0x180066afc  lea     rax, [rbp+57h+SRWLock]
0x180066b00  mov     [rbp+57h+var_78], edx
0x180066b03  mov     [rbp+57h+var_90], rax
0x180066b07  lea     rdx, unk_18009DB28
0x180066b0e  lea     rax, [rbp+57h+var_C8]
0x180066b12  mov     [rbp+57h+var_80], rsi
0x180066b16  mov     [rbp+57h+var_A0], rax
0x180066b1a  add     r8, 8
0x180066b1e  lea     rax, [rbp+57h+var_C0]
0x180066b22  mov     [rbp+57h+var_74], r12d
0x180066b26  mov     [rsp+100h+var_D8], rax
0x180066b2b  mov     rcx, rbx
0x180066b2e  mov     [rsp+100h+var_E0], 7
0x180066b36  mov     [rbp+57h+var_88], 4
0x180066b3e  mov     [rbp+57h+var_98], 8
0x180066b46  call    _tlgWriteTransfer_EventWriteTransfer
0x180066b4b  lea     rcx, [r14+120h]; this
0x180066b52  cmp     [rcx+18h], r12d
0x180066b56  jnz     short loc_180066B5D
0x180066b58  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180066b5d  mov     rcx, [rbp+57h+var_50]
0x180066b61  xor     rcx, rsp; StackCookie
0x180066b64  call    __security_check_cookie
0x180066b69  add     rsp, 0C8h
0x180066b70  pop     r15
0x180066b72  pop     r14
0x180066b74  pop     r13
0x180066b76  pop     r12
0x180066b78  pop     rdi
0x180066b79  pop     rsi
0x180066b7a  pop     rbx
0x180066b7b  pop     rbp
0x180066b7c  retn
```
