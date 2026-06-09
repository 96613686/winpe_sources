# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004bf0`
- end: `0x180004df6`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004bf0`
- `0x1800052e8`
- `0x1800053cc`
- `0x180005ef0`
- `0x1800076b8`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004c1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004cdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004c1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004cdb`

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
0x180004bf0  push    rbx
0x180004bf2  push    rbp
0x180004bf3  push    rsi
0x180004bf4  push    rdi
0x180004bf5  push    r14
0x180004bf7  sub     rsp, 20h
0x180004bfb  mov     byte ptr [rdx], 0
0x180004bfe  xor     bpl, bpl
0x180004c01  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004c08  mov     r14, r8
0x180004c0b  mov     rsi, rdx
0x180004c0e  mov     rdi, rcx
0x180004c11  test    rbx, rbx
0x180004c14  jz      loc_180004CB0
0x180004c1a  call    cs:__imp_GetCurrentThreadId
0x180004c20  mov     r8d, eax
0x180004c23  mov     r9d, eax
0x180004c26  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004c30  shr     r8, 2
0x180004c34  mul     r8
0x180004c37  shr     rdx, 3
0x180004c3b  lea     rcx, [rdx+rdx*4]
0x180004c3f  add     rcx, rcx
0x180004c42  sub     r8, rcx
0x180004c45  mov     rbx, [rbx+r8*8]
0x180004c49  jmp     short loc_180004C54
0x180004c4b  cmp     [rbx], r9d
0x180004c4e  jz      short loc_180004CCB
0x180004c50  mov     rbx, [rbx+8]
0x180004c54  test    rbx, rbx
0x180004c57  jnz     short loc_180004C4B
0x180004c59  test    rbx, rbx
0x180004c5c  jz      short loc_180004CB0
0x180004c5e  cmp     qword ptr [rbx], 0
0x180004c62  jz      short loc_180004CB0
0x180004c64  mov     [rsi], bpl
0x180004c67  mov     r9, r14; unsigned __int64
0x180004c6a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004c6d  mov     r8, rsi; char *
0x180004c70  mov     rcx, rdi; struct wil::FailureInfo *
0x180004c73  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004c78  test    al, al
0x180004c7a  jz      short loc_180004C80
0x180004c7c  mov     [rdi+48h], rsi
0x180004c80  mov     rbx, [rbx]
0x180004c83  mov     al, [rbx+28h]
0x180004c86  mov     byte ptr [rbx+28h], 1
0x180004c8a  test    al, al
0x180004c8c  jnz     short loc_180004CA7
0x180004c8e  mov     rcx, [rbx+8]
0x180004c92  mov     rdx, rdi
0x180004c95  mov     rax, [rcx]
0x180004c98  mov     rax, [rax]
0x180004c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ca0  or      bpl, al
0x180004ca3  mov     byte ptr [rbx+28h], 0
0x180004ca7  mov     rbx, [rbx+10h]
0x180004cab  test    rbx, rbx
0x180004cae  jnz     short loc_180004C83
0x180004cb0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004cb7  test    rax, rax
0x180004cba  jz      short loc_180004CDB
0x180004cbc  test    bpl, bpl
0x180004cbf  jnz     short loc_180004CD1
0x180004cc1  test    byte ptr [rdi+4], 2
0x180004cc5  jnz     short loc_180004CD1
0x180004cc7  xor     ecx, ecx
0x180004cc9  jmp     short loc_180004CD3
0x180004ccb  add     rbx, 10h
0x180004ccf  jmp     short loc_180004C59
0x180004cd1  mov     cl, 1
0x180004cd3  mov     rdx, rdi
0x180004cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cdb  call    cs:__imp_GetCurrentThreadId
0x180004ce1  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004ce7  cmp     ecx, eax
0x180004ce9  jz      loc_180004DEB
0x180004cef  mov     ecx, 1
0x180004cf4  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004cfc  inc     ecx; this
0x180004cfe  cmp     ecx, 4
0x180004d01  jge     loc_180004DE4
0x180004d07  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004d0d  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180004d12  mov     rbx, rax
0x180004d15  test    rax, rax
0x180004d18  jz      loc_180004DDA
0x180004d1e  cmp     qword ptr [rax+18h], 0
0x180004d23  mov     ebp, 50h ; 'P'
0x180004d28  mov     esi, [rax+10h]
0x180004d2b  jnz     short loc_180004D62
0x180004d2d  test    esi, esi
0x180004d2f  jz      short loc_180004D62
0x180004d31  mov     edx, 190h; dwBytes
0x180004d36  lea     ecx, [rbp-48h]; dwFlags
0x180004d39  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004d3e  mov     [rbx+18h], rax
0x180004d42  test    rax, rax
0x180004d45  jz      short loc_180004D62
0x180004d47  mov     dword ptr [rbx+20h], 5
0x180004d4e  lea     rcx, [rax+190h]
0x180004d55  jmp     short loc_180004D5D
0x180004d57  mov     [rax], bp
0x180004d5a  add     rax, rbp
0x180004d5d  cmp     rax, rcx
0x180004d60  jnz     short loc_180004D57
0x180004d62  mov     r9, [rbx+18h]
0x180004d66  test    r9, r9
0x180004d69  jz      short loc_180004DDA
0x180004d6b  test    esi, esi
0x180004d6d  jz      short loc_180004DA0
0x180004d6f  movzx   eax, word ptr [rbx+20h]
0x180004d73  mov     rcx, r9
0x180004d76  lea     rdx, [rax+rax*4]
0x180004d7a  shl     rdx, 4
0x180004d7e  add     rdx, r9
0x180004d81  cmp     r9, rdx
0x180004d84  jz      short loc_180004DA0
0x180004d86  mov     r8d, [rbx+10h]
0x180004d8a  cmp     [rcx+4], r8d
0x180004d8e  jbe     short loc_180004D98
0x180004d90  mov     eax, [rdi+8]
0x180004d93  cmp     [rcx+8], eax
0x180004d96  jz      short loc_180004DDA
0x180004d98  add     rcx, rbp
0x180004d9b  cmp     rcx, rdx
0x180004d9e  jnz     short loc_180004D8A
0x180004da0  movzx   eax, word ptr [rbx+22h]
0x180004da4  xor     edx, edx
0x180004da6  movzx   ecx, word ptr [rbx+20h]
0x180004daa  inc     eax
0x180004dac  div     ecx
0x180004dae  mov     rax, [rbx+8]
0x180004db2  mov     r8d, 1
0x180004db8  mov     [rbx+22h], dx
0x180004dbc  lock xadd [rax], r8d
0x180004dc1  movzx   eax, dx
0x180004dc4  inc     r8d; unsigned int
0x180004dc7  mov     rdx, rdi; struct wil::FailureInfo *
0x180004dca  lea     rcx, [rax+rax*4]
0x180004dce  shl     rcx, 4
0x180004dd2  add     rcx, r9; this
0x180004dd5  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180004dda  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004de4  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004deb  add     rsp, 20h
0x180004def  pop     r14
0x180004df1  pop     rdi
0x180004df2  pop     rsi
0x180004df3  pop     rbp
0x180004df4  pop     rbx
0x180004df5  retn
```
