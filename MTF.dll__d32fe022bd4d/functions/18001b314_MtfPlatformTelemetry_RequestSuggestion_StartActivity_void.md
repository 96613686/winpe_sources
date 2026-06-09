# MtfPlatformTelemetry::RequestSuggestion::StartActivity(void)

- ea: `0x18001b314`
- end: `0x18001b485`
- name: `?StartActivity@RequestSuggestion@MtfPlatformTelemetry@@QEAAXXZ`
- size: `369`
- prototype: `void __fastcall(MtfPlatformTelemetry::RequestSuggestion *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001a450`

## callees

- `0x18000163c`
- `0x180004d20`
- `0x1800053cc`
- `0x180018d00`
- `0x18001b314`
- `0x18002bca0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b383`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b383`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001b365`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001b365`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b39d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b452`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b39d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b452`

## pseudocode

```c
void __fastcall MtfPlatformTelemetry::RequestSuggestion::StartActivity(MtfPlatformTelemetry::RequestSuggestion *this)
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
    tlgWriteTransfer_EventWriteTransfer(v5, word_18003649A, v6 + 8);
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
0x18001b314  mov     [rsp-8+arg_8], rbx
0x18001b319  mov     [rsp-8+arg_10], rdi
0x18001b31e  push    rbp
0x18001b31f  lea     rbp, [rsp-57h]
0x18001b324  sub     rsp, 90h
0x18001b32b  mov     rax, cs:__security_cookie
0x18001b332  xor     rax, rsp
0x18001b335  mov     [rbp+57h+var_10], rax
0x18001b339  mov     rbx, rcx
0x18001b33c  lea     rdx, [rbp+57h+SRWLock]
0x18001b340  call    ?LockExclusive@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001b345  mov     rdi, [rbx+110h]
0x18001b34c  call    ?Instance@MtfPlatformTelemetry@@KAPEAV1@XZ; MtfPlatformTelemetry::Instance(void)
0x18001b351  mov     rdx, [rax+8]
0x18001b355  mov     eax, [rdx]
0x18001b357  cmp     eax, 5
0x18001b35a  jbe     short loc_18001B36D
0x18001b35c  lea     rdx, [rdi+8]; ActivityId
0x18001b360  mov     ecx, 3; ControlCode
0x18001b365  call    cs:__imp_EventActivityIdControl
0x18001b36b  jmp     short loc_18001B374
0x18001b36d  xorps   xmm0, xmm0
0x18001b370  movups  xmmword ptr [rdi+8], xmm0
0x18001b374  mov     dword ptr [rdi], 1
0x18001b37a  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001b37e  test    rcx, rcx
0x18001b381  jz      short loc_18001B389
0x18001b383  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b389  call    ?Instance@MtfPlatformTelemetry@@KAPEAV1@XZ; MtfPlatformTelemetry::Instance(void)
0x18001b38e  mov     rdi, [rax+8]
0x18001b392  mov     eax, [rdi]
0x18001b394  cmp     eax, 5
0x18001b397  jbe     loc_18001B41F
0x18001b39d  call    cs:__imp_GetCurrentThreadId
0x18001b3a3  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001b3a6  mov     [rbp+57h+var_58], 0
0x18001b3ae  mov     r8, [rbx+110h]
0x18001b3b5  cmp     byte ptr [r8+4], 0
0x18001b3ba  jz      short loc_18001B3DB
0x18001b3bc  lea     r9, [r8+18h]
0x18001b3c0  cmp     dword ptr [r9], 0
0x18001b3c4  jnz     short loc_18001B3DE
0x18001b3c6  cmp     dword ptr [r9+4], 0
0x18001b3cb  jnz     short loc_18001B3DE
0x18001b3cd  cmp     dword ptr [r9+8], 0
0x18001b3d2  jnz     short loc_18001B3DE
0x18001b3d4  cmp     dword ptr [r9+0Ch], 0
0x18001b3d9  jnz     short loc_18001B3DE
0x18001b3db  xor     r9d, r9d
0x18001b3de  lea     rax, [rbp+57h+SRWLock]
0x18001b3e2  mov     [rbp+57h+var_20], rax
0x18001b3e6  mov     ecx, 4
0x18001b3eb  mov     [rbp+57h+var_18], rcx
0x18001b3ef  lea     rax, [rbp+57h+var_58]
0x18001b3f3  mov     [rbp+57h+var_30], rax
0x18001b3f7  mov     [rbp+57h+var_28], 8
0x18001b3ff  add     r8, 8
0x18001b403  lea     rax, [rbp+57h+var_50]
0x18001b407  mov     [rsp+90h+var_68], rax
0x18001b40c  mov     [rsp+90h+var_70], ecx
0x18001b410  lea     rdx, word_18003649A
0x18001b417  mov     rcx, rdi
0x18001b41a  call    _tlgWriteTransfer_EventWriteTransfer
0x18001b41f  cmp     dword ptr [rbx+138h], 0
0x18001b426  jnz     short loc_18001B464
0x18001b428  add     rbx, 120h
0x18001b42f  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001b437  jz      short loc_18001B45D
0x18001b439  mov     dl, 1
0x18001b43b  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18001b440  mov     [rbx], rax
0x18001b443  test    rax, rax
0x18001b446  jz      short loc_18001B464
0x18001b448  mov     rcx, [rax]
0x18001b44b  mov     [rbx+10h], rcx
0x18001b44f  mov     [rax], rbx
0x18001b452  call    cs:__imp_GetCurrentThreadId
0x18001b458  mov     [rbx+18h], eax
0x18001b45b  jmp     short loc_18001B464
0x18001b45d  mov     qword ptr [rbx], 0
0x18001b464  mov     rcx, [rbp+57h+var_10]
0x18001b468  xor     rcx, rsp; StackCookie
0x18001b46b  call    __security_check_cookie
0x18001b470  lea     r11, [rsp+90h+var_s0]
0x18001b478  mov     rbx, [r11+18h]
0x18001b47c  mov     rdi, [r11+20h]
0x18001b480  mov     rsp, r11
0x18001b483  pop     rbp
0x18001b484  retn
```
