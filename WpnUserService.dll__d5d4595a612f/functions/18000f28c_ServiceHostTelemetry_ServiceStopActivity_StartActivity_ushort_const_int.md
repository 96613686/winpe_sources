# ServiceHostTelemetry::ServiceStopActivity::StartActivity(ushort const *,int)

- ea: `0x18000f28c`
- end: `0x18000f4a8`
- name: `?StartActivity@ServiceStopActivity@ServiceHostTelemetry@@QEAAXPEBGH@Z`
- size: `540`
- prototype: `void __fastcall(ServiceHostTelemetry::ServiceStopActivity *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000edbc`

## callees

- `0x180001bdc`
- `0x180002bc0`
- `0x180005330`
- `0x18000a648`
- `0x18000e47c`
- `0x18000f28c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f329`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f329`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f36d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f472`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f36d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f472`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000f308`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000f308`

## pseudocode

```c
void __fastcall ServiceHostTelemetry::ServiceStopActivity::StartActivity(
        ServiceHostTelemetry::ServiceStopActivity *this,
        const unsigned __int16 *a2,
        int a3)
{
  __int64 v6; // rbx
  const struct _tlgProvider_t *v7; // rax
  RTL_SRWLOCK *v8; // rcx
  const struct _tlgProvider_t *v9; // rax
  const struct _tlgProvider_t *v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // rdx
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rax
  int v17; // eax
  _QWORD *v18; // rbx
  _QWORD *Local; // rax
  int v20; // [rsp+30h] [rbp-69h] BYREF
  int v21; // [rsp+34h] [rbp-65h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-61h] BYREF
  __int64 v23; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v24[32]; // [rsp+50h] [rbp-49h] BYREF
  __int64 *v25; // [rsp+70h] [rbp-29h]
  __int64 v26; // [rsp+78h] [rbp-21h]
  PSRWLOCK *p_SRWLock; // [rsp+80h] [rbp-19h]
  __int64 v28; // [rsp+88h] [rbp-11h]
  const unsigned __int16 *v29; // [rsp+90h] [rbp-9h]
  int v30; // [rsp+98h] [rbp-1h]
  int v31; // [rsp+9Ch] [rbp+3h]
  int *v32; // [rsp+A0h] [rbp+7h]
  __int64 v33; // [rsp+A8h] [rbp+Fh]
  int *v34; // [rsp+B0h] [rbp+17h]
  __int64 v35; // [rsp+B8h] [rbp+1Fh]

  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &SRWLock);
  v6 = *((_QWORD *)this + 34);
  v7 = ServiceHostLogging::Provider();
  if ( *(_DWORD *)v7 > 5u
    && (*((_QWORD *)v7 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v7 + 3) & 0x400000000000LL) == *((_QWORD *)v7 + 3) )
  {
    EventActivityIdControl(3u, (LPGUID)(v6 + 8));
  }
  else
  {
    *(_OWORD *)(v6 + 8) = 0;
  }
  v8 = SRWLock;
  *(_DWORD *)v6 = 1;
  if ( v8 )
    ReleaseSRWLockExclusive(v8);
  v9 = ServiceHostLogging::Provider();
  v10 = v9;
  v11 = *(unsigned int *)v9;
  if ( (unsigned int)v11 > 5 )
  {
    v12 = *((_QWORD *)v9 + 3);
    v11 = *((_QWORD *)v9 + 2);
    if ( (v11 & 0x400000000000LL) != 0 )
    {
      v11 = v12 & 0x400000000000LL;
      if ( (v12 & 0x400000000000LL) == v12 )
      {
        v20 = 1;
        v21 = a3;
        CurrentThreadId = GetCurrentThreadId();
        v14 = *((_QWORD *)this + 34);
        LODWORD(SRWLock) = CurrentThreadId;
        v23 = 0x1000000;
        if ( !*(_BYTE *)(v14 + 4)
          || (v15 = v14 + 24, !*(_DWORD *)(v14 + 24))
          && !*(_DWORD *)(v14 + 28)
          && !*(_DWORD *)(v14 + 32)
          && !*(_DWORD *)(v14 + 36) )
        {
          v15 = 0;
        }
        v35 = 4;
        v34 = &v20;
        v32 = &v21;
        v33 = 4;
        if ( a2 )
        {
          v16 = -1;
          do
            ++v16;
          while ( a2[v16] );
          v17 = 2 * v16 + 2;
        }
        else
        {
          a2 = (const unsigned __int16 *)&qword_1800142D0;
          v17 = 2;
        }
        v30 = v17;
        v29 = a2;
        p_SRWLock = &SRWLock;
        v31 = 0;
        v25 = &v23;
        v28 = 4;
        v26 = 8;
        tlgWriteTransfer_EventWriteTransfer(v10, &word_1800156BE, v14 + 8, v15, 7, v24);
      }
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v18 = (_QWORD *)((char *)this + 288);
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v11,
                          1);
      *v18 = Local;
      if ( Local )
      {
        *((_QWORD *)this + 38) = *Local;
        *Local = v18;
        *((_DWORD *)this + 78) = GetCurrentThreadId();
      }
    }
    else
    {
      *v18 = 0;
    }
  }
}

```

## disassembly

```asm
0x18000f28c  mov     [rsp-8+arg_8], rbx
0x18000f291  mov     [rsp-8+arg_10], rsi
0x18000f296  push    rbp
0x18000f297  push    rdi
0x18000f298  push    r12
0x18000f29a  push    r14
0x18000f29c  push    r15
0x18000f29e  lea     rbp, [rsp-37h]
0x18000f2a3  sub     rsp, 0D0h
0x18000f2aa  mov     rax, cs:__security_cookie
0x18000f2b1  xor     rax, rsp
0x18000f2b4  mov     [rbp+57h+var_30], rax
0x18000f2b8  mov     rsi, rdx
0x18000f2bb  mov     r14d, r8d
0x18000f2be  lea     rdx, [rbp+57h+SRWLock]
0x18000f2c2  mov     rdi, rcx
0x18000f2c5  call    ?LockExclusive@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000f2ca  mov     rbx, [rdi+110h]
0x18000f2d1  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18000f2d6  mov     r12, 400000000000h
0x18000f2e0  mov     edx, [rax]
0x18000f2e2  cmp     edx, 5
0x18000f2e5  jbe     short loc_18000F310
0x18000f2e7  mov     rcx, [rax+18h]
0x18000f2eb  mov     rax, [rax+10h]
0x18000f2ef  test    r12, rax
0x18000f2f2  jz      short loc_18000F310
0x18000f2f4  mov     rax, rcx
0x18000f2f7  and     rax, r12
0x18000f2fa  cmp     rax, rcx
0x18000f2fd  jnz     short loc_18000F310
0x18000f2ff  lea     rdx, [rbx+8]; ActivityId
0x18000f303  mov     ecx, 3; ControlCode
0x18000f308  call    cs:__imp_EventActivityIdControl
0x18000f30e  jmp     short loc_18000F317
0x18000f310  xorps   xmm0, xmm0
0x18000f313  movups  xmmword ptr [rbx+8], xmm0
0x18000f317  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18000f31b  xor     r15d, r15d
0x18000f31e  mov     dword ptr [rbx], 1
0x18000f324  test    rcx, rcx
0x18000f327  jz      short loc_18000F32F
0x18000f329  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f32f  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18000f334  mov     rbx, rax
0x18000f337  mov     ecx, [rax]
0x18000f339  cmp     ecx, 5
0x18000f33c  jbe     loc_18000F440
0x18000f342  mov     rdx, [rax+18h]
0x18000f346  mov     rcx, [rax+10h]
0x18000f34a  test    r12, rcx
0x18000f34d  jz      loc_18000F440
0x18000f353  mov     rcx, rdx
0x18000f356  and     rcx, r12
0x18000f359  cmp     rcx, rdx
0x18000f35c  jnz     loc_18000F440
0x18000f362  mov     [rbp+57h+var_C0], 1
0x18000f369  mov     [rbp+57h+var_BC], r14d
0x18000f36d  call    cs:__imp_GetCurrentThreadId
0x18000f373  mov     r8, [rdi+110h]
0x18000f37a  mov     dword ptr [rbp+57h+SRWLock], eax
0x18000f37d  mov     [rbp+57h+var_B0], 1000000h
0x18000f385  cmp     [r8+4], r15b
0x18000f389  jz      short loc_18000F3A6
0x18000f38b  lea     r9, [r8+18h]
0x18000f38f  cmp     [r9], r15d
0x18000f392  jnz     short loc_18000F3A9
0x18000f394  cmp     [r9+4], r15d
0x18000f398  jnz     short loc_18000F3A9
0x18000f39a  cmp     [r9+8], r15d
0x18000f39e  jnz     short loc_18000F3A9
0x18000f3a0  cmp     [r9+0Ch], r15d
0x18000f3a4  jnz     short loc_18000F3A9
0x18000f3a6  mov     r9, r15
0x18000f3a9  mov     [rbp+57h+var_38], 4
0x18000f3b1  lea     rax, [rbp+57h+var_C0]
0x18000f3b5  mov     [rbp+57h+var_40], rax
0x18000f3b9  lea     rax, [rbp+57h+var_BC]
0x18000f3bd  mov     [rbp+57h+var_50], rax
0x18000f3c1  mov     [rbp+57h+var_48], 4
0x18000f3c9  test    rsi, rsi
0x18000f3cc  jz      short loc_18000F3E5
0x18000f3ce  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f3d2  inc     rax
0x18000f3d5  cmp     [rsi+rax*2], r15w
0x18000f3da  jnz     short loc_18000F3D2
0x18000f3dc  lea     eax, ds:2[rax*2]
0x18000f3e3  jmp     short loc_18000F3F1
0x18000f3e5  lea     rsi, qword_1800142D0
0x18000f3ec  mov     eax, 2
0x18000f3f1  mov     [rbp+57h+var_58], eax
0x18000f3f4  lea     rdx, word_1800156BE
0x18000f3fb  lea     rax, [rbp+57h+SRWLock]
0x18000f3ff  mov     [rbp+57h+var_60], rsi
0x18000f403  mov     [rbp+57h+var_70], rax
0x18000f407  add     r8, 8
0x18000f40b  lea     rax, [rbp+57h+var_B0]
0x18000f40f  mov     [rbp+57h+var_54], r15d
0x18000f413  mov     [rbp+57h+var_80], rax
0x18000f417  mov     rcx, rbx
0x18000f41a  lea     rax, [rbp+57h+var_A0]
0x18000f41e  mov     [rbp+57h+var_68], 4
0x18000f426  mov     [rsp+0F0h+var_C8], rax
0x18000f42b  mov     [rsp+0F0h+var_D0], 7
0x18000f433  mov     [rbp+57h+var_78], 8
0x18000f43b  call    _tlgWriteTransfer_EventWriteTransfer
0x18000f440  cmp     [rdi+138h], r15d
0x18000f447  jnz     short loc_18000F480
0x18000f449  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r15; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000f450  lea     rbx, [rdi+120h]
0x18000f457  jz      short loc_18000F47D
0x18000f459  mov     dl, 1
0x18000f45b  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000f460  mov     [rbx], rax
0x18000f463  test    rax, rax
0x18000f466  jz      short loc_18000F480
0x18000f468  mov     rcx, [rax]
0x18000f46b  mov     [rbx+10h], rcx
0x18000f46f  mov     [rax], rbx
0x18000f472  call    cs:__imp_GetCurrentThreadId
0x18000f478  mov     [rbx+18h], eax
0x18000f47b  jmp     short loc_18000F480
0x18000f47d  mov     [rbx], r15
0x18000f480  mov     rcx, [rbp+57h+var_30]
0x18000f484  xor     rcx, rsp; StackCookie
0x18000f487  call    __security_check_cookie
0x18000f48c  lea     r11, [rsp+0F0h+var_20]
0x18000f494  mov     rbx, [r11+38h]
0x18000f498  mov     rsi, [r11+40h]
0x18000f49c  mov     rsp, r11
0x18000f49f  pop     r15
0x18000f4a1  pop     r14
0x18000f4a3  pop     r12
0x18000f4a5  pop     rdi
0x18000f4a6  pop     rbp
0x18000f4a7  retn
```
