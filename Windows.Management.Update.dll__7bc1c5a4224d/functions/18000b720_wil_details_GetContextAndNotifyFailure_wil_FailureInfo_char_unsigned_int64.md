# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000b720`
- end: `0x18000b927`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000b720`
- `0x18000be1c`
- `0x18000bf00`
- `0x18000cac0`
- `0x18000e444`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b74a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b80c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b74a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b80c`

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
  struct wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax
  unsigned __int64 v16; // r8
  struct wil::details_abi::ThreadLocalData *v17; // rbx
  int v18; // esi
  _WORD *v19; // rax
  _WORD *v20; // rcx
  __int64 v21; // r9
  __int64 v22; // rcx
  __int64 v23; // rdx
  unsigned __int16 v24; // dx

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
      v17 = ThreadLocalDataCache;
      if ( ThreadLocalDataCache )
      {
        v18 = *((_DWORD *)ThreadLocalDataCache + 4);
        if ( !*((_QWORD *)ThreadLocalDataCache + 3) )
        {
          if ( v18 )
          {
            v19 = wil::details::ProcessHeapAlloc(8u, 0x190u, v16);
            *((_QWORD *)v17 + 3) = v19;
            if ( v19 )
            {
              *((_DWORD *)v17 + 8) = 5;
              v20 = v19 + 200;
              while ( v19 != v20 )
              {
                *v19 = 80;
                v19 += 40;
              }
            }
          }
        }
        v21 = *((_QWORD *)v17 + 3);
        if ( v21 )
        {
          if ( !v18 || (v22 = *((_QWORD *)v17 + 3), v23 = v21 + 80LL * *((unsigned __int16 *)v17 + 16), v21 == v23) )
          {
LABEL_36:
            v24 = ((unsigned int)*((unsigned __int16 *)v17 + 17) + 1) % *((unsigned __int16 *)v17 + 16);
            *((_WORD *)v17 + 17) = v24;
            wil::details_abi::ThreadLocalFailureInfo::Set(
              (wil::details_abi::ThreadLocalFailureInfo *)(v21 + 80LL * v24),
              v5,
              _InterlockedIncrement(*((volatile signed __int32 **)v17 + 1)));
          }
          else
          {
            while ( *(_DWORD *)(v22 + 4) <= *((_DWORD *)v17 + 4) || *(_DWORD *)(v22 + 8) != *((_DWORD *)v5 + 2) )
            {
              v22 += 80;
              if ( v22 == v23 )
                goto LABEL_36;
            }
          }
        }
      }
      `wil::SetLastError'::`2'::lastThread = 0;
    }
    _InterlockedDecrement(&`wil::SetLastError'::`5'::depth);
  }
}

```

## disassembly

```asm
0x18000b720  push    rbx
0x18000b722  push    rbp
0x18000b723  push    rsi
0x18000b724  push    rdi
0x18000b725  push    r14
0x18000b727  sub     rsp, 20h
0x18000b72b  mov     r14, r8
0x18000b72e  mov     rsi, rdx
0x18000b731  mov     rdi, rcx
0x18000b734  mov     byte ptr [rdx], 0
0x18000b737  xor     bpl, bpl
0x18000b73a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000b741  test    rbx, rbx
0x18000b744  jz      loc_18000B7E0
0x18000b74a  call    cs:__imp_GetCurrentThreadId
0x18000b750  mov     r9d, eax
0x18000b753  mov     r8d, eax
0x18000b756  shr     r8, 2
0x18000b75a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000b764  mul     r8
0x18000b767  shr     rdx, 3
0x18000b76b  lea     rcx, [rdx+rdx*4]
0x18000b76f  add     rcx, rcx
0x18000b772  sub     r8, rcx
0x18000b775  mov     rbx, [rbx+r8*8]
0x18000b779  jmp     short loc_18000B784
0x18000b77b  cmp     [rbx], r9d
0x18000b77e  jz      short loc_18000B7FB
0x18000b780  mov     rbx, [rbx+8]
0x18000b784  test    rbx, rbx
0x18000b787  jnz     short loc_18000B77B
0x18000b789  test    rbx, rbx
0x18000b78c  jz      short loc_18000B7E0
0x18000b78e  cmp     qword ptr [rbx], 0
0x18000b792  jz      short loc_18000B7E0
0x18000b794  mov     [rsi], bpl
0x18000b797  mov     r9, r14; unsigned __int64
0x18000b79a  mov     r8, rsi; char *
0x18000b79d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000b7a0  mov     rcx, rdi; struct wil::FailureInfo *
0x18000b7a3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000b7a8  test    al, al
0x18000b7aa  jz      short loc_18000B7B0
0x18000b7ac  mov     [rdi+48h], rsi
0x18000b7b0  mov     rbx, [rbx]
0x18000b7b3  mov     al, [rbx+28h]
0x18000b7b6  mov     byte ptr [rbx+28h], 1
0x18000b7ba  test    al, al
0x18000b7bc  jnz     short loc_18000B7D7
0x18000b7be  mov     rcx, [rbx+8]
0x18000b7c2  mov     rax, [rcx]
0x18000b7c5  mov     rdx, rdi
0x18000b7c8  mov     rax, [rax]
0x18000b7cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7d0  or      bpl, al
0x18000b7d3  mov     byte ptr [rbx+28h], 0
0x18000b7d7  mov     rbx, [rbx+10h]
0x18000b7db  test    rbx, rbx
0x18000b7de  jnz     short loc_18000B7B3
0x18000b7e0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000b7e7  test    rax, rax
0x18000b7ea  jz      short loc_18000B80C
0x18000b7ec  test    bpl, bpl
0x18000b7ef  jnz     short loc_18000B801
0x18000b7f1  test    byte ptr [rdi+4], 2
0x18000b7f5  jnz     short loc_18000B801
0x18000b7f7  xor     ecx, ecx
0x18000b7f9  jmp     short loc_18000B803
0x18000b7fb  add     rbx, 10h
0x18000b7ff  jmp     short loc_18000B789
0x18000b801  mov     cl, 1
0x18000b803  mov     rdx, rdi
0x18000b806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b80b  nop
0x18000b80c  call    cs:__imp_GetCurrentThreadId
0x18000b812  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000b818  cmp     ecx, eax
0x18000b81a  jz      loc_18000B91C
0x18000b820  mov     ecx, 1
0x18000b825  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000b82d  inc     ecx; this
0x18000b82f  cmp     ecx, 4
0x18000b832  jge     loc_18000B915
0x18000b838  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000b83e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000b843  mov     rbx, rax
0x18000b846  test    rax, rax
0x18000b849  jz      loc_18000B90B
0x18000b84f  mov     esi, [rax+10h]
0x18000b852  mov     ebp, 50h ; 'P'
0x18000b857  cmp     qword ptr [rax+18h], 0
0x18000b85c  jnz     short loc_18000B893
0x18000b85e  test    esi, esi
0x18000b860  jz      short loc_18000B893
0x18000b862  mov     edx, 190h; dwBytes
0x18000b867  lea     ecx, [rbp-48h]; dwFlags
0x18000b86a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000b86f  mov     [rbx+18h], rax
0x18000b873  test    rax, rax
0x18000b876  jz      short loc_18000B893
0x18000b878  mov     dword ptr [rbx+20h], 5
0x18000b87f  lea     rcx, [rax+190h]
0x18000b886  jmp     short loc_18000B88E
0x18000b888  mov     [rax], bp
0x18000b88b  add     rax, rbp
0x18000b88e  cmp     rax, rcx
0x18000b891  jnz     short loc_18000B888
0x18000b893  mov     r9, [rbx+18h]
0x18000b897  test    r9, r9
0x18000b89a  jz      short loc_18000B90B
0x18000b89c  test    esi, esi
0x18000b89e  jz      short loc_18000B8D1
0x18000b8a0  mov     rcx, r9
0x18000b8a3  movzx   eax, word ptr [rbx+20h]
0x18000b8a7  lea     rdx, [rax+rax*4]
0x18000b8ab  shl     rdx, 4
0x18000b8af  add     rdx, r9
0x18000b8b2  cmp     r9, rdx
0x18000b8b5  jz      short loc_18000B8D1
0x18000b8b7  mov     r8d, [rbx+10h]
0x18000b8bb  cmp     [rcx+4], r8d
0x18000b8bf  jbe     short loc_18000B8C9
0x18000b8c1  mov     eax, [rdi+8]
0x18000b8c4  cmp     [rcx+8], eax
0x18000b8c7  jz      short loc_18000B90B
0x18000b8c9  add     rcx, rbp
0x18000b8cc  cmp     rcx, rdx
0x18000b8cf  jnz     short loc_18000B8BB
0x18000b8d1  movzx   eax, word ptr [rbx+22h]
0x18000b8d5  inc     eax
0x18000b8d7  movzx   ecx, word ptr [rbx+20h]
0x18000b8db  xor     edx, edx
0x18000b8dd  div     ecx
0x18000b8df  mov     [rbx+22h], dx
0x18000b8e3  mov     rax, [rbx+8]
0x18000b8e7  mov     r8d, 1
0x18000b8ed  lock xadd [rax], r8d
0x18000b8f2  inc     r8d; unsigned int
0x18000b8f5  movzx   eax, dx
0x18000b8f8  lea     rcx, [rax+rax*4]
0x18000b8fc  shl     rcx, 4
0x18000b900  add     rcx, r9; this
0x18000b903  mov     rdx, rdi; struct wil::FailureInfo *
0x18000b906  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000b90b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000b915  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000b91c  add     rsp, 20h
0x18000b920  pop     r14
0x18000b922  pop     rdi
0x18000b923  pop     rsi
0x18000b924  pop     rbp
0x18000b925  pop     rbx
0x18000b926  retn
```
