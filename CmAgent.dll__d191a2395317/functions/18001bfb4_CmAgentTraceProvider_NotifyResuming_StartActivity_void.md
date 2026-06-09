# CmAgentTraceProvider::NotifyResuming::StartActivity(void)

- ea: `0x18001bfb4`
- end: `0x18001c0df`
- name: `?StartActivity@NotifyResuming@CmAgentTraceProvider@@QEAAXXZ`
- size: `299`
- prototype: `void __fastcall(CmAgentTraceProvider::NotifyResuming *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180004e30`

## callees

- `0x180001970`
- `0x180002140`
- `0x180006fcc`
- `0x1800088b0`
- `0x180009940`
- `0x18001bfb4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c019`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c019`

## pseudocode

```c
void __fastcall CmAgentTraceProvider::NotifyResuming::StartActivity(CmAgentTraceProvider::NotifyResuming *this)
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
    tlgWriteTransfer_EventWriteTransfer(v2, (unsigned __int8 *)&byte_180044A5F, (const GUID *)(v3 + 8), v4, 4u, &v7);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((CmAgentTraceProvider::NotifyResuming *)((char *)this + 288));
}

```

## disassembly

```asm
0x18001bfb4  mov     [rsp+arg_8], rbx
0x18001bfb9  push    rdi
0x18001bfba  sub     rsp, 90h
0x18001bfc1  mov     rax, cs:__security_cookie
0x18001bfc8  xor     rax, rsp
0x18001bfcb  mov     [rsp+98h+var_18], rax
0x18001bfd3  mov     rbx, rcx
0x18001bfd6  call    ?zInternalStart@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001bfdb  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001bfe0  mov     rdi, [rax+8]
0x18001bfe4  mov     eax, [rdi]
0x18001bfe6  cmp     eax, 5
0x18001bfe9  jbe     loc_18001C0AA
0x18001bfef  mov     rcx, [rdi+18h]
0x18001bff3  mov     rax, [rdi+10h]
0x18001bff7  mov     rdx, 400000000000h
0x18001c001  test    rdx, rax
0x18001c004  jz      loc_18001C0AA
0x18001c00a  mov     rax, rcx
0x18001c00d  and     rax, rdx
0x18001c010  cmp     rax, rcx
0x18001c013  jnz     loc_18001C0AA
0x18001c019  call    cs:__imp_GetCurrentThreadId
0x18001c020  nop     dword ptr [rax+rax+00h]
0x18001c025  mov     [rsp+98h+var_68], eax
0x18001c029  mov     [rsp+98h+var_60], 1000000h
0x18001c032  mov     r8, [rbx+110h]
0x18001c039  cmp     byte ptr [r8+4], 0
0x18001c03e  jz      short loc_18001C05F
0x18001c040  lea     r9, [r8+18h]
0x18001c044  cmp     dword ptr [r9], 0
0x18001c048  jnz     short loc_18001C062
0x18001c04a  cmp     dword ptr [r9+4], 0
0x18001c04f  jnz     short loc_18001C062
0x18001c051  cmp     dword ptr [r9+8], 0
0x18001c056  jnz     short loc_18001C062
0x18001c058  cmp     dword ptr [r9+0Ch], 0
0x18001c05d  jnz     short loc_18001C062
0x18001c05f  xor     r9d, r9d
0x18001c062  lea     rax, [rsp+98h+var_68]
0x18001c067  mov     [rsp+98h+var_28], rax
0x18001c06c  mov     ecx, 4
0x18001c071  mov     [rsp+98h+var_20], rcx
0x18001c076  lea     rax, [rsp+98h+var_60]
0x18001c07b  mov     [rsp+98h+var_38], rax
0x18001c080  mov     [rsp+98h+var_30], 8
0x18001c089  add     r8, 8
0x18001c08d  lea     rax, [rsp+98h+var_58]
0x18001c092  mov     [rsp+98h+var_70], rax
0x18001c097  mov     [rsp+98h+var_78], ecx
0x18001c09b  lea     rdx, byte_180044A5F
0x18001c0a2  mov     rcx, rdi
0x18001c0a5  call    _tlgWriteTransfer_EventWriteTransfer
0x18001c0aa  lea     rcx, [rbx+120h]; this
0x18001c0b1  cmp     dword ptr [rcx+18h], 0
0x18001c0b5  jnz     short loc_18001C0BD
0x18001c0b7  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18001c0bc  nop
0x18001c0bd  mov     rcx, [rsp+98h+var_18]
0x18001c0c5  xor     rcx, rsp; StackCookie
0x18001c0c8  call    __security_check_cookie
0x18001c0cd  mov     rbx, [rsp+98h+arg_8]
0x18001c0d5  add     rsp, 90h
0x18001c0dc  pop     rdi
0x18001c0dd  retn
```
