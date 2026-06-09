# MtfPlatformTelemetry::SuggestionReady::StartActivity(void)

- ea: `0x18001b48c`
- end: `0x18001b5fd`
- name: `?StartActivity@SuggestionReady@MtfPlatformTelemetry@@QEAAXXZ`
- size: `369`
- prototype: `void __fastcall(MtfPlatformTelemetry::SuggestionReady *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180018f80`

## callees

- `0x18000163c`
- `0x180004d20`
- `0x1800053cc`
- `0x180018d00`
- `0x18001b48c`
- `0x18002bca0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b4fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b4fb`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001b4dd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001b4dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b515`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b5ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b515`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b5ca`

## pseudocode

```c
void __fastcall MtfPlatformTelemetry::SuggestionReady::StartActivity(MtfPlatformTelemetry::SuggestionReady *this)
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
    tlgWriteTransfer_EventWriteTransfer(v5, qword_180036AE8, v6 + 8);
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
0x18001b48c  mov     [rsp-8+arg_8], rbx
0x18001b491  mov     [rsp-8+arg_10], rdi
0x18001b496  push    rbp
0x18001b497  lea     rbp, [rsp-57h]
0x18001b49c  sub     rsp, 90h
0x18001b4a3  mov     rax, cs:__security_cookie
0x18001b4aa  xor     rax, rsp
0x18001b4ad  mov     [rbp+57h+var_10], rax
0x18001b4b1  mov     rbx, rcx
0x18001b4b4  lea     rdx, [rbp+57h+SRWLock]
0x18001b4b8  call    ?LockExclusive@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001b4bd  mov     rdi, [rbx+110h]
0x18001b4c4  call    ?Instance@MtfPlatformTelemetry@@KAPEAV1@XZ; MtfPlatformTelemetry::Instance(void)
0x18001b4c9  mov     rdx, [rax+8]
0x18001b4cd  mov     eax, [rdx]
0x18001b4cf  cmp     eax, 5
0x18001b4d2  jbe     short loc_18001B4E5
0x18001b4d4  lea     rdx, [rdi+8]; ActivityId
0x18001b4d8  mov     ecx, 3; ControlCode
0x18001b4dd  call    cs:__imp_EventActivityIdControl
0x18001b4e3  jmp     short loc_18001B4EC
0x18001b4e5  xorps   xmm0, xmm0
0x18001b4e8  movups  xmmword ptr [rdi+8], xmm0
0x18001b4ec  mov     dword ptr [rdi], 1
0x18001b4f2  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001b4f6  test    rcx, rcx
0x18001b4f9  jz      short loc_18001B501
0x18001b4fb  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b501  call    ?Instance@MtfPlatformTelemetry@@KAPEAV1@XZ; MtfPlatformTelemetry::Instance(void)
0x18001b506  mov     rdi, [rax+8]
0x18001b50a  mov     eax, [rdi]
0x18001b50c  cmp     eax, 5
0x18001b50f  jbe     loc_18001B597
0x18001b515  call    cs:__imp_GetCurrentThreadId
0x18001b51b  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001b51e  mov     [rbp+57h+var_58], 0
0x18001b526  mov     r8, [rbx+110h]
0x18001b52d  cmp     byte ptr [r8+4], 0
0x18001b532  jz      short loc_18001B553
0x18001b534  lea     r9, [r8+18h]
0x18001b538  cmp     dword ptr [r9], 0
0x18001b53c  jnz     short loc_18001B556
0x18001b53e  cmp     dword ptr [r9+4], 0
0x18001b543  jnz     short loc_18001B556
0x18001b545  cmp     dword ptr [r9+8], 0
0x18001b54a  jnz     short loc_18001B556
0x18001b54c  cmp     dword ptr [r9+0Ch], 0
0x18001b551  jnz     short loc_18001B556
0x18001b553  xor     r9d, r9d
0x18001b556  lea     rax, [rbp+57h+SRWLock]
0x18001b55a  mov     [rbp+57h+var_20], rax
0x18001b55e  mov     ecx, 4
0x18001b563  mov     [rbp+57h+var_18], rcx
0x18001b567  lea     rax, [rbp+57h+var_58]
0x18001b56b  mov     [rbp+57h+var_30], rax
0x18001b56f  mov     [rbp+57h+var_28], 8
0x18001b577  add     r8, 8
0x18001b57b  lea     rax, [rbp+57h+var_50]
0x18001b57f  mov     [rsp+90h+var_68], rax
0x18001b584  mov     [rsp+90h+var_70], ecx
0x18001b588  lea     rdx, qword_180036AE8
0x18001b58f  mov     rcx, rdi
0x18001b592  call    _tlgWriteTransfer_EventWriteTransfer
0x18001b597  cmp     dword ptr [rbx+138h], 0
0x18001b59e  jnz     short loc_18001B5DC
0x18001b5a0  add     rbx, 120h
0x18001b5a7  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001b5af  jz      short loc_18001B5D5
0x18001b5b1  mov     dl, 1
0x18001b5b3  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18001b5b8  mov     [rbx], rax
0x18001b5bb  test    rax, rax
0x18001b5be  jz      short loc_18001B5DC
0x18001b5c0  mov     rcx, [rax]
0x18001b5c3  mov     [rbx+10h], rcx
0x18001b5c7  mov     [rax], rbx
0x18001b5ca  call    cs:__imp_GetCurrentThreadId
0x18001b5d0  mov     [rbx+18h], eax
0x18001b5d3  jmp     short loc_18001B5DC
0x18001b5d5  mov     qword ptr [rbx], 0
0x18001b5dc  mov     rcx, [rbp+57h+var_10]
0x18001b5e0  xor     rcx, rsp; StackCookie
0x18001b5e3  call    __security_check_cookie
0x18001b5e8  lea     r11, [rsp+90h+var_s0]
0x18001b5f0  mov     rbx, [r11+18h]
0x18001b5f4  mov     rdi, [r11+20h]
0x18001b5f8  mov     rsp, r11
0x18001b5fb  pop     rbp
0x18001b5fc  retn
```
