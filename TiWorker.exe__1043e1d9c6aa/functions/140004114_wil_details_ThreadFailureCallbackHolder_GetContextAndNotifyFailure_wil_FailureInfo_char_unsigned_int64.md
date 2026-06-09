# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140004114`
- end: `0x1400041cd`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `185`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400041e0`

## callees

- `0x140004114`
- `0x1400045ec`
- `0x140004774`
- `0x14002b010`

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
0x140004114  push    rbx
0x140004116  push    rbp
0x140004117  push    rsi
0x140004118  push    rdi
0x140004119  push    r14
0x14000411b  push    r15
0x14000411d  sub     rsp, 28h
0x140004121  xor     r14b, r14b
0x140004124  mov     byte ptr [rdx], 0
0x140004127  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14000412f  mov     r15, r8
0x140004132  mov     rsi, rdx
0x140004135  mov     rdi, rcx
0x140004138  mov     bpl, 1
0x14000413b  jz      short loc_14000419C
0x14000413d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x140004142  mov     rbx, rax
0x140004145  test    rax, rax
0x140004148  jz      short loc_14000419C
0x14000414a  cmp     qword ptr [rax], 0
0x14000414e  jz      short loc_14000419C
0x140004150  mov     [rsi], r14b
0x140004153  mov     r9, r15; unsigned __int64
0x140004156  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x140004159  mov     r8, rsi; char *
0x14000415c  mov     rcx, rdi; struct wil::FailureInfo *
0x14000415f  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140004164  test    al, al
0x140004166  jz      short loc_14000416C
0x140004168  mov     [rdi+48h], rsi
0x14000416c  mov     rbx, [rbx]
0x14000416f  mov     al, [rbx+28h]
0x140004172  mov     [rbx+28h], bpl
0x140004176  test    al, al
0x140004178  jnz     short loc_140004193
0x14000417a  mov     rcx, [rbx+8]
0x14000417e  mov     rdx, rdi
0x140004181  mov     rax, [rcx]
0x140004184  mov     rax, [rax]
0x140004187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000418c  or      r14b, al
0x14000418f  mov     byte ptr [rbx+28h], 0
0x140004193  mov     rbx, [rbx+10h]
0x140004197  test    rbx, rbx
0x14000419a  jnz     short loc_14000416F
0x14000419c  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1400041a3  test    rax, rax
0x1400041a6  jz      short loc_1400041C0
0x1400041a8  test    r14b, r14b
0x1400041ab  jnz     short loc_1400041B5
0x1400041ad  test    byte ptr [rdi+4], 2
0x1400041b1  jnz     short loc_1400041B5
0x1400041b3  xor     ebp, ebp
0x1400041b5  mov     rdx, rdi
0x1400041b8  mov     cl, bpl
0x1400041bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400041c0  add     rsp, 28h
0x1400041c4  pop     r15
0x1400041c6  pop     r14
0x1400041c8  pop     rdi
0x1400041c9  pop     rsi
0x1400041ca  pop     rbp
0x1400041cb  pop     rbx
0x1400041cc  retn
```
