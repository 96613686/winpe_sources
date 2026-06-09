# CmAgentTraceProvider::OptimizeSnapshot::StartActivity(void)

- ea: `0x18001c0e8`
- end: `0x18001c213`
- name: `?StartActivity@OptimizeSnapshot@CmAgentTraceProvider@@QEAAXXZ`
- size: `299`
- prototype: `void __fastcall(CmAgentTraceProvider::OptimizeSnapshot *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180004f40`

## callees

- `0x180001970`
- `0x180002140`
- `0x180006fcc`
- `0x1800088b0`
- `0x180009940`
- `0x18001c0e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c14d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c14d`

## pseudocode

```c
void __fastcall CmAgentTraceProvider::OptimizeSnapshot::StartActivity(CmAgentTraceProvider::OptimizeSnapshot *this)
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
    tlgWriteTransfer_EventWriteTransfer(v2, (unsigned __int8 *)byte_180044439, (const GUID *)(v3 + 8), v4, 4u, &v7);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((CmAgentTraceProvider::OptimizeSnapshot *)((char *)this + 288));
}

```

## disassembly

```asm
0x18001c0e8  mov     [rsp+arg_8], rbx
0x18001c0ed  push    rdi
0x18001c0ee  sub     rsp, 90h
0x18001c0f5  mov     rax, cs:__security_cookie
0x18001c0fc  xor     rax, rsp
0x18001c0ff  mov     [rsp+98h+var_18], rax
0x18001c107  mov     rbx, rcx
0x18001c10a  call    ?zInternalStart@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001c10f  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001c114  mov     rdi, [rax+8]
0x18001c118  mov     eax, [rdi]
0x18001c11a  cmp     eax, 5
0x18001c11d  jbe     loc_18001C1DE
0x18001c123  mov     rcx, [rdi+18h]
0x18001c127  mov     rax, [rdi+10h]
0x18001c12b  mov     rdx, 400000000000h
0x18001c135  test    rdx, rax
0x18001c138  jz      loc_18001C1DE
0x18001c13e  mov     rax, rcx
0x18001c141  and     rax, rdx
0x18001c144  cmp     rax, rcx
0x18001c147  jnz     loc_18001C1DE
0x18001c14d  call    cs:__imp_GetCurrentThreadId
0x18001c154  nop     dword ptr [rax+rax+00h]
0x18001c159  mov     [rsp+98h+var_68], eax
0x18001c15d  mov     [rsp+98h+var_60], 1000000h
0x18001c166  mov     r8, [rbx+110h]
0x18001c16d  cmp     byte ptr [r8+4], 0
0x18001c172  jz      short loc_18001C193
0x18001c174  lea     r9, [r8+18h]
0x18001c178  cmp     dword ptr [r9], 0
0x18001c17c  jnz     short loc_18001C196
0x18001c17e  cmp     dword ptr [r9+4], 0
0x18001c183  jnz     short loc_18001C196
0x18001c185  cmp     dword ptr [r9+8], 0
0x18001c18a  jnz     short loc_18001C196
0x18001c18c  cmp     dword ptr [r9+0Ch], 0
0x18001c191  jnz     short loc_18001C196
0x18001c193  xor     r9d, r9d
0x18001c196  lea     rax, [rsp+98h+var_68]
0x18001c19b  mov     [rsp+98h+var_28], rax
0x18001c1a0  mov     ecx, 4
0x18001c1a5  mov     [rsp+98h+var_20], rcx
0x18001c1aa  lea     rax, [rsp+98h+var_60]
0x18001c1af  mov     [rsp+98h+var_38], rax
0x18001c1b4  mov     [rsp+98h+var_30], 8
0x18001c1bd  add     r8, 8
0x18001c1c1  lea     rax, [rsp+98h+var_58]
0x18001c1c6  mov     [rsp+98h+var_70], rax
0x18001c1cb  mov     [rsp+98h+var_78], ecx
0x18001c1cf  lea     rdx, byte_180044439
0x18001c1d6  mov     rcx, rdi
0x18001c1d9  call    _tlgWriteTransfer_EventWriteTransfer
0x18001c1de  lea     rcx, [rbx+120h]; this
0x18001c1e5  cmp     dword ptr [rcx+18h], 0
0x18001c1e9  jnz     short loc_18001C1F1
0x18001c1eb  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18001c1f0  nop
0x18001c1f1  mov     rcx, [rsp+98h+var_18]
0x18001c1f9  xor     rcx, rsp; StackCookie
0x18001c1fc  call    __security_check_cookie
0x18001c201  mov     rbx, [rsp+98h+arg_8]
0x18001c209  add     rsp, 90h
0x18001c210  pop     rdi
0x18001c211  retn
```
