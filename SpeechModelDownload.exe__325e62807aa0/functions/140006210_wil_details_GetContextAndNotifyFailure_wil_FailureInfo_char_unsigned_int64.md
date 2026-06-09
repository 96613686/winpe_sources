# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140006210`
- end: `0x140006417`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140006210`
- `0x140006ac0`
- `0x140006ba4`
- `0x14000770c`
- `0x140007eb4`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000623a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400062fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000623a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400062fc`

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
0x140006210  push    rbx
0x140006212  push    rbp
0x140006213  push    rsi
0x140006214  push    rdi
0x140006215  push    r14
0x140006217  sub     rsp, 20h
0x14000621b  mov     r14, r8
0x14000621e  mov     rsi, rdx
0x140006221  mov     rdi, rcx
0x140006224  mov     byte ptr [rdx], 0
0x140006227  xor     bpl, bpl
0x14000622a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140006231  test    rbx, rbx
0x140006234  jz      loc_1400062D0
0x14000623a  call    cs:__imp_GetCurrentThreadId
0x140006240  mov     r9d, eax
0x140006243  mov     r8d, eax
0x140006246  shr     r8, 2
0x14000624a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140006254  mul     r8
0x140006257  shr     rdx, 3
0x14000625b  lea     rcx, [rdx+rdx*4]
0x14000625f  add     rcx, rcx
0x140006262  sub     r8, rcx
0x140006265  mov     rbx, [rbx+r8*8]
0x140006269  jmp     short loc_140006274
0x14000626b  cmp     [rbx], r9d
0x14000626e  jz      short loc_1400062EB
0x140006270  mov     rbx, [rbx+8]
0x140006274  test    rbx, rbx
0x140006277  jnz     short loc_14000626B
0x140006279  test    rbx, rbx
0x14000627c  jz      short loc_1400062D0
0x14000627e  cmp     qword ptr [rbx], 0
0x140006282  jz      short loc_1400062D0
0x140006284  mov     [rsi], bpl
0x140006287  mov     r9, r14; unsigned __int64
0x14000628a  mov     r8, rsi; char *
0x14000628d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x140006290  mov     rcx, rdi; struct wil::FailureInfo *
0x140006293  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140006298  test    al, al
0x14000629a  jz      short loc_1400062A0
0x14000629c  mov     [rdi+48h], rsi
0x1400062a0  mov     rbx, [rbx]
0x1400062a3  mov     al, [rbx+28h]
0x1400062a6  mov     byte ptr [rbx+28h], 1
0x1400062aa  test    al, al
0x1400062ac  jnz     short loc_1400062C7
0x1400062ae  mov     rcx, [rbx+8]
0x1400062b2  mov     rax, [rcx]
0x1400062b5  mov     rdx, rdi
0x1400062b8  mov     rax, [rax]
0x1400062bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400062c0  or      bpl, al
0x1400062c3  mov     byte ptr [rbx+28h], 0
0x1400062c7  mov     rbx, [rbx+10h]
0x1400062cb  test    rbx, rbx
0x1400062ce  jnz     short loc_1400062A3
0x1400062d0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1400062d7  test    rax, rax
0x1400062da  jz      short loc_1400062FC
0x1400062dc  test    bpl, bpl
0x1400062df  jnz     short loc_1400062F1
0x1400062e1  test    byte ptr [rdi+4], 2
0x1400062e5  jnz     short loc_1400062F1
0x1400062e7  xor     ecx, ecx
0x1400062e9  jmp     short loc_1400062F3
0x1400062eb  add     rbx, 10h
0x1400062ef  jmp     short loc_140006279
0x1400062f1  mov     cl, 1
0x1400062f3  mov     rdx, rdi
0x1400062f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400062fb  nop
0x1400062fc  call    cs:__imp_GetCurrentThreadId
0x140006302  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140006308  cmp     ecx, eax
0x14000630a  jz      loc_14000640C
0x140006310  mov     ecx, 1
0x140006315  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000631d  inc     ecx; this
0x14000631f  cmp     ecx, 4
0x140006322  jge     loc_140006405
0x140006328  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14000632e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140006333  mov     rbx, rax
0x140006336  test    rax, rax
0x140006339  jz      loc_1400063FB
0x14000633f  mov     esi, [rax+10h]
0x140006342  mov     ebp, 50h ; 'P'
0x140006347  cmp     qword ptr [rax+18h], 0
0x14000634c  jnz     short loc_140006383
0x14000634e  test    esi, esi
0x140006350  jz      short loc_140006383
0x140006352  mov     edx, 190h; dwBytes
0x140006357  lea     ecx, [rbp-48h]; dwFlags
0x14000635a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000635f  mov     [rbx+18h], rax
0x140006363  test    rax, rax
0x140006366  jz      short loc_140006383
0x140006368  mov     dword ptr [rbx+20h], 5
0x14000636f  lea     rcx, [rax+190h]
0x140006376  jmp     short loc_14000637E
0x140006378  mov     [rax], bp
0x14000637b  add     rax, rbp
0x14000637e  cmp     rax, rcx
0x140006381  jnz     short loc_140006378
0x140006383  mov     r9, [rbx+18h]
0x140006387  test    r9, r9
0x14000638a  jz      short loc_1400063FB
0x14000638c  test    esi, esi
0x14000638e  jz      short loc_1400063C1
0x140006390  mov     rcx, r9
0x140006393  movzx   eax, word ptr [rbx+20h]
0x140006397  lea     rdx, [rax+rax*4]
0x14000639b  shl     rdx, 4
0x14000639f  add     rdx, r9
0x1400063a2  cmp     r9, rdx
0x1400063a5  jz      short loc_1400063C1
0x1400063a7  mov     r8d, [rbx+10h]
0x1400063ab  cmp     [rcx+4], r8d
0x1400063af  jbe     short loc_1400063B9
0x1400063b1  mov     eax, [rdi+8]
0x1400063b4  cmp     [rcx+8], eax
0x1400063b7  jz      short loc_1400063FB
0x1400063b9  add     rcx, rbp
0x1400063bc  cmp     rcx, rdx
0x1400063bf  jnz     short loc_1400063AB
0x1400063c1  movzx   eax, word ptr [rbx+22h]
0x1400063c5  inc     eax
0x1400063c7  movzx   ecx, word ptr [rbx+20h]
0x1400063cb  xor     edx, edx
0x1400063cd  div     ecx
0x1400063cf  mov     [rbx+22h], dx
0x1400063d3  mov     rax, [rbx+8]
0x1400063d7  mov     r8d, 1
0x1400063dd  lock xadd [rax], r8d
0x1400063e2  inc     r8d; unsigned int
0x1400063e5  movzx   eax, dx
0x1400063e8  lea     rcx, [rax+rax*4]
0x1400063ec  shl     rcx, 4
0x1400063f0  add     rcx, r9; this
0x1400063f3  mov     rdx, rdi; struct wil::FailureInfo *
0x1400063f6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1400063fb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140006405  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000640c  add     rsp, 20h
0x140006410  pop     r14
0x140006412  pop     rdi
0x140006413  pop     rsi
0x140006414  pop     rbp
0x140006415  pop     rbx
0x140006416  retn
```
