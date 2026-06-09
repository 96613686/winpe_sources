# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140002b90`
- end: `0x140002d96`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140002b90`
- `0x140003288`
- `0x14000336c`
- `0x140003bd8`
- `0x140003f20`
- `0x140005010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140002bba`
- `KERNEL32!GetCurrentThreadId` at `0x140002c7b`
- `KERNEL32!GetCurrentThreadId` at `0x140002bba`
- `KERNEL32!GetCurrentThreadId` at `0x140002c7b`

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
0x140002b90  push    rbx
0x140002b92  push    rbp
0x140002b93  push    rsi
0x140002b94  push    rdi
0x140002b95  push    r14
0x140002b97  sub     rsp, 20h
0x140002b9b  mov     byte ptr [rdx], 0
0x140002b9e  xor     bpl, bpl
0x140002ba1  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140002ba8  mov     r14, r8
0x140002bab  mov     rsi, rdx
0x140002bae  mov     rdi, rcx
0x140002bb1  test    rbx, rbx
0x140002bb4  jz      loc_140002C50
0x140002bba  call    cs:__imp_GetCurrentThreadId
0x140002bc0  mov     r8d, eax
0x140002bc3  mov     r9d, eax
0x140002bc6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140002bd0  shr     r8, 2
0x140002bd4  mul     r8
0x140002bd7  shr     rdx, 3
0x140002bdb  lea     rcx, [rdx+rdx*4]
0x140002bdf  add     rcx, rcx
0x140002be2  sub     r8, rcx
0x140002be5  mov     rbx, [rbx+r8*8]
0x140002be9  jmp     short loc_140002BF4
0x140002beb  cmp     [rbx], r9d
0x140002bee  jz      short loc_140002C6B
0x140002bf0  mov     rbx, [rbx+8]
0x140002bf4  test    rbx, rbx
0x140002bf7  jnz     short loc_140002BEB
0x140002bf9  test    rbx, rbx
0x140002bfc  jz      short loc_140002C50
0x140002bfe  cmp     qword ptr [rbx], 0
0x140002c02  jz      short loc_140002C50
0x140002c04  mov     [rsi], bpl
0x140002c07  mov     r9, r14; unsigned __int64
0x140002c0a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x140002c0d  mov     r8, rsi; char *
0x140002c10  mov     rcx, rdi; struct wil::FailureInfo *
0x140002c13  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140002c18  test    al, al
0x140002c1a  jz      short loc_140002C20
0x140002c1c  mov     [rdi+48h], rsi
0x140002c20  mov     rbx, [rbx]
0x140002c23  mov     al, [rbx+28h]
0x140002c26  mov     byte ptr [rbx+28h], 1
0x140002c2a  test    al, al
0x140002c2c  jnz     short loc_140002C47
0x140002c2e  mov     rcx, [rbx+8]
0x140002c32  mov     rdx, rdi
0x140002c35  mov     rax, [rcx]
0x140002c38  mov     rax, [rax]
0x140002c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c40  or      bpl, al
0x140002c43  mov     byte ptr [rbx+28h], 0
0x140002c47  mov     rbx, [rbx+10h]
0x140002c4b  test    rbx, rbx
0x140002c4e  jnz     short loc_140002C23
0x140002c50  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140002c57  test    rax, rax
0x140002c5a  jz      short loc_140002C7B
0x140002c5c  test    bpl, bpl
0x140002c5f  jnz     short loc_140002C71
0x140002c61  test    byte ptr [rdi+4], 2
0x140002c65  jnz     short loc_140002C71
0x140002c67  xor     ecx, ecx
0x140002c69  jmp     short loc_140002C73
0x140002c6b  add     rbx, 10h
0x140002c6f  jmp     short loc_140002BF9
0x140002c71  mov     cl, 1
0x140002c73  mov     rdx, rdi
0x140002c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c7b  call    cs:__imp_GetCurrentThreadId
0x140002c81  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140002c87  cmp     ecx, eax
0x140002c89  jz      loc_140002D8B
0x140002c8f  mov     ecx, 1
0x140002c94  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140002c9c  inc     ecx; this
0x140002c9e  cmp     ecx, 4
0x140002ca1  jge     loc_140002D84
0x140002ca7  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140002cad  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140002cb2  mov     rbx, rax
0x140002cb5  test    rax, rax
0x140002cb8  jz      loc_140002D7A
0x140002cbe  cmp     qword ptr [rax+18h], 0
0x140002cc3  mov     ebp, 50h ; 'P'
0x140002cc8  mov     esi, [rax+10h]
0x140002ccb  jnz     short loc_140002D02
0x140002ccd  test    esi, esi
0x140002ccf  jz      short loc_140002D02
0x140002cd1  mov     edx, 190h; dwBytes
0x140002cd6  lea     ecx, [rbp-48h]; dwFlags
0x140002cd9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140002cde  mov     [rbx+18h], rax
0x140002ce2  test    rax, rax
0x140002ce5  jz      short loc_140002D02
0x140002ce7  mov     dword ptr [rbx+20h], 5
0x140002cee  lea     rcx, [rax+190h]
0x140002cf5  jmp     short loc_140002CFD
0x140002cf7  mov     [rax], bp
0x140002cfa  add     rax, rbp
0x140002cfd  cmp     rax, rcx
0x140002d00  jnz     short loc_140002CF7
0x140002d02  mov     r9, [rbx+18h]
0x140002d06  test    r9, r9
0x140002d09  jz      short loc_140002D7A
0x140002d0b  test    esi, esi
0x140002d0d  jz      short loc_140002D40
0x140002d0f  movzx   eax, word ptr [rbx+20h]
0x140002d13  mov     rcx, r9
0x140002d16  lea     rdx, [rax+rax*4]
0x140002d1a  shl     rdx, 4
0x140002d1e  add     rdx, r9
0x140002d21  cmp     r9, rdx
0x140002d24  jz      short loc_140002D40
0x140002d26  mov     r8d, [rbx+10h]
0x140002d2a  cmp     [rcx+4], r8d
0x140002d2e  jbe     short loc_140002D38
0x140002d30  mov     eax, [rdi+8]
0x140002d33  cmp     [rcx+8], eax
0x140002d36  jz      short loc_140002D7A
0x140002d38  add     rcx, rbp
0x140002d3b  cmp     rcx, rdx
0x140002d3e  jnz     short loc_140002D2A
0x140002d40  movzx   eax, word ptr [rbx+22h]
0x140002d44  xor     edx, edx
0x140002d46  movzx   ecx, word ptr [rbx+20h]
0x140002d4a  inc     eax
0x140002d4c  div     ecx
0x140002d4e  mov     rax, [rbx+8]
0x140002d52  mov     r8d, 1
0x140002d58  mov     [rbx+22h], dx
0x140002d5c  lock xadd [rax], r8d
0x140002d61  movzx   eax, dx
0x140002d64  inc     r8d; unsigned int
0x140002d67  mov     rdx, rdi; struct wil::FailureInfo *
0x140002d6a  lea     rcx, [rax+rax*4]
0x140002d6e  shl     rcx, 4
0x140002d72  add     rcx, r9; this
0x140002d75  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x140002d7a  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140002d84  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140002d8b  add     rsp, 20h
0x140002d8f  pop     r14
0x140002d91  pop     rdi
0x140002d92  pop     rsi
0x140002d93  pop     rbp
0x140002d94  pop     rbx
0x140002d95  retn
```
