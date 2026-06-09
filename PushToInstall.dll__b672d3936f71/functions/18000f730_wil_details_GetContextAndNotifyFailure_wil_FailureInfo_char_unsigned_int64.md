# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000f730`
- end: `0x18000f937`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000f730`
- `0x18000fe2c`
- `0x18000ff10`
- `0x180010788`
- `0x180010c74`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f75a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f81c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f75a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f81c`

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
0x18000f730  push    rbx
0x18000f732  push    rbp
0x18000f733  push    rsi
0x18000f734  push    rdi
0x18000f735  push    r14
0x18000f737  sub     rsp, 20h
0x18000f73b  mov     r14, r8
0x18000f73e  mov     rsi, rdx
0x18000f741  mov     rdi, rcx
0x18000f744  mov     byte ptr [rdx], 0
0x18000f747  xor     bpl, bpl
0x18000f74a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000f751  test    rbx, rbx
0x18000f754  jz      loc_18000F7F0
0x18000f75a  call    cs:__imp_GetCurrentThreadId
0x18000f760  mov     r9d, eax
0x18000f763  mov     r8d, eax
0x18000f766  shr     r8, 2
0x18000f76a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000f774  mul     r8
0x18000f777  shr     rdx, 3
0x18000f77b  lea     rcx, [rdx+rdx*4]
0x18000f77f  add     rcx, rcx
0x18000f782  sub     r8, rcx
0x18000f785  mov     rbx, [rbx+r8*8]
0x18000f789  jmp     short loc_18000F794
0x18000f78b  cmp     [rbx], r9d
0x18000f78e  jz      short loc_18000F80B
0x18000f790  mov     rbx, [rbx+8]
0x18000f794  test    rbx, rbx
0x18000f797  jnz     short loc_18000F78B
0x18000f799  test    rbx, rbx
0x18000f79c  jz      short loc_18000F7F0
0x18000f79e  cmp     qword ptr [rbx], 0
0x18000f7a2  jz      short loc_18000F7F0
0x18000f7a4  mov     [rsi], bpl
0x18000f7a7  mov     r9, r14; unsigned __int64
0x18000f7aa  mov     r8, rsi; char *
0x18000f7ad  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000f7b0  mov     rcx, rdi; struct wil::FailureInfo *
0x18000f7b3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000f7b8  test    al, al
0x18000f7ba  jz      short loc_18000F7C0
0x18000f7bc  mov     [rdi+48h], rsi
0x18000f7c0  mov     rbx, [rbx]
0x18000f7c3  mov     al, [rbx+28h]
0x18000f7c6  mov     byte ptr [rbx+28h], 1
0x18000f7ca  test    al, al
0x18000f7cc  jnz     short loc_18000F7E7
0x18000f7ce  mov     rcx, [rbx+8]
0x18000f7d2  mov     rax, [rcx]
0x18000f7d5  mov     rdx, rdi
0x18000f7d8  mov     rax, [rax]
0x18000f7db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7e0  or      bpl, al
0x18000f7e3  mov     byte ptr [rbx+28h], 0
0x18000f7e7  mov     rbx, [rbx+10h]
0x18000f7eb  test    rbx, rbx
0x18000f7ee  jnz     short loc_18000F7C3
0x18000f7f0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000f7f7  test    rax, rax
0x18000f7fa  jz      short loc_18000F81C
0x18000f7fc  test    bpl, bpl
0x18000f7ff  jnz     short loc_18000F811
0x18000f801  test    byte ptr [rdi+4], 2
0x18000f805  jnz     short loc_18000F811
0x18000f807  xor     ecx, ecx
0x18000f809  jmp     short loc_18000F813
0x18000f80b  add     rbx, 10h
0x18000f80f  jmp     short loc_18000F799
0x18000f811  mov     cl, 1
0x18000f813  mov     rdx, rdi
0x18000f816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f81b  nop
0x18000f81c  call    cs:__imp_GetCurrentThreadId
0x18000f822  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000f828  cmp     ecx, eax
0x18000f82a  jz      loc_18000F92C
0x18000f830  mov     ecx, 1
0x18000f835  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000f83d  inc     ecx; this
0x18000f83f  cmp     ecx, 4
0x18000f842  jge     loc_18000F925
0x18000f848  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000f84e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000f853  mov     rbx, rax
0x18000f856  test    rax, rax
0x18000f859  jz      loc_18000F91B
0x18000f85f  mov     esi, [rax+10h]
0x18000f862  mov     ebp, 50h ; 'P'
0x18000f867  cmp     qword ptr [rax+18h], 0
0x18000f86c  jnz     short loc_18000F8A3
0x18000f86e  test    esi, esi
0x18000f870  jz      short loc_18000F8A3
0x18000f872  mov     edx, 190h; dwBytes
0x18000f877  lea     ecx, [rbp-48h]; dwFlags
0x18000f87a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000f87f  mov     [rbx+18h], rax
0x18000f883  test    rax, rax
0x18000f886  jz      short loc_18000F8A3
0x18000f888  mov     dword ptr [rbx+20h], 5
0x18000f88f  lea     rcx, [rax+190h]
0x18000f896  jmp     short loc_18000F89E
0x18000f898  mov     [rax], bp
0x18000f89b  add     rax, rbp
0x18000f89e  cmp     rax, rcx
0x18000f8a1  jnz     short loc_18000F898
0x18000f8a3  mov     r9, [rbx+18h]
0x18000f8a7  test    r9, r9
0x18000f8aa  jz      short loc_18000F91B
0x18000f8ac  test    esi, esi
0x18000f8ae  jz      short loc_18000F8E1
0x18000f8b0  mov     rcx, r9
0x18000f8b3  movzx   eax, word ptr [rbx+20h]
0x18000f8b7  lea     rdx, [rax+rax*4]
0x18000f8bb  shl     rdx, 4
0x18000f8bf  add     rdx, r9
0x18000f8c2  cmp     r9, rdx
0x18000f8c5  jz      short loc_18000F8E1
0x18000f8c7  mov     r8d, [rbx+10h]
0x18000f8cb  cmp     [rcx+4], r8d
0x18000f8cf  jbe     short loc_18000F8D9
0x18000f8d1  mov     eax, [rdi+8]
0x18000f8d4  cmp     [rcx+8], eax
0x18000f8d7  jz      short loc_18000F91B
0x18000f8d9  add     rcx, rbp
0x18000f8dc  cmp     rcx, rdx
0x18000f8df  jnz     short loc_18000F8CB
0x18000f8e1  movzx   eax, word ptr [rbx+22h]
0x18000f8e5  inc     eax
0x18000f8e7  movzx   ecx, word ptr [rbx+20h]
0x18000f8eb  xor     edx, edx
0x18000f8ed  div     ecx
0x18000f8ef  mov     [rbx+22h], dx
0x18000f8f3  mov     rax, [rbx+8]
0x18000f8f7  mov     r8d, 1
0x18000f8fd  lock xadd [rax], r8d
0x18000f902  inc     r8d; unsigned int
0x18000f905  movzx   eax, dx
0x18000f908  lea     rcx, [rax+rax*4]
0x18000f90c  shl     rcx, 4
0x18000f910  add     rcx, r9; this
0x18000f913  mov     rdx, rdi; struct wil::FailureInfo *
0x18000f916  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000f91b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000f925  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000f92c  add     rsp, 20h
0x18000f930  pop     r14
0x18000f932  pop     rdi
0x18000f933  pop     rsi
0x18000f934  pop     rbp
0x18000f935  pop     rbx
0x18000f936  retn
```
