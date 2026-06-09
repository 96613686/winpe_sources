# CExec::Diagnostics::TraceProvider::ExecuteProcess_LoadProfile::StartActivity(void)

- ea: `0x140019948`
- end: `0x140019a96`
- name: `?StartActivity@ExecuteProcess_LoadProfile@TraceProvider@Diagnostics@CExec@@QEAAXXZ`
- size: `334`
- prototype: `void __fastcall(CExec::Diagnostics::TraceProvider::ExecuteProcess_LoadProfile *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140016cc0`

## callees

- `0x140001a8c`
- `0x140002310`
- `0x140009b98`
- `0x140019190`
- `0x140019948`
- `0x14001ae44`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400199a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140019a63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400199a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140019a63`

## pseudocode

```c
void __fastcall CExec::Diagnostics::TraceProvider::ExecuteProcess_LoadProfile::StartActivity(
        CExec::Diagnostics::TraceProvider::ExecuteProcess_LoadProfile *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // rcx
  const struct _tlgProvider_t *v4; // rdi
  __int64 v5; // rax
  __int64 v6; // r8
  int v7; // r9d
  char *v8; // rbx
  _QWORD *Local; // rax
  DWORD CurrentThreadId; // [rsp+30h] [rbp-68h] BYREF
  __int64 v11; // [rsp+38h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+40h] [rbp-58h] BYREF
  __int64 *v13; // [rsp+60h] [rbp-38h]
  __int64 v14; // [rsp+68h] [rbp-30h]
  DWORD *p_CurrentThreadId; // [rsp+70h] [rbp-28h]
  __int64 v16; // [rsp+78h] [rbp-20h]

  wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = CExec::Diagnostics::TraceProvider::Provider();
  v4 = v2;
  if ( *(_DWORD *)v2 > 4u )
  {
    v5 = *((_QWORD *)v2 + 3);
    v3 = *((_QWORD *)v4 + 2);
    if ( (v3 & 2) != 0 )
    {
      v3 = v5 & 2;
      if ( v3 == v5 )
      {
        CurrentThreadId = GetCurrentThreadId();
        v11 = 0;
        v6 = *((_QWORD *)this + 34);
        if ( !*(_BYTE *)(v6 + 4)
          || (v7 = v6 + 24, !*(_DWORD *)(v6 + 24))
          && !*(_DWORD *)(v6 + 28)
          && !*(_DWORD *)(v6 + 32)
          && !*(_DWORD *)(v6 + 36) )
        {
          v7 = 0;
        }
        p_CurrentThreadId = &CurrentThreadId;
        v16 = 4;
        v13 = &v11;
        v14 = 8;
        tlgWriteTransfer_EventWriteTransfer((int)v4, (int)&byte_140029F0F, v6 + 8, v7, 4u, &v12);
      }
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v8 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v3,
                          1);
      *(_QWORD *)v8 = Local;
      if ( Local )
      {
        *((_QWORD *)v8 + 2) = *Local;
        *Local = v8;
        *((_DWORD *)v8 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v8 = 0;
    }
  }
}

```

## disassembly

```asm
0x140019948  mov     [rsp+arg_8], rbx
0x14001994d  push    rdi
0x14001994e  sub     rsp, 90h
0x140019955  mov     rax, cs:__security_cookie
0x14001995c  xor     rax, rsp
0x14001995f  mov     [rsp+98h+var_18], rax
0x140019967  mov     rbx, rcx
0x14001996a  call    ?zInternalStart@?$ActivityBase@VTraceProvider@Diagnostics@CExec@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x14001996f  call    ?Provider@TraceProvider@Diagnostics@CExec@@SAPEBU_tlgProvider_t@@XZ; CExec::Diagnostics::TraceProvider::Provider(void)
0x140019974  mov     rdi, rax
0x140019977  mov     edx, [rax]
0x140019979  cmp     edx, 4
0x14001997c  jbe     loc_140019A30
0x140019982  mov     rax, [rax+18h]
0x140019986  mov     rcx, [rdi+10h]
0x14001998a  test    cl, 2
0x14001998d  jz      loc_140019A30
0x140019993  mov     rcx, rax
0x140019996  and     ecx, 2
0x140019999  cmp     rcx, rax
0x14001999c  jnz     loc_140019A30
0x1400199a2  call    cs:__imp_GetCurrentThreadId
0x1400199a8  mov     [rsp+98h+var_68], eax
0x1400199ac  mov     [rsp+98h+var_60], 0
0x1400199b5  mov     r8, [rbx+110h]
0x1400199bc  cmp     byte ptr [r8+4], 0
0x1400199c1  jz      short loc_1400199E2
0x1400199c3  lea     r9, [r8+18h]
0x1400199c7  cmp     dword ptr [r9], 0
0x1400199cb  jnz     short loc_1400199E5
0x1400199cd  cmp     dword ptr [r9+4], 0
0x1400199d2  jnz     short loc_1400199E5
0x1400199d4  cmp     dword ptr [r9+8], 0
0x1400199d9  jnz     short loc_1400199E5
0x1400199db  cmp     dword ptr [r9+0Ch], 0
0x1400199e0  jnz     short loc_1400199E5
0x1400199e2  xor     r9d, r9d; int
0x1400199e5  lea     rax, [rsp+98h+var_68]
0x1400199ea  mov     [rsp+98h+var_28], rax
0x1400199ef  mov     [rsp+98h+var_20], 4
0x1400199f8  lea     rax, [rsp+98h+var_60]
0x1400199fd  mov     [rsp+98h+var_38], rax
0x140019a02  mov     [rsp+98h+var_30], 8
0x140019a0b  add     r8, 8; int
0x140019a0f  lea     rax, [rsp+98h+var_58]
0x140019a14  mov     [rsp+98h+var_70], rax; PEVENT_DATA_DESCRIPTOR
0x140019a19  mov     [rsp+98h+var_78], 4; ULONG
0x140019a21  lea     rdx, byte_140029F0F; int
0x140019a28  mov     rcx, rdi; int
0x140019a2b  call    _tlgWriteTransfer_EventWriteTransfer
0x140019a30  cmp     dword ptr [rbx+138h], 0
0x140019a37  jnz     short loc_140019A75
0x140019a39  add     rbx, 120h
0x140019a40  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140019a48  jz      short loc_140019A6E
0x140019a4a  mov     dl, 1
0x140019a4c  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x140019a51  mov     [rbx], rax
0x140019a54  test    rax, rax
0x140019a57  jz      short loc_140019A75
0x140019a59  mov     rcx, [rax]
0x140019a5c  mov     [rbx+10h], rcx
0x140019a60  mov     [rax], rbx
0x140019a63  call    cs:__imp_GetCurrentThreadId
0x140019a69  mov     [rbx+18h], eax
0x140019a6c  jmp     short loc_140019A75
0x140019a6e  mov     qword ptr [rbx], 0
0x140019a75  mov     rcx, [rsp+98h+var_18]
0x140019a7d  xor     rcx, rsp; StackCookie
0x140019a80  call    __security_check_cookie
0x140019a85  mov     rbx, [rsp+98h+arg_8]
0x140019a8d  add     rsp, 90h
0x140019a94  pop     rdi
0x140019a95  retn
```
