# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x18000b520`
- end: `0x18000b660`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `320`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b4e0`
- `0x18001ef50`
- `0x1800371a4`
- `0x18003730c`

## callees

- `0x18000b520`
- `0x180019b68`
- `0x18002292c`
- `0x1800449fa`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b558`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b5d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b558`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b5d1`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  __int64 v2; // rsi
  DWORD CurrentThreadId; // edi
  unsigned __int64 v4; // r8
  __int64 v5; // r15
  __int64 v6; // rax
  volatile signed __int64 *v7; // r14
  _QWORD *v8; // rcx
  char *v9; // rax
  signed __int64 v10; // r8
  signed __int64 *v11; // rdx
  signed __int64 v12; // rax
  const struct wil::FailureInfo *v13; // rdx
  _BYTE v14[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    memset_0(v14, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v14, v13);
  }
  v2 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    v4 = CurrentThreadId % 0xAuLL;
    v5 = 8 * v4;
    v6 = *(_QWORD *)(8 * v4 + v2);
    v7 = (volatile signed __int64 *)(8 * v4 + v2);
    while ( v6 )
    {
      if ( *(_DWORD *)v6 == CurrentThreadId )
      {
        v8 = (_QWORD *)(v6 + 16);
        goto LABEL_8;
      }
      v6 = *(_QWORD *)(v6 + 8);
    }
    v9 = (char *)wil::details::ProcessHeapAlloc(0, 0x18u, v4);
    v10 = (signed __int64)v9;
    if ( v9 )
    {
      *(_DWORD *)v9 = CurrentThreadId;
      v8 = v9 + 16;
      *((_DWORD *)v9 + 1) = 0;
      *((_QWORD *)v9 + 1) = 0;
      *((_QWORD *)v9 + 2) = 0;
      v11 = (signed __int64 *)(v5 + v2);
      do
      {
        v12 = *v11;
        *(_QWORD *)(v10 + 8) = *v11;
      }
      while ( v12 != _InterlockedCompareExchange64(v7, v10, v12) );
    }
    else
    {
      v8 = 0;
    }
LABEL_8:
    *(_QWORD *)this = v8;
    if ( v8 )
    {
      *((_QWORD *)this + 2) = *v8;
      *v8 = this;
      *((_DWORD *)this + 6) = GetCurrentThreadId();
    }
  }
  else
  {
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x18000b520  mov     rax, rsp
0x18000b523  push    rbx
0x18000b524  sub     rsp, 0C0h
0x18000b52b  cmp     dword ptr [rcx+18h], 0
0x18000b52f  mov     rbx, rcx
0x18000b532  jnz     loc_18000B63A
0x18000b538  mov     [rax+8], rsi
0x18000b53c  mov     rsi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000b543  test    rsi, rsi
0x18000b546  jz      loc_18000B5F2
0x18000b54c  mov     [rax+10h], rdi
0x18000b550  mov     [rax+18h], r14
0x18000b554  mov     [rax+20h], r15
0x18000b558  call    cs:__imp_GetCurrentThreadId
0x18000b55f  nop     dword ptr [rax+rax+00h]
0x18000b564  mov     r8d, eax
0x18000b567  mov     edi, eax
0x18000b569  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000b573  mul     rdi
0x18000b576  shr     rdx, 3
0x18000b57a  lea     rcx, [rdx+rdx*4]
0x18000b57e  add     rcx, rcx
0x18000b581  sub     r8, rcx; unsigned __int64
0x18000b584  lea     r15, ds:0[r8*8]
0x18000b58c  mov     rax, [r15+rsi]
0x18000b590  lea     r14, [r15+rsi]
0x18000b594  test    rax, rax
0x18000b597  jz      short loc_18000B5F9
0x18000b599  cmp     [rax], edi
0x18000b59b  jz      short loc_18000B5A3
0x18000b59d  mov     rax, [rax+8]
0x18000b5a1  jmp     short loc_18000B594
0x18000b5a3  lea     rcx, [rax+10h]
0x18000b5a7  mov     r15, [rsp+0C8h+arg_18]
0x18000b5af  mov     r14, [rsp+0C8h+arg_10]
0x18000b5b7  mov     rdi, [rsp+0C8h+arg_8]
0x18000b5bf  mov     [rbx], rcx
0x18000b5c2  test    rcx, rcx
0x18000b5c5  jz      short loc_18000B5E0
0x18000b5c7  mov     rax, [rcx]
0x18000b5ca  mov     [rbx+10h], rax
0x18000b5ce  mov     [rcx], rbx
0x18000b5d1  call    cs:__imp_GetCurrentThreadId
0x18000b5d8  nop     dword ptr [rax+rax+00h]
0x18000b5dd  mov     [rbx+18h], eax
0x18000b5e0  mov     rsi, [rsp+0C8h+arg_0]
0x18000b5e8  add     rsp, 0C0h
0x18000b5ef  pop     rbx
0x18000b5f0  retn
0x18000b5f2  xor     edx, edx
0x18000b5f4  mov     [rcx], rdx
0x18000b5f7  jmp     short loc_18000B5E0
0x18000b5f9  mov     edx, 18h; dwBytes
0x18000b5fe  xor     ecx, ecx; dwFlags
0x18000b600  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000b605  mov     r8, rax
0x18000b608  test    rax, rax
0x18000b60b  jz      short loc_18000B657
0x18000b60d  mov     [rax], edi
0x18000b60f  lea     rcx, [r8+10h]
0x18000b613  xor     eax, eax
0x18000b615  xor     edx, edx
0x18000b617  mov     [r8+4], eax
0x18000b61b  mov     [r8+8], rdx
0x18000b61f  mov     [rcx], rdx
0x18000b622  lea     rdx, [r15+rsi]
0x18000b626  mov     rax, [rdx]
0x18000b629  mov     [r8+8], rax
0x18000b62d  lock cmpxchg [r14], r8
0x18000b632  jz      loc_18000B5A7
0x18000b638  jmp     short loc_18000B626
0x18000b63a  xor     edx, edx; Val
0x18000b63c  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000b641  mov     r8d, 98h; Size
0x18000b647  call    memset_0
0x18000b64c  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000b651  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000b657  xor     edx, edx
0x18000b659  mov     ecx, edx
0x18000b65b  jmp     loc_18000B5A7
```
