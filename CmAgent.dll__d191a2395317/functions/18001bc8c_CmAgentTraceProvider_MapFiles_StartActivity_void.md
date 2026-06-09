# CmAgentTraceProvider::MapFiles::StartActivity(void)

- ea: `0x18001bc8c`
- end: `0x18001bdb7`
- name: `?StartActivity@MapFiles@CmAgentTraceProvider@@QEAAXXZ`
- size: `299`
- prototype: `void __fastcall(CmAgentTraceProvider::MapFiles *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800173f4`

## callees

- `0x180001970`
- `0x180002140`
- `0x180006fcc`
- `0x1800088b0`
- `0x180009940`
- `0x18001bc8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bcf1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bcf1`

## pseudocode

```c
void __fastcall CmAgentTraceProvider::MapFiles::StartActivity(CmAgentTraceProvider::MapFiles *this)
{
  __int64 v2; // rdi
  __int64 v3; // r8
  __int64 v4; // r9
  DWORD CurrentThreadId; // [rsp+30h] [rbp-68h] BYREF
  __int64 v6; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v7[32]; // [rsp+40h] [rbp-58h] BYREF
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
      || (v4 = v3 + 24, !*(_DWORD *)(v3 + 24))
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
    tlgWriteTransfer_EventWriteTransfer(v2, &dword_180043BAC, v3 + 8, v4, 4, v7);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((CmAgentTraceProvider::MapFiles *)((char *)this + 288));
}

```

## disassembly

```asm
0x18001bc8c  mov     [rsp+arg_8], rbx
0x18001bc91  push    rdi
0x18001bc92  sub     rsp, 90h
0x18001bc99  mov     rax, cs:__security_cookie
0x18001bca0  xor     rax, rsp
0x18001bca3  mov     [rsp+98h+var_18], rax
0x18001bcab  mov     rbx, rcx
0x18001bcae  call    ?zInternalStart@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001bcb3  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001bcb8  mov     rdi, [rax+8]
0x18001bcbc  mov     eax, [rdi]
0x18001bcbe  cmp     eax, 5
0x18001bcc1  jbe     loc_18001BD82
0x18001bcc7  mov     rcx, [rdi+18h]
0x18001bccb  mov     rax, [rdi+10h]
0x18001bccf  mov     rdx, 400000000000h
0x18001bcd9  test    rdx, rax
0x18001bcdc  jz      loc_18001BD82
0x18001bce2  mov     rax, rcx
0x18001bce5  and     rax, rdx
0x18001bce8  cmp     rax, rcx
0x18001bceb  jnz     loc_18001BD82
0x18001bcf1  call    cs:__imp_GetCurrentThreadId
0x18001bcf8  nop     dword ptr [rax+rax+00h]
0x18001bcfd  mov     [rsp+98h+var_68], eax
0x18001bd01  mov     [rsp+98h+var_60], 1000000h
0x18001bd0a  mov     r8, [rbx+110h]
0x18001bd11  cmp     byte ptr [r8+4], 0
0x18001bd16  jz      short loc_18001BD37
0x18001bd18  lea     r9, [r8+18h]
0x18001bd1c  cmp     dword ptr [r9], 0
0x18001bd20  jnz     short loc_18001BD3A
0x18001bd22  cmp     dword ptr [r9+4], 0
0x18001bd27  jnz     short loc_18001BD3A
0x18001bd29  cmp     dword ptr [r9+8], 0
0x18001bd2e  jnz     short loc_18001BD3A
0x18001bd30  cmp     dword ptr [r9+0Ch], 0
0x18001bd35  jnz     short loc_18001BD3A
0x18001bd37  xor     r9d, r9d
0x18001bd3a  lea     rax, [rsp+98h+var_68]
0x18001bd3f  mov     [rsp+98h+var_28], rax
0x18001bd44  mov     ecx, 4
0x18001bd49  mov     [rsp+98h+var_20], rcx
0x18001bd4e  lea     rax, [rsp+98h+var_60]
0x18001bd53  mov     [rsp+98h+var_38], rax
0x18001bd58  mov     [rsp+98h+var_30], 8
0x18001bd61  add     r8, 8
0x18001bd65  lea     rax, [rsp+98h+var_58]
0x18001bd6a  mov     [rsp+98h+var_70], rax
0x18001bd6f  mov     [rsp+98h+var_78], ecx
0x18001bd73  lea     rdx, dword_180043BAC
0x18001bd7a  mov     rcx, rdi
0x18001bd7d  call    _tlgWriteTransfer_EventWriteTransfer
0x18001bd82  lea     rcx, [rbx+120h]; this
0x18001bd89  cmp     dword ptr [rcx+18h], 0
0x18001bd8d  jnz     short loc_18001BD95
0x18001bd8f  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18001bd94  nop
0x18001bd95  mov     rcx, [rsp+98h+var_18]
0x18001bd9d  xor     rcx, rsp; StackCookie
0x18001bda0  call    __security_check_cookie
0x18001bda5  mov     rbx, [rsp+98h+arg_8]
0x18001bdad  add     rsp, 90h
0x18001bdb4  pop     rdi
0x18001bdb5  retn
```
