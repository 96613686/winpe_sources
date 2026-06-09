# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800059e0`
- end: `0x180005be7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800059e0`
- `0x1800060dc`
- `0x1800061c0`
- `0x180006c38`
- `0x1800084a4`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005a0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005acc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005a0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005acc`

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
0x1800059e0  push    rbx
0x1800059e2  push    rbp
0x1800059e3  push    rsi
0x1800059e4  push    rdi
0x1800059e5  push    r14
0x1800059e7  sub     rsp, 20h
0x1800059eb  mov     r14, r8
0x1800059ee  mov     rsi, rdx
0x1800059f1  mov     rdi, rcx
0x1800059f4  mov     byte ptr [rdx], 0
0x1800059f7  xor     bpl, bpl
0x1800059fa  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005a01  test    rbx, rbx
0x180005a04  jz      loc_180005AA0
0x180005a0a  call    cs:__imp_GetCurrentThreadId
0x180005a10  mov     r9d, eax
0x180005a13  mov     r8d, eax
0x180005a16  shr     r8, 2
0x180005a1a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005a24  mul     r8
0x180005a27  shr     rdx, 3
0x180005a2b  lea     rcx, [rdx+rdx*4]
0x180005a2f  add     rcx, rcx
0x180005a32  sub     r8, rcx
0x180005a35  mov     rbx, [rbx+r8*8]
0x180005a39  jmp     short loc_180005A44
0x180005a3b  cmp     [rbx], r9d
0x180005a3e  jz      short loc_180005ABB
0x180005a40  mov     rbx, [rbx+8]
0x180005a44  test    rbx, rbx
0x180005a47  jnz     short loc_180005A3B
0x180005a49  test    rbx, rbx
0x180005a4c  jz      short loc_180005AA0
0x180005a4e  cmp     qword ptr [rbx], 0
0x180005a52  jz      short loc_180005AA0
0x180005a54  mov     [rsi], bpl
0x180005a57  mov     r9, r14; unsigned __int64
0x180005a5a  mov     r8, rsi; char *
0x180005a5d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180005a60  mov     rcx, rdi; struct wil::FailureInfo *
0x180005a63  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005a68  test    al, al
0x180005a6a  jz      short loc_180005A70
0x180005a6c  mov     [rdi+48h], rsi
0x180005a70  mov     rbx, [rbx]
0x180005a73  mov     al, [rbx+28h]
0x180005a76  mov     byte ptr [rbx+28h], 1
0x180005a7a  test    al, al
0x180005a7c  jnz     short loc_180005A97
0x180005a7e  mov     rcx, [rbx+8]
0x180005a82  mov     rax, [rcx]
0x180005a85  mov     rdx, rdi
0x180005a88  mov     rax, [rax]
0x180005a8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a90  or      bpl, al
0x180005a93  mov     byte ptr [rbx+28h], 0
0x180005a97  mov     rbx, [rbx+10h]
0x180005a9b  test    rbx, rbx
0x180005a9e  jnz     short loc_180005A73
0x180005aa0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180005aa7  test    rax, rax
0x180005aaa  jz      short loc_180005ACC
0x180005aac  test    bpl, bpl
0x180005aaf  jnz     short loc_180005AC1
0x180005ab1  test    byte ptr [rdi+4], 2
0x180005ab5  jnz     short loc_180005AC1
0x180005ab7  xor     ecx, ecx
0x180005ab9  jmp     short loc_180005AC3
0x180005abb  add     rbx, 10h
0x180005abf  jmp     short loc_180005A49
0x180005ac1  mov     cl, 1
0x180005ac3  mov     rdx, rdi
0x180005ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005acb  nop
0x180005acc  call    cs:__imp_GetCurrentThreadId
0x180005ad2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005ad8  cmp     ecx, eax
0x180005ada  jz      loc_180005BDC
0x180005ae0  mov     ecx, 1
0x180005ae5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180005aed  inc     ecx; this
0x180005aef  cmp     ecx, 4
0x180005af2  jge     loc_180005BD5
0x180005af8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005afe  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180005b03  mov     rbx, rax
0x180005b06  test    rax, rax
0x180005b09  jz      loc_180005BCB
0x180005b0f  mov     esi, [rax+10h]
0x180005b12  mov     ebp, 50h ; 'P'
0x180005b17  cmp     qword ptr [rax+18h], 0
0x180005b1c  jnz     short loc_180005B53
0x180005b1e  test    esi, esi
0x180005b20  jz      short loc_180005B53
0x180005b22  mov     edx, 190h; dwBytes
0x180005b27  lea     ecx, [rbp-48h]; dwFlags
0x180005b2a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005b2f  mov     [rbx+18h], rax
0x180005b33  test    rax, rax
0x180005b36  jz      short loc_180005B53
0x180005b38  mov     dword ptr [rbx+20h], 5
0x180005b3f  lea     rcx, [rax+190h]
0x180005b46  jmp     short loc_180005B4E
0x180005b48  mov     [rax], bp
0x180005b4b  add     rax, rbp
0x180005b4e  cmp     rax, rcx
0x180005b51  jnz     short loc_180005B48
0x180005b53  mov     r9, [rbx+18h]
0x180005b57  test    r9, r9
0x180005b5a  jz      short loc_180005BCB
0x180005b5c  test    esi, esi
0x180005b5e  jz      short loc_180005B91
0x180005b60  mov     rcx, r9
0x180005b63  movzx   eax, word ptr [rbx+20h]
0x180005b67  lea     rdx, [rax+rax*4]
0x180005b6b  shl     rdx, 4
0x180005b6f  add     rdx, r9
0x180005b72  cmp     r9, rdx
0x180005b75  jz      short loc_180005B91
0x180005b77  mov     r8d, [rbx+10h]
0x180005b7b  cmp     [rcx+4], r8d
0x180005b7f  jbe     short loc_180005B89
0x180005b81  mov     eax, [rdi+8]
0x180005b84  cmp     [rcx+8], eax
0x180005b87  jz      short loc_180005BCB
0x180005b89  add     rcx, rbp
0x180005b8c  cmp     rcx, rdx
0x180005b8f  jnz     short loc_180005B7B
0x180005b91  movzx   eax, word ptr [rbx+22h]
0x180005b95  inc     eax
0x180005b97  movzx   ecx, word ptr [rbx+20h]
0x180005b9b  xor     edx, edx
0x180005b9d  div     ecx
0x180005b9f  mov     [rbx+22h], dx
0x180005ba3  mov     rax, [rbx+8]
0x180005ba7  mov     r8d, 1
0x180005bad  lock xadd [rax], r8d
0x180005bb2  inc     r8d; unsigned int
0x180005bb5  movzx   eax, dx
0x180005bb8  lea     rcx, [rax+rax*4]
0x180005bbc  shl     rcx, 4
0x180005bc0  add     rcx, r9; this
0x180005bc3  mov     rdx, rdi; struct wil::FailureInfo *
0x180005bc6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180005bcb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005bd5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180005bdc  add     rsp, 20h
0x180005be0  pop     r14
0x180005be2  pop     rdi
0x180005be3  pop     rsi
0x180005be4  pop     rbp
0x180005be5  pop     rbx
0x180005be6  retn
```
