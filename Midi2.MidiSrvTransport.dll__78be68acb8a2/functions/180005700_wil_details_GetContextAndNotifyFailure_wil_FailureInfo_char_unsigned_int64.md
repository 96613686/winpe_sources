# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180005700`
- end: `0x180005907`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180005700`
- `0x180005dfc`
- `0x180005ee0`
- `0x180006c1c`
- `0x180007eb0`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000572a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800057ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000572a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800057ec`

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
0x180005700  push    rbx
0x180005702  push    rbp
0x180005703  push    rsi
0x180005704  push    rdi
0x180005705  push    r14
0x180005707  sub     rsp, 20h
0x18000570b  mov     r14, r8
0x18000570e  mov     rsi, rdx
0x180005711  mov     rdi, rcx
0x180005714  mov     byte ptr [rdx], 0
0x180005717  xor     bpl, bpl
0x18000571a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005721  test    rbx, rbx
0x180005724  jz      loc_1800057C0
0x18000572a  call    cs:__imp_GetCurrentThreadId
0x180005730  mov     r9d, eax
0x180005733  mov     r8d, eax
0x180005736  shr     r8, 2
0x18000573a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005744  mul     r8
0x180005747  shr     rdx, 3
0x18000574b  lea     rcx, [rdx+rdx*4]
0x18000574f  add     rcx, rcx
0x180005752  sub     r8, rcx
0x180005755  mov     rbx, [rbx+r8*8]
0x180005759  jmp     short loc_180005764
0x18000575b  cmp     [rbx], r9d
0x18000575e  jz      short loc_1800057DB
0x180005760  mov     rbx, [rbx+8]
0x180005764  test    rbx, rbx
0x180005767  jnz     short loc_18000575B
0x180005769  test    rbx, rbx
0x18000576c  jz      short loc_1800057C0
0x18000576e  cmp     qword ptr [rbx], 0
0x180005772  jz      short loc_1800057C0
0x180005774  mov     [rsi], bpl
0x180005777  mov     r9, r14; unsigned __int64
0x18000577a  mov     r8, rsi; char *
0x18000577d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180005780  mov     rcx, rdi; struct wil::FailureInfo *
0x180005783  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005788  test    al, al
0x18000578a  jz      short loc_180005790
0x18000578c  mov     [rdi+48h], rsi
0x180005790  mov     rbx, [rbx]
0x180005793  mov     al, [rbx+28h]
0x180005796  mov     byte ptr [rbx+28h], 1
0x18000579a  test    al, al
0x18000579c  jnz     short loc_1800057B7
0x18000579e  mov     rcx, [rbx+8]
0x1800057a2  mov     rax, [rcx]
0x1800057a5  mov     rdx, rdi
0x1800057a8  mov     rax, [rax]
0x1800057ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057b0  or      bpl, al
0x1800057b3  mov     byte ptr [rbx+28h], 0
0x1800057b7  mov     rbx, [rbx+10h]
0x1800057bb  test    rbx, rbx
0x1800057be  jnz     short loc_180005793
0x1800057c0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800057c7  test    rax, rax
0x1800057ca  jz      short loc_1800057EC
0x1800057cc  test    bpl, bpl
0x1800057cf  jnz     short loc_1800057E1
0x1800057d1  test    byte ptr [rdi+4], 2
0x1800057d5  jnz     short loc_1800057E1
0x1800057d7  xor     ecx, ecx
0x1800057d9  jmp     short loc_1800057E3
0x1800057db  add     rbx, 10h
0x1800057df  jmp     short loc_180005769
0x1800057e1  mov     cl, 1
0x1800057e3  mov     rdx, rdi
0x1800057e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057eb  nop
0x1800057ec  call    cs:__imp_GetCurrentThreadId
0x1800057f2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800057f8  cmp     ecx, eax
0x1800057fa  jz      loc_1800058FC
0x180005800  mov     ecx, 1
0x180005805  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000580d  inc     ecx; this
0x18000580f  cmp     ecx, 4
0x180005812  jge     loc_1800058F5
0x180005818  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000581e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180005823  mov     rbx, rax
0x180005826  test    rax, rax
0x180005829  jz      loc_1800058EB
0x18000582f  mov     esi, [rax+10h]
0x180005832  mov     ebp, 50h ; 'P'
0x180005837  cmp     qword ptr [rax+18h], 0
0x18000583c  jnz     short loc_180005873
0x18000583e  test    esi, esi
0x180005840  jz      short loc_180005873
0x180005842  mov     edx, 190h; dwBytes
0x180005847  lea     ecx, [rbp-48h]; dwFlags
0x18000584a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000584f  mov     [rbx+18h], rax
0x180005853  test    rax, rax
0x180005856  jz      short loc_180005873
0x180005858  mov     dword ptr [rbx+20h], 5
0x18000585f  lea     rcx, [rax+190h]
0x180005866  jmp     short loc_18000586E
0x180005868  mov     [rax], bp
0x18000586b  add     rax, rbp
0x18000586e  cmp     rax, rcx
0x180005871  jnz     short loc_180005868
0x180005873  mov     r9, [rbx+18h]
0x180005877  test    r9, r9
0x18000587a  jz      short loc_1800058EB
0x18000587c  test    esi, esi
0x18000587e  jz      short loc_1800058B1
0x180005880  mov     rcx, r9
0x180005883  movzx   eax, word ptr [rbx+20h]
0x180005887  lea     rdx, [rax+rax*4]
0x18000588b  shl     rdx, 4
0x18000588f  add     rdx, r9
0x180005892  cmp     r9, rdx
0x180005895  jz      short loc_1800058B1
0x180005897  mov     r8d, [rbx+10h]
0x18000589b  cmp     [rcx+4], r8d
0x18000589f  jbe     short loc_1800058A9
0x1800058a1  mov     eax, [rdi+8]
0x1800058a4  cmp     [rcx+8], eax
0x1800058a7  jz      short loc_1800058EB
0x1800058a9  add     rcx, rbp
0x1800058ac  cmp     rcx, rdx
0x1800058af  jnz     short loc_18000589B
0x1800058b1  movzx   eax, word ptr [rbx+22h]
0x1800058b5  inc     eax
0x1800058b7  movzx   ecx, word ptr [rbx+20h]
0x1800058bb  xor     edx, edx
0x1800058bd  div     ecx
0x1800058bf  mov     [rbx+22h], dx
0x1800058c3  mov     rax, [rbx+8]
0x1800058c7  mov     r8d, 1
0x1800058cd  lock xadd [rax], r8d
0x1800058d2  inc     r8d; unsigned int
0x1800058d5  movzx   eax, dx
0x1800058d8  lea     rcx, [rax+rax*4]
0x1800058dc  shl     rcx, 4
0x1800058e0  add     rcx, r9; this
0x1800058e3  mov     rdx, rdi; struct wil::FailureInfo *
0x1800058e6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800058eb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800058f5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800058fc  add     rsp, 20h
0x180005900  pop     r14
0x180005902  pop     rdi
0x180005903  pop     rsi
0x180005904  pop     rbp
0x180005905  pop     rbx
0x180005906  retn
```
