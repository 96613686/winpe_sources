# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180018470`
- end: `0x1800185c4`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `340`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180018470`
- `0x18001881c`
- `0x180018900`
- `0x180019808`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001849a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018562`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001849a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018562`

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
0x180018470  push    rbx
0x180018472  push    rbp
0x180018473  push    rsi
0x180018474  push    rdi
0x180018475  push    r14
0x180018477  sub     rsp, 20h
0x18001847b  mov     r14, r8
0x18001847e  mov     rsi, rdx
0x180018481  mov     rdi, rcx
0x180018484  mov     byte ptr [rdx], 0
0x180018487  xor     bpl, bpl
0x18001848a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180018491  test    rbx, rbx
0x180018494  jz      loc_180018536
0x18001849a  call    cs:__imp_GetCurrentThreadId
0x1800184a1  nop     dword ptr [rax+rax+00h]
0x1800184a6  mov     r9d, eax
0x1800184a9  mov     r8d, eax
0x1800184ac  shr     r8, 2
0x1800184b0  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800184ba  mul     r8
0x1800184bd  shr     rdx, 3
0x1800184c1  lea     rcx, [rdx+rdx*4]
0x1800184c5  add     rcx, rcx
0x1800184c8  sub     r8, rcx
0x1800184cb  mov     rbx, [rbx+r8*8]
0x1800184cf  jmp     short loc_1800184DA
0x1800184d1  cmp     [rbx], r9d
0x1800184d4  jz      short loc_180018551
0x1800184d6  mov     rbx, [rbx+8]
0x1800184da  test    rbx, rbx
0x1800184dd  jnz     short loc_1800184D1
0x1800184df  test    rbx, rbx
0x1800184e2  jz      short loc_180018536
0x1800184e4  cmp     qword ptr [rbx], 0
0x1800184e8  jz      short loc_180018536
0x1800184ea  mov     [rsi], bpl
0x1800184ed  mov     r9, r14; unsigned __int64
0x1800184f0  mov     r8, rsi; char *
0x1800184f3  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800184f6  mov     rcx, rdi; struct wil::FailureInfo *
0x1800184f9  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800184fe  test    al, al
0x180018500  jz      short loc_180018506
0x180018502  mov     [rdi+48h], rsi
0x180018506  mov     rbx, [rbx]
0x180018509  mov     al, [rbx+28h]
0x18001850c  mov     byte ptr [rbx+28h], 1
0x180018510  test    al, al
0x180018512  jnz     short loc_18001852D
0x180018514  mov     rcx, [rbx+8]
0x180018518  mov     rax, [rcx]
0x18001851b  mov     rdx, rdi
0x18001851e  mov     rax, [rax]
0x180018521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018526  or      bpl, al
0x180018529  mov     byte ptr [rbx+28h], 0
0x18001852d  mov     rbx, [rbx+10h]
0x180018531  test    rbx, rbx
0x180018534  jnz     short loc_180018509
0x180018536  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18001853d  test    rax, rax
0x180018540  jz      short loc_180018562
0x180018542  test    bpl, bpl
0x180018545  jnz     short loc_180018557
0x180018547  test    byte ptr [rdi+4], 2
0x18001854b  jnz     short loc_180018557
0x18001854d  xor     ecx, ecx
0x18001854f  jmp     short loc_180018559
0x180018551  add     rbx, 10h
0x180018555  jmp     short loc_1800184DF
0x180018557  mov     cl, 1
0x180018559  mov     rdx, rdi
0x18001855c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018561  nop
0x180018562  call    cs:__imp_GetCurrentThreadId
0x180018569  nop     dword ptr [rax+rax+00h]
0x18001856e  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180018574  cmp     ecx, eax
0x180018576  jz      short loc_1800185B8
0x180018578  mov     ecx, 1
0x18001857d  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180018585  inc     ecx; this
0x180018587  cmp     ecx, 4
0x18001858a  jge     short loc_1800185B1
0x18001858c  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180018592  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180018597  test    rax, rax
0x18001859a  jz      short loc_1800185A7
0x18001859c  mov     rdx, rdi; struct wil::FailureInfo *
0x18001859f  mov     rcx, rax; this
0x1800185a2  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x1800185a7  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800185b1  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800185b8  add     rsp, 20h
0x1800185bc  pop     r14
0x1800185be  pop     rdi
0x1800185bf  pop     rsi
0x1800185c0  pop     rbp
0x1800185c1  pop     rbx
0x1800185c2  retn
```
