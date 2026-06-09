# CExec::Diagnostics::TraceProvider::ExecuteProcess::StartActivity(void)

- ea: `0x1400197f4`
- end: `0x140019942`
- name: `?StartActivity@ExecuteProcess@TraceProvider@Diagnostics@CExec@@QEAAXXZ`
- size: `334`
- prototype: `void __fastcall(CExec::Diagnostics::TraceProvider::ExecuteProcess *__hidden this)`
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
- `0x1400197f4`
- `0x14001ae44`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001984e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001990f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001984e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001990f`

## pseudocode

```c
void __fastcall CExec::Diagnostics::TraceProvider::ExecuteProcess::StartActivity(
        CExec::Diagnostics::TraceProvider::ExecuteProcess *this)
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
        tlgWriteTransfer_EventWriteTransfer((int)v4, (int)&byte_140029EC9, v6 + 8, v7, 4u, &v12);
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
0x1400197f4  mov     [rsp+arg_8], rbx
0x1400197f9  push    rdi
0x1400197fa  sub     rsp, 90h
0x140019801  mov     rax, cs:__security_cookie
0x140019808  xor     rax, rsp
0x14001980b  mov     [rsp+98h+var_18], rax
0x140019813  mov     rbx, rcx
0x140019816  call    ?zInternalStart@?$ActivityBase@VTraceProvider@Diagnostics@CExec@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x14001981b  call    ?Provider@TraceProvider@Diagnostics@CExec@@SAPEBU_tlgProvider_t@@XZ; CExec::Diagnostics::TraceProvider::Provider(void)
0x140019820  mov     rdi, rax
0x140019823  mov     edx, [rax]
0x140019825  cmp     edx, 4
0x140019828  jbe     loc_1400198DC
0x14001982e  mov     rax, [rax+18h]
0x140019832  mov     rcx, [rdi+10h]
0x140019836  test    cl, 2
0x140019839  jz      loc_1400198DC
0x14001983f  mov     rcx, rax
0x140019842  and     ecx, 2
0x140019845  cmp     rcx, rax
0x140019848  jnz     loc_1400198DC
0x14001984e  call    cs:__imp_GetCurrentThreadId
0x140019854  mov     [rsp+98h+var_68], eax
0x140019858  mov     [rsp+98h+var_60], 0
0x140019861  mov     r8, [rbx+110h]
0x140019868  cmp     byte ptr [r8+4], 0
0x14001986d  jz      short loc_14001988E
0x14001986f  lea     r9, [r8+18h]
0x140019873  cmp     dword ptr [r9], 0
0x140019877  jnz     short loc_140019891
0x140019879  cmp     dword ptr [r9+4], 0
0x14001987e  jnz     short loc_140019891
0x140019880  cmp     dword ptr [r9+8], 0
0x140019885  jnz     short loc_140019891
0x140019887  cmp     dword ptr [r9+0Ch], 0
0x14001988c  jnz     short loc_140019891
0x14001988e  xor     r9d, r9d; int
0x140019891  lea     rax, [rsp+98h+var_68]
0x140019896  mov     [rsp+98h+var_28], rax
0x14001989b  mov     [rsp+98h+var_20], 4
0x1400198a4  lea     rax, [rsp+98h+var_60]
0x1400198a9  mov     [rsp+98h+var_38], rax
0x1400198ae  mov     [rsp+98h+var_30], 8
0x1400198b7  add     r8, 8; int
0x1400198bb  lea     rax, [rsp+98h+var_58]
0x1400198c0  mov     [rsp+98h+var_70], rax; PEVENT_DATA_DESCRIPTOR
0x1400198c5  mov     [rsp+98h+var_78], 4; ULONG
0x1400198cd  lea     rdx, byte_140029EC9; int
0x1400198d4  mov     rcx, rdi; int
0x1400198d7  call    _tlgWriteTransfer_EventWriteTransfer
0x1400198dc  cmp     dword ptr [rbx+138h], 0
0x1400198e3  jnz     short loc_140019921
0x1400198e5  add     rbx, 120h
0x1400198ec  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1400198f4  jz      short loc_14001991A
0x1400198f6  mov     dl, 1
0x1400198f8  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1400198fd  mov     [rbx], rax
0x140019900  test    rax, rax
0x140019903  jz      short loc_140019921
0x140019905  mov     rcx, [rax]
0x140019908  mov     [rbx+10h], rcx
0x14001990c  mov     [rax], rbx
0x14001990f  call    cs:__imp_GetCurrentThreadId
0x140019915  mov     [rbx+18h], eax
0x140019918  jmp     short loc_140019921
0x14001991a  mov     qword ptr [rbx], 0
0x140019921  mov     rcx, [rsp+98h+var_18]
0x140019929  xor     rcx, rsp; StackCookie
0x14001992c  call    __security_check_cookie
0x140019931  mov     rbx, [rsp+98h+arg_8]
0x140019939  add     rsp, 90h
0x140019940  pop     rdi
0x140019941  retn
```
