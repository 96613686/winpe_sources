# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18002a6dc`
- end: `0x18002a7d7`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `251`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002a7e0`

## callees

- `0x18002a6dc`
- `0x18002acb0`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a70b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a70b`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(
        unsigned __int64 a1,
        char *a2,
        unsigned __int64 a3)
{
  struct wil::FailureInfo *v5; // rdi
  char v6; // r14
  char v7; // bp
  __int64 v8; // rbx
  unsigned __int64 CurrentThreadId; // r9
  __int64 i; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v11; // rbx
  char v12; // al

  v5 = (struct wil::FailureInfo *)a1;
  *a2 = 0;
  v6 = 0;
  v7 = 1;
  v8 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    a1 = 10 * ((CurrentThreadId >> 2) / 0xA);
    for ( i = *(_QWORD *)(v8 + 8 * ((CurrentThreadId >> 2) % 0xA)); i; i = *(_QWORD *)(i + 8) )
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
             v5,
             *(struct wil::details::ThreadFailureCallbackHolder **)i,
             a2,
             a3) )
      {
        *((_QWORD *)v5 + 9) = a2;
      }
      v11 = *(struct wil::details::ThreadFailureCallbackHolder **)i;
      do
      {
        v12 = *((_BYTE *)v11 + 40);
        *((_BYTE *)v11 + 40) = 1;
        if ( !v12 )
        {
          v6 |= (***((__int64 (__fastcall ****)(_QWORD, struct wil::FailureInfo *))v11 + 1))(*((_QWORD *)v11 + 1), v5);
          *((_BYTE *)v11 + 40) = 0;
        }
        v11 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v11 + 2);
      }
      while ( v11 );
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( !v6 && (*((_BYTE *)v5 + 4) & 2) == 0 )
      v7 = 0;
    LOBYTE(a1) = v7;
    wil::details::g_pfnTelemetryCallback(a1, v5);
  }
}

```

## disassembly

```asm
0x18002a6dc  push    rbx
0x18002a6de  push    rbp
0x18002a6df  push    rsi
0x18002a6e0  push    rdi
0x18002a6e1  push    r14
0x18002a6e3  push    r15
0x18002a6e5  sub     rsp, 28h
0x18002a6e9  mov     r15, r8
0x18002a6ec  mov     rsi, rdx
0x18002a6ef  mov     rdi, rcx
0x18002a6f2  mov     byte ptr [rdx], 0
0x18002a6f5  xor     r14b, r14b
0x18002a6f8  mov     bpl, 1
0x18002a6fb  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18002a702  test    rbx, rbx
0x18002a705  jz      loc_18002A7A5
0x18002a70b  call    cs:__imp_GetCurrentThreadId
0x18002a711  mov     r9d, eax
0x18002a714  mov     r8d, eax
0x18002a717  shr     r8, 2
0x18002a71b  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002a725  mul     r8
0x18002a728  shr     rdx, 3
0x18002a72c  lea     rcx, [rdx+rdx*4]
0x18002a730  add     rcx, rcx
0x18002a733  sub     r8, rcx
0x18002a736  mov     rbx, [rbx+r8*8]
0x18002a73a  test    rbx, rbx
0x18002a73d  jz      short loc_18002A74E
0x18002a73f  cmp     [rbx], r9d
0x18002a742  jz      short loc_18002A74A
0x18002a744  mov     rbx, [rbx+8]
0x18002a748  jmp     short loc_18002A73A
0x18002a74a  add     rbx, 10h
0x18002a74e  test    rbx, rbx
0x18002a751  jz      short loc_18002A7A5
0x18002a753  cmp     qword ptr [rbx], 0
0x18002a757  jz      short loc_18002A7A5
0x18002a759  mov     [rsi], r14b
0x18002a75c  mov     r9, r15; unsigned __int64
0x18002a75f  mov     r8, rsi; char *
0x18002a762  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18002a765  mov     rcx, rdi; struct wil::FailureInfo *
0x18002a768  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18002a76d  test    al, al
0x18002a76f  jz      short loc_18002A775
0x18002a771  mov     [rdi+48h], rsi
0x18002a775  mov     rbx, [rbx]
0x18002a778  mov     al, [rbx+28h]
0x18002a77b  mov     [rbx+28h], bpl
0x18002a77f  test    al, al
0x18002a781  jnz     short loc_18002A79C
0x18002a783  mov     rcx, [rbx+8]
0x18002a787  mov     rax, [rcx]
0x18002a78a  mov     rdx, rdi
0x18002a78d  mov     rax, [rax]
0x18002a790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a795  or      r14b, al
0x18002a798  mov     byte ptr [rbx+28h], 0
0x18002a79c  mov     rbx, [rbx+10h]
0x18002a7a0  test    rbx, rbx
0x18002a7a3  jnz     short loc_18002A778
0x18002a7a5  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18002a7ac  test    rax, rax
0x18002a7af  jz      short loc_18002A7CA
0x18002a7b1  test    r14b, r14b
0x18002a7b4  jnz     short loc_18002A7BE
0x18002a7b6  test    byte ptr [rdi+4], 2
0x18002a7ba  jnz     short loc_18002A7BE
0x18002a7bc  xor     ebp, ebp
0x18002a7be  mov     rdx, rdi
0x18002a7c1  mov     cl, bpl
0x18002a7c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a7c9  nop
0x18002a7ca  add     rsp, 28h
0x18002a7ce  pop     r15
0x18002a7d0  pop     r14
0x18002a7d2  pop     rdi
0x18002a7d3  pop     rsi
0x18002a7d4  pop     rbp
0x18002a7d5  pop     rbx
0x18002a7d6  retn
```
