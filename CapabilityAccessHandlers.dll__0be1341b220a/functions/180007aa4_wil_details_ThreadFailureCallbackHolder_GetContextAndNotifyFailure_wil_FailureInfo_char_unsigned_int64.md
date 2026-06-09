# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180007aa4`
- end: `0x180007b5e`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007b70`

## callees

- `0x180007aa4`
- `0x180007f8c`
- `0x180008130`
- `0x180014010`

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
0x180007aa4  push    rbx
0x180007aa6  push    rbp
0x180007aa7  push    rsi
0x180007aa8  push    rdi
0x180007aa9  push    r14
0x180007aab  push    r15
0x180007aad  sub     rsp, 28h
0x180007ab1  mov     r15, r8
0x180007ab4  mov     rsi, rdx
0x180007ab7  mov     rdi, rcx
0x180007aba  mov     byte ptr [rdx], 0
0x180007abd  xor     r14b, r14b
0x180007ac0  mov     bpl, 1
0x180007ac3  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180007acb  jz      short loc_180007B2C
0x180007acd  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180007ad2  mov     rbx, rax
0x180007ad5  test    rax, rax
0x180007ad8  jz      short loc_180007B2C
0x180007ada  cmp     qword ptr [rax], 0
0x180007ade  jz      short loc_180007B2C
0x180007ae0  mov     [rsi], r14b
0x180007ae3  mov     r9, r15; unsigned __int64
0x180007ae6  mov     r8, rsi; char *
0x180007ae9  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x180007aec  mov     rcx, rdi; struct wil::FailureInfo *
0x180007aef  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180007af4  test    al, al
0x180007af6  jz      short loc_180007AFC
0x180007af8  mov     [rdi+48h], rsi
0x180007afc  mov     rbx, [rbx]
0x180007aff  mov     al, [rbx+28h]
0x180007b02  mov     [rbx+28h], bpl
0x180007b06  test    al, al
0x180007b08  jnz     short loc_180007B23
0x180007b0a  mov     rcx, [rbx+8]
0x180007b0e  mov     rax, [rcx]
0x180007b11  mov     rdx, rdi
0x180007b14  mov     rax, [rax]
0x180007b17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b1c  or      r14b, al
0x180007b1f  mov     byte ptr [rbx+28h], 0
0x180007b23  mov     rbx, [rbx+10h]
0x180007b27  test    rbx, rbx
0x180007b2a  jnz     short loc_180007AFF
0x180007b2c  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180007b33  test    rax, rax
0x180007b36  jz      short loc_180007B51
0x180007b38  test    r14b, r14b
0x180007b3b  jnz     short loc_180007B45
0x180007b3d  test    byte ptr [rdi+4], 2
0x180007b41  jnz     short loc_180007B45
0x180007b43  xor     ebp, ebp
0x180007b45  mov     rdx, rdi
0x180007b48  mov     cl, bpl
0x180007b4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b50  nop
0x180007b51  add     rsp, 28h
0x180007b55  pop     r15
0x180007b57  pop     r14
0x180007b59  pop     rdi
0x180007b5a  pop     rsi
0x180007b5b  pop     rbp
0x180007b5c  pop     rbx
0x180007b5d  retn
```
