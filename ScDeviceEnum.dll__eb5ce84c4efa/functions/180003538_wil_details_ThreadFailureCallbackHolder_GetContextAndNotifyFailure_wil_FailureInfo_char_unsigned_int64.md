# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180003538`
- end: `0x1800035f2`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003600`

## callees

- `0x180003538`
- `0x180003a0c`
- `0x180003b94`
- `0x180020010`

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
0x180003538  push    rbx
0x18000353a  push    rbp
0x18000353b  push    rsi
0x18000353c  push    rdi
0x18000353d  push    r14
0x18000353f  push    r15
0x180003541  sub     rsp, 28h
0x180003545  mov     r15, r8
0x180003548  mov     rsi, rdx
0x18000354b  mov     rdi, rcx
0x18000354e  mov     byte ptr [rdx], 0
0x180003551  xor     r14b, r14b
0x180003554  mov     bpl, 1
0x180003557  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000355f  jz      short loc_1800035C0
0x180003561  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180003566  mov     rbx, rax
0x180003569  test    rax, rax
0x18000356c  jz      short loc_1800035C0
0x18000356e  cmp     qword ptr [rax], 0
0x180003572  jz      short loc_1800035C0
0x180003574  mov     [rsi], r14b
0x180003577  mov     r9, r15; unsigned __int64
0x18000357a  mov     r8, rsi; char *
0x18000357d  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x180003580  mov     rcx, rdi; struct wil::FailureInfo *
0x180003583  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180003588  test    al, al
0x18000358a  jz      short loc_180003590
0x18000358c  mov     [rdi+48h], rsi
0x180003590  mov     rbx, [rbx]
0x180003593  mov     al, [rbx+28h]
0x180003596  mov     [rbx+28h], bpl
0x18000359a  test    al, al
0x18000359c  jnz     short loc_1800035B7
0x18000359e  mov     rcx, [rbx+8]
0x1800035a2  mov     rax, [rcx]
0x1800035a5  mov     rdx, rdi
0x1800035a8  mov     rax, [rax]
0x1800035ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035b0  or      r14b, al
0x1800035b3  mov     byte ptr [rbx+28h], 0
0x1800035b7  mov     rbx, [rbx+10h]
0x1800035bb  test    rbx, rbx
0x1800035be  jnz     short loc_180003593
0x1800035c0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800035c7  test    rax, rax
0x1800035ca  jz      short loc_1800035E5
0x1800035cc  test    r14b, r14b
0x1800035cf  jnz     short loc_1800035D9
0x1800035d1  test    byte ptr [rdi+4], 2
0x1800035d5  jnz     short loc_1800035D9
0x1800035d7  xor     ebp, ebp
0x1800035d9  mov     rdx, rdi
0x1800035dc  mov     cl, bpl
0x1800035df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035e4  nop
0x1800035e5  add     rsp, 28h
0x1800035e9  pop     r15
0x1800035eb  pop     r14
0x1800035ed  pop     rdi
0x1800035ee  pop     rsi
0x1800035ef  pop     rbp
0x1800035f0  pop     rbx
0x1800035f1  retn
```
