# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180006630`
- end: `0x180006784`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `340`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180006630`
- `0x180006908`
- `0x1800069ec`
- `0x1800080cc`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000665a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006722`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000665a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006722`

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
0x180006630  push    rbx
0x180006632  push    rbp
0x180006633  push    rsi
0x180006634  push    rdi
0x180006635  push    r14
0x180006637  sub     rsp, 20h
0x18000663b  mov     r14, r8
0x18000663e  mov     rsi, rdx
0x180006641  mov     rdi, rcx
0x180006644  mov     byte ptr [rdx], 0
0x180006647  xor     bpl, bpl
0x18000664a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006651  test    rbx, rbx
0x180006654  jz      loc_1800066F6
0x18000665a  call    cs:__imp_GetCurrentThreadId
0x180006661  nop     dword ptr [rax+rax+00h]
0x180006666  mov     r9d, eax
0x180006669  mov     r8d, eax
0x18000666c  shr     r8, 2
0x180006670  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000667a  mul     r8
0x18000667d  shr     rdx, 3
0x180006681  lea     rcx, [rdx+rdx*4]
0x180006685  add     rcx, rcx
0x180006688  sub     r8, rcx
0x18000668b  mov     rbx, [rbx+r8*8]
0x18000668f  jmp     short loc_18000669A
0x180006691  cmp     [rbx], r9d
0x180006694  jz      short loc_180006711
0x180006696  mov     rbx, [rbx+8]
0x18000669a  test    rbx, rbx
0x18000669d  jnz     short loc_180006691
0x18000669f  test    rbx, rbx
0x1800066a2  jz      short loc_1800066F6
0x1800066a4  cmp     qword ptr [rbx], 0
0x1800066a8  jz      short loc_1800066F6
0x1800066aa  mov     [rsi], bpl
0x1800066ad  mov     r9, r14; unsigned __int64
0x1800066b0  mov     r8, rsi; char *
0x1800066b3  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800066b6  mov     rcx, rdi; struct wil::FailureInfo *
0x1800066b9  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800066be  test    al, al
0x1800066c0  jz      short loc_1800066C6
0x1800066c2  mov     [rdi+48h], rsi
0x1800066c6  mov     rbx, [rbx]
0x1800066c9  mov     al, [rbx+28h]
0x1800066cc  mov     byte ptr [rbx+28h], 1
0x1800066d0  test    al, al
0x1800066d2  jnz     short loc_1800066ED
0x1800066d4  mov     rcx, [rbx+8]
0x1800066d8  mov     rax, [rcx]
0x1800066db  mov     rdx, rdi
0x1800066de  mov     rax, [rax]
0x1800066e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066e6  or      bpl, al
0x1800066e9  mov     byte ptr [rbx+28h], 0
0x1800066ed  mov     rbx, [rbx+10h]
0x1800066f1  test    rbx, rbx
0x1800066f4  jnz     short loc_1800066C9
0x1800066f6  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800066fd  test    rax, rax
0x180006700  jz      short loc_180006722
0x180006702  test    bpl, bpl
0x180006705  jnz     short loc_180006717
0x180006707  test    byte ptr [rdi+4], 2
0x18000670b  jnz     short loc_180006717
0x18000670d  xor     ecx, ecx
0x18000670f  jmp     short loc_180006719
0x180006711  add     rbx, 10h
0x180006715  jmp     short loc_18000669F
0x180006717  mov     cl, 1
0x180006719  mov     rdx, rdi
0x18000671c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006721  nop
0x180006722  call    cs:__imp_GetCurrentThreadId
0x180006729  nop     dword ptr [rax+rax+00h]
0x18000672e  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006734  cmp     ecx, eax
0x180006736  jz      short loc_180006778
0x180006738  mov     ecx, 1
0x18000673d  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180006745  inc     ecx; this
0x180006747  cmp     ecx, 4
0x18000674a  jge     short loc_180006771
0x18000674c  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006752  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180006757  test    rax, rax
0x18000675a  jz      short loc_180006767
0x18000675c  mov     rdx, rdi; struct wil::FailureInfo *
0x18000675f  mov     rcx, rax; this
0x180006762  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x180006767  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006771  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180006778  add     rsp, 20h
0x18000677c  pop     r14
0x18000677e  pop     rdi
0x18000677f  pop     rsi
0x180006780  pop     rbp
0x180006781  pop     rbx
0x180006782  retn
```
