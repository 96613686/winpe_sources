# wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser::StartActivity(void)

- ea: `0x180012e98`
- end: `0x180013009`
- name: `?StartActivity@WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser@AppInventoryLogger@AppInventory@AppLimits@wpc@@QEAAXXZ`
- size: `369`
- prototype: `void __fastcall(wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000e248`

## callees

- `0x180001d7c`
- `0x1800032a0`
- `0x180007af0`
- `0x180010810`
- `0x180010d90`
- `0x180012e98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012f05`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012f05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012f1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012fd6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012f1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012fd6`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180012ee7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180012ee7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser::StartActivity(
        wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser *this)
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
    tlgWriteTransfer_EventWriteTransfer(v3, byte_18003CD55, v5 + 8, v6, 4, v11);
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
0x180012e98  mov     [rsp-8+arg_8], rbx
0x180012e9d  mov     [rsp-8+arg_10], rdi
0x180012ea2  push    rbp
0x180012ea3  lea     rbp, [rsp-57h]
0x180012ea8  sub     rsp, 90h
0x180012eaf  mov     rax, cs:__security_cookie
0x180012eb6  xor     rax, rsp
0x180012eb9  mov     [rbp+57h+var_10], rax
0x180012ebd  mov     rbx, rcx
0x180012ec0  lea     rdx, [rbp+57h+SRWLock]
0x180012ec4  call    ?LockExclusive@?$ActivityBase@VWpcBaseLogger@Logging@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180012ec9  mov     rdi, [rbx+110h]
0x180012ed0  call    ?Provider@WpcBaseLogger@Logging@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Logging::WpcBaseLogger::Provider(void)
0x180012ed5  mov     r8d, [rax]
0x180012ed8  cmp     r8d, 4
0x180012edc  jbe     short loc_180012EEF
0x180012ede  lea     rdx, [rdi+8]; ActivityId
0x180012ee2  mov     ecx, 3; ControlCode
0x180012ee7  call    cs:__imp_EventActivityIdControl
0x180012eed  jmp     short loc_180012EF6
0x180012eef  xorps   xmm0, xmm0
0x180012ef2  movups  xmmword ptr [rdi+8], xmm0
0x180012ef6  mov     dword ptr [rdi], 1
0x180012efc  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180012f00  test    rcx, rcx
0x180012f03  jz      short loc_180012F0B
0x180012f05  call    cs:__imp_ReleaseSRWLockExclusive
0x180012f0b  call    ?Provider@WpcBaseLogger@Logging@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Logging::WpcBaseLogger::Provider(void)
0x180012f10  mov     rdi, rax
0x180012f13  mov     ecx, [rax]
0x180012f15  cmp     ecx, 4
0x180012f18  jbe     loc_180012FA3
0x180012f1e  call    cs:__imp_GetCurrentThreadId
0x180012f24  mov     dword ptr [rbp+57h+SRWLock], eax
0x180012f27  mov     [rbp+57h+var_58], 1000000h
0x180012f2f  mov     r8, [rbx+110h]
0x180012f36  cmp     byte ptr [r8+4], 0
0x180012f3b  jz      short loc_180012F5C
0x180012f3d  lea     r9, [r8+18h]
0x180012f41  cmp     dword ptr [r9], 0
0x180012f45  jnz     short loc_180012F5F
0x180012f47  cmp     dword ptr [r9+4], 0
0x180012f4c  jnz     short loc_180012F5F
0x180012f4e  cmp     dword ptr [r9+8], 0
0x180012f53  jnz     short loc_180012F5F
0x180012f55  cmp     dword ptr [r9+0Ch], 0
0x180012f5a  jnz     short loc_180012F5F
0x180012f5c  xor     r9d, r9d
0x180012f5f  lea     rax, [rbp+57h+SRWLock]
0x180012f63  mov     [rbp+57h+var_20], rax
0x180012f67  mov     [rbp+57h+var_18], 4
0x180012f6f  lea     rax, [rbp+57h+var_58]
0x180012f73  mov     [rbp+57h+var_30], rax
0x180012f77  mov     [rbp+57h+var_28], 8
0x180012f7f  add     r8, 8
0x180012f83  lea     rax, [rbp+57h+var_50]
0x180012f87  mov     [rsp+90h+var_68], rax
0x180012f8c  mov     [rsp+90h+var_70], 4
0x180012f94  lea     rdx, byte_18003CD55
0x180012f9b  mov     rcx, rdi
0x180012f9e  call    _tlgWriteTransfer_EventWriteTransfer
0x180012fa3  cmp     dword ptr [rbx+138h], 0
0x180012faa  jnz     short loc_180012FE8
0x180012fac  add     rbx, 120h
0x180012fb3  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180012fbb  jz      short loc_180012FE1
0x180012fbd  mov     dl, 1
0x180012fbf  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180012fc4  mov     [rbx], rax
0x180012fc7  test    rax, rax
0x180012fca  jz      short loc_180012FE8
0x180012fcc  mov     rcx, [rax]
0x180012fcf  mov     [rbx+10h], rcx
0x180012fd3  mov     [rax], rbx
0x180012fd6  call    cs:__imp_GetCurrentThreadId
0x180012fdc  mov     [rbx+18h], eax
0x180012fdf  jmp     short loc_180012FE8
0x180012fe1  mov     qword ptr [rbx], 0
0x180012fe8  mov     rcx, [rbp+57h+var_10]
0x180012fec  xor     rcx, rsp; StackCookie
0x180012fef  call    __security_check_cookie
0x180012ff4  lea     r11, [rsp+90h+var_s0]
0x180012ffc  mov     rbx, [r11+18h]
0x180013000  mov     rdi, [r11+20h]
0x180013004  mov     rsp, r11
0x180013007  pop     rbp
0x180013008  retn
```
