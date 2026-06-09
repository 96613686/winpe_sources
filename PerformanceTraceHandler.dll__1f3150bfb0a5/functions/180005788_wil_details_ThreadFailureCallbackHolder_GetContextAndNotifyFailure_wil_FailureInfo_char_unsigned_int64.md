# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180005788`
- end: `0x180005844`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `188`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005850`

## callees

- `0x180005788`
- `0x180005c5c`
- `0x180005e60`
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
0x180005788  push    rbx
0x18000578a  push    rbp
0x18000578b  push    rsi
0x18000578c  push    rdi
0x18000578d  push    r14
0x18000578f  push    r15
0x180005791  sub     rsp, 28h
0x180005795  mov     r15, r8
0x180005798  mov     rsi, rdx
0x18000579b  mov     rdi, rcx
0x18000579e  mov     byte ptr [rdx], 0
0x1800057a1  xor     r14b, r14b
0x1800057a4  mov     bpl, 1
0x1800057a7  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800057af  jz      short loc_180005812
0x1800057b1  xor     edx, edx
0x1800057b3  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800057b8  mov     rbx, rax
0x1800057bb  test    rax, rax
0x1800057be  jz      short loc_180005812
0x1800057c0  cmp     qword ptr [rax], 0
0x1800057c4  jz      short loc_180005812
0x1800057c6  mov     [rsi], r14b
0x1800057c9  mov     r9, r15; unsigned __int64
0x1800057cc  mov     r8, rsi; char *
0x1800057cf  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x1800057d2  mov     rcx, rdi; struct wil::FailureInfo *
0x1800057d5  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800057da  test    al, al
0x1800057dc  jz      short loc_1800057E2
0x1800057de  mov     [rdi+48h], rsi
0x1800057e2  mov     rbx, [rbx]
0x1800057e5  mov     al, [rbx+28h]
0x1800057e8  mov     [rbx+28h], bpl
0x1800057ec  test    al, al
0x1800057ee  jnz     short loc_180005809
0x1800057f0  mov     rcx, [rbx+8]
0x1800057f4  mov     rax, [rcx]
0x1800057f7  mov     rdx, rdi
0x1800057fa  mov     rax, [rax]
0x1800057fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005802  or      r14b, al
0x180005805  mov     byte ptr [rbx+28h], 0
0x180005809  mov     rbx, [rbx+10h]
0x18000580d  test    rbx, rbx
0x180005810  jnz     short loc_1800057E5
0x180005812  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180005819  test    rax, rax
0x18000581c  jz      short loc_180005837
0x18000581e  test    r14b, r14b
0x180005821  jnz     short loc_18000582B
0x180005823  test    byte ptr [rdi+4], 2
0x180005827  jnz     short loc_18000582B
0x180005829  xor     ebp, ebp
0x18000582b  mov     rdx, rdi
0x18000582e  mov     cl, bpl
0x180005831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005836  nop
0x180005837  add     rsp, 28h
0x18000583b  pop     r15
0x18000583d  pop     r14
0x18000583f  pop     rdi
0x180005840  pop     rsi
0x180005841  pop     rbp
0x180005842  pop     rbx
0x180005843  retn
```
