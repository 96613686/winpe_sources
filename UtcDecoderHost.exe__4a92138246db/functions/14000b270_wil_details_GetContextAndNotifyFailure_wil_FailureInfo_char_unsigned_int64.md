# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x14000b270`
- end: `0x14000b477`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14000b270`
- `0x14000b96c`
- `0x14000ba50`
- `0x14000bfc8`
- `0x14000c524`
- `0x140018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000b29a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000b35c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000b29a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000b35c`

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
0x14000b270  push    rbx
0x14000b272  push    rbp
0x14000b273  push    rsi
0x14000b274  push    rdi
0x14000b275  push    r14
0x14000b277  sub     rsp, 20h
0x14000b27b  mov     r14, r8
0x14000b27e  mov     rsi, rdx
0x14000b281  mov     rdi, rcx
0x14000b284  mov     byte ptr [rdx], 0
0x14000b287  xor     bpl, bpl
0x14000b28a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14000b291  test    rbx, rbx
0x14000b294  jz      loc_14000B330
0x14000b29a  call    cs:__imp_GetCurrentThreadId
0x14000b2a0  mov     r9d, eax
0x14000b2a3  mov     r8d, eax
0x14000b2a6  shr     r8, 2
0x14000b2aa  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000b2b4  mul     r8
0x14000b2b7  shr     rdx, 3
0x14000b2bb  lea     rcx, [rdx+rdx*4]
0x14000b2bf  add     rcx, rcx
0x14000b2c2  sub     r8, rcx
0x14000b2c5  mov     rbx, [rbx+r8*8]
0x14000b2c9  jmp     short loc_14000B2D4
0x14000b2cb  cmp     [rbx], r9d
0x14000b2ce  jz      short loc_14000B34B
0x14000b2d0  mov     rbx, [rbx+8]
0x14000b2d4  test    rbx, rbx
0x14000b2d7  jnz     short loc_14000B2CB
0x14000b2d9  test    rbx, rbx
0x14000b2dc  jz      short loc_14000B330
0x14000b2de  cmp     qword ptr [rbx], 0
0x14000b2e2  jz      short loc_14000B330
0x14000b2e4  mov     [rsi], bpl
0x14000b2e7  mov     r9, r14; unsigned __int64
0x14000b2ea  mov     r8, rsi; char *
0x14000b2ed  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x14000b2f0  mov     rcx, rdi; struct wil::FailureInfo *
0x14000b2f3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x14000b2f8  test    al, al
0x14000b2fa  jz      short loc_14000B300
0x14000b2fc  mov     [rdi+48h], rsi
0x14000b300  mov     rbx, [rbx]
0x14000b303  mov     al, [rbx+28h]
0x14000b306  mov     byte ptr [rbx+28h], 1
0x14000b30a  test    al, al
0x14000b30c  jnz     short loc_14000B327
0x14000b30e  mov     rcx, [rbx+8]
0x14000b312  mov     rax, [rcx]
0x14000b315  mov     rdx, rdi
0x14000b318  mov     rax, [rax]
0x14000b31b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b320  or      bpl, al
0x14000b323  mov     byte ptr [rbx+28h], 0
0x14000b327  mov     rbx, [rbx+10h]
0x14000b32b  test    rbx, rbx
0x14000b32e  jnz     short loc_14000B303
0x14000b330  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x14000b337  test    rax, rax
0x14000b33a  jz      short loc_14000B35C
0x14000b33c  test    bpl, bpl
0x14000b33f  jnz     short loc_14000B351
0x14000b341  test    byte ptr [rdi+4], 2
0x14000b345  jnz     short loc_14000B351
0x14000b347  xor     ecx, ecx
0x14000b349  jmp     short loc_14000B353
0x14000b34b  add     rbx, 10h
0x14000b34f  jmp     short loc_14000B2D9
0x14000b351  mov     cl, 1
0x14000b353  mov     rdx, rdi
0x14000b356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b35b  nop
0x14000b35c  call    cs:__imp_GetCurrentThreadId
0x14000b362  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14000b368  cmp     ecx, eax
0x14000b36a  jz      loc_14000B46C
0x14000b370  mov     ecx, 1
0x14000b375  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000b37d  inc     ecx; this
0x14000b37f  cmp     ecx, 4
0x14000b382  jge     loc_14000B465
0x14000b388  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14000b38e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x14000b393  mov     rbx, rax
0x14000b396  test    rax, rax
0x14000b399  jz      loc_14000B45B
0x14000b39f  mov     esi, [rax+10h]
0x14000b3a2  mov     ebp, 50h ; 'P'
0x14000b3a7  cmp     qword ptr [rax+18h], 0
0x14000b3ac  jnz     short loc_14000B3E3
0x14000b3ae  test    esi, esi
0x14000b3b0  jz      short loc_14000B3E3
0x14000b3b2  mov     edx, 190h; dwBytes
0x14000b3b7  lea     ecx, [rbp-48h]; dwFlags
0x14000b3ba  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000b3bf  mov     [rbx+18h], rax
0x14000b3c3  test    rax, rax
0x14000b3c6  jz      short loc_14000B3E3
0x14000b3c8  mov     dword ptr [rbx+20h], 5
0x14000b3cf  lea     rcx, [rax+190h]
0x14000b3d6  jmp     short loc_14000B3DE
0x14000b3d8  mov     [rax], bp
0x14000b3db  add     rax, rbp
0x14000b3de  cmp     rax, rcx
0x14000b3e1  jnz     short loc_14000B3D8
0x14000b3e3  mov     r9, [rbx+18h]
0x14000b3e7  test    r9, r9
0x14000b3ea  jz      short loc_14000B45B
0x14000b3ec  test    esi, esi
0x14000b3ee  jz      short loc_14000B421
0x14000b3f0  mov     rcx, r9
0x14000b3f3  movzx   eax, word ptr [rbx+20h]
0x14000b3f7  lea     rdx, [rax+rax*4]
0x14000b3fb  shl     rdx, 4
0x14000b3ff  add     rdx, r9
0x14000b402  cmp     r9, rdx
0x14000b405  jz      short loc_14000B421
0x14000b407  mov     r8d, [rbx+10h]
0x14000b40b  cmp     [rcx+4], r8d
0x14000b40f  jbe     short loc_14000B419
0x14000b411  mov     eax, [rdi+8]
0x14000b414  cmp     [rcx+8], eax
0x14000b417  jz      short loc_14000B45B
0x14000b419  add     rcx, rbp
0x14000b41c  cmp     rcx, rdx
0x14000b41f  jnz     short loc_14000B40B
0x14000b421  movzx   eax, word ptr [rbx+22h]
0x14000b425  inc     eax
0x14000b427  movzx   ecx, word ptr [rbx+20h]
0x14000b42b  xor     edx, edx
0x14000b42d  div     ecx
0x14000b42f  mov     [rbx+22h], dx
0x14000b433  mov     rax, [rbx+8]
0x14000b437  mov     r8d, 1
0x14000b43d  lock xadd [rax], r8d
0x14000b442  inc     r8d; unsigned int
0x14000b445  movzx   eax, dx
0x14000b448  lea     rcx, [rax+rax*4]
0x14000b44c  shl     rcx, 4
0x14000b450  add     rcx, r9; this
0x14000b453  mov     rdx, rdi; struct wil::FailureInfo *
0x14000b456  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x14000b45b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14000b465  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000b46c  add     rsp, 20h
0x14000b470  pop     r14
0x14000b472  pop     rdi
0x14000b473  pop     rsi
0x14000b474  pop     rbp
0x14000b475  pop     rbx
0x14000b476  retn
```
