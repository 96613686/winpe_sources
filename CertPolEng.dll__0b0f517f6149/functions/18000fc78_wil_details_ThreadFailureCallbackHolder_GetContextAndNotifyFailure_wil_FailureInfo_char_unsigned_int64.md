# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000fc78`
- end: `0x18000fd32`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000fd40`

## callees

- `0x18000fc78`
- `0x1800100b0`
- `0x180010290`
- `0x18001b010`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(
        struct wil::FailureInfo *a1,
        char *a2,
        unsigned __int64 a3)
{
  struct wil::FailureInfo *v5; // rdi
  char v6; // r14
  char v7; // bp
  struct wil::details::ThreadFailureCallbackHolder **Local; // rax
  struct wil::details::ThreadFailureCallbackHolder **v9; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v10; // rbx
  char v11; // al

  v5 = a1;
  *a2 = 0;
  v6 = 0;
  v7 = 1;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    Local = (struct wil::details::ThreadFailureCallbackHolder **)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal();
    v9 = Local;
    if ( Local )
    {
      if ( *Local )
      {
        *a2 = 0;
        if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(v5, *Local, a2, a3) )
          *((_QWORD *)v5 + 9) = a2;
        v10 = *v9;
        do
        {
          v11 = *((_BYTE *)v10 + 40);
          *((_BYTE *)v10 + 40) = 1;
          if ( !v11 )
          {
            v6 |= (***((__int64 (__fastcall ****)(_QWORD, struct wil::FailureInfo *))v10 + 1))(*((_QWORD *)v10 + 1), v5);
            *((_BYTE *)v10 + 40) = 0;
          }
          v10 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v10 + 2);
        }
        while ( v10 );
      }
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
0x18000fc78  push    rbx
0x18000fc7a  push    rbp
0x18000fc7b  push    rsi
0x18000fc7c  push    rdi
0x18000fc7d  push    r14
0x18000fc7f  push    r15
0x18000fc81  sub     rsp, 28h
0x18000fc85  mov     r15, r8
0x18000fc88  mov     rsi, rdx
0x18000fc8b  mov     rdi, rcx
0x18000fc8e  mov     byte ptr [rdx], 0
0x18000fc91  xor     r14b, r14b
0x18000fc94  mov     bpl, 1
0x18000fc97  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000fc9f  jz      short loc_18000FD00
0x18000fca1  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000fca6  mov     rbx, rax
0x18000fca9  test    rax, rax
0x18000fcac  jz      short loc_18000FD00
0x18000fcae  cmp     qword ptr [rax], 0
0x18000fcb2  jz      short loc_18000FD00
0x18000fcb4  mov     [rsi], r14b
0x18000fcb7  mov     r9, r15; unsigned __int64
0x18000fcba  mov     r8, rsi; char *
0x18000fcbd  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x18000fcc0  mov     rcx, rdi; struct wil::FailureInfo *
0x18000fcc3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000fcc8  test    al, al
0x18000fcca  jz      short loc_18000FCD0
0x18000fccc  mov     [rdi+48h], rsi
0x18000fcd0  mov     rbx, [rbx]
0x18000fcd3  mov     al, [rbx+28h]
0x18000fcd6  mov     [rbx+28h], bpl
0x18000fcda  test    al, al
0x18000fcdc  jnz     short loc_18000FCF7
0x18000fcde  mov     rcx, [rbx+8]
0x18000fce2  mov     rax, [rcx]
0x18000fce5  mov     rdx, rdi
0x18000fce8  mov     rax, [rax]
0x18000fceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcf0  or      r14b, al
0x18000fcf3  mov     byte ptr [rbx+28h], 0
0x18000fcf7  mov     rbx, [rbx+10h]
0x18000fcfb  test    rbx, rbx
0x18000fcfe  jnz     short loc_18000FCD3
0x18000fd00  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000fd07  test    rax, rax
0x18000fd0a  jz      short loc_18000FD25
0x18000fd0c  test    r14b, r14b
0x18000fd0f  jnz     short loc_18000FD19
0x18000fd11  test    byte ptr [rdi+4], 2
0x18000fd15  jnz     short loc_18000FD19
0x18000fd17  xor     ebp, ebp
0x18000fd19  mov     rdx, rdi
0x18000fd1c  mov     cl, bpl
0x18000fd1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd24  nop
0x18000fd25  add     rsp, 28h
0x18000fd29  pop     r15
0x18000fd2b  pop     r14
0x18000fd2d  pop     rdi
0x18000fd2e  pop     rsi
0x18000fd2f  pop     rbp
0x18000fd30  pop     rbx
0x18000fd31  retn
```
