# wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_GetKnownAppsForUser::StartActivity(void)

- ea: `0x180012d20`
- end: `0x180012e91`
- name: `?StartActivity@WpcAppInventory_GetKnownAppsForUser@AppInventoryLogger@AppInventory@AppLimits@wpc@@QEAAXXZ`
- size: `369`
- prototype: `void __fastcall(wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_GetKnownAppsForUser *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000e188`

## callees

- `0x180001d7c`
- `0x1800032a0`
- `0x180007af0`
- `0x180010810`
- `0x180010d90`
- `0x180012d20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012d8d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012d8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012da6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012e5e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012da6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012e5e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180012d6f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180012d6f`

## pseudocode

```c
void __fastcall wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_GetKnownAppsForUser::StartActivity(
        wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_GetKnownAppsForUser *this)
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

  wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &SRWLock);
  v2 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)wpc::Logging::WpcBaseLogger::Provider() <= 4u )
    *(_OWORD *)(v2 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  *(_DWORD *)v2 = 1;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v3 = wpc::Logging::WpcBaseLogger::Provider();
  v4 = *(unsigned int *)v3;
  if ( (unsigned int)v4 > 4 )
  {
    LODWORD(SRWLock) = GetCurrentThreadId();
    v10 = 0x1000000;
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
    tlgWriteTransfer_EventWriteTransfer(v3, &unk_18003CDC0, v5 + 8, v6, 4, v11);
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
0x180012d20  mov     [rsp-8+arg_8], rbx
0x180012d25  mov     [rsp-8+arg_10], rdi
0x180012d2a  push    rbp
0x180012d2b  lea     rbp, [rsp-57h]
0x180012d30  sub     rsp, 90h
0x180012d37  mov     rax, cs:__security_cookie
0x180012d3e  xor     rax, rsp
0x180012d41  mov     [rbp+57h+var_10], rax
0x180012d45  mov     rbx, rcx
0x180012d48  lea     rdx, [rbp+57h+SRWLock]
0x180012d4c  call    ?LockExclusive@?$ActivityBase@VWpcBaseLogger@Logging@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180012d51  mov     rdi, [rbx+110h]
0x180012d58  call    ?Provider@WpcBaseLogger@Logging@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Logging::WpcBaseLogger::Provider(void)
0x180012d5d  mov     r8d, [rax]
0x180012d60  cmp     r8d, 4
0x180012d64  jbe     short loc_180012D77
0x180012d66  lea     rdx, [rdi+8]; ActivityId
0x180012d6a  mov     ecx, 3; ControlCode
0x180012d6f  call    cs:__imp_EventActivityIdControl
0x180012d75  jmp     short loc_180012D7E
0x180012d77  xorps   xmm0, xmm0
0x180012d7a  movups  xmmword ptr [rdi+8], xmm0
0x180012d7e  mov     dword ptr [rdi], 1
0x180012d84  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180012d88  test    rcx, rcx
0x180012d8b  jz      short loc_180012D93
0x180012d8d  call    cs:__imp_ReleaseSRWLockExclusive
0x180012d93  call    ?Provider@WpcBaseLogger@Logging@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Logging::WpcBaseLogger::Provider(void)
0x180012d98  mov     rdi, rax
0x180012d9b  mov     ecx, [rax]
0x180012d9d  cmp     ecx, 4
0x180012da0  jbe     loc_180012E2B
0x180012da6  call    cs:__imp_GetCurrentThreadId
0x180012dac  mov     dword ptr [rbp+57h+SRWLock], eax
0x180012daf  mov     [rbp+57h+var_58], 1000000h
0x180012db7  mov     r8, [rbx+110h]
0x180012dbe  cmp     byte ptr [r8+4], 0
0x180012dc3  jz      short loc_180012DE4
0x180012dc5  lea     r9, [r8+18h]
0x180012dc9  cmp     dword ptr [r9], 0
0x180012dcd  jnz     short loc_180012DE7
0x180012dcf  cmp     dword ptr [r9+4], 0
0x180012dd4  jnz     short loc_180012DE7
0x180012dd6  cmp     dword ptr [r9+8], 0
0x180012ddb  jnz     short loc_180012DE7
0x180012ddd  cmp     dword ptr [r9+0Ch], 0
0x180012de2  jnz     short loc_180012DE7
0x180012de4  xor     r9d, r9d
0x180012de7  lea     rax, [rbp+57h+SRWLock]
0x180012deb  mov     [rbp+57h+var_20], rax
0x180012def  mov     [rbp+57h+var_18], 4
0x180012df7  lea     rax, [rbp+57h+var_58]
0x180012dfb  mov     [rbp+57h+var_30], rax
0x180012dff  mov     [rbp+57h+var_28], 8
0x180012e07  add     r8, 8
0x180012e0b  lea     rax, [rbp+57h+var_50]
0x180012e0f  mov     [rsp+90h+var_68], rax
0x180012e14  mov     [rsp+90h+var_70], 4
0x180012e1c  lea     rdx, unk_18003CDC0
0x180012e23  mov     rcx, rdi
0x180012e26  call    _tlgWriteTransfer_EventWriteTransfer
0x180012e2b  cmp     dword ptr [rbx+138h], 0
0x180012e32  jnz     short loc_180012E70
0x180012e34  add     rbx, 120h
0x180012e3b  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180012e43  jz      short loc_180012E69
0x180012e45  mov     dl, 1
0x180012e47  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180012e4c  mov     [rbx], rax
0x180012e4f  test    rax, rax
0x180012e52  jz      short loc_180012E70
0x180012e54  mov     rcx, [rax]
0x180012e57  mov     [rbx+10h], rcx
0x180012e5b  mov     [rax], rbx
0x180012e5e  call    cs:__imp_GetCurrentThreadId
0x180012e64  mov     [rbx+18h], eax
0x180012e67  jmp     short loc_180012E70
0x180012e69  mov     qword ptr [rbx], 0
0x180012e70  mov     rcx, [rbp+57h+var_10]
0x180012e74  xor     rcx, rsp; StackCookie
0x180012e77  call    __security_check_cookie
0x180012e7c  lea     r11, [rsp+90h+var_s0]
0x180012e84  mov     rbx, [r11+18h]
0x180012e88  mov     rdi, [r11+20h]
0x180012e8c  mov     rsp, r11
0x180012e8f  pop     rbp
0x180012e90  retn
```
