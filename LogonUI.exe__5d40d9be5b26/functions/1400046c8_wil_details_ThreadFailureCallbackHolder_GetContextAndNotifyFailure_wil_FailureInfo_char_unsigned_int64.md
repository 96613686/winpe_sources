# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1400046c8`
- end: `0x1400047c2`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `250`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400047d0`

## callees

- `0x1400046c8`
- `0x140004ca0`
- `0x140008010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400046f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400046f7`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(
        unsigned __int64 a1,
        char *a2,
        unsigned __int64 a3)
{
  char v3; // r14
  __int64 v4; // rbx
  struct wil::FailureInfo *v7; // rdi
  char v8; // bp
  unsigned __int64 CurrentThreadId; // r9
  __int64 i; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v11; // rbx
  char v12; // al

  *a2 = 0;
  v3 = 0;
  v4 = wil::details::g_pThreadFailureCallbacks;
  v7 = (struct wil::FailureInfo *)a1;
  v8 = 1;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    a1 = 10 * ((CurrentThreadId >> 2) / 0xA);
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
      *a2 = 0;
      if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(
             v7,
             *(struct wil::details::ThreadFailureCallbackHolder **)i,
             a2,
             a3) )
      {
        *((_QWORD *)v7 + 9) = a2;
      }
      v11 = *(struct wil::details::ThreadFailureCallbackHolder **)i;
      do
      {
        v12 = *((_BYTE *)v11 + 40);
        *((_BYTE *)v11 + 40) = 1;
        if ( !v12 )
        {
          v3 |= (***((__int64 (__fastcall ****)(_QWORD, struct wil::FailureInfo *))v11 + 1))(*((_QWORD *)v11 + 1), v7);
          *((_BYTE *)v11 + 40) = 0;
        }
        v11 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v11 + 2);
      }
      while ( v11 );
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( !v3 && (*((_BYTE *)v7 + 4) & 2) == 0 )
      v8 = 0;
    LOBYTE(a1) = v8;
    wil::details::g_pfnTelemetryCallback(a1, v7);
  }
}

```

## disassembly

```asm
0x1400046c8  push    rbx
0x1400046ca  push    rbp
0x1400046cb  push    rsi
0x1400046cc  push    rdi
0x1400046cd  push    r14
0x1400046cf  push    r15
0x1400046d1  sub     rsp, 28h
0x1400046d5  mov     byte ptr [rdx], 0
0x1400046d8  xor     r14b, r14b
0x1400046db  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1400046e2  mov     r15, r8
0x1400046e5  mov     rsi, rdx
0x1400046e8  mov     rdi, rcx
0x1400046eb  mov     bpl, 1
0x1400046ee  test    rbx, rbx
0x1400046f1  jz      loc_140004791
0x1400046f7  call    cs:__imp_GetCurrentThreadId
0x1400046fd  mov     r8d, eax
0x140004700  mov     r9d, eax
0x140004703  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000470d  shr     r8, 2
0x140004711  mul     r8
0x140004714  shr     rdx, 3
0x140004718  lea     rcx, [rdx+rdx*4]
0x14000471c  add     rcx, rcx
0x14000471f  sub     r8, rcx
0x140004722  mov     rbx, [rbx+r8*8]
0x140004726  test    rbx, rbx
0x140004729  jz      short loc_14000473A
0x14000472b  cmp     [rbx], r9d
0x14000472e  jz      short loc_140004736
0x140004730  mov     rbx, [rbx+8]
0x140004734  jmp     short loc_140004726
0x140004736  add     rbx, 10h
0x14000473a  test    rbx, rbx
0x14000473d  jz      short loc_140004791
0x14000473f  cmp     qword ptr [rbx], 0
0x140004743  jz      short loc_140004791
0x140004745  mov     [rsi], r14b
0x140004748  mov     r9, r15; unsigned __int64
0x14000474b  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x14000474e  mov     r8, rsi; char *
0x140004751  mov     rcx, rdi; struct wil::FailureInfo *
0x140004754  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140004759  test    al, al
0x14000475b  jz      short loc_140004761
0x14000475d  mov     [rdi+48h], rsi
0x140004761  mov     rbx, [rbx]
0x140004764  mov     al, [rbx+28h]
0x140004767  mov     [rbx+28h], bpl
0x14000476b  test    al, al
0x14000476d  jnz     short loc_140004788
0x14000476f  mov     rcx, [rbx+8]
0x140004773  mov     rdx, rdi
0x140004776  mov     rax, [rcx]
0x140004779  mov     rax, [rax]
0x14000477c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004781  or      r14b, al
0x140004784  mov     byte ptr [rbx+28h], 0
0x140004788  mov     rbx, [rbx+10h]
0x14000478c  test    rbx, rbx
0x14000478f  jnz     short loc_140004764
0x140004791  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140004798  test    rax, rax
0x14000479b  jz      short loc_1400047B5
0x14000479d  test    r14b, r14b
0x1400047a0  jnz     short loc_1400047AA
0x1400047a2  test    byte ptr [rdi+4], 2
0x1400047a6  jnz     short loc_1400047AA
0x1400047a8  xor     ebp, ebp
0x1400047aa  mov     rdx, rdi
0x1400047ad  mov     cl, bpl
0x1400047b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400047b5  add     rsp, 28h
0x1400047b9  pop     r15
0x1400047bb  pop     r14
0x1400047bd  pop     rdi
0x1400047be  pop     rsi
0x1400047bf  pop     rbp
0x1400047c0  pop     rbx
0x1400047c1  retn
```
