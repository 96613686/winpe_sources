# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800052e0`
- end: `0x180005427`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `327`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800052e0`
- `0x180005a8c`
- `0x180005b70`
- `0x18000902c`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000530a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800053cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000530a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800053cc`

## pseudocode

```c
void __fastcall wil::details::GetContextAndNotifyFailure(unsigned __int64 this, struct wil::FailureInfo *a2, char *a3)
{
  wil::details *v5; // rdi
  char v6; // bp
  __int64 v7; // rbx
  unsigned __int64 CurrentThreadId; // r9
  __int64 i; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v10; // rbx
  char v11; // al
  DWORD v12; // eax
  bool v13; // dl
  wil::details_abi *v14; // rcx
  wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax

  v5 = (wil::details *)this;
  *(_BYTE *)a2 = 0;
  v6 = 0;
  v7 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    this = 10 * ((CurrentThreadId >> 2) / 0xA);
    for ( i = *(_QWORD *)(v7 + 8 * ((CurrentThreadId >> 2) % 0xA)); i; i = *(_QWORD *)(i + 8) )
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
             v5,
             *(struct wil::details::ThreadFailureCallbackHolder **)i,
             (char *)a2,
             (unsigned __int64)a3) )
      {
        *((_QWORD *)v5 + 9) = a2;
      }
      v10 = *(struct wil::details::ThreadFailureCallbackHolder **)i;
      do
      {
        v11 = *((_BYTE *)v10 + 40);
        *((_BYTE *)v10 + 40) = 1;
        if ( !v11 )
        {
          v6 |= (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v10 + 1))(*((_QWORD *)v10 + 1), v5);
          *((_BYTE *)v10 + 40) = 0;
        }
        v10 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v10 + 2);
      }
      while ( v10 );
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( v6 || (*((_BYTE *)v5 + 4) & 2) != 0 )
      LOBYTE(this) = 1;
    else
      this = 0;
    wil::details::g_pfnTelemetryCallback(this, v5);
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
        wil::details_abi::ThreadLocalData::SetLastError(ThreadLocalDataCache, v5);
      `wil::SetLastError'::`2'::lastThread = 0;
    }
    _InterlockedDecrement(&`wil::SetLastError'::`5'::depth);
  }
}

```

## disassembly

```asm
0x1800052e0  push    rbx
0x1800052e2  push    rbp
0x1800052e3  push    rsi
0x1800052e4  push    rdi
0x1800052e5  push    r14
0x1800052e7  sub     rsp, 20h
0x1800052eb  mov     r14, r8
0x1800052ee  mov     rsi, rdx
0x1800052f1  mov     rdi, rcx
0x1800052f4  mov     byte ptr [rdx], 0
0x1800052f7  xor     bpl, bpl
0x1800052fa  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005301  test    rbx, rbx
0x180005304  jz      loc_1800053A0
0x18000530a  call    cs:__imp_GetCurrentThreadId
0x180005310  mov     r9d, eax
0x180005313  mov     r8d, eax
0x180005316  shr     r8, 2
0x18000531a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005324  mul     r8
0x180005327  shr     rdx, 3
0x18000532b  lea     rcx, [rdx+rdx*4]
0x18000532f  add     rcx, rcx
0x180005332  sub     r8, rcx
0x180005335  mov     rbx, [rbx+r8*8]
0x180005339  jmp     short loc_180005344
0x18000533b  cmp     [rbx], r9d
0x18000533e  jz      short loc_1800053BB
0x180005340  mov     rbx, [rbx+8]
0x180005344  test    rbx, rbx
0x180005347  jnz     short loc_18000533B
0x180005349  test    rbx, rbx
0x18000534c  jz      short loc_1800053A0
0x18000534e  cmp     qword ptr [rbx], 0
0x180005352  jz      short loc_1800053A0
0x180005354  mov     [rsi], bpl
0x180005357  mov     r9, r14; unsigned __int64
0x18000535a  mov     r8, rsi; char *
0x18000535d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180005360  mov     rcx, rdi; struct wil::FailureInfo *
0x180005363  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005368  test    al, al
0x18000536a  jz      short loc_180005370
0x18000536c  mov     [rdi+48h], rsi
0x180005370  mov     rbx, [rbx]
0x180005373  mov     al, [rbx+28h]
0x180005376  mov     byte ptr [rbx+28h], 1
0x18000537a  test    al, al
0x18000537c  jnz     short loc_180005397
0x18000537e  mov     rcx, [rbx+8]
0x180005382  mov     rax, [rcx]
0x180005385  mov     rdx, rdi
0x180005388  mov     rax, [rax]
0x18000538b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005390  or      bpl, al
0x180005393  mov     byte ptr [rbx+28h], 0
0x180005397  mov     rbx, [rbx+10h]
0x18000539b  test    rbx, rbx
0x18000539e  jnz     short loc_180005373
0x1800053a0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800053a7  test    rax, rax
0x1800053aa  jz      short loc_1800053CC
0x1800053ac  test    bpl, bpl
0x1800053af  jnz     short loc_1800053C1
0x1800053b1  test    byte ptr [rdi+4], 2
0x1800053b5  jnz     short loc_1800053C1
0x1800053b7  xor     ecx, ecx
0x1800053b9  jmp     short loc_1800053C3
0x1800053bb  add     rbx, 10h
0x1800053bf  jmp     short loc_180005349
0x1800053c1  mov     cl, 1
0x1800053c3  mov     rdx, rdi
0x1800053c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053cb  nop
0x1800053cc  call    cs:__imp_GetCurrentThreadId
0x1800053d2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800053d8  cmp     ecx, eax
0x1800053da  jz      short loc_18000541C
0x1800053dc  mov     ecx, 1
0x1800053e1  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800053e9  inc     ecx; this
0x1800053eb  cmp     ecx, 4
0x1800053ee  jge     short loc_180005415
0x1800053f0  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800053f6  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800053fb  test    rax, rax
0x1800053fe  jz      short loc_18000540B
0x180005400  mov     rdx, rdi; struct wil::FailureInfo *
0x180005403  mov     rcx, rax; this
0x180005406  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x18000540b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005415  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000541c  add     rsp, 20h
0x180005420  pop     r14
0x180005422  pop     rdi
0x180005423  pop     rsi
0x180005424  pop     rbp
0x180005425  pop     rbx
0x180005426  retn
```
