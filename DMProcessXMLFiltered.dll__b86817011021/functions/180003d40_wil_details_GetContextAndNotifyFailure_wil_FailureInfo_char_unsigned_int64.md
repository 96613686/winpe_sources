# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180003d40`
- end: `0x180003f47`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180003d40`
- `0x18000443c`
- `0x180004520`
- `0x180004d98`
- `0x1800052b0`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003d6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003e2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003d6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003e2c`

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
0x180003d40  push    rbx
0x180003d42  push    rbp
0x180003d43  push    rsi
0x180003d44  push    rdi
0x180003d45  push    r14
0x180003d47  sub     rsp, 20h
0x180003d4b  mov     r14, r8
0x180003d4e  mov     rsi, rdx
0x180003d51  mov     rdi, rcx
0x180003d54  mov     byte ptr [rdx], 0
0x180003d57  xor     bpl, bpl
0x180003d5a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180003d61  test    rbx, rbx
0x180003d64  jz      loc_180003E00
0x180003d6a  call    cs:__imp_GetCurrentThreadId
0x180003d70  mov     r9d, eax
0x180003d73  mov     r8d, eax
0x180003d76  shr     r8, 2
0x180003d7a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003d84  mul     r8
0x180003d87  shr     rdx, 3
0x180003d8b  lea     rcx, [rdx+rdx*4]
0x180003d8f  add     rcx, rcx
0x180003d92  sub     r8, rcx
0x180003d95  mov     rbx, [rbx+r8*8]
0x180003d99  jmp     short loc_180003DA4
0x180003d9b  cmp     [rbx], r9d
0x180003d9e  jz      short loc_180003E1B
0x180003da0  mov     rbx, [rbx+8]
0x180003da4  test    rbx, rbx
0x180003da7  jnz     short loc_180003D9B
0x180003da9  test    rbx, rbx
0x180003dac  jz      short loc_180003E00
0x180003dae  cmp     qword ptr [rbx], 0
0x180003db2  jz      short loc_180003E00
0x180003db4  mov     [rsi], bpl
0x180003db7  mov     r9, r14; unsigned __int64
0x180003dba  mov     r8, rsi; char *
0x180003dbd  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180003dc0  mov     rcx, rdi; struct wil::FailureInfo *
0x180003dc3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180003dc8  test    al, al
0x180003dca  jz      short loc_180003DD0
0x180003dcc  mov     [rdi+48h], rsi
0x180003dd0  mov     rbx, [rbx]
0x180003dd3  mov     al, [rbx+28h]
0x180003dd6  mov     byte ptr [rbx+28h], 1
0x180003dda  test    al, al
0x180003ddc  jnz     short loc_180003DF7
0x180003dde  mov     rcx, [rbx+8]
0x180003de2  mov     rax, [rcx]
0x180003de5  mov     rdx, rdi
0x180003de8  mov     rax, [rax]
0x180003deb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003df0  or      bpl, al
0x180003df3  mov     byte ptr [rbx+28h], 0
0x180003df7  mov     rbx, [rbx+10h]
0x180003dfb  test    rbx, rbx
0x180003dfe  jnz     short loc_180003DD3
0x180003e00  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180003e07  test    rax, rax
0x180003e0a  jz      short loc_180003E2C
0x180003e0c  test    bpl, bpl
0x180003e0f  jnz     short loc_180003E21
0x180003e11  test    byte ptr [rdi+4], 2
0x180003e15  jnz     short loc_180003E21
0x180003e17  xor     ecx, ecx
0x180003e19  jmp     short loc_180003E23
0x180003e1b  add     rbx, 10h
0x180003e1f  jmp     short loc_180003DA9
0x180003e21  mov     cl, 1
0x180003e23  mov     rdx, rdi
0x180003e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e2b  nop
0x180003e2c  call    cs:__imp_GetCurrentThreadId
0x180003e32  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003e38  cmp     ecx, eax
0x180003e3a  jz      loc_180003F3C
0x180003e40  mov     ecx, 1
0x180003e45  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180003e4d  inc     ecx; this
0x180003e4f  cmp     ecx, 4
0x180003e52  jge     loc_180003F35
0x180003e58  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003e5e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180003e63  mov     rbx, rax
0x180003e66  test    rax, rax
0x180003e69  jz      loc_180003F2B
0x180003e6f  mov     esi, [rax+10h]
0x180003e72  mov     ebp, 50h ; 'P'
0x180003e77  cmp     qword ptr [rax+18h], 0
0x180003e7c  jnz     short loc_180003EB3
0x180003e7e  test    esi, esi
0x180003e80  jz      short loc_180003EB3
0x180003e82  mov     edx, 190h; dwBytes
0x180003e87  lea     ecx, [rbp-48h]; dwFlags
0x180003e8a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003e8f  mov     [rbx+18h], rax
0x180003e93  test    rax, rax
0x180003e96  jz      short loc_180003EB3
0x180003e98  mov     dword ptr [rbx+20h], 5
0x180003e9f  lea     rcx, [rax+190h]
0x180003ea6  jmp     short loc_180003EAE
0x180003ea8  mov     [rax], bp
0x180003eab  add     rax, rbp
0x180003eae  cmp     rax, rcx
0x180003eb1  jnz     short loc_180003EA8
0x180003eb3  mov     r9, [rbx+18h]
0x180003eb7  test    r9, r9
0x180003eba  jz      short loc_180003F2B
0x180003ebc  test    esi, esi
0x180003ebe  jz      short loc_180003EF1
0x180003ec0  mov     rcx, r9
0x180003ec3  movzx   eax, word ptr [rbx+20h]
0x180003ec7  lea     rdx, [rax+rax*4]
0x180003ecb  shl     rdx, 4
0x180003ecf  add     rdx, r9
0x180003ed2  cmp     r9, rdx
0x180003ed5  jz      short loc_180003EF1
0x180003ed7  mov     r8d, [rbx+10h]
0x180003edb  cmp     [rcx+4], r8d
0x180003edf  jbe     short loc_180003EE9
0x180003ee1  mov     eax, [rdi+8]
0x180003ee4  cmp     [rcx+8], eax
0x180003ee7  jz      short loc_180003F2B
0x180003ee9  add     rcx, rbp
0x180003eec  cmp     rcx, rdx
0x180003eef  jnz     short loc_180003EDB
0x180003ef1  movzx   eax, word ptr [rbx+22h]
0x180003ef5  inc     eax
0x180003ef7  movzx   ecx, word ptr [rbx+20h]
0x180003efb  xor     edx, edx
0x180003efd  div     ecx
0x180003eff  mov     [rbx+22h], dx
0x180003f03  mov     rax, [rbx+8]
0x180003f07  mov     r8d, 1
0x180003f0d  lock xadd [rax], r8d
0x180003f12  inc     r8d; unsigned int
0x180003f15  movzx   eax, dx
0x180003f18  lea     rcx, [rax+rax*4]
0x180003f1c  shl     rcx, 4
0x180003f20  add     rcx, r9; this
0x180003f23  mov     rdx, rdi; struct wil::FailureInfo *
0x180003f26  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180003f2b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003f35  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180003f3c  add     rsp, 20h
0x180003f40  pop     r14
0x180003f42  pop     rdi
0x180003f43  pop     rsi
0x180003f44  pop     rbp
0x180003f45  pop     rbx
0x180003f46  retn
```
