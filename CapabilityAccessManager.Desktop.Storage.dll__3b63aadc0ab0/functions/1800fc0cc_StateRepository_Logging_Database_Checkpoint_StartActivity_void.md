# StateRepository::Logging::Database::Checkpoint::StartActivity(void)

- ea: `0x1800fc0cc`
- end: `0x1800fc221`
- name: `?StartActivity@Checkpoint@Database@Logging@StateRepository@@QEAAXXZ`
- size: `341`
- prototype: `void __fastcall(StateRepository::Logging::Database::Checkpoint *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800f8b68`

## callees

- `0x18000163c`
- `0x180003060`
- `0x1800e8310`
- `0x1800fb134`
- `0x1800fc0cc`
- `0x1800ffadc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800fc130`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800fc1ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800fc130`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800fc1ee`

## pseudocode

```c
void __fastcall StateRepository::Logging::Database::Checkpoint::StartActivity(
        StateRepository::Logging::Database::Checkpoint *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // rcx
  const struct _tlgProvider_t *v4; // rdi
  __int64 v5; // rax
  DWORD CurrentThreadId; // eax
  __int64 v7; // r8
  __int64 v8; // r9
  char *v9; // rbx
  _QWORD *Local; // rax
  DWORD v11; // [rsp+30h] [rbp-68h] BYREF
  __int64 v12; // [rsp+38h] [rbp-60h] BYREF
  char v13[32]; // [rsp+40h] [rbp-58h] BYREF
  __int64 *v14; // [rsp+60h] [rbp-38h]
  __int64 v15; // [rsp+68h] [rbp-30h]
  DWORD *v16; // [rsp+70h] [rbp-28h]
  __int64 v17; // [rsp+78h] [rbp-20h]

  wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = StateRepository::Tracing::Service::Provider();
  v4 = v2;
  if ( *(_DWORD *)v2 > 5u )
  {
    v5 = *((_QWORD *)v2 + 3);
    if ( (*((_QWORD *)v4 + 2) & 0x200000000000LL) != 0 )
    {
      v3 = v5 & 0x200000000000LL;
      if ( (v5 & 0x200000000000LL) == v5 )
      {
        CurrentThreadId = GetCurrentThreadId();
        v7 = *((_QWORD *)this + 34);
        v11 = CurrentThreadId;
        v12 = 0;
        if ( !*(_BYTE *)(v7 + 4)
          || (v8 = v7 + 24, !*(_DWORD *)(v7 + 24))
          && !*(_DWORD *)(v7 + 28)
          && !*(_DWORD *)(v7 + 32)
          && !*(_DWORD *)(v7 + 36) )
        {
          v8 = 0;
        }
        v15 = 8;
        v17 = 4;
        v16 = &v11;
        v14 = &v12;
        tlgWriteTransfer_EventWriteTransfer(v4, qword_180129950, v7 + 8, v8, 4, v13);
      }
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v9 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v3,
                          1);
      *(_QWORD *)v9 = Local;
      if ( Local )
      {
        *((_QWORD *)v9 + 2) = *Local;
        *Local = v9;
        *((_DWORD *)v9 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v9 = 0;
    }
  }
}

```

## disassembly

```asm
0x1800fc0cc  mov     [rsp+arg_8], rbx
0x1800fc0d1  push    rdi
0x1800fc0d2  sub     rsp, 90h
0x1800fc0d9  mov     rax, cs:__security_cookie
0x1800fc0e0  xor     rax, rsp
0x1800fc0e3  mov     [rsp+98h+var_18], rax
0x1800fc0eb  mov     rbx, rcx
0x1800fc0ee  call    ?zInternalStart@?$ActivityBase@VService@Tracing@StateRepository@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800fc0f3  call    ?Provider@Service@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Service::Provider(void)
0x1800fc0f8  mov     rdi, rax
0x1800fc0fb  mov     edx, [rax]
0x1800fc0fd  cmp     edx, 5
0x1800fc100  jbe     loc_1800FC1BB
0x1800fc106  mov     rax, [rax+18h]
0x1800fc10a  mov     r8, 200000000000h
0x1800fc114  mov     rdx, [rdi+10h]
0x1800fc118  test    r8, rdx
0x1800fc11b  jz      loc_1800FC1BB
0x1800fc121  mov     rcx, rax
0x1800fc124  and     rcx, r8
0x1800fc127  cmp     rcx, rax
0x1800fc12a  jnz     loc_1800FC1BB
0x1800fc130  call    cs:__imp_GetCurrentThreadId
0x1800fc136  mov     r8, [rbx+110h]
0x1800fc13d  mov     [rsp+98h+var_68], eax
0x1800fc141  mov     [rsp+98h+var_60], 0
0x1800fc14a  cmp     byte ptr [r8+4], 0
0x1800fc14f  jz      short loc_1800FC170
0x1800fc151  lea     r9, [r8+18h]
0x1800fc155  cmp     dword ptr [r9], 0
0x1800fc159  jnz     short loc_1800FC173
0x1800fc15b  cmp     dword ptr [r9+4], 0
0x1800fc160  jnz     short loc_1800FC173
0x1800fc162  cmp     dword ptr [r9+8], 0
0x1800fc167  jnz     short loc_1800FC173
0x1800fc169  cmp     dword ptr [r9+0Ch], 0
0x1800fc16e  jnz     short loc_1800FC173
0x1800fc170  xor     r9d, r9d
0x1800fc173  mov     ecx, 4
0x1800fc178  mov     [rsp+98h+var_30], 8
0x1800fc181  lea     rax, [rsp+98h+var_68]
0x1800fc186  mov     [rsp+98h+var_20], rcx
0x1800fc18b  mov     [rsp+98h+var_28], rax
0x1800fc190  lea     rdx, qword_180129950
0x1800fc197  lea     rax, [rsp+98h+var_60]
0x1800fc19c  add     r8, 8
0x1800fc1a0  mov     [rsp+98h+var_38], rax
0x1800fc1a5  lea     rax, [rsp+98h+var_58]
0x1800fc1aa  mov     [rsp+98h+var_70], rax
0x1800fc1af  mov     [rsp+98h+var_78], ecx
0x1800fc1b3  mov     rcx, rdi
0x1800fc1b6  call    _tlgWriteTransfer_EventWriteTransfer
0x1800fc1bb  cmp     dword ptr [rbx+138h], 0
0x1800fc1c2  jnz     short loc_1800FC200
0x1800fc1c4  add     rbx, 120h
0x1800fc1cb  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800fc1d3  jz      short loc_1800FC1F9
0x1800fc1d5  mov     dl, 1
0x1800fc1d7  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800fc1dc  mov     [rbx], rax
0x1800fc1df  test    rax, rax
0x1800fc1e2  jz      short loc_1800FC200
0x1800fc1e4  mov     rcx, [rax]
0x1800fc1e7  mov     [rbx+10h], rcx
0x1800fc1eb  mov     [rax], rbx
0x1800fc1ee  call    cs:__imp_GetCurrentThreadId
0x1800fc1f4  mov     [rbx+18h], eax
0x1800fc1f7  jmp     short loc_1800FC200
0x1800fc1f9  mov     qword ptr [rbx], 0
0x1800fc200  mov     rcx, [rsp+98h+var_18]
0x1800fc208  xor     rcx, rsp; StackCookie
0x1800fc20b  call    __security_check_cookie
0x1800fc210  mov     rbx, [rsp+98h+arg_8]
0x1800fc218  add     rsp, 90h
0x1800fc21f  pop     rdi
0x1800fc220  retn
```
