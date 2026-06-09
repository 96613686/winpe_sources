# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180007960`
- end: `0x180007b67`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180007960`
- `0x180008100`
- `0x1800081e4`
- `0x1800088bc`
- `0x180009174`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000798a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007a4c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000798a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007a4c`

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
0x180007960  push    rbx
0x180007962  push    rbp
0x180007963  push    rsi
0x180007964  push    rdi
0x180007965  push    r14
0x180007967  sub     rsp, 20h
0x18000796b  mov     r14, r8
0x18000796e  mov     rsi, rdx
0x180007971  mov     rdi, rcx
0x180007974  mov     byte ptr [rdx], 0
0x180007977  xor     bpl, bpl
0x18000797a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180007981  test    rbx, rbx
0x180007984  jz      loc_180007A20
0x18000798a  call    cs:__imp_GetCurrentThreadId
0x180007990  mov     r9d, eax
0x180007993  mov     r8d, eax
0x180007996  shr     r8, 2
0x18000799a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800079a4  mul     r8
0x1800079a7  shr     rdx, 3
0x1800079ab  lea     rcx, [rdx+rdx*4]
0x1800079af  add     rcx, rcx
0x1800079b2  sub     r8, rcx
0x1800079b5  mov     rbx, [rbx+r8*8]
0x1800079b9  jmp     short loc_1800079C4
0x1800079bb  cmp     [rbx], r9d
0x1800079be  jz      short loc_180007A3B
0x1800079c0  mov     rbx, [rbx+8]
0x1800079c4  test    rbx, rbx
0x1800079c7  jnz     short loc_1800079BB
0x1800079c9  test    rbx, rbx
0x1800079cc  jz      short loc_180007A20
0x1800079ce  cmp     qword ptr [rbx], 0
0x1800079d2  jz      short loc_180007A20
0x1800079d4  mov     [rsi], bpl
0x1800079d7  mov     r9, r14; unsigned __int64
0x1800079da  mov     r8, rsi; char *
0x1800079dd  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800079e0  mov     rcx, rdi; struct wil::FailureInfo *
0x1800079e3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800079e8  test    al, al
0x1800079ea  jz      short loc_1800079F0
0x1800079ec  mov     [rdi+48h], rsi
0x1800079f0  mov     rbx, [rbx]
0x1800079f3  mov     al, [rbx+28h]
0x1800079f6  mov     byte ptr [rbx+28h], 1
0x1800079fa  test    al, al
0x1800079fc  jnz     short loc_180007A17
0x1800079fe  mov     rcx, [rbx+8]
0x180007a02  mov     rax, [rcx]
0x180007a05  mov     rdx, rdi
0x180007a08  mov     rax, [rax]
0x180007a0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a10  or      bpl, al
0x180007a13  mov     byte ptr [rbx+28h], 0
0x180007a17  mov     rbx, [rbx+10h]
0x180007a1b  test    rbx, rbx
0x180007a1e  jnz     short loc_1800079F3
0x180007a20  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180007a27  test    rax, rax
0x180007a2a  jz      short loc_180007A4C
0x180007a2c  test    bpl, bpl
0x180007a2f  jnz     short loc_180007A41
0x180007a31  test    byte ptr [rdi+4], 2
0x180007a35  jnz     short loc_180007A41
0x180007a37  xor     ecx, ecx
0x180007a39  jmp     short loc_180007A43
0x180007a3b  add     rbx, 10h
0x180007a3f  jmp     short loc_1800079C9
0x180007a41  mov     cl, 1
0x180007a43  mov     rdx, rdi
0x180007a46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a4b  nop
0x180007a4c  call    cs:__imp_GetCurrentThreadId
0x180007a52  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007a58  cmp     ecx, eax
0x180007a5a  jz      loc_180007B5C
0x180007a60  mov     ecx, 1
0x180007a65  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180007a6d  inc     ecx; this
0x180007a6f  cmp     ecx, 4
0x180007a72  jge     loc_180007B55
0x180007a78  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007a7e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180007a83  mov     rbx, rax
0x180007a86  test    rax, rax
0x180007a89  jz      loc_180007B4B
0x180007a8f  mov     esi, [rax+10h]
0x180007a92  mov     ebp, 50h ; 'P'
0x180007a97  cmp     qword ptr [rax+18h], 0
0x180007a9c  jnz     short loc_180007AD3
0x180007a9e  test    esi, esi
0x180007aa0  jz      short loc_180007AD3
0x180007aa2  mov     edx, 190h; dwBytes
0x180007aa7  lea     ecx, [rbp-48h]; dwFlags
0x180007aaa  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007aaf  mov     [rbx+18h], rax
0x180007ab3  test    rax, rax
0x180007ab6  jz      short loc_180007AD3
0x180007ab8  mov     dword ptr [rbx+20h], 5
0x180007abf  lea     rcx, [rax+190h]
0x180007ac6  jmp     short loc_180007ACE
0x180007ac8  mov     [rax], bp
0x180007acb  add     rax, rbp
0x180007ace  cmp     rax, rcx
0x180007ad1  jnz     short loc_180007AC8
0x180007ad3  mov     r9, [rbx+18h]
0x180007ad7  test    r9, r9
0x180007ada  jz      short loc_180007B4B
0x180007adc  test    esi, esi
0x180007ade  jz      short loc_180007B11
0x180007ae0  mov     rcx, r9
0x180007ae3  movzx   eax, word ptr [rbx+20h]
0x180007ae7  lea     rdx, [rax+rax*4]
0x180007aeb  shl     rdx, 4
0x180007aef  add     rdx, r9
0x180007af2  cmp     r9, rdx
0x180007af5  jz      short loc_180007B11
0x180007af7  mov     r8d, [rbx+10h]
0x180007afb  cmp     [rcx+4], r8d
0x180007aff  jbe     short loc_180007B09
0x180007b01  mov     eax, [rdi+8]
0x180007b04  cmp     [rcx+8], eax
0x180007b07  jz      short loc_180007B4B
0x180007b09  add     rcx, rbp
0x180007b0c  cmp     rcx, rdx
0x180007b0f  jnz     short loc_180007AFB
0x180007b11  movzx   eax, word ptr [rbx+22h]
0x180007b15  inc     eax
0x180007b17  movzx   ecx, word ptr [rbx+20h]
0x180007b1b  xor     edx, edx
0x180007b1d  div     ecx
0x180007b1f  mov     [rbx+22h], dx
0x180007b23  mov     rax, [rbx+8]
0x180007b27  mov     r8d, 1
0x180007b2d  lock xadd [rax], r8d
0x180007b32  inc     r8d; unsigned int
0x180007b35  movzx   eax, dx
0x180007b38  lea     rcx, [rax+rax*4]
0x180007b3c  shl     rcx, 4
0x180007b40  add     rcx, r9; this
0x180007b43  mov     rdx, rdi; struct wil::FailureInfo *
0x180007b46  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180007b4b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007b55  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180007b5c  add     rsp, 20h
0x180007b60  pop     r14
0x180007b62  pop     rdi
0x180007b63  pop     rsi
0x180007b64  pop     rbp
0x180007b65  pop     rbx
0x180007b66  retn
```
