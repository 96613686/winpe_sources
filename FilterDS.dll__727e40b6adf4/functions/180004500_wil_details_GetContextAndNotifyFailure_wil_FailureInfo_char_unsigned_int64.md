# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004500`
- end: `0x180004647`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `327`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180004500`
- `0x180004b90`
- `0x180004c74`
- `0x180006198`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000452a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800045ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000452a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800045ec`

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
0x180004500  push    rbx
0x180004502  push    rbp
0x180004503  push    rsi
0x180004504  push    rdi
0x180004505  push    r14
0x180004507  sub     rsp, 20h
0x18000450b  mov     r14, r8
0x18000450e  mov     rsi, rdx
0x180004511  mov     rdi, rcx
0x180004514  mov     byte ptr [rdx], 0
0x180004517  xor     bpl, bpl
0x18000451a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004521  test    rbx, rbx
0x180004524  jz      loc_1800045C0
0x18000452a  call    cs:__imp_GetCurrentThreadId
0x180004530  mov     r9d, eax
0x180004533  mov     r8d, eax
0x180004536  shr     r8, 2
0x18000453a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004544  mul     r8
0x180004547  shr     rdx, 3
0x18000454b  lea     rcx, [rdx+rdx*4]
0x18000454f  add     rcx, rcx
0x180004552  sub     r8, rcx
0x180004555  mov     rbx, [rbx+r8*8]
0x180004559  jmp     short loc_180004564
0x18000455b  cmp     [rbx], r9d
0x18000455e  jz      short loc_1800045DB
0x180004560  mov     rbx, [rbx+8]
0x180004564  test    rbx, rbx
0x180004567  jnz     short loc_18000455B
0x180004569  test    rbx, rbx
0x18000456c  jz      short loc_1800045C0
0x18000456e  cmp     qword ptr [rbx], 0
0x180004572  jz      short loc_1800045C0
0x180004574  mov     [rsi], bpl
0x180004577  mov     r9, r14; unsigned __int64
0x18000457a  mov     r8, rsi; char *
0x18000457d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004580  mov     rcx, rdi; struct wil::FailureInfo *
0x180004583  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004588  test    al, al
0x18000458a  jz      short loc_180004590
0x18000458c  mov     [rdi+48h], rsi
0x180004590  mov     rbx, [rbx]
0x180004593  mov     al, [rbx+28h]
0x180004596  mov     byte ptr [rbx+28h], 1
0x18000459a  test    al, al
0x18000459c  jnz     short loc_1800045B7
0x18000459e  mov     rcx, [rbx+8]
0x1800045a2  mov     rax, [rcx]
0x1800045a5  mov     rdx, rdi
0x1800045a8  mov     rax, [rax]
0x1800045ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045b0  or      bpl, al
0x1800045b3  mov     byte ptr [rbx+28h], 0
0x1800045b7  mov     rbx, [rbx+10h]
0x1800045bb  test    rbx, rbx
0x1800045be  jnz     short loc_180004593
0x1800045c0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800045c7  test    rax, rax
0x1800045ca  jz      short loc_1800045EC
0x1800045cc  test    bpl, bpl
0x1800045cf  jnz     short loc_1800045E1
0x1800045d1  test    byte ptr [rdi+4], 2
0x1800045d5  jnz     short loc_1800045E1
0x1800045d7  xor     ecx, ecx
0x1800045d9  jmp     short loc_1800045E3
0x1800045db  add     rbx, 10h
0x1800045df  jmp     short loc_180004569
0x1800045e1  mov     cl, 1
0x1800045e3  mov     rdx, rdi
0x1800045e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045eb  nop
0x1800045ec  call    cs:__imp_GetCurrentThreadId
0x1800045f2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800045f8  cmp     ecx, eax
0x1800045fa  jz      short loc_18000463C
0x1800045fc  mov     ecx, 1
0x180004601  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004609  inc     ecx; this
0x18000460b  cmp     ecx, 4
0x18000460e  jge     short loc_180004635
0x180004610  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004616  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000461b  test    rax, rax
0x18000461e  jz      short loc_18000462B
0x180004620  mov     rdx, rdi; struct wil::FailureInfo *
0x180004623  mov     rcx, rax; this
0x180004626  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x18000462b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004635  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000463c  add     rsp, 20h
0x180004640  pop     r14
0x180004642  pop     rdi
0x180004643  pop     rsi
0x180004644  pop     rbp
0x180004645  pop     rbx
0x180004646  retn
```
