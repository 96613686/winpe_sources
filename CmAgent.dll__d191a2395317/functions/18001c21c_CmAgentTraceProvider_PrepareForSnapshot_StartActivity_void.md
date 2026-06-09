# CmAgentTraceProvider::PrepareForSnapshot::StartActivity(void)

- ea: `0x18001c21c`
- end: `0x18001c347`
- name: `?StartActivity@PrepareForSnapshot@CmAgentTraceProvider@@QEAAXXZ`
- size: `299`
- prototype: `void __fastcall(CmAgentTraceProvider::PrepareForSnapshot *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180005050`

## callees

- `0x180001970`
- `0x180002140`
- `0x180006fcc`
- `0x1800088b0`
- `0x180009940`
- `0x18001c21c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c281`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c281`

## pseudocode

```c
void __fastcall CmAgentTraceProvider::PrepareForSnapshot::StartActivity(CmAgentTraceProvider::PrepareForSnapshot *this)
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
    tlgWriteTransfer_EventWriteTransfer(v2, (unsigned __int8 *)&word_180043366, (const GUID *)(v3 + 8), v4, 4u, &v7);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((CmAgentTraceProvider::PrepareForSnapshot *)((char *)this + 288));
}

```

## disassembly

```asm
0x18001c21c  mov     [rsp+arg_8], rbx
0x18001c221  push    rdi
0x18001c222  sub     rsp, 90h
0x18001c229  mov     rax, cs:__security_cookie
0x18001c230  xor     rax, rsp
0x18001c233  mov     [rsp+98h+var_18], rax
0x18001c23b  mov     rbx, rcx
0x18001c23e  call    ?zInternalStart@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001c243  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001c248  mov     rdi, [rax+8]
0x18001c24c  mov     eax, [rdi]
0x18001c24e  cmp     eax, 5
0x18001c251  jbe     loc_18001C312
0x18001c257  mov     rcx, [rdi+18h]
0x18001c25b  mov     rax, [rdi+10h]
0x18001c25f  mov     rdx, 400000000000h
0x18001c269  test    rdx, rax
0x18001c26c  jz      loc_18001C312
0x18001c272  mov     rax, rcx
0x18001c275  and     rax, rdx
0x18001c278  cmp     rax, rcx
0x18001c27b  jnz     loc_18001C312
0x18001c281  call    cs:__imp_GetCurrentThreadId
0x18001c288  nop     dword ptr [rax+rax+00h]
0x18001c28d  mov     [rsp+98h+var_68], eax
0x18001c291  mov     [rsp+98h+var_60], 1000000h
0x18001c29a  mov     r8, [rbx+110h]
0x18001c2a1  cmp     byte ptr [r8+4], 0
0x18001c2a6  jz      short loc_18001C2C7
0x18001c2a8  lea     r9, [r8+18h]
0x18001c2ac  cmp     dword ptr [r9], 0
0x18001c2b0  jnz     short loc_18001C2CA
0x18001c2b2  cmp     dword ptr [r9+4], 0
0x18001c2b7  jnz     short loc_18001C2CA
0x18001c2b9  cmp     dword ptr [r9+8], 0
0x18001c2be  jnz     short loc_18001C2CA
0x18001c2c0  cmp     dword ptr [r9+0Ch], 0
0x18001c2c5  jnz     short loc_18001C2CA
0x18001c2c7  xor     r9d, r9d
0x18001c2ca  lea     rax, [rsp+98h+var_68]
0x18001c2cf  mov     [rsp+98h+var_28], rax
0x18001c2d4  mov     ecx, 4
0x18001c2d9  mov     [rsp+98h+var_20], rcx
0x18001c2de  lea     rax, [rsp+98h+var_60]
0x18001c2e3  mov     [rsp+98h+var_38], rax
0x18001c2e8  mov     [rsp+98h+var_30], 8
0x18001c2f1  add     r8, 8
0x18001c2f5  lea     rax, [rsp+98h+var_58]
0x18001c2fa  mov     [rsp+98h+var_70], rax
0x18001c2ff  mov     [rsp+98h+var_78], ecx
0x18001c303  lea     rdx, word_180043366
0x18001c30a  mov     rcx, rdi
0x18001c30d  call    _tlgWriteTransfer_EventWriteTransfer
0x18001c312  lea     rcx, [rbx+120h]; this
0x18001c319  cmp     dword ptr [rcx+18h], 0
0x18001c31d  jnz     short loc_18001C325
0x18001c31f  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18001c324  nop
0x18001c325  mov     rcx, [rsp+98h+var_18]
0x18001c32d  xor     rcx, rsp; StackCookie
0x18001c330  call    __security_check_cookie
0x18001c335  mov     rbx, [rsp+98h+arg_8]
0x18001c33d  add     rsp, 90h
0x18001c344  pop     rdi
0x18001c345  retn
```
