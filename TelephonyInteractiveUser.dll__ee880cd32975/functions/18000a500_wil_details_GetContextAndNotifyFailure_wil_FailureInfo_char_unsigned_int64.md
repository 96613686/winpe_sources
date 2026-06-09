# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000a500`
- end: `0x18000a706`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000a500`
- `0x18000b7e4`
- `0x18000b8c8`
- `0x18000d114`
- `0x18000ef78`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a52a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a5eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a52a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a5eb`

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
0x18000a500  push    rbx
0x18000a502  push    rbp
0x18000a503  push    rsi
0x18000a504  push    rdi
0x18000a505  push    r14
0x18000a507  sub     rsp, 20h
0x18000a50b  mov     byte ptr [rdx], 0
0x18000a50e  xor     bpl, bpl
0x18000a511  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000a518  mov     r14, r8
0x18000a51b  mov     rsi, rdx
0x18000a51e  mov     rdi, rcx
0x18000a521  test    rbx, rbx
0x18000a524  jz      loc_18000A5C0
0x18000a52a  call    cs:__imp_GetCurrentThreadId
0x18000a530  mov     r8d, eax
0x18000a533  mov     r9d, eax
0x18000a536  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000a540  shr     r8, 2
0x18000a544  mul     r8
0x18000a547  shr     rdx, 3
0x18000a54b  lea     rcx, [rdx+rdx*4]
0x18000a54f  add     rcx, rcx
0x18000a552  sub     r8, rcx
0x18000a555  mov     rbx, [rbx+r8*8]
0x18000a559  jmp     short loc_18000A564
0x18000a55b  cmp     [rbx], r9d
0x18000a55e  jz      short loc_18000A5DB
0x18000a560  mov     rbx, [rbx+8]
0x18000a564  test    rbx, rbx
0x18000a567  jnz     short loc_18000A55B
0x18000a569  test    rbx, rbx
0x18000a56c  jz      short loc_18000A5C0
0x18000a56e  cmp     qword ptr [rbx], 0
0x18000a572  jz      short loc_18000A5C0
0x18000a574  mov     [rsi], bpl
0x18000a577  mov     r9, r14; unsigned __int64
0x18000a57a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000a57d  mov     r8, rsi; char *
0x18000a580  mov     rcx, rdi; struct wil::FailureInfo *
0x18000a583  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000a588  test    al, al
0x18000a58a  jz      short loc_18000A590
0x18000a58c  mov     [rdi+48h], rsi
0x18000a590  mov     rbx, [rbx]
0x18000a593  mov     al, [rbx+28h]
0x18000a596  mov     byte ptr [rbx+28h], 1
0x18000a59a  test    al, al
0x18000a59c  jnz     short loc_18000A5B7
0x18000a59e  mov     rcx, [rbx+8]
0x18000a5a2  mov     rdx, rdi
0x18000a5a5  mov     rax, [rcx]
0x18000a5a8  mov     rax, [rax]
0x18000a5ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5b0  or      bpl, al
0x18000a5b3  mov     byte ptr [rbx+28h], 0
0x18000a5b7  mov     rbx, [rbx+10h]
0x18000a5bb  test    rbx, rbx
0x18000a5be  jnz     short loc_18000A593
0x18000a5c0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000a5c7  test    rax, rax
0x18000a5ca  jz      short loc_18000A5EB
0x18000a5cc  test    bpl, bpl
0x18000a5cf  jnz     short loc_18000A5E1
0x18000a5d1  test    byte ptr [rdi+4], 2
0x18000a5d5  jnz     short loc_18000A5E1
0x18000a5d7  xor     ecx, ecx
0x18000a5d9  jmp     short loc_18000A5E3
0x18000a5db  add     rbx, 10h
0x18000a5df  jmp     short loc_18000A569
0x18000a5e1  mov     cl, 1
0x18000a5e3  mov     rdx, rdi
0x18000a5e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5eb  call    cs:__imp_GetCurrentThreadId
0x18000a5f1  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000a5f7  cmp     ecx, eax
0x18000a5f9  jz      loc_18000A6FB
0x18000a5ff  mov     ecx, 1
0x18000a604  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000a60c  inc     ecx; this
0x18000a60e  cmp     ecx, 4
0x18000a611  jge     loc_18000A6F4
0x18000a617  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000a61d  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000a622  mov     rbx, rax
0x18000a625  test    rax, rax
0x18000a628  jz      loc_18000A6EA
0x18000a62e  cmp     qword ptr [rax+18h], 0
0x18000a633  mov     ebp, 50h ; 'P'
0x18000a638  mov     esi, [rax+10h]
0x18000a63b  jnz     short loc_18000A672
0x18000a63d  test    esi, esi
0x18000a63f  jz      short loc_18000A672
0x18000a641  mov     edx, 190h; dwBytes
0x18000a646  lea     ecx, [rbp-48h]; dwFlags
0x18000a649  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a64e  mov     [rbx+18h], rax
0x18000a652  test    rax, rax
0x18000a655  jz      short loc_18000A672
0x18000a657  mov     dword ptr [rbx+20h], 5
0x18000a65e  lea     rcx, [rax+190h]
0x18000a665  jmp     short loc_18000A66D
0x18000a667  mov     [rax], bp
0x18000a66a  add     rax, rbp
0x18000a66d  cmp     rax, rcx
0x18000a670  jnz     short loc_18000A667
0x18000a672  mov     r9, [rbx+18h]
0x18000a676  test    r9, r9
0x18000a679  jz      short loc_18000A6EA
0x18000a67b  test    esi, esi
0x18000a67d  jz      short loc_18000A6B0
0x18000a67f  movzx   eax, word ptr [rbx+20h]
0x18000a683  mov     rcx, r9
0x18000a686  lea     rdx, [rax+rax*4]
0x18000a68a  shl     rdx, 4
0x18000a68e  add     rdx, r9
0x18000a691  cmp     r9, rdx
0x18000a694  jz      short loc_18000A6B0
0x18000a696  mov     r8d, [rbx+10h]
0x18000a69a  cmp     [rcx+4], r8d
0x18000a69e  jbe     short loc_18000A6A8
0x18000a6a0  mov     eax, [rdi+8]
0x18000a6a3  cmp     [rcx+8], eax
0x18000a6a6  jz      short loc_18000A6EA
0x18000a6a8  add     rcx, rbp
0x18000a6ab  cmp     rcx, rdx
0x18000a6ae  jnz     short loc_18000A69A
0x18000a6b0  movzx   eax, word ptr [rbx+22h]
0x18000a6b4  xor     edx, edx
0x18000a6b6  movzx   ecx, word ptr [rbx+20h]
0x18000a6ba  inc     eax
0x18000a6bc  div     ecx
0x18000a6be  mov     rax, [rbx+8]
0x18000a6c2  mov     r8d, 1
0x18000a6c8  mov     [rbx+22h], dx
0x18000a6cc  lock xadd [rax], r8d
0x18000a6d1  movzx   eax, dx
0x18000a6d4  inc     r8d; unsigned int
0x18000a6d7  mov     rdx, rdi; struct wil::FailureInfo *
0x18000a6da  lea     rcx, [rax+rax*4]
0x18000a6de  shl     rcx, 4
0x18000a6e2  add     rcx, r9; this
0x18000a6e5  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000a6ea  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000a6f4  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000a6fb  add     rsp, 20h
0x18000a6ff  pop     r14
0x18000a701  pop     rdi
0x18000a702  pop     rsi
0x18000a703  pop     rbp
0x18000a704  pop     rbx
0x18000a705  retn
```
