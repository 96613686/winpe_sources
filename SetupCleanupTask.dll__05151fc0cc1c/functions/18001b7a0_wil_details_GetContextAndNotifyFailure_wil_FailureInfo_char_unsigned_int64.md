# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18001b7a0`
- end: `0x18001b8e6`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `326`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18001b7a0`
- `0x18001c398`
- `0x18001c47c`
- `0x1800223ec`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b7ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b88b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b7ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b88b`

## pseudocode

```c
void __fastcall wil::details::GetContextAndNotifyFailure(unsigned __int64 this, struct wil::FailureInfo *a2, char *a3)
{
  char v3; // bp
  __int64 v4; // rbx
  wil::details *v7; // rdi
  unsigned __int64 CurrentThreadId; // r9
  __int64 i; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v10; // rbx
  char v11; // al
  DWORD v12; // eax
  bool v13; // dl
  wil::details_abi *v14; // rcx
  wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax

  *(_BYTE *)a2 = 0;
  v3 = 0;
  v4 = wil::details::g_pThreadFailureCallbacks;
  v7 = (wil::details *)this;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    this = 10 * ((CurrentThreadId >> 2) / 0xA);
    for ( i = *(_QWORD *)(v4 + 8 * ((CurrentThreadId >> 2) % 0xA)); i; i = *(_QWORD *)(i + 8) )
    {
      if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
      {
        i += 16;
        break;
      }
    }
    if ( i && *(_QWORD *)i )
    {
      *(_BYTE *)a2 = 0;
      if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(
             v7,
             *(struct wil::details::ThreadFailureCallbackHolder **)i,
             (char *)a2,
             (unsigned __int64)a3) )
      {
        *((_QWORD *)v7 + 9) = a2;
      }
      v10 = *(struct wil::details::ThreadFailureCallbackHolder **)i;
      do
      {
        v11 = *((_BYTE *)v10 + 40);
        *((_BYTE *)v10 + 40) = 1;
        if ( !v11 )
        {
          v3 |= (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v10 + 1))(*((_QWORD *)v10 + 1), v7);
          *((_BYTE *)v10 + 40) = 0;
        }
        v10 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v10 + 2);
      }
      while ( v10 );
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( v3 || (*((_BYTE *)v7 + 4) & 2) != 0 )
      LOBYTE(this) = 1;
    else
      this = 0;
    wil::details::g_pfnTelemetryCallback(this, v7);
  }
  v12 = GetCurrentThreadId();
  if ( `wil::SetLastError'::`2'::lastThread != v12 )
  {
    v14 = (wil::details_abi *)(unsigned int)_InterlockedIncrement(&`wil::SetLastError'::`5'::depth);
    if ( (int)v14 < 4 )
    {
      `wil::SetLastError'::`2'::lastThread = v12;
      ThreadLocalDataCache = wil::details_abi::GetThreadLocalDataCache(v14, v13);
      if ( ThreadLocalDataCache )
        wil::details_abi::ThreadLocalData::SetLastError(ThreadLocalDataCache, v7);
      `wil::SetLastError'::`2'::lastThread = 0;
    }
    _InterlockedDecrement(&`wil::SetLastError'::`5'::depth);
  }
}

```

## disassembly

```asm
0x18001b7a0  push    rbx
0x18001b7a2  push    rbp
0x18001b7a3  push    rsi
0x18001b7a4  push    rdi
0x18001b7a5  push    r14
0x18001b7a7  sub     rsp, 20h
0x18001b7ab  mov     byte ptr [rdx], 0
0x18001b7ae  xor     bpl, bpl
0x18001b7b1  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001b7b8  mov     r14, r8
0x18001b7bb  mov     rsi, rdx
0x18001b7be  mov     rdi, rcx
0x18001b7c1  test    rbx, rbx
0x18001b7c4  jz      loc_18001B860
0x18001b7ca  call    cs:__imp_GetCurrentThreadId
0x18001b7d0  mov     r8d, eax
0x18001b7d3  mov     r9d, eax
0x18001b7d6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001b7e0  shr     r8, 2
0x18001b7e4  mul     r8
0x18001b7e7  shr     rdx, 3
0x18001b7eb  lea     rcx, [rdx+rdx*4]
0x18001b7ef  add     rcx, rcx
0x18001b7f2  sub     r8, rcx
0x18001b7f5  mov     rbx, [rbx+r8*8]
0x18001b7f9  jmp     short loc_18001B804
0x18001b7fb  cmp     [rbx], r9d
0x18001b7fe  jz      short loc_18001B87B
0x18001b800  mov     rbx, [rbx+8]
0x18001b804  test    rbx, rbx
0x18001b807  jnz     short loc_18001B7FB
0x18001b809  test    rbx, rbx
0x18001b80c  jz      short loc_18001B860
0x18001b80e  cmp     qword ptr [rbx], 0
0x18001b812  jz      short loc_18001B860
0x18001b814  mov     [rsi], bpl
0x18001b817  mov     r9, r14; unsigned __int64
0x18001b81a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18001b81d  mov     r8, rsi; char *
0x18001b820  mov     rcx, rdi; struct wil::FailureInfo *
0x18001b823  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18001b828  test    al, al
0x18001b82a  jz      short loc_18001B830
0x18001b82c  mov     [rdi+48h], rsi
0x18001b830  mov     rbx, [rbx]
0x18001b833  mov     al, [rbx+28h]
0x18001b836  mov     byte ptr [rbx+28h], 1
0x18001b83a  test    al, al
0x18001b83c  jnz     short loc_18001B857
0x18001b83e  mov     rcx, [rbx+8]
0x18001b842  mov     rdx, rdi
0x18001b845  mov     rax, [rcx]
0x18001b848  mov     rax, [rax]
0x18001b84b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b850  or      bpl, al
0x18001b853  mov     byte ptr [rbx+28h], 0
0x18001b857  mov     rbx, [rbx+10h]
0x18001b85b  test    rbx, rbx
0x18001b85e  jnz     short loc_18001B833
0x18001b860  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18001b867  test    rax, rax
0x18001b86a  jz      short loc_18001B88B
0x18001b86c  test    bpl, bpl
0x18001b86f  jnz     short loc_18001B881
0x18001b871  test    byte ptr [rdi+4], 2
0x18001b875  jnz     short loc_18001B881
0x18001b877  xor     ecx, ecx
0x18001b879  jmp     short loc_18001B883
0x18001b87b  add     rbx, 10h
0x18001b87f  jmp     short loc_18001B809
0x18001b881  mov     cl, 1
0x18001b883  mov     rdx, rdi
0x18001b886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b88b  call    cs:__imp_GetCurrentThreadId
0x18001b891  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18001b897  cmp     ecx, eax
0x18001b899  jz      short loc_18001B8DB
0x18001b89b  mov     ecx, 1
0x18001b8a0  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18001b8a8  inc     ecx; this
0x18001b8aa  cmp     ecx, 4
0x18001b8ad  jge     short loc_18001B8D4
0x18001b8af  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18001b8b5  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18001b8ba  test    rax, rax
0x18001b8bd  jz      short loc_18001B8CA
0x18001b8bf  mov     rdx, rdi; struct wil::FailureInfo *
0x18001b8c2  mov     rcx, rax; this
0x18001b8c5  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x18001b8ca  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18001b8d4  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18001b8db  add     rsp, 20h
0x18001b8df  pop     r14
0x18001b8e1  pop     rdi
0x18001b8e2  pop     rsi
0x18001b8e3  pop     rbp
0x18001b8e4  pop     rbx
0x18001b8e5  retn
```
