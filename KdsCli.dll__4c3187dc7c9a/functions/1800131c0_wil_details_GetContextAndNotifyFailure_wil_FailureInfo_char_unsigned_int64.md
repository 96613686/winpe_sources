# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800131c0`
- end: `0x1800133c6`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000c600`
- `0x1800131c0`
- `0x1800138b8`
- `0x18001399c`
- `0x180015728`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800131ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800132ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800131ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800132ab`

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
  volatile signed __int32 *v25; // rax

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
            v25 = (volatile signed __int32 *)*((_QWORD *)v17 + 1);
            *((_WORD *)v17 + 17) = v24;
            wil::details_abi::ThreadLocalFailureInfo::Set(
              (wil::details_abi::ThreadLocalFailureInfo *)(v21 + 80LL * v24),
              v7,
              _InterlockedIncrement(v25));
          }
          else
          {
            while ( *(_DWORD *)(v22 + 4) <= *((_DWORD *)v17 + 4) || *(_DWORD *)(v22 + 8) != *((_DWORD *)v7 + 2) )
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
0x1800131c0  push    rbx
0x1800131c2  push    rbp
0x1800131c3  push    rsi
0x1800131c4  push    rdi
0x1800131c5  push    r14
0x1800131c7  sub     rsp, 20h
0x1800131cb  mov     byte ptr [rdx], 0
0x1800131ce  xor     bpl, bpl
0x1800131d1  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800131d8  mov     r14, r8
0x1800131db  mov     rsi, rdx
0x1800131de  mov     rdi, rcx
0x1800131e1  test    rbx, rbx
0x1800131e4  jz      loc_180013280
0x1800131ea  call    cs:__imp_GetCurrentThreadId
0x1800131f0  mov     r8d, eax
0x1800131f3  mov     r9d, eax
0x1800131f6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180013200  shr     r8, 2
0x180013204  mul     r8
0x180013207  shr     rdx, 3
0x18001320b  lea     rcx, [rdx+rdx*4]
0x18001320f  add     rcx, rcx
0x180013212  sub     r8, rcx
0x180013215  mov     rbx, [rbx+r8*8]
0x180013219  jmp     short loc_180013224
0x18001321b  cmp     [rbx], r9d
0x18001321e  jz      short loc_18001329B
0x180013220  mov     rbx, [rbx+8]
0x180013224  test    rbx, rbx
0x180013227  jnz     short loc_18001321B
0x180013229  test    rbx, rbx
0x18001322c  jz      short loc_180013280
0x18001322e  cmp     qword ptr [rbx], 0
0x180013232  jz      short loc_180013280
0x180013234  mov     [rsi], bpl
0x180013237  mov     r9, r14; unsigned __int64
0x18001323a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18001323d  mov     r8, rsi; char *
0x180013240  mov     rcx, rdi; struct wil::FailureInfo *
0x180013243  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180013248  test    al, al
0x18001324a  jz      short loc_180013250
0x18001324c  mov     [rdi+48h], rsi
0x180013250  mov     rbx, [rbx]
0x180013253  mov     al, [rbx+28h]
0x180013256  mov     byte ptr [rbx+28h], 1
0x18001325a  test    al, al
0x18001325c  jnz     short loc_180013277
0x18001325e  mov     rcx, [rbx+8]
0x180013262  mov     rdx, rdi
0x180013265  mov     rax, [rcx]
0x180013268  mov     rax, [rax]
0x18001326b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013270  or      bpl, al
0x180013273  mov     byte ptr [rbx+28h], 0
0x180013277  mov     rbx, [rbx+10h]
0x18001327b  test    rbx, rbx
0x18001327e  jnz     short loc_180013253
0x180013280  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180013287  test    rax, rax
0x18001328a  jz      short loc_1800132AB
0x18001328c  test    bpl, bpl
0x18001328f  jnz     short loc_1800132A1
0x180013291  test    byte ptr [rdi+4], 2
0x180013295  jnz     short loc_1800132A1
0x180013297  xor     ecx, ecx
0x180013299  jmp     short loc_1800132A3
0x18001329b  add     rbx, 10h
0x18001329f  jmp     short loc_180013229
0x1800132a1  mov     cl, 1
0x1800132a3  mov     rdx, rdi
0x1800132a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132ab  call    cs:__imp_GetCurrentThreadId
0x1800132b1  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800132b7  cmp     ecx, eax
0x1800132b9  jz      loc_1800133BB
0x1800132bf  mov     ecx, 1
0x1800132c4  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800132cc  inc     ecx; this
0x1800132ce  cmp     ecx, 4
0x1800132d1  jge     loc_1800133B4
0x1800132d7  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800132dd  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800132e2  mov     rbx, rax
0x1800132e5  test    rax, rax
0x1800132e8  jz      loc_1800133AA
0x1800132ee  cmp     qword ptr [rax+18h], 0
0x1800132f3  mov     ebp, 50h ; 'P'
0x1800132f8  mov     esi, [rax+10h]
0x1800132fb  jnz     short loc_180013332
0x1800132fd  test    esi, esi
0x1800132ff  jz      short loc_180013332
0x180013301  mov     edx, 190h; dwBytes
0x180013306  lea     ecx, [rbp-48h]; dwFlags
0x180013309  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001330e  mov     [rbx+18h], rax
0x180013312  test    rax, rax
0x180013315  jz      short loc_180013332
0x180013317  mov     dword ptr [rbx+20h], 5
0x18001331e  lea     rcx, [rax+190h]
0x180013325  jmp     short loc_18001332D
0x180013327  mov     [rax], bp
0x18001332a  add     rax, rbp
0x18001332d  cmp     rax, rcx
0x180013330  jnz     short loc_180013327
0x180013332  mov     r9, [rbx+18h]
0x180013336  test    r9, r9
0x180013339  jz      short loc_1800133AA
0x18001333b  test    esi, esi
0x18001333d  jz      short loc_180013370
0x18001333f  movzx   eax, word ptr [rbx+20h]
0x180013343  mov     rcx, r9
0x180013346  lea     rdx, [rax+rax*4]
0x18001334a  shl     rdx, 4
0x18001334e  add     rdx, r9
0x180013351  cmp     r9, rdx
0x180013354  jz      short loc_180013370
0x180013356  mov     r8d, [rbx+10h]
0x18001335a  cmp     [rcx+4], r8d
0x18001335e  jbe     short loc_180013368
0x180013360  mov     eax, [rdi+8]
0x180013363  cmp     [rcx+8], eax
0x180013366  jz      short loc_1800133AA
0x180013368  add     rcx, rbp
0x18001336b  cmp     rcx, rdx
0x18001336e  jnz     short loc_18001335A
0x180013370  movzx   eax, word ptr [rbx+22h]
0x180013374  xor     edx, edx
0x180013376  movzx   ecx, word ptr [rbx+20h]
0x18001337a  inc     eax
0x18001337c  div     ecx
0x18001337e  mov     rax, [rbx+8]
0x180013382  mov     r8d, 1
0x180013388  mov     [rbx+22h], dx
0x18001338c  lock xadd [rax], r8d
0x180013391  movzx   eax, dx
0x180013394  inc     r8d; unsigned int
0x180013397  mov     rdx, rdi; struct wil::FailureInfo *
0x18001339a  lea     rcx, [rax+rax*4]
0x18001339e  shl     rcx, 4
0x1800133a2  add     rcx, r9; this
0x1800133a5  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800133aa  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800133b4  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800133bb  add     rsp, 20h
0x1800133bf  pop     r14
0x1800133c1  pop     rdi
0x1800133c2  pop     rsi
0x1800133c3  pop     rbp
0x1800133c4  pop     rbx
0x1800133c5  retn
```
