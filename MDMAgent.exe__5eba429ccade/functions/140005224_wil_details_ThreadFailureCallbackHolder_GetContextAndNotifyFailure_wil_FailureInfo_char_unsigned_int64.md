# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140005224`
- end: `0x1400052e0`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `188`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400052f0`

## callees

- `0x140005224`
- `0x1400056fc`
- `0x1400059d0`
- `0x140019010`

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
0x140005224  push    rbx
0x140005226  push    rbp
0x140005227  push    rsi
0x140005228  push    rdi
0x140005229  push    r14
0x14000522b  push    r15
0x14000522d  sub     rsp, 28h
0x140005231  mov     r15, r8
0x140005234  mov     rsi, rdx
0x140005237  mov     rdi, rcx
0x14000523a  mov     byte ptr [rdx], 0
0x14000523d  xor     r14b, r14b
0x140005240  mov     bpl, 1
0x140005243  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14000524b  jz      short loc_1400052AE
0x14000524d  xor     edx, edx
0x14000524f  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x140005254  mov     rbx, rax
0x140005257  test    rax, rax
0x14000525a  jz      short loc_1400052AE
0x14000525c  cmp     qword ptr [rax], 0
0x140005260  jz      short loc_1400052AE
0x140005262  mov     [rsi], r14b
0x140005265  mov     r9, r15; unsigned __int64
0x140005268  mov     r8, rsi; char *
0x14000526b  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x14000526e  mov     rcx, rdi; struct wil::FailureInfo *
0x140005271  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140005276  test    al, al
0x140005278  jz      short loc_14000527E
0x14000527a  mov     [rdi+48h], rsi
0x14000527e  mov     rbx, [rbx]
0x140005281  mov     al, [rbx+28h]
0x140005284  mov     [rbx+28h], bpl
0x140005288  test    al, al
0x14000528a  jnz     short loc_1400052A5
0x14000528c  mov     rcx, [rbx+8]
0x140005290  mov     rax, [rcx]
0x140005293  mov     rdx, rdi
0x140005296  mov     rax, [rax]
0x140005299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000529e  or      r14b, al
0x1400052a1  mov     byte ptr [rbx+28h], 0
0x1400052a5  mov     rbx, [rbx+10h]
0x1400052a9  test    rbx, rbx
0x1400052ac  jnz     short loc_140005281
0x1400052ae  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1400052b5  test    rax, rax
0x1400052b8  jz      short loc_1400052D3
0x1400052ba  test    r14b, r14b
0x1400052bd  jnz     short loc_1400052C7
0x1400052bf  test    byte ptr [rdi+4], 2
0x1400052c3  jnz     short loc_1400052C7
0x1400052c5  xor     ebp, ebp
0x1400052c7  mov     rdx, rdi
0x1400052ca  mov     cl, bpl
0x1400052cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400052d2  nop
0x1400052d3  add     rsp, 28h
0x1400052d7  pop     r15
0x1400052d9  pop     r14
0x1400052db  pop     rdi
0x1400052dc  pop     rsi
0x1400052dd  pop     rbp
0x1400052de  pop     rbx
0x1400052df  retn
```
