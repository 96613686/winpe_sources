# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800036e4`
- end: `0x18000379f`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `187`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800037b0`

## callees

- `0x1800036e4`
- `0x180003be4`
- `0x180003d80`
- `0x180021010`

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
0x1800036e4  push    rbx
0x1800036e6  push    rbp
0x1800036e7  push    rsi
0x1800036e8  push    rdi
0x1800036e9  push    r14
0x1800036eb  push    r15
0x1800036ed  sub     rsp, 28h
0x1800036f1  mov     r15, r8
0x1800036f4  mov     rsi, rdx
0x1800036f7  mov     rdi, rcx
0x1800036fa  mov     byte ptr [rdx], 0
0x1800036fd  xor     r14b, r14b
0x180003700  mov     bpl, 1
0x180003703  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000370b  jz      short loc_18000376C
0x18000370d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180003712  mov     rbx, rax
0x180003715  test    rax, rax
0x180003718  jz      short loc_18000376C
0x18000371a  cmp     qword ptr [rax], 0
0x18000371e  jz      short loc_18000376C
0x180003720  mov     [rsi], r14b
0x180003723  mov     r9, r15; unsigned __int64
0x180003726  mov     r8, rsi; char *
0x180003729  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x18000372c  mov     rcx, rdi; struct wil::FailureInfo *
0x18000372f  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180003734  test    al, al
0x180003736  jz      short loc_18000373C
0x180003738  mov     [rdi+48h], rsi
0x18000373c  mov     rbx, [rbx]
0x18000373f  mov     al, [rbx+28h]
0x180003742  mov     [rbx+28h], bpl
0x180003746  test    al, al
0x180003748  jnz     short loc_180003763
0x18000374a  mov     rcx, [rbx+8]
0x18000374e  mov     rax, [rcx]
0x180003751  mov     rdx, rdi
0x180003754  mov     rax, [rax]
0x180003757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000375c  or      r14b, al
0x18000375f  mov     byte ptr [rbx+28h], 0
0x180003763  mov     rbx, [rbx+10h]
0x180003767  test    rbx, rbx
0x18000376a  jnz     short loc_18000373F
0x18000376c  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180003773  test    rax, rax
0x180003776  jz      short loc_180003791
0x180003778  test    r14b, r14b
0x18000377b  jnz     short loc_180003785
0x18000377d  test    byte ptr [rdi+4], 2
0x180003781  jnz     short loc_180003785
0x180003783  xor     ebp, ebp
0x180003785  mov     rdx, rdi
0x180003788  mov     cl, bpl
0x18000378b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003790  nop
0x180003791  add     rsp, 28h
0x180003795  pop     r15
0x180003797  pop     r14
0x180003799  pop     rdi
0x18000379a  pop     rsi
0x18000379b  pop     rbp
0x18000379c  pop     rbx
0x18000379d  retn
```
