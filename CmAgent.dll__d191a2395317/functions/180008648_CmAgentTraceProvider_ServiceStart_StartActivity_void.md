# CmAgentTraceProvider::ServiceStart::StartActivity(void)

- ea: `0x180008648`
- end: `0x180008773`
- name: `?StartActivity@ServiceStart@CmAgentTraceProvider@@QEAAXXZ`
- size: `299`
- prototype: `void __fastcall(CmAgentTraceProvider::ServiceStart *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180009a60`

## callees

- `0x180001970`
- `0x180002140`
- `0x180006fcc`
- `0x180008648`
- `0x1800088b0`
- `0x180009940`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800086ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800086ad`

## pseudocode

```c
void __fastcall CmAgentTraceProvider::ServiceStart::StartActivity(CmAgentTraceProvider::ServiceStart *this)
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
    tlgWriteTransfer_EventWriteTransfer(v2, (unsigned __int8 *)byte_180043143, (const GUID *)(v3 + 8), v4, 4u, &v7);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((CmAgentTraceProvider::ServiceStart *)((char *)this + 288));
}

```

## disassembly

```asm
0x180008648  mov     [rsp+arg_8], rbx
0x18000864d  push    rdi
0x18000864e  sub     rsp, 90h
0x180008655  mov     rax, cs:__security_cookie
0x18000865c  xor     rax, rsp
0x18000865f  mov     [rsp+98h+var_18], rax
0x180008667  mov     rbx, rcx
0x18000866a  call    ?zInternalStart@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000866f  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x180008674  mov     rdi, [rax+8]
0x180008678  mov     eax, [rdi]
0x18000867a  cmp     eax, 5
0x18000867d  jbe     loc_18000873E
0x180008683  mov     rcx, [rdi+18h]
0x180008687  mov     rax, [rdi+10h]
0x18000868b  mov     rdx, 400000000000h
0x180008695  test    rdx, rax
0x180008698  jz      loc_18000873E
0x18000869e  mov     rax, rcx
0x1800086a1  and     rax, rdx
0x1800086a4  cmp     rax, rcx
0x1800086a7  jnz     loc_18000873E
0x1800086ad  call    cs:__imp_GetCurrentThreadId
0x1800086b4  nop     dword ptr [rax+rax+00h]
0x1800086b9  mov     [rsp+98h+var_68], eax
0x1800086bd  mov     [rsp+98h+var_60], 1000000h
0x1800086c6  mov     r8, [rbx+110h]
0x1800086cd  cmp     byte ptr [r8+4], 0
0x1800086d2  jz      short loc_1800086F3
0x1800086d4  lea     r9, [r8+18h]
0x1800086d8  cmp     dword ptr [r9], 0
0x1800086dc  jnz     short loc_1800086F6
0x1800086de  cmp     dword ptr [r9+4], 0
0x1800086e3  jnz     short loc_1800086F6
0x1800086e5  cmp     dword ptr [r9+8], 0
0x1800086ea  jnz     short loc_1800086F6
0x1800086ec  cmp     dword ptr [r9+0Ch], 0
0x1800086f1  jnz     short loc_1800086F6
0x1800086f3  xor     r9d, r9d
0x1800086f6  lea     rax, [rsp+98h+var_68]
0x1800086fb  mov     [rsp+98h+var_28], rax
0x180008700  mov     ecx, 4
0x180008705  mov     [rsp+98h+var_20], rcx
0x18000870a  lea     rax, [rsp+98h+var_60]
0x18000870f  mov     [rsp+98h+var_38], rax
0x180008714  mov     [rsp+98h+var_30], 8
0x18000871d  add     r8, 8
0x180008721  lea     rax, [rsp+98h+var_58]
0x180008726  mov     [rsp+98h+var_70], rax
0x18000872b  mov     [rsp+98h+var_78], ecx
0x18000872f  lea     rdx, byte_180043143
0x180008736  mov     rcx, rdi
0x180008739  call    _tlgWriteTransfer_EventWriteTransfer
0x18000873e  lea     rcx, [rbx+120h]; this
0x180008745  cmp     dword ptr [rcx+18h], 0
0x180008749  jnz     short loc_180008751
0x18000874b  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180008750  nop
0x180008751  mov     rcx, [rsp+98h+var_18]
0x180008759  xor     rcx, rsp; StackCookie
0x18000875c  call    __security_check_cookie
0x180008761  mov     rbx, [rsp+98h+arg_8]
0x180008769  add     rsp, 90h
0x180008770  pop     rdi
0x180008771  retn
```
