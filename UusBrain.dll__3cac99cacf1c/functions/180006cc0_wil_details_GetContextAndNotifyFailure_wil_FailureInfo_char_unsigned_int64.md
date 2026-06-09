# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180006cc0`
- end: `0x180006eca`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `522`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004dfc`
- `0x180006864`
- `0x180006b04`
- `0x180006bc4`
- `0x180006cc0`
- `0x180047a30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006cf2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006da7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006cf2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006da7`

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
  struct wil::details::ThreadFailureCallbackHolder **v10; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v11; // rbx
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
    this = 10 * (CurrentThreadId / 0xA);
    for ( i = *(_QWORD *)(v7 + 8 * (CurrentThreadId % 0xA)); ; i = *(_QWORD *)(i + 8) )
    {
      if ( !i )
      {
        v10 = 0;
        goto LABEL_7;
      }
      if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
        break;
    }
    v10 = (struct wil::details::ThreadFailureCallbackHolder **)(i + 16);
LABEL_7:
    if ( v10 && *v10 )
    {
      *(_BYTE *)a2 = 0;
      if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(v5, *v10, (char *)a2, (unsigned __int64)a3) )
        *((_QWORD *)v5 + 9) = a2;
      v11 = *v10;
      do
      {
        v6 |= (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v11 + 1))(*((_QWORD *)v11 + 1), v5);
        v11 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v11 + 2);
      }
      while ( v11 );
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( v6 || (LOBYTE(this) = 0, (*((_BYTE *)v5 + 4) & 2) != 0) )
      LOBYTE(this) = 1;
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
LABEL_34:
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
                goto LABEL_34;
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
0x180006cc0  mov     [rsp+arg_18], rbx
0x180006cc5  push    rbp
0x180006cc6  push    rsi
0x180006cc7  push    rdi
0x180006cc8  push    r14
0x180006cca  push    r15
0x180006ccc  sub     rsp, 20h
0x180006cd0  mov     r14, r8
0x180006cd3  mov     rsi, rdx
0x180006cd6  mov     rdi, rcx
0x180006cd9  xor     r15d, r15d
0x180006cdc  mov     [rdx], r15b
0x180006cdf  mov     bpl, r15b
0x180006ce2  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006ce9  test    rbx, rbx
0x180006cec  jz      loc_180006D7B
0x180006cf2  call    cs:__imp_GetCurrentThreadId
0x180006cf8  mov     r9d, eax
0x180006cfb  mov     r8d, eax
0x180006cfe  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006d08  mul     r9
0x180006d0b  shr     rdx, 3
0x180006d0f  lea     rcx, [rdx+rdx*4]
0x180006d13  add     rcx, rcx
0x180006d16  sub     r8, rcx
0x180006d19  mov     rbx, [rbx+r8*8]
0x180006d1d  jmp     short loc_180006D2C
0x180006d1f  cmp     [rbx], r9d
0x180006d22  jz      loc_180006E21
0x180006d28  mov     rbx, [rbx+8]
0x180006d2c  test    rbx, rbx
0x180006d2f  jnz     short loc_180006D1F
0x180006d31  mov     rbx, r15
0x180006d34  test    rbx, rbx
0x180006d37  jz      short loc_180006D7B
0x180006d39  cmp     [rbx], r15
0x180006d3c  jz      short loc_180006D7B
0x180006d3e  mov     [rsi], r15b
0x180006d41  mov     r9, r14; unsigned __int64
0x180006d44  mov     r8, rsi; char *
0x180006d47  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180006d4a  mov     rcx, rdi; struct wil::FailureInfo *
0x180006d4d  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180006d52  test    al, al
0x180006d54  jz      short loc_180006D5A
0x180006d56  mov     [rdi+48h], rsi
0x180006d5a  mov     rbx, [rbx]
0x180006d5d  mov     rcx, [rbx+8]
0x180006d61  mov     rax, [rcx]
0x180006d64  mov     rdx, rdi
0x180006d67  mov     rax, [rax]
0x180006d6a  call    _guard_dispatch_icall
0x180006d6f  or      bpl, al
0x180006d72  mov     rbx, [rbx+10h]
0x180006d76  test    rbx, rbx
0x180006d79  jnz     short loc_180006D5D
0x180006d7b  mov     r14d, 1
0x180006d81  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180006d88  test    rax, rax
0x180006d8b  jz      short loc_180006DA7
0x180006d8d  test    bpl, bpl
0x180006d90  jnz     short loc_180006D9B
0x180006d92  test    byte ptr [rdi+4], 2
0x180006d96  mov     cl, r15b
0x180006d99  jz      short loc_180006D9E
0x180006d9b  mov     cl, r14b
0x180006d9e  mov     rdx, rdi
0x180006da1  call    _guard_dispatch_icall
0x180006da6  nop
0x180006da7  call    cs:__imp_GetCurrentThreadId
0x180006dad  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006db3  cmp     ecx, eax
0x180006db5  jz      loc_180006EB9
0x180006dbb  mov     ecx, r14d
0x180006dbe  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180006dc6  add     ecx, r14d; this
0x180006dc9  cmp     ecx, 4
0x180006dcc  jge     loc_180006EB2
0x180006dd2  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006dd8  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180006ddd  mov     rbx, rax
0x180006de0  test    rax, rax
0x180006de3  jz      loc_180006EAB
0x180006de9  mov     esi, [rax+10h]
0x180006dec  mov     ebp, 50h ; 'P'
0x180006df1  cmp     [rax+18h], r15
0x180006df5  jnz     short loc_180006E35
0x180006df7  test    esi, esi
0x180006df9  jz      short loc_180006E35
0x180006dfb  mov     edx, 190h; dwBytes
0x180006e00  lea     ecx, [rbp-48h]; dwFlags
0x180006e03  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006e08  mov     [rbx+18h], rax
0x180006e0c  test    rax, rax
0x180006e0f  jz      short loc_180006E35
0x180006e11  mov     dword ptr [rbx+20h], 5
0x180006e18  lea     rcx, [rax+190h]
0x180006e1f  jmp     short loc_180006E30
0x180006e21  add     rbx, 10h
0x180006e25  jmp     loc_180006D34
0x180006e2a  mov     [rax], bp
0x180006e2d  add     rax, rbp
0x180006e30  cmp     rax, rcx
0x180006e33  jnz     short loc_180006E2A
0x180006e35  mov     r9, [rbx+18h]
0x180006e39  test    r9, r9
0x180006e3c  jz      short loc_180006EAB
0x180006e3e  test    esi, esi
0x180006e40  jz      short loc_180006E73
0x180006e42  mov     rcx, r9
0x180006e45  movzx   eax, word ptr [rbx+20h]
0x180006e49  lea     rdx, [rax+rax*4]
0x180006e4d  shl     rdx, 4
0x180006e51  add     rdx, r9
0x180006e54  cmp     r9, rdx
0x180006e57  jz      short loc_180006E73
0x180006e59  mov     r8d, [rbx+10h]
0x180006e5d  cmp     [rcx+4], r8d
0x180006e61  jbe     short loc_180006E6B
0x180006e63  mov     eax, [rdi+8]
0x180006e66  cmp     [rcx+8], eax
0x180006e69  jz      short loc_180006EAB
0x180006e6b  add     rcx, rbp
0x180006e6e  cmp     rcx, rdx
0x180006e71  jnz     short loc_180006E5D
0x180006e73  movzx   eax, word ptr [rbx+22h]
0x180006e77  add     eax, r14d
0x180006e7a  movzx   ecx, word ptr [rbx+20h]
0x180006e7e  xor     edx, edx
0x180006e80  div     ecx
0x180006e82  mov     [rbx+22h], dx
0x180006e86  mov     rax, [rbx+8]
0x180006e8a  mov     r8d, r14d
0x180006e8d  lock xadd [rax], r8d
0x180006e92  add     r8d, r14d; unsigned int
0x180006e95  movzx   eax, dx
0x180006e98  lea     rcx, [rax+rax*4]
0x180006e9c  shl     rcx, 4
0x180006ea0  add     rcx, r9; this
0x180006ea3  mov     rdx, rdi; struct wil::FailureInfo *
0x180006ea6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180006eab  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, r15d; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006eb2  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180006eb9  mov     rbx, [rsp+48h+arg_18]
0x180006ebe  add     rsp, 20h
0x180006ec2  pop     r15
0x180006ec4  pop     r14
0x180006ec6  pop     rdi
0x180006ec7  pop     rsi
0x180006ec8  pop     rbp
0x180006ec9  retn
```
