# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18002a5f0`
- end: `0x18002a737`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `327`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18002a5f0`
- `0x18002acd0`
- `0x18002adb4`
- `0x18002e2cc`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a61a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a6dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a61a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a6dc`

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
0x18002a5f0  push    rbx
0x18002a5f2  push    rbp
0x18002a5f3  push    rsi
0x18002a5f4  push    rdi
0x18002a5f5  push    r14
0x18002a5f7  sub     rsp, 20h
0x18002a5fb  mov     r14, r8
0x18002a5fe  mov     rsi, rdx
0x18002a601  mov     rdi, rcx
0x18002a604  mov     byte ptr [rdx], 0
0x18002a607  xor     bpl, bpl
0x18002a60a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18002a611  test    rbx, rbx
0x18002a614  jz      loc_18002A6B0
0x18002a61a  call    cs:__imp_GetCurrentThreadId
0x18002a620  mov     r9d, eax
0x18002a623  mov     r8d, eax
0x18002a626  shr     r8, 2
0x18002a62a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002a634  mul     r8
0x18002a637  shr     rdx, 3
0x18002a63b  lea     rcx, [rdx+rdx*4]
0x18002a63f  add     rcx, rcx
0x18002a642  sub     r8, rcx
0x18002a645  mov     rbx, [rbx+r8*8]
0x18002a649  jmp     short loc_18002A654
0x18002a64b  cmp     [rbx], r9d
0x18002a64e  jz      short loc_18002A6CB
0x18002a650  mov     rbx, [rbx+8]
0x18002a654  test    rbx, rbx
0x18002a657  jnz     short loc_18002A64B
0x18002a659  test    rbx, rbx
0x18002a65c  jz      short loc_18002A6B0
0x18002a65e  cmp     qword ptr [rbx], 0
0x18002a662  jz      short loc_18002A6B0
0x18002a664  mov     [rsi], bpl
0x18002a667  mov     r9, r14; unsigned __int64
0x18002a66a  mov     r8, rsi; char *
0x18002a66d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18002a670  mov     rcx, rdi; struct wil::FailureInfo *
0x18002a673  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18002a678  test    al, al
0x18002a67a  jz      short loc_18002A680
0x18002a67c  mov     [rdi+48h], rsi
0x18002a680  mov     rbx, [rbx]
0x18002a683  mov     al, [rbx+28h]
0x18002a686  mov     byte ptr [rbx+28h], 1
0x18002a68a  test    al, al
0x18002a68c  jnz     short loc_18002A6A7
0x18002a68e  mov     rcx, [rbx+8]
0x18002a692  mov     rax, [rcx]
0x18002a695  mov     rdx, rdi
0x18002a698  mov     rax, [rax]
0x18002a69b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a6a0  or      bpl, al
0x18002a6a3  mov     byte ptr [rbx+28h], 0
0x18002a6a7  mov     rbx, [rbx+10h]
0x18002a6ab  test    rbx, rbx
0x18002a6ae  jnz     short loc_18002A683
0x18002a6b0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18002a6b7  test    rax, rax
0x18002a6ba  jz      short loc_18002A6DC
0x18002a6bc  test    bpl, bpl
0x18002a6bf  jnz     short loc_18002A6D1
0x18002a6c1  test    byte ptr [rdi+4], 2
0x18002a6c5  jnz     short loc_18002A6D1
0x18002a6c7  xor     ecx, ecx
0x18002a6c9  jmp     short loc_18002A6D3
0x18002a6cb  add     rbx, 10h
0x18002a6cf  jmp     short loc_18002A659
0x18002a6d1  mov     cl, 1
0x18002a6d3  mov     rdx, rdi
0x18002a6d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a6db  nop
0x18002a6dc  call    cs:__imp_GetCurrentThreadId
0x18002a6e2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18002a6e8  cmp     ecx, eax
0x18002a6ea  jz      short loc_18002A72C
0x18002a6ec  mov     ecx, 1
0x18002a6f1  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18002a6f9  inc     ecx; this
0x18002a6fb  cmp     ecx, 4
0x18002a6fe  jge     short loc_18002A725
0x18002a700  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18002a706  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18002a70b  test    rax, rax
0x18002a70e  jz      short loc_18002A71B
0x18002a710  mov     rdx, rdi; struct wil::FailureInfo *
0x18002a713  mov     rcx, rax; this
0x18002a716  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x18002a71b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18002a725  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18002a72c  add     rsp, 20h
0x18002a730  pop     r14
0x18002a732  pop     rdi
0x18002a733  pop     rsi
0x18002a734  pop     rbp
0x18002a735  pop     rbx
0x18002a736  retn
```
