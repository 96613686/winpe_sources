# EcoScoreTaskTelemetry::GetEcoScoreActivity::StartActivity(void)

- ea: `0x180006654`
- end: `0x1800067f5`
- name: `?StartActivity@GetEcoScoreActivity@EcoScoreTaskTelemetry@@QEAAXXZ`
- size: `417`
- prototype: `void __fastcall(EcoScoreTaskTelemetry::GetEcoScoreActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800073f0`

## callees

- `0x1800018dc`
- `0x1800046ac`
- `0x180004d4c`
- `0x180005760`
- `0x180006654`
- `0x180007c90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006715`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800067ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006715`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800067ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800066dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800066dc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800066be`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800066be`

## pseudocode

```c
void __fastcall EcoScoreTaskTelemetry::GetEcoScoreActivity::StartActivity(
        EcoScoreTaskTelemetry::GetEcoScoreActivity *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rax
  RTL_SRWLOCK *v4; // rcx
  const struct _tlgProvider_t *v5; // rax
  const struct _tlgProvider_t *v6; // rdi
  __int64 v7; // rcx
  __int64 v8; // rax
  DWORD CurrentThreadId; // eax
  __int64 v10; // r8
  __int64 v11; // r9
  char *v12; // rbx
  _QWORD *Local; // rax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-29h] BYREF
  __int64 v15; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v16[32]; // [rsp+40h] [rbp-19h] BYREF
  __int64 *v17; // [rsp+60h] [rbp+7h]
  __int64 v18; // [rsp+68h] [rbp+Fh]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp+17h]
  __int64 v20; // [rsp+78h] [rbp+1Fh]

  wil::ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &SRWLock);
  v2 = *((_QWORD *)this + 34);
  v3 = EcoScoreTaskTelemetry::Provider();
  if ( *(_DWORD *)v3 > 5u
    && (*((_QWORD *)v3 + 2) & 0x200000000000LL) != 0
    && (*((_QWORD *)v3 + 3) & 0x200000000000LL) == *((_QWORD *)v3 + 3) )
  {
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  }
  else
  {
    *(_OWORD *)(v2 + 8) = 0;
  }
  v4 = SRWLock;
  *(_DWORD *)v2 = 1;
  if ( v4 )
    ReleaseSRWLockExclusive(v4);
  v5 = EcoScoreTaskTelemetry::Provider();
  v6 = v5;
  v7 = *(unsigned int *)v5;
  if ( (unsigned int)v7 > 5 )
  {
    v8 = *((_QWORD *)v5 + 3);
    v7 = *((_QWORD *)v6 + 2);
    if ( (v7 & 0x200000000000LL) != 0 )
    {
      v7 = v8 & 0x200000000000LL;
      if ( (v8 & 0x200000000000LL) == v8 )
      {
        CurrentThreadId = GetCurrentThreadId();
        v10 = *((_QWORD *)this + 34);
        LODWORD(SRWLock) = CurrentThreadId;
        v15 = 0x1000000;
        if ( !*(_BYTE *)(v10 + 4)
          || (v11 = v10 + 24, !*(_DWORD *)(v10 + 24))
          && !*(_DWORD *)(v10 + 28)
          && !*(_DWORD *)(v10 + 32)
          && !*(_DWORD *)(v10 + 36) )
        {
          v11 = 0;
        }
        v18 = 8;
        v20 = 4;
        p_SRWLock = &SRWLock;
        v17 = &v15;
        tlgWriteTransfer_EventWriteTransfer(v6, byte_18000B2EB, v10 + 8, v11, 4, v16);
      }
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v12 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v7,
                          1);
      *(_QWORD *)v12 = Local;
      if ( Local )
      {
        *((_QWORD *)v12 + 2) = *Local;
        *Local = v12;
        *((_DWORD *)v12 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v12 = 0;
    }
  }
}

```

## disassembly

```asm
0x180006654  push    rbp
0x180006656  push    rbx
0x180006657  push    rdi
0x180006658  push    r14
0x18000665a  lea     rbp, [rsp-3Fh]
0x18000665f  sub     rsp, 98h
0x180006666  mov     rax, cs:__security_cookie
0x18000666d  xor     rax, rsp
0x180006670  mov     [rbp+57h+var_30], rax
0x180006674  lea     rdx, [rbp+57h+SRWLock]
0x180006678  mov     rbx, rcx
0x18000667b  call    ?LockExclusive@?$ActivityBase@VEcoScoreTaskTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180006680  mov     rdi, [rbx+110h]
0x180006687  call    ?Provider@EcoScoreTaskTelemetry@@SAPEBU_tlgProvider_t@@XZ; EcoScoreTaskTelemetry::Provider(void)
0x18000668c  mov     r14, 200000000000h
0x180006696  mov     edx, [rax]
0x180006698  cmp     edx, 5
0x18000669b  jbe     short loc_1800066C6
0x18000669d  mov     rcx, [rax+18h]
0x1800066a1  mov     rax, [rax+10h]
0x1800066a5  test    r14, rax
0x1800066a8  jz      short loc_1800066C6
0x1800066aa  mov     rax, rcx
0x1800066ad  and     rax, r14
0x1800066b0  cmp     rax, rcx
0x1800066b3  jnz     short loc_1800066C6
0x1800066b5  lea     rdx, [rdi+8]; ActivityId
0x1800066b9  mov     ecx, 3; ControlCode
0x1800066be  call    cs:__imp_EventActivityIdControl
0x1800066c4  jmp     short loc_1800066CD
0x1800066c6  xorps   xmm0, xmm0
0x1800066c9  movups  xmmword ptr [rdi+8], xmm0
0x1800066cd  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800066d1  mov     dword ptr [rdi], 1
0x1800066d7  test    rcx, rcx
0x1800066da  jz      short loc_1800066E2
0x1800066dc  call    cs:__imp_ReleaseSRWLockExclusive
0x1800066e2  call    ?Provider@EcoScoreTaskTelemetry@@SAPEBU_tlgProvider_t@@XZ; EcoScoreTaskTelemetry::Provider(void)
0x1800066e7  mov     rdi, rax
0x1800066ea  mov     ecx, [rax]
0x1800066ec  cmp     ecx, 5
0x1800066ef  jbe     loc_180006797
0x1800066f5  mov     rax, [rax+18h]
0x1800066f9  mov     rcx, [rdi+10h]
0x1800066fd  test    r14, rcx
0x180006700  jz      loc_180006797
0x180006706  mov     rcx, rax
0x180006709  and     rcx, r14
0x18000670c  cmp     rcx, rax
0x18000670f  jnz     loc_180006797
0x180006715  call    cs:__imp_GetCurrentThreadId
0x18000671b  mov     r8, [rbx+110h]
0x180006722  mov     dword ptr [rbp+57h+SRWLock], eax
0x180006725  mov     [rbp+57h+var_78], 1000000h
0x18000672d  cmp     byte ptr [r8+4], 0
0x180006732  jz      short loc_180006753
0x180006734  lea     r9, [r8+18h]
0x180006738  cmp     dword ptr [r9], 0
0x18000673c  jnz     short loc_180006756
0x18000673e  cmp     dword ptr [r9+4], 0
0x180006743  jnz     short loc_180006756
0x180006745  cmp     dword ptr [r9+8], 0
0x18000674a  jnz     short loc_180006756
0x18000674c  cmp     dword ptr [r9+0Ch], 0
0x180006751  jnz     short loc_180006756
0x180006753  xor     r9d, r9d
0x180006756  mov     ecx, 4
0x18000675b  mov     [rbp+57h+var_48], 8
0x180006763  lea     rax, [rbp+57h+SRWLock]
0x180006767  mov     [rbp+57h+var_38], rcx
0x18000676b  mov     [rbp+57h+var_40], rax
0x18000676f  lea     rdx, byte_18000B2EB
0x180006776  lea     rax, [rbp+57h+var_78]
0x18000677a  add     r8, 8
0x18000677e  mov     [rbp+57h+var_50], rax
0x180006782  lea     rax, [rbp+57h+var_70]
0x180006786  mov     [rsp+0B0h+var_88], rax
0x18000678b  mov     [rsp+0B0h+var_90], ecx
0x18000678f  mov     rcx, rdi
0x180006792  call    _tlgWriteTransfer_EventWriteTransfer
0x180006797  cmp     dword ptr [rbx+138h], 0
0x18000679e  jnz     short loc_1800067DC
0x1800067a0  add     rbx, 120h
0x1800067a7  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800067af  jz      short loc_1800067D5
0x1800067b1  mov     dl, 1
0x1800067b3  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800067b8  mov     [rbx], rax
0x1800067bb  test    rax, rax
0x1800067be  jz      short loc_1800067DC
0x1800067c0  mov     rcx, [rax]
0x1800067c3  mov     [rbx+10h], rcx
0x1800067c7  mov     [rax], rbx
0x1800067ca  call    cs:__imp_GetCurrentThreadId
0x1800067d0  mov     [rbx+18h], eax
0x1800067d3  jmp     short loc_1800067DC
0x1800067d5  mov     qword ptr [rbx], 0
0x1800067dc  mov     rcx, [rbp+57h+var_30]
0x1800067e0  xor     rcx, rsp; StackCookie
0x1800067e3  call    __security_check_cookie
0x1800067e8  add     rsp, 98h
0x1800067ef  pop     r14
0x1800067f1  pop     rdi
0x1800067f2  pop     rbx
0x1800067f3  pop     rbp
0x1800067f4  retn
```
