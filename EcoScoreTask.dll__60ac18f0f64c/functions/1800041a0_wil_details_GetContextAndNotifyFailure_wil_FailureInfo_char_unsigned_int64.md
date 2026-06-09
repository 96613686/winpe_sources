# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800041a0`
- end: `0x1800042e6`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `326`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800041a0`
- `0x18000487c`
- `0x180004960`
- `0x1800063a8`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800041ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000428b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800041ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000428b`

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
0x1800041a0  push    rbx
0x1800041a2  push    rbp
0x1800041a3  push    rsi
0x1800041a4  push    rdi
0x1800041a5  push    r14
0x1800041a7  sub     rsp, 20h
0x1800041ab  mov     byte ptr [rdx], 0
0x1800041ae  xor     bpl, bpl
0x1800041b1  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800041b8  mov     r14, r8
0x1800041bb  mov     rsi, rdx
0x1800041be  mov     rdi, rcx
0x1800041c1  test    rbx, rbx
0x1800041c4  jz      loc_180004260
0x1800041ca  call    cs:__imp_GetCurrentThreadId
0x1800041d0  mov     r8d, eax
0x1800041d3  mov     r9d, eax
0x1800041d6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800041e0  shr     r8, 2
0x1800041e4  mul     r8
0x1800041e7  shr     rdx, 3
0x1800041eb  lea     rcx, [rdx+rdx*4]
0x1800041ef  add     rcx, rcx
0x1800041f2  sub     r8, rcx
0x1800041f5  mov     rbx, [rbx+r8*8]
0x1800041f9  jmp     short loc_180004204
0x1800041fb  cmp     [rbx], r9d
0x1800041fe  jz      short loc_18000427B
0x180004200  mov     rbx, [rbx+8]
0x180004204  test    rbx, rbx
0x180004207  jnz     short loc_1800041FB
0x180004209  test    rbx, rbx
0x18000420c  jz      short loc_180004260
0x18000420e  cmp     qword ptr [rbx], 0
0x180004212  jz      short loc_180004260
0x180004214  mov     [rsi], bpl
0x180004217  mov     r9, r14; unsigned __int64
0x18000421a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000421d  mov     r8, rsi; char *
0x180004220  mov     rcx, rdi; struct wil::FailureInfo *
0x180004223  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004228  test    al, al
0x18000422a  jz      short loc_180004230
0x18000422c  mov     [rdi+48h], rsi
0x180004230  mov     rbx, [rbx]
0x180004233  mov     al, [rbx+28h]
0x180004236  mov     byte ptr [rbx+28h], 1
0x18000423a  test    al, al
0x18000423c  jnz     short loc_180004257
0x18000423e  mov     rcx, [rbx+8]
0x180004242  mov     rdx, rdi
0x180004245  mov     rax, [rcx]
0x180004248  mov     rax, [rax]
0x18000424b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004250  or      bpl, al
0x180004253  mov     byte ptr [rbx+28h], 0
0x180004257  mov     rbx, [rbx+10h]
0x18000425b  test    rbx, rbx
0x18000425e  jnz     short loc_180004233
0x180004260  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004267  test    rax, rax
0x18000426a  jz      short loc_18000428B
0x18000426c  test    bpl, bpl
0x18000426f  jnz     short loc_180004281
0x180004271  test    byte ptr [rdi+4], 2
0x180004275  jnz     short loc_180004281
0x180004277  xor     ecx, ecx
0x180004279  jmp     short loc_180004283
0x18000427b  add     rbx, 10h
0x18000427f  jmp     short loc_180004209
0x180004281  mov     cl, 1
0x180004283  mov     rdx, rdi
0x180004286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000428b  call    cs:__imp_GetCurrentThreadId
0x180004291  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004297  cmp     ecx, eax
0x180004299  jz      short loc_1800042DB
0x18000429b  mov     ecx, 1
0x1800042a0  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800042a8  inc     ecx; this
0x1800042aa  cmp     ecx, 4
0x1800042ad  jge     short loc_1800042D4
0x1800042af  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800042b5  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800042ba  test    rax, rax
0x1800042bd  jz      short loc_1800042CA
0x1800042bf  mov     rdx, rdi; struct wil::FailureInfo *
0x1800042c2  mov     rcx, rax; this
0x1800042c5  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x1800042ca  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800042d4  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800042db  add     rsp, 20h
0x1800042df  pop     r14
0x1800042e1  pop     rdi
0x1800042e2  pop     rsi
0x1800042e3  pop     rbp
0x1800042e4  pop     rbx
0x1800042e5  retn
```
