# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x14000a310`
- end: `0x14000a457`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `327`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x14000a310`
- `0x14000a988`
- `0x14000aa6c`
- `0x14000d89c`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a33a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a3fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a33a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a3fc`

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
0x14000a310  push    rbx
0x14000a312  push    rbp
0x14000a313  push    rsi
0x14000a314  push    rdi
0x14000a315  push    r14
0x14000a317  sub     rsp, 20h
0x14000a31b  mov     r14, r8
0x14000a31e  mov     rsi, rdx
0x14000a321  mov     rdi, rcx
0x14000a324  mov     byte ptr [rdx], 0
0x14000a327  xor     bpl, bpl
0x14000a32a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14000a331  test    rbx, rbx
0x14000a334  jz      loc_14000A3D0
0x14000a33a  call    cs:__imp_GetCurrentThreadId
0x14000a340  mov     r9d, eax
0x14000a343  mov     r8d, eax
0x14000a346  shr     r8, 2
0x14000a34a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000a354  mul     r8
0x14000a357  shr     rdx, 3
0x14000a35b  lea     rcx, [rdx+rdx*4]
0x14000a35f  add     rcx, rcx
0x14000a362  sub     r8, rcx
0x14000a365  mov     rbx, [rbx+r8*8]
0x14000a369  jmp     short loc_14000A374
0x14000a36b  cmp     [rbx], r9d
0x14000a36e  jz      short loc_14000A3EB
0x14000a370  mov     rbx, [rbx+8]
0x14000a374  test    rbx, rbx
0x14000a377  jnz     short loc_14000A36B
0x14000a379  test    rbx, rbx
0x14000a37c  jz      short loc_14000A3D0
0x14000a37e  cmp     qword ptr [rbx], 0
0x14000a382  jz      short loc_14000A3D0
0x14000a384  mov     [rsi], bpl
0x14000a387  mov     r9, r14; unsigned __int64
0x14000a38a  mov     r8, rsi; char *
0x14000a38d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x14000a390  mov     rcx, rdi; struct wil::FailureInfo *
0x14000a393  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x14000a398  test    al, al
0x14000a39a  jz      short loc_14000A3A0
0x14000a39c  mov     [rdi+48h], rsi
0x14000a3a0  mov     rbx, [rbx]
0x14000a3a3  mov     al, [rbx+28h]
0x14000a3a6  mov     byte ptr [rbx+28h], 1
0x14000a3aa  test    al, al
0x14000a3ac  jnz     short loc_14000A3C7
0x14000a3ae  mov     rcx, [rbx+8]
0x14000a3b2  mov     rax, [rcx]
0x14000a3b5  mov     rdx, rdi
0x14000a3b8  mov     rax, [rax]
0x14000a3bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a3c0  or      bpl, al
0x14000a3c3  mov     byte ptr [rbx+28h], 0
0x14000a3c7  mov     rbx, [rbx+10h]
0x14000a3cb  test    rbx, rbx
0x14000a3ce  jnz     short loc_14000A3A3
0x14000a3d0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x14000a3d7  test    rax, rax
0x14000a3da  jz      short loc_14000A3FC
0x14000a3dc  test    bpl, bpl
0x14000a3df  jnz     short loc_14000A3F1
0x14000a3e1  test    byte ptr [rdi+4], 2
0x14000a3e5  jnz     short loc_14000A3F1
0x14000a3e7  xor     ecx, ecx
0x14000a3e9  jmp     short loc_14000A3F3
0x14000a3eb  add     rbx, 10h
0x14000a3ef  jmp     short loc_14000A379
0x14000a3f1  mov     cl, 1
0x14000a3f3  mov     rdx, rdi
0x14000a3f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a3fb  nop
0x14000a3fc  call    cs:__imp_GetCurrentThreadId
0x14000a402  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14000a408  cmp     ecx, eax
0x14000a40a  jz      short loc_14000A44C
0x14000a40c  mov     ecx, 1
0x14000a411  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000a419  inc     ecx; this
0x14000a41b  cmp     ecx, 4
0x14000a41e  jge     short loc_14000A445
0x14000a420  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14000a426  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x14000a42b  test    rax, rax
0x14000a42e  jz      short loc_14000A43B
0x14000a430  mov     rdx, rdi; struct wil::FailureInfo *
0x14000a433  mov     rcx, rax; this
0x14000a436  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x14000a43b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14000a445  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000a44c  add     rsp, 20h
0x14000a450  pop     r14
0x14000a452  pop     rdi
0x14000a453  pop     rsi
0x14000a454  pop     rbp
0x14000a455  pop     rbx
0x14000a456  retn
```
