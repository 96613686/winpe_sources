# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004480`
- end: `0x1800045d3`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `339`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180004480`
- `0x180004ba0`
- `0x180004c84`
- `0x180005bc0`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800044aa`
- `KERNEL32!GetCurrentThreadId` at `0x180004571`
- `KERNEL32!GetCurrentThreadId` at `0x1800044aa`
- `KERNEL32!GetCurrentThreadId` at `0x180004571`

## pseudocode

```c
void __fastcall wil::details::GetContextAndNotifyFailure(unsigned __int64 this, struct wil::FailureInfo *a2, char *a3)
{
  char v3; // bp
  __int64 v4; // rbx
  wil::details *v7; // rdi
  unsigned __int64 CurrentThreadId; // r9
  __int64 i; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v10; // rbx
  char v11; // al
  DWORD v12; // eax
  bool v13; // dl
  wil::details_abi *v14; // rcx
  wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax

  *(_BYTE *)a2 = 0;
  v3 = 0;
  v4 = wil::details::g_pThreadFailureCallbacks;
  v7 = (wil::details *)this;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    this = 10 * ((CurrentThreadId >> 2) / 0xA);
    for ( i = *(_QWORD *)(v4 + 8 * ((CurrentThreadId >> 2) % 0xA)); i; i = *(_QWORD *)(i + 8) )
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
             v7,
             *(struct wil::details::ThreadFailureCallbackHolder **)i,
             (char *)a2,
             (unsigned __int64)a3) )
      {
        *((_QWORD *)v7 + 9) = a2;
      }
      v10 = *(struct wil::details::ThreadFailureCallbackHolder **)i;
      do
      {
        v11 = *((_BYTE *)v10 + 40);
        *((_BYTE *)v10 + 40) = 1;
        if ( !v11 )
        {
          v3 |= (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v10 + 1))(*((_QWORD *)v10 + 1), v7);
          *((_BYTE *)v10 + 40) = 0;
        }
        v10 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v10 + 2);
      }
      while ( v10 );
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( v3 || (*((_BYTE *)v7 + 4) & 2) != 0 )
      LOBYTE(this) = 1;
    else
      this = 0;
    wil::details::g_pfnTelemetryCallback(this, v7);
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
        wil::details_abi::ThreadLocalData::SetLastError(ThreadLocalDataCache, v7);
      `wil::SetLastError'::`2'::lastThread = 0;
    }
    _InterlockedDecrement(&`wil::SetLastError'::`5'::depth);
  }
}

```

## disassembly

```asm
0x180004480  push    rbx
0x180004482  push    rbp
0x180004483  push    rsi
0x180004484  push    rdi
0x180004485  push    r14
0x180004487  sub     rsp, 20h
0x18000448b  mov     byte ptr [rdx], 0
0x18000448e  xor     bpl, bpl
0x180004491  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004498  mov     r14, r8
0x18000449b  mov     rsi, rdx
0x18000449e  mov     rdi, rcx
0x1800044a1  test    rbx, rbx
0x1800044a4  jz      loc_180004546
0x1800044aa  call    cs:__imp_GetCurrentThreadId
0x1800044b1  nop     dword ptr [rax+rax+00h]
0x1800044b6  mov     r8d, eax
0x1800044b9  mov     r9d, eax
0x1800044bc  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800044c6  shr     r8, 2
0x1800044ca  mul     r8
0x1800044cd  shr     rdx, 3
0x1800044d1  lea     rcx, [rdx+rdx*4]
0x1800044d5  add     rcx, rcx
0x1800044d8  sub     r8, rcx
0x1800044db  mov     rbx, [rbx+r8*8]
0x1800044df  jmp     short loc_1800044EA
0x1800044e1  cmp     [rbx], r9d
0x1800044e4  jz      short loc_180004561
0x1800044e6  mov     rbx, [rbx+8]
0x1800044ea  test    rbx, rbx
0x1800044ed  jnz     short loc_1800044E1
0x1800044ef  test    rbx, rbx
0x1800044f2  jz      short loc_180004546
0x1800044f4  cmp     qword ptr [rbx], 0
0x1800044f8  jz      short loc_180004546
0x1800044fa  mov     [rsi], bpl
0x1800044fd  mov     r9, r14; unsigned __int64
0x180004500  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004503  mov     r8, rsi; char *
0x180004506  mov     rcx, rdi; struct wil::FailureInfo *
0x180004509  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000450e  test    al, al
0x180004510  jz      short loc_180004516
0x180004512  mov     [rdi+48h], rsi
0x180004516  mov     rbx, [rbx]
0x180004519  mov     al, [rbx+28h]
0x18000451c  mov     byte ptr [rbx+28h], 1
0x180004520  test    al, al
0x180004522  jnz     short loc_18000453D
0x180004524  mov     rcx, [rbx+8]
0x180004528  mov     rdx, rdi
0x18000452b  mov     rax, [rcx]
0x18000452e  mov     rax, [rax]
0x180004531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004536  or      bpl, al
0x180004539  mov     byte ptr [rbx+28h], 0
0x18000453d  mov     rbx, [rbx+10h]
0x180004541  test    rbx, rbx
0x180004544  jnz     short loc_180004519
0x180004546  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000454d  test    rax, rax
0x180004550  jz      short loc_180004571
0x180004552  test    bpl, bpl
0x180004555  jnz     short loc_180004567
0x180004557  test    byte ptr [rdi+4], 2
0x18000455b  jnz     short loc_180004567
0x18000455d  xor     ecx, ecx
0x18000455f  jmp     short loc_180004569
0x180004561  add     rbx, 10h
0x180004565  jmp     short loc_1800044EF
0x180004567  mov     cl, 1
0x180004569  mov     rdx, rdi
0x18000456c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004571  call    cs:__imp_GetCurrentThreadId
0x180004578  nop     dword ptr [rax+rax+00h]
0x18000457d  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004583  cmp     ecx, eax
0x180004585  jz      short loc_1800045C7
0x180004587  mov     ecx, 1
0x18000458c  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004594  inc     ecx; this
0x180004596  cmp     ecx, 4
0x180004599  jge     short loc_1800045C0
0x18000459b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800045a1  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800045a6  test    rax, rax
0x1800045a9  jz      short loc_1800045B6
0x1800045ab  mov     rdx, rdi; struct wil::FailureInfo *
0x1800045ae  mov     rcx, rax; this
0x1800045b1  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x1800045b6  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800045c0  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800045c7  add     rsp, 20h
0x1800045cb  pop     r14
0x1800045cd  pop     rdi
0x1800045ce  pop     rsi
0x1800045cf  pop     rbp
0x1800045d0  pop     rbx
0x1800045d1  retn
```
