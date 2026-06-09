# CmAgentTraceProvider::FirstUserLogon::StartActivity(void)

- ea: `0x180022f5c`
- end: `0x180023087`
- name: `?StartActivity@FirstUserLogon@CmAgentTraceProvider@@QEAAXXZ`
- size: `299`
- prototype: `void __fastcall(CmAgentTraceProvider::FirstUserLogon *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180022d50`

## callees

- `0x180001970`
- `0x180002140`
- `0x180006fcc`
- `0x1800088b0`
- `0x180009940`
- `0x180022f5c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022fc1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022fc1`

## pseudocode

```c
void __fastcall CmAgentTraceProvider::FirstUserLogon::StartActivity(CmAgentTraceProvider::FirstUserLogon *this)
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
    tlgWriteTransfer_EventWriteTransfer(v2, byte_180044AA5, v3 + 8, v4, 4, v7);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((CmAgentTraceProvider::FirstUserLogon *)((char *)this + 288));
}

```

## disassembly

```asm
0x180022f5c  mov     [rsp+arg_8], rbx
0x180022f61  push    rdi
0x180022f62  sub     rsp, 90h
0x180022f69  mov     rax, cs:__security_cookie
0x180022f70  xor     rax, rsp
0x180022f73  mov     [rsp+98h+var_18], rax
0x180022f7b  mov     rbx, rcx
0x180022f7e  call    ?zInternalStart@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180022f83  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x180022f88  mov     rdi, [rax+8]
0x180022f8c  mov     eax, [rdi]
0x180022f8e  cmp     eax, 5
0x180022f91  jbe     loc_180023052
0x180022f97  mov     rcx, [rdi+18h]
0x180022f9b  mov     rax, [rdi+10h]
0x180022f9f  mov     rdx, 400000000000h
0x180022fa9  test    rdx, rax
0x180022fac  jz      loc_180023052
0x180022fb2  mov     rax, rcx
0x180022fb5  and     rax, rdx
0x180022fb8  cmp     rax, rcx
0x180022fbb  jnz     loc_180023052
0x180022fc1  call    cs:__imp_GetCurrentThreadId
0x180022fc8  nop     dword ptr [rax+rax+00h]
0x180022fcd  mov     [rsp+98h+var_68], eax
0x180022fd1  mov     [rsp+98h+var_60], 1000000h
0x180022fda  mov     r8, [rbx+110h]
0x180022fe1  cmp     byte ptr [r8+4], 0
0x180022fe6  jz      short loc_180023007
0x180022fe8  lea     r9, [r8+18h]
0x180022fec  cmp     dword ptr [r9], 0
0x180022ff0  jnz     short loc_18002300A
0x180022ff2  cmp     dword ptr [r9+4], 0
0x180022ff7  jnz     short loc_18002300A
0x180022ff9  cmp     dword ptr [r9+8], 0
0x180022ffe  jnz     short loc_18002300A
0x180023000  cmp     dword ptr [r9+0Ch], 0
0x180023005  jnz     short loc_18002300A
0x180023007  xor     r9d, r9d
0x18002300a  lea     rax, [rsp+98h+var_68]
0x18002300f  mov     [rsp+98h+var_28], rax
0x180023014  mov     ecx, 4
0x180023019  mov     [rsp+98h+var_20], rcx
0x18002301e  lea     rax, [rsp+98h+var_60]
0x180023023  mov     [rsp+98h+var_38], rax
0x180023028  mov     [rsp+98h+var_30], 8
0x180023031  add     r8, 8
0x180023035  lea     rax, [rsp+98h+var_58]
0x18002303a  mov     [rsp+98h+var_70], rax
0x18002303f  mov     [rsp+98h+var_78], ecx
0x180023043  lea     rdx, byte_180044AA5
0x18002304a  mov     rcx, rdi
0x18002304d  call    _tlgWriteTransfer_EventWriteTransfer
0x180023052  lea     rcx, [rbx+120h]; this
0x180023059  cmp     dword ptr [rcx+18h], 0
0x18002305d  jnz     short loc_180023065
0x18002305f  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180023064  nop
0x180023065  mov     rcx, [rsp+98h+var_18]
0x18002306d  xor     rcx, rsp; StackCookie
0x180023070  call    __security_check_cookie
0x180023075  mov     rbx, [rsp+98h+arg_8]
0x18002307d  add     rsp, 90h
0x180023084  pop     rdi
0x180023085  retn
```
