# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180008000`
- end: `0x180008207`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180008000`
- `0x180008898`
- `0x18000897c`
- `0x180009664`
- `0x180009b44`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000802a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800080ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000802a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800080ec`

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
0x180008000  push    rbx
0x180008002  push    rbp
0x180008003  push    rsi
0x180008004  push    rdi
0x180008005  push    r14
0x180008007  sub     rsp, 20h
0x18000800b  mov     r14, r8
0x18000800e  mov     rsi, rdx
0x180008011  mov     rdi, rcx
0x180008014  mov     byte ptr [rdx], 0
0x180008017  xor     bpl, bpl
0x18000801a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180008021  test    rbx, rbx
0x180008024  jz      loc_1800080C0
0x18000802a  call    cs:__imp_GetCurrentThreadId
0x180008030  mov     r9d, eax
0x180008033  mov     r8d, eax
0x180008036  shr     r8, 2
0x18000803a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180008044  mul     r8
0x180008047  shr     rdx, 3
0x18000804b  lea     rcx, [rdx+rdx*4]
0x18000804f  add     rcx, rcx
0x180008052  sub     r8, rcx
0x180008055  mov     rbx, [rbx+r8*8]
0x180008059  jmp     short loc_180008064
0x18000805b  cmp     [rbx], r9d
0x18000805e  jz      short loc_1800080DB
0x180008060  mov     rbx, [rbx+8]
0x180008064  test    rbx, rbx
0x180008067  jnz     short loc_18000805B
0x180008069  test    rbx, rbx
0x18000806c  jz      short loc_1800080C0
0x18000806e  cmp     qword ptr [rbx], 0
0x180008072  jz      short loc_1800080C0
0x180008074  mov     [rsi], bpl
0x180008077  mov     r9, r14; unsigned __int64
0x18000807a  mov     r8, rsi; char *
0x18000807d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180008080  mov     rcx, rdi; struct wil::FailureInfo *
0x180008083  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180008088  test    al, al
0x18000808a  jz      short loc_180008090
0x18000808c  mov     [rdi+48h], rsi
0x180008090  mov     rbx, [rbx]
0x180008093  mov     al, [rbx+28h]
0x180008096  mov     byte ptr [rbx+28h], 1
0x18000809a  test    al, al
0x18000809c  jnz     short loc_1800080B7
0x18000809e  mov     rcx, [rbx+8]
0x1800080a2  mov     rax, [rcx]
0x1800080a5  mov     rdx, rdi
0x1800080a8  mov     rax, [rax]
0x1800080ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080b0  or      bpl, al
0x1800080b3  mov     byte ptr [rbx+28h], 0
0x1800080b7  mov     rbx, [rbx+10h]
0x1800080bb  test    rbx, rbx
0x1800080be  jnz     short loc_180008093
0x1800080c0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800080c7  test    rax, rax
0x1800080ca  jz      short loc_1800080EC
0x1800080cc  test    bpl, bpl
0x1800080cf  jnz     short loc_1800080E1
0x1800080d1  test    byte ptr [rdi+4], 2
0x1800080d5  jnz     short loc_1800080E1
0x1800080d7  xor     ecx, ecx
0x1800080d9  jmp     short loc_1800080E3
0x1800080db  add     rbx, 10h
0x1800080df  jmp     short loc_180008069
0x1800080e1  mov     cl, 1
0x1800080e3  mov     rdx, rdi
0x1800080e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080eb  nop
0x1800080ec  call    cs:__imp_GetCurrentThreadId
0x1800080f2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800080f8  cmp     ecx, eax
0x1800080fa  jz      loc_1800081FC
0x180008100  mov     ecx, 1
0x180008105  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000810d  inc     ecx; this
0x18000810f  cmp     ecx, 4
0x180008112  jge     loc_1800081F5
0x180008118  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000811e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180008123  mov     rbx, rax
0x180008126  test    rax, rax
0x180008129  jz      loc_1800081EB
0x18000812f  mov     esi, [rax+10h]
0x180008132  mov     ebp, 50h ; 'P'
0x180008137  cmp     qword ptr [rax+18h], 0
0x18000813c  jnz     short loc_180008173
0x18000813e  test    esi, esi
0x180008140  jz      short loc_180008173
0x180008142  mov     edx, 190h; dwBytes
0x180008147  lea     ecx, [rbp-48h]; dwFlags
0x18000814a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000814f  mov     [rbx+18h], rax
0x180008153  test    rax, rax
0x180008156  jz      short loc_180008173
0x180008158  mov     dword ptr [rbx+20h], 5
0x18000815f  lea     rcx, [rax+190h]
0x180008166  jmp     short loc_18000816E
0x180008168  mov     [rax], bp
0x18000816b  add     rax, rbp
0x18000816e  cmp     rax, rcx
0x180008171  jnz     short loc_180008168
0x180008173  mov     r9, [rbx+18h]
0x180008177  test    r9, r9
0x18000817a  jz      short loc_1800081EB
0x18000817c  test    esi, esi
0x18000817e  jz      short loc_1800081B1
0x180008180  mov     rcx, r9
0x180008183  movzx   eax, word ptr [rbx+20h]
0x180008187  lea     rdx, [rax+rax*4]
0x18000818b  shl     rdx, 4
0x18000818f  add     rdx, r9
0x180008192  cmp     r9, rdx
0x180008195  jz      short loc_1800081B1
0x180008197  mov     r8d, [rbx+10h]
0x18000819b  cmp     [rcx+4], r8d
0x18000819f  jbe     short loc_1800081A9
0x1800081a1  mov     eax, [rdi+8]
0x1800081a4  cmp     [rcx+8], eax
0x1800081a7  jz      short loc_1800081EB
0x1800081a9  add     rcx, rbp
0x1800081ac  cmp     rcx, rdx
0x1800081af  jnz     short loc_18000819B
0x1800081b1  movzx   eax, word ptr [rbx+22h]
0x1800081b5  inc     eax
0x1800081b7  movzx   ecx, word ptr [rbx+20h]
0x1800081bb  xor     edx, edx
0x1800081bd  div     ecx
0x1800081bf  mov     [rbx+22h], dx
0x1800081c3  mov     rax, [rbx+8]
0x1800081c7  mov     r8d, 1
0x1800081cd  lock xadd [rax], r8d
0x1800081d2  inc     r8d; unsigned int
0x1800081d5  movzx   eax, dx
0x1800081d8  lea     rcx, [rax+rax*4]
0x1800081dc  shl     rcx, 4
0x1800081e0  add     rcx, r9; this
0x1800081e3  mov     rdx, rdi; struct wil::FailureInfo *
0x1800081e6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800081eb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800081f5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800081fc  add     rsp, 20h
0x180008200  pop     r14
0x180008202  pop     rdi
0x180008203  pop     rsi
0x180008204  pop     rbp
0x180008205  pop     rbx
0x180008206  retn
```
