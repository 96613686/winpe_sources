# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180003764`
- end: `0x18000381f`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `187`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003830`

## callees

- `0x180003764`
- `0x180003c64`
- `0x180003e00`
- `0x18000b010`

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
0x180003764  push    rbx
0x180003766  push    rbp
0x180003767  push    rsi
0x180003768  push    rdi
0x180003769  push    r14
0x18000376b  push    r15
0x18000376d  sub     rsp, 28h
0x180003771  mov     r15, r8
0x180003774  mov     rsi, rdx
0x180003777  mov     rdi, rcx
0x18000377a  mov     byte ptr [rdx], 0
0x18000377d  xor     r14b, r14b
0x180003780  mov     bpl, 1
0x180003783  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000378b  jz      short loc_1800037EC
0x18000378d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180003792  mov     rbx, rax
0x180003795  test    rax, rax
0x180003798  jz      short loc_1800037EC
0x18000379a  cmp     qword ptr [rax], 0
0x18000379e  jz      short loc_1800037EC
0x1800037a0  mov     [rsi], r14b
0x1800037a3  mov     r9, r15; unsigned __int64
0x1800037a6  mov     r8, rsi; char *
0x1800037a9  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x1800037ac  mov     rcx, rdi; struct wil::FailureInfo *
0x1800037af  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800037b4  test    al, al
0x1800037b6  jz      short loc_1800037BC
0x1800037b8  mov     [rdi+48h], rsi
0x1800037bc  mov     rbx, [rbx]
0x1800037bf  mov     al, [rbx+28h]
0x1800037c2  mov     [rbx+28h], bpl
0x1800037c6  test    al, al
0x1800037c8  jnz     short loc_1800037E3
0x1800037ca  mov     rcx, [rbx+8]
0x1800037ce  mov     rax, [rcx]
0x1800037d1  mov     rdx, rdi
0x1800037d4  mov     rax, [rax]
0x1800037d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037dc  or      r14b, al
0x1800037df  mov     byte ptr [rbx+28h], 0
0x1800037e3  mov     rbx, [rbx+10h]
0x1800037e7  test    rbx, rbx
0x1800037ea  jnz     short loc_1800037BF
0x1800037ec  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800037f3  test    rax, rax
0x1800037f6  jz      short loc_180003811
0x1800037f8  test    r14b, r14b
0x1800037fb  jnz     short loc_180003805
0x1800037fd  test    byte ptr [rdi+4], 2
0x180003801  jnz     short loc_180003805
0x180003803  xor     ebp, ebp
0x180003805  mov     rdx, rdi
0x180003808  mov     cl, bpl
0x18000380b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003810  nop
0x180003811  add     rsp, 28h
0x180003815  pop     r15
0x180003817  pop     r14
0x180003819  pop     rdi
0x18000381a  pop     rsi
0x18000381b  pop     rbp
0x18000381c  pop     rbx
0x18000381d  retn
```
