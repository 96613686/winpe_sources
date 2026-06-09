# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180005160`
- end: `0x1800052b4`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `340`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180005160`
- `0x18000582c`
- `0x180005918`
- `0x1800076ec`
- `0x18000b010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000518a`
- `KERNEL32!GetCurrentThreadId` at `0x180005252`
- `KERNEL32!GetCurrentThreadId` at `0x18000518a`
- `KERNEL32!GetCurrentThreadId` at `0x180005252`

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
  wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax

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
      if ( ThreadLocalDataCache )
        wil::details_abi::ThreadLocalData::SetLastError(ThreadLocalDataCache, v5);
      `wil::SetLastError'::`2'::lastThread = 0;
    }
    _InterlockedDecrement(&`wil::SetLastError'::`5'::depth);
  }
}

```

## disassembly

```asm
0x180005160  push    rbx
0x180005162  push    rbp
0x180005163  push    rsi
0x180005164  push    rdi
0x180005165  push    r14
0x180005167  sub     rsp, 20h
0x18000516b  mov     r14, r8
0x18000516e  mov     rsi, rdx
0x180005171  mov     rdi, rcx
0x180005174  mov     byte ptr [rdx], 0
0x180005177  xor     bpl, bpl
0x18000517a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005181  test    rbx, rbx
0x180005184  jz      loc_180005226
0x18000518a  call    cs:__imp_GetCurrentThreadId
0x180005191  nop     dword ptr [rax+rax+00h]
0x180005196  mov     r9d, eax
0x180005199  mov     r8d, eax
0x18000519c  shr     r8, 2
0x1800051a0  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800051aa  mul     r8
0x1800051ad  shr     rdx, 3
0x1800051b1  lea     rcx, [rdx+rdx*4]
0x1800051b5  add     rcx, rcx
0x1800051b8  sub     r8, rcx
0x1800051bb  mov     rbx, [rbx+r8*8]
0x1800051bf  jmp     short loc_1800051CA
0x1800051c1  cmp     [rbx], r9d
0x1800051c4  jz      short loc_180005241
0x1800051c6  mov     rbx, [rbx+8]
0x1800051ca  test    rbx, rbx
0x1800051cd  jnz     short loc_1800051C1
0x1800051cf  test    rbx, rbx
0x1800051d2  jz      short loc_180005226
0x1800051d4  cmp     qword ptr [rbx], 0
0x1800051d8  jz      short loc_180005226
0x1800051da  mov     [rsi], bpl
0x1800051dd  mov     r9, r14; unsigned __int64
0x1800051e0  mov     r8, rsi; char *
0x1800051e3  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800051e6  mov     rcx, rdi; struct wil::FailureInfo *
0x1800051e9  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800051ee  test    al, al
0x1800051f0  jz      short loc_1800051F6
0x1800051f2  mov     [rdi+48h], rsi
0x1800051f6  mov     rbx, [rbx]
0x1800051f9  mov     al, [rbx+28h]
0x1800051fc  mov     byte ptr [rbx+28h], 1
0x180005200  test    al, al
0x180005202  jnz     short loc_18000521D
0x180005204  mov     rcx, [rbx+8]
0x180005208  mov     rax, [rcx]
0x18000520b  mov     rdx, rdi
0x18000520e  mov     rax, [rax]
0x180005211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005216  or      bpl, al
0x180005219  mov     byte ptr [rbx+28h], 0
0x18000521d  mov     rbx, [rbx+10h]
0x180005221  test    rbx, rbx
0x180005224  jnz     short loc_1800051F9
0x180005226  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000522d  test    rax, rax
0x180005230  jz      short loc_180005252
0x180005232  test    bpl, bpl
0x180005235  jnz     short loc_180005247
0x180005237  test    byte ptr [rdi+4], 2
0x18000523b  jnz     short loc_180005247
0x18000523d  xor     ecx, ecx
0x18000523f  jmp     short loc_180005249
0x180005241  add     rbx, 10h
0x180005245  jmp     short loc_1800051CF
0x180005247  mov     cl, 1
0x180005249  mov     rdx, rdi
0x18000524c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005251  nop
0x180005252  call    cs:__imp_GetCurrentThreadId
0x180005259  nop     dword ptr [rax+rax+00h]
0x18000525e  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005264  cmp     ecx, eax
0x180005266  jz      short loc_1800052A8
0x180005268  mov     ecx, 1
0x18000526d  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180005275  inc     ecx; this
0x180005277  cmp     ecx, 4
0x18000527a  jge     short loc_1800052A1
0x18000527c  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005282  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180005287  test    rax, rax
0x18000528a  jz      short loc_180005297
0x18000528c  mov     rdx, rdi; struct wil::FailureInfo *
0x18000528f  mov     rcx, rax; this
0x180005292  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x180005297  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800052a1  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800052a8  add     rsp, 20h
0x1800052ac  pop     r14
0x1800052ae  pop     rdi
0x1800052af  pop     rsi
0x1800052b0  pop     rbp
0x1800052b1  pop     rbx
0x1800052b2  retn
```
