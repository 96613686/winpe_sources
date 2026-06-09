# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004d60`
- end: `0x180004f67`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004d60`
- `0x180005500`
- `0x1800055e4`
- `0x180005e58`
- `0x180006334`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e4c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e4c`

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
0x180004d60  push    rbx
0x180004d62  push    rbp
0x180004d63  push    rsi
0x180004d64  push    rdi
0x180004d65  push    r14
0x180004d67  sub     rsp, 20h
0x180004d6b  mov     r14, r8
0x180004d6e  mov     rsi, rdx
0x180004d71  mov     rdi, rcx
0x180004d74  mov     byte ptr [rdx], 0
0x180004d77  xor     bpl, bpl
0x180004d7a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004d81  test    rbx, rbx
0x180004d84  jz      loc_180004E20
0x180004d8a  call    cs:__imp_GetCurrentThreadId
0x180004d90  mov     r9d, eax
0x180004d93  mov     r8d, eax
0x180004d96  shr     r8, 2
0x180004d9a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004da4  mul     r8
0x180004da7  shr     rdx, 3
0x180004dab  lea     rcx, [rdx+rdx*4]
0x180004daf  add     rcx, rcx
0x180004db2  sub     r8, rcx
0x180004db5  mov     rbx, [rbx+r8*8]
0x180004db9  jmp     short loc_180004DC4
0x180004dbb  cmp     [rbx], r9d
0x180004dbe  jz      short loc_180004E3B
0x180004dc0  mov     rbx, [rbx+8]
0x180004dc4  test    rbx, rbx
0x180004dc7  jnz     short loc_180004DBB
0x180004dc9  test    rbx, rbx
0x180004dcc  jz      short loc_180004E20
0x180004dce  cmp     qword ptr [rbx], 0
0x180004dd2  jz      short loc_180004E20
0x180004dd4  mov     [rsi], bpl
0x180004dd7  mov     r9, r14; unsigned __int64
0x180004dda  mov     r8, rsi; char *
0x180004ddd  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004de0  mov     rcx, rdi; struct wil::FailureInfo *
0x180004de3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004de8  test    al, al
0x180004dea  jz      short loc_180004DF0
0x180004dec  mov     [rdi+48h], rsi
0x180004df0  mov     rbx, [rbx]
0x180004df3  mov     al, [rbx+28h]
0x180004df6  mov     byte ptr [rbx+28h], 1
0x180004dfa  test    al, al
0x180004dfc  jnz     short loc_180004E17
0x180004dfe  mov     rcx, [rbx+8]
0x180004e02  mov     rax, [rcx]
0x180004e05  mov     rdx, rdi
0x180004e08  mov     rax, [rax]
0x180004e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e10  or      bpl, al
0x180004e13  mov     byte ptr [rbx+28h], 0
0x180004e17  mov     rbx, [rbx+10h]
0x180004e1b  test    rbx, rbx
0x180004e1e  jnz     short loc_180004DF3
0x180004e20  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004e27  test    rax, rax
0x180004e2a  jz      short loc_180004E4C
0x180004e2c  test    bpl, bpl
0x180004e2f  jnz     short loc_180004E41
0x180004e31  test    byte ptr [rdi+4], 2
0x180004e35  jnz     short loc_180004E41
0x180004e37  xor     ecx, ecx
0x180004e39  jmp     short loc_180004E43
0x180004e3b  add     rbx, 10h
0x180004e3f  jmp     short loc_180004DC9
0x180004e41  mov     cl, 1
0x180004e43  mov     rdx, rdi
0x180004e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e4b  nop
0x180004e4c  call    cs:__imp_GetCurrentThreadId
0x180004e52  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004e58  cmp     ecx, eax
0x180004e5a  jz      loc_180004F5C
0x180004e60  mov     ecx, 1
0x180004e65  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004e6d  inc     ecx; this
0x180004e6f  cmp     ecx, 4
0x180004e72  jge     loc_180004F55
0x180004e78  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004e7e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180004e83  mov     rbx, rax
0x180004e86  test    rax, rax
0x180004e89  jz      loc_180004F4B
0x180004e8f  mov     esi, [rax+10h]
0x180004e92  mov     ebp, 50h ; 'P'
0x180004e97  cmp     qword ptr [rax+18h], 0
0x180004e9c  jnz     short loc_180004ED3
0x180004e9e  test    esi, esi
0x180004ea0  jz      short loc_180004ED3
0x180004ea2  mov     edx, 190h; dwBytes
0x180004ea7  lea     ecx, [rbp-48h]; dwFlags
0x180004eaa  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004eaf  mov     [rbx+18h], rax
0x180004eb3  test    rax, rax
0x180004eb6  jz      short loc_180004ED3
0x180004eb8  mov     dword ptr [rbx+20h], 5
0x180004ebf  lea     rcx, [rax+190h]
0x180004ec6  jmp     short loc_180004ECE
0x180004ec8  mov     [rax], bp
0x180004ecb  add     rax, rbp
0x180004ece  cmp     rax, rcx
0x180004ed1  jnz     short loc_180004EC8
0x180004ed3  mov     r9, [rbx+18h]
0x180004ed7  test    r9, r9
0x180004eda  jz      short loc_180004F4B
0x180004edc  test    esi, esi
0x180004ede  jz      short loc_180004F11
0x180004ee0  mov     rcx, r9
0x180004ee3  movzx   eax, word ptr [rbx+20h]
0x180004ee7  lea     rdx, [rax+rax*4]
0x180004eeb  shl     rdx, 4
0x180004eef  add     rdx, r9
0x180004ef2  cmp     r9, rdx
0x180004ef5  jz      short loc_180004F11
0x180004ef7  mov     r8d, [rbx+10h]
0x180004efb  cmp     [rcx+4], r8d
0x180004eff  jbe     short loc_180004F09
0x180004f01  mov     eax, [rdi+8]
0x180004f04  cmp     [rcx+8], eax
0x180004f07  jz      short loc_180004F4B
0x180004f09  add     rcx, rbp
0x180004f0c  cmp     rcx, rdx
0x180004f0f  jnz     short loc_180004EFB
0x180004f11  movzx   eax, word ptr [rbx+22h]
0x180004f15  inc     eax
0x180004f17  movzx   ecx, word ptr [rbx+20h]
0x180004f1b  xor     edx, edx
0x180004f1d  div     ecx
0x180004f1f  mov     [rbx+22h], dx
0x180004f23  mov     rax, [rbx+8]
0x180004f27  mov     r8d, 1
0x180004f2d  lock xadd [rax], r8d
0x180004f32  inc     r8d; unsigned int
0x180004f35  movzx   eax, dx
0x180004f38  lea     rcx, [rax+rax*4]
0x180004f3c  shl     rcx, 4
0x180004f40  add     rcx, r9; this
0x180004f43  mov     rdx, rdi; struct wil::FailureInfo *
0x180004f46  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180004f4b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004f55  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004f5c  add     rsp, 20h
0x180004f60  pop     r14
0x180004f62  pop     rdi
0x180004f63  pop     rsi
0x180004f64  pop     rbp
0x180004f65  pop     rbx
0x180004f66  retn
```
