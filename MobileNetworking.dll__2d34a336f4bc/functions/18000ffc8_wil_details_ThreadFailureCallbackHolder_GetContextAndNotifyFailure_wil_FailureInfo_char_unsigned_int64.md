# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000ffc8`
- end: `0x180010081`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `185`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180010090`

## callees

- `0x18000ffc8`
- `0x1800103b8`
- `0x1800104dc`
- `0x180012010`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(
        struct wil::FailureInfo *a1,
        char *a2,
        unsigned __int64 a3)
{
  char v3; // r14
  struct wil::FailureInfo *v6; // rdi
  char v7; // bp
  struct wil::details::ThreadFailureCallbackHolder **Local; // rax
  struct wil::details::ThreadFailureCallbackHolder **v9; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v10; // rbx
  char v11; // al

  v3 = 0;
  *a2 = 0;
  v6 = a1;
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
        if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(v6, *Local, a2, a3) )
          *((_QWORD *)v6 + 9) = a2;
        v10 = *v9;
        do
        {
          v11 = *((_BYTE *)v10 + 40);
          *((_BYTE *)v10 + 40) = 1;
          if ( !v11 )
          {
            v3 |= (***((__int64 (__fastcall ****)(_QWORD, struct wil::FailureInfo *))v10 + 1))(*((_QWORD *)v10 + 1), v6);
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
    if ( !v3 && (*((_BYTE *)v6 + 4) & 2) == 0 )
      v7 = 0;
    LOBYTE(a1) = v7;
    wil::details::g_pfnTelemetryCallback(a1, v6);
  }
}

```

## disassembly

```asm
0x18000ffc8  push    rbx
0x18000ffca  push    rbp
0x18000ffcb  push    rsi
0x18000ffcc  push    rdi
0x18000ffcd  push    r14
0x18000ffcf  push    r15
0x18000ffd1  sub     rsp, 28h
0x18000ffd5  xor     r14b, r14b
0x18000ffd8  mov     byte ptr [rdx], 0
0x18000ffdb  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000ffe3  mov     r15, r8
0x18000ffe6  mov     rsi, rdx
0x18000ffe9  mov     rdi, rcx
0x18000ffec  mov     bpl, 1
0x18000ffef  jz      short loc_180010050
0x18000fff1  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000fff6  mov     rbx, rax
0x18000fff9  test    rax, rax
0x18000fffc  jz      short loc_180010050
0x18000fffe  cmp     qword ptr [rax], 0
0x180010002  jz      short loc_180010050
0x180010004  mov     [rsi], r14b
0x180010007  mov     r9, r15; unsigned __int64
0x18001000a  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x18001000d  mov     r8, rsi; char *
0x180010010  mov     rcx, rdi; struct wil::FailureInfo *
0x180010013  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180010018  test    al, al
0x18001001a  jz      short loc_180010020
0x18001001c  mov     [rdi+48h], rsi
0x180010020  mov     rbx, [rbx]
0x180010023  mov     al, [rbx+28h]
0x180010026  mov     [rbx+28h], bpl
0x18001002a  test    al, al
0x18001002c  jnz     short loc_180010047
0x18001002e  mov     rcx, [rbx+8]
0x180010032  mov     rdx, rdi
0x180010035  mov     rax, [rcx]
0x180010038  mov     rax, [rax]
0x18001003b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010040  or      r14b, al
0x180010043  mov     byte ptr [rbx+28h], 0
0x180010047  mov     rbx, [rbx+10h]
0x18001004b  test    rbx, rbx
0x18001004e  jnz     short loc_180010023
0x180010050  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180010057  test    rax, rax
0x18001005a  jz      short loc_180010074
0x18001005c  test    r14b, r14b
0x18001005f  jnz     short loc_180010069
0x180010061  test    byte ptr [rdi+4], 2
0x180010065  jnz     short loc_180010069
0x180010067  xor     ebp, ebp
0x180010069  mov     rdx, rdi
0x18001006c  mov     cl, bpl
0x18001006f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010074  add     rsp, 28h
0x180010078  pop     r15
0x18001007a  pop     r14
0x18001007c  pop     rdi
0x18001007d  pop     rsi
0x18001007e  pop     rbp
0x18001007f  pop     rbx
0x180010080  retn
```
