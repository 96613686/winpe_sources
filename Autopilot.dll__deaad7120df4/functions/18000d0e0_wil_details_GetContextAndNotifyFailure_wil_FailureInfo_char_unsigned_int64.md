# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000d0e0`
- end: `0x18000d234`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `340`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000d0e0`
- `0x18000d85c`
- `0x18000d940`
- `0x180010d9c`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d10a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d1d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d10a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d1d2`

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
0x18000d0e0  push    rbx
0x18000d0e2  push    rbp
0x18000d0e3  push    rsi
0x18000d0e4  push    rdi
0x18000d0e5  push    r14
0x18000d0e7  sub     rsp, 20h
0x18000d0eb  mov     r14, r8
0x18000d0ee  mov     rsi, rdx
0x18000d0f1  mov     rdi, rcx
0x18000d0f4  mov     byte ptr [rdx], 0
0x18000d0f7  xor     bpl, bpl
0x18000d0fa  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000d101  test    rbx, rbx
0x18000d104  jz      loc_18000D1A6
0x18000d10a  call    cs:__imp_GetCurrentThreadId
0x18000d111  nop     dword ptr [rax+rax+00h]
0x18000d116  mov     r9d, eax
0x18000d119  mov     r8d, eax
0x18000d11c  shr     r8, 2
0x18000d120  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000d12a  mul     r8
0x18000d12d  shr     rdx, 3
0x18000d131  lea     rcx, [rdx+rdx*4]
0x18000d135  add     rcx, rcx
0x18000d138  sub     r8, rcx
0x18000d13b  mov     rbx, [rbx+r8*8]
0x18000d13f  jmp     short loc_18000D14A
0x18000d141  cmp     [rbx], r9d
0x18000d144  jz      short loc_18000D1C1
0x18000d146  mov     rbx, [rbx+8]
0x18000d14a  test    rbx, rbx
0x18000d14d  jnz     short loc_18000D141
0x18000d14f  test    rbx, rbx
0x18000d152  jz      short loc_18000D1A6
0x18000d154  cmp     qword ptr [rbx], 0
0x18000d158  jz      short loc_18000D1A6
0x18000d15a  mov     [rsi], bpl
0x18000d15d  mov     r9, r14; unsigned __int64
0x18000d160  mov     r8, rsi; char *
0x18000d163  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000d166  mov     rcx, rdi; struct wil::FailureInfo *
0x18000d169  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000d16e  test    al, al
0x18000d170  jz      short loc_18000D176
0x18000d172  mov     [rdi+48h], rsi
0x18000d176  mov     rbx, [rbx]
0x18000d179  mov     al, [rbx+28h]
0x18000d17c  mov     byte ptr [rbx+28h], 1
0x18000d180  test    al, al
0x18000d182  jnz     short loc_18000D19D
0x18000d184  mov     rcx, [rbx+8]
0x18000d188  mov     rax, [rcx]
0x18000d18b  mov     rdx, rdi
0x18000d18e  mov     rax, [rax]
0x18000d191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d196  or      bpl, al
0x18000d199  mov     byte ptr [rbx+28h], 0
0x18000d19d  mov     rbx, [rbx+10h]
0x18000d1a1  test    rbx, rbx
0x18000d1a4  jnz     short loc_18000D179
0x18000d1a6  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000d1ad  test    rax, rax
0x18000d1b0  jz      short loc_18000D1D2
0x18000d1b2  test    bpl, bpl
0x18000d1b5  jnz     short loc_18000D1C7
0x18000d1b7  test    byte ptr [rdi+4], 2
0x18000d1bb  jnz     short loc_18000D1C7
0x18000d1bd  xor     ecx, ecx
0x18000d1bf  jmp     short loc_18000D1C9
0x18000d1c1  add     rbx, 10h
0x18000d1c5  jmp     short loc_18000D14F
0x18000d1c7  mov     cl, 1
0x18000d1c9  mov     rdx, rdi
0x18000d1cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1d1  nop
0x18000d1d2  call    cs:__imp_GetCurrentThreadId
0x18000d1d9  nop     dword ptr [rax+rax+00h]
0x18000d1de  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000d1e4  cmp     ecx, eax
0x18000d1e6  jz      short loc_18000D228
0x18000d1e8  mov     ecx, 1
0x18000d1ed  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000d1f5  inc     ecx; this
0x18000d1f7  cmp     ecx, 4
0x18000d1fa  jge     short loc_18000D221
0x18000d1fc  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000d202  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000d207  test    rax, rax
0x18000d20a  jz      short loc_18000D217
0x18000d20c  mov     rdx, rdi; struct wil::FailureInfo *
0x18000d20f  mov     rcx, rax; this
0x18000d212  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x18000d217  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000d221  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000d228  add     rsp, 20h
0x18000d22c  pop     r14
0x18000d22e  pop     rdi
0x18000d22f  pop     rsi
0x18000d230  pop     rbp
0x18000d231  pop     rbx
0x18000d232  retn
```
