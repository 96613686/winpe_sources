# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800248d0`
- end: `0x180024ad6`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800248d0`
- `0x18002508c`
- `0x180025170`
- `0x180025b78`
- `0x180026fd8`
- `0x18005d010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800248fa`
- `KERNEL32!GetCurrentThreadId` at `0x1800249bb`
- `KERNEL32!GetCurrentThreadId` at `0x1800248fa`
- `KERNEL32!GetCurrentThreadId` at `0x1800249bb`

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
0x1800248d0  push    rbx
0x1800248d2  push    rbp
0x1800248d3  push    rsi
0x1800248d4  push    rdi
0x1800248d5  push    r14
0x1800248d7  sub     rsp, 20h
0x1800248db  mov     byte ptr [rdx], 0
0x1800248de  xor     bpl, bpl
0x1800248e1  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800248e8  mov     r14, r8
0x1800248eb  mov     rsi, rdx
0x1800248ee  mov     rdi, rcx
0x1800248f1  test    rbx, rbx
0x1800248f4  jz      loc_180024990
0x1800248fa  call    cs:__imp_GetCurrentThreadId
0x180024900  mov     r8d, eax
0x180024903  mov     r9d, eax
0x180024906  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180024910  shr     r8, 2
0x180024914  mul     r8
0x180024917  shr     rdx, 3
0x18002491b  lea     rcx, [rdx+rdx*4]
0x18002491f  add     rcx, rcx
0x180024922  sub     r8, rcx
0x180024925  mov     rbx, [rbx+r8*8]
0x180024929  jmp     short loc_180024934
0x18002492b  cmp     [rbx], r9d
0x18002492e  jz      short loc_1800249AB
0x180024930  mov     rbx, [rbx+8]
0x180024934  test    rbx, rbx
0x180024937  jnz     short loc_18002492B
0x180024939  test    rbx, rbx
0x18002493c  jz      short loc_180024990
0x18002493e  cmp     qword ptr [rbx], 0
0x180024942  jz      short loc_180024990
0x180024944  mov     [rsi], bpl
0x180024947  mov     r9, r14; unsigned __int64
0x18002494a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18002494d  mov     r8, rsi; char *
0x180024950  mov     rcx, rdi; struct wil::FailureInfo *
0x180024953  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180024958  test    al, al
0x18002495a  jz      short loc_180024960
0x18002495c  mov     [rdi+48h], rsi
0x180024960  mov     rbx, [rbx]
0x180024963  mov     al, [rbx+28h]
0x180024966  mov     byte ptr [rbx+28h], 1
0x18002496a  test    al, al
0x18002496c  jnz     short loc_180024987
0x18002496e  mov     rcx, [rbx+8]
0x180024972  mov     rdx, rdi
0x180024975  mov     rax, [rcx]
0x180024978  mov     rax, [rax]
0x18002497b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024980  or      bpl, al
0x180024983  mov     byte ptr [rbx+28h], 0
0x180024987  mov     rbx, [rbx+10h]
0x18002498b  test    rbx, rbx
0x18002498e  jnz     short loc_180024963
0x180024990  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180024997  test    rax, rax
0x18002499a  jz      short loc_1800249BB
0x18002499c  test    bpl, bpl
0x18002499f  jnz     short loc_1800249B1
0x1800249a1  test    byte ptr [rdi+4], 2
0x1800249a5  jnz     short loc_1800249B1
0x1800249a7  xor     ecx, ecx
0x1800249a9  jmp     short loc_1800249B3
0x1800249ab  add     rbx, 10h
0x1800249af  jmp     short loc_180024939
0x1800249b1  mov     cl, 1
0x1800249b3  mov     rdx, rdi
0x1800249b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249bb  call    cs:__imp_GetCurrentThreadId
0x1800249c1  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800249c7  cmp     ecx, eax
0x1800249c9  jz      loc_180024ACB
0x1800249cf  mov     ecx, 1
0x1800249d4  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800249dc  inc     ecx; this
0x1800249de  cmp     ecx, 4
0x1800249e1  jge     loc_180024AC4
0x1800249e7  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800249ed  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800249f2  mov     rbx, rax
0x1800249f5  test    rax, rax
0x1800249f8  jz      loc_180024ABA
0x1800249fe  cmp     qword ptr [rax+18h], 0
0x180024a03  mov     ebp, 50h ; 'P'
0x180024a08  mov     esi, [rax+10h]
0x180024a0b  jnz     short loc_180024A42
0x180024a0d  test    esi, esi
0x180024a0f  jz      short loc_180024A42
0x180024a11  mov     edx, 190h; dwBytes
0x180024a16  lea     ecx, [rbp-48h]; dwFlags
0x180024a19  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180024a1e  mov     [rbx+18h], rax
0x180024a22  test    rax, rax
0x180024a25  jz      short loc_180024A42
0x180024a27  mov     dword ptr [rbx+20h], 5
0x180024a2e  lea     rcx, [rax+190h]
0x180024a35  jmp     short loc_180024A3D
0x180024a37  mov     [rax], bp
0x180024a3a  add     rax, rbp
0x180024a3d  cmp     rax, rcx
0x180024a40  jnz     short loc_180024A37
0x180024a42  mov     r9, [rbx+18h]
0x180024a46  test    r9, r9
0x180024a49  jz      short loc_180024ABA
0x180024a4b  test    esi, esi
0x180024a4d  jz      short loc_180024A80
0x180024a4f  movzx   eax, word ptr [rbx+20h]
0x180024a53  mov     rcx, r9
0x180024a56  lea     rdx, [rax+rax*4]
0x180024a5a  shl     rdx, 4
0x180024a5e  add     rdx, r9
0x180024a61  cmp     r9, rdx
0x180024a64  jz      short loc_180024A80
0x180024a66  mov     r8d, [rbx+10h]
0x180024a6a  cmp     [rcx+4], r8d
0x180024a6e  jbe     short loc_180024A78
0x180024a70  mov     eax, [rdi+8]
0x180024a73  cmp     [rcx+8], eax
0x180024a76  jz      short loc_180024ABA
0x180024a78  add     rcx, rbp
0x180024a7b  cmp     rcx, rdx
0x180024a7e  jnz     short loc_180024A6A
0x180024a80  movzx   eax, word ptr [rbx+22h]
0x180024a84  xor     edx, edx
0x180024a86  movzx   ecx, word ptr [rbx+20h]
0x180024a8a  inc     eax
0x180024a8c  div     ecx
0x180024a8e  mov     rax, [rbx+8]
0x180024a92  mov     r8d, 1
0x180024a98  mov     [rbx+22h], dx
0x180024a9c  lock xadd [rax], r8d
0x180024aa1  movzx   eax, dx
0x180024aa4  inc     r8d; unsigned int
0x180024aa7  mov     rdx, rdi; struct wil::FailureInfo *
0x180024aaa  lea     rcx, [rax+rax*4]
0x180024aae  shl     rcx, 4
0x180024ab2  add     rcx, r9; this
0x180024ab5  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180024aba  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180024ac4  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180024acb  add     rsp, 20h
0x180024acf  pop     r14
0x180024ad1  pop     rdi
0x180024ad2  pop     rsi
0x180024ad3  pop     rbp
0x180024ad4  pop     rbx
0x180024ad5  retn
```
