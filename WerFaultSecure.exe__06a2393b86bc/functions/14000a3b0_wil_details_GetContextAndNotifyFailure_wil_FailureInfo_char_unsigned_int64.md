# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x14000a3b0`
- end: `0x14000a5b7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14000a3b0`
- `0x14000a680`
- `0x14000a764`
- `0x14000ac10`
- `0x14000c1ac`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a3da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a49c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a3da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a49c`

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
0x14000a3b0  push    rbx
0x14000a3b2  push    rbp
0x14000a3b3  push    rsi
0x14000a3b4  push    rdi
0x14000a3b5  push    r14
0x14000a3b7  sub     rsp, 20h
0x14000a3bb  mov     r14, r8
0x14000a3be  mov     rsi, rdx
0x14000a3c1  mov     rdi, rcx
0x14000a3c4  mov     byte ptr [rdx], 0
0x14000a3c7  xor     bpl, bpl
0x14000a3ca  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14000a3d1  test    rbx, rbx
0x14000a3d4  jz      loc_14000A470
0x14000a3da  call    cs:__imp_GetCurrentThreadId
0x14000a3e0  mov     r9d, eax
0x14000a3e3  mov     r8d, eax
0x14000a3e6  shr     r8, 2
0x14000a3ea  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000a3f4  mul     r8
0x14000a3f7  shr     rdx, 3
0x14000a3fb  lea     rcx, [rdx+rdx*4]
0x14000a3ff  add     rcx, rcx
0x14000a402  sub     r8, rcx
0x14000a405  mov     rbx, [rbx+r8*8]
0x14000a409  jmp     short loc_14000A414
0x14000a40b  cmp     [rbx], r9d
0x14000a40e  jz      short loc_14000A48B
0x14000a410  mov     rbx, [rbx+8]
0x14000a414  test    rbx, rbx
0x14000a417  jnz     short loc_14000A40B
0x14000a419  test    rbx, rbx
0x14000a41c  jz      short loc_14000A470
0x14000a41e  cmp     qword ptr [rbx], 0
0x14000a422  jz      short loc_14000A470
0x14000a424  mov     [rsi], bpl
0x14000a427  mov     r9, r14; unsigned __int64
0x14000a42a  mov     r8, rsi; char *
0x14000a42d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x14000a430  mov     rcx, rdi; struct wil::FailureInfo *
0x14000a433  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x14000a438  test    al, al
0x14000a43a  jz      short loc_14000A440
0x14000a43c  mov     [rdi+48h], rsi
0x14000a440  mov     rbx, [rbx]
0x14000a443  mov     al, [rbx+28h]
0x14000a446  mov     byte ptr [rbx+28h], 1
0x14000a44a  test    al, al
0x14000a44c  jnz     short loc_14000A467
0x14000a44e  mov     rcx, [rbx+8]
0x14000a452  mov     rax, [rcx]
0x14000a455  mov     rdx, rdi
0x14000a458  mov     rax, [rax]
0x14000a45b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a460  or      bpl, al
0x14000a463  mov     byte ptr [rbx+28h], 0
0x14000a467  mov     rbx, [rbx+10h]
0x14000a46b  test    rbx, rbx
0x14000a46e  jnz     short loc_14000A443
0x14000a470  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x14000a477  test    rax, rax
0x14000a47a  jz      short loc_14000A49C
0x14000a47c  test    bpl, bpl
0x14000a47f  jnz     short loc_14000A491
0x14000a481  test    byte ptr [rdi+4], 2
0x14000a485  jnz     short loc_14000A491
0x14000a487  xor     ecx, ecx
0x14000a489  jmp     short loc_14000A493
0x14000a48b  add     rbx, 10h
0x14000a48f  jmp     short loc_14000A419
0x14000a491  mov     cl, 1
0x14000a493  mov     rdx, rdi
0x14000a496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a49b  nop
0x14000a49c  call    cs:__imp_GetCurrentThreadId
0x14000a4a2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14000a4a8  cmp     ecx, eax
0x14000a4aa  jz      loc_14000A5AC
0x14000a4b0  mov     ecx, 1
0x14000a4b5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000a4bd  inc     ecx; this
0x14000a4bf  cmp     ecx, 4
0x14000a4c2  jge     loc_14000A5A5
0x14000a4c8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14000a4ce  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x14000a4d3  mov     rbx, rax
0x14000a4d6  test    rax, rax
0x14000a4d9  jz      loc_14000A59B
0x14000a4df  mov     esi, [rax+10h]
0x14000a4e2  mov     ebp, 50h ; 'P'
0x14000a4e7  cmp     qword ptr [rax+18h], 0
0x14000a4ec  jnz     short loc_14000A523
0x14000a4ee  test    esi, esi
0x14000a4f0  jz      short loc_14000A523
0x14000a4f2  mov     edx, 190h; dwBytes
0x14000a4f7  lea     ecx, [rbp-48h]; dwFlags
0x14000a4fa  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000a4ff  mov     [rbx+18h], rax
0x14000a503  test    rax, rax
0x14000a506  jz      short loc_14000A523
0x14000a508  mov     dword ptr [rbx+20h], 5
0x14000a50f  lea     rcx, [rax+190h]
0x14000a516  jmp     short loc_14000A51E
0x14000a518  mov     [rax], bp
0x14000a51b  add     rax, rbp
0x14000a51e  cmp     rax, rcx
0x14000a521  jnz     short loc_14000A518
0x14000a523  mov     r9, [rbx+18h]
0x14000a527  test    r9, r9
0x14000a52a  jz      short loc_14000A59B
0x14000a52c  test    esi, esi
0x14000a52e  jz      short loc_14000A561
0x14000a530  mov     rcx, r9
0x14000a533  movzx   eax, word ptr [rbx+20h]
0x14000a537  lea     rdx, [rax+rax*4]
0x14000a53b  shl     rdx, 4
0x14000a53f  add     rdx, r9
0x14000a542  cmp     r9, rdx
0x14000a545  jz      short loc_14000A561
0x14000a547  mov     r8d, [rbx+10h]
0x14000a54b  cmp     [rcx+4], r8d
0x14000a54f  jbe     short loc_14000A559
0x14000a551  mov     eax, [rdi+8]
0x14000a554  cmp     [rcx+8], eax
0x14000a557  jz      short loc_14000A59B
0x14000a559  add     rcx, rbp
0x14000a55c  cmp     rcx, rdx
0x14000a55f  jnz     short loc_14000A54B
0x14000a561  movzx   eax, word ptr [rbx+22h]
0x14000a565  inc     eax
0x14000a567  movzx   ecx, word ptr [rbx+20h]
0x14000a56b  xor     edx, edx
0x14000a56d  div     ecx
0x14000a56f  mov     [rbx+22h], dx
0x14000a573  mov     rax, [rbx+8]
0x14000a577  mov     r8d, 1
0x14000a57d  lock xadd [rax], r8d
0x14000a582  inc     r8d; unsigned int
0x14000a585  movzx   eax, dx
0x14000a588  lea     rcx, [rax+rax*4]
0x14000a58c  shl     rcx, 4
0x14000a590  add     rcx, r9; this
0x14000a593  mov     rdx, rdi; struct wil::FailureInfo *
0x14000a596  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x14000a59b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14000a5a5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000a5ac  add     rsp, 20h
0x14000a5b0  pop     r14
0x14000a5b2  pop     rdi
0x14000a5b3  pop     rsi
0x14000a5b4  pop     rbp
0x14000a5b5  pop     rbx
0x14000a5b6  retn
```
