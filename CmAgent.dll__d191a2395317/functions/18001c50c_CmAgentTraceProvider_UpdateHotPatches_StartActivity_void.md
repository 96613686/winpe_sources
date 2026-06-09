# CmAgentTraceProvider::UpdateHotPatches::StartActivity(void)

- ea: `0x18001c50c`
- end: `0x18001c637`
- name: `?StartActivity@UpdateHotPatches@CmAgentTraceProvider@@QEAAXXZ`
- size: `299`
- prototype: `void __fastcall(CmAgentTraceProvider::UpdateHotPatches *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x18001fb70`

## callees

- `0x180001970`
- `0x180002140`
- `0x180006fcc`
- `0x1800088b0`
- `0x180009940`
- `0x18001c50c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c571`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c571`

## pseudocode

```c
void __fastcall CmAgentTraceProvider::UpdateHotPatches::StartActivity(CmAgentTraceProvider::UpdateHotPatches *this)
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
    tlgWriteTransfer_EventWriteTransfer(v2, (unsigned __int8 *)byte_1800442C5, (const GUID *)(v3 + 8), v4, 4u, &v7);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((CmAgentTraceProvider::UpdateHotPatches *)((char *)this + 288));
}

```

## disassembly

```asm
0x18001c50c  mov     [rsp+arg_8], rbx
0x18001c511  push    rdi
0x18001c512  sub     rsp, 90h
0x18001c519  mov     rax, cs:__security_cookie
0x18001c520  xor     rax, rsp
0x18001c523  mov     [rsp+98h+var_18], rax
0x18001c52b  mov     rbx, rcx
0x18001c52e  call    ?zInternalStart@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001c533  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001c538  mov     rdi, [rax+8]
0x18001c53c  mov     eax, [rdi]
0x18001c53e  cmp     eax, 5
0x18001c541  jbe     loc_18001C602
0x18001c547  mov     rcx, [rdi+18h]
0x18001c54b  mov     rax, [rdi+10h]
0x18001c54f  mov     rdx, 400000000000h
0x18001c559  test    rdx, rax
0x18001c55c  jz      loc_18001C602
0x18001c562  mov     rax, rcx
0x18001c565  and     rax, rdx
0x18001c568  cmp     rax, rcx
0x18001c56b  jnz     loc_18001C602
0x18001c571  call    cs:__imp_GetCurrentThreadId
0x18001c578  nop     dword ptr [rax+rax+00h]
0x18001c57d  mov     [rsp+98h+var_68], eax
0x18001c581  mov     [rsp+98h+var_60], 1000000h
0x18001c58a  mov     r8, [rbx+110h]
0x18001c591  cmp     byte ptr [r8+4], 0
0x18001c596  jz      short loc_18001C5B7
0x18001c598  lea     r9, [r8+18h]
0x18001c59c  cmp     dword ptr [r9], 0
0x18001c5a0  jnz     short loc_18001C5BA
0x18001c5a2  cmp     dword ptr [r9+4], 0
0x18001c5a7  jnz     short loc_18001C5BA
0x18001c5a9  cmp     dword ptr [r9+8], 0
0x18001c5ae  jnz     short loc_18001C5BA
0x18001c5b0  cmp     dword ptr [r9+0Ch], 0
0x18001c5b5  jnz     short loc_18001C5BA
0x18001c5b7  xor     r9d, r9d
0x18001c5ba  lea     rax, [rsp+98h+var_68]
0x18001c5bf  mov     [rsp+98h+var_28], rax
0x18001c5c4  mov     ecx, 4
0x18001c5c9  mov     [rsp+98h+var_20], rcx
0x18001c5ce  lea     rax, [rsp+98h+var_60]
0x18001c5d3  mov     [rsp+98h+var_38], rax
0x18001c5d8  mov     [rsp+98h+var_30], 8
0x18001c5e1  add     r8, 8
0x18001c5e5  lea     rax, [rsp+98h+var_58]
0x18001c5ea  mov     [rsp+98h+var_70], rax
0x18001c5ef  mov     [rsp+98h+var_78], ecx
0x18001c5f3  lea     rdx, byte_1800442C5
0x18001c5fa  mov     rcx, rdi
0x18001c5fd  call    _tlgWriteTransfer_EventWriteTransfer
0x18001c602  lea     rcx, [rbx+120h]; this
0x18001c609  cmp     dword ptr [rcx+18h], 0
0x18001c60d  jnz     short loc_18001C615
0x18001c60f  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18001c614  nop
0x18001c615  mov     rcx, [rsp+98h+var_18]
0x18001c61d  xor     rcx, rsp; StackCookie
0x18001c620  call    __security_check_cookie
0x18001c625  mov     rbx, [rsp+98h+arg_8]
0x18001c62d  add     rsp, 90h
0x18001c634  pop     rdi
0x18001c635  retn
```
