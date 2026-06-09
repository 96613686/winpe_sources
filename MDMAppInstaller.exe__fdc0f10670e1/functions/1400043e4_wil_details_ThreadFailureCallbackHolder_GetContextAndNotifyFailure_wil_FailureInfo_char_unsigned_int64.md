# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1400043e4`
- end: `0x14000449e`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400044b0`

## callees

- `0x1400043e4`
- `0x1400048bc`
- `0x140004a44`
- `0x14001c010`

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
0x1400043e4  push    rbx
0x1400043e6  push    rbp
0x1400043e7  push    rsi
0x1400043e8  push    rdi
0x1400043e9  push    r14
0x1400043eb  push    r15
0x1400043ed  sub     rsp, 28h
0x1400043f1  mov     r15, r8
0x1400043f4  mov     rsi, rdx
0x1400043f7  mov     rdi, rcx
0x1400043fa  mov     byte ptr [rdx], 0
0x1400043fd  xor     r14b, r14b
0x140004400  mov     bpl, 1
0x140004403  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14000440b  jz      short loc_14000446C
0x14000440d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x140004412  mov     rbx, rax
0x140004415  test    rax, rax
0x140004418  jz      short loc_14000446C
0x14000441a  cmp     qword ptr [rax], 0
0x14000441e  jz      short loc_14000446C
0x140004420  mov     [rsi], r14b
0x140004423  mov     r9, r15; unsigned __int64
0x140004426  mov     r8, rsi; char *
0x140004429  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x14000442c  mov     rcx, rdi; struct wil::FailureInfo *
0x14000442f  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140004434  test    al, al
0x140004436  jz      short loc_14000443C
0x140004438  mov     [rdi+48h], rsi
0x14000443c  mov     rbx, [rbx]
0x14000443f  mov     al, [rbx+28h]
0x140004442  mov     [rbx+28h], bpl
0x140004446  test    al, al
0x140004448  jnz     short loc_140004463
0x14000444a  mov     rcx, [rbx+8]
0x14000444e  mov     rax, [rcx]
0x140004451  mov     rdx, rdi
0x140004454  mov     rax, [rax]
0x140004457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000445c  or      r14b, al
0x14000445f  mov     byte ptr [rbx+28h], 0
0x140004463  mov     rbx, [rbx+10h]
0x140004467  test    rbx, rbx
0x14000446a  jnz     short loc_14000443F
0x14000446c  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140004473  test    rax, rax
0x140004476  jz      short loc_140004491
0x140004478  test    r14b, r14b
0x14000447b  jnz     short loc_140004485
0x14000447d  test    byte ptr [rdi+4], 2
0x140004481  jnz     short loc_140004485
0x140004483  xor     ebp, ebp
0x140004485  mov     rdx, rdi
0x140004488  mov     cl, bpl
0x14000448b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004490  nop
0x140004491  add     rsp, 28h
0x140004495  pop     r15
0x140004497  pop     r14
0x140004499  pop     rdi
0x14000449a  pop     rsi
0x14000449b  pop     rbp
0x14000449c  pop     rbx
0x14000449d  retn
```
