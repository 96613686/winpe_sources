# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1400040f0`
- end: `0x140004237`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `327`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1400040f0`
- `0x14000472c`
- `0x140004810`
- `0x140005968`
- `0x14000f010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000411a`
- `KERNEL32!GetCurrentThreadId` at `0x1400041dc`
- `KERNEL32!GetCurrentThreadId` at `0x14000411a`
- `KERNEL32!GetCurrentThreadId` at `0x1400041dc`

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
0x1400040f0  push    rbx
0x1400040f2  push    rbp
0x1400040f3  push    rsi
0x1400040f4  push    rdi
0x1400040f5  push    r14
0x1400040f7  sub     rsp, 20h
0x1400040fb  mov     r14, r8
0x1400040fe  mov     rsi, rdx
0x140004101  mov     rdi, rcx
0x140004104  mov     byte ptr [rdx], 0
0x140004107  xor     bpl, bpl
0x14000410a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140004111  test    rbx, rbx
0x140004114  jz      loc_1400041B0
0x14000411a  call    cs:__imp_GetCurrentThreadId
0x140004120  mov     r9d, eax
0x140004123  mov     r8d, eax
0x140004126  shr     r8, 2
0x14000412a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140004134  mul     r8
0x140004137  shr     rdx, 3
0x14000413b  lea     rcx, [rdx+rdx*4]
0x14000413f  add     rcx, rcx
0x140004142  sub     r8, rcx
0x140004145  mov     rbx, [rbx+r8*8]
0x140004149  jmp     short loc_140004154
0x14000414b  cmp     [rbx], r9d
0x14000414e  jz      short loc_1400041CB
0x140004150  mov     rbx, [rbx+8]
0x140004154  test    rbx, rbx
0x140004157  jnz     short loc_14000414B
0x140004159  test    rbx, rbx
0x14000415c  jz      short loc_1400041B0
0x14000415e  cmp     qword ptr [rbx], 0
0x140004162  jz      short loc_1400041B0
0x140004164  mov     [rsi], bpl
0x140004167  mov     r9, r14; unsigned __int64
0x14000416a  mov     r8, rsi; char *
0x14000416d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x140004170  mov     rcx, rdi; struct wil::FailureInfo *
0x140004173  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140004178  test    al, al
0x14000417a  jz      short loc_140004180
0x14000417c  mov     [rdi+48h], rsi
0x140004180  mov     rbx, [rbx]
0x140004183  mov     al, [rbx+28h]
0x140004186  mov     byte ptr [rbx+28h], 1
0x14000418a  test    al, al
0x14000418c  jnz     short loc_1400041A7
0x14000418e  mov     rcx, [rbx+8]
0x140004192  mov     rax, [rcx]
0x140004195  mov     rdx, rdi
0x140004198  mov     rax, [rax]
0x14000419b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400041a0  or      bpl, al
0x1400041a3  mov     byte ptr [rbx+28h], 0
0x1400041a7  mov     rbx, [rbx+10h]
0x1400041ab  test    rbx, rbx
0x1400041ae  jnz     short loc_140004183
0x1400041b0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1400041b7  test    rax, rax
0x1400041ba  jz      short loc_1400041DC
0x1400041bc  test    bpl, bpl
0x1400041bf  jnz     short loc_1400041D1
0x1400041c1  test    byte ptr [rdi+4], 2
0x1400041c5  jnz     short loc_1400041D1
0x1400041c7  xor     ecx, ecx
0x1400041c9  jmp     short loc_1400041D3
0x1400041cb  add     rbx, 10h
0x1400041cf  jmp     short loc_140004159
0x1400041d1  mov     cl, 1
0x1400041d3  mov     rdx, rdi
0x1400041d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400041db  nop
0x1400041dc  call    cs:__imp_GetCurrentThreadId
0x1400041e2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400041e8  cmp     ecx, eax
0x1400041ea  jz      short loc_14000422C
0x1400041ec  mov     ecx, 1
0x1400041f1  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1400041f9  inc     ecx; this
0x1400041fb  cmp     ecx, 4
0x1400041fe  jge     short loc_140004225
0x140004200  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140004206  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x14000420b  test    rax, rax
0x14000420e  jz      short loc_14000421B
0x140004210  mov     rdx, rdi; struct wil::FailureInfo *
0x140004213  mov     rcx, rax; this
0x140004216  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x14000421b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140004225  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000422c  add     rsp, 20h
0x140004230  pop     r14
0x140004232  pop     rdi
0x140004233  pop     rsi
0x140004234  pop     rbp
0x140004235  pop     rbx
0x140004236  retn
```
