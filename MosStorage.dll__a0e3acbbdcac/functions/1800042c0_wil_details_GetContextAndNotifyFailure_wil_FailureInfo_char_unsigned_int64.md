# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800042c0`
- end: `0x1800044c7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800042c0`
- `0x1800049bc`
- `0x180004aa0`
- `0x180005308`
- `0x180005800`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800042ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800043ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800042ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800043ac`

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
0x1800042c0  push    rbx
0x1800042c2  push    rbp
0x1800042c3  push    rsi
0x1800042c4  push    rdi
0x1800042c5  push    r14
0x1800042c7  sub     rsp, 20h
0x1800042cb  mov     r14, r8
0x1800042ce  mov     rsi, rdx
0x1800042d1  mov     rdi, rcx
0x1800042d4  mov     byte ptr [rdx], 0
0x1800042d7  xor     bpl, bpl
0x1800042da  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800042e1  test    rbx, rbx
0x1800042e4  jz      loc_180004380
0x1800042ea  call    cs:__imp_GetCurrentThreadId
0x1800042f0  mov     r9d, eax
0x1800042f3  mov     r8d, eax
0x1800042f6  shr     r8, 2
0x1800042fa  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004304  mul     r8
0x180004307  shr     rdx, 3
0x18000430b  lea     rcx, [rdx+rdx*4]
0x18000430f  add     rcx, rcx
0x180004312  sub     r8, rcx
0x180004315  mov     rbx, [rbx+r8*8]
0x180004319  jmp     short loc_180004324
0x18000431b  cmp     [rbx], r9d
0x18000431e  jz      short loc_18000439B
0x180004320  mov     rbx, [rbx+8]
0x180004324  test    rbx, rbx
0x180004327  jnz     short loc_18000431B
0x180004329  test    rbx, rbx
0x18000432c  jz      short loc_180004380
0x18000432e  cmp     qword ptr [rbx], 0
0x180004332  jz      short loc_180004380
0x180004334  mov     [rsi], bpl
0x180004337  mov     r9, r14; unsigned __int64
0x18000433a  mov     r8, rsi; char *
0x18000433d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004340  mov     rcx, rdi; struct wil::FailureInfo *
0x180004343  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004348  test    al, al
0x18000434a  jz      short loc_180004350
0x18000434c  mov     [rdi+48h], rsi
0x180004350  mov     rbx, [rbx]
0x180004353  mov     al, [rbx+28h]
0x180004356  mov     byte ptr [rbx+28h], 1
0x18000435a  test    al, al
0x18000435c  jnz     short loc_180004377
0x18000435e  mov     rcx, [rbx+8]
0x180004362  mov     rax, [rcx]
0x180004365  mov     rdx, rdi
0x180004368  mov     rax, [rax]
0x18000436b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004370  or      bpl, al
0x180004373  mov     byte ptr [rbx+28h], 0
0x180004377  mov     rbx, [rbx+10h]
0x18000437b  test    rbx, rbx
0x18000437e  jnz     short loc_180004353
0x180004380  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004387  test    rax, rax
0x18000438a  jz      short loc_1800043AC
0x18000438c  test    bpl, bpl
0x18000438f  jnz     short loc_1800043A1
0x180004391  test    byte ptr [rdi+4], 2
0x180004395  jnz     short loc_1800043A1
0x180004397  xor     ecx, ecx
0x180004399  jmp     short loc_1800043A3
0x18000439b  add     rbx, 10h
0x18000439f  jmp     short loc_180004329
0x1800043a1  mov     cl, 1
0x1800043a3  mov     rdx, rdi
0x1800043a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043ab  nop
0x1800043ac  call    cs:__imp_GetCurrentThreadId
0x1800043b2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800043b8  cmp     ecx, eax
0x1800043ba  jz      loc_1800044BC
0x1800043c0  mov     ecx, 1
0x1800043c5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800043cd  inc     ecx; this
0x1800043cf  cmp     ecx, 4
0x1800043d2  jge     loc_1800044B5
0x1800043d8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800043de  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800043e3  mov     rbx, rax
0x1800043e6  test    rax, rax
0x1800043e9  jz      loc_1800044AB
0x1800043ef  mov     esi, [rax+10h]
0x1800043f2  mov     ebp, 50h ; 'P'
0x1800043f7  cmp     qword ptr [rax+18h], 0
0x1800043fc  jnz     short loc_180004433
0x1800043fe  test    esi, esi
0x180004400  jz      short loc_180004433
0x180004402  mov     edx, 190h; dwBytes
0x180004407  lea     ecx, [rbp-48h]; dwFlags
0x18000440a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000440f  mov     [rbx+18h], rax
0x180004413  test    rax, rax
0x180004416  jz      short loc_180004433
0x180004418  mov     dword ptr [rbx+20h], 5
0x18000441f  lea     rcx, [rax+190h]
0x180004426  jmp     short loc_18000442E
0x180004428  mov     [rax], bp
0x18000442b  add     rax, rbp
0x18000442e  cmp     rax, rcx
0x180004431  jnz     short loc_180004428
0x180004433  mov     r9, [rbx+18h]
0x180004437  test    r9, r9
0x18000443a  jz      short loc_1800044AB
0x18000443c  test    esi, esi
0x18000443e  jz      short loc_180004471
0x180004440  mov     rcx, r9
0x180004443  movzx   eax, word ptr [rbx+20h]
0x180004447  lea     rdx, [rax+rax*4]
0x18000444b  shl     rdx, 4
0x18000444f  add     rdx, r9
0x180004452  cmp     r9, rdx
0x180004455  jz      short loc_180004471
0x180004457  mov     r8d, [rbx+10h]
0x18000445b  cmp     [rcx+4], r8d
0x18000445f  jbe     short loc_180004469
0x180004461  mov     eax, [rdi+8]
0x180004464  cmp     [rcx+8], eax
0x180004467  jz      short loc_1800044AB
0x180004469  add     rcx, rbp
0x18000446c  cmp     rcx, rdx
0x18000446f  jnz     short loc_18000445B
0x180004471  movzx   eax, word ptr [rbx+22h]
0x180004475  inc     eax
0x180004477  movzx   ecx, word ptr [rbx+20h]
0x18000447b  xor     edx, edx
0x18000447d  div     ecx
0x18000447f  mov     [rbx+22h], dx
0x180004483  mov     rax, [rbx+8]
0x180004487  mov     r8d, 1
0x18000448d  lock xadd [rax], r8d
0x180004492  inc     r8d; unsigned int
0x180004495  movzx   eax, dx
0x180004498  lea     rcx, [rax+rax*4]
0x18000449c  shl     rcx, 4
0x1800044a0  add     rcx, r9; this
0x1800044a3  mov     rdx, rdi; struct wil::FailureInfo *
0x1800044a6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800044ab  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800044b5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800044bc  add     rsp, 20h
0x1800044c0  pop     r14
0x1800044c2  pop     rdi
0x1800044c3  pop     rsi
0x1800044c4  pop     rbp
0x1800044c5  pop     rbx
0x1800044c6  retn
```
