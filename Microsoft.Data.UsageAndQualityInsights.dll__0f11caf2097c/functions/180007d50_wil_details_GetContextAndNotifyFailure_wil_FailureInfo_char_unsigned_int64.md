# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180007d50`
- end: `0x180007f57`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180007d50`
- `0x1800084f0`
- `0x1800085d4`
- `0x180009058`
- `0x18000a984`
- `0x180108010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007d7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007e3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007d7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007e3c`

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
0x180007d50  push    rbx
0x180007d52  push    rbp
0x180007d53  push    rsi
0x180007d54  push    rdi
0x180007d55  push    r14
0x180007d57  sub     rsp, 20h
0x180007d5b  mov     r14, r8
0x180007d5e  mov     rsi, rdx
0x180007d61  mov     rdi, rcx
0x180007d64  mov     byte ptr [rdx], 0
0x180007d67  xor     bpl, bpl
0x180007d6a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180007d71  test    rbx, rbx
0x180007d74  jz      loc_180007E10
0x180007d7a  call    cs:__imp_GetCurrentThreadId
0x180007d80  mov     r9d, eax
0x180007d83  mov     r8d, eax
0x180007d86  shr     r8, 2
0x180007d8a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007d94  mul     r8
0x180007d97  shr     rdx, 3
0x180007d9b  lea     rcx, [rdx+rdx*4]
0x180007d9f  add     rcx, rcx
0x180007da2  sub     r8, rcx
0x180007da5  mov     rbx, [rbx+r8*8]
0x180007da9  jmp     short loc_180007DB4
0x180007dab  cmp     [rbx], r9d
0x180007dae  jz      short loc_180007E2B
0x180007db0  mov     rbx, [rbx+8]
0x180007db4  test    rbx, rbx
0x180007db7  jnz     short loc_180007DAB
0x180007db9  test    rbx, rbx
0x180007dbc  jz      short loc_180007E10
0x180007dbe  cmp     qword ptr [rbx], 0
0x180007dc2  jz      short loc_180007E10
0x180007dc4  mov     [rsi], bpl
0x180007dc7  mov     r9, r14; unsigned __int64
0x180007dca  mov     r8, rsi; char *
0x180007dcd  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180007dd0  mov     rcx, rdi; struct wil::FailureInfo *
0x180007dd3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180007dd8  test    al, al
0x180007dda  jz      short loc_180007DE0
0x180007ddc  mov     [rdi+48h], rsi
0x180007de0  mov     rbx, [rbx]
0x180007de3  mov     al, [rbx+28h]
0x180007de6  mov     byte ptr [rbx+28h], 1
0x180007dea  test    al, al
0x180007dec  jnz     short loc_180007E07
0x180007dee  mov     rcx, [rbx+8]
0x180007df2  mov     rax, [rcx]
0x180007df5  mov     rdx, rdi
0x180007df8  mov     rax, [rax]
0x180007dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e00  or      bpl, al
0x180007e03  mov     byte ptr [rbx+28h], 0
0x180007e07  mov     rbx, [rbx+10h]
0x180007e0b  test    rbx, rbx
0x180007e0e  jnz     short loc_180007DE3
0x180007e10  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180007e17  test    rax, rax
0x180007e1a  jz      short loc_180007E3C
0x180007e1c  test    bpl, bpl
0x180007e1f  jnz     short loc_180007E31
0x180007e21  test    byte ptr [rdi+4], 2
0x180007e25  jnz     short loc_180007E31
0x180007e27  xor     ecx, ecx
0x180007e29  jmp     short loc_180007E33
0x180007e2b  add     rbx, 10h
0x180007e2f  jmp     short loc_180007DB9
0x180007e31  mov     cl, 1
0x180007e33  mov     rdx, rdi
0x180007e36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e3b  nop
0x180007e3c  call    cs:__imp_GetCurrentThreadId
0x180007e42  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007e48  cmp     ecx, eax
0x180007e4a  jz      loc_180007F4C
0x180007e50  mov     ecx, 1
0x180007e55  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180007e5d  inc     ecx; this
0x180007e5f  cmp     ecx, 4
0x180007e62  jge     loc_180007F45
0x180007e68  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007e6e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180007e73  mov     rbx, rax
0x180007e76  test    rax, rax
0x180007e79  jz      loc_180007F3B
0x180007e7f  mov     esi, [rax+10h]
0x180007e82  mov     ebp, 50h ; 'P'
0x180007e87  cmp     qword ptr [rax+18h], 0
0x180007e8c  jnz     short loc_180007EC3
0x180007e8e  test    esi, esi
0x180007e90  jz      short loc_180007EC3
0x180007e92  mov     edx, 190h; dwBytes
0x180007e97  lea     ecx, [rbp-48h]; dwFlags
0x180007e9a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007e9f  mov     [rbx+18h], rax
0x180007ea3  test    rax, rax
0x180007ea6  jz      short loc_180007EC3
0x180007ea8  mov     dword ptr [rbx+20h], 5
0x180007eaf  lea     rcx, [rax+190h]
0x180007eb6  jmp     short loc_180007EBE
0x180007eb8  mov     [rax], bp
0x180007ebb  add     rax, rbp
0x180007ebe  cmp     rax, rcx
0x180007ec1  jnz     short loc_180007EB8
0x180007ec3  mov     r9, [rbx+18h]
0x180007ec7  test    r9, r9
0x180007eca  jz      short loc_180007F3B
0x180007ecc  test    esi, esi
0x180007ece  jz      short loc_180007F01
0x180007ed0  mov     rcx, r9
0x180007ed3  movzx   eax, word ptr [rbx+20h]
0x180007ed7  lea     rdx, [rax+rax*4]
0x180007edb  shl     rdx, 4
0x180007edf  add     rdx, r9
0x180007ee2  cmp     r9, rdx
0x180007ee5  jz      short loc_180007F01
0x180007ee7  mov     r8d, [rbx+10h]
0x180007eeb  cmp     [rcx+4], r8d
0x180007eef  jbe     short loc_180007EF9
0x180007ef1  mov     eax, [rdi+8]
0x180007ef4  cmp     [rcx+8], eax
0x180007ef7  jz      short loc_180007F3B
0x180007ef9  add     rcx, rbp
0x180007efc  cmp     rcx, rdx
0x180007eff  jnz     short loc_180007EEB
0x180007f01  movzx   eax, word ptr [rbx+22h]
0x180007f05  inc     eax
0x180007f07  movzx   ecx, word ptr [rbx+20h]
0x180007f0b  xor     edx, edx
0x180007f0d  div     ecx
0x180007f0f  mov     [rbx+22h], dx
0x180007f13  mov     rax, [rbx+8]
0x180007f17  mov     r8d, 1
0x180007f1d  lock xadd [rax], r8d
0x180007f22  inc     r8d; unsigned int
0x180007f25  movzx   eax, dx
0x180007f28  lea     rcx, [rax+rax*4]
0x180007f2c  shl     rcx, 4
0x180007f30  add     rcx, r9; this
0x180007f33  mov     rdx, rdi; struct wil::FailureInfo *
0x180007f36  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180007f3b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007f45  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180007f4c  add     rsp, 20h
0x180007f50  pop     r14
0x180007f52  pop     rdi
0x180007f53  pop     rsi
0x180007f54  pop     rbp
0x180007f55  pop     rbx
0x180007f56  retn
```
