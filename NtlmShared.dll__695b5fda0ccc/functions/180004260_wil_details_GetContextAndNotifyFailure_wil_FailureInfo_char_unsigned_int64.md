# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004260`
- end: `0x180004466`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004260`
- `0x180004958`
- `0x180004a3c`
- `0x1800054b8`
- `0x180006be8`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000428a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000434b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000428a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000434b`

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
0x180004260  push    rbx
0x180004262  push    rbp
0x180004263  push    rsi
0x180004264  push    rdi
0x180004265  push    r14
0x180004267  sub     rsp, 20h
0x18000426b  mov     byte ptr [rdx], 0
0x18000426e  xor     bpl, bpl
0x180004271  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004278  mov     r14, r8
0x18000427b  mov     rsi, rdx
0x18000427e  mov     rdi, rcx
0x180004281  test    rbx, rbx
0x180004284  jz      loc_180004320
0x18000428a  call    cs:__imp_GetCurrentThreadId
0x180004290  mov     r8d, eax
0x180004293  mov     r9d, eax
0x180004296  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800042a0  shr     r8, 2
0x1800042a4  mul     r8
0x1800042a7  shr     rdx, 3
0x1800042ab  lea     rcx, [rdx+rdx*4]
0x1800042af  add     rcx, rcx
0x1800042b2  sub     r8, rcx
0x1800042b5  mov     rbx, [rbx+r8*8]
0x1800042b9  jmp     short loc_1800042C4
0x1800042bb  cmp     [rbx], r9d
0x1800042be  jz      short loc_18000433B
0x1800042c0  mov     rbx, [rbx+8]
0x1800042c4  test    rbx, rbx
0x1800042c7  jnz     short loc_1800042BB
0x1800042c9  test    rbx, rbx
0x1800042cc  jz      short loc_180004320
0x1800042ce  cmp     qword ptr [rbx], 0
0x1800042d2  jz      short loc_180004320
0x1800042d4  mov     [rsi], bpl
0x1800042d7  mov     r9, r14; unsigned __int64
0x1800042da  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800042dd  mov     r8, rsi; char *
0x1800042e0  mov     rcx, rdi; struct wil::FailureInfo *
0x1800042e3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800042e8  test    al, al
0x1800042ea  jz      short loc_1800042F0
0x1800042ec  mov     [rdi+48h], rsi
0x1800042f0  mov     rbx, [rbx]
0x1800042f3  mov     al, [rbx+28h]
0x1800042f6  mov     byte ptr [rbx+28h], 1
0x1800042fa  test    al, al
0x1800042fc  jnz     short loc_180004317
0x1800042fe  mov     rcx, [rbx+8]
0x180004302  mov     rdx, rdi
0x180004305  mov     rax, [rcx]
0x180004308  mov     rax, [rax]
0x18000430b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004310  or      bpl, al
0x180004313  mov     byte ptr [rbx+28h], 0
0x180004317  mov     rbx, [rbx+10h]
0x18000431b  test    rbx, rbx
0x18000431e  jnz     short loc_1800042F3
0x180004320  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004327  test    rax, rax
0x18000432a  jz      short loc_18000434B
0x18000432c  test    bpl, bpl
0x18000432f  jnz     short loc_180004341
0x180004331  test    byte ptr [rdi+4], 2
0x180004335  jnz     short loc_180004341
0x180004337  xor     ecx, ecx
0x180004339  jmp     short loc_180004343
0x18000433b  add     rbx, 10h
0x18000433f  jmp     short loc_1800042C9
0x180004341  mov     cl, 1
0x180004343  mov     rdx, rdi
0x180004346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000434b  call    cs:__imp_GetCurrentThreadId
0x180004351  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004357  cmp     ecx, eax
0x180004359  jz      loc_18000445B
0x18000435f  mov     ecx, 1
0x180004364  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000436c  inc     ecx; this
0x18000436e  cmp     ecx, 4
0x180004371  jge     loc_180004454
0x180004377  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000437d  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180004382  mov     rbx, rax
0x180004385  test    rax, rax
0x180004388  jz      loc_18000444A
0x18000438e  cmp     qword ptr [rax+18h], 0
0x180004393  mov     ebp, 50h ; 'P'
0x180004398  mov     esi, [rax+10h]
0x18000439b  jnz     short loc_1800043D2
0x18000439d  test    esi, esi
0x18000439f  jz      short loc_1800043D2
0x1800043a1  mov     edx, 190h; dwBytes
0x1800043a6  lea     ecx, [rbp-48h]; dwFlags
0x1800043a9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800043ae  mov     [rbx+18h], rax
0x1800043b2  test    rax, rax
0x1800043b5  jz      short loc_1800043D2
0x1800043b7  mov     dword ptr [rbx+20h], 5
0x1800043be  lea     rcx, [rax+190h]
0x1800043c5  jmp     short loc_1800043CD
0x1800043c7  mov     [rax], bp
0x1800043ca  add     rax, rbp
0x1800043cd  cmp     rax, rcx
0x1800043d0  jnz     short loc_1800043C7
0x1800043d2  mov     r9, [rbx+18h]
0x1800043d6  test    r9, r9
0x1800043d9  jz      short loc_18000444A
0x1800043db  test    esi, esi
0x1800043dd  jz      short loc_180004410
0x1800043df  movzx   eax, word ptr [rbx+20h]
0x1800043e3  mov     rcx, r9
0x1800043e6  lea     rdx, [rax+rax*4]
0x1800043ea  shl     rdx, 4
0x1800043ee  add     rdx, r9
0x1800043f1  cmp     r9, rdx
0x1800043f4  jz      short loc_180004410
0x1800043f6  mov     r8d, [rbx+10h]
0x1800043fa  cmp     [rcx+4], r8d
0x1800043fe  jbe     short loc_180004408
0x180004400  mov     eax, [rdi+8]
0x180004403  cmp     [rcx+8], eax
0x180004406  jz      short loc_18000444A
0x180004408  add     rcx, rbp
0x18000440b  cmp     rcx, rdx
0x18000440e  jnz     short loc_1800043FA
0x180004410  movzx   eax, word ptr [rbx+22h]
0x180004414  xor     edx, edx
0x180004416  movzx   ecx, word ptr [rbx+20h]
0x18000441a  inc     eax
0x18000441c  div     ecx
0x18000441e  mov     rax, [rbx+8]
0x180004422  mov     r8d, 1
0x180004428  mov     [rbx+22h], dx
0x18000442c  lock xadd [rax], r8d
0x180004431  movzx   eax, dx
0x180004434  inc     r8d; unsigned int
0x180004437  mov     rdx, rdi; struct wil::FailureInfo *
0x18000443a  lea     rcx, [rax+rax*4]
0x18000443e  shl     rcx, 4
0x180004442  add     rcx, r9; this
0x180004445  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000444a  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004454  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000445b  add     rsp, 20h
0x18000445f  pop     r14
0x180004461  pop     rdi
0x180004462  pop     rsi
0x180004463  pop     rbp
0x180004464  pop     rbx
0x180004465  retn
```
