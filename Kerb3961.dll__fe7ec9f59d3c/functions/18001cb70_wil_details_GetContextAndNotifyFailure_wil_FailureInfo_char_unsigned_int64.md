# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18001cb70`
- end: `0x18001cd76`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180014c4c`
- `0x18001cb70`
- `0x18001cd7c`
- `0x18001ce60`
- `0x18001d044`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001cb9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001cc5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001cb9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001cc5b`

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
0x18001cb70  push    rbx
0x18001cb72  push    rbp
0x18001cb73  push    rsi
0x18001cb74  push    rdi
0x18001cb75  push    r14
0x18001cb77  sub     rsp, 20h
0x18001cb7b  mov     byte ptr [rdx], 0
0x18001cb7e  xor     bpl, bpl
0x18001cb81  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001cb88  mov     r14, r8
0x18001cb8b  mov     rsi, rdx
0x18001cb8e  mov     rdi, rcx
0x18001cb91  test    rbx, rbx
0x18001cb94  jz      loc_18001CC30
0x18001cb9a  call    cs:__imp_GetCurrentThreadId
0x18001cba0  mov     r8d, eax
0x18001cba3  mov     r9d, eax
0x18001cba6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001cbb0  shr     r8, 2
0x18001cbb4  mul     r8
0x18001cbb7  shr     rdx, 3
0x18001cbbb  lea     rcx, [rdx+rdx*4]
0x18001cbbf  add     rcx, rcx
0x18001cbc2  sub     r8, rcx
0x18001cbc5  mov     rbx, [rbx+r8*8]
0x18001cbc9  jmp     short loc_18001CBD4
0x18001cbcb  cmp     [rbx], r9d
0x18001cbce  jz      short loc_18001CC4B
0x18001cbd0  mov     rbx, [rbx+8]
0x18001cbd4  test    rbx, rbx
0x18001cbd7  jnz     short loc_18001CBCB
0x18001cbd9  test    rbx, rbx
0x18001cbdc  jz      short loc_18001CC30
0x18001cbde  cmp     qword ptr [rbx], 0
0x18001cbe2  jz      short loc_18001CC30
0x18001cbe4  mov     [rsi], bpl
0x18001cbe7  mov     r9, r14; unsigned __int64
0x18001cbea  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18001cbed  mov     r8, rsi; char *
0x18001cbf0  mov     rcx, rdi; struct wil::FailureInfo *
0x18001cbf3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18001cbf8  test    al, al
0x18001cbfa  jz      short loc_18001CC00
0x18001cbfc  mov     [rdi+48h], rsi
0x18001cc00  mov     rbx, [rbx]
0x18001cc03  mov     al, [rbx+28h]
0x18001cc06  mov     byte ptr [rbx+28h], 1
0x18001cc0a  test    al, al
0x18001cc0c  jnz     short loc_18001CC27
0x18001cc0e  mov     rcx, [rbx+8]
0x18001cc12  mov     rdx, rdi
0x18001cc15  mov     rax, [rcx]
0x18001cc18  mov     rax, [rax]
0x18001cc1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc20  or      bpl, al
0x18001cc23  mov     byte ptr [rbx+28h], 0
0x18001cc27  mov     rbx, [rbx+10h]
0x18001cc2b  test    rbx, rbx
0x18001cc2e  jnz     short loc_18001CC03
0x18001cc30  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18001cc37  test    rax, rax
0x18001cc3a  jz      short loc_18001CC5B
0x18001cc3c  test    bpl, bpl
0x18001cc3f  jnz     short loc_18001CC51
0x18001cc41  test    byte ptr [rdi+4], 2
0x18001cc45  jnz     short loc_18001CC51
0x18001cc47  xor     ecx, ecx
0x18001cc49  jmp     short loc_18001CC53
0x18001cc4b  add     rbx, 10h
0x18001cc4f  jmp     short loc_18001CBD9
0x18001cc51  mov     cl, 1
0x18001cc53  mov     rdx, rdi
0x18001cc56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc5b  call    cs:__imp_GetCurrentThreadId
0x18001cc61  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18001cc67  cmp     ecx, eax
0x18001cc69  jz      loc_18001CD6B
0x18001cc6f  mov     ecx, 1
0x18001cc74  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18001cc7c  inc     ecx; this
0x18001cc7e  cmp     ecx, 4
0x18001cc81  jge     loc_18001CD64
0x18001cc87  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18001cc8d  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18001cc92  mov     rbx, rax
0x18001cc95  test    rax, rax
0x18001cc98  jz      loc_18001CD5A
0x18001cc9e  cmp     qword ptr [rax+18h], 0
0x18001cca3  mov     ebp, 50h ; 'P'
0x18001cca8  mov     esi, [rax+10h]
0x18001ccab  jnz     short loc_18001CCE2
0x18001ccad  test    esi, esi
0x18001ccaf  jz      short loc_18001CCE2
0x18001ccb1  mov     edx, 190h; dwBytes
0x18001ccb6  lea     ecx, [rbp-48h]; dwFlags
0x18001ccb9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001ccbe  mov     [rbx+18h], rax
0x18001ccc2  test    rax, rax
0x18001ccc5  jz      short loc_18001CCE2
0x18001ccc7  mov     dword ptr [rbx+20h], 5
0x18001ccce  lea     rcx, [rax+190h]
0x18001ccd5  jmp     short loc_18001CCDD
0x18001ccd7  mov     [rax], bp
0x18001ccda  add     rax, rbp
0x18001ccdd  cmp     rax, rcx
0x18001cce0  jnz     short loc_18001CCD7
0x18001cce2  mov     r9, [rbx+18h]
0x18001cce6  test    r9, r9
0x18001cce9  jz      short loc_18001CD5A
0x18001cceb  test    esi, esi
0x18001cced  jz      short loc_18001CD20
0x18001ccef  movzx   eax, word ptr [rbx+20h]
0x18001ccf3  mov     rcx, r9
0x18001ccf6  lea     rdx, [rax+rax*4]
0x18001ccfa  shl     rdx, 4
0x18001ccfe  add     rdx, r9
0x18001cd01  cmp     r9, rdx
0x18001cd04  jz      short loc_18001CD20
0x18001cd06  mov     r8d, [rbx+10h]
0x18001cd0a  cmp     [rcx+4], r8d
0x18001cd0e  jbe     short loc_18001CD18
0x18001cd10  mov     eax, [rdi+8]
0x18001cd13  cmp     [rcx+8], eax
0x18001cd16  jz      short loc_18001CD5A
0x18001cd18  add     rcx, rbp
0x18001cd1b  cmp     rcx, rdx
0x18001cd1e  jnz     short loc_18001CD0A
0x18001cd20  movzx   eax, word ptr [rbx+22h]
0x18001cd24  xor     edx, edx
0x18001cd26  movzx   ecx, word ptr [rbx+20h]
0x18001cd2a  inc     eax
0x18001cd2c  div     ecx
0x18001cd2e  mov     rax, [rbx+8]
0x18001cd32  mov     r8d, 1
0x18001cd38  mov     [rbx+22h], dx
0x18001cd3c  lock xadd [rax], r8d
0x18001cd41  movzx   eax, dx
0x18001cd44  inc     r8d; unsigned int
0x18001cd47  mov     rdx, rdi; struct wil::FailureInfo *
0x18001cd4a  lea     rcx, [rax+rax*4]
0x18001cd4e  shl     rcx, 4
0x18001cd52  add     rcx, r9; this
0x18001cd55  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18001cd5a  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18001cd64  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18001cd6b  add     rsp, 20h
0x18001cd6f  pop     r14
0x18001cd71  pop     rdi
0x18001cd72  pop     rsi
0x18001cd73  pop     rbp
0x18001cd74  pop     rbx
0x18001cd75  retn
```
