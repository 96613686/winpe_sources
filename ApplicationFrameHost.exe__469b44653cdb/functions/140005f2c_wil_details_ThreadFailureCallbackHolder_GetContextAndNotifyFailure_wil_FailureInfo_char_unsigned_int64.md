# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140005f2c`
- end: `0x140005fe6`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140005ff0`

## callees

- `0x140005f2c`
- `0x140006388`
- `0x14000659c`
- `0x14000b010`

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
0x140005f2c  push    rbx
0x140005f2e  push    rbp
0x140005f2f  push    rsi
0x140005f30  push    rdi
0x140005f31  push    r14
0x140005f33  push    r15
0x140005f35  sub     rsp, 28h
0x140005f39  mov     r15, r8
0x140005f3c  mov     rsi, rdx
0x140005f3f  mov     rdi, rcx
0x140005f42  mov     byte ptr [rdx], 0
0x140005f45  xor     r14b, r14b
0x140005f48  mov     bpl, 1
0x140005f4b  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140005f53  jz      short loc_140005FB4
0x140005f55  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x140005f5a  mov     rbx, rax
0x140005f5d  test    rax, rax
0x140005f60  jz      short loc_140005FB4
0x140005f62  cmp     qword ptr [rax], 0
0x140005f66  jz      short loc_140005FB4
0x140005f68  mov     [rsi], r14b
0x140005f6b  mov     r9, r15; unsigned __int64
0x140005f6e  mov     r8, rsi; char *
0x140005f71  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x140005f74  mov     rcx, rdi; struct wil::FailureInfo *
0x140005f77  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140005f7c  test    al, al
0x140005f7e  jz      short loc_140005F84
0x140005f80  mov     [rdi+48h], rsi
0x140005f84  mov     rbx, [rbx]
0x140005f87  mov     al, [rbx+28h]
0x140005f8a  mov     [rbx+28h], bpl
0x140005f8e  test    al, al
0x140005f90  jnz     short loc_140005FAB
0x140005f92  mov     rcx, [rbx+8]
0x140005f96  mov     rax, [rcx]
0x140005f99  mov     rdx, rdi
0x140005f9c  mov     rax, [rax]
0x140005f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005fa4  or      r14b, al
0x140005fa7  mov     byte ptr [rbx+28h], 0
0x140005fab  mov     rbx, [rbx+10h]
0x140005faf  test    rbx, rbx
0x140005fb2  jnz     short loc_140005F87
0x140005fb4  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140005fbb  test    rax, rax
0x140005fbe  jz      short loc_140005FD9
0x140005fc0  test    r14b, r14b
0x140005fc3  jnz     short loc_140005FCD
0x140005fc5  test    byte ptr [rdi+4], 2
0x140005fc9  jnz     short loc_140005FCD
0x140005fcb  xor     ebp, ebp
0x140005fcd  mov     rdx, rdi
0x140005fd0  mov     cl, bpl
0x140005fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005fd8  nop
0x140005fd9  add     rsp, 28h
0x140005fdd  pop     r15
0x140005fdf  pop     r14
0x140005fe1  pop     rdi
0x140005fe2  pop     rsi
0x140005fe3  pop     rbp
0x140005fe4  pop     rbx
0x140005fe5  retn
```
