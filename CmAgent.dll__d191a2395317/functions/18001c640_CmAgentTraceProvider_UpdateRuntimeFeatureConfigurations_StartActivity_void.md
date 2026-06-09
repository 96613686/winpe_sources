# CmAgentTraceProvider::UpdateRuntimeFeatureConfigurations::StartActivity(void)

- ea: `0x18001c640`
- end: `0x18001c76b`
- name: `?StartActivity@UpdateRuntimeFeatureConfigurations@CmAgentTraceProvider@@QEAAXXZ`
- size: `299`
- prototype: `void __fastcall(CmAgentTraceProvider::UpdateRuntimeFeatureConfigurations *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180020000`

## callees

- `0x180001970`
- `0x180002140`
- `0x180006fcc`
- `0x1800088b0`
- `0x180009940`
- `0x18001c640`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c6a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c6a5`

## pseudocode

```c
void __fastcall CmAgentTraceProvider::UpdateRuntimeFeatureConfigurations::StartActivity(
        CmAgentTraceProvider::UpdateRuntimeFeatureConfigurations *this)
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
    tlgWriteTransfer_EventWriteTransfer(v2, (unsigned __int8 *)byte_180043531, (const GUID *)(v3 + 8), v4, 4u, &v7);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((CmAgentTraceProvider::UpdateRuntimeFeatureConfigurations *)((char *)this + 288));
}

```

## disassembly

```asm
0x18001c640  mov     [rsp+arg_8], rbx
0x18001c645  push    rdi
0x18001c646  sub     rsp, 90h
0x18001c64d  mov     rax, cs:__security_cookie
0x18001c654  xor     rax, rsp
0x18001c657  mov     [rsp+98h+var_18], rax
0x18001c65f  mov     rbx, rcx
0x18001c662  call    ?zInternalStart@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001c667  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001c66c  mov     rdi, [rax+8]
0x18001c670  mov     eax, [rdi]
0x18001c672  cmp     eax, 5
0x18001c675  jbe     loc_18001C736
0x18001c67b  mov     rcx, [rdi+18h]
0x18001c67f  mov     rax, [rdi+10h]
0x18001c683  mov     rdx, 400000000000h
0x18001c68d  test    rdx, rax
0x18001c690  jz      loc_18001C736
0x18001c696  mov     rax, rcx
0x18001c699  and     rax, rdx
0x18001c69c  cmp     rax, rcx
0x18001c69f  jnz     loc_18001C736
0x18001c6a5  call    cs:__imp_GetCurrentThreadId
0x18001c6ac  nop     dword ptr [rax+rax+00h]
0x18001c6b1  mov     [rsp+98h+var_68], eax
0x18001c6b5  mov     [rsp+98h+var_60], 1000000h
0x18001c6be  mov     r8, [rbx+110h]
0x18001c6c5  cmp     byte ptr [r8+4], 0
0x18001c6ca  jz      short loc_18001C6EB
0x18001c6cc  lea     r9, [r8+18h]
0x18001c6d0  cmp     dword ptr [r9], 0
0x18001c6d4  jnz     short loc_18001C6EE
0x18001c6d6  cmp     dword ptr [r9+4], 0
0x18001c6db  jnz     short loc_18001C6EE
0x18001c6dd  cmp     dword ptr [r9+8], 0
0x18001c6e2  jnz     short loc_18001C6EE
0x18001c6e4  cmp     dword ptr [r9+0Ch], 0
0x18001c6e9  jnz     short loc_18001C6EE
0x18001c6eb  xor     r9d, r9d
0x18001c6ee  lea     rax, [rsp+98h+var_68]
0x18001c6f3  mov     [rsp+98h+var_28], rax
0x18001c6f8  mov     ecx, 4
0x18001c6fd  mov     [rsp+98h+var_20], rcx
0x18001c702  lea     rax, [rsp+98h+var_60]
0x18001c707  mov     [rsp+98h+var_38], rax
0x18001c70c  mov     [rsp+98h+var_30], 8
0x18001c715  add     r8, 8
0x18001c719  lea     rax, [rsp+98h+var_58]
0x18001c71e  mov     [rsp+98h+var_70], rax
0x18001c723  mov     [rsp+98h+var_78], ecx
0x18001c727  lea     rdx, byte_180043531
0x18001c72e  mov     rcx, rdi
0x18001c731  call    _tlgWriteTransfer_EventWriteTransfer
0x18001c736  lea     rcx, [rbx+120h]; this
0x18001c73d  cmp     dword ptr [rcx+18h], 0
0x18001c741  jnz     short loc_18001C749
0x18001c743  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18001c748  nop
0x18001c749  mov     rcx, [rsp+98h+var_18]
0x18001c751  xor     rcx, rsp; StackCookie
0x18001c754  call    __security_check_cookie
0x18001c759  mov     rbx, [rsp+98h+arg_8]
0x18001c761  add     rsp, 90h
0x18001c768  pop     rdi
0x18001c769  retn
```
