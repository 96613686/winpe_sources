# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180015bb0`
- end: `0x180015db7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180015bb0`
- `0x180016350`
- `0x180016434`
- `0x180016bd8`
- `0x1800184e4`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015bda`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015c9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015bda`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015c9c`

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
0x180015bb0  push    rbx
0x180015bb2  push    rbp
0x180015bb3  push    rsi
0x180015bb4  push    rdi
0x180015bb5  push    r14
0x180015bb7  sub     rsp, 20h
0x180015bbb  mov     r14, r8
0x180015bbe  mov     rsi, rdx
0x180015bc1  mov     rdi, rcx
0x180015bc4  mov     byte ptr [rdx], 0
0x180015bc7  xor     bpl, bpl
0x180015bca  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180015bd1  test    rbx, rbx
0x180015bd4  jz      loc_180015C70
0x180015bda  call    cs:__imp_GetCurrentThreadId
0x180015be0  mov     r9d, eax
0x180015be3  mov     r8d, eax
0x180015be6  shr     r8, 2
0x180015bea  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180015bf4  mul     r8
0x180015bf7  shr     rdx, 3
0x180015bfb  lea     rcx, [rdx+rdx*4]
0x180015bff  add     rcx, rcx
0x180015c02  sub     r8, rcx
0x180015c05  mov     rbx, [rbx+r8*8]
0x180015c09  jmp     short loc_180015C14
0x180015c0b  cmp     [rbx], r9d
0x180015c0e  jz      short loc_180015C8B
0x180015c10  mov     rbx, [rbx+8]
0x180015c14  test    rbx, rbx
0x180015c17  jnz     short loc_180015C0B
0x180015c19  test    rbx, rbx
0x180015c1c  jz      short loc_180015C70
0x180015c1e  cmp     qword ptr [rbx], 0
0x180015c22  jz      short loc_180015C70
0x180015c24  mov     [rsi], bpl
0x180015c27  mov     r9, r14; unsigned __int64
0x180015c2a  mov     r8, rsi; char *
0x180015c2d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180015c30  mov     rcx, rdi; struct wil::FailureInfo *
0x180015c33  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180015c38  test    al, al
0x180015c3a  jz      short loc_180015C40
0x180015c3c  mov     [rdi+48h], rsi
0x180015c40  mov     rbx, [rbx]
0x180015c43  mov     al, [rbx+28h]
0x180015c46  mov     byte ptr [rbx+28h], 1
0x180015c4a  test    al, al
0x180015c4c  jnz     short loc_180015C67
0x180015c4e  mov     rcx, [rbx+8]
0x180015c52  mov     rax, [rcx]
0x180015c55  mov     rdx, rdi
0x180015c58  mov     rax, [rax]
0x180015c5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c60  or      bpl, al
0x180015c63  mov     byte ptr [rbx+28h], 0
0x180015c67  mov     rbx, [rbx+10h]
0x180015c6b  test    rbx, rbx
0x180015c6e  jnz     short loc_180015C43
0x180015c70  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180015c77  test    rax, rax
0x180015c7a  jz      short loc_180015C9C
0x180015c7c  test    bpl, bpl
0x180015c7f  jnz     short loc_180015C91
0x180015c81  test    byte ptr [rdi+4], 2
0x180015c85  jnz     short loc_180015C91
0x180015c87  xor     ecx, ecx
0x180015c89  jmp     short loc_180015C93
0x180015c8b  add     rbx, 10h
0x180015c8f  jmp     short loc_180015C19
0x180015c91  mov     cl, 1
0x180015c93  mov     rdx, rdi
0x180015c96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c9b  nop
0x180015c9c  call    cs:__imp_GetCurrentThreadId
0x180015ca2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180015ca8  cmp     ecx, eax
0x180015caa  jz      loc_180015DAC
0x180015cb0  mov     ecx, 1
0x180015cb5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180015cbd  inc     ecx; this
0x180015cbf  cmp     ecx, 4
0x180015cc2  jge     loc_180015DA5
0x180015cc8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180015cce  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180015cd3  mov     rbx, rax
0x180015cd6  test    rax, rax
0x180015cd9  jz      loc_180015D9B
0x180015cdf  mov     esi, [rax+10h]
0x180015ce2  mov     ebp, 50h ; 'P'
0x180015ce7  cmp     qword ptr [rax+18h], 0
0x180015cec  jnz     short loc_180015D23
0x180015cee  test    esi, esi
0x180015cf0  jz      short loc_180015D23
0x180015cf2  mov     edx, 190h; dwBytes
0x180015cf7  lea     ecx, [rbp-48h]; dwFlags
0x180015cfa  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180015cff  mov     [rbx+18h], rax
0x180015d03  test    rax, rax
0x180015d06  jz      short loc_180015D23
0x180015d08  mov     dword ptr [rbx+20h], 5
0x180015d0f  lea     rcx, [rax+190h]
0x180015d16  jmp     short loc_180015D1E
0x180015d18  mov     [rax], bp
0x180015d1b  add     rax, rbp
0x180015d1e  cmp     rax, rcx
0x180015d21  jnz     short loc_180015D18
0x180015d23  mov     r9, [rbx+18h]
0x180015d27  test    r9, r9
0x180015d2a  jz      short loc_180015D9B
0x180015d2c  test    esi, esi
0x180015d2e  jz      short loc_180015D61
0x180015d30  mov     rcx, r9
0x180015d33  movzx   eax, word ptr [rbx+20h]
0x180015d37  lea     rdx, [rax+rax*4]
0x180015d3b  shl     rdx, 4
0x180015d3f  add     rdx, r9
0x180015d42  cmp     r9, rdx
0x180015d45  jz      short loc_180015D61
0x180015d47  mov     r8d, [rbx+10h]
0x180015d4b  cmp     [rcx+4], r8d
0x180015d4f  jbe     short loc_180015D59
0x180015d51  mov     eax, [rdi+8]
0x180015d54  cmp     [rcx+8], eax
0x180015d57  jz      short loc_180015D9B
0x180015d59  add     rcx, rbp
0x180015d5c  cmp     rcx, rdx
0x180015d5f  jnz     short loc_180015D4B
0x180015d61  movzx   eax, word ptr [rbx+22h]
0x180015d65  inc     eax
0x180015d67  movzx   ecx, word ptr [rbx+20h]
0x180015d6b  xor     edx, edx
0x180015d6d  div     ecx
0x180015d6f  mov     [rbx+22h], dx
0x180015d73  mov     rax, [rbx+8]
0x180015d77  mov     r8d, 1
0x180015d7d  lock xadd [rax], r8d
0x180015d82  inc     r8d; unsigned int
0x180015d85  movzx   eax, dx
0x180015d88  lea     rcx, [rax+rax*4]
0x180015d8c  shl     rcx, 4
0x180015d90  add     rcx, r9; this
0x180015d93  mov     rdx, rdi; struct wil::FailureInfo *
0x180015d96  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180015d9b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180015da5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180015dac  add     rsp, 20h
0x180015db0  pop     r14
0x180015db2  pop     rdi
0x180015db3  pop     rsi
0x180015db4  pop     rbp
0x180015db5  pop     rbx
0x180015db6  retn
```
