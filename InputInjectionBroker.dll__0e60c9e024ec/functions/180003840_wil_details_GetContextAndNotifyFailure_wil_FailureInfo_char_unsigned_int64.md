# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180003840`
- end: `0x180003987`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `327`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180003840`
- `0x180003e7c`
- `0x180003f60`
- `0x180004f28`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000386a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000392c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000386a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000392c`

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
0x180003840  push    rbx
0x180003842  push    rbp
0x180003843  push    rsi
0x180003844  push    rdi
0x180003845  push    r14
0x180003847  sub     rsp, 20h
0x18000384b  mov     r14, r8
0x18000384e  mov     rsi, rdx
0x180003851  mov     rdi, rcx
0x180003854  mov     byte ptr [rdx], 0
0x180003857  xor     bpl, bpl
0x18000385a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180003861  test    rbx, rbx
0x180003864  jz      loc_180003900
0x18000386a  call    cs:__imp_GetCurrentThreadId
0x180003870  mov     r9d, eax
0x180003873  mov     r8d, eax
0x180003876  shr     r8, 2
0x18000387a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003884  mul     r8
0x180003887  shr     rdx, 3
0x18000388b  lea     rcx, [rdx+rdx*4]
0x18000388f  add     rcx, rcx
0x180003892  sub     r8, rcx
0x180003895  mov     rbx, [rbx+r8*8]
0x180003899  jmp     short loc_1800038A4
0x18000389b  cmp     [rbx], r9d
0x18000389e  jz      short loc_18000391B
0x1800038a0  mov     rbx, [rbx+8]
0x1800038a4  test    rbx, rbx
0x1800038a7  jnz     short loc_18000389B
0x1800038a9  test    rbx, rbx
0x1800038ac  jz      short loc_180003900
0x1800038ae  cmp     qword ptr [rbx], 0
0x1800038b2  jz      short loc_180003900
0x1800038b4  mov     [rsi], bpl
0x1800038b7  mov     r9, r14; unsigned __int64
0x1800038ba  mov     r8, rsi; char *
0x1800038bd  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800038c0  mov     rcx, rdi; struct wil::FailureInfo *
0x1800038c3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800038c8  test    al, al
0x1800038ca  jz      short loc_1800038D0
0x1800038cc  mov     [rdi+48h], rsi
0x1800038d0  mov     rbx, [rbx]
0x1800038d3  mov     al, [rbx+28h]
0x1800038d6  mov     byte ptr [rbx+28h], 1
0x1800038da  test    al, al
0x1800038dc  jnz     short loc_1800038F7
0x1800038de  mov     rcx, [rbx+8]
0x1800038e2  mov     rax, [rcx]
0x1800038e5  mov     rdx, rdi
0x1800038e8  mov     rax, [rax]
0x1800038eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038f0  or      bpl, al
0x1800038f3  mov     byte ptr [rbx+28h], 0
0x1800038f7  mov     rbx, [rbx+10h]
0x1800038fb  test    rbx, rbx
0x1800038fe  jnz     short loc_1800038D3
0x180003900  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180003907  test    rax, rax
0x18000390a  jz      short loc_18000392C
0x18000390c  test    bpl, bpl
0x18000390f  jnz     short loc_180003921
0x180003911  test    byte ptr [rdi+4], 2
0x180003915  jnz     short loc_180003921
0x180003917  xor     ecx, ecx
0x180003919  jmp     short loc_180003923
0x18000391b  add     rbx, 10h
0x18000391f  jmp     short loc_1800038A9
0x180003921  mov     cl, 1
0x180003923  mov     rdx, rdi
0x180003926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000392b  nop
0x18000392c  call    cs:__imp_GetCurrentThreadId
0x180003932  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003938  cmp     ecx, eax
0x18000393a  jz      short loc_18000397C
0x18000393c  mov     ecx, 1
0x180003941  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180003949  inc     ecx; this
0x18000394b  cmp     ecx, 4
0x18000394e  jge     short loc_180003975
0x180003950  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003956  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000395b  test    rax, rax
0x18000395e  jz      short loc_18000396B
0x180003960  mov     rdx, rdi; struct wil::FailureInfo *
0x180003963  mov     rcx, rax; this
0x180003966  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x18000396b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003975  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000397c  add     rsp, 20h
0x180003980  pop     r14
0x180003982  pop     rdi
0x180003983  pop     rsi
0x180003984  pop     rbp
0x180003985  pop     rbx
0x180003986  retn
```
