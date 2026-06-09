# ServiceHostTelemetry::ServiceStartActivity::StartActivity(ushort const *)

- ea: `0x18000f094`
- end: `0x18000f284`
- name: `?StartActivity@ServiceStartActivity@ServiceHostTelemetry@@QEAAXPEBG@Z`
- size: `496`
- prototype: `void __fastcall(ServiceHostTelemetry::ServiceStartActivity *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000e9e8`
- `0x180010444`

## callees

- `0x180001bdc`
- `0x180002bc0`
- `0x180005330`
- `0x18000a648`
- `0x18000e47c`
- `0x18000f094`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f125`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f125`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f165`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f25a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f165`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f25a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000f104`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000f104`

## pseudocode

```c
void __fastcall ServiceHostTelemetry::ServiceStartActivity::StartActivity(
        ServiceHostTelemetry::ServiceStartActivity *this,
        const unsigned __int16 *a2)
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
  int v18; // [rsp+30h] [rbp-69h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-61h] BYREF
  __int64 v20; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v21[32]; // [rsp+50h] [rbp-49h] BYREF
  __int64 *v22; // [rsp+70h] [rbp-29h]
  __int64 v23; // [rsp+78h] [rbp-21h]
  PSRWLOCK *p_SRWLock; // [rsp+80h] [rbp-19h]
  __int64 v25; // [rsp+88h] [rbp-11h]
  const unsigned __int16 *v26; // [rsp+90h] [rbp-9h]
  int v27; // [rsp+98h] [rbp-1h]
  int v28; // [rsp+9Ch] [rbp+3h]
  int *v29; // [rsp+A0h] [rbp+7h]
  __int64 v30; // [rsp+A8h] [rbp+Fh]

  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &SRWLock);
  v4 = *((_QWORD *)this + 34);
  v5 = ServiceHostLogging::Provider();
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
  v7 = ServiceHostLogging::Provider();
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
        v18 = 1;
        CurrentThreadId = GetCurrentThreadId();
        v12 = *((_QWORD *)this + 34);
        LODWORD(SRWLock) = CurrentThreadId;
        v20 = 0x1000000;
        if ( !*(_BYTE *)(v12 + 4)
          || (v13 = v12 + 24, !*(_DWORD *)(v12 + 24))
          && !*(_DWORD *)(v12 + 28)
          && !*(_DWORD *)(v12 + 32)
          && !*(_DWORD *)(v12 + 36) )
        {
          v13 = 0;
        }
        v30 = 4;
        v29 = &v18;
        if ( a2 )
        {
          v14 = -1;
          do
            ++v14;
          while ( a2[v14] );
          v15 = 2 * v14 + 2;
        }
        else
        {
          a2 = (const unsigned __int16 *)&qword_1800142D0;
          v15 = 2;
        }
        v27 = v15;
        v26 = a2;
        p_SRWLock = &SRWLock;
        v28 = 0;
        v22 = &v20;
        v25 = 4;
        v23 = 8;
        tlgWriteTransfer_EventWriteTransfer(v8, &dword_180015A6C, v12 + 8, v13, 6, v21);
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
0x18000f094  push    rbp
0x18000f096  push    rbx
0x18000f097  push    rsi
0x18000f098  push    rdi
0x18000f099  push    r14
0x18000f09b  push    r15
0x18000f09d  lea     rbp, [rsp-2Fh]
0x18000f0a2  sub     rsp, 0C8h
0x18000f0a9  mov     rax, cs:__security_cookie
0x18000f0b0  xor     rax, rsp
0x18000f0b3  mov     [rbp+57h+var_40], rax
0x18000f0b7  mov     rsi, rdx
0x18000f0ba  mov     rdi, rcx
0x18000f0bd  lea     rdx, [rbp+57h+SRWLock]
0x18000f0c1  call    ?LockExclusive@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000f0c6  mov     rbx, [rdi+110h]
0x18000f0cd  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18000f0d2  mov     r15, 400000000000h
0x18000f0dc  mov     edx, [rax]
0x18000f0de  cmp     edx, 5
0x18000f0e1  jbe     short loc_18000F10C
0x18000f0e3  mov     rcx, [rax+18h]
0x18000f0e7  mov     rax, [rax+10h]
0x18000f0eb  test    r15, rax
0x18000f0ee  jz      short loc_18000F10C
0x18000f0f0  mov     rax, rcx
0x18000f0f3  and     rax, r15
0x18000f0f6  cmp     rax, rcx
0x18000f0f9  jnz     short loc_18000F10C
0x18000f0fb  lea     rdx, [rbx+8]; ActivityId
0x18000f0ff  mov     ecx, 3; ControlCode
0x18000f104  call    cs:__imp_EventActivityIdControl
0x18000f10a  jmp     short loc_18000F113
0x18000f10c  xorps   xmm0, xmm0
0x18000f10f  movups  xmmword ptr [rbx+8], xmm0
0x18000f113  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18000f117  xor     r14d, r14d
0x18000f11a  mov     dword ptr [rbx], 1
0x18000f120  test    rcx, rcx
0x18000f123  jz      short loc_18000F12B
0x18000f125  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f12b  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18000f130  mov     rbx, rax
0x18000f133  mov     ecx, [rax]
0x18000f135  cmp     ecx, 5
0x18000f138  jbe     loc_18000F228
0x18000f13e  mov     rdx, [rax+18h]
0x18000f142  mov     rcx, [rax+10h]
0x18000f146  test    r15, rcx
0x18000f149  jz      loc_18000F228
0x18000f14f  mov     rcx, rdx
0x18000f152  and     rcx, r15
0x18000f155  cmp     rcx, rdx
0x18000f158  jnz     loc_18000F228
0x18000f15e  mov     [rbp+57h+var_C0], 1
0x18000f165  call    cs:__imp_GetCurrentThreadId
0x18000f16b  mov     r8, [rdi+110h]
0x18000f172  mov     dword ptr [rbp+57h+SRWLock], eax
0x18000f175  mov     [rbp+57h+var_B0], 1000000h
0x18000f17d  cmp     [r8+4], r14b
0x18000f181  jz      short loc_18000F19E
0x18000f183  lea     r9, [r8+18h]
0x18000f187  cmp     [r9], r14d
0x18000f18a  jnz     short loc_18000F1A1
0x18000f18c  cmp     [r9+4], r14d
0x18000f190  jnz     short loc_18000F1A1
0x18000f192  cmp     [r9+8], r14d
0x18000f196  jnz     short loc_18000F1A1
0x18000f198  cmp     [r9+0Ch], r14d
0x18000f19c  jnz     short loc_18000F1A1
0x18000f19e  mov     r9, r14
0x18000f1a1  mov     [rbp+57h+var_48], 4
0x18000f1a9  lea     rax, [rbp+57h+var_C0]
0x18000f1ad  mov     [rbp+57h+var_50], rax
0x18000f1b1  test    rsi, rsi
0x18000f1b4  jz      short loc_18000F1CD
0x18000f1b6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f1ba  inc     rax
0x18000f1bd  cmp     [rsi+rax*2], r14w
0x18000f1c2  jnz     short loc_18000F1BA
0x18000f1c4  lea     eax, ds:2[rax*2]
0x18000f1cb  jmp     short loc_18000F1D9
0x18000f1cd  lea     rsi, qword_1800142D0
0x18000f1d4  mov     eax, 2
0x18000f1d9  mov     [rbp+57h+var_58], eax
0x18000f1dc  lea     rdx, dword_180015A6C
0x18000f1e3  lea     rax, [rbp+57h+SRWLock]
0x18000f1e7  mov     [rbp+57h+var_60], rsi
0x18000f1eb  mov     [rbp+57h+var_70], rax
0x18000f1ef  add     r8, 8
0x18000f1f3  lea     rax, [rbp+57h+var_B0]
0x18000f1f7  mov     [rbp+57h+var_54], r14d
0x18000f1fb  mov     [rbp+57h+var_80], rax
0x18000f1ff  mov     rcx, rbx
0x18000f202  lea     rax, [rbp+57h+var_A0]
0x18000f206  mov     [rbp+57h+var_68], 4
0x18000f20e  mov     [rsp+0F0h+var_C8], rax
0x18000f213  mov     [rsp+0F0h+var_D0], 6
0x18000f21b  mov     [rbp+57h+var_78], 8
0x18000f223  call    _tlgWriteTransfer_EventWriteTransfer
0x18000f228  cmp     [rdi+138h], r14d
0x18000f22f  jnz     short loc_18000F268
0x18000f231  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r14; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000f238  lea     rbx, [rdi+120h]
0x18000f23f  jz      short loc_18000F265
0x18000f241  mov     dl, 1
0x18000f243  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000f248  mov     [rbx], rax
0x18000f24b  test    rax, rax
0x18000f24e  jz      short loc_18000F268
0x18000f250  mov     rcx, [rax]
0x18000f253  mov     [rbx+10h], rcx
0x18000f257  mov     [rax], rbx
0x18000f25a  call    cs:__imp_GetCurrentThreadId
0x18000f260  mov     [rbx+18h], eax
0x18000f263  jmp     short loc_18000F268
0x18000f265  mov     [rbx], r14
0x18000f268  mov     rcx, [rbp+57h+var_40]
0x18000f26c  xor     rcx, rsp; StackCookie
0x18000f26f  call    __security_check_cookie
0x18000f274  add     rsp, 0C8h
0x18000f27b  pop     r15
0x18000f27d  pop     r14
0x18000f27f  pop     rdi
0x18000f280  pop     rsi
0x18000f281  pop     rbx
0x18000f282  pop     rbp
0x18000f283  retn
```
