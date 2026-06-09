# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140005234`
- end: `0x1400052f0`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `188`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140005300`

## callees

- `0x140005234`
- `0x14000576c`
- `0x14000593c`
- `0x140012010`

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
                                                                   a1,
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
0x140005234  push    rbx
0x140005236  push    rbp
0x140005237  push    rsi
0x140005238  push    rdi
0x140005239  push    r14
0x14000523b  push    r15
0x14000523d  sub     rsp, 28h
0x140005241  mov     r15, r8
0x140005244  mov     rsi, rdx
0x140005247  mov     rdi, rcx
0x14000524a  mov     byte ptr [rdx], 0
0x14000524d  xor     r14b, r14b
0x140005250  mov     bpl, 1
0x140005253  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14000525b  jz      short loc_1400052BE
0x14000525d  xor     edx, edx
0x14000525f  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x140005264  mov     rbx, rax
0x140005267  test    rax, rax
0x14000526a  jz      short loc_1400052BE
0x14000526c  cmp     qword ptr [rax], 0
0x140005270  jz      short loc_1400052BE
0x140005272  mov     [rsi], r14b
0x140005275  mov     r9, r15; unsigned __int64
0x140005278  mov     r8, rsi; char *
0x14000527b  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x14000527e  mov     rcx, rdi; struct wil::FailureInfo *
0x140005281  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140005286  test    al, al
0x140005288  jz      short loc_14000528E
0x14000528a  mov     [rdi+48h], rsi
0x14000528e  mov     rbx, [rbx]
0x140005291  mov     al, [rbx+28h]
0x140005294  mov     [rbx+28h], bpl
0x140005298  test    al, al
0x14000529a  jnz     short loc_1400052B5
0x14000529c  mov     rcx, [rbx+8]
0x1400052a0  mov     rax, [rcx]
0x1400052a3  mov     rdx, rdi
0x1400052a6  mov     rax, [rax]
0x1400052a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400052ae  or      r14b, al
0x1400052b1  mov     byte ptr [rbx+28h], 0
0x1400052b5  mov     rbx, [rbx+10h]
0x1400052b9  test    rbx, rbx
0x1400052bc  jnz     short loc_140005291
0x1400052be  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1400052c5  test    rax, rax
0x1400052c8  jz      short loc_1400052E3
0x1400052ca  test    r14b, r14b
0x1400052cd  jnz     short loc_1400052D7
0x1400052cf  test    byte ptr [rdi+4], 2
0x1400052d3  jnz     short loc_1400052D7
0x1400052d5  xor     ebp, ebp
0x1400052d7  mov     rdx, rdi
0x1400052da  mov     cl, bpl
0x1400052dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400052e2  nop
0x1400052e3  add     rsp, 28h
0x1400052e7  pop     r15
0x1400052e9  pop     r14
0x1400052eb  pop     rdi
0x1400052ec  pop     rsi
0x1400052ed  pop     rbp
0x1400052ee  pop     rbx
0x1400052ef  retn
```
