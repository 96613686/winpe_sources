# wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_AddAppInfoForUser::StartActivity(void)

- ea: `0x180012a30`
- end: `0x180012ba1`
- name: `?StartActivity@WpcAppInventory_AddAppInfoForUser@AppInventoryLogger@AppInventory@AppLimits@wpc@@QEAAXXZ`
- size: `369`
- prototype: `void __fastcall(wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_AddAppInfoForUser *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000e008`

## callees

- `0x180001d7c`
- `0x1800032a0`
- `0x180007af0`
- `0x180010810`
- `0x180010d90`
- `0x180012a30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012a9d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012a9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012ab6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012b6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012ab6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012b6e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180012a7f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180012a7f`

## pseudocode

```c
void __fastcall wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_AddAppInfoForUser::StartActivity(
        wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_AddAppInfoForUser *this)
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
    tlgWriteTransfer_EventWriteTransfer(v3, byte_18003CE1B, v5 + 8, v6, 4, v11);
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
0x180012a30  mov     [rsp-8+arg_8], rbx
0x180012a35  mov     [rsp-8+arg_10], rdi
0x180012a3a  push    rbp
0x180012a3b  lea     rbp, [rsp-57h]
0x180012a40  sub     rsp, 90h
0x180012a47  mov     rax, cs:__security_cookie
0x180012a4e  xor     rax, rsp
0x180012a51  mov     [rbp+57h+var_10], rax
0x180012a55  mov     rbx, rcx
0x180012a58  lea     rdx, [rbp+57h+SRWLock]
0x180012a5c  call    ?LockExclusive@?$ActivityBase@VWpcBaseLogger@Logging@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180012a61  mov     rdi, [rbx+110h]
0x180012a68  call    ?Provider@WpcBaseLogger@Logging@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Logging::WpcBaseLogger::Provider(void)
0x180012a6d  mov     r8d, [rax]
0x180012a70  cmp     r8d, 4
0x180012a74  jbe     short loc_180012A87
0x180012a76  lea     rdx, [rdi+8]; ActivityId
0x180012a7a  mov     ecx, 3; ControlCode
0x180012a7f  call    cs:__imp_EventActivityIdControl
0x180012a85  jmp     short loc_180012A8E
0x180012a87  xorps   xmm0, xmm0
0x180012a8a  movups  xmmword ptr [rdi+8], xmm0
0x180012a8e  mov     dword ptr [rdi], 1
0x180012a94  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180012a98  test    rcx, rcx
0x180012a9b  jz      short loc_180012AA3
0x180012a9d  call    cs:__imp_ReleaseSRWLockExclusive
0x180012aa3  call    ?Provider@WpcBaseLogger@Logging@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Logging::WpcBaseLogger::Provider(void)
0x180012aa8  mov     rdi, rax
0x180012aab  mov     ecx, [rax]
0x180012aad  cmp     ecx, 4
0x180012ab0  jbe     loc_180012B3B
0x180012ab6  call    cs:__imp_GetCurrentThreadId
0x180012abc  mov     dword ptr [rbp+57h+SRWLock], eax
0x180012abf  mov     [rbp+57h+var_58], 1000000h
0x180012ac7  mov     r8, [rbx+110h]
0x180012ace  cmp     byte ptr [r8+4], 0
0x180012ad3  jz      short loc_180012AF4
0x180012ad5  lea     r9, [r8+18h]
0x180012ad9  cmp     dword ptr [r9], 0
0x180012add  jnz     short loc_180012AF7
0x180012adf  cmp     dword ptr [r9+4], 0
0x180012ae4  jnz     short loc_180012AF7
0x180012ae6  cmp     dword ptr [r9+8], 0
0x180012aeb  jnz     short loc_180012AF7
0x180012aed  cmp     dword ptr [r9+0Ch], 0
0x180012af2  jnz     short loc_180012AF7
0x180012af4  xor     r9d, r9d
0x180012af7  lea     rax, [rbp+57h+SRWLock]
0x180012afb  mov     [rbp+57h+var_20], rax
0x180012aff  mov     [rbp+57h+var_18], 4
0x180012b07  lea     rax, [rbp+57h+var_58]
0x180012b0b  mov     [rbp+57h+var_30], rax
0x180012b0f  mov     [rbp+57h+var_28], 8
0x180012b17  add     r8, 8
0x180012b1b  lea     rax, [rbp+57h+var_50]
0x180012b1f  mov     [rsp+90h+var_68], rax
0x180012b24  mov     [rsp+90h+var_70], 4
0x180012b2c  lea     rdx, byte_18003CE1B
0x180012b33  mov     rcx, rdi
0x180012b36  call    _tlgWriteTransfer_EventWriteTransfer
0x180012b3b  cmp     dword ptr [rbx+138h], 0
0x180012b42  jnz     short loc_180012B80
0x180012b44  add     rbx, 120h
0x180012b4b  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180012b53  jz      short loc_180012B79
0x180012b55  mov     dl, 1
0x180012b57  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180012b5c  mov     [rbx], rax
0x180012b5f  test    rax, rax
0x180012b62  jz      short loc_180012B80
0x180012b64  mov     rcx, [rax]
0x180012b67  mov     [rbx+10h], rcx
0x180012b6b  mov     [rax], rbx
0x180012b6e  call    cs:__imp_GetCurrentThreadId
0x180012b74  mov     [rbx+18h], eax
0x180012b77  jmp     short loc_180012B80
0x180012b79  mov     qword ptr [rbx], 0
0x180012b80  mov     rcx, [rbp+57h+var_10]
0x180012b84  xor     rcx, rsp; StackCookie
0x180012b87  call    __security_check_cookie
0x180012b8c  lea     r11, [rsp+90h+var_s0]
0x180012b94  mov     rbx, [r11+18h]
0x180012b98  mov     rdi, [r11+20h]
0x180012b9c  mov     rsp, r11
0x180012b9f  pop     rbp
0x180012ba0  retn
```
