# WaasMedic::TelemetryProvider::AgentRunActivity::StartActivity(char const *)

- ea: `0x14000a314`
- end: `0x14000a4e7`
- name: `?StartActivity@AgentRunActivity@TelemetryProvider@WaasMedic@@QEAAXPEBD@Z`
- size: `467`
- prototype: `void __fastcall(WaasMedic::TelemetryProvider::AgentRunActivity *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x14000a8f0`

## callees

- `0x14000198c`
- `0x140002a30`
- `0x1400056a0`
- `0x14000830c`
- `0x14000885c`
- `0x14000a314`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000a3a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000a3a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a3de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a4bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a3de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a4bd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14000a384`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14000a384`

## pseudocode

```c
void __fastcall WaasMedic::TelemetryProvider::AgentRunActivity::StartActivity(
        WaasMedic::TelemetryProvider::AgentRunActivity *this,
        const char *a2)
{
  __int64 v4; // rbx
  const struct _tlgProvider_t *v5; // rax
  RTL_SRWLOCK *v6; // rcx
  const struct _tlgProvider_t *v7; // rax
  const struct _tlgProvider_t *v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // rdx
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rax
  int v15; // eax
  _QWORD *v16; // rbx
  _QWORD *Local; // rax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-49h] BYREF
  __int64 v19; // [rsp+38h] [rbp-41h] BYREF
  _BYTE v20[32]; // [rsp+40h] [rbp-39h] BYREF
  __int64 *v21; // [rsp+60h] [rbp-19h]
  __int64 v22; // [rsp+68h] [rbp-11h]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp-9h]
  __int64 v24; // [rsp+78h] [rbp-1h]
  const char *v25; // [rsp+80h] [rbp+7h]
  int v26; // [rsp+88h] [rbp+Fh]
  int v27; // [rsp+8Ch] [rbp+13h]

  wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &SRWLock);
  v4 = *((_QWORD *)this + 34);
  v5 = WaasMedic::TelemetryProvider::Provider();
  if ( *(_DWORD *)v5 > 5u
    && (*((_QWORD *)v5 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v5 + 3) & 0x400000000000LL) == *((_QWORD *)v5 + 3) )
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
  v7 = WaasMedic::TelemetryProvider::Provider();
  v8 = v7;
  v9 = *(unsigned int *)v7;
  if ( (unsigned int)v9 > 5 )
  {
    v10 = *((_QWORD *)v7 + 3);
    v9 = *((_QWORD *)v7 + 2);
    if ( (v9 & 0x400000000000LL) != 0 )
    {
      v9 = v10 & 0x400000000000LL;
      if ( (v10 & 0x400000000000LL) == v10 )
      {
        CurrentThreadId = GetCurrentThreadId();
        v12 = *((_QWORD *)this + 34);
        LODWORD(SRWLock) = CurrentThreadId;
        v19 = 0x1000000;
        if ( !*(_BYTE *)(v12 + 4)
          || (v13 = v12 + 24, !*(_DWORD *)(v12 + 24))
          && !*(_DWORD *)(v12 + 28)
          && !*(_DWORD *)(v12 + 32)
          && !*(_DWORD *)(v12 + 36) )
        {
          v13 = 0;
        }
        if ( a2 )
        {
          v14 = -1;
          do
            ++v14;
          while ( a2[v14] );
          v15 = v14 + 1;
        }
        else
        {
          a2 = (const char *)&qword_1400150C8;
          v15 = 1;
        }
        v26 = v15;
        v25 = a2;
        p_SRWLock = &SRWLock;
        v27 = 0;
        v21 = &v19;
        v24 = 4;
        v22 = 8;
        tlgWriteTransfer_EventWriteTransfer(v8, word_140019C42, v12 + 8, v13, 5, v20);
      }
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v16 = (_QWORD *)((char *)this + 288);
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v9,
                          1);
      *v16 = Local;
      if ( Local )
      {
        *((_QWORD *)this + 38) = *Local;
        *Local = v16;
        *((_DWORD *)this + 78) = GetCurrentThreadId();
      }
    }
    else
    {
      *v16 = 0;
    }
  }
}

```

## disassembly

```asm
0x14000a314  push    rbp
0x14000a316  push    rbx
0x14000a317  push    rsi
0x14000a318  push    rdi
0x14000a319  push    r14
0x14000a31b  push    r15
0x14000a31d  lea     rbp, [rsp-2Fh]
0x14000a322  sub     rsp, 0A8h
0x14000a329  mov     rax, cs:__security_cookie
0x14000a330  xor     rax, rsp
0x14000a333  mov     [rbp+57h+var_40], rax
0x14000a337  mov     rsi, rdx
0x14000a33a  mov     rdi, rcx
0x14000a33d  lea     rdx, [rbp+57h+SRWLock]
0x14000a341  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14000a346  mov     rbx, [rdi+110h]
0x14000a34d  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x14000a352  mov     r15, 400000000000h
0x14000a35c  mov     edx, [rax]
0x14000a35e  cmp     edx, 5
0x14000a361  jbe     short loc_14000A38C
0x14000a363  mov     rcx, [rax+18h]
0x14000a367  mov     rax, [rax+10h]
0x14000a36b  test    r15, rax
0x14000a36e  jz      short loc_14000A38C
0x14000a370  mov     rax, rcx
0x14000a373  and     rax, r15
0x14000a376  cmp     rax, rcx
0x14000a379  jnz     short loc_14000A38C
0x14000a37b  lea     rdx, [rbx+8]; ActivityId
0x14000a37f  mov     ecx, 3; ControlCode
0x14000a384  call    cs:__imp_EventActivityIdControl
0x14000a38a  jmp     short loc_14000A393
0x14000a38c  xorps   xmm0, xmm0
0x14000a38f  movups  xmmword ptr [rbx+8], xmm0
0x14000a393  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x14000a397  xor     r14d, r14d
0x14000a39a  mov     dword ptr [rbx], 1
0x14000a3a0  test    rcx, rcx
0x14000a3a3  jz      short loc_14000A3AB
0x14000a3a5  call    cs:__imp_ReleaseSRWLockExclusive
0x14000a3ab  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x14000a3b0  mov     rbx, rax
0x14000a3b3  mov     ecx, [rax]
0x14000a3b5  cmp     ecx, 5
0x14000a3b8  jbe     loc_14000A48B
0x14000a3be  mov     rdx, [rax+18h]
0x14000a3c2  mov     rcx, [rax+10h]
0x14000a3c6  test    r15, rcx
0x14000a3c9  jz      loc_14000A48B
0x14000a3cf  mov     rcx, rdx
0x14000a3d2  and     rcx, r15
0x14000a3d5  cmp     rcx, rdx
0x14000a3d8  jnz     loc_14000A48B
0x14000a3de  call    cs:__imp_GetCurrentThreadId
0x14000a3e4  mov     r8, [rdi+110h]
0x14000a3eb  mov     dword ptr [rbp+57h+SRWLock], eax
0x14000a3ee  mov     [rbp+57h+var_98], 1000000h
0x14000a3f6  cmp     [r8+4], r14b
0x14000a3fa  jz      short loc_14000A417
0x14000a3fc  lea     r9, [r8+18h]
0x14000a400  cmp     [r9], r14d
0x14000a403  jnz     short loc_14000A41A
0x14000a405  cmp     [r9+4], r14d
0x14000a409  jnz     short loc_14000A41A
0x14000a40b  cmp     [r9+8], r14d
0x14000a40f  jnz     short loc_14000A41A
0x14000a411  cmp     [r9+0Ch], r14d
0x14000a415  jnz     short loc_14000A41A
0x14000a417  mov     r9, r14
0x14000a41a  test    rsi, rsi
0x14000a41d  jz      short loc_14000A430
0x14000a41f  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000a423  inc     rax
0x14000a426  cmp     [rsi+rax], r14b
0x14000a42a  jnz     short loc_14000A423
0x14000a42c  inc     eax
0x14000a42e  jmp     short loc_14000A43C
0x14000a430  lea     rsi, qword_1400150C8
0x14000a437  mov     eax, 1
0x14000a43c  mov     [rbp+57h+var_48], eax
0x14000a43f  lea     rdx, word_140019C42
0x14000a446  lea     rax, [rbp+57h+SRWLock]
0x14000a44a  mov     [rbp+57h+var_50], rsi
0x14000a44e  mov     [rbp+57h+var_60], rax
0x14000a452  add     r8, 8
0x14000a456  lea     rax, [rbp+57h+var_98]
0x14000a45a  mov     [rbp+57h+var_44], r14d
0x14000a45e  mov     [rbp+57h+var_70], rax
0x14000a462  mov     rcx, rbx
0x14000a465  lea     rax, [rbp+57h+var_90]
0x14000a469  mov     [rbp+57h+var_58], 4
0x14000a471  mov     [rsp+0D0h+var_A8], rax
0x14000a476  mov     [rsp+0D0h+var_B0], 5
0x14000a47e  mov     [rbp+57h+var_68], 8
0x14000a486  call    _tlgWriteTransfer_EventWriteTransfer
0x14000a48b  cmp     [rdi+138h], r14d
0x14000a492  jnz     short loc_14000A4CB
0x14000a494  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r14; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14000a49b  lea     rbx, [rdi+120h]
0x14000a4a2  jz      short loc_14000A4C8
0x14000a4a4  mov     dl, 1
0x14000a4a6  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x14000a4ab  mov     [rbx], rax
0x14000a4ae  test    rax, rax
0x14000a4b1  jz      short loc_14000A4CB
0x14000a4b3  mov     rcx, [rax]
0x14000a4b6  mov     [rbx+10h], rcx
0x14000a4ba  mov     [rax], rbx
0x14000a4bd  call    cs:__imp_GetCurrentThreadId
0x14000a4c3  mov     [rbx+18h], eax
0x14000a4c6  jmp     short loc_14000A4CB
0x14000a4c8  mov     [rbx], r14
0x14000a4cb  mov     rcx, [rbp+57h+var_40]
0x14000a4cf  xor     rcx, rsp; StackCookie
0x14000a4d2  call    __security_check_cookie
0x14000a4d7  add     rsp, 0A8h
0x14000a4de  pop     r15
0x14000a4e0  pop     r14
0x14000a4e2  pop     rdi
0x14000a4e3  pop     rsi
0x14000a4e4  pop     rbx
0x14000a4e5  pop     rbp
0x14000a4e6  retn
```
