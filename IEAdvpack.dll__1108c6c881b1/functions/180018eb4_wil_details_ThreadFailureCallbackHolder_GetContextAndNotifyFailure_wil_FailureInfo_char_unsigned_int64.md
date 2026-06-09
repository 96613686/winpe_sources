# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180018eb4`
- end: `0x180018f6d`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `185`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180018f80`

## callees

- `0x180018eb4`
- `0x18001938c`
- `0x1800193e8`
- `0x18001c010`

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
0x180018eb4  push    rbx
0x180018eb6  push    rbp
0x180018eb7  push    rsi
0x180018eb8  push    rdi
0x180018eb9  push    r14
0x180018ebb  push    r15
0x180018ebd  sub     rsp, 28h
0x180018ec1  xor     r14b, r14b
0x180018ec4  mov     byte ptr [rdx], 0
0x180018ec7  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180018ecf  mov     r15, r8
0x180018ed2  mov     rsi, rdx
0x180018ed5  mov     rdi, rcx
0x180018ed8  mov     bpl, 1
0x180018edb  jz      short loc_180018F3C
0x180018edd  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180018ee2  mov     rbx, rax
0x180018ee5  test    rax, rax
0x180018ee8  jz      short loc_180018F3C
0x180018eea  cmp     qword ptr [rax], 0
0x180018eee  jz      short loc_180018F3C
0x180018ef0  mov     [rsi], r14b
0x180018ef3  mov     r9, r15; unsigned __int64
0x180018ef6  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x180018ef9  mov     r8, rsi; char *
0x180018efc  mov     rcx, rdi; struct wil::FailureInfo *
0x180018eff  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180018f04  test    al, al
0x180018f06  jz      short loc_180018F0C
0x180018f08  mov     [rdi+48h], rsi
0x180018f0c  mov     rbx, [rbx]
0x180018f0f  mov     al, [rbx+28h]
0x180018f12  mov     [rbx+28h], bpl
0x180018f16  test    al, al
0x180018f18  jnz     short loc_180018F33
0x180018f1a  mov     rcx, [rbx+8]
0x180018f1e  mov     rdx, rdi
0x180018f21  mov     rax, [rcx]
0x180018f24  mov     rax, [rax]
0x180018f27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f2c  or      r14b, al
0x180018f2f  mov     byte ptr [rbx+28h], 0
0x180018f33  mov     rbx, [rbx+10h]
0x180018f37  test    rbx, rbx
0x180018f3a  jnz     short loc_180018F0F
0x180018f3c  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180018f43  test    rax, rax
0x180018f46  jz      short loc_180018F60
0x180018f48  test    r14b, r14b
0x180018f4b  jnz     short loc_180018F55
0x180018f4d  test    byte ptr [rdi+4], 2
0x180018f51  jnz     short loc_180018F55
0x180018f53  xor     ebp, ebp
0x180018f55  mov     rdx, rdi
0x180018f58  mov     cl, bpl
0x180018f5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f60  add     rsp, 28h
0x180018f64  pop     r15
0x180018f66  pop     r14
0x180018f68  pop     rdi
0x180018f69  pop     rsi
0x180018f6a  pop     rbp
0x180018f6b  pop     rbx
0x180018f6c  retn
```
