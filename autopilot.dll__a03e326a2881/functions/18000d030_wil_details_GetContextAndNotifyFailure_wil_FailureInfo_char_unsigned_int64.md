# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000d030`
- end: `0x18000d237`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000d030`
- `0x18000d830`
- `0x18000d914`
- `0x18000e6bc`
- `0x1800106e4`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d05a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d11c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d05a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d11c`

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
0x18000d030  push    rbx
0x18000d032  push    rbp
0x18000d033  push    rsi
0x18000d034  push    rdi
0x18000d035  push    r14
0x18000d037  sub     rsp, 20h
0x18000d03b  mov     r14, r8
0x18000d03e  mov     rsi, rdx
0x18000d041  mov     rdi, rcx
0x18000d044  mov     byte ptr [rdx], 0
0x18000d047  xor     bpl, bpl
0x18000d04a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000d051  test    rbx, rbx
0x18000d054  jz      loc_18000D0F0
0x18000d05a  call    cs:__imp_GetCurrentThreadId
0x18000d060  mov     r9d, eax
0x18000d063  mov     r8d, eax
0x18000d066  shr     r8, 2
0x18000d06a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000d074  mul     r8
0x18000d077  shr     rdx, 3
0x18000d07b  lea     rcx, [rdx+rdx*4]
0x18000d07f  add     rcx, rcx
0x18000d082  sub     r8, rcx
0x18000d085  mov     rbx, [rbx+r8*8]
0x18000d089  jmp     short loc_18000D094
0x18000d08b  cmp     [rbx], r9d
0x18000d08e  jz      short loc_18000D10B
0x18000d090  mov     rbx, [rbx+8]
0x18000d094  test    rbx, rbx
0x18000d097  jnz     short loc_18000D08B
0x18000d099  test    rbx, rbx
0x18000d09c  jz      short loc_18000D0F0
0x18000d09e  cmp     qword ptr [rbx], 0
0x18000d0a2  jz      short loc_18000D0F0
0x18000d0a4  mov     [rsi], bpl
0x18000d0a7  mov     r9, r14; unsigned __int64
0x18000d0aa  mov     r8, rsi; char *
0x18000d0ad  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000d0b0  mov     rcx, rdi; struct wil::FailureInfo *
0x18000d0b3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000d0b8  test    al, al
0x18000d0ba  jz      short loc_18000D0C0
0x18000d0bc  mov     [rdi+48h], rsi
0x18000d0c0  mov     rbx, [rbx]
0x18000d0c3  mov     al, [rbx+28h]
0x18000d0c6  mov     byte ptr [rbx+28h], 1
0x18000d0ca  test    al, al
0x18000d0cc  jnz     short loc_18000D0E7
0x18000d0ce  mov     rcx, [rbx+8]
0x18000d0d2  mov     rax, [rcx]
0x18000d0d5  mov     rdx, rdi
0x18000d0d8  mov     rax, [rax]
0x18000d0db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0e0  or      bpl, al
0x18000d0e3  mov     byte ptr [rbx+28h], 0
0x18000d0e7  mov     rbx, [rbx+10h]
0x18000d0eb  test    rbx, rbx
0x18000d0ee  jnz     short loc_18000D0C3
0x18000d0f0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000d0f7  test    rax, rax
0x18000d0fa  jz      short loc_18000D11C
0x18000d0fc  test    bpl, bpl
0x18000d0ff  jnz     short loc_18000D111
0x18000d101  test    byte ptr [rdi+4], 2
0x18000d105  jnz     short loc_18000D111
0x18000d107  xor     ecx, ecx
0x18000d109  jmp     short loc_18000D113
0x18000d10b  add     rbx, 10h
0x18000d10f  jmp     short loc_18000D099
0x18000d111  mov     cl, 1
0x18000d113  mov     rdx, rdi
0x18000d116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d11b  nop
0x18000d11c  call    cs:__imp_GetCurrentThreadId
0x18000d122  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000d128  cmp     ecx, eax
0x18000d12a  jz      loc_18000D22C
0x18000d130  mov     ecx, 1
0x18000d135  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000d13d  inc     ecx; this
0x18000d13f  cmp     ecx, 4
0x18000d142  jge     loc_18000D225
0x18000d148  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000d14e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000d153  mov     rbx, rax
0x18000d156  test    rax, rax
0x18000d159  jz      loc_18000D21B
0x18000d15f  mov     esi, [rax+10h]
0x18000d162  mov     ebp, 50h ; 'P'
0x18000d167  cmp     qword ptr [rax+18h], 0
0x18000d16c  jnz     short loc_18000D1A3
0x18000d16e  test    esi, esi
0x18000d170  jz      short loc_18000D1A3
0x18000d172  mov     edx, 190h; dwBytes
0x18000d177  lea     ecx, [rbp-48h]; dwFlags
0x18000d17a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000d17f  mov     [rbx+18h], rax
0x18000d183  test    rax, rax
0x18000d186  jz      short loc_18000D1A3
0x18000d188  mov     dword ptr [rbx+20h], 5
0x18000d18f  lea     rcx, [rax+190h]
0x18000d196  jmp     short loc_18000D19E
0x18000d198  mov     [rax], bp
0x18000d19b  add     rax, rbp
0x18000d19e  cmp     rax, rcx
0x18000d1a1  jnz     short loc_18000D198
0x18000d1a3  mov     r9, [rbx+18h]
0x18000d1a7  test    r9, r9
0x18000d1aa  jz      short loc_18000D21B
0x18000d1ac  test    esi, esi
0x18000d1ae  jz      short loc_18000D1E1
0x18000d1b0  mov     rcx, r9
0x18000d1b3  movzx   eax, word ptr [rbx+20h]
0x18000d1b7  lea     rdx, [rax+rax*4]
0x18000d1bb  shl     rdx, 4
0x18000d1bf  add     rdx, r9
0x18000d1c2  cmp     r9, rdx
0x18000d1c5  jz      short loc_18000D1E1
0x18000d1c7  mov     r8d, [rbx+10h]
0x18000d1cb  cmp     [rcx+4], r8d
0x18000d1cf  jbe     short loc_18000D1D9
0x18000d1d1  mov     eax, [rdi+8]
0x18000d1d4  cmp     [rcx+8], eax
0x18000d1d7  jz      short loc_18000D21B
0x18000d1d9  add     rcx, rbp
0x18000d1dc  cmp     rcx, rdx
0x18000d1df  jnz     short loc_18000D1CB
0x18000d1e1  movzx   eax, word ptr [rbx+22h]
0x18000d1e5  inc     eax
0x18000d1e7  movzx   ecx, word ptr [rbx+20h]
0x18000d1eb  xor     edx, edx
0x18000d1ed  div     ecx
0x18000d1ef  mov     [rbx+22h], dx
0x18000d1f3  mov     rax, [rbx+8]
0x18000d1f7  mov     r8d, 1
0x18000d1fd  lock xadd [rax], r8d
0x18000d202  inc     r8d; unsigned int
0x18000d205  movzx   eax, dx
0x18000d208  lea     rcx, [rax+rax*4]
0x18000d20c  shl     rcx, 4
0x18000d210  add     rcx, r9; this
0x18000d213  mov     rdx, rdi; struct wil::FailureInfo *
0x18000d216  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000d21b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000d225  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000d22c  add     rsp, 20h
0x18000d230  pop     r14
0x18000d232  pop     rdi
0x18000d233  pop     rsi
0x18000d234  pop     rbp
0x18000d235  pop     rbx
0x18000d236  retn
```
