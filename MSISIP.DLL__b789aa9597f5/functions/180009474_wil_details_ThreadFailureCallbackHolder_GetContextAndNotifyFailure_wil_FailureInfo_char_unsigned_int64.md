# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180009474`
- end: `0x180009537`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `195`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180009450`

## callees

- `0x180009474`
- `0x18000b38c`
- `0x18000b53c`
- `0x18000e010`

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
0x180009474  push    rbx
0x180009476  push    rbp
0x180009477  push    rsi
0x180009478  push    rdi
0x180009479  push    r14
0x18000947b  push    r15
0x18000947d  sub     rsp, 38h
0x180009481  mov     [rsp+68h+var_48], 0FFFFFFFFFFFFFFFEh
0x18000948a  mov     r15, r8
0x18000948d  mov     rsi, rdx
0x180009490  mov     rdi, rcx
0x180009493  mov     byte ptr [rdx], 0
0x180009496  xor     r14b, r14b
0x180009499  mov     bpl, 1
0x18000949c  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800094a4  jz      short loc_180009505
0x1800094a6  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800094ab  mov     rbx, rax
0x1800094ae  test    rax, rax
0x1800094b1  jz      short loc_180009505
0x1800094b3  cmp     qword ptr [rax], 0
0x1800094b7  jz      short loc_180009505
0x1800094b9  mov     [rsi], r14b
0x1800094bc  mov     r9, r15; unsigned __int64
0x1800094bf  mov     r8, rsi; char *
0x1800094c2  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x1800094c5  mov     rcx, rdi; struct wil::FailureInfo *
0x1800094c8  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800094cd  test    al, al
0x1800094cf  jz      short loc_1800094D5
0x1800094d1  mov     [rdi+48h], rsi
0x1800094d5  mov     rbx, [rbx]
0x1800094d8  mov     al, [rbx+28h]
0x1800094db  mov     [rbx+28h], bpl
0x1800094df  test    al, al
0x1800094e1  jnz     short loc_1800094FC
0x1800094e3  mov     rcx, [rbx+8]
0x1800094e7  mov     rax, [rcx]
0x1800094ea  mov     rdx, rdi
0x1800094ed  mov     rax, [rax]
0x1800094f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094f5  or      r14b, al
0x1800094f8  mov     byte ptr [rbx+28h], 0
0x1800094fc  mov     rbx, [rbx+10h]
0x180009500  test    rbx, rbx
0x180009503  jnz     short loc_1800094D8
0x180009505  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000950c  test    rax, rax
0x18000950f  jz      short loc_18000952A
0x180009511  test    r14b, r14b
0x180009514  jnz     short loc_18000951E
0x180009516  test    byte ptr [rdi+4], 2
0x18000951a  jnz     short loc_18000951E
0x18000951c  xor     ebp, ebp
0x18000951e  mov     rdx, rdi
0x180009521  mov     cl, bpl
0x180009524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009529  nop
0x18000952a  add     rsp, 38h
0x18000952e  pop     r15
0x180009530  pop     r14
0x180009532  pop     rdi
0x180009533  pop     rsi
0x180009534  pop     rbp
0x180009535  pop     rbx
0x180009536  retn
```
