# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004030`
- end: `0x180004177`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `327`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180004030`
- `0x1800046c0`
- `0x1800047a4`
- `0x180005ad4`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000405a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000411c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000405a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000411c`

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
0x180004030  push    rbx
0x180004032  push    rbp
0x180004033  push    rsi
0x180004034  push    rdi
0x180004035  push    r14
0x180004037  sub     rsp, 20h
0x18000403b  mov     r14, r8
0x18000403e  mov     rsi, rdx
0x180004041  mov     rdi, rcx
0x180004044  mov     byte ptr [rdx], 0
0x180004047  xor     bpl, bpl
0x18000404a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004051  test    rbx, rbx
0x180004054  jz      loc_1800040F0
0x18000405a  call    cs:__imp_GetCurrentThreadId
0x180004060  mov     r9d, eax
0x180004063  mov     r8d, eax
0x180004066  shr     r8, 2
0x18000406a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004074  mul     r8
0x180004077  shr     rdx, 3
0x18000407b  lea     rcx, [rdx+rdx*4]
0x18000407f  add     rcx, rcx
0x180004082  sub     r8, rcx
0x180004085  mov     rbx, [rbx+r8*8]
0x180004089  jmp     short loc_180004094
0x18000408b  cmp     [rbx], r9d
0x18000408e  jz      short loc_18000410B
0x180004090  mov     rbx, [rbx+8]
0x180004094  test    rbx, rbx
0x180004097  jnz     short loc_18000408B
0x180004099  test    rbx, rbx
0x18000409c  jz      short loc_1800040F0
0x18000409e  cmp     qword ptr [rbx], 0
0x1800040a2  jz      short loc_1800040F0
0x1800040a4  mov     [rsi], bpl
0x1800040a7  mov     r9, r14; unsigned __int64
0x1800040aa  mov     r8, rsi; char *
0x1800040ad  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800040b0  mov     rcx, rdi; struct wil::FailureInfo *
0x1800040b3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800040b8  test    al, al
0x1800040ba  jz      short loc_1800040C0
0x1800040bc  mov     [rdi+48h], rsi
0x1800040c0  mov     rbx, [rbx]
0x1800040c3  mov     al, [rbx+28h]
0x1800040c6  mov     byte ptr [rbx+28h], 1
0x1800040ca  test    al, al
0x1800040cc  jnz     short loc_1800040E7
0x1800040ce  mov     rcx, [rbx+8]
0x1800040d2  mov     rax, [rcx]
0x1800040d5  mov     rdx, rdi
0x1800040d8  mov     rax, [rax]
0x1800040db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040e0  or      bpl, al
0x1800040e3  mov     byte ptr [rbx+28h], 0
0x1800040e7  mov     rbx, [rbx+10h]
0x1800040eb  test    rbx, rbx
0x1800040ee  jnz     short loc_1800040C3
0x1800040f0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800040f7  test    rax, rax
0x1800040fa  jz      short loc_18000411C
0x1800040fc  test    bpl, bpl
0x1800040ff  jnz     short loc_180004111
0x180004101  test    byte ptr [rdi+4], 2
0x180004105  jnz     short loc_180004111
0x180004107  xor     ecx, ecx
0x180004109  jmp     short loc_180004113
0x18000410b  add     rbx, 10h
0x18000410f  jmp     short loc_180004099
0x180004111  mov     cl, 1
0x180004113  mov     rdx, rdi
0x180004116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000411b  nop
0x18000411c  call    cs:__imp_GetCurrentThreadId
0x180004122  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004128  cmp     ecx, eax
0x18000412a  jz      short loc_18000416C
0x18000412c  mov     ecx, 1
0x180004131  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004139  inc     ecx; this
0x18000413b  cmp     ecx, 4
0x18000413e  jge     short loc_180004165
0x180004140  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004146  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000414b  test    rax, rax
0x18000414e  jz      short loc_18000415B
0x180004150  mov     rdx, rdi; struct wil::FailureInfo *
0x180004153  mov     rcx, rax; this
0x180004156  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x18000415b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004165  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000416c  add     rsp, 20h
0x180004170  pop     r14
0x180004172  pop     rdi
0x180004173  pop     rsi
0x180004174  pop     rbp
0x180004175  pop     rbx
0x180004176  retn
```
