# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004c80`
- end: `0x180004e86`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004c80`
- `0x180005378`
- `0x18000545c`
- `0x180005ea8`
- `0x180007528`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004caa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004caa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d6b`

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
0x180004c80  push    rbx
0x180004c82  push    rbp
0x180004c83  push    rsi
0x180004c84  push    rdi
0x180004c85  push    r14
0x180004c87  sub     rsp, 20h
0x180004c8b  mov     byte ptr [rdx], 0
0x180004c8e  xor     bpl, bpl
0x180004c91  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004c98  mov     r14, r8
0x180004c9b  mov     rsi, rdx
0x180004c9e  mov     rdi, rcx
0x180004ca1  test    rbx, rbx
0x180004ca4  jz      loc_180004D40
0x180004caa  call    cs:__imp_GetCurrentThreadId
0x180004cb0  mov     r8d, eax
0x180004cb3  mov     r9d, eax
0x180004cb6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004cc0  shr     r8, 2
0x180004cc4  mul     r8
0x180004cc7  shr     rdx, 3
0x180004ccb  lea     rcx, [rdx+rdx*4]
0x180004ccf  add     rcx, rcx
0x180004cd2  sub     r8, rcx
0x180004cd5  mov     rbx, [rbx+r8*8]
0x180004cd9  jmp     short loc_180004CE4
0x180004cdb  cmp     [rbx], r9d
0x180004cde  jz      short loc_180004D5B
0x180004ce0  mov     rbx, [rbx+8]
0x180004ce4  test    rbx, rbx
0x180004ce7  jnz     short loc_180004CDB
0x180004ce9  test    rbx, rbx
0x180004cec  jz      short loc_180004D40
0x180004cee  cmp     qword ptr [rbx], 0
0x180004cf2  jz      short loc_180004D40
0x180004cf4  mov     [rsi], bpl
0x180004cf7  mov     r9, r14; unsigned __int64
0x180004cfa  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004cfd  mov     r8, rsi; char *
0x180004d00  mov     rcx, rdi; struct wil::FailureInfo *
0x180004d03  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004d08  test    al, al
0x180004d0a  jz      short loc_180004D10
0x180004d0c  mov     [rdi+48h], rsi
0x180004d10  mov     rbx, [rbx]
0x180004d13  mov     al, [rbx+28h]
0x180004d16  mov     byte ptr [rbx+28h], 1
0x180004d1a  test    al, al
0x180004d1c  jnz     short loc_180004D37
0x180004d1e  mov     rcx, [rbx+8]
0x180004d22  mov     rdx, rdi
0x180004d25  mov     rax, [rcx]
0x180004d28  mov     rax, [rax]
0x180004d2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d30  or      bpl, al
0x180004d33  mov     byte ptr [rbx+28h], 0
0x180004d37  mov     rbx, [rbx+10h]
0x180004d3b  test    rbx, rbx
0x180004d3e  jnz     short loc_180004D13
0x180004d40  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004d47  test    rax, rax
0x180004d4a  jz      short loc_180004D6B
0x180004d4c  test    bpl, bpl
0x180004d4f  jnz     short loc_180004D61
0x180004d51  test    byte ptr [rdi+4], 2
0x180004d55  jnz     short loc_180004D61
0x180004d57  xor     ecx, ecx
0x180004d59  jmp     short loc_180004D63
0x180004d5b  add     rbx, 10h
0x180004d5f  jmp     short loc_180004CE9
0x180004d61  mov     cl, 1
0x180004d63  mov     rdx, rdi
0x180004d66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d6b  call    cs:__imp_GetCurrentThreadId
0x180004d71  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004d77  cmp     ecx, eax
0x180004d79  jz      loc_180004E7B
0x180004d7f  mov     ecx, 1
0x180004d84  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004d8c  inc     ecx; this
0x180004d8e  cmp     ecx, 4
0x180004d91  jge     loc_180004E74
0x180004d97  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004d9d  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180004da2  mov     rbx, rax
0x180004da5  test    rax, rax
0x180004da8  jz      loc_180004E6A
0x180004dae  cmp     qword ptr [rax+18h], 0
0x180004db3  mov     ebp, 50h ; 'P'
0x180004db8  mov     esi, [rax+10h]
0x180004dbb  jnz     short loc_180004DF2
0x180004dbd  test    esi, esi
0x180004dbf  jz      short loc_180004DF2
0x180004dc1  mov     edx, 190h; dwBytes
0x180004dc6  lea     ecx, [rbp-48h]; dwFlags
0x180004dc9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004dce  mov     [rbx+18h], rax
0x180004dd2  test    rax, rax
0x180004dd5  jz      short loc_180004DF2
0x180004dd7  mov     dword ptr [rbx+20h], 5
0x180004dde  lea     rcx, [rax+190h]
0x180004de5  jmp     short loc_180004DED
0x180004de7  mov     [rax], bp
0x180004dea  add     rax, rbp
0x180004ded  cmp     rax, rcx
0x180004df0  jnz     short loc_180004DE7
0x180004df2  mov     r9, [rbx+18h]
0x180004df6  test    r9, r9
0x180004df9  jz      short loc_180004E6A
0x180004dfb  test    esi, esi
0x180004dfd  jz      short loc_180004E30
0x180004dff  movzx   eax, word ptr [rbx+20h]
0x180004e03  mov     rcx, r9
0x180004e06  lea     rdx, [rax+rax*4]
0x180004e0a  shl     rdx, 4
0x180004e0e  add     rdx, r9
0x180004e11  cmp     r9, rdx
0x180004e14  jz      short loc_180004E30
0x180004e16  mov     r8d, [rbx+10h]
0x180004e1a  cmp     [rcx+4], r8d
0x180004e1e  jbe     short loc_180004E28
0x180004e20  mov     eax, [rdi+8]
0x180004e23  cmp     [rcx+8], eax
0x180004e26  jz      short loc_180004E6A
0x180004e28  add     rcx, rbp
0x180004e2b  cmp     rcx, rdx
0x180004e2e  jnz     short loc_180004E1A
0x180004e30  movzx   eax, word ptr [rbx+22h]
0x180004e34  xor     edx, edx
0x180004e36  movzx   ecx, word ptr [rbx+20h]
0x180004e3a  inc     eax
0x180004e3c  div     ecx
0x180004e3e  mov     rax, [rbx+8]
0x180004e42  mov     r8d, 1
0x180004e48  mov     [rbx+22h], dx
0x180004e4c  lock xadd [rax], r8d
0x180004e51  movzx   eax, dx
0x180004e54  inc     r8d; unsigned int
0x180004e57  mov     rdx, rdi; struct wil::FailureInfo *
0x180004e5a  lea     rcx, [rax+rax*4]
0x180004e5e  shl     rcx, 4
0x180004e62  add     rcx, r9; this
0x180004e65  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180004e6a  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004e74  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004e7b  add     rsp, 20h
0x180004e7f  pop     r14
0x180004e81  pop     rdi
0x180004e82  pop     rsi
0x180004e83  pop     rbp
0x180004e84  pop     rbx
0x180004e85  retn
```
