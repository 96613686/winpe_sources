# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140004160`
- end: `0x1400042a7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `327`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140004160`
- `0x14000479c`
- `0x140004880`
- `0x140005a14`
- `0x14000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000418a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000424c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000418a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000424c`

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
0x140004160  push    rbx
0x140004162  push    rbp
0x140004163  push    rsi
0x140004164  push    rdi
0x140004165  push    r14
0x140004167  sub     rsp, 20h
0x14000416b  mov     r14, r8
0x14000416e  mov     rsi, rdx
0x140004171  mov     rdi, rcx
0x140004174  mov     byte ptr [rdx], 0
0x140004177  xor     bpl, bpl
0x14000417a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140004181  test    rbx, rbx
0x140004184  jz      loc_140004220
0x14000418a  call    cs:__imp_GetCurrentThreadId
0x140004190  mov     r9d, eax
0x140004193  mov     r8d, eax
0x140004196  shr     r8, 2
0x14000419a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400041a4  mul     r8
0x1400041a7  shr     rdx, 3
0x1400041ab  lea     rcx, [rdx+rdx*4]
0x1400041af  add     rcx, rcx
0x1400041b2  sub     r8, rcx
0x1400041b5  mov     rbx, [rbx+r8*8]
0x1400041b9  jmp     short loc_1400041C4
0x1400041bb  cmp     [rbx], r9d
0x1400041be  jz      short loc_14000423B
0x1400041c0  mov     rbx, [rbx+8]
0x1400041c4  test    rbx, rbx
0x1400041c7  jnz     short loc_1400041BB
0x1400041c9  test    rbx, rbx
0x1400041cc  jz      short loc_140004220
0x1400041ce  cmp     qword ptr [rbx], 0
0x1400041d2  jz      short loc_140004220
0x1400041d4  mov     [rsi], bpl
0x1400041d7  mov     r9, r14; unsigned __int64
0x1400041da  mov     r8, rsi; char *
0x1400041dd  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1400041e0  mov     rcx, rdi; struct wil::FailureInfo *
0x1400041e3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1400041e8  test    al, al
0x1400041ea  jz      short loc_1400041F0
0x1400041ec  mov     [rdi+48h], rsi
0x1400041f0  mov     rbx, [rbx]
0x1400041f3  mov     al, [rbx+28h]
0x1400041f6  mov     byte ptr [rbx+28h], 1
0x1400041fa  test    al, al
0x1400041fc  jnz     short loc_140004217
0x1400041fe  mov     rcx, [rbx+8]
0x140004202  mov     rax, [rcx]
0x140004205  mov     rdx, rdi
0x140004208  mov     rax, [rax]
0x14000420b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004210  or      bpl, al
0x140004213  mov     byte ptr [rbx+28h], 0
0x140004217  mov     rbx, [rbx+10h]
0x14000421b  test    rbx, rbx
0x14000421e  jnz     short loc_1400041F3
0x140004220  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140004227  test    rax, rax
0x14000422a  jz      short loc_14000424C
0x14000422c  test    bpl, bpl
0x14000422f  jnz     short loc_140004241
0x140004231  test    byte ptr [rdi+4], 2
0x140004235  jnz     short loc_140004241
0x140004237  xor     ecx, ecx
0x140004239  jmp     short loc_140004243
0x14000423b  add     rbx, 10h
0x14000423f  jmp     short loc_1400041C9
0x140004241  mov     cl, 1
0x140004243  mov     rdx, rdi
0x140004246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000424b  nop
0x14000424c  call    cs:__imp_GetCurrentThreadId
0x140004252  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140004258  cmp     ecx, eax
0x14000425a  jz      short loc_14000429C
0x14000425c  mov     ecx, 1
0x140004261  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140004269  inc     ecx; this
0x14000426b  cmp     ecx, 4
0x14000426e  jge     short loc_140004295
0x140004270  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140004276  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x14000427b  test    rax, rax
0x14000427e  jz      short loc_14000428B
0x140004280  mov     rdx, rdi; struct wil::FailureInfo *
0x140004283  mov     rcx, rax; this
0x140004286  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x14000428b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140004295  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000429c  add     rsp, 20h
0x1400042a0  pop     r14
0x1400042a2  pop     rdi
0x1400042a3  pop     rsi
0x1400042a4  pop     rbp
0x1400042a5  pop     rbx
0x1400042a6  retn
```
