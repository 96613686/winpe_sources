# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180005210`
- end: `0x180005417`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180005210`
- `0x18000590c`
- `0x1800059f0`
- `0x180006478`
- `0x180007cd4`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000523a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800052fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000523a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800052fc`

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
0x180005210  push    rbx
0x180005212  push    rbp
0x180005213  push    rsi
0x180005214  push    rdi
0x180005215  push    r14
0x180005217  sub     rsp, 20h
0x18000521b  mov     r14, r8
0x18000521e  mov     rsi, rdx
0x180005221  mov     rdi, rcx
0x180005224  mov     byte ptr [rdx], 0
0x180005227  xor     bpl, bpl
0x18000522a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005231  test    rbx, rbx
0x180005234  jz      loc_1800052D0
0x18000523a  call    cs:__imp_GetCurrentThreadId
0x180005240  mov     r9d, eax
0x180005243  mov     r8d, eax
0x180005246  shr     r8, 2
0x18000524a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005254  mul     r8
0x180005257  shr     rdx, 3
0x18000525b  lea     rcx, [rdx+rdx*4]
0x18000525f  add     rcx, rcx
0x180005262  sub     r8, rcx
0x180005265  mov     rbx, [rbx+r8*8]
0x180005269  jmp     short loc_180005274
0x18000526b  cmp     [rbx], r9d
0x18000526e  jz      short loc_1800052EB
0x180005270  mov     rbx, [rbx+8]
0x180005274  test    rbx, rbx
0x180005277  jnz     short loc_18000526B
0x180005279  test    rbx, rbx
0x18000527c  jz      short loc_1800052D0
0x18000527e  cmp     qword ptr [rbx], 0
0x180005282  jz      short loc_1800052D0
0x180005284  mov     [rsi], bpl
0x180005287  mov     r9, r14; unsigned __int64
0x18000528a  mov     r8, rsi; char *
0x18000528d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180005290  mov     rcx, rdi; struct wil::FailureInfo *
0x180005293  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005298  test    al, al
0x18000529a  jz      short loc_1800052A0
0x18000529c  mov     [rdi+48h], rsi
0x1800052a0  mov     rbx, [rbx]
0x1800052a3  mov     al, [rbx+28h]
0x1800052a6  mov     byte ptr [rbx+28h], 1
0x1800052aa  test    al, al
0x1800052ac  jnz     short loc_1800052C7
0x1800052ae  mov     rcx, [rbx+8]
0x1800052b2  mov     rax, [rcx]
0x1800052b5  mov     rdx, rdi
0x1800052b8  mov     rax, [rax]
0x1800052bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052c0  or      bpl, al
0x1800052c3  mov     byte ptr [rbx+28h], 0
0x1800052c7  mov     rbx, [rbx+10h]
0x1800052cb  test    rbx, rbx
0x1800052ce  jnz     short loc_1800052A3
0x1800052d0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800052d7  test    rax, rax
0x1800052da  jz      short loc_1800052FC
0x1800052dc  test    bpl, bpl
0x1800052df  jnz     short loc_1800052F1
0x1800052e1  test    byte ptr [rdi+4], 2
0x1800052e5  jnz     short loc_1800052F1
0x1800052e7  xor     ecx, ecx
0x1800052e9  jmp     short loc_1800052F3
0x1800052eb  add     rbx, 10h
0x1800052ef  jmp     short loc_180005279
0x1800052f1  mov     cl, 1
0x1800052f3  mov     rdx, rdi
0x1800052f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052fb  nop
0x1800052fc  call    cs:__imp_GetCurrentThreadId
0x180005302  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005308  cmp     ecx, eax
0x18000530a  jz      loc_18000540C
0x180005310  mov     ecx, 1
0x180005315  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000531d  inc     ecx; this
0x18000531f  cmp     ecx, 4
0x180005322  jge     loc_180005405
0x180005328  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000532e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180005333  mov     rbx, rax
0x180005336  test    rax, rax
0x180005339  jz      loc_1800053FB
0x18000533f  mov     esi, [rax+10h]
0x180005342  mov     ebp, 50h ; 'P'
0x180005347  cmp     qword ptr [rax+18h], 0
0x18000534c  jnz     short loc_180005383
0x18000534e  test    esi, esi
0x180005350  jz      short loc_180005383
0x180005352  mov     edx, 190h; dwBytes
0x180005357  lea     ecx, [rbp-48h]; dwFlags
0x18000535a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000535f  mov     [rbx+18h], rax
0x180005363  test    rax, rax
0x180005366  jz      short loc_180005383
0x180005368  mov     dword ptr [rbx+20h], 5
0x18000536f  lea     rcx, [rax+190h]
0x180005376  jmp     short loc_18000537E
0x180005378  mov     [rax], bp
0x18000537b  add     rax, rbp
0x18000537e  cmp     rax, rcx
0x180005381  jnz     short loc_180005378
0x180005383  mov     r9, [rbx+18h]
0x180005387  test    r9, r9
0x18000538a  jz      short loc_1800053FB
0x18000538c  test    esi, esi
0x18000538e  jz      short loc_1800053C1
0x180005390  mov     rcx, r9
0x180005393  movzx   eax, word ptr [rbx+20h]
0x180005397  lea     rdx, [rax+rax*4]
0x18000539b  shl     rdx, 4
0x18000539f  add     rdx, r9
0x1800053a2  cmp     r9, rdx
0x1800053a5  jz      short loc_1800053C1
0x1800053a7  mov     r8d, [rbx+10h]
0x1800053ab  cmp     [rcx+4], r8d
0x1800053af  jbe     short loc_1800053B9
0x1800053b1  mov     eax, [rdi+8]
0x1800053b4  cmp     [rcx+8], eax
0x1800053b7  jz      short loc_1800053FB
0x1800053b9  add     rcx, rbp
0x1800053bc  cmp     rcx, rdx
0x1800053bf  jnz     short loc_1800053AB
0x1800053c1  movzx   eax, word ptr [rbx+22h]
0x1800053c5  inc     eax
0x1800053c7  movzx   ecx, word ptr [rbx+20h]
0x1800053cb  xor     edx, edx
0x1800053cd  div     ecx
0x1800053cf  mov     [rbx+22h], dx
0x1800053d3  mov     rax, [rbx+8]
0x1800053d7  mov     r8d, 1
0x1800053dd  lock xadd [rax], r8d
0x1800053e2  inc     r8d; unsigned int
0x1800053e5  movzx   eax, dx
0x1800053e8  lea     rcx, [rax+rax*4]
0x1800053ec  shl     rcx, 4
0x1800053f0  add     rcx, r9; this
0x1800053f3  mov     rdx, rdi; struct wil::FailureInfo *
0x1800053f6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800053fb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005405  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000540c  add     rsp, 20h
0x180005410  pop     r14
0x180005412  pop     rdi
0x180005413  pop     rsi
0x180005414  pop     rbp
0x180005415  pop     rbx
0x180005416  retn
```
