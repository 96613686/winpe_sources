# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1400043e4`
- end: `0x1400044a7`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `195`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400044b0`

## callees

- `0x1400043e4`
- `0x1400048d4`
- `0x140004a2c`
- `0x14002a010`

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
0x1400043ed  sub     rsp, 38h
0x1400043f1  mov     [rsp+68h+var_48], 0FFFFFFFFFFFFFFFEh
0x1400043fa  mov     r15, r8
0x1400043fd  mov     rsi, rdx
0x140004400  mov     rdi, rcx
0x140004403  mov     byte ptr [rdx], 0
0x140004406  xor     r14b, r14b
0x140004409  mov     bpl, 1
0x14000440c  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140004414  jz      short loc_140004475
0x140004416  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x14000441b  mov     rbx, rax
0x14000441e  test    rax, rax
0x140004421  jz      short loc_140004475
0x140004423  cmp     qword ptr [rax], 0
0x140004427  jz      short loc_140004475
0x140004429  mov     [rsi], r14b
0x14000442c  mov     r9, r15; unsigned __int64
0x14000442f  mov     r8, rsi; char *
0x140004432  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x140004435  mov     rcx, rdi; struct wil::FailureInfo *
0x140004438  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x14000443d  test    al, al
0x14000443f  jz      short loc_140004445
0x140004441  mov     [rdi+48h], rsi
0x140004445  mov     rbx, [rbx]
0x140004448  mov     al, [rbx+28h]
0x14000444b  mov     [rbx+28h], bpl
0x14000444f  test    al, al
0x140004451  jnz     short loc_14000446C
0x140004453  mov     rcx, [rbx+8]
0x140004457  mov     rax, [rcx]
0x14000445a  mov     rdx, rdi
0x14000445d  mov     rax, [rax]
0x140004460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004465  or      r14b, al
0x140004468  mov     byte ptr [rbx+28h], 0
0x14000446c  mov     rbx, [rbx+10h]
0x140004470  test    rbx, rbx
0x140004473  jnz     short loc_140004448
0x140004475  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x14000447c  test    rax, rax
0x14000447f  jz      short loc_14000449A
0x140004481  test    r14b, r14b
0x140004484  jnz     short loc_14000448E
0x140004486  test    byte ptr [rdi+4], 2
0x14000448a  jnz     short loc_14000448E
0x14000448c  xor     ebp, ebp
0x14000448e  mov     rdx, rdi
0x140004491  mov     cl, bpl
0x140004494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004499  nop
0x14000449a  add     rsp, 38h
0x14000449e  pop     r15
0x1400044a0  pop     r14
0x1400044a2  pop     rdi
0x1400044a3  pop     rsi
0x1400044a4  pop     rbp
0x1400044a5  pop     rbx
0x1400044a6  retn
```
