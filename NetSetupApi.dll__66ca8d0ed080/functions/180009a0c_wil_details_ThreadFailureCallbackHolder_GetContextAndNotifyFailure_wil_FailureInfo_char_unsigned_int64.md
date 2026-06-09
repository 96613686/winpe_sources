# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180009a0c`
- end: `0x180009acf`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `195`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180009ae0`

## callees

- `0x180009a0c`
- `0x180009e5c`
- `0x180009fe4`
- `0x180015010`

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
    Local = (struct wil::details::ThreadFailureCallbackHolder **)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(a1);
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
0x180009a0c  push    rbx
0x180009a0e  push    rbp
0x180009a0f  push    rsi
0x180009a10  push    rdi
0x180009a11  push    r14
0x180009a13  push    r15
0x180009a15  sub     rsp, 38h
0x180009a19  mov     [rsp+68h+var_48], 0FFFFFFFFFFFFFFFEh
0x180009a22  mov     r15, r8
0x180009a25  mov     rsi, rdx
0x180009a28  mov     rdi, rcx
0x180009a2b  mov     byte ptr [rdx], 0
0x180009a2e  xor     r14b, r14b
0x180009a31  mov     bpl, 1
0x180009a34  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180009a3c  jz      short loc_180009A9D
0x180009a3e  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180009a43  mov     rbx, rax
0x180009a46  test    rax, rax
0x180009a49  jz      short loc_180009A9D
0x180009a4b  cmp     qword ptr [rax], 0
0x180009a4f  jz      short loc_180009A9D
0x180009a51  mov     [rsi], r14b
0x180009a54  mov     r9, r15; unsigned __int64
0x180009a57  mov     r8, rsi; char *
0x180009a5a  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x180009a5d  mov     rcx, rdi; struct wil::FailureInfo *
0x180009a60  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180009a65  test    al, al
0x180009a67  jz      short loc_180009A6D
0x180009a69  mov     [rdi+48h], rsi
0x180009a6d  mov     rbx, [rbx]
0x180009a70  mov     al, [rbx+28h]
0x180009a73  mov     [rbx+28h], bpl
0x180009a77  test    al, al
0x180009a79  jnz     short loc_180009A94
0x180009a7b  mov     rcx, [rbx+8]
0x180009a7f  mov     rax, [rcx]
0x180009a82  mov     rdx, rdi
0x180009a85  mov     rax, [rax]
0x180009a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a8d  or      r14b, al
0x180009a90  mov     byte ptr [rbx+28h], 0
0x180009a94  mov     rbx, [rbx+10h]
0x180009a98  test    rbx, rbx
0x180009a9b  jnz     short loc_180009A70
0x180009a9d  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180009aa4  test    rax, rax
0x180009aa7  jz      short loc_180009AC2
0x180009aa9  test    r14b, r14b
0x180009aac  jnz     short loc_180009AB6
0x180009aae  test    byte ptr [rdi+4], 2
0x180009ab2  jnz     short loc_180009AB6
0x180009ab4  xor     ebp, ebp
0x180009ab6  mov     rdx, rdi
0x180009ab9  mov     cl, bpl
0x180009abc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ac1  nop
0x180009ac2  add     rsp, 38h
0x180009ac6  pop     r15
0x180009ac8  pop     r14
0x180009aca  pop     rdi
0x180009acb  pop     rsi
0x180009acc  pop     rbp
0x180009acd  pop     rbx
0x180009ace  retn
```
