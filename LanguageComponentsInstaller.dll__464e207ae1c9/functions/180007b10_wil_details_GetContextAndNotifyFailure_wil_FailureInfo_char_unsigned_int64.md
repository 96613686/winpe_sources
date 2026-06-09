# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180007b10`
- end: `0x180007d17`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180007b10`
- `0x1800082b0`
- `0x180008394`
- `0x180008d74`
- `0x180009394`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007b3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007bfc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007b3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007bfc`

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
0x180007b10  push    rbx
0x180007b12  push    rbp
0x180007b13  push    rsi
0x180007b14  push    rdi
0x180007b15  push    r14
0x180007b17  sub     rsp, 20h
0x180007b1b  mov     r14, r8
0x180007b1e  mov     rsi, rdx
0x180007b21  mov     rdi, rcx
0x180007b24  mov     byte ptr [rdx], 0
0x180007b27  xor     bpl, bpl
0x180007b2a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180007b31  test    rbx, rbx
0x180007b34  jz      loc_180007BD0
0x180007b3a  call    cs:__imp_GetCurrentThreadId
0x180007b40  mov     r9d, eax
0x180007b43  mov     r8d, eax
0x180007b46  shr     r8, 2
0x180007b4a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007b54  mul     r8
0x180007b57  shr     rdx, 3
0x180007b5b  lea     rcx, [rdx+rdx*4]
0x180007b5f  add     rcx, rcx
0x180007b62  sub     r8, rcx
0x180007b65  mov     rbx, [rbx+r8*8]
0x180007b69  jmp     short loc_180007B74
0x180007b6b  cmp     [rbx], r9d
0x180007b6e  jz      short loc_180007BEB
0x180007b70  mov     rbx, [rbx+8]
0x180007b74  test    rbx, rbx
0x180007b77  jnz     short loc_180007B6B
0x180007b79  test    rbx, rbx
0x180007b7c  jz      short loc_180007BD0
0x180007b7e  cmp     qword ptr [rbx], 0
0x180007b82  jz      short loc_180007BD0
0x180007b84  mov     [rsi], bpl
0x180007b87  mov     r9, r14; unsigned __int64
0x180007b8a  mov     r8, rsi; char *
0x180007b8d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180007b90  mov     rcx, rdi; struct wil::FailureInfo *
0x180007b93  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180007b98  test    al, al
0x180007b9a  jz      short loc_180007BA0
0x180007b9c  mov     [rdi+48h], rsi
0x180007ba0  mov     rbx, [rbx]
0x180007ba3  mov     al, [rbx+28h]
0x180007ba6  mov     byte ptr [rbx+28h], 1
0x180007baa  test    al, al
0x180007bac  jnz     short loc_180007BC7
0x180007bae  mov     rcx, [rbx+8]
0x180007bb2  mov     rax, [rcx]
0x180007bb5  mov     rdx, rdi
0x180007bb8  mov     rax, [rax]
0x180007bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bc0  or      bpl, al
0x180007bc3  mov     byte ptr [rbx+28h], 0
0x180007bc7  mov     rbx, [rbx+10h]
0x180007bcb  test    rbx, rbx
0x180007bce  jnz     short loc_180007BA3
0x180007bd0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180007bd7  test    rax, rax
0x180007bda  jz      short loc_180007BFC
0x180007bdc  test    bpl, bpl
0x180007bdf  jnz     short loc_180007BF1
0x180007be1  test    byte ptr [rdi+4], 2
0x180007be5  jnz     short loc_180007BF1
0x180007be7  xor     ecx, ecx
0x180007be9  jmp     short loc_180007BF3
0x180007beb  add     rbx, 10h
0x180007bef  jmp     short loc_180007B79
0x180007bf1  mov     cl, 1
0x180007bf3  mov     rdx, rdi
0x180007bf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bfb  nop
0x180007bfc  call    cs:__imp_GetCurrentThreadId
0x180007c02  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007c08  cmp     ecx, eax
0x180007c0a  jz      loc_180007D0C
0x180007c10  mov     ecx, 1
0x180007c15  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180007c1d  inc     ecx; this
0x180007c1f  cmp     ecx, 4
0x180007c22  jge     loc_180007D05
0x180007c28  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007c2e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180007c33  mov     rbx, rax
0x180007c36  test    rax, rax
0x180007c39  jz      loc_180007CFB
0x180007c3f  mov     esi, [rax+10h]
0x180007c42  mov     ebp, 50h ; 'P'
0x180007c47  cmp     qword ptr [rax+18h], 0
0x180007c4c  jnz     short loc_180007C83
0x180007c4e  test    esi, esi
0x180007c50  jz      short loc_180007C83
0x180007c52  mov     edx, 190h; dwBytes
0x180007c57  lea     ecx, [rbp-48h]; dwFlags
0x180007c5a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007c5f  mov     [rbx+18h], rax
0x180007c63  test    rax, rax
0x180007c66  jz      short loc_180007C83
0x180007c68  mov     dword ptr [rbx+20h], 5
0x180007c6f  lea     rcx, [rax+190h]
0x180007c76  jmp     short loc_180007C7E
0x180007c78  mov     [rax], bp
0x180007c7b  add     rax, rbp
0x180007c7e  cmp     rax, rcx
0x180007c81  jnz     short loc_180007C78
0x180007c83  mov     r9, [rbx+18h]
0x180007c87  test    r9, r9
0x180007c8a  jz      short loc_180007CFB
0x180007c8c  test    esi, esi
0x180007c8e  jz      short loc_180007CC1
0x180007c90  mov     rcx, r9
0x180007c93  movzx   eax, word ptr [rbx+20h]
0x180007c97  lea     rdx, [rax+rax*4]
0x180007c9b  shl     rdx, 4
0x180007c9f  add     rdx, r9
0x180007ca2  cmp     r9, rdx
0x180007ca5  jz      short loc_180007CC1
0x180007ca7  mov     r8d, [rbx+10h]
0x180007cab  cmp     [rcx+4], r8d
0x180007caf  jbe     short loc_180007CB9
0x180007cb1  mov     eax, [rdi+8]
0x180007cb4  cmp     [rcx+8], eax
0x180007cb7  jz      short loc_180007CFB
0x180007cb9  add     rcx, rbp
0x180007cbc  cmp     rcx, rdx
0x180007cbf  jnz     short loc_180007CAB
0x180007cc1  movzx   eax, word ptr [rbx+22h]
0x180007cc5  inc     eax
0x180007cc7  movzx   ecx, word ptr [rbx+20h]
0x180007ccb  xor     edx, edx
0x180007ccd  div     ecx
0x180007ccf  mov     [rbx+22h], dx
0x180007cd3  mov     rax, [rbx+8]
0x180007cd7  mov     r8d, 1
0x180007cdd  lock xadd [rax], r8d
0x180007ce2  inc     r8d; unsigned int
0x180007ce5  movzx   eax, dx
0x180007ce8  lea     rcx, [rax+rax*4]
0x180007cec  shl     rcx, 4
0x180007cf0  add     rcx, r9; this
0x180007cf3  mov     rdx, rdi; struct wil::FailureInfo *
0x180007cf6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180007cfb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007d05  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180007d0c  add     rsp, 20h
0x180007d10  pop     r14
0x180007d12  pop     rdi
0x180007d13  pop     rsi
0x180007d14  pop     rbp
0x180007d15  pop     rbx
0x180007d16  retn
```
