# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000d890`
- end: `0x18000d9d6`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `326`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000d890`
- `0x18000e758`
- `0x18000e83c`
- `0x18000f010`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d8ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d97b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d8ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d97b`

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
0x18000d890  push    rbx
0x18000d892  push    rbp
0x18000d893  push    rsi
0x18000d894  push    rdi
0x18000d895  push    r14
0x18000d897  sub     rsp, 20h
0x18000d89b  mov     byte ptr [rdx], 0
0x18000d89e  xor     bpl, bpl
0x18000d8a1  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000d8a8  mov     r14, r8
0x18000d8ab  mov     rsi, rdx
0x18000d8ae  mov     rdi, rcx
0x18000d8b1  test    rbx, rbx
0x18000d8b4  jz      loc_18000D950
0x18000d8ba  call    cs:__imp_GetCurrentThreadId
0x18000d8c0  mov     r8d, eax
0x18000d8c3  mov     r9d, eax
0x18000d8c6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000d8d0  shr     r8, 2
0x18000d8d4  mul     r8
0x18000d8d7  shr     rdx, 3
0x18000d8db  lea     rcx, [rdx+rdx*4]
0x18000d8df  add     rcx, rcx
0x18000d8e2  sub     r8, rcx
0x18000d8e5  mov     rbx, [rbx+r8*8]
0x18000d8e9  jmp     short loc_18000D8F4
0x18000d8eb  cmp     [rbx], r9d
0x18000d8ee  jz      short loc_18000D96B
0x18000d8f0  mov     rbx, [rbx+8]
0x18000d8f4  test    rbx, rbx
0x18000d8f7  jnz     short loc_18000D8EB
0x18000d8f9  test    rbx, rbx
0x18000d8fc  jz      short loc_18000D950
0x18000d8fe  cmp     qword ptr [rbx], 0
0x18000d902  jz      short loc_18000D950
0x18000d904  mov     [rsi], bpl
0x18000d907  mov     r9, r14; unsigned __int64
0x18000d90a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000d90d  mov     r8, rsi; char *
0x18000d910  mov     rcx, rdi; struct wil::FailureInfo *
0x18000d913  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000d918  test    al, al
0x18000d91a  jz      short loc_18000D920
0x18000d91c  mov     [rdi+48h], rsi
0x18000d920  mov     rbx, [rbx]
0x18000d923  mov     al, [rbx+28h]
0x18000d926  mov     byte ptr [rbx+28h], 1
0x18000d92a  test    al, al
0x18000d92c  jnz     short loc_18000D947
0x18000d92e  mov     rcx, [rbx+8]
0x18000d932  mov     rdx, rdi
0x18000d935  mov     rax, [rcx]
0x18000d938  mov     rax, [rax]
0x18000d93b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d940  or      bpl, al
0x18000d943  mov     byte ptr [rbx+28h], 0
0x18000d947  mov     rbx, [rbx+10h]
0x18000d94b  test    rbx, rbx
0x18000d94e  jnz     short loc_18000D923
0x18000d950  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000d957  test    rax, rax
0x18000d95a  jz      short loc_18000D97B
0x18000d95c  test    bpl, bpl
0x18000d95f  jnz     short loc_18000D971
0x18000d961  test    byte ptr [rdi+4], 2
0x18000d965  jnz     short loc_18000D971
0x18000d967  xor     ecx, ecx
0x18000d969  jmp     short loc_18000D973
0x18000d96b  add     rbx, 10h
0x18000d96f  jmp     short loc_18000D8F9
0x18000d971  mov     cl, 1
0x18000d973  mov     rdx, rdi
0x18000d976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d97b  call    cs:__imp_GetCurrentThreadId
0x18000d981  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000d987  cmp     ecx, eax
0x18000d989  jz      short loc_18000D9CB
0x18000d98b  mov     ecx, 1
0x18000d990  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000d998  inc     ecx; this
0x18000d99a  cmp     ecx, 4
0x18000d99d  jge     short loc_18000D9C4
0x18000d99f  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000d9a5  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000d9aa  test    rax, rax
0x18000d9ad  jz      short loc_18000D9BA
0x18000d9af  mov     rdx, rdi; struct wil::FailureInfo *
0x18000d9b2  mov     rcx, rax; this
0x18000d9b5  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x18000d9ba  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000d9c4  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000d9cb  add     rsp, 20h
0x18000d9cf  pop     r14
0x18000d9d1  pop     rdi
0x18000d9d2  pop     rsi
0x18000d9d3  pop     rbp
0x18000d9d4  pop     rbx
0x18000d9d5  retn
```
