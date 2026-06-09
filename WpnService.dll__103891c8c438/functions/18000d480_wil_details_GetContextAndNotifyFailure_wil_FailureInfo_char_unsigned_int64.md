# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000d480`
- end: `0x18000d59c`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `284`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000d480`
- `0x18000d5b0`
- `0x18000d6e4`
- `0x18000da50`
- `0x180027adc`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d4b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d4b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::GetContextAndNotifyFailure(wil::details *this, struct wil::FailureInfo *a2, char *a3)
{
  wil::details *v5; // rdi
  char v6; // bp
  DWORD CurrentThreadId; // eax
  wil::details_abi *v8; // rcx
  wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax
  char *Local; // rax
  char *v11; // rbx
  __int64 v12; // rbx
  char v13; // al

  v5 = this;
  *(_BYTE *)a2 = 0;
  v6 = 0;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    Local = wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
              (__int64)this,
              0);
    v11 = Local;
    if ( Local )
    {
      if ( *(_QWORD *)Local )
      {
        *(_BYTE *)a2 = 0;
        if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(
               v5,
               *(struct wil::details::ThreadFailureCallbackHolder **)Local,
               (char *)a2,
               (unsigned __int64)a3) )
        {
          *((_QWORD *)v5 + 9) = a2;
        }
        v12 = *(_QWORD *)v11;
        do
        {
          v13 = *(_BYTE *)(v12 + 40);
          *(_BYTE *)(v12 + 40) = 1;
          if ( !v13 )
          {
            v6 |= (***(__int64 (__fastcall ****)(_QWORD, wil::details *))(v12 + 8))(*(_QWORD *)(v12 + 8), v5);
            *(_BYTE *)(v12 + 40) = 0;
          }
          v12 = *(_QWORD *)(v12 + 16);
        }
        while ( v12 );
      }
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
  CurrentThreadId = GetCurrentThreadId();
  if ( `wil::SetLastError'::`2'::lastThread != CurrentThreadId )
  {
    v8 = (wil::details_abi *)(unsigned int)_InterlockedIncrement(&`wil::SetLastError'::`5'::depth);
    if ( (int)v8 < 4 )
    {
      `wil::SetLastError'::`2'::lastThread = CurrentThreadId;
      ThreadLocalDataCache = wil::details_abi::GetThreadLocalDataCache(v8);
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
0x18000d480  push    rbx
0x18000d482  push    rbp
0x18000d483  push    rsi
0x18000d484  push    rdi
0x18000d485  push    r14
0x18000d487  sub     rsp, 20h
0x18000d48b  mov     r14, r8
0x18000d48e  mov     rsi, rdx
0x18000d491  mov     rdi, rcx
0x18000d494  mov     byte ptr [rdx], 0
0x18000d497  xor     bpl, bpl
0x18000d49a  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000d4a2  jnz     short loc_18000D508
0x18000d4a4  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000d4ab  test    rax, rax
0x18000d4ae  jnz     loc_18000D56E
0x18000d4b4  call    cs:__imp_GetCurrentThreadId
0x18000d4ba  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000d4c0  cmp     ecx, eax
0x18000d4c2  jz      short loc_18000D4FD
0x18000d4c4  mov     ecx, 1
0x18000d4c9  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000d4d1  inc     ecx; this
0x18000d4d3  cmp     ecx, 4
0x18000d4d6  jge     short loc_18000D4F6
0x18000d4d8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000d4de  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000d4e3  test    rax, rax
0x18000d4e6  jnz     loc_18000D58C
0x18000d4ec  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000d4f6  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000d4fd  add     rsp, 20h
0x18000d501  pop     r14
0x18000d503  pop     rdi
0x18000d504  pop     rsi
0x18000d505  pop     rbp
0x18000d506  pop     rbx
0x18000d507  retn
0x18000d508  xor     edx, edx
0x18000d50a  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000d50f  mov     rbx, rax
0x18000d512  test    rax, rax
0x18000d515  jz      short loc_18000D4A4
0x18000d517  cmp     qword ptr [rax], 0
0x18000d51b  jz      short loc_18000D4A4
0x18000d51d  mov     [rsi], bpl
0x18000d520  mov     r9, r14; unsigned __int64
0x18000d523  mov     r8, rsi; char *
0x18000d526  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x18000d529  mov     rcx, rdi; struct wil::FailureInfo *
0x18000d52c  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000d531  test    al, al
0x18000d533  jz      short loc_18000D539
0x18000d535  mov     [rdi+48h], rsi
0x18000d539  mov     rbx, [rbx]
0x18000d53c  mov     al, [rbx+28h]
0x18000d53f  mov     byte ptr [rbx+28h], 1
0x18000d543  test    al, al
0x18000d545  jnz     short loc_18000D560
0x18000d547  mov     rcx, [rbx+8]
0x18000d54b  mov     rax, [rcx]
0x18000d54e  mov     rdx, rdi
0x18000d551  mov     rax, [rax]
0x18000d554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d559  or      bpl, al
0x18000d55c  mov     byte ptr [rbx+28h], 0
0x18000d560  mov     rbx, [rbx+10h]
0x18000d564  test    rbx, rbx
0x18000d567  jnz     short loc_18000D53C
0x18000d569  jmp     loc_18000D4A4
0x18000d56e  test    bpl, bpl
0x18000d571  jnz     short loc_18000D57D
0x18000d573  test    byte ptr [rdi+4], 2
0x18000d577  jnz     short loc_18000D57D
0x18000d579  xor     ecx, ecx
0x18000d57b  jmp     short loc_18000D57F
0x18000d57d  mov     cl, 1
0x18000d57f  mov     rdx, rdi
0x18000d582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d587  jmp     loc_18000D4B4
0x18000d58c  mov     rdx, rdi; struct wil::FailureInfo *
0x18000d58f  mov     rcx, rax; this
0x18000d592  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x18000d597  jmp     loc_18000D4EC
```
