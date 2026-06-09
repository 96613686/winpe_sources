# CmAgentTraceProvider::WaitForFirstBootNoLogon::StartActivity(void)

- ea: `0x18001c8a8`
- end: `0x18001c9d3`
- name: `?StartActivity@WaitForFirstBootNoLogon@CmAgentTraceProvider@@QEAAXXZ`
- size: `299`
- prototype: `void __fastcall(CmAgentTraceProvider::WaitForFirstBootNoLogon *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180005400`

## callees

- `0x180001970`
- `0x180002140`
- `0x180006fcc`
- `0x1800088b0`
- `0x180009940`
- `0x18001c8a8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c90d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c90d`

## pseudocode

```c
void __fastcall CmAgentTraceProvider::WaitForFirstBootNoLogon::StartActivity(
        CmAgentTraceProvider::WaitForFirstBootNoLogon *this)
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
    tlgWriteTransfer_EventWriteTransfer(v2, (unsigned __int8 *)byte_18004329B, (const GUID *)(v3 + 8), v4, 4u, &v7);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((CmAgentTraceProvider::WaitForFirstBootNoLogon *)((char *)this + 288));
}

```

## disassembly

```asm
0x18001c8a8  mov     [rsp+arg_8], rbx
0x18001c8ad  push    rdi
0x18001c8ae  sub     rsp, 90h
0x18001c8b5  mov     rax, cs:__security_cookie
0x18001c8bc  xor     rax, rsp
0x18001c8bf  mov     [rsp+98h+var_18], rax
0x18001c8c7  mov     rbx, rcx
0x18001c8ca  call    ?zInternalStart@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001c8cf  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001c8d4  mov     rdi, [rax+8]
0x18001c8d8  mov     eax, [rdi]
0x18001c8da  cmp     eax, 5
0x18001c8dd  jbe     loc_18001C99E
0x18001c8e3  mov     rcx, [rdi+18h]
0x18001c8e7  mov     rax, [rdi+10h]
0x18001c8eb  mov     rdx, 400000000000h
0x18001c8f5  test    rdx, rax
0x18001c8f8  jz      loc_18001C99E
0x18001c8fe  mov     rax, rcx
0x18001c901  and     rax, rdx
0x18001c904  cmp     rax, rcx
0x18001c907  jnz     loc_18001C99E
0x18001c90d  call    cs:__imp_GetCurrentThreadId
0x18001c914  nop     dword ptr [rax+rax+00h]
0x18001c919  mov     [rsp+98h+var_68], eax
0x18001c91d  mov     [rsp+98h+var_60], 1000000h
0x18001c926  mov     r8, [rbx+110h]
0x18001c92d  cmp     byte ptr [r8+4], 0
0x18001c932  jz      short loc_18001C953
0x18001c934  lea     r9, [r8+18h]
0x18001c938  cmp     dword ptr [r9], 0
0x18001c93c  jnz     short loc_18001C956
0x18001c93e  cmp     dword ptr [r9+4], 0
0x18001c943  jnz     short loc_18001C956
0x18001c945  cmp     dword ptr [r9+8], 0
0x18001c94a  jnz     short loc_18001C956
0x18001c94c  cmp     dword ptr [r9+0Ch], 0
0x18001c951  jnz     short loc_18001C956
0x18001c953  xor     r9d, r9d
0x18001c956  lea     rax, [rsp+98h+var_68]
0x18001c95b  mov     [rsp+98h+var_28], rax
0x18001c960  mov     ecx, 4
0x18001c965  mov     [rsp+98h+var_20], rcx
0x18001c96a  lea     rax, [rsp+98h+var_60]
0x18001c96f  mov     [rsp+98h+var_38], rax
0x18001c974  mov     [rsp+98h+var_30], 8
0x18001c97d  add     r8, 8
0x18001c981  lea     rax, [rsp+98h+var_58]
0x18001c986  mov     [rsp+98h+var_70], rax
0x18001c98b  mov     [rsp+98h+var_78], ecx
0x18001c98f  lea     rdx, byte_18004329B
0x18001c996  mov     rcx, rdi
0x18001c999  call    _tlgWriteTransfer_EventWriteTransfer
0x18001c99e  lea     rcx, [rbx+120h]; this
0x18001c9a5  cmp     dword ptr [rcx+18h], 0
0x18001c9a9  jnz     short loc_18001C9B1
0x18001c9ab  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18001c9b0  nop
0x18001c9b1  mov     rcx, [rsp+98h+var_18]
0x18001c9b9  xor     rcx, rsp; StackCookie
0x18001c9bc  call    __security_check_cookie
0x18001c9c1  mov     rbx, [rsp+98h+arg_8]
0x18001c9c9  add     rsp, 90h
0x18001c9d0  pop     rdi
0x18001c9d1  retn
```
