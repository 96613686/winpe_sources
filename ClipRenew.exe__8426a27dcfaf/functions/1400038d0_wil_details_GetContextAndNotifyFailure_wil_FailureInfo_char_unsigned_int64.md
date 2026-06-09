# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1400038d0`
- end: `0x140003ad6`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1400038d0`
- `0x140003fc8`
- `0x1400040ac`
- `0x140004a94`
- `0x140004dd8`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400038fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400039bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400038fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400039bb`

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
0x1400038d0  push    rbx
0x1400038d2  push    rbp
0x1400038d3  push    rsi
0x1400038d4  push    rdi
0x1400038d5  push    r14
0x1400038d7  sub     rsp, 20h
0x1400038db  mov     byte ptr [rdx], 0
0x1400038de  xor     bpl, bpl
0x1400038e1  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1400038e8  mov     r14, r8
0x1400038eb  mov     rsi, rdx
0x1400038ee  mov     rdi, rcx
0x1400038f1  test    rbx, rbx
0x1400038f4  jz      loc_140003990
0x1400038fa  call    cs:__imp_GetCurrentThreadId
0x140003900  mov     r8d, eax
0x140003903  mov     r9d, eax
0x140003906  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140003910  shr     r8, 2
0x140003914  mul     r8
0x140003917  shr     rdx, 3
0x14000391b  lea     rcx, [rdx+rdx*4]
0x14000391f  add     rcx, rcx
0x140003922  sub     r8, rcx
0x140003925  mov     rbx, [rbx+r8*8]
0x140003929  jmp     short loc_140003934
0x14000392b  cmp     [rbx], r9d
0x14000392e  jz      short loc_1400039AB
0x140003930  mov     rbx, [rbx+8]
0x140003934  test    rbx, rbx
0x140003937  jnz     short loc_14000392B
0x140003939  test    rbx, rbx
0x14000393c  jz      short loc_140003990
0x14000393e  cmp     qword ptr [rbx], 0
0x140003942  jz      short loc_140003990
0x140003944  mov     [rsi], bpl
0x140003947  mov     r9, r14; unsigned __int64
0x14000394a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x14000394d  mov     r8, rsi; char *
0x140003950  mov     rcx, rdi; struct wil::FailureInfo *
0x140003953  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140003958  test    al, al
0x14000395a  jz      short loc_140003960
0x14000395c  mov     [rdi+48h], rsi
0x140003960  mov     rbx, [rbx]
0x140003963  mov     al, [rbx+28h]
0x140003966  mov     byte ptr [rbx+28h], 1
0x14000396a  test    al, al
0x14000396c  jnz     short loc_140003987
0x14000396e  mov     rcx, [rbx+8]
0x140003972  mov     rdx, rdi
0x140003975  mov     rax, [rcx]
0x140003978  mov     rax, [rax]
0x14000397b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003980  or      bpl, al
0x140003983  mov     byte ptr [rbx+28h], 0
0x140003987  mov     rbx, [rbx+10h]
0x14000398b  test    rbx, rbx
0x14000398e  jnz     short loc_140003963
0x140003990  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140003997  test    rax, rax
0x14000399a  jz      short loc_1400039BB
0x14000399c  test    bpl, bpl
0x14000399f  jnz     short loc_1400039B1
0x1400039a1  test    byte ptr [rdi+4], 2
0x1400039a5  jnz     short loc_1400039B1
0x1400039a7  xor     ecx, ecx
0x1400039a9  jmp     short loc_1400039B3
0x1400039ab  add     rbx, 10h
0x1400039af  jmp     short loc_140003939
0x1400039b1  mov     cl, 1
0x1400039b3  mov     rdx, rdi
0x1400039b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400039bb  call    cs:__imp_GetCurrentThreadId
0x1400039c1  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400039c7  cmp     ecx, eax
0x1400039c9  jz      loc_140003ACB
0x1400039cf  mov     ecx, 1
0x1400039d4  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1400039dc  inc     ecx; this
0x1400039de  cmp     ecx, 4
0x1400039e1  jge     loc_140003AC4
0x1400039e7  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400039ed  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1400039f2  mov     rbx, rax
0x1400039f5  test    rax, rax
0x1400039f8  jz      loc_140003ABA
0x1400039fe  cmp     qword ptr [rax+18h], 0
0x140003a03  mov     ebp, 50h ; 'P'
0x140003a08  mov     esi, [rax+10h]
0x140003a0b  jnz     short loc_140003A42
0x140003a0d  test    esi, esi
0x140003a0f  jz      short loc_140003A42
0x140003a11  mov     edx, 190h; dwBytes
0x140003a16  lea     ecx, [rbp-48h]; dwFlags
0x140003a19  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140003a1e  mov     [rbx+18h], rax
0x140003a22  test    rax, rax
0x140003a25  jz      short loc_140003A42
0x140003a27  mov     dword ptr [rbx+20h], 5
0x140003a2e  lea     rcx, [rax+190h]
0x140003a35  jmp     short loc_140003A3D
0x140003a37  mov     [rax], bp
0x140003a3a  add     rax, rbp
0x140003a3d  cmp     rax, rcx
0x140003a40  jnz     short loc_140003A37
0x140003a42  mov     r9, [rbx+18h]
0x140003a46  test    r9, r9
0x140003a49  jz      short loc_140003ABA
0x140003a4b  test    esi, esi
0x140003a4d  jz      short loc_140003A80
0x140003a4f  movzx   eax, word ptr [rbx+20h]
0x140003a53  mov     rcx, r9
0x140003a56  lea     rdx, [rax+rax*4]
0x140003a5a  shl     rdx, 4
0x140003a5e  add     rdx, r9
0x140003a61  cmp     r9, rdx
0x140003a64  jz      short loc_140003A80
0x140003a66  mov     r8d, [rbx+10h]
0x140003a6a  cmp     [rcx+4], r8d
0x140003a6e  jbe     short loc_140003A78
0x140003a70  mov     eax, [rdi+8]
0x140003a73  cmp     [rcx+8], eax
0x140003a76  jz      short loc_140003ABA
0x140003a78  add     rcx, rbp
0x140003a7b  cmp     rcx, rdx
0x140003a7e  jnz     short loc_140003A6A
0x140003a80  movzx   eax, word ptr [rbx+22h]
0x140003a84  xor     edx, edx
0x140003a86  movzx   ecx, word ptr [rbx+20h]
0x140003a8a  inc     eax
0x140003a8c  div     ecx
0x140003a8e  mov     rax, [rbx+8]
0x140003a92  mov     r8d, 1
0x140003a98  mov     [rbx+22h], dx
0x140003a9c  lock xadd [rax], r8d
0x140003aa1  movzx   eax, dx
0x140003aa4  inc     r8d; unsigned int
0x140003aa7  mov     rdx, rdi; struct wil::FailureInfo *
0x140003aaa  lea     rcx, [rax+rax*4]
0x140003aae  shl     rcx, 4
0x140003ab2  add     rcx, r9; this
0x140003ab5  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x140003aba  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140003ac4  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140003acb  add     rsp, 20h
0x140003acf  pop     r14
0x140003ad1  pop     rdi
0x140003ad2  pop     rsi
0x140003ad3  pop     rbp
0x140003ad4  pop     rbx
0x140003ad5  retn
```
