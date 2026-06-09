# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800054a4`
- end: `0x180005560`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `188`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005570`

## callees

- `0x1800054a4`
- `0x180005988`
- `0x180005b58`
- `0x18001c010`

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
0x1800054a4  push    rbx
0x1800054a6  push    rbp
0x1800054a7  push    rsi
0x1800054a8  push    rdi
0x1800054a9  push    r14
0x1800054ab  push    r15
0x1800054ad  sub     rsp, 28h
0x1800054b1  mov     r15, r8
0x1800054b4  mov     rsi, rdx
0x1800054b7  mov     rdi, rcx
0x1800054ba  mov     byte ptr [rdx], 0
0x1800054bd  xor     r14b, r14b
0x1800054c0  mov     bpl, 1
0x1800054c3  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800054cb  jz      short loc_18000552E
0x1800054cd  xor     edx, edx
0x1800054cf  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800054d4  mov     rbx, rax
0x1800054d7  test    rax, rax
0x1800054da  jz      short loc_18000552E
0x1800054dc  cmp     qword ptr [rax], 0
0x1800054e0  jz      short loc_18000552E
0x1800054e2  mov     [rsi], r14b
0x1800054e5  mov     r9, r15; unsigned __int64
0x1800054e8  mov     r8, rsi; char *
0x1800054eb  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x1800054ee  mov     rcx, rdi; struct wil::FailureInfo *
0x1800054f1  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800054f6  test    al, al
0x1800054f8  jz      short loc_1800054FE
0x1800054fa  mov     [rdi+48h], rsi
0x1800054fe  mov     rbx, [rbx]
0x180005501  mov     al, [rbx+28h]
0x180005504  mov     [rbx+28h], bpl
0x180005508  test    al, al
0x18000550a  jnz     short loc_180005525
0x18000550c  mov     rcx, [rbx+8]
0x180005510  mov     rax, [rcx]
0x180005513  mov     rdx, rdi
0x180005516  mov     rax, [rax]
0x180005519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000551e  or      r14b, al
0x180005521  mov     byte ptr [rbx+28h], 0
0x180005525  mov     rbx, [rbx+10h]
0x180005529  test    rbx, rbx
0x18000552c  jnz     short loc_180005501
0x18000552e  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180005535  test    rax, rax
0x180005538  jz      short loc_180005553
0x18000553a  test    r14b, r14b
0x18000553d  jnz     short loc_180005547
0x18000553f  test    byte ptr [rdi+4], 2
0x180005543  jnz     short loc_180005547
0x180005545  xor     ebp, ebp
0x180005547  mov     rdx, rdi
0x18000554a  mov     cl, bpl
0x18000554d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005552  nop
0x180005553  add     rsp, 28h
0x180005557  pop     r15
0x180005559  pop     r14
0x18000555b  pop     rdi
0x18000555c  pop     rsi
0x18000555d  pop     rbp
0x18000555e  pop     rbx
0x18000555f  retn
```
