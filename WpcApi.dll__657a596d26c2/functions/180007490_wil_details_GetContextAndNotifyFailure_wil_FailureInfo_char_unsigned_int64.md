# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180007490`
- end: `0x180007697`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180007490`
- `0x180007d88`
- `0x180007e6c`
- `0x180008b08`
- `0x180009524`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800074ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000757c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800074ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000757c`

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
0x180007490  push    rbx
0x180007492  push    rbp
0x180007493  push    rsi
0x180007494  push    rdi
0x180007495  push    r14
0x180007497  sub     rsp, 20h
0x18000749b  mov     r14, r8
0x18000749e  mov     rsi, rdx
0x1800074a1  mov     rdi, rcx
0x1800074a4  mov     byte ptr [rdx], 0
0x1800074a7  xor     bpl, bpl
0x1800074aa  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800074b1  test    rbx, rbx
0x1800074b4  jz      loc_180007550
0x1800074ba  call    cs:__imp_GetCurrentThreadId
0x1800074c0  mov     r9d, eax
0x1800074c3  mov     r8d, eax
0x1800074c6  shr     r8, 2
0x1800074ca  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800074d4  mul     r8
0x1800074d7  shr     rdx, 3
0x1800074db  lea     rcx, [rdx+rdx*4]
0x1800074df  add     rcx, rcx
0x1800074e2  sub     r8, rcx
0x1800074e5  mov     rbx, [rbx+r8*8]
0x1800074e9  jmp     short loc_1800074F4
0x1800074eb  cmp     [rbx], r9d
0x1800074ee  jz      short loc_18000756B
0x1800074f0  mov     rbx, [rbx+8]
0x1800074f4  test    rbx, rbx
0x1800074f7  jnz     short loc_1800074EB
0x1800074f9  test    rbx, rbx
0x1800074fc  jz      short loc_180007550
0x1800074fe  cmp     qword ptr [rbx], 0
0x180007502  jz      short loc_180007550
0x180007504  mov     [rsi], bpl
0x180007507  mov     r9, r14; unsigned __int64
0x18000750a  mov     r8, rsi; char *
0x18000750d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180007510  mov     rcx, rdi; struct wil::FailureInfo *
0x180007513  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180007518  test    al, al
0x18000751a  jz      short loc_180007520
0x18000751c  mov     [rdi+48h], rsi
0x180007520  mov     rbx, [rbx]
0x180007523  mov     al, [rbx+28h]
0x180007526  mov     byte ptr [rbx+28h], 1
0x18000752a  test    al, al
0x18000752c  jnz     short loc_180007547
0x18000752e  mov     rcx, [rbx+8]
0x180007532  mov     rax, [rcx]
0x180007535  mov     rdx, rdi
0x180007538  mov     rax, [rax]
0x18000753b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007540  or      bpl, al
0x180007543  mov     byte ptr [rbx+28h], 0
0x180007547  mov     rbx, [rbx+10h]
0x18000754b  test    rbx, rbx
0x18000754e  jnz     short loc_180007523
0x180007550  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180007557  test    rax, rax
0x18000755a  jz      short loc_18000757C
0x18000755c  test    bpl, bpl
0x18000755f  jnz     short loc_180007571
0x180007561  test    byte ptr [rdi+4], 2
0x180007565  jnz     short loc_180007571
0x180007567  xor     ecx, ecx
0x180007569  jmp     short loc_180007573
0x18000756b  add     rbx, 10h
0x18000756f  jmp     short loc_1800074F9
0x180007571  mov     cl, 1
0x180007573  mov     rdx, rdi
0x180007576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000757b  nop
0x18000757c  call    cs:__imp_GetCurrentThreadId
0x180007582  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007588  cmp     ecx, eax
0x18000758a  jz      loc_18000768C
0x180007590  mov     ecx, 1
0x180007595  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000759d  inc     ecx; this
0x18000759f  cmp     ecx, 4
0x1800075a2  jge     loc_180007685
0x1800075a8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800075ae  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800075b3  mov     rbx, rax
0x1800075b6  test    rax, rax
0x1800075b9  jz      loc_18000767B
0x1800075bf  mov     esi, [rax+10h]
0x1800075c2  mov     ebp, 50h ; 'P'
0x1800075c7  cmp     qword ptr [rax+18h], 0
0x1800075cc  jnz     short loc_180007603
0x1800075ce  test    esi, esi
0x1800075d0  jz      short loc_180007603
0x1800075d2  mov     edx, 190h; dwBytes
0x1800075d7  lea     ecx, [rbp-48h]; dwFlags
0x1800075da  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800075df  mov     [rbx+18h], rax
0x1800075e3  test    rax, rax
0x1800075e6  jz      short loc_180007603
0x1800075e8  mov     dword ptr [rbx+20h], 5
0x1800075ef  lea     rcx, [rax+190h]
0x1800075f6  jmp     short loc_1800075FE
0x1800075f8  mov     [rax], bp
0x1800075fb  add     rax, rbp
0x1800075fe  cmp     rax, rcx
0x180007601  jnz     short loc_1800075F8
0x180007603  mov     r9, [rbx+18h]
0x180007607  test    r9, r9
0x18000760a  jz      short loc_18000767B
0x18000760c  test    esi, esi
0x18000760e  jz      short loc_180007641
0x180007610  mov     rcx, r9
0x180007613  movzx   eax, word ptr [rbx+20h]
0x180007617  lea     rdx, [rax+rax*4]
0x18000761b  shl     rdx, 4
0x18000761f  add     rdx, r9
0x180007622  cmp     r9, rdx
0x180007625  jz      short loc_180007641
0x180007627  mov     r8d, [rbx+10h]
0x18000762b  cmp     [rcx+4], r8d
0x18000762f  jbe     short loc_180007639
0x180007631  mov     eax, [rdi+8]
0x180007634  cmp     [rcx+8], eax
0x180007637  jz      short loc_18000767B
0x180007639  add     rcx, rbp
0x18000763c  cmp     rcx, rdx
0x18000763f  jnz     short loc_18000762B
0x180007641  movzx   eax, word ptr [rbx+22h]
0x180007645  inc     eax
0x180007647  movzx   ecx, word ptr [rbx+20h]
0x18000764b  xor     edx, edx
0x18000764d  div     ecx
0x18000764f  mov     [rbx+22h], dx
0x180007653  mov     rax, [rbx+8]
0x180007657  mov     r8d, 1
0x18000765d  lock xadd [rax], r8d
0x180007662  inc     r8d; unsigned int
0x180007665  movzx   eax, dx
0x180007668  lea     rcx, [rax+rax*4]
0x18000766c  shl     rcx, 4
0x180007670  add     rcx, r9; this
0x180007673  mov     rdx, rdi; struct wil::FailureInfo *
0x180007676  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000767b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007685  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000768c  add     rsp, 20h
0x180007690  pop     r14
0x180007692  pop     rdi
0x180007693  pop     rsi
0x180007694  pop     rbp
0x180007695  pop     rbx
0x180007696  retn
```
