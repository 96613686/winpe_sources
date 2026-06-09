# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004600`
- end: `0x180004754`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `340`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180004600`
- `0x180004c78`
- `0x180004d5c`
- `0x1800060c8`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000462a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800046f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000462a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800046f2`

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
0x180004600  push    rbx
0x180004602  push    rbp
0x180004603  push    rsi
0x180004604  push    rdi
0x180004605  push    r14
0x180004607  sub     rsp, 20h
0x18000460b  mov     r14, r8
0x18000460e  mov     rsi, rdx
0x180004611  mov     rdi, rcx
0x180004614  mov     byte ptr [rdx], 0
0x180004617  xor     bpl, bpl
0x18000461a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004621  test    rbx, rbx
0x180004624  jz      loc_1800046C6
0x18000462a  call    cs:__imp_GetCurrentThreadId
0x180004631  nop     dword ptr [rax+rax+00h]
0x180004636  mov     r9d, eax
0x180004639  mov     r8d, eax
0x18000463c  shr     r8, 2
0x180004640  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000464a  mul     r8
0x18000464d  shr     rdx, 3
0x180004651  lea     rcx, [rdx+rdx*4]
0x180004655  add     rcx, rcx
0x180004658  sub     r8, rcx
0x18000465b  mov     rbx, [rbx+r8*8]
0x18000465f  jmp     short loc_18000466A
0x180004661  cmp     [rbx], r9d
0x180004664  jz      short loc_1800046E1
0x180004666  mov     rbx, [rbx+8]
0x18000466a  test    rbx, rbx
0x18000466d  jnz     short loc_180004661
0x18000466f  test    rbx, rbx
0x180004672  jz      short loc_1800046C6
0x180004674  cmp     qword ptr [rbx], 0
0x180004678  jz      short loc_1800046C6
0x18000467a  mov     [rsi], bpl
0x18000467d  mov     r9, r14; unsigned __int64
0x180004680  mov     r8, rsi; char *
0x180004683  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004686  mov     rcx, rdi; struct wil::FailureInfo *
0x180004689  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000468e  test    al, al
0x180004690  jz      short loc_180004696
0x180004692  mov     [rdi+48h], rsi
0x180004696  mov     rbx, [rbx]
0x180004699  mov     al, [rbx+28h]
0x18000469c  mov     byte ptr [rbx+28h], 1
0x1800046a0  test    al, al
0x1800046a2  jnz     short loc_1800046BD
0x1800046a4  mov     rcx, [rbx+8]
0x1800046a8  mov     rax, [rcx]
0x1800046ab  mov     rdx, rdi
0x1800046ae  mov     rax, [rax]
0x1800046b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046b6  or      bpl, al
0x1800046b9  mov     byte ptr [rbx+28h], 0
0x1800046bd  mov     rbx, [rbx+10h]
0x1800046c1  test    rbx, rbx
0x1800046c4  jnz     short loc_180004699
0x1800046c6  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800046cd  test    rax, rax
0x1800046d0  jz      short loc_1800046F2
0x1800046d2  test    bpl, bpl
0x1800046d5  jnz     short loc_1800046E7
0x1800046d7  test    byte ptr [rdi+4], 2
0x1800046db  jnz     short loc_1800046E7
0x1800046dd  xor     ecx, ecx
0x1800046df  jmp     short loc_1800046E9
0x1800046e1  add     rbx, 10h
0x1800046e5  jmp     short loc_18000466F
0x1800046e7  mov     cl, 1
0x1800046e9  mov     rdx, rdi
0x1800046ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046f1  nop
0x1800046f2  call    cs:__imp_GetCurrentThreadId
0x1800046f9  nop     dword ptr [rax+rax+00h]
0x1800046fe  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004704  cmp     ecx, eax
0x180004706  jz      short loc_180004748
0x180004708  mov     ecx, 1
0x18000470d  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004715  inc     ecx; this
0x180004717  cmp     ecx, 4
0x18000471a  jge     short loc_180004741
0x18000471c  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004722  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180004727  test    rax, rax
0x18000472a  jz      short loc_180004737
0x18000472c  mov     rdx, rdi; struct wil::FailureInfo *
0x18000472f  mov     rcx, rax; this
0x180004732  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x180004737  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004741  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004748  add     rsp, 20h
0x18000474c  pop     r14
0x18000474e  pop     rdi
0x18000474f  pop     rsi
0x180004750  pop     rbp
0x180004751  pop     rbx
0x180004752  retn
```
