# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180007a90`
- end: `0x180007c97`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180007a90`
- `0x180007e68`
- `0x180007f4c`
- `0x180008288`
- `0x180008560`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007aba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007b7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007aba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007b7c`

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
0x180007a90  push    rbx
0x180007a92  push    rbp
0x180007a93  push    rsi
0x180007a94  push    rdi
0x180007a95  push    r14
0x180007a97  sub     rsp, 20h
0x180007a9b  mov     r14, r8
0x180007a9e  mov     rsi, rdx
0x180007aa1  mov     rdi, rcx
0x180007aa4  mov     byte ptr [rdx], 0
0x180007aa7  xor     bpl, bpl
0x180007aaa  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180007ab1  test    rbx, rbx
0x180007ab4  jz      loc_180007B50
0x180007aba  call    cs:__imp_GetCurrentThreadId
0x180007ac0  mov     r9d, eax
0x180007ac3  mov     r8d, eax
0x180007ac6  shr     r8, 2
0x180007aca  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007ad4  mul     r8
0x180007ad7  shr     rdx, 3
0x180007adb  lea     rcx, [rdx+rdx*4]
0x180007adf  add     rcx, rcx
0x180007ae2  sub     r8, rcx
0x180007ae5  mov     rbx, [rbx+r8*8]
0x180007ae9  jmp     short loc_180007AF4
0x180007aeb  cmp     [rbx], r9d
0x180007aee  jz      short loc_180007B6B
0x180007af0  mov     rbx, [rbx+8]
0x180007af4  test    rbx, rbx
0x180007af7  jnz     short loc_180007AEB
0x180007af9  test    rbx, rbx
0x180007afc  jz      short loc_180007B50
0x180007afe  cmp     qword ptr [rbx], 0
0x180007b02  jz      short loc_180007B50
0x180007b04  mov     [rsi], bpl
0x180007b07  mov     r9, r14; unsigned __int64
0x180007b0a  mov     r8, rsi; char *
0x180007b0d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180007b10  mov     rcx, rdi; struct wil::FailureInfo *
0x180007b13  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180007b18  test    al, al
0x180007b1a  jz      short loc_180007B20
0x180007b1c  mov     [rdi+48h], rsi
0x180007b20  mov     rbx, [rbx]
0x180007b23  mov     al, [rbx+28h]
0x180007b26  mov     byte ptr [rbx+28h], 1
0x180007b2a  test    al, al
0x180007b2c  jnz     short loc_180007B47
0x180007b2e  mov     rcx, [rbx+8]
0x180007b32  mov     rax, [rcx]
0x180007b35  mov     rdx, rdi
0x180007b38  mov     rax, [rax]
0x180007b3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b40  or      bpl, al
0x180007b43  mov     byte ptr [rbx+28h], 0
0x180007b47  mov     rbx, [rbx+10h]
0x180007b4b  test    rbx, rbx
0x180007b4e  jnz     short loc_180007B23
0x180007b50  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180007b57  test    rax, rax
0x180007b5a  jz      short loc_180007B7C
0x180007b5c  test    bpl, bpl
0x180007b5f  jnz     short loc_180007B71
0x180007b61  test    byte ptr [rdi+4], 2
0x180007b65  jnz     short loc_180007B71
0x180007b67  xor     ecx, ecx
0x180007b69  jmp     short loc_180007B73
0x180007b6b  add     rbx, 10h
0x180007b6f  jmp     short loc_180007AF9
0x180007b71  mov     cl, 1
0x180007b73  mov     rdx, rdi
0x180007b76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b7b  nop
0x180007b7c  call    cs:__imp_GetCurrentThreadId
0x180007b82  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007b88  cmp     ecx, eax
0x180007b8a  jz      loc_180007C8C
0x180007b90  mov     ecx, 1
0x180007b95  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180007b9d  inc     ecx; this
0x180007b9f  cmp     ecx, 4
0x180007ba2  jge     loc_180007C85
0x180007ba8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007bae  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180007bb3  mov     rbx, rax
0x180007bb6  test    rax, rax
0x180007bb9  jz      loc_180007C7B
0x180007bbf  mov     esi, [rax+10h]
0x180007bc2  mov     ebp, 50h ; 'P'
0x180007bc7  cmp     qword ptr [rax+18h], 0
0x180007bcc  jnz     short loc_180007C03
0x180007bce  test    esi, esi
0x180007bd0  jz      short loc_180007C03
0x180007bd2  mov     edx, 190h; dwBytes
0x180007bd7  lea     ecx, [rbp-48h]; dwFlags
0x180007bda  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007bdf  mov     [rbx+18h], rax
0x180007be3  test    rax, rax
0x180007be6  jz      short loc_180007C03
0x180007be8  mov     dword ptr [rbx+20h], 5
0x180007bef  lea     rcx, [rax+190h]
0x180007bf6  jmp     short loc_180007BFE
0x180007bf8  mov     [rax], bp
0x180007bfb  add     rax, rbp
0x180007bfe  cmp     rax, rcx
0x180007c01  jnz     short loc_180007BF8
0x180007c03  mov     r9, [rbx+18h]
0x180007c07  test    r9, r9
0x180007c0a  jz      short loc_180007C7B
0x180007c0c  test    esi, esi
0x180007c0e  jz      short loc_180007C41
0x180007c10  mov     rcx, r9
0x180007c13  movzx   eax, word ptr [rbx+20h]
0x180007c17  lea     rdx, [rax+rax*4]
0x180007c1b  shl     rdx, 4
0x180007c1f  add     rdx, r9
0x180007c22  cmp     r9, rdx
0x180007c25  jz      short loc_180007C41
0x180007c27  mov     r8d, [rbx+10h]
0x180007c2b  cmp     [rcx+4], r8d
0x180007c2f  jbe     short loc_180007C39
0x180007c31  mov     eax, [rdi+8]
0x180007c34  cmp     [rcx+8], eax
0x180007c37  jz      short loc_180007C7B
0x180007c39  add     rcx, rbp
0x180007c3c  cmp     rcx, rdx
0x180007c3f  jnz     short loc_180007C2B
0x180007c41  movzx   eax, word ptr [rbx+22h]
0x180007c45  inc     eax
0x180007c47  movzx   ecx, word ptr [rbx+20h]
0x180007c4b  xor     edx, edx
0x180007c4d  div     ecx
0x180007c4f  mov     [rbx+22h], dx
0x180007c53  mov     rax, [rbx+8]
0x180007c57  mov     r8d, 1
0x180007c5d  lock xadd [rax], r8d
0x180007c62  inc     r8d; unsigned int
0x180007c65  movzx   eax, dx
0x180007c68  lea     rcx, [rax+rax*4]
0x180007c6c  shl     rcx, 4
0x180007c70  add     rcx, r9; this
0x180007c73  mov     rdx, rdi; struct wil::FailureInfo *
0x180007c76  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180007c7b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007c85  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180007c8c  add     rsp, 20h
0x180007c90  pop     r14
0x180007c92  pop     rdi
0x180007c93  pop     rsi
0x180007c94  pop     rbp
0x180007c95  pop     rbx
0x180007c96  retn
```
