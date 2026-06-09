# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180005370`
- end: `0x180005577`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180005370`
- `0x180005a6c`
- `0x180005b50`
- `0x1800063c8`
- `0x180006934`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000539a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000545c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000539a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000545c`

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
0x180005370  push    rbx
0x180005372  push    rbp
0x180005373  push    rsi
0x180005374  push    rdi
0x180005375  push    r14
0x180005377  sub     rsp, 20h
0x18000537b  mov     r14, r8
0x18000537e  mov     rsi, rdx
0x180005381  mov     rdi, rcx
0x180005384  mov     byte ptr [rdx], 0
0x180005387  xor     bpl, bpl
0x18000538a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005391  test    rbx, rbx
0x180005394  jz      loc_180005430
0x18000539a  call    cs:__imp_GetCurrentThreadId
0x1800053a0  mov     r9d, eax
0x1800053a3  mov     r8d, eax
0x1800053a6  shr     r8, 2
0x1800053aa  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800053b4  mul     r8
0x1800053b7  shr     rdx, 3
0x1800053bb  lea     rcx, [rdx+rdx*4]
0x1800053bf  add     rcx, rcx
0x1800053c2  sub     r8, rcx
0x1800053c5  mov     rbx, [rbx+r8*8]
0x1800053c9  jmp     short loc_1800053D4
0x1800053cb  cmp     [rbx], r9d
0x1800053ce  jz      short loc_18000544B
0x1800053d0  mov     rbx, [rbx+8]
0x1800053d4  test    rbx, rbx
0x1800053d7  jnz     short loc_1800053CB
0x1800053d9  test    rbx, rbx
0x1800053dc  jz      short loc_180005430
0x1800053de  cmp     qword ptr [rbx], 0
0x1800053e2  jz      short loc_180005430
0x1800053e4  mov     [rsi], bpl
0x1800053e7  mov     r9, r14; unsigned __int64
0x1800053ea  mov     r8, rsi; char *
0x1800053ed  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800053f0  mov     rcx, rdi; struct wil::FailureInfo *
0x1800053f3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800053f8  test    al, al
0x1800053fa  jz      short loc_180005400
0x1800053fc  mov     [rdi+48h], rsi
0x180005400  mov     rbx, [rbx]
0x180005403  mov     al, [rbx+28h]
0x180005406  mov     byte ptr [rbx+28h], 1
0x18000540a  test    al, al
0x18000540c  jnz     short loc_180005427
0x18000540e  mov     rcx, [rbx+8]
0x180005412  mov     rax, [rcx]
0x180005415  mov     rdx, rdi
0x180005418  mov     rax, [rax]
0x18000541b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005420  or      bpl, al
0x180005423  mov     byte ptr [rbx+28h], 0
0x180005427  mov     rbx, [rbx+10h]
0x18000542b  test    rbx, rbx
0x18000542e  jnz     short loc_180005403
0x180005430  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180005437  test    rax, rax
0x18000543a  jz      short loc_18000545C
0x18000543c  test    bpl, bpl
0x18000543f  jnz     short loc_180005451
0x180005441  test    byte ptr [rdi+4], 2
0x180005445  jnz     short loc_180005451
0x180005447  xor     ecx, ecx
0x180005449  jmp     short loc_180005453
0x18000544b  add     rbx, 10h
0x18000544f  jmp     short loc_1800053D9
0x180005451  mov     cl, 1
0x180005453  mov     rdx, rdi
0x180005456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000545b  nop
0x18000545c  call    cs:__imp_GetCurrentThreadId
0x180005462  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005468  cmp     ecx, eax
0x18000546a  jz      loc_18000556C
0x180005470  mov     ecx, 1
0x180005475  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000547d  inc     ecx; this
0x18000547f  cmp     ecx, 4
0x180005482  jge     loc_180005565
0x180005488  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000548e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180005493  mov     rbx, rax
0x180005496  test    rax, rax
0x180005499  jz      loc_18000555B
0x18000549f  mov     esi, [rax+10h]
0x1800054a2  mov     ebp, 50h ; 'P'
0x1800054a7  cmp     qword ptr [rax+18h], 0
0x1800054ac  jnz     short loc_1800054E3
0x1800054ae  test    esi, esi
0x1800054b0  jz      short loc_1800054E3
0x1800054b2  mov     edx, 190h; dwBytes
0x1800054b7  lea     ecx, [rbp-48h]; dwFlags
0x1800054ba  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800054bf  mov     [rbx+18h], rax
0x1800054c3  test    rax, rax
0x1800054c6  jz      short loc_1800054E3
0x1800054c8  mov     dword ptr [rbx+20h], 5
0x1800054cf  lea     rcx, [rax+190h]
0x1800054d6  jmp     short loc_1800054DE
0x1800054d8  mov     [rax], bp
0x1800054db  add     rax, rbp
0x1800054de  cmp     rax, rcx
0x1800054e1  jnz     short loc_1800054D8
0x1800054e3  mov     r9, [rbx+18h]
0x1800054e7  test    r9, r9
0x1800054ea  jz      short loc_18000555B
0x1800054ec  test    esi, esi
0x1800054ee  jz      short loc_180005521
0x1800054f0  mov     rcx, r9
0x1800054f3  movzx   eax, word ptr [rbx+20h]
0x1800054f7  lea     rdx, [rax+rax*4]
0x1800054fb  shl     rdx, 4
0x1800054ff  add     rdx, r9
0x180005502  cmp     r9, rdx
0x180005505  jz      short loc_180005521
0x180005507  mov     r8d, [rbx+10h]
0x18000550b  cmp     [rcx+4], r8d
0x18000550f  jbe     short loc_180005519
0x180005511  mov     eax, [rdi+8]
0x180005514  cmp     [rcx+8], eax
0x180005517  jz      short loc_18000555B
0x180005519  add     rcx, rbp
0x18000551c  cmp     rcx, rdx
0x18000551f  jnz     short loc_18000550B
0x180005521  movzx   eax, word ptr [rbx+22h]
0x180005525  inc     eax
0x180005527  movzx   ecx, word ptr [rbx+20h]
0x18000552b  xor     edx, edx
0x18000552d  div     ecx
0x18000552f  mov     [rbx+22h], dx
0x180005533  mov     rax, [rbx+8]
0x180005537  mov     r8d, 1
0x18000553d  lock xadd [rax], r8d
0x180005542  inc     r8d; unsigned int
0x180005545  movzx   eax, dx
0x180005548  lea     rcx, [rax+rax*4]
0x18000554c  shl     rcx, 4
0x180005550  add     rcx, r9; this
0x180005553  mov     rdx, rdi; struct wil::FailureInfo *
0x180005556  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000555b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005565  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000556c  add     rsp, 20h
0x180005570  pop     r14
0x180005572  pop     rdi
0x180005573  pop     rsi
0x180005574  pop     rbp
0x180005575  pop     rbx
0x180005576  retn
```
