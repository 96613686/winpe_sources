# CmAgentTraceProvider::WaitForSystemQuiesce::StartActivity(void)

- ea: `0x18001c9dc`
- end: `0x18001cb07`
- name: `?StartActivity@WaitForSystemQuiesce@CmAgentTraceProvider@@QEAAXXZ`
- size: `299`
- prototype: `void __fastcall(CmAgentTraceProvider::WaitForSystemQuiesce *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180020308`

## callees

- `0x180001970`
- `0x180002140`
- `0x180006fcc`
- `0x1800088b0`
- `0x180009940`
- `0x18001c9dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ca41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ca41`

## pseudocode

```c
void __fastcall CmAgentTraceProvider::WaitForSystemQuiesce::StartActivity(
        CmAgentTraceProvider::WaitForSystemQuiesce *this)
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
    tlgWriteTransfer_EventWriteTransfer(v2, (unsigned __int8 *)&dword_1800437AC, (const GUID *)(v3 + 8), v4, 4u, &v7);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((CmAgentTraceProvider::WaitForSystemQuiesce *)((char *)this + 288));
}

```

## disassembly

```asm
0x18001c9dc  mov     [rsp+arg_8], rbx
0x18001c9e1  push    rdi
0x18001c9e2  sub     rsp, 90h
0x18001c9e9  mov     rax, cs:__security_cookie
0x18001c9f0  xor     rax, rsp
0x18001c9f3  mov     [rsp+98h+var_18], rax
0x18001c9fb  mov     rbx, rcx
0x18001c9fe  call    ?zInternalStart@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001ca03  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001ca08  mov     rdi, [rax+8]
0x18001ca0c  mov     eax, [rdi]
0x18001ca0e  cmp     eax, 5
0x18001ca11  jbe     loc_18001CAD2
0x18001ca17  mov     rcx, [rdi+18h]
0x18001ca1b  mov     rax, [rdi+10h]
0x18001ca1f  mov     rdx, 400000000000h
0x18001ca29  test    rdx, rax
0x18001ca2c  jz      loc_18001CAD2
0x18001ca32  mov     rax, rcx
0x18001ca35  and     rax, rdx
0x18001ca38  cmp     rax, rcx
0x18001ca3b  jnz     loc_18001CAD2
0x18001ca41  call    cs:__imp_GetCurrentThreadId
0x18001ca48  nop     dword ptr [rax+rax+00h]
0x18001ca4d  mov     [rsp+98h+var_68], eax
0x18001ca51  mov     [rsp+98h+var_60], 1000000h
0x18001ca5a  mov     r8, [rbx+110h]
0x18001ca61  cmp     byte ptr [r8+4], 0
0x18001ca66  jz      short loc_18001CA87
0x18001ca68  lea     r9, [r8+18h]
0x18001ca6c  cmp     dword ptr [r9], 0
0x18001ca70  jnz     short loc_18001CA8A
0x18001ca72  cmp     dword ptr [r9+4], 0
0x18001ca77  jnz     short loc_18001CA8A
0x18001ca79  cmp     dword ptr [r9+8], 0
0x18001ca7e  jnz     short loc_18001CA8A
0x18001ca80  cmp     dword ptr [r9+0Ch], 0
0x18001ca85  jnz     short loc_18001CA8A
0x18001ca87  xor     r9d, r9d
0x18001ca8a  lea     rax, [rsp+98h+var_68]
0x18001ca8f  mov     [rsp+98h+var_28], rax
0x18001ca94  mov     ecx, 4
0x18001ca99  mov     [rsp+98h+var_20], rcx
0x18001ca9e  lea     rax, [rsp+98h+var_60]
0x18001caa3  mov     [rsp+98h+var_38], rax
0x18001caa8  mov     [rsp+98h+var_30], 8
0x18001cab1  add     r8, 8
0x18001cab5  lea     rax, [rsp+98h+var_58]
0x18001caba  mov     [rsp+98h+var_70], rax
0x18001cabf  mov     [rsp+98h+var_78], ecx
0x18001cac3  lea     rdx, dword_1800437AC
0x18001caca  mov     rcx, rdi
0x18001cacd  call    _tlgWriteTransfer_EventWriteTransfer
0x18001cad2  lea     rcx, [rbx+120h]; this
0x18001cad9  cmp     dword ptr [rcx+18h], 0
0x18001cadd  jnz     short loc_18001CAE5
0x18001cadf  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18001cae4  nop
0x18001cae5  mov     rcx, [rsp+98h+var_18]
0x18001caed  xor     rcx, rsp; StackCookie
0x18001caf0  call    __security_check_cookie
0x18001caf5  mov     rbx, [rsp+98h+arg_8]
0x18001cafd  add     rsp, 90h
0x18001cb04  pop     rdi
0x18001cb05  retn
```
