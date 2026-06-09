# MtfPlatformTelemetry::UpdateDataSource::StartActivity(void)

- ea: `0x18001b77c`
- end: `0x18001b8ed`
- name: `?StartActivity@UpdateDataSource@MtfPlatformTelemetry@@QEAAXXZ`
- size: `369`
- prototype: `void __fastcall(MtfPlatformTelemetry::UpdateDataSource *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18001cae0`

## callees

- `0x18000163c`
- `0x180004d20`
- `0x1800053cc`
- `0x180018d00`
- `0x18001b77c`
- `0x18002bca0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b7eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b7eb`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001b7cd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001b7cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b805`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b8ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b805`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b8ba`

## pseudocode

```c
void __fastcall MtfPlatformTelemetry::UpdateDataSource::StartActivity(MtfPlatformTelemetry::UpdateDataSource *this)
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
    tlgWriteTransfer_EventWriteTransfer(v5, word_180036222, v6 + 8);
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
0x18001b77c  mov     [rsp-8+arg_8], rbx
0x18001b781  mov     [rsp-8+arg_10], rdi
0x18001b786  push    rbp
0x18001b787  lea     rbp, [rsp-57h]
0x18001b78c  sub     rsp, 90h
0x18001b793  mov     rax, cs:__security_cookie
0x18001b79a  xor     rax, rsp
0x18001b79d  mov     [rbp+57h+var_10], rax
0x18001b7a1  mov     rbx, rcx
0x18001b7a4  lea     rdx, [rbp+57h+SRWLock]
0x18001b7a8  call    ?LockExclusive@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001b7ad  mov     rdi, [rbx+110h]
0x18001b7b4  call    ?Instance@MtfPlatformTelemetry@@KAPEAV1@XZ; MtfPlatformTelemetry::Instance(void)
0x18001b7b9  mov     rdx, [rax+8]
0x18001b7bd  mov     eax, [rdx]
0x18001b7bf  cmp     eax, 5
0x18001b7c2  jbe     short loc_18001B7D5
0x18001b7c4  lea     rdx, [rdi+8]; ActivityId
0x18001b7c8  mov     ecx, 3; ControlCode
0x18001b7cd  call    cs:__imp_EventActivityIdControl
0x18001b7d3  jmp     short loc_18001B7DC
0x18001b7d5  xorps   xmm0, xmm0
0x18001b7d8  movups  xmmword ptr [rdi+8], xmm0
0x18001b7dc  mov     dword ptr [rdi], 1
0x18001b7e2  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001b7e6  test    rcx, rcx
0x18001b7e9  jz      short loc_18001B7F1
0x18001b7eb  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b7f1  call    ?Instance@MtfPlatformTelemetry@@KAPEAV1@XZ; MtfPlatformTelemetry::Instance(void)
0x18001b7f6  mov     rdi, [rax+8]
0x18001b7fa  mov     eax, [rdi]
0x18001b7fc  cmp     eax, 5
0x18001b7ff  jbe     loc_18001B887
0x18001b805  call    cs:__imp_GetCurrentThreadId
0x18001b80b  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001b80e  mov     [rbp+57h+var_58], 0
0x18001b816  mov     r8, [rbx+110h]
0x18001b81d  cmp     byte ptr [r8+4], 0
0x18001b822  jz      short loc_18001B843
0x18001b824  lea     r9, [r8+18h]
0x18001b828  cmp     dword ptr [r9], 0
0x18001b82c  jnz     short loc_18001B846
0x18001b82e  cmp     dword ptr [r9+4], 0
0x18001b833  jnz     short loc_18001B846
0x18001b835  cmp     dword ptr [r9+8], 0
0x18001b83a  jnz     short loc_18001B846
0x18001b83c  cmp     dword ptr [r9+0Ch], 0
0x18001b841  jnz     short loc_18001B846
0x18001b843  xor     r9d, r9d
0x18001b846  lea     rax, [rbp+57h+SRWLock]
0x18001b84a  mov     [rbp+57h+var_20], rax
0x18001b84e  mov     ecx, 4
0x18001b853  mov     [rbp+57h+var_18], rcx
0x18001b857  lea     rax, [rbp+57h+var_58]
0x18001b85b  mov     [rbp+57h+var_30], rax
0x18001b85f  mov     [rbp+57h+var_28], 8
0x18001b867  add     r8, 8
0x18001b86b  lea     rax, [rbp+57h+var_50]
0x18001b86f  mov     [rsp+90h+var_68], rax
0x18001b874  mov     [rsp+90h+var_70], ecx
0x18001b878  lea     rdx, word_180036222
0x18001b87f  mov     rcx, rdi
0x18001b882  call    _tlgWriteTransfer_EventWriteTransfer
0x18001b887  cmp     dword ptr [rbx+138h], 0
0x18001b88e  jnz     short loc_18001B8CC
0x18001b890  add     rbx, 120h
0x18001b897  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001b89f  jz      short loc_18001B8C5
0x18001b8a1  mov     dl, 1
0x18001b8a3  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18001b8a8  mov     [rbx], rax
0x18001b8ab  test    rax, rax
0x18001b8ae  jz      short loc_18001B8CC
0x18001b8b0  mov     rcx, [rax]
0x18001b8b3  mov     [rbx+10h], rcx
0x18001b8b7  mov     [rax], rbx
0x18001b8ba  call    cs:__imp_GetCurrentThreadId
0x18001b8c0  mov     [rbx+18h], eax
0x18001b8c3  jmp     short loc_18001B8CC
0x18001b8c5  mov     qword ptr [rbx], 0
0x18001b8cc  mov     rcx, [rbp+57h+var_10]
0x18001b8d0  xor     rcx, rsp; StackCookie
0x18001b8d3  call    __security_check_cookie
0x18001b8d8  lea     r11, [rsp+90h+var_s0]
0x18001b8e0  mov     rbx, [r11+18h]
0x18001b8e4  mov     rdi, [r11+20h]
0x18001b8e8  mov     rsp, r11
0x18001b8eb  pop     rbp
0x18001b8ec  retn
```
