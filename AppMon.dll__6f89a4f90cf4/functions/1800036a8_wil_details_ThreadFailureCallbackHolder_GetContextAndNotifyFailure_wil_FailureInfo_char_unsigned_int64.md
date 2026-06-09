# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800036a8`
- end: `0x180003762`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003770`

## callees

- `0x1800036a8`
- `0x180003b7c`
- `0x180003d04`
- `0x180010010`

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
0x1800036a8  push    rbx
0x1800036aa  push    rbp
0x1800036ab  push    rsi
0x1800036ac  push    rdi
0x1800036ad  push    r14
0x1800036af  push    r15
0x1800036b1  sub     rsp, 28h
0x1800036b5  mov     r15, r8
0x1800036b8  mov     rsi, rdx
0x1800036bb  mov     rdi, rcx
0x1800036be  mov     byte ptr [rdx], 0
0x1800036c1  xor     r14b, r14b
0x1800036c4  mov     bpl, 1
0x1800036c7  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800036cf  jz      short loc_180003730
0x1800036d1  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800036d6  mov     rbx, rax
0x1800036d9  test    rax, rax
0x1800036dc  jz      short loc_180003730
0x1800036de  cmp     qword ptr [rax], 0
0x1800036e2  jz      short loc_180003730
0x1800036e4  mov     [rsi], r14b
0x1800036e7  mov     r9, r15; unsigned __int64
0x1800036ea  mov     r8, rsi; char *
0x1800036ed  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x1800036f0  mov     rcx, rdi; struct wil::FailureInfo *
0x1800036f3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800036f8  test    al, al
0x1800036fa  jz      short loc_180003700
0x1800036fc  mov     [rdi+48h], rsi
0x180003700  mov     rbx, [rbx]
0x180003703  mov     al, [rbx+28h]
0x180003706  mov     [rbx+28h], bpl
0x18000370a  test    al, al
0x18000370c  jnz     short loc_180003727
0x18000370e  mov     rcx, [rbx+8]
0x180003712  mov     rax, [rcx]
0x180003715  mov     rdx, rdi
0x180003718  mov     rax, [rax]
0x18000371b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003720  or      r14b, al
0x180003723  mov     byte ptr [rbx+28h], 0
0x180003727  mov     rbx, [rbx+10h]
0x18000372b  test    rbx, rbx
0x18000372e  jnz     short loc_180003703
0x180003730  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180003737  test    rax, rax
0x18000373a  jz      short loc_180003755
0x18000373c  test    r14b, r14b
0x18000373f  jnz     short loc_180003749
0x180003741  test    byte ptr [rdi+4], 2
0x180003745  jnz     short loc_180003749
0x180003747  xor     ebp, ebp
0x180003749  mov     rdx, rdi
0x18000374c  mov     cl, bpl
0x18000374f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003754  nop
0x180003755  add     rsp, 28h
0x180003759  pop     r15
0x18000375b  pop     r14
0x18000375d  pop     rdi
0x18000375e  pop     rsi
0x18000375f  pop     rbp
0x180003760  pop     rbx
0x180003761  retn
```
