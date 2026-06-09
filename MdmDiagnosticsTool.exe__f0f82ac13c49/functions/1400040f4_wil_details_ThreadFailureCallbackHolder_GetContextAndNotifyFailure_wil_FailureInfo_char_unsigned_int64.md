# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1400040f4`
- end: `0x1400041ae`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400041c0`

## callees

- `0x1400040f4`
- `0x1400045cc`
- `0x140004df0`
- `0x14000a010`

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
0x1400040f4  push    rbx
0x1400040f6  push    rbp
0x1400040f7  push    rsi
0x1400040f8  push    rdi
0x1400040f9  push    r14
0x1400040fb  push    r15
0x1400040fd  sub     rsp, 28h
0x140004101  mov     r15, r8
0x140004104  mov     rsi, rdx
0x140004107  mov     rdi, rcx
0x14000410a  mov     byte ptr [rdx], 0
0x14000410d  xor     r14b, r14b
0x140004110  mov     bpl, 1
0x140004113  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14000411b  jz      short loc_14000417C
0x14000411d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x140004122  mov     rbx, rax
0x140004125  test    rax, rax
0x140004128  jz      short loc_14000417C
0x14000412a  cmp     qword ptr [rax], 0
0x14000412e  jz      short loc_14000417C
0x140004130  mov     [rsi], r14b
0x140004133  mov     r9, r15; unsigned __int64
0x140004136  mov     r8, rsi; char *
0x140004139  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x14000413c  mov     rcx, rdi; struct wil::FailureInfo *
0x14000413f  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140004144  test    al, al
0x140004146  jz      short loc_14000414C
0x140004148  mov     [rdi+48h], rsi
0x14000414c  mov     rbx, [rbx]
0x14000414f  mov     al, [rbx+28h]
0x140004152  mov     [rbx+28h], bpl
0x140004156  test    al, al
0x140004158  jnz     short loc_140004173
0x14000415a  mov     rcx, [rbx+8]
0x14000415e  mov     rax, [rcx]
0x140004161  mov     rdx, rdi
0x140004164  mov     rax, [rax]
0x140004167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000416c  or      r14b, al
0x14000416f  mov     byte ptr [rbx+28h], 0
0x140004173  mov     rbx, [rbx+10h]
0x140004177  test    rbx, rbx
0x14000417a  jnz     short loc_14000414F
0x14000417c  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140004183  test    rax, rax
0x140004186  jz      short loc_1400041A1
0x140004188  test    r14b, r14b
0x14000418b  jnz     short loc_140004195
0x14000418d  test    byte ptr [rdi+4], 2
0x140004191  jnz     short loc_140004195
0x140004193  xor     ebp, ebp
0x140004195  mov     rdx, rdi
0x140004198  mov     cl, bpl
0x14000419b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400041a0  nop
0x1400041a1  add     rsp, 28h
0x1400041a5  pop     r15
0x1400041a7  pop     r14
0x1400041a9  pop     rdi
0x1400041aa  pop     rsi
0x1400041ab  pop     rbp
0x1400041ac  pop     rbx
0x1400041ad  retn
```
