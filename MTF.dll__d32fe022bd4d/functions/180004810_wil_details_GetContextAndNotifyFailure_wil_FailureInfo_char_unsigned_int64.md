# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004810`
- end: `0x180004957`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `327`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180004810`
- `0x180004ef0`
- `0x180004fd4`
- `0x180006568`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000483a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800048fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000483a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800048fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180004810  push    rbx
0x180004812  push    rbp
0x180004813  push    rsi
0x180004814  push    rdi
0x180004815  push    r14
0x180004817  sub     rsp, 20h
0x18000481b  mov     r14, r8
0x18000481e  mov     rsi, rdx
0x180004821  mov     rdi, rcx
0x180004824  mov     byte ptr [rdx], 0
0x180004827  xor     bpl, bpl
0x18000482a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004831  test    rbx, rbx
0x180004834  jz      loc_1800048D0
0x18000483a  call    cs:__imp_GetCurrentThreadId
0x180004840  mov     r9d, eax
0x180004843  mov     r8d, eax
0x180004846  shr     r8, 2
0x18000484a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004854  mul     r8
0x180004857  shr     rdx, 3
0x18000485b  lea     rcx, [rdx+rdx*4]
0x18000485f  add     rcx, rcx
0x180004862  sub     r8, rcx
0x180004865  mov     rbx, [rbx+r8*8]
0x180004869  jmp     short loc_180004874
0x18000486b  cmp     [rbx], r9d
0x18000486e  jz      short loc_1800048EB
0x180004870  mov     rbx, [rbx+8]
0x180004874  test    rbx, rbx
0x180004877  jnz     short loc_18000486B
0x180004879  test    rbx, rbx
0x18000487c  jz      short loc_1800048D0
0x18000487e  cmp     qword ptr [rbx], 0
0x180004882  jz      short loc_1800048D0
0x180004884  mov     [rsi], bpl
0x180004887  mov     r9, r14; unsigned __int64
0x18000488a  mov     r8, rsi; char *
0x18000488d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004890  mov     rcx, rdi; struct wil::FailureInfo *
0x180004893  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004898  test    al, al
0x18000489a  jz      short loc_1800048A0
0x18000489c  mov     [rdi+48h], rsi
0x1800048a0  mov     rbx, [rbx]
0x1800048a3  mov     al, [rbx+28h]
0x1800048a6  mov     byte ptr [rbx+28h], 1
0x1800048aa  test    al, al
0x1800048ac  jnz     short loc_1800048C7
0x1800048ae  mov     rcx, [rbx+8]
0x1800048b2  mov     rax, [rcx]
0x1800048b5  mov     rdx, rdi
0x1800048b8  mov     rax, [rax]
0x1800048bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048c0  or      bpl, al
0x1800048c3  mov     byte ptr [rbx+28h], 0
0x1800048c7  mov     rbx, [rbx+10h]
0x1800048cb  test    rbx, rbx
0x1800048ce  jnz     short loc_1800048A3
0x1800048d0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800048d7  test    rax, rax
0x1800048da  jz      short loc_1800048FC
0x1800048dc  test    bpl, bpl
0x1800048df  jnz     short loc_1800048F1
0x1800048e1  test    byte ptr [rdi+4], 2
0x1800048e5  jnz     short loc_1800048F1
0x1800048e7  xor     ecx, ecx
0x1800048e9  jmp     short loc_1800048F3
0x1800048eb  add     rbx, 10h
0x1800048ef  jmp     short loc_180004879
0x1800048f1  mov     cl, 1
0x1800048f3  mov     rdx, rdi
0x1800048f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048fb  nop
0x1800048fc  call    cs:__imp_GetCurrentThreadId
0x180004902  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004908  cmp     ecx, eax
0x18000490a  jz      short loc_18000494C
0x18000490c  mov     ecx, 1
0x180004911  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004919  inc     ecx; this
0x18000491b  cmp     ecx, 4
0x18000491e  jge     short loc_180004945
0x180004920  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004926  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000492b  test    rax, rax
0x18000492e  jz      short loc_18000493B
0x180004930  mov     rdx, rdi; struct wil::FailureInfo *
0x180004933  mov     rcx, rax; this
0x180004936  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x18000493b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004945  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000494c  add     rsp, 20h
0x180004950  pop     r14
0x180004952  pop     rdi
0x180004953  pop     rsi
0x180004954  pop     rbp
0x180004955  pop     rbx
0x180004956  retn
```
