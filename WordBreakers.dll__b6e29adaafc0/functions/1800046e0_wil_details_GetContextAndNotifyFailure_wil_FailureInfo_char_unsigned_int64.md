# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800046e0`
- end: `0x180004827`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `327`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800046e0`
- `0x180004d1c`
- `0x180004e00`
- `0x180005dc8`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000470a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800047cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000470a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800047cc`

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
0x1800046e0  push    rbx
0x1800046e2  push    rbp
0x1800046e3  push    rsi
0x1800046e4  push    rdi
0x1800046e5  push    r14
0x1800046e7  sub     rsp, 20h
0x1800046eb  mov     r14, r8
0x1800046ee  mov     rsi, rdx
0x1800046f1  mov     rdi, rcx
0x1800046f4  mov     byte ptr [rdx], 0
0x1800046f7  xor     bpl, bpl
0x1800046fa  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004701  test    rbx, rbx
0x180004704  jz      loc_1800047A0
0x18000470a  call    cs:__imp_GetCurrentThreadId
0x180004710  mov     r9d, eax
0x180004713  mov     r8d, eax
0x180004716  shr     r8, 2
0x18000471a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004724  mul     r8
0x180004727  shr     rdx, 3
0x18000472b  lea     rcx, [rdx+rdx*4]
0x18000472f  add     rcx, rcx
0x180004732  sub     r8, rcx
0x180004735  mov     rbx, [rbx+r8*8]
0x180004739  jmp     short loc_180004744
0x18000473b  cmp     [rbx], r9d
0x18000473e  jz      short loc_1800047BB
0x180004740  mov     rbx, [rbx+8]
0x180004744  test    rbx, rbx
0x180004747  jnz     short loc_18000473B
0x180004749  test    rbx, rbx
0x18000474c  jz      short loc_1800047A0
0x18000474e  cmp     qword ptr [rbx], 0
0x180004752  jz      short loc_1800047A0
0x180004754  mov     [rsi], bpl
0x180004757  mov     r9, r14; unsigned __int64
0x18000475a  mov     r8, rsi; char *
0x18000475d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004760  mov     rcx, rdi; struct wil::FailureInfo *
0x180004763  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004768  test    al, al
0x18000476a  jz      short loc_180004770
0x18000476c  mov     [rdi+48h], rsi
0x180004770  mov     rbx, [rbx]
0x180004773  mov     al, [rbx+28h]
0x180004776  mov     byte ptr [rbx+28h], 1
0x18000477a  test    al, al
0x18000477c  jnz     short loc_180004797
0x18000477e  mov     rcx, [rbx+8]
0x180004782  mov     rax, [rcx]
0x180004785  mov     rdx, rdi
0x180004788  mov     rax, [rax]
0x18000478b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004790  or      bpl, al
0x180004793  mov     byte ptr [rbx+28h], 0
0x180004797  mov     rbx, [rbx+10h]
0x18000479b  test    rbx, rbx
0x18000479e  jnz     short loc_180004773
0x1800047a0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800047a7  test    rax, rax
0x1800047aa  jz      short loc_1800047CC
0x1800047ac  test    bpl, bpl
0x1800047af  jnz     short loc_1800047C1
0x1800047b1  test    byte ptr [rdi+4], 2
0x1800047b5  jnz     short loc_1800047C1
0x1800047b7  xor     ecx, ecx
0x1800047b9  jmp     short loc_1800047C3
0x1800047bb  add     rbx, 10h
0x1800047bf  jmp     short loc_180004749
0x1800047c1  mov     cl, 1
0x1800047c3  mov     rdx, rdi
0x1800047c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047cb  nop
0x1800047cc  call    cs:__imp_GetCurrentThreadId
0x1800047d2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800047d8  cmp     ecx, eax
0x1800047da  jz      short loc_18000481C
0x1800047dc  mov     ecx, 1
0x1800047e1  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800047e9  inc     ecx; this
0x1800047eb  cmp     ecx, 4
0x1800047ee  jge     short loc_180004815
0x1800047f0  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800047f6  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800047fb  test    rax, rax
0x1800047fe  jz      short loc_18000480B
0x180004800  mov     rdx, rdi; struct wil::FailureInfo *
0x180004803  mov     rcx, rax; this
0x180004806  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x18000480b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004815  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000481c  add     rsp, 20h
0x180004820  pop     r14
0x180004822  pop     rdi
0x180004823  pop     rsi
0x180004824  pop     rbp
0x180004825  pop     rbx
0x180004826  retn
```
