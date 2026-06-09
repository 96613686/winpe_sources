# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800041f0`
- end: `0x1800043f7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800041f0`
- `0x1800048ec`
- `0x1800049d0`
- `0x180005248`
- `0x180005614`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000421a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800042dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000421a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800042dc`

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
0x1800041f0  push    rbx
0x1800041f2  push    rbp
0x1800041f3  push    rsi
0x1800041f4  push    rdi
0x1800041f5  push    r14
0x1800041f7  sub     rsp, 20h
0x1800041fb  mov     r14, r8
0x1800041fe  mov     rsi, rdx
0x180004201  mov     rdi, rcx
0x180004204  mov     byte ptr [rdx], 0
0x180004207  xor     bpl, bpl
0x18000420a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004211  test    rbx, rbx
0x180004214  jz      loc_1800042B0
0x18000421a  call    cs:__imp_GetCurrentThreadId
0x180004220  mov     r9d, eax
0x180004223  mov     r8d, eax
0x180004226  shr     r8, 2
0x18000422a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004234  mul     r8
0x180004237  shr     rdx, 3
0x18000423b  lea     rcx, [rdx+rdx*4]
0x18000423f  add     rcx, rcx
0x180004242  sub     r8, rcx
0x180004245  mov     rbx, [rbx+r8*8]
0x180004249  jmp     short loc_180004254
0x18000424b  cmp     [rbx], r9d
0x18000424e  jz      short loc_1800042CB
0x180004250  mov     rbx, [rbx+8]
0x180004254  test    rbx, rbx
0x180004257  jnz     short loc_18000424B
0x180004259  test    rbx, rbx
0x18000425c  jz      short loc_1800042B0
0x18000425e  cmp     qword ptr [rbx], 0
0x180004262  jz      short loc_1800042B0
0x180004264  mov     [rsi], bpl
0x180004267  mov     r9, r14; unsigned __int64
0x18000426a  mov     r8, rsi; char *
0x18000426d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004270  mov     rcx, rdi; struct wil::FailureInfo *
0x180004273  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004278  test    al, al
0x18000427a  jz      short loc_180004280
0x18000427c  mov     [rdi+48h], rsi
0x180004280  mov     rbx, [rbx]
0x180004283  mov     al, [rbx+28h]
0x180004286  mov     byte ptr [rbx+28h], 1
0x18000428a  test    al, al
0x18000428c  jnz     short loc_1800042A7
0x18000428e  mov     rcx, [rbx+8]
0x180004292  mov     rax, [rcx]
0x180004295  mov     rdx, rdi
0x180004298  mov     rax, [rax]
0x18000429b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042a0  or      bpl, al
0x1800042a3  mov     byte ptr [rbx+28h], 0
0x1800042a7  mov     rbx, [rbx+10h]
0x1800042ab  test    rbx, rbx
0x1800042ae  jnz     short loc_180004283
0x1800042b0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800042b7  test    rax, rax
0x1800042ba  jz      short loc_1800042DC
0x1800042bc  test    bpl, bpl
0x1800042bf  jnz     short loc_1800042D1
0x1800042c1  test    byte ptr [rdi+4], 2
0x1800042c5  jnz     short loc_1800042D1
0x1800042c7  xor     ecx, ecx
0x1800042c9  jmp     short loc_1800042D3
0x1800042cb  add     rbx, 10h
0x1800042cf  jmp     short loc_180004259
0x1800042d1  mov     cl, 1
0x1800042d3  mov     rdx, rdi
0x1800042d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042db  nop
0x1800042dc  call    cs:__imp_GetCurrentThreadId
0x1800042e2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800042e8  cmp     ecx, eax
0x1800042ea  jz      loc_1800043EC
0x1800042f0  mov     ecx, 1
0x1800042f5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800042fd  inc     ecx; this
0x1800042ff  cmp     ecx, 4
0x180004302  jge     loc_1800043E5
0x180004308  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000430e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180004313  mov     rbx, rax
0x180004316  test    rax, rax
0x180004319  jz      loc_1800043DB
0x18000431f  mov     esi, [rax+10h]
0x180004322  mov     ebp, 50h ; 'P'
0x180004327  cmp     qword ptr [rax+18h], 0
0x18000432c  jnz     short loc_180004363
0x18000432e  test    esi, esi
0x180004330  jz      short loc_180004363
0x180004332  mov     edx, 190h; dwBytes
0x180004337  lea     ecx, [rbp-48h]; dwFlags
0x18000433a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000433f  mov     [rbx+18h], rax
0x180004343  test    rax, rax
0x180004346  jz      short loc_180004363
0x180004348  mov     dword ptr [rbx+20h], 5
0x18000434f  lea     rcx, [rax+190h]
0x180004356  jmp     short loc_18000435E
0x180004358  mov     [rax], bp
0x18000435b  add     rax, rbp
0x18000435e  cmp     rax, rcx
0x180004361  jnz     short loc_180004358
0x180004363  mov     r9, [rbx+18h]
0x180004367  test    r9, r9
0x18000436a  jz      short loc_1800043DB
0x18000436c  test    esi, esi
0x18000436e  jz      short loc_1800043A1
0x180004370  mov     rcx, r9
0x180004373  movzx   eax, word ptr [rbx+20h]
0x180004377  lea     rdx, [rax+rax*4]
0x18000437b  shl     rdx, 4
0x18000437f  add     rdx, r9
0x180004382  cmp     r9, rdx
0x180004385  jz      short loc_1800043A1
0x180004387  mov     r8d, [rbx+10h]
0x18000438b  cmp     [rcx+4], r8d
0x18000438f  jbe     short loc_180004399
0x180004391  mov     eax, [rdi+8]
0x180004394  cmp     [rcx+8], eax
0x180004397  jz      short loc_1800043DB
0x180004399  add     rcx, rbp
0x18000439c  cmp     rcx, rdx
0x18000439f  jnz     short loc_18000438B
0x1800043a1  movzx   eax, word ptr [rbx+22h]
0x1800043a5  inc     eax
0x1800043a7  movzx   ecx, word ptr [rbx+20h]
0x1800043ab  xor     edx, edx
0x1800043ad  div     ecx
0x1800043af  mov     [rbx+22h], dx
0x1800043b3  mov     rax, [rbx+8]
0x1800043b7  mov     r8d, 1
0x1800043bd  lock xadd [rax], r8d
0x1800043c2  inc     r8d; unsigned int
0x1800043c5  movzx   eax, dx
0x1800043c8  lea     rcx, [rax+rax*4]
0x1800043cc  shl     rcx, 4
0x1800043d0  add     rcx, r9; this
0x1800043d3  mov     rdx, rdi; struct wil::FailureInfo *
0x1800043d6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800043db  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800043e5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800043ec  add     rsp, 20h
0x1800043f0  pop     r14
0x1800043f2  pop     rdi
0x1800043f3  pop     rsi
0x1800043f4  pop     rbp
0x1800043f5  pop     rbx
0x1800043f6  retn
```
