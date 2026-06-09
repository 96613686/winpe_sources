# MtfPlatformTelemetry::GetSuggestion::StartActivity(void)

- ea: `0x18001b19c`
- end: `0x18001b30d`
- name: `?StartActivity@GetSuggestion@MtfPlatformTelemetry@@QEAAXXZ`
- size: `369`
- prototype: `void __fastcall(MtfPlatformTelemetry::GetSuggestion *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180017a40`

## callees

- `0x18000163c`
- `0x180004d20`
- `0x1800053cc`
- `0x180018d00`
- `0x18001b19c`
- `0x18002bca0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b20b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b20b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001b1ed`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001b1ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b225`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b2da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b225`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b2da`

## pseudocode

```c
void __fastcall MtfPlatformTelemetry::GetSuggestion::StartActivity(MtfPlatformTelemetry::GetSuggestion *this)
{
  __int64 v2; // rdi
  __int64 v3; // rdx
  __int64 v4; // rcx
  _DWORD *v5; // rdi
  __int64 v6; // r8
  char *v7; // rbx
  _QWORD *Local; // rax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-9h] BYREF
  _QWORD v10[9]; // [rsp+38h] [rbp-1h] BYREF

  wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
  v2 = *((_QWORD *)this + 34);
  if ( **((_DWORD **)MtfPlatformTelemetry::Instance() + 1) <= 5u )
    *(_OWORD *)(v2 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  *(_DWORD *)v2 = 1;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v5 = (_DWORD *)*((_QWORD *)MtfPlatformTelemetry::Instance() + 1);
  if ( *v5 > 5u )
  {
    LODWORD(SRWLock) = GetCurrentThreadId();
    v10[0] = 0;
    v6 = *((_QWORD *)this + 34);
    v10[7] = &SRWLock;
    v10[8] = 4;
    v10[5] = v10;
    v10[6] = 8;
    tlgWriteTransfer_EventWriteTransfer(v5, word_180036142, v6 + 8);
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v7 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      LOBYTE(v3) = 1;
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v4,
                          v3);
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
0x18001b19c  mov     [rsp-8+arg_8], rbx
0x18001b1a1  mov     [rsp-8+arg_10], rdi
0x18001b1a6  push    rbp
0x18001b1a7  lea     rbp, [rsp-57h]
0x18001b1ac  sub     rsp, 90h
0x18001b1b3  mov     rax, cs:__security_cookie
0x18001b1ba  xor     rax, rsp
0x18001b1bd  mov     [rbp+57h+var_10], rax
0x18001b1c1  mov     rbx, rcx
0x18001b1c4  lea     rdx, [rbp+57h+SRWLock]
0x18001b1c8  call    ?LockExclusive@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001b1cd  mov     rdi, [rbx+110h]
0x18001b1d4  call    ?Instance@MtfPlatformTelemetry@@KAPEAV1@XZ; MtfPlatformTelemetry::Instance(void)
0x18001b1d9  mov     rdx, [rax+8]
0x18001b1dd  mov     eax, [rdx]
0x18001b1df  cmp     eax, 5
0x18001b1e2  jbe     short loc_18001B1F5
0x18001b1e4  lea     rdx, [rdi+8]; ActivityId
0x18001b1e8  mov     ecx, 3; ControlCode
0x18001b1ed  call    cs:__imp_EventActivityIdControl
0x18001b1f3  jmp     short loc_18001B1FC
0x18001b1f5  xorps   xmm0, xmm0
0x18001b1f8  movups  xmmword ptr [rdi+8], xmm0
0x18001b1fc  mov     dword ptr [rdi], 1
0x18001b202  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001b206  test    rcx, rcx
0x18001b209  jz      short loc_18001B211
0x18001b20b  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b211  call    ?Instance@MtfPlatformTelemetry@@KAPEAV1@XZ; MtfPlatformTelemetry::Instance(void)
0x18001b216  mov     rdi, [rax+8]
0x18001b21a  mov     eax, [rdi]
0x18001b21c  cmp     eax, 5
0x18001b21f  jbe     loc_18001B2A7
0x18001b225  call    cs:__imp_GetCurrentThreadId
0x18001b22b  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001b22e  mov     [rbp+57h+var_58], 0
0x18001b236  mov     r8, [rbx+110h]
0x18001b23d  cmp     byte ptr [r8+4], 0
0x18001b242  jz      short loc_18001B263
0x18001b244  lea     r9, [r8+18h]
0x18001b248  cmp     dword ptr [r9], 0
0x18001b24c  jnz     short loc_18001B266
0x18001b24e  cmp     dword ptr [r9+4], 0
0x18001b253  jnz     short loc_18001B266
0x18001b255  cmp     dword ptr [r9+8], 0
0x18001b25a  jnz     short loc_18001B266
0x18001b25c  cmp     dword ptr [r9+0Ch], 0
0x18001b261  jnz     short loc_18001B266
0x18001b263  xor     r9d, r9d
0x18001b266  lea     rax, [rbp+57h+SRWLock]
0x18001b26a  mov     [rbp+57h+var_20], rax
0x18001b26e  mov     ecx, 4
0x18001b273  mov     [rbp+57h+var_18], rcx
0x18001b277  lea     rax, [rbp+57h+var_58]
0x18001b27b  mov     [rbp+57h+var_30], rax
0x18001b27f  mov     [rbp+57h+var_28], 8
0x18001b287  add     r8, 8
0x18001b28b  lea     rax, [rbp+57h+var_50]
0x18001b28f  mov     [rsp+90h+var_68], rax
0x18001b294  mov     [rsp+90h+var_70], ecx
0x18001b298  lea     rdx, word_180036142
0x18001b29f  mov     rcx, rdi
0x18001b2a2  call    _tlgWriteTransfer_EventWriteTransfer
0x18001b2a7  cmp     dword ptr [rbx+138h], 0
0x18001b2ae  jnz     short loc_18001B2EC
0x18001b2b0  add     rbx, 120h
0x18001b2b7  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001b2bf  jz      short loc_18001B2E5
0x18001b2c1  mov     dl, 1
0x18001b2c3  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18001b2c8  mov     [rbx], rax
0x18001b2cb  test    rax, rax
0x18001b2ce  jz      short loc_18001B2EC
0x18001b2d0  mov     rcx, [rax]
0x18001b2d3  mov     [rbx+10h], rcx
0x18001b2d7  mov     [rax], rbx
0x18001b2da  call    cs:__imp_GetCurrentThreadId
0x18001b2e0  mov     [rbx+18h], eax
0x18001b2e3  jmp     short loc_18001B2EC
0x18001b2e5  mov     qword ptr [rbx], 0
0x18001b2ec  mov     rcx, [rbp+57h+var_10]
0x18001b2f0  xor     rcx, rsp; StackCookie
0x18001b2f3  call    __security_check_cookie
0x18001b2f8  lea     r11, [rsp+90h+var_s0]
0x18001b300  mov     rbx, [r11+18h]
0x18001b304  mov     rdi, [r11+20h]
0x18001b308  mov     rsp, r11
0x18001b30b  pop     rbp
0x18001b30c  retn
```
