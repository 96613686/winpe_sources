# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000c1f0`
- end: `0x18000c2aa`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000c2b0`

## callees

- `0x18000c1f0`
- `0x18000c4d8`
- `0x18000ce0c`
- `0x180018010`

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
0x18000c1f0  push    rbx
0x18000c1f2  push    rbp
0x18000c1f3  push    rsi
0x18000c1f4  push    rdi
0x18000c1f5  push    r14
0x18000c1f7  push    r15
0x18000c1f9  sub     rsp, 28h
0x18000c1fd  mov     r15, r8
0x18000c200  mov     rsi, rdx
0x18000c203  mov     rdi, rcx
0x18000c206  mov     byte ptr [rdx], 0
0x18000c209  xor     r14b, r14b
0x18000c20c  mov     bpl, 1
0x18000c20f  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000c217  jz      short loc_18000C278
0x18000c219  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000c21e  mov     rbx, rax
0x18000c221  test    rax, rax
0x18000c224  jz      short loc_18000C278
0x18000c226  cmp     qword ptr [rax], 0
0x18000c22a  jz      short loc_18000C278
0x18000c22c  mov     [rsi], r14b
0x18000c22f  mov     r9, r15; unsigned __int64
0x18000c232  mov     r8, rsi; char *
0x18000c235  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x18000c238  mov     rcx, rdi; struct wil::FailureInfo *
0x18000c23b  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000c240  test    al, al
0x18000c242  jz      short loc_18000C248
0x18000c244  mov     [rdi+48h], rsi
0x18000c248  mov     rbx, [rbx]
0x18000c24b  mov     al, [rbx+28h]
0x18000c24e  mov     [rbx+28h], bpl
0x18000c252  test    al, al
0x18000c254  jnz     short loc_18000C26F
0x18000c256  mov     rcx, [rbx+8]
0x18000c25a  mov     rax, [rcx]
0x18000c25d  mov     rdx, rdi
0x18000c260  mov     rax, [rax]
0x18000c263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c268  or      r14b, al
0x18000c26b  mov     byte ptr [rbx+28h], 0
0x18000c26f  mov     rbx, [rbx+10h]
0x18000c273  test    rbx, rbx
0x18000c276  jnz     short loc_18000C24B
0x18000c278  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000c27f  test    rax, rax
0x18000c282  jz      short loc_18000C29D
0x18000c284  test    r14b, r14b
0x18000c287  jnz     short loc_18000C291
0x18000c289  test    byte ptr [rdi+4], 2
0x18000c28d  jnz     short loc_18000C291
0x18000c28f  xor     ebp, ebp
0x18000c291  mov     rdx, rdi
0x18000c294  mov     cl, bpl
0x18000c297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c29c  nop
0x18000c29d  add     rsp, 28h
0x18000c2a1  pop     r15
0x18000c2a3  pop     r14
0x18000c2a5  pop     rdi
0x18000c2a6  pop     rsi
0x18000c2a7  pop     rbp
0x18000c2a8  pop     rbx
0x18000c2a9  retn
```
