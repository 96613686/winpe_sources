# PowerGridForecastTaskTelemetry::GeneratePowerGridForecastActivity::StartActivity(void)

- ea: `0x18002e574`
- end: `0x18002e715`
- name: `?StartActivity@GeneratePowerGridForecastActivity@PowerGridForecastTaskTelemetry@@QEAAXXZ`
- size: `417`
- prototype: `void __fastcall(PowerGridForecastTaskTelemetry::GeneratePowerGridForecastActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18002fa90`

## callees

- `0x180001c7c`
- `0x18002ab00`
- `0x18002b340`
- `0x18002befc`
- `0x18002e574`
- `0x1800350e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e635`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e6ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e635`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e6ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002e5fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002e5fc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002e5de`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002e5de`

## pseudocode

```c
void __fastcall PowerGridForecastTaskTelemetry::GeneratePowerGridForecastActivity::StartActivity(
        PowerGridForecastTaskTelemetry::GeneratePowerGridForecastActivity *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rax
  const struct _tlgProvider_t *v4; // rax
  const struct _tlgProvider_t *v5; // rdi
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // r8
  __int64 v9; // r9
  char *v10; // rbx
  _QWORD *Local; // rax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-29h] BYREF
  __int64 v13; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v14[32]; // [rsp+40h] [rbp-19h] BYREF
  __int64 *v15; // [rsp+60h] [rbp+7h]
  __int64 v16; // [rsp+68h] [rbp+Fh]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp+17h]
  __int64 v18; // [rsp+78h] [rbp+1Fh]

  wil::ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &SRWLock);
  v2 = *((_QWORD *)this + 34);
  v3 = PowerGridForecastTaskTelemetry::Provider();
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
  *(_DWORD *)v2 = 1;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v4 = PowerGridForecastTaskTelemetry::Provider();
  v5 = v4;
  v6 = *(unsigned int *)v4;
  if ( (unsigned int)v6 > 5 )
  {
    v7 = *((_QWORD *)v4 + 3);
    v6 = *((_QWORD *)v5 + 2);
    if ( (v6 & 0x200000000000LL) != 0 )
    {
      v6 = v7 & 0x200000000000LL;
      if ( (v7 & 0x200000000000LL) == v7 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v13 = 0x1000000;
        v8 = *((_QWORD *)this + 34);
        if ( !*(_BYTE *)(v8 + 4)
          || (v9 = v8 + 24, !*(_DWORD *)(v8 + 24))
          && !*(_DWORD *)(v8 + 28)
          && !*(_DWORD *)(v8 + 32)
          && !*(_DWORD *)(v8 + 36) )
        {
          v9 = 0;
        }
        p_SRWLock = &SRWLock;
        v18 = 4;
        v15 = &v13;
        v16 = 8;
        tlgWriteTransfer_EventWriteTransfer(v5, &dword_18003E87C, v8 + 8, v9, 4, v14);
      }
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v10 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v6,
                          1);
      *(_QWORD *)v10 = Local;
      if ( Local )
      {
        *((_QWORD *)v10 + 2) = *Local;
        *Local = v10;
        *((_DWORD *)v10 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v10 = 0;
    }
  }
}

```

## disassembly

```asm
0x18002e574  push    rbp
0x18002e576  push    rbx
0x18002e577  push    rdi
0x18002e578  push    r14
0x18002e57a  lea     rbp, [rsp-3Fh]
0x18002e57f  sub     rsp, 98h
0x18002e586  mov     rax, cs:__security_cookie
0x18002e58d  xor     rax, rsp
0x18002e590  mov     [rbp+57h+var_30], rax
0x18002e594  mov     rbx, rcx
0x18002e597  lea     rdx, [rbp+57h+SRWLock]
0x18002e59b  call    ?LockExclusive@?$ActivityBase@VPowerGridForecastTaskTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002e5a0  mov     rdi, [rbx+110h]
0x18002e5a7  call    ?Provider@PowerGridForecastTaskTelemetry@@SAPEBU_tlgProvider_t@@XZ; PowerGridForecastTaskTelemetry::Provider(void)
0x18002e5ac  mov     edx, [rax]
0x18002e5ae  mov     r14, 200000000000h
0x18002e5b8  cmp     edx, 5
0x18002e5bb  jbe     short loc_18002E5E6
0x18002e5bd  mov     rcx, [rax+18h]
0x18002e5c1  mov     rax, [rax+10h]
0x18002e5c5  test    r14, rax
0x18002e5c8  jz      short loc_18002E5E6
0x18002e5ca  mov     rax, rcx
0x18002e5cd  and     rax, r14
0x18002e5d0  cmp     rax, rcx
0x18002e5d3  jnz     short loc_18002E5E6
0x18002e5d5  lea     rdx, [rdi+8]; ActivityId
0x18002e5d9  mov     ecx, 3; ControlCode
0x18002e5de  call    cs:__imp_EventActivityIdControl
0x18002e5e4  jmp     short loc_18002E5ED
0x18002e5e6  xorps   xmm0, xmm0
0x18002e5e9  movups  xmmword ptr [rdi+8], xmm0
0x18002e5ed  mov     dword ptr [rdi], 1
0x18002e5f3  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18002e5f7  test    rcx, rcx
0x18002e5fa  jz      short loc_18002E602
0x18002e5fc  call    cs:__imp_ReleaseSRWLockExclusive
0x18002e602  call    ?Provider@PowerGridForecastTaskTelemetry@@SAPEBU_tlgProvider_t@@XZ; PowerGridForecastTaskTelemetry::Provider(void)
0x18002e607  mov     rdi, rax
0x18002e60a  mov     ecx, [rax]
0x18002e60c  cmp     ecx, 5
0x18002e60f  jbe     loc_18002E6B7
0x18002e615  mov     rax, [rax+18h]
0x18002e619  mov     rcx, [rdi+10h]
0x18002e61d  test    r14, rcx
0x18002e620  jz      loc_18002E6B7
0x18002e626  mov     rcx, rax
0x18002e629  and     rcx, r14
0x18002e62c  cmp     rcx, rax
0x18002e62f  jnz     loc_18002E6B7
0x18002e635  call    cs:__imp_GetCurrentThreadId
0x18002e63b  mov     dword ptr [rbp+57h+SRWLock], eax
0x18002e63e  mov     [rbp+57h+var_78], 1000000h
0x18002e646  mov     r8, [rbx+110h]
0x18002e64d  cmp     byte ptr [r8+4], 0
0x18002e652  jz      short loc_18002E673
0x18002e654  lea     r9, [r8+18h]
0x18002e658  cmp     dword ptr [r9], 0
0x18002e65c  jnz     short loc_18002E676
0x18002e65e  cmp     dword ptr [r9+4], 0
0x18002e663  jnz     short loc_18002E676
0x18002e665  cmp     dword ptr [r9+8], 0
0x18002e66a  jnz     short loc_18002E676
0x18002e66c  cmp     dword ptr [r9+0Ch], 0
0x18002e671  jnz     short loc_18002E676
0x18002e673  xor     r9d, r9d
0x18002e676  lea     rax, [rbp+57h+SRWLock]
0x18002e67a  mov     [rbp+57h+var_40], rax
0x18002e67e  mov     ecx, 4
0x18002e683  mov     [rbp+57h+var_38], rcx
0x18002e687  lea     rax, [rbp+57h+var_78]
0x18002e68b  mov     [rbp+57h+var_50], rax
0x18002e68f  mov     [rbp+57h+var_48], 8
0x18002e697  add     r8, 8
0x18002e69b  lea     rax, [rbp+57h+var_70]
0x18002e69f  mov     [rsp+0B0h+var_88], rax
0x18002e6a4  mov     [rsp+0B0h+var_90], ecx
0x18002e6a8  lea     rdx, dword_18003E87C
0x18002e6af  mov     rcx, rdi
0x18002e6b2  call    _tlgWriteTransfer_EventWriteTransfer
0x18002e6b7  cmp     dword ptr [rbx+138h], 0
0x18002e6be  jnz     short loc_18002E6FC
0x18002e6c0  add     rbx, 120h
0x18002e6c7  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18002e6cf  jz      short loc_18002E6F5
0x18002e6d1  mov     dl, 1
0x18002e6d3  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18002e6d8  mov     [rbx], rax
0x18002e6db  test    rax, rax
0x18002e6de  jz      short loc_18002E6FC
0x18002e6e0  mov     rcx, [rax]
0x18002e6e3  mov     [rbx+10h], rcx
0x18002e6e7  mov     [rax], rbx
0x18002e6ea  call    cs:__imp_GetCurrentThreadId
0x18002e6f0  mov     [rbx+18h], eax
0x18002e6f3  jmp     short loc_18002E6FC
0x18002e6f5  mov     qword ptr [rbx], 0
0x18002e6fc  mov     rcx, [rbp+57h+var_30]
0x18002e700  xor     rcx, rsp; StackCookie
0x18002e703  call    __security_check_cookie
0x18002e708  add     rsp, 98h
0x18002e70f  pop     r14
0x18002e711  pop     rdi
0x18002e712  pop     rbx
0x18002e713  pop     rbp
0x18002e714  retn
```
