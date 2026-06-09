# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004670`
- end: `0x180004876`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004670`
- `0x180004d68`
- `0x180004e4c`
- `0x1800057d8`
- `0x180006bd8`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000469a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000475b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000469a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000475b`

## pseudocode

```c
void __fastcall wil::details::GetContextAndNotifyFailure(unsigned __int64 this, struct wil::FailureInfo *a2, char *a3)
{
  char v3; // bp
  __int64 v4; // rbx
  wil::details *v7; // rdi
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
  volatile signed __int32 *v25; // rax

  *(_BYTE *)a2 = 0;
  v3 = 0;
  v4 = wil::details::g_pThreadFailureCallbacks;
  v7 = (wil::details *)this;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    this = 10 * ((CurrentThreadId >> 2) / 0xA);
    for ( i = *(_QWORD *)(v4 + 8 * ((CurrentThreadId >> 2) % 0xA)); i; i = *(_QWORD *)(i + 8) )
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
             v7,
             *(struct wil::details::ThreadFailureCallbackHolder **)i,
             (char *)a2,
             (unsigned __int64)a3) )
      {
        *((_QWORD *)v7 + 9) = a2;
      }
      v10 = *(struct wil::details::ThreadFailureCallbackHolder **)i;
      do
      {
        v11 = *((_BYTE *)v10 + 40);
        *((_BYTE *)v10 + 40) = 1;
        if ( !v11 )
        {
          v3 |= (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v10 + 1))(*((_QWORD *)v10 + 1), v7);
          *((_BYTE *)v10 + 40) = 0;
        }
        v10 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v10 + 2);
      }
      while ( v10 );
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( v3 || (*((_BYTE *)v7 + 4) & 2) != 0 )
      LOBYTE(this) = 1;
    else
      this = 0;
    wil::details::g_pfnTelemetryCallback(this, v7);
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
            v25 = (volatile signed __int32 *)*((_QWORD *)v17 + 1);
            *((_WORD *)v17 + 17) = v24;
            wil::details_abi::ThreadLocalFailureInfo::Set(
              (wil::details_abi::ThreadLocalFailureInfo *)(v21 + 80LL * v24),
              v7,
              _InterlockedIncrement(v25));
          }
          else
          {
            while ( *(_DWORD *)(v22 + 4) <= *((_DWORD *)v17 + 4) || *(_DWORD *)(v22 + 8) != *((_DWORD *)v7 + 2) )
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
0x180004670  push    rbx
0x180004672  push    rbp
0x180004673  push    rsi
0x180004674  push    rdi
0x180004675  push    r14
0x180004677  sub     rsp, 20h
0x18000467b  mov     byte ptr [rdx], 0
0x18000467e  xor     bpl, bpl
0x180004681  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004688  mov     r14, r8
0x18000468b  mov     rsi, rdx
0x18000468e  mov     rdi, rcx
0x180004691  test    rbx, rbx
0x180004694  jz      loc_180004730
0x18000469a  call    cs:__imp_GetCurrentThreadId
0x1800046a0  mov     r8d, eax
0x1800046a3  mov     r9d, eax
0x1800046a6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800046b0  shr     r8, 2
0x1800046b4  mul     r8
0x1800046b7  shr     rdx, 3
0x1800046bb  lea     rcx, [rdx+rdx*4]
0x1800046bf  add     rcx, rcx
0x1800046c2  sub     r8, rcx
0x1800046c5  mov     rbx, [rbx+r8*8]
0x1800046c9  jmp     short loc_1800046D4
0x1800046cb  cmp     [rbx], r9d
0x1800046ce  jz      short loc_18000474B
0x1800046d0  mov     rbx, [rbx+8]
0x1800046d4  test    rbx, rbx
0x1800046d7  jnz     short loc_1800046CB
0x1800046d9  test    rbx, rbx
0x1800046dc  jz      short loc_180004730
0x1800046de  cmp     qword ptr [rbx], 0
0x1800046e2  jz      short loc_180004730
0x1800046e4  mov     [rsi], bpl
0x1800046e7  mov     r9, r14; unsigned __int64
0x1800046ea  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800046ed  mov     r8, rsi; char *
0x1800046f0  mov     rcx, rdi; struct wil::FailureInfo *
0x1800046f3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800046f8  test    al, al
0x1800046fa  jz      short loc_180004700
0x1800046fc  mov     [rdi+48h], rsi
0x180004700  mov     rbx, [rbx]
0x180004703  mov     al, [rbx+28h]
0x180004706  mov     byte ptr [rbx+28h], 1
0x18000470a  test    al, al
0x18000470c  jnz     short loc_180004727
0x18000470e  mov     rcx, [rbx+8]
0x180004712  mov     rdx, rdi
0x180004715  mov     rax, [rcx]
0x180004718  mov     rax, [rax]
0x18000471b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004720  or      bpl, al
0x180004723  mov     byte ptr [rbx+28h], 0
0x180004727  mov     rbx, [rbx+10h]
0x18000472b  test    rbx, rbx
0x18000472e  jnz     short loc_180004703
0x180004730  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004737  test    rax, rax
0x18000473a  jz      short loc_18000475B
0x18000473c  test    bpl, bpl
0x18000473f  jnz     short loc_180004751
0x180004741  test    byte ptr [rdi+4], 2
0x180004745  jnz     short loc_180004751
0x180004747  xor     ecx, ecx
0x180004749  jmp     short loc_180004753
0x18000474b  add     rbx, 10h
0x18000474f  jmp     short loc_1800046D9
0x180004751  mov     cl, 1
0x180004753  mov     rdx, rdi
0x180004756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000475b  call    cs:__imp_GetCurrentThreadId
0x180004761  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004767  cmp     ecx, eax
0x180004769  jz      loc_18000486B
0x18000476f  mov     ecx, 1
0x180004774  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000477c  inc     ecx; this
0x18000477e  cmp     ecx, 4
0x180004781  jge     loc_180004864
0x180004787  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000478d  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180004792  mov     rbx, rax
0x180004795  test    rax, rax
0x180004798  jz      loc_18000485A
0x18000479e  cmp     qword ptr [rax+18h], 0
0x1800047a3  mov     ebp, 50h ; 'P'
0x1800047a8  mov     esi, [rax+10h]
0x1800047ab  jnz     short loc_1800047E2
0x1800047ad  test    esi, esi
0x1800047af  jz      short loc_1800047E2
0x1800047b1  mov     edx, 190h; dwBytes
0x1800047b6  lea     ecx, [rbp-48h]; dwFlags
0x1800047b9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800047be  mov     [rbx+18h], rax
0x1800047c2  test    rax, rax
0x1800047c5  jz      short loc_1800047E2
0x1800047c7  mov     dword ptr [rbx+20h], 5
0x1800047ce  lea     rcx, [rax+190h]
0x1800047d5  jmp     short loc_1800047DD
0x1800047d7  mov     [rax], bp
0x1800047da  add     rax, rbp
0x1800047dd  cmp     rax, rcx
0x1800047e0  jnz     short loc_1800047D7
0x1800047e2  mov     r9, [rbx+18h]
0x1800047e6  test    r9, r9
0x1800047e9  jz      short loc_18000485A
0x1800047eb  test    esi, esi
0x1800047ed  jz      short loc_180004820
0x1800047ef  movzx   eax, word ptr [rbx+20h]
0x1800047f3  mov     rcx, r9
0x1800047f6  lea     rdx, [rax+rax*4]
0x1800047fa  shl     rdx, 4
0x1800047fe  add     rdx, r9
0x180004801  cmp     r9, rdx
0x180004804  jz      short loc_180004820
0x180004806  mov     r8d, [rbx+10h]
0x18000480a  cmp     [rcx+4], r8d
0x18000480e  jbe     short loc_180004818
0x180004810  mov     eax, [rdi+8]
0x180004813  cmp     [rcx+8], eax
0x180004816  jz      short loc_18000485A
0x180004818  add     rcx, rbp
0x18000481b  cmp     rcx, rdx
0x18000481e  jnz     short loc_18000480A
0x180004820  movzx   eax, word ptr [rbx+22h]
0x180004824  xor     edx, edx
0x180004826  movzx   ecx, word ptr [rbx+20h]
0x18000482a  inc     eax
0x18000482c  div     ecx
0x18000482e  mov     rax, [rbx+8]
0x180004832  mov     r8d, 1
0x180004838  mov     [rbx+22h], dx
0x18000483c  lock xadd [rax], r8d
0x180004841  movzx   eax, dx
0x180004844  inc     r8d; unsigned int
0x180004847  mov     rdx, rdi; struct wil::FailureInfo *
0x18000484a  lea     rcx, [rax+rax*4]
0x18000484e  shl     rcx, 4
0x180004852  add     rcx, r9; this
0x180004855  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000485a  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004864  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000486b  add     rsp, 20h
0x18000486f  pop     r14
0x180004871  pop     rdi
0x180004872  pop     rsi
0x180004873  pop     rbp
0x180004874  pop     rbx
0x180004875  retn
```
