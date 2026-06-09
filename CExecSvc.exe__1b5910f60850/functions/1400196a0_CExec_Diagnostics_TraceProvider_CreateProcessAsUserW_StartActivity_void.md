# CExec::Diagnostics::TraceProvider::CreateProcessAsUserW::StartActivity(void)

- ea: `0x1400196a0`
- end: `0x1400197ee`
- name: `?StartActivity@CreateProcessAsUserW@TraceProvider@Diagnostics@CExec@@QEAAXXZ`
- size: `334`
- prototype: `void __fastcall(CExec::Diagnostics::TraceProvider::CreateProcessAsUserW *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140016cc0`

## callees

- `0x140001a8c`
- `0x140002310`
- `0x140009b98`
- `0x140019190`
- `0x1400196a0`
- `0x14001ae44`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400196fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400197bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400196fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400197bb`

## pseudocode

```c
void __fastcall CExec::Diagnostics::TraceProvider::CreateProcessAsUserW::StartActivity(
        CExec::Diagnostics::TraceProvider::CreateProcessAsUserW *this)
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
        tlgWriteTransfer_EventWriteTransfer((int)v4, (int)&word_14002A53A, v6 + 8, v7, 4u, &v12);
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
0x1400196a0  mov     [rsp+arg_8], rbx
0x1400196a5  push    rdi
0x1400196a6  sub     rsp, 90h
0x1400196ad  mov     rax, cs:__security_cookie
0x1400196b4  xor     rax, rsp
0x1400196b7  mov     [rsp+98h+var_18], rax
0x1400196bf  mov     rbx, rcx
0x1400196c2  call    ?zInternalStart@?$ActivityBase@VTraceProvider@Diagnostics@CExec@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1400196c7  call    ?Provider@TraceProvider@Diagnostics@CExec@@SAPEBU_tlgProvider_t@@XZ; CExec::Diagnostics::TraceProvider::Provider(void)
0x1400196cc  mov     rdi, rax
0x1400196cf  mov     edx, [rax]
0x1400196d1  cmp     edx, 4
0x1400196d4  jbe     loc_140019788
0x1400196da  mov     rax, [rax+18h]
0x1400196de  mov     rcx, [rdi+10h]
0x1400196e2  test    cl, 2
0x1400196e5  jz      loc_140019788
0x1400196eb  mov     rcx, rax
0x1400196ee  and     ecx, 2
0x1400196f1  cmp     rcx, rax
0x1400196f4  jnz     loc_140019788
0x1400196fa  call    cs:__imp_GetCurrentThreadId
0x140019700  mov     [rsp+98h+var_68], eax
0x140019704  mov     [rsp+98h+var_60], 0
0x14001970d  mov     r8, [rbx+110h]
0x140019714  cmp     byte ptr [r8+4], 0
0x140019719  jz      short loc_14001973A
0x14001971b  lea     r9, [r8+18h]
0x14001971f  cmp     dword ptr [r9], 0
0x140019723  jnz     short loc_14001973D
0x140019725  cmp     dword ptr [r9+4], 0
0x14001972a  jnz     short loc_14001973D
0x14001972c  cmp     dword ptr [r9+8], 0
0x140019731  jnz     short loc_14001973D
0x140019733  cmp     dword ptr [r9+0Ch], 0
0x140019738  jnz     short loc_14001973D
0x14001973a  xor     r9d, r9d; int
0x14001973d  lea     rax, [rsp+98h+var_68]
0x140019742  mov     [rsp+98h+var_28], rax
0x140019747  mov     [rsp+98h+var_20], 4
0x140019750  lea     rax, [rsp+98h+var_60]
0x140019755  mov     [rsp+98h+var_38], rax
0x14001975a  mov     [rsp+98h+var_30], 8
0x140019763  add     r8, 8; int
0x140019767  lea     rax, [rsp+98h+var_58]
0x14001976c  mov     [rsp+98h+var_70], rax; PEVENT_DATA_DESCRIPTOR
0x140019771  mov     [rsp+98h+var_78], 4; ULONG
0x140019779  lea     rdx, word_14002A53A; int
0x140019780  mov     rcx, rdi; int
0x140019783  call    _tlgWriteTransfer_EventWriteTransfer
0x140019788  cmp     dword ptr [rbx+138h], 0
0x14001978f  jnz     short loc_1400197CD
0x140019791  add     rbx, 120h
0x140019798  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1400197a0  jz      short loc_1400197C6
0x1400197a2  mov     dl, 1
0x1400197a4  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1400197a9  mov     [rbx], rax
0x1400197ac  test    rax, rax
0x1400197af  jz      short loc_1400197CD
0x1400197b1  mov     rcx, [rax]
0x1400197b4  mov     [rbx+10h], rcx
0x1400197b8  mov     [rax], rbx
0x1400197bb  call    cs:__imp_GetCurrentThreadId
0x1400197c1  mov     [rbx+18h], eax
0x1400197c4  jmp     short loc_1400197CD
0x1400197c6  mov     qword ptr [rbx], 0
0x1400197cd  mov     rcx, [rsp+98h+var_18]
0x1400197d5  xor     rcx, rsp; StackCookie
0x1400197d8  call    __security_check_cookie
0x1400197dd  mov     rbx, [rsp+98h+arg_8]
0x1400197e5  add     rsp, 90h
0x1400197ec  pop     rdi
0x1400197ed  retn
```
