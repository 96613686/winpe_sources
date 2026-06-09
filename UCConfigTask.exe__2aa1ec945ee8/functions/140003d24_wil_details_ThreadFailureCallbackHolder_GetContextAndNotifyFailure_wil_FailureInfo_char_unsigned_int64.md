# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140003d24`
- end: `0x140003dde`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140003df0`

## callees

- `0x140003d24`
- `0x1400041fc`
- `0x140004410`
- `0x140009010`

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
0x140003d24  push    rbx
0x140003d26  push    rbp
0x140003d27  push    rsi
0x140003d28  push    rdi
0x140003d29  push    r14
0x140003d2b  push    r15
0x140003d2d  sub     rsp, 28h
0x140003d31  mov     r15, r8
0x140003d34  mov     rsi, rdx
0x140003d37  mov     rdi, rcx
0x140003d3a  mov     byte ptr [rdx], 0
0x140003d3d  xor     r14b, r14b
0x140003d40  mov     bpl, 1
0x140003d43  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140003d4b  jz      short loc_140003DAC
0x140003d4d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x140003d52  mov     rbx, rax
0x140003d55  test    rax, rax
0x140003d58  jz      short loc_140003DAC
0x140003d5a  cmp     qword ptr [rax], 0
0x140003d5e  jz      short loc_140003DAC
0x140003d60  mov     [rsi], r14b
0x140003d63  mov     r9, r15; unsigned __int64
0x140003d66  mov     r8, rsi; char *
0x140003d69  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x140003d6c  mov     rcx, rdi; struct wil::FailureInfo *
0x140003d6f  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140003d74  test    al, al
0x140003d76  jz      short loc_140003D7C
0x140003d78  mov     [rdi+48h], rsi
0x140003d7c  mov     rbx, [rbx]
0x140003d7f  mov     al, [rbx+28h]
0x140003d82  mov     [rbx+28h], bpl
0x140003d86  test    al, al
0x140003d88  jnz     short loc_140003DA3
0x140003d8a  mov     rcx, [rbx+8]
0x140003d8e  mov     rax, [rcx]
0x140003d91  mov     rdx, rdi
0x140003d94  mov     rax, [rax]
0x140003d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d9c  or      r14b, al
0x140003d9f  mov     byte ptr [rbx+28h], 0
0x140003da3  mov     rbx, [rbx+10h]
0x140003da7  test    rbx, rbx
0x140003daa  jnz     short loc_140003D7F
0x140003dac  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140003db3  test    rax, rax
0x140003db6  jz      short loc_140003DD1
0x140003db8  test    r14b, r14b
0x140003dbb  jnz     short loc_140003DC5
0x140003dbd  test    byte ptr [rdi+4], 2
0x140003dc1  jnz     short loc_140003DC5
0x140003dc3  xor     ebp, ebp
0x140003dc5  mov     rdx, rdi
0x140003dc8  mov     cl, bpl
0x140003dcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003dd0  nop
0x140003dd1  add     rsp, 28h
0x140003dd5  pop     r15
0x140003dd7  pop     r14
0x140003dd9  pop     rdi
0x140003dda  pop     rsi
0x140003ddb  pop     rbp
0x140003ddc  pop     rbx
0x140003ddd  retn
```
