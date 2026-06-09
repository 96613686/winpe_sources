# CmAgentTraceProvider::ServiceStop::StartActivity(void)

- ea: `0x18000877c`
- end: `0x1800088a7`
- name: `?StartActivity@ServiceStop@CmAgentTraceProvider@@QEAAXXZ`
- size: `299`
- prototype: `void __fastcall(CmAgentTraceProvider::ServiceStop *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180007c30`

## callees

- `0x180001970`
- `0x180002140`
- `0x180006fcc`
- `0x18000877c`
- `0x1800088b0`
- `0x180009940`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800087e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800087e1`

## pseudocode

```c
void __fastcall CmAgentTraceProvider::ServiceStop::StartActivity(CmAgentTraceProvider::ServiceStop *this)
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
    tlgWriteTransfer_EventWriteTransfer(v2, (unsigned __int8 *)byte_1800431D3, (const GUID *)(v3 + 8), v4, 4u, &v7);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((CmAgentTraceProvider::ServiceStop *)((char *)this + 288));
}

```

## disassembly

```asm
0x18000877c  mov     [rsp+arg_8], rbx
0x180008781  push    rdi
0x180008782  sub     rsp, 90h
0x180008789  mov     rax, cs:__security_cookie
0x180008790  xor     rax, rsp
0x180008793  mov     [rsp+98h+var_18], rax
0x18000879b  mov     rbx, rcx
0x18000879e  call    ?zInternalStart@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800087a3  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x1800087a8  mov     rdi, [rax+8]
0x1800087ac  mov     eax, [rdi]
0x1800087ae  cmp     eax, 5
0x1800087b1  jbe     loc_180008872
0x1800087b7  mov     rcx, [rdi+18h]
0x1800087bb  mov     rax, [rdi+10h]
0x1800087bf  mov     rdx, 400000000000h
0x1800087c9  test    rdx, rax
0x1800087cc  jz      loc_180008872
0x1800087d2  mov     rax, rcx
0x1800087d5  and     rax, rdx
0x1800087d8  cmp     rax, rcx
0x1800087db  jnz     loc_180008872
0x1800087e1  call    cs:__imp_GetCurrentThreadId
0x1800087e8  nop     dword ptr [rax+rax+00h]
0x1800087ed  mov     [rsp+98h+var_68], eax
0x1800087f1  mov     [rsp+98h+var_60], 1000000h
0x1800087fa  mov     r8, [rbx+110h]
0x180008801  cmp     byte ptr [r8+4], 0
0x180008806  jz      short loc_180008827
0x180008808  lea     r9, [r8+18h]
0x18000880c  cmp     dword ptr [r9], 0
0x180008810  jnz     short loc_18000882A
0x180008812  cmp     dword ptr [r9+4], 0
0x180008817  jnz     short loc_18000882A
0x180008819  cmp     dword ptr [r9+8], 0
0x18000881e  jnz     short loc_18000882A
0x180008820  cmp     dword ptr [r9+0Ch], 0
0x180008825  jnz     short loc_18000882A
0x180008827  xor     r9d, r9d
0x18000882a  lea     rax, [rsp+98h+var_68]
0x18000882f  mov     [rsp+98h+var_28], rax
0x180008834  mov     ecx, 4
0x180008839  mov     [rsp+98h+var_20], rcx
0x18000883e  lea     rax, [rsp+98h+var_60]
0x180008843  mov     [rsp+98h+var_38], rax
0x180008848  mov     [rsp+98h+var_30], 8
0x180008851  add     r8, 8
0x180008855  lea     rax, [rsp+98h+var_58]
0x18000885a  mov     [rsp+98h+var_70], rax
0x18000885f  mov     [rsp+98h+var_78], ecx
0x180008863  lea     rdx, byte_1800431D3
0x18000886a  mov     rcx, rdi
0x18000886d  call    _tlgWriteTransfer_EventWriteTransfer
0x180008872  lea     rcx, [rbx+120h]; this
0x180008879  cmp     dword ptr [rcx+18h], 0
0x18000887d  jnz     short loc_180008885
0x18000887f  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180008884  nop
0x180008885  mov     rcx, [rsp+98h+var_18]
0x18000888d  xor     rcx, rsp; StackCookie
0x180008890  call    __security_check_cookie
0x180008895  mov     rbx, [rsp+98h+arg_8]
0x18000889d  add     rsp, 90h
0x1800088a4  pop     rdi
0x1800088a5  retn
```
