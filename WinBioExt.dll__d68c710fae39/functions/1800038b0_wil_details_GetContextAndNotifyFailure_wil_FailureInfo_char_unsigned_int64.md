# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800038b0`
- end: `0x180003ab7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800038b0`
- `0x180003fac`
- `0x180004090`
- `0x1800048f8`
- `0x180004de4`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800038da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000399c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800038da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000399c`

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
0x1800038b0  push    rbx
0x1800038b2  push    rbp
0x1800038b3  push    rsi
0x1800038b4  push    rdi
0x1800038b5  push    r14
0x1800038b7  sub     rsp, 20h
0x1800038bb  mov     r14, r8
0x1800038be  mov     rsi, rdx
0x1800038c1  mov     rdi, rcx
0x1800038c4  mov     byte ptr [rdx], 0
0x1800038c7  xor     bpl, bpl
0x1800038ca  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800038d1  test    rbx, rbx
0x1800038d4  jz      loc_180003970
0x1800038da  call    cs:__imp_GetCurrentThreadId
0x1800038e0  mov     r9d, eax
0x1800038e3  mov     r8d, eax
0x1800038e6  shr     r8, 2
0x1800038ea  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800038f4  mul     r8
0x1800038f7  shr     rdx, 3
0x1800038fb  lea     rcx, [rdx+rdx*4]
0x1800038ff  add     rcx, rcx
0x180003902  sub     r8, rcx
0x180003905  mov     rbx, [rbx+r8*8]
0x180003909  jmp     short loc_180003914
0x18000390b  cmp     [rbx], r9d
0x18000390e  jz      short loc_18000398B
0x180003910  mov     rbx, [rbx+8]
0x180003914  test    rbx, rbx
0x180003917  jnz     short loc_18000390B
0x180003919  test    rbx, rbx
0x18000391c  jz      short loc_180003970
0x18000391e  cmp     qword ptr [rbx], 0
0x180003922  jz      short loc_180003970
0x180003924  mov     [rsi], bpl
0x180003927  mov     r9, r14; unsigned __int64
0x18000392a  mov     r8, rsi; char *
0x18000392d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180003930  mov     rcx, rdi; struct wil::FailureInfo *
0x180003933  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180003938  test    al, al
0x18000393a  jz      short loc_180003940
0x18000393c  mov     [rdi+48h], rsi
0x180003940  mov     rbx, [rbx]
0x180003943  mov     al, [rbx+28h]
0x180003946  mov     byte ptr [rbx+28h], 1
0x18000394a  test    al, al
0x18000394c  jnz     short loc_180003967
0x18000394e  mov     rcx, [rbx+8]
0x180003952  mov     rax, [rcx]
0x180003955  mov     rdx, rdi
0x180003958  mov     rax, [rax]
0x18000395b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003960  or      bpl, al
0x180003963  mov     byte ptr [rbx+28h], 0
0x180003967  mov     rbx, [rbx+10h]
0x18000396b  test    rbx, rbx
0x18000396e  jnz     short loc_180003943
0x180003970  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180003977  test    rax, rax
0x18000397a  jz      short loc_18000399C
0x18000397c  test    bpl, bpl
0x18000397f  jnz     short loc_180003991
0x180003981  test    byte ptr [rdi+4], 2
0x180003985  jnz     short loc_180003991
0x180003987  xor     ecx, ecx
0x180003989  jmp     short loc_180003993
0x18000398b  add     rbx, 10h
0x18000398f  jmp     short loc_180003919
0x180003991  mov     cl, 1
0x180003993  mov     rdx, rdi
0x180003996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000399b  nop
0x18000399c  call    cs:__imp_GetCurrentThreadId
0x1800039a2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800039a8  cmp     ecx, eax
0x1800039aa  jz      loc_180003AAC
0x1800039b0  mov     ecx, 1
0x1800039b5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800039bd  inc     ecx; this
0x1800039bf  cmp     ecx, 4
0x1800039c2  jge     loc_180003AA5
0x1800039c8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800039ce  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800039d3  mov     rbx, rax
0x1800039d6  test    rax, rax
0x1800039d9  jz      loc_180003A9B
0x1800039df  mov     esi, [rax+10h]
0x1800039e2  mov     ebp, 50h ; 'P'
0x1800039e7  cmp     qword ptr [rax+18h], 0
0x1800039ec  jnz     short loc_180003A23
0x1800039ee  test    esi, esi
0x1800039f0  jz      short loc_180003A23
0x1800039f2  mov     edx, 190h; dwBytes
0x1800039f7  lea     ecx, [rbp-48h]; dwFlags
0x1800039fa  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800039ff  mov     [rbx+18h], rax
0x180003a03  test    rax, rax
0x180003a06  jz      short loc_180003A23
0x180003a08  mov     dword ptr [rbx+20h], 5
0x180003a0f  lea     rcx, [rax+190h]
0x180003a16  jmp     short loc_180003A1E
0x180003a18  mov     [rax], bp
0x180003a1b  add     rax, rbp
0x180003a1e  cmp     rax, rcx
0x180003a21  jnz     short loc_180003A18
0x180003a23  mov     r9, [rbx+18h]
0x180003a27  test    r9, r9
0x180003a2a  jz      short loc_180003A9B
0x180003a2c  test    esi, esi
0x180003a2e  jz      short loc_180003A61
0x180003a30  mov     rcx, r9
0x180003a33  movzx   eax, word ptr [rbx+20h]
0x180003a37  lea     rdx, [rax+rax*4]
0x180003a3b  shl     rdx, 4
0x180003a3f  add     rdx, r9
0x180003a42  cmp     r9, rdx
0x180003a45  jz      short loc_180003A61
0x180003a47  mov     r8d, [rbx+10h]
0x180003a4b  cmp     [rcx+4], r8d
0x180003a4f  jbe     short loc_180003A59
0x180003a51  mov     eax, [rdi+8]
0x180003a54  cmp     [rcx+8], eax
0x180003a57  jz      short loc_180003A9B
0x180003a59  add     rcx, rbp
0x180003a5c  cmp     rcx, rdx
0x180003a5f  jnz     short loc_180003A4B
0x180003a61  movzx   eax, word ptr [rbx+22h]
0x180003a65  inc     eax
0x180003a67  movzx   ecx, word ptr [rbx+20h]
0x180003a6b  xor     edx, edx
0x180003a6d  div     ecx
0x180003a6f  mov     [rbx+22h], dx
0x180003a73  mov     rax, [rbx+8]
0x180003a77  mov     r8d, 1
0x180003a7d  lock xadd [rax], r8d
0x180003a82  inc     r8d; unsigned int
0x180003a85  movzx   eax, dx
0x180003a88  lea     rcx, [rax+rax*4]
0x180003a8c  shl     rcx, 4
0x180003a90  add     rcx, r9; this
0x180003a93  mov     rdx, rdi; struct wil::FailureInfo *
0x180003a96  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180003a9b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003aa5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180003aac  add     rsp, 20h
0x180003ab0  pop     r14
0x180003ab2  pop     rdi
0x180003ab3  pop     rsi
0x180003ab4  pop     rbp
0x180003ab5  pop     rbx
0x180003ab6  retn
```
