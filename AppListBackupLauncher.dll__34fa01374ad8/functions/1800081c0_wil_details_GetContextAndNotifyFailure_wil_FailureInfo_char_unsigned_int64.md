# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800081c0`
- end: `0x1800083c7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800081c0`
- `0x180008bb0`
- `0x180008c94`
- `0x180009ccc`
- `0x18000c0a4`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800081ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800082ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800081ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800082ac`

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
0x1800081c0  push    rbx
0x1800081c2  push    rbp
0x1800081c3  push    rsi
0x1800081c4  push    rdi
0x1800081c5  push    r14
0x1800081c7  sub     rsp, 20h
0x1800081cb  mov     r14, r8
0x1800081ce  mov     rsi, rdx
0x1800081d1  mov     rdi, rcx
0x1800081d4  mov     byte ptr [rdx], 0
0x1800081d7  xor     bpl, bpl
0x1800081da  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800081e1  test    rbx, rbx
0x1800081e4  jz      loc_180008280
0x1800081ea  call    cs:__imp_GetCurrentThreadId
0x1800081f0  mov     r9d, eax
0x1800081f3  mov     r8d, eax
0x1800081f6  shr     r8, 2
0x1800081fa  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180008204  mul     r8
0x180008207  shr     rdx, 3
0x18000820b  lea     rcx, [rdx+rdx*4]
0x18000820f  add     rcx, rcx
0x180008212  sub     r8, rcx
0x180008215  mov     rbx, [rbx+r8*8]
0x180008219  jmp     short loc_180008224
0x18000821b  cmp     [rbx], r9d
0x18000821e  jz      short loc_18000829B
0x180008220  mov     rbx, [rbx+8]
0x180008224  test    rbx, rbx
0x180008227  jnz     short loc_18000821B
0x180008229  test    rbx, rbx
0x18000822c  jz      short loc_180008280
0x18000822e  cmp     qword ptr [rbx], 0
0x180008232  jz      short loc_180008280
0x180008234  mov     [rsi], bpl
0x180008237  mov     r9, r14; unsigned __int64
0x18000823a  mov     r8, rsi; char *
0x18000823d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180008240  mov     rcx, rdi; struct wil::FailureInfo *
0x180008243  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180008248  test    al, al
0x18000824a  jz      short loc_180008250
0x18000824c  mov     [rdi+48h], rsi
0x180008250  mov     rbx, [rbx]
0x180008253  mov     al, [rbx+28h]
0x180008256  mov     byte ptr [rbx+28h], 1
0x18000825a  test    al, al
0x18000825c  jnz     short loc_180008277
0x18000825e  mov     rcx, [rbx+8]
0x180008262  mov     rax, [rcx]
0x180008265  mov     rdx, rdi
0x180008268  mov     rax, [rax]
0x18000826b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008270  or      bpl, al
0x180008273  mov     byte ptr [rbx+28h], 0
0x180008277  mov     rbx, [rbx+10h]
0x18000827b  test    rbx, rbx
0x18000827e  jnz     short loc_180008253
0x180008280  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180008287  test    rax, rax
0x18000828a  jz      short loc_1800082AC
0x18000828c  test    bpl, bpl
0x18000828f  jnz     short loc_1800082A1
0x180008291  test    byte ptr [rdi+4], 2
0x180008295  jnz     short loc_1800082A1
0x180008297  xor     ecx, ecx
0x180008299  jmp     short loc_1800082A3
0x18000829b  add     rbx, 10h
0x18000829f  jmp     short loc_180008229
0x1800082a1  mov     cl, 1
0x1800082a3  mov     rdx, rdi
0x1800082a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082ab  nop
0x1800082ac  call    cs:__imp_GetCurrentThreadId
0x1800082b2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800082b8  cmp     ecx, eax
0x1800082ba  jz      loc_1800083BC
0x1800082c0  mov     ecx, 1
0x1800082c5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800082cd  inc     ecx; this
0x1800082cf  cmp     ecx, 4
0x1800082d2  jge     loc_1800083B5
0x1800082d8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800082de  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800082e3  mov     rbx, rax
0x1800082e6  test    rax, rax
0x1800082e9  jz      loc_1800083AB
0x1800082ef  mov     esi, [rax+10h]
0x1800082f2  mov     ebp, 50h ; 'P'
0x1800082f7  cmp     qword ptr [rax+18h], 0
0x1800082fc  jnz     short loc_180008333
0x1800082fe  test    esi, esi
0x180008300  jz      short loc_180008333
0x180008302  mov     edx, 190h; dwBytes
0x180008307  lea     ecx, [rbp-48h]; dwFlags
0x18000830a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000830f  mov     [rbx+18h], rax
0x180008313  test    rax, rax
0x180008316  jz      short loc_180008333
0x180008318  mov     dword ptr [rbx+20h], 5
0x18000831f  lea     rcx, [rax+190h]
0x180008326  jmp     short loc_18000832E
0x180008328  mov     [rax], bp
0x18000832b  add     rax, rbp
0x18000832e  cmp     rax, rcx
0x180008331  jnz     short loc_180008328
0x180008333  mov     r9, [rbx+18h]
0x180008337  test    r9, r9
0x18000833a  jz      short loc_1800083AB
0x18000833c  test    esi, esi
0x18000833e  jz      short loc_180008371
0x180008340  mov     rcx, r9
0x180008343  movzx   eax, word ptr [rbx+20h]
0x180008347  lea     rdx, [rax+rax*4]
0x18000834b  shl     rdx, 4
0x18000834f  add     rdx, r9
0x180008352  cmp     r9, rdx
0x180008355  jz      short loc_180008371
0x180008357  mov     r8d, [rbx+10h]
0x18000835b  cmp     [rcx+4], r8d
0x18000835f  jbe     short loc_180008369
0x180008361  mov     eax, [rdi+8]
0x180008364  cmp     [rcx+8], eax
0x180008367  jz      short loc_1800083AB
0x180008369  add     rcx, rbp
0x18000836c  cmp     rcx, rdx
0x18000836f  jnz     short loc_18000835B
0x180008371  movzx   eax, word ptr [rbx+22h]
0x180008375  inc     eax
0x180008377  movzx   ecx, word ptr [rbx+20h]
0x18000837b  xor     edx, edx
0x18000837d  div     ecx
0x18000837f  mov     [rbx+22h], dx
0x180008383  mov     rax, [rbx+8]
0x180008387  mov     r8d, 1
0x18000838d  lock xadd [rax], r8d
0x180008392  inc     r8d; unsigned int
0x180008395  movzx   eax, dx
0x180008398  lea     rcx, [rax+rax*4]
0x18000839c  shl     rcx, 4
0x1800083a0  add     rcx, r9; this
0x1800083a3  mov     rdx, rdi; struct wil::FailureInfo *
0x1800083a6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800083ab  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800083b5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800083bc  add     rsp, 20h
0x1800083c0  pop     r14
0x1800083c2  pop     rdi
0x1800083c3  pop     rsi
0x1800083c4  pop     rbp
0x1800083c5  pop     rbx
0x1800083c6  retn
```
