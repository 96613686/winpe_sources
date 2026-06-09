# CmAgentTraceProvider::WaitForFirstBootExperience::StartActivity(void)

- ea: `0x18001c774`
- end: `0x18001c89f`
- name: `?StartActivity@WaitForFirstBootExperience@CmAgentTraceProvider@@QEAAXXZ`
- size: `299`
- prototype: `void __fastcall(CmAgentTraceProvider::WaitForFirstBootExperience *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800052f0`

## callees

- `0x180001970`
- `0x180002140`
- `0x180006fcc`
- `0x1800088b0`
- `0x180009940`
- `0x18001c774`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c7d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c7d9`

## pseudocode

```c
void __fastcall CmAgentTraceProvider::WaitForFirstBootExperience::StartActivity(
        CmAgentTraceProvider::WaitForFirstBootExperience *this)
{
  __int64 v2; // rdi
  __int64 v3; // r8
  const GUID *v4; // r9
  DWORD CurrentThreadId; // [rsp+30h] [rbp-68h] BYREF
  __int64 v6; // [rsp+38h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+40h] [rbp-58h] BYREF
  __int64 *v8; // [rsp+60h] [rbp-38h]
  __int64 v9; // [rsp+68h] [rbp-30h]
  DWORD *p_CurrentThreadId; // [rsp+70h] [rbp-28h]
  __int64 v11; // [rsp+78h] [rbp-20h]

  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = *((_QWORD *)CmAgentTraceProvider::Instance() + 1);
  if ( *(_DWORD *)v2 > 5u
    && (*(_QWORD *)(v2 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v2 + 24) & 0x400000000000LL) == *(_QWORD *)(v2 + 24) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v6 = 0x1000000;
    v3 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v3 + 4)
      || (v4 = (const GUID *)(v3 + 24), !*(_DWORD *)(v3 + 24))
      && !*(_DWORD *)(v3 + 28)
      && !*(_DWORD *)(v3 + 32)
      && !*(_DWORD *)(v3 + 36) )
    {
      v4 = 0;
    }
    p_CurrentThreadId = &CurrentThreadId;
    v11 = 4;
    v8 = &v6;
    v9 = 8;
    tlgWriteTransfer_EventWriteTransfer(v2, (unsigned __int8 *)byte_180043F29, (const GUID *)(v3 + 8), v4, 4u, &v7);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((CmAgentTraceProvider::WaitForFirstBootExperience *)((char *)this + 288));
}

```

## disassembly

```asm
0x18001c774  mov     [rsp+arg_8], rbx
0x18001c779  push    rdi
0x18001c77a  sub     rsp, 90h
0x18001c781  mov     rax, cs:__security_cookie
0x18001c788  xor     rax, rsp
0x18001c78b  mov     [rsp+98h+var_18], rax
0x18001c793  mov     rbx, rcx
0x18001c796  call    ?zInternalStart@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001c79b  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001c7a0  mov     rdi, [rax+8]
0x18001c7a4  mov     eax, [rdi]
0x18001c7a6  cmp     eax, 5
0x18001c7a9  jbe     loc_18001C86A
0x18001c7af  mov     rcx, [rdi+18h]
0x18001c7b3  mov     rax, [rdi+10h]
0x18001c7b7  mov     rdx, 400000000000h
0x18001c7c1  test    rdx, rax
0x18001c7c4  jz      loc_18001C86A
0x18001c7ca  mov     rax, rcx
0x18001c7cd  and     rax, rdx
0x18001c7d0  cmp     rax, rcx
0x18001c7d3  jnz     loc_18001C86A
0x18001c7d9  call    cs:__imp_GetCurrentThreadId
0x18001c7e0  nop     dword ptr [rax+rax+00h]
0x18001c7e5  mov     [rsp+98h+var_68], eax
0x18001c7e9  mov     [rsp+98h+var_60], 1000000h
0x18001c7f2  mov     r8, [rbx+110h]
0x18001c7f9  cmp     byte ptr [r8+4], 0
0x18001c7fe  jz      short loc_18001C81F
0x18001c800  lea     r9, [r8+18h]
0x18001c804  cmp     dword ptr [r9], 0
0x18001c808  jnz     short loc_18001C822
0x18001c80a  cmp     dword ptr [r9+4], 0
0x18001c80f  jnz     short loc_18001C822
0x18001c811  cmp     dword ptr [r9+8], 0
0x18001c816  jnz     short loc_18001C822
0x18001c818  cmp     dword ptr [r9+0Ch], 0
0x18001c81d  jnz     short loc_18001C822
0x18001c81f  xor     r9d, r9d
0x18001c822  lea     rax, [rsp+98h+var_68]
0x18001c827  mov     [rsp+98h+var_28], rax
0x18001c82c  mov     ecx, 4
0x18001c831  mov     [rsp+98h+var_20], rcx
0x18001c836  lea     rax, [rsp+98h+var_60]
0x18001c83b  mov     [rsp+98h+var_38], rax
0x18001c840  mov     [rsp+98h+var_30], 8
0x18001c849  add     r8, 8
0x18001c84d  lea     rax, [rsp+98h+var_58]
0x18001c852  mov     [rsp+98h+var_70], rax
0x18001c857  mov     [rsp+98h+var_78], ecx
0x18001c85b  lea     rdx, byte_180043F29
0x18001c862  mov     rcx, rdi
0x18001c865  call    _tlgWriteTransfer_EventWriteTransfer
0x18001c86a  lea     rcx, [rbx+120h]; this
0x18001c871  cmp     dword ptr [rcx+18h], 0
0x18001c875  jnz     short loc_18001C87D
0x18001c877  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18001c87c  nop
0x18001c87d  mov     rcx, [rsp+98h+var_18]
0x18001c885  xor     rcx, rsp; StackCookie
0x18001c888  call    __security_check_cookie
0x18001c88d  mov     rbx, [rsp+98h+arg_8]
0x18001c895  add     rsp, 90h
0x18001c89c  pop     rdi
0x18001c89d  retn
```
