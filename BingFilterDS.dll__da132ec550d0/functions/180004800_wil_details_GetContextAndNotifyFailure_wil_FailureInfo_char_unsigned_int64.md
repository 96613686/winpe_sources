# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004800`
- end: `0x180004947`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `327`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180004800`
- `0x180004e90`
- `0x180004f74`
- `0x1800066f4`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000482a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800048ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000482a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800048ec`

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
0x180004800  push    rbx
0x180004802  push    rbp
0x180004803  push    rsi
0x180004804  push    rdi
0x180004805  push    r14
0x180004807  sub     rsp, 20h
0x18000480b  mov     r14, r8
0x18000480e  mov     rsi, rdx
0x180004811  mov     rdi, rcx
0x180004814  mov     byte ptr [rdx], 0
0x180004817  xor     bpl, bpl
0x18000481a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004821  test    rbx, rbx
0x180004824  jz      loc_1800048C0
0x18000482a  call    cs:__imp_GetCurrentThreadId
0x180004830  mov     r9d, eax
0x180004833  mov     r8d, eax
0x180004836  shr     r8, 2
0x18000483a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004844  mul     r8
0x180004847  shr     rdx, 3
0x18000484b  lea     rcx, [rdx+rdx*4]
0x18000484f  add     rcx, rcx
0x180004852  sub     r8, rcx
0x180004855  mov     rbx, [rbx+r8*8]
0x180004859  jmp     short loc_180004864
0x18000485b  cmp     [rbx], r9d
0x18000485e  jz      short loc_1800048DB
0x180004860  mov     rbx, [rbx+8]
0x180004864  test    rbx, rbx
0x180004867  jnz     short loc_18000485B
0x180004869  test    rbx, rbx
0x18000486c  jz      short loc_1800048C0
0x18000486e  cmp     qword ptr [rbx], 0
0x180004872  jz      short loc_1800048C0
0x180004874  mov     [rsi], bpl
0x180004877  mov     r9, r14; unsigned __int64
0x18000487a  mov     r8, rsi; char *
0x18000487d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004880  mov     rcx, rdi; struct wil::FailureInfo *
0x180004883  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004888  test    al, al
0x18000488a  jz      short loc_180004890
0x18000488c  mov     [rdi+48h], rsi
0x180004890  mov     rbx, [rbx]
0x180004893  mov     al, [rbx+28h]
0x180004896  mov     byte ptr [rbx+28h], 1
0x18000489a  test    al, al
0x18000489c  jnz     short loc_1800048B7
0x18000489e  mov     rcx, [rbx+8]
0x1800048a2  mov     rax, [rcx]
0x1800048a5  mov     rdx, rdi
0x1800048a8  mov     rax, [rax]
0x1800048ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048b0  or      bpl, al
0x1800048b3  mov     byte ptr [rbx+28h], 0
0x1800048b7  mov     rbx, [rbx+10h]
0x1800048bb  test    rbx, rbx
0x1800048be  jnz     short loc_180004893
0x1800048c0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800048c7  test    rax, rax
0x1800048ca  jz      short loc_1800048EC
0x1800048cc  test    bpl, bpl
0x1800048cf  jnz     short loc_1800048E1
0x1800048d1  test    byte ptr [rdi+4], 2
0x1800048d5  jnz     short loc_1800048E1
0x1800048d7  xor     ecx, ecx
0x1800048d9  jmp     short loc_1800048E3
0x1800048db  add     rbx, 10h
0x1800048df  jmp     short loc_180004869
0x1800048e1  mov     cl, 1
0x1800048e3  mov     rdx, rdi
0x1800048e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048eb  nop
0x1800048ec  call    cs:__imp_GetCurrentThreadId
0x1800048f2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800048f8  cmp     ecx, eax
0x1800048fa  jz      short loc_18000493C
0x1800048fc  mov     ecx, 1
0x180004901  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004909  inc     ecx; this
0x18000490b  cmp     ecx, 4
0x18000490e  jge     short loc_180004935
0x180004910  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004916  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000491b  test    rax, rax
0x18000491e  jz      short loc_18000492B
0x180004920  mov     rdx, rdi; struct wil::FailureInfo *
0x180004923  mov     rcx, rax; this
0x180004926  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x18000492b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004935  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000493c  add     rsp, 20h
0x180004940  pop     r14
0x180004942  pop     rdi
0x180004943  pop     rsi
0x180004944  pop     rbp
0x180004945  pop     rbx
0x180004946  retn
```
