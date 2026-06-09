# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180005280`
- end: `0x180005339`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `185`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005340`

## callees

- `0x180005280`
- `0x18000574c`
- `0x1800058a4`
- `0x18000c010`

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
0x180005280  push    rbx
0x180005282  push    rbp
0x180005283  push    rsi
0x180005284  push    rdi
0x180005285  push    r14
0x180005287  push    r15
0x180005289  sub     rsp, 28h
0x18000528d  xor     r14b, r14b
0x180005290  mov     byte ptr [rdx], 0
0x180005293  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000529b  mov     r15, r8
0x18000529e  mov     rsi, rdx
0x1800052a1  mov     rdi, rcx
0x1800052a4  mov     bpl, 1
0x1800052a7  jz      short loc_180005308
0x1800052a9  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800052ae  mov     rbx, rax
0x1800052b1  test    rax, rax
0x1800052b4  jz      short loc_180005308
0x1800052b6  cmp     qword ptr [rax], 0
0x1800052ba  jz      short loc_180005308
0x1800052bc  mov     [rsi], r14b
0x1800052bf  mov     r9, r15; unsigned __int64
0x1800052c2  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x1800052c5  mov     r8, rsi; char *
0x1800052c8  mov     rcx, rdi; struct wil::FailureInfo *
0x1800052cb  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800052d0  test    al, al
0x1800052d2  jz      short loc_1800052D8
0x1800052d4  mov     [rdi+48h], rsi
0x1800052d8  mov     rbx, [rbx]
0x1800052db  mov     al, [rbx+28h]
0x1800052de  mov     [rbx+28h], bpl
0x1800052e2  test    al, al
0x1800052e4  jnz     short loc_1800052FF
0x1800052e6  mov     rcx, [rbx+8]
0x1800052ea  mov     rdx, rdi
0x1800052ed  mov     rax, [rcx]
0x1800052f0  mov     rax, [rax]
0x1800052f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052f8  or      r14b, al
0x1800052fb  mov     byte ptr [rbx+28h], 0
0x1800052ff  mov     rbx, [rbx+10h]
0x180005303  test    rbx, rbx
0x180005306  jnz     short loc_1800052DB
0x180005308  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000530f  test    rax, rax
0x180005312  jz      short loc_18000532C
0x180005314  test    r14b, r14b
0x180005317  jnz     short loc_180005321
0x180005319  test    byte ptr [rdi+4], 2
0x18000531d  jnz     short loc_180005321
0x18000531f  xor     ebp, ebp
0x180005321  mov     rdx, rdi
0x180005324  mov     cl, bpl
0x180005327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000532c  add     rsp, 28h
0x180005330  pop     r15
0x180005332  pop     r14
0x180005334  pop     rdi
0x180005335  pop     rsi
0x180005336  pop     rbp
0x180005337  pop     rbx
0x180005338  retn
```
