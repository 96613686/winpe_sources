# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1400053a4`
- end: `0x140005461`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `189`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140005470`

## callees

- `0x1400053a4`
- `0x1400058a4`
- `0x140005b98`
- `0x14001a010`

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
                                                                   (__int64)a1,
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
0x1400053a4  push    rbx
0x1400053a6  push    rbp
0x1400053a7  push    rsi
0x1400053a8  push    rdi
0x1400053a9  push    r14
0x1400053ab  push    r15
0x1400053ad  sub     rsp, 28h
0x1400053b1  mov     r15, r8
0x1400053b4  mov     rsi, rdx
0x1400053b7  mov     rdi, rcx
0x1400053ba  mov     byte ptr [rdx], 0
0x1400053bd  xor     r14b, r14b
0x1400053c0  mov     bpl, 1
0x1400053c3  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1400053cb  jz      short loc_14000542E
0x1400053cd  xor     edx, edx
0x1400053cf  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1400053d4  mov     rbx, rax
0x1400053d7  test    rax, rax
0x1400053da  jz      short loc_14000542E
0x1400053dc  cmp     qword ptr [rax], 0
0x1400053e0  jz      short loc_14000542E
0x1400053e2  mov     [rsi], r14b
0x1400053e5  mov     r9, r15; unsigned __int64
0x1400053e8  mov     r8, rsi; char *
0x1400053eb  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x1400053ee  mov     rcx, rdi; struct wil::FailureInfo *
0x1400053f1  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1400053f6  test    al, al
0x1400053f8  jz      short loc_1400053FE
0x1400053fa  mov     [rdi+48h], rsi
0x1400053fe  mov     rbx, [rbx]
0x140005401  mov     al, [rbx+28h]
0x140005404  mov     [rbx+28h], bpl
0x140005408  test    al, al
0x14000540a  jnz     short loc_140005425
0x14000540c  mov     rcx, [rbx+8]
0x140005410  mov     rax, [rcx]
0x140005413  mov     rdx, rdi
0x140005416  mov     rax, [rax]
0x140005419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000541e  or      r14b, al
0x140005421  mov     byte ptr [rbx+28h], 0
0x140005425  mov     rbx, [rbx+10h]
0x140005429  test    rbx, rbx
0x14000542c  jnz     short loc_140005401
0x14000542e  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140005435  test    rax, rax
0x140005438  jz      short loc_140005453
0x14000543a  test    r14b, r14b
0x14000543d  jnz     short loc_140005447
0x14000543f  test    byte ptr [rdi+4], 2
0x140005443  jnz     short loc_140005447
0x140005445  xor     ebp, ebp
0x140005447  mov     rdx, rdi
0x14000544a  mov     cl, bpl
0x14000544d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005452  nop
0x140005453  add     rsp, 28h
0x140005457  pop     r15
0x140005459  pop     r14
0x14000545b  pop     rdi
0x14000545c  pop     rsi
0x14000545d  pop     rbp
0x14000545e  pop     rbx
0x14000545f  retn
```
