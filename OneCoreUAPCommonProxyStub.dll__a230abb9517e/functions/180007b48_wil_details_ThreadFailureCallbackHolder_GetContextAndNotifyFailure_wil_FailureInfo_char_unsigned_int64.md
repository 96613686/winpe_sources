# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180007b48`
- end: `0x180007c04`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `188`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007c10`

## callees

- `0x180002ab8`
- `0x180007b48`
- `0x180008148`
- `0x18000c010`

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
    Local = (struct wil::details::ThreadFailureCallbackHolder **)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                                                                   (__int64)a1,
                                                                   0);
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
0x180007b48  push    rbx
0x180007b4a  push    rbp
0x180007b4b  push    rsi
0x180007b4c  push    rdi
0x180007b4d  push    r14
0x180007b4f  push    r15
0x180007b51  sub     rsp, 28h
0x180007b55  mov     r15, r8
0x180007b58  mov     rsi, rdx
0x180007b5b  mov     rdi, rcx
0x180007b5e  mov     byte ptr [rdx], 0
0x180007b61  xor     r14b, r14b
0x180007b64  mov     bpl, 1
0x180007b67  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180007b6f  jz      short loc_180007BD2
0x180007b71  xor     edx, edx
0x180007b73  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180007b78  mov     rbx, rax
0x180007b7b  test    rax, rax
0x180007b7e  jz      short loc_180007BD2
0x180007b80  cmp     qword ptr [rax], 0
0x180007b84  jz      short loc_180007BD2
0x180007b86  mov     [rsi], r14b
0x180007b89  mov     r9, r15; unsigned __int64
0x180007b8c  mov     r8, rsi; char *
0x180007b8f  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x180007b92  mov     rcx, rdi; struct wil::FailureInfo *
0x180007b95  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180007b9a  test    al, al
0x180007b9c  jz      short loc_180007BA2
0x180007b9e  mov     [rdi+48h], rsi
0x180007ba2  mov     rbx, [rbx]
0x180007ba5  mov     al, [rbx+28h]
0x180007ba8  mov     [rbx+28h], bpl
0x180007bac  test    al, al
0x180007bae  jnz     short loc_180007BC9
0x180007bb0  mov     rcx, [rbx+8]
0x180007bb4  mov     rax, [rcx]
0x180007bb7  mov     rdx, rdi
0x180007bba  mov     rax, [rax]
0x180007bbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bc2  or      r14b, al
0x180007bc5  mov     byte ptr [rbx+28h], 0
0x180007bc9  mov     rbx, [rbx+10h]
0x180007bcd  test    rbx, rbx
0x180007bd0  jnz     short loc_180007BA5
0x180007bd2  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180007bd9  test    rax, rax
0x180007bdc  jz      short loc_180007BF7
0x180007bde  test    r14b, r14b
0x180007be1  jnz     short loc_180007BEB
0x180007be3  test    byte ptr [rdi+4], 2
0x180007be7  jnz     short loc_180007BEB
0x180007be9  xor     ebp, ebp
0x180007beb  mov     rdx, rdi
0x180007bee  mov     cl, bpl
0x180007bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bf6  nop
0x180007bf7  add     rsp, 28h
0x180007bfb  pop     r15
0x180007bfd  pop     r14
0x180007bff  pop     rdi
0x180007c00  pop     rsi
0x180007c01  pop     rbp
0x180007c02  pop     rbx
0x180007c03  retn
```
