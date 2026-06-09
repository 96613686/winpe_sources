# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180008370`
- end: `0x18000857a`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `522`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000650c`
- `0x180007f08`
- `0x1800081a8`
- `0x180008268`
- `0x180008370`
- `0x18005c5e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800083a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008457`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800083a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008457`

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
  struct wil::details::ThreadFailureCallbackHolder **v10; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v11; // rbx
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
    this = 10 * (CurrentThreadId / 0xA);
    for ( i = *(_QWORD *)(v7 + 8 * (CurrentThreadId % 0xA)); ; i = *(_QWORD *)(i + 8) )
    {
      if ( !i )
      {
        v10 = 0;
        goto LABEL_7;
      }
      if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
        break;
    }
    v10 = (struct wil::details::ThreadFailureCallbackHolder **)(i + 16);
LABEL_7:
    if ( v10 && *v10 )
    {
      *(_BYTE *)a2 = 0;
      if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(v5, *v10, (char *)a2, (unsigned __int64)a3) )
        *((_QWORD *)v5 + 9) = a2;
      v11 = *v10;
      do
      {
        v6 |= (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v11 + 1))(*((_QWORD *)v11 + 1), v5);
        v11 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v11 + 2);
      }
      while ( v11 );
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( v6 || (LOBYTE(this) = 0, (*((_BYTE *)v5 + 4) & 2) != 0) )
      LOBYTE(this) = 1;
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
LABEL_34:
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
                goto LABEL_34;
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
0x180008370  mov     [rsp+arg_18], rbx
0x180008375  push    rbp
0x180008376  push    rsi
0x180008377  push    rdi
0x180008378  push    r14
0x18000837a  push    r15
0x18000837c  sub     rsp, 20h
0x180008380  mov     r14, r8
0x180008383  mov     rsi, rdx
0x180008386  mov     rdi, rcx
0x180008389  xor     r15d, r15d
0x18000838c  mov     [rdx], r15b
0x18000838f  mov     bpl, r15b
0x180008392  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180008399  test    rbx, rbx
0x18000839c  jz      loc_18000842B
0x1800083a2  call    cs:__imp_GetCurrentThreadId
0x1800083a8  mov     r9d, eax
0x1800083ab  mov     r8d, eax
0x1800083ae  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800083b8  mul     r9
0x1800083bb  shr     rdx, 3
0x1800083bf  lea     rcx, [rdx+rdx*4]
0x1800083c3  add     rcx, rcx
0x1800083c6  sub     r8, rcx
0x1800083c9  mov     rbx, [rbx+r8*8]
0x1800083cd  jmp     short loc_1800083DC
0x1800083cf  cmp     [rbx], r9d
0x1800083d2  jz      loc_1800084D1
0x1800083d8  mov     rbx, [rbx+8]
0x1800083dc  test    rbx, rbx
0x1800083df  jnz     short loc_1800083CF
0x1800083e1  mov     rbx, r15
0x1800083e4  test    rbx, rbx
0x1800083e7  jz      short loc_18000842B
0x1800083e9  cmp     [rbx], r15
0x1800083ec  jz      short loc_18000842B
0x1800083ee  mov     [rsi], r15b
0x1800083f1  mov     r9, r14; unsigned __int64
0x1800083f4  mov     r8, rsi; char *
0x1800083f7  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800083fa  mov     rcx, rdi; struct wil::FailureInfo *
0x1800083fd  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180008402  test    al, al
0x180008404  jz      short loc_18000840A
0x180008406  mov     [rdi+48h], rsi
0x18000840a  mov     rbx, [rbx]
0x18000840d  mov     rcx, [rbx+8]
0x180008411  mov     rax, [rcx]
0x180008414  mov     rdx, rdi
0x180008417  mov     rax, [rax]
0x18000841a  call    _guard_dispatch_icall
0x18000841f  or      bpl, al
0x180008422  mov     rbx, [rbx+10h]
0x180008426  test    rbx, rbx
0x180008429  jnz     short loc_18000840D
0x18000842b  mov     r14d, 1
0x180008431  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180008438  test    rax, rax
0x18000843b  jz      short loc_180008457
0x18000843d  test    bpl, bpl
0x180008440  jnz     short loc_18000844B
0x180008442  test    byte ptr [rdi+4], 2
0x180008446  mov     cl, r15b
0x180008449  jz      short loc_18000844E
0x18000844b  mov     cl, r14b
0x18000844e  mov     rdx, rdi
0x180008451  call    _guard_dispatch_icall
0x180008456  nop
0x180008457  call    cs:__imp_GetCurrentThreadId
0x18000845d  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180008463  cmp     ecx, eax
0x180008465  jz      loc_180008569
0x18000846b  mov     ecx, r14d
0x18000846e  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180008476  add     ecx, r14d; this
0x180008479  cmp     ecx, 4
0x18000847c  jge     loc_180008562
0x180008482  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180008488  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000848d  mov     rbx, rax
0x180008490  test    rax, rax
0x180008493  jz      loc_18000855B
0x180008499  mov     esi, [rax+10h]
0x18000849c  mov     ebp, 50h ; 'P'
0x1800084a1  cmp     [rax+18h], r15
0x1800084a5  jnz     short loc_1800084E5
0x1800084a7  test    esi, esi
0x1800084a9  jz      short loc_1800084E5
0x1800084ab  mov     edx, 190h; dwBytes
0x1800084b0  lea     ecx, [rbp-48h]; dwFlags
0x1800084b3  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800084b8  mov     [rbx+18h], rax
0x1800084bc  test    rax, rax
0x1800084bf  jz      short loc_1800084E5
0x1800084c1  mov     dword ptr [rbx+20h], 5
0x1800084c8  lea     rcx, [rax+190h]
0x1800084cf  jmp     short loc_1800084E0
0x1800084d1  add     rbx, 10h
0x1800084d5  jmp     loc_1800083E4
0x1800084da  mov     [rax], bp
0x1800084dd  add     rax, rbp
0x1800084e0  cmp     rax, rcx
0x1800084e3  jnz     short loc_1800084DA
0x1800084e5  mov     r9, [rbx+18h]
0x1800084e9  test    r9, r9
0x1800084ec  jz      short loc_18000855B
0x1800084ee  test    esi, esi
0x1800084f0  jz      short loc_180008523
0x1800084f2  mov     rcx, r9
0x1800084f5  movzx   eax, word ptr [rbx+20h]
0x1800084f9  lea     rdx, [rax+rax*4]
0x1800084fd  shl     rdx, 4
0x180008501  add     rdx, r9
0x180008504  cmp     r9, rdx
0x180008507  jz      short loc_180008523
0x180008509  mov     r8d, [rbx+10h]
0x18000850d  cmp     [rcx+4], r8d
0x180008511  jbe     short loc_18000851B
0x180008513  mov     eax, [rdi+8]
0x180008516  cmp     [rcx+8], eax
0x180008519  jz      short loc_18000855B
0x18000851b  add     rcx, rbp
0x18000851e  cmp     rcx, rdx
0x180008521  jnz     short loc_18000850D
0x180008523  movzx   eax, word ptr [rbx+22h]
0x180008527  add     eax, r14d
0x18000852a  movzx   ecx, word ptr [rbx+20h]
0x18000852e  xor     edx, edx
0x180008530  div     ecx
0x180008532  mov     [rbx+22h], dx
0x180008536  mov     rax, [rbx+8]
0x18000853a  mov     r8d, r14d
0x18000853d  lock xadd [rax], r8d
0x180008542  add     r8d, r14d; unsigned int
0x180008545  movzx   eax, dx
0x180008548  lea     rcx, [rax+rax*4]
0x18000854c  shl     rcx, 4
0x180008550  add     rcx, r9; this
0x180008553  mov     rdx, rdi; struct wil::FailureInfo *
0x180008556  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000855b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, r15d; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180008562  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180008569  mov     rbx, [rsp+48h+arg_18]
0x18000856e  add     rsp, 20h
0x180008572  pop     r15
0x180008574  pop     r14
0x180008576  pop     rdi
0x180008577  pop     rsi
0x180008578  pop     rbp
0x180008579  retn
```
