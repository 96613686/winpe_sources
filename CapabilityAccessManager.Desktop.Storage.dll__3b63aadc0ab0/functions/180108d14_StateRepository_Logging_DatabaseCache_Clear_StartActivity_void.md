# StateRepository::Logging::DatabaseCache::Clear::StartActivity(void)

- ea: `0x180108d14`
- end: `0x180108e83`
- name: `?StartActivity@Clear@DatabaseCache@Logging@StateRepository@@QEAAXXZ`
- size: `367`
- prototype: `void __fastcall(StateRepository::Logging::DatabaseCache::Clear *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180108030`

## callees

- `0x18000163c`
- `0x180003060`
- `0x1800e8310`
- `0x1800f9e44`
- `0x1800fb134`
- `0x180108d14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180108d81`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180108d81`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180108d63`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180108d63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180108d9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180108e50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180108d9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180108e50`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall StateRepository::Logging::DatabaseCache::Clear::StartActivity(
        StateRepository::Logging::DatabaseCache::Clear *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rdi
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  char *v7; // rbx
  _QWORD *Local; // rax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-9h] BYREF
  __int64 v10; // [rsp+38h] [rbp-1h] BYREF
  _BYTE v11[32]; // [rsp+40h] [rbp+7h] BYREF
  __int64 *v12; // [rsp+60h] [rbp+27h]
  __int64 v13; // [rsp+68h] [rbp+2Fh]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp+37h]
  __int64 v15; // [rsp+78h] [rbp+3Fh]

  wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &SRWLock);
  v2 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)StateRepository::Tracing::Service::Provider() <= 5u )
    *(_OWORD *)(v2 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  *(_DWORD *)v2 = 1;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v3 = StateRepository::Tracing::Service::Provider();
  v4 = *(unsigned int *)v3;
  if ( (unsigned int)v4 > 5 )
  {
    LODWORD(SRWLock) = GetCurrentThreadId();
    v10 = 0;
    v5 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v5 + 4)
      || (v6 = v5 + 24, !*(_DWORD *)(v5 + 24))
      && !*(_DWORD *)(v5 + 28)
      && !*(_DWORD *)(v5 + 32)
      && !*(_DWORD *)(v5 + 36) )
    {
      v6 = 0;
    }
    p_SRWLock = &SRWLock;
    v15 = 4;
    v12 = &v10;
    v13 = 8;
    tlgWriteTransfer_EventWriteTransfer(v3, byte_18012A5B1, v5 + 8, v6, 4, v11);
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v7 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v4,
                          1);
      *(_QWORD *)v7 = Local;
      if ( Local )
      {
        *((_QWORD *)v7 + 2) = *Local;
        *Local = v7;
        *((_DWORD *)v7 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v7 = 0;
    }
  }
}

```

## disassembly

```asm
0x180108d14  mov     [rsp-8+arg_8], rbx
0x180108d19  mov     [rsp-8+arg_10], rdi
0x180108d1e  push    rbp
0x180108d1f  lea     rbp, [rsp-57h]
0x180108d24  sub     rsp, 90h
0x180108d2b  mov     rax, cs:__security_cookie
0x180108d32  xor     rax, rsp
0x180108d35  mov     [rbp+57h+var_10], rax
0x180108d39  mov     rbx, rcx
0x180108d3c  lea     rdx, [rbp+57h+SRWLock]
0x180108d40  call    ?LockExclusive@?$ActivityBase@VService@Tracing@StateRepository@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180108d45  mov     rdi, [rbx+110h]
0x180108d4c  call    ?Provider@Service@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Service::Provider(void)
0x180108d51  mov     r8d, [rax]
0x180108d54  cmp     r8d, 5
0x180108d58  jbe     short loc_180108D6B
0x180108d5a  lea     rdx, [rdi+8]; ActivityId
0x180108d5e  mov     ecx, 3; ControlCode
0x180108d63  call    cs:__imp_EventActivityIdControl
0x180108d69  jmp     short loc_180108D72
0x180108d6b  xorps   xmm0, xmm0
0x180108d6e  movups  xmmword ptr [rdi+8], xmm0
0x180108d72  mov     dword ptr [rdi], 1
0x180108d78  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180108d7c  test    rcx, rcx
0x180108d7f  jz      short loc_180108D88
0x180108d81  call    cs:__imp_ReleaseSRWLockExclusive
0x180108d87  nop
0x180108d88  call    ?Provider@Service@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Service::Provider(void)
0x180108d8d  mov     rdi, rax
0x180108d90  mov     ecx, [rax]
0x180108d92  cmp     ecx, 5
0x180108d95  jbe     loc_180108E1D
0x180108d9b  call    cs:__imp_GetCurrentThreadId
0x180108da1  mov     dword ptr [rbp+57h+SRWLock], eax
0x180108da4  mov     [rbp+57h+var_58], 0
0x180108dac  mov     r8, [rbx+110h]
0x180108db3  cmp     byte ptr [r8+4], 0
0x180108db8  jz      short loc_180108DD9
0x180108dba  lea     r9, [r8+18h]
0x180108dbe  cmp     dword ptr [r9], 0
0x180108dc2  jnz     short loc_180108DDC
0x180108dc4  cmp     dword ptr [r9+4], 0
0x180108dc9  jnz     short loc_180108DDC
0x180108dcb  cmp     dword ptr [r9+8], 0
0x180108dd0  jnz     short loc_180108DDC
0x180108dd2  cmp     dword ptr [r9+0Ch], 0
0x180108dd7  jnz     short loc_180108DDC
0x180108dd9  xor     r9d, r9d
0x180108ddc  lea     rax, [rbp+57h+SRWLock]
0x180108de0  mov     [rbp+57h+var_20], rax
0x180108de4  mov     ecx, 4
0x180108de9  mov     [rbp+57h+var_18], rcx
0x180108ded  lea     rax, [rbp+57h+var_58]
0x180108df1  mov     [rbp+57h+var_30], rax
0x180108df5  mov     [rbp+57h+var_28], 8
0x180108dfd  add     r8, 8
0x180108e01  lea     rax, [rbp+57h+var_50]
0x180108e05  mov     [rsp+90h+var_68], rax
0x180108e0a  mov     [rsp+90h+var_70], ecx
0x180108e0e  lea     rdx, byte_18012A5B1
0x180108e15  mov     rcx, rdi
0x180108e18  call    _tlgWriteTransfer_EventWriteTransfer
0x180108e1d  cmp     dword ptr [rbx+138h], 0
0x180108e24  jnz     short loc_180108E62
0x180108e26  add     rbx, 120h
0x180108e2d  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180108e35  jz      short loc_180108E5B
0x180108e37  mov     dl, 1
0x180108e39  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180108e3e  mov     [rbx], rax
0x180108e41  test    rax, rax
0x180108e44  jz      short loc_180108E62
0x180108e46  mov     rcx, [rax]
0x180108e49  mov     [rbx+10h], rcx
0x180108e4d  mov     [rax], rbx
0x180108e50  call    cs:__imp_GetCurrentThreadId
0x180108e56  mov     [rbx+18h], eax
0x180108e59  jmp     short loc_180108E62
0x180108e5b  mov     qword ptr [rbx], 0
0x180108e62  mov     rcx, [rbp+57h+var_10]
0x180108e66  xor     rcx, rsp; StackCookie
0x180108e69  call    __security_check_cookie
0x180108e6e  lea     r11, [rsp+90h+var_s0]
0x180108e76  mov     rbx, [r11+18h]
0x180108e7a  mov     rdi, [r11+20h]
0x180108e7e  mov     rsp, r11
0x180108e81  pop     rbp
0x180108e82  retn
```
