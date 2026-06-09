# wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_GetDisplayNameForUserApp::StartActivity(void)

- ea: `0x180012ba8`
- end: `0x180012d19`
- name: `?StartActivity@WpcAppInventory_GetDisplayNameForUserApp@AppInventoryLogger@AppInventory@AppLimits@wpc@@QEAAXXZ`
- size: `369`
- prototype: `void __fastcall(wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_GetDisplayNameForUserApp *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000e0c8`

## callees

- `0x180001d7c`
- `0x1800032a0`
- `0x180007af0`
- `0x180010810`
- `0x180010d90`
- `0x180012ba8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012c15`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012c15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012c2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012ce6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012c2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012ce6`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180012bf7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180012bf7`

## pseudocode

```c
void __fastcall wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_GetDisplayNameForUserApp::StartActivity(
        wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_GetDisplayNameForUserApp *this)
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
    tlgWriteTransfer_EventWriteTransfer(v3, &unk_18003CB08, v5 + 8, v6, 4, v11);
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
0x180012ba8  mov     [rsp-8+arg_8], rbx
0x180012bad  mov     [rsp-8+arg_10], rdi
0x180012bb2  push    rbp
0x180012bb3  lea     rbp, [rsp-57h]
0x180012bb8  sub     rsp, 90h
0x180012bbf  mov     rax, cs:__security_cookie
0x180012bc6  xor     rax, rsp
0x180012bc9  mov     [rbp+57h+var_10], rax
0x180012bcd  mov     rbx, rcx
0x180012bd0  lea     rdx, [rbp+57h+SRWLock]
0x180012bd4  call    ?LockExclusive@?$ActivityBase@VWpcBaseLogger@Logging@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180012bd9  mov     rdi, [rbx+110h]
0x180012be0  call    ?Provider@WpcBaseLogger@Logging@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Logging::WpcBaseLogger::Provider(void)
0x180012be5  mov     r8d, [rax]
0x180012be8  cmp     r8d, 4
0x180012bec  jbe     short loc_180012BFF
0x180012bee  lea     rdx, [rdi+8]; ActivityId
0x180012bf2  mov     ecx, 3; ControlCode
0x180012bf7  call    cs:__imp_EventActivityIdControl
0x180012bfd  jmp     short loc_180012C06
0x180012bff  xorps   xmm0, xmm0
0x180012c02  movups  xmmword ptr [rdi+8], xmm0
0x180012c06  mov     dword ptr [rdi], 1
0x180012c0c  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180012c10  test    rcx, rcx
0x180012c13  jz      short loc_180012C1B
0x180012c15  call    cs:__imp_ReleaseSRWLockExclusive
0x180012c1b  call    ?Provider@WpcBaseLogger@Logging@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Logging::WpcBaseLogger::Provider(void)
0x180012c20  mov     rdi, rax
0x180012c23  mov     ecx, [rax]
0x180012c25  cmp     ecx, 4
0x180012c28  jbe     loc_180012CB3
0x180012c2e  call    cs:__imp_GetCurrentThreadId
0x180012c34  mov     dword ptr [rbp+57h+SRWLock], eax
0x180012c37  mov     [rbp+57h+var_58], 1000000h
0x180012c3f  mov     r8, [rbx+110h]
0x180012c46  cmp     byte ptr [r8+4], 0
0x180012c4b  jz      short loc_180012C6C
0x180012c4d  lea     r9, [r8+18h]
0x180012c51  cmp     dword ptr [r9], 0
0x180012c55  jnz     short loc_180012C6F
0x180012c57  cmp     dword ptr [r9+4], 0
0x180012c5c  jnz     short loc_180012C6F
0x180012c5e  cmp     dword ptr [r9+8], 0
0x180012c63  jnz     short loc_180012C6F
0x180012c65  cmp     dword ptr [r9+0Ch], 0
0x180012c6a  jnz     short loc_180012C6F
0x180012c6c  xor     r9d, r9d
0x180012c6f  lea     rax, [rbp+57h+SRWLock]
0x180012c73  mov     [rbp+57h+var_20], rax
0x180012c77  mov     [rbp+57h+var_18], 4
0x180012c7f  lea     rax, [rbp+57h+var_58]
0x180012c83  mov     [rbp+57h+var_30], rax
0x180012c87  mov     [rbp+57h+var_28], 8
0x180012c8f  add     r8, 8
0x180012c93  lea     rax, [rbp+57h+var_50]
0x180012c97  mov     [rsp+90h+var_68], rax
0x180012c9c  mov     [rsp+90h+var_70], 4
0x180012ca4  lea     rdx, unk_18003CB08
0x180012cab  mov     rcx, rdi
0x180012cae  call    _tlgWriteTransfer_EventWriteTransfer
0x180012cb3  cmp     dword ptr [rbx+138h], 0
0x180012cba  jnz     short loc_180012CF8
0x180012cbc  add     rbx, 120h
0x180012cc3  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180012ccb  jz      short loc_180012CF1
0x180012ccd  mov     dl, 1
0x180012ccf  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180012cd4  mov     [rbx], rax
0x180012cd7  test    rax, rax
0x180012cda  jz      short loc_180012CF8
0x180012cdc  mov     rcx, [rax]
0x180012cdf  mov     [rbx+10h], rcx
0x180012ce3  mov     [rax], rbx
0x180012ce6  call    cs:__imp_GetCurrentThreadId
0x180012cec  mov     [rbx+18h], eax
0x180012cef  jmp     short loc_180012CF8
0x180012cf1  mov     qword ptr [rbx], 0
0x180012cf8  mov     rcx, [rbp+57h+var_10]
0x180012cfc  xor     rcx, rsp; StackCookie
0x180012cff  call    __security_check_cookie
0x180012d04  lea     r11, [rsp+90h+var_s0]
0x180012d0c  mov     rbx, [r11+18h]
0x180012d10  mov     rdi, [r11+20h]
0x180012d14  mov     rsp, r11
0x180012d17  pop     rbp
0x180012d18  retn
```
