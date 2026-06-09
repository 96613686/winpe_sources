# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180006864`
- end: `0x18000691e`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006930`

## callees

- `0x180006864`
- `0x180006d3c`
- `0x180006f20`
- `0x180012010`

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
0x180006864  push    rbx
0x180006866  push    rbp
0x180006867  push    rsi
0x180006868  push    rdi
0x180006869  push    r14
0x18000686b  push    r15
0x18000686d  sub     rsp, 28h
0x180006871  mov     r15, r8
0x180006874  mov     rsi, rdx
0x180006877  mov     rdi, rcx
0x18000687a  mov     byte ptr [rdx], 0
0x18000687d  xor     r14b, r14b
0x180006880  mov     bpl, 1
0x180006883  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000688b  jz      short loc_1800068EC
0x18000688d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180006892  mov     rbx, rax
0x180006895  test    rax, rax
0x180006898  jz      short loc_1800068EC
0x18000689a  cmp     qword ptr [rax], 0
0x18000689e  jz      short loc_1800068EC
0x1800068a0  mov     [rsi], r14b
0x1800068a3  mov     r9, r15; unsigned __int64
0x1800068a6  mov     r8, rsi; char *
0x1800068a9  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x1800068ac  mov     rcx, rdi; struct wil::FailureInfo *
0x1800068af  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800068b4  test    al, al
0x1800068b6  jz      short loc_1800068BC
0x1800068b8  mov     [rdi+48h], rsi
0x1800068bc  mov     rbx, [rbx]
0x1800068bf  mov     al, [rbx+28h]
0x1800068c2  mov     [rbx+28h], bpl
0x1800068c6  test    al, al
0x1800068c8  jnz     short loc_1800068E3
0x1800068ca  mov     rcx, [rbx+8]
0x1800068ce  mov     rax, [rcx]
0x1800068d1  mov     rdx, rdi
0x1800068d4  mov     rax, [rax]
0x1800068d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068dc  or      r14b, al
0x1800068df  mov     byte ptr [rbx+28h], 0
0x1800068e3  mov     rbx, [rbx+10h]
0x1800068e7  test    rbx, rbx
0x1800068ea  jnz     short loc_1800068BF
0x1800068ec  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800068f3  test    rax, rax
0x1800068f6  jz      short loc_180006911
0x1800068f8  test    r14b, r14b
0x1800068fb  jnz     short loc_180006905
0x1800068fd  test    byte ptr [rdi+4], 2
0x180006901  jnz     short loc_180006905
0x180006903  xor     ebp, ebp
0x180006905  mov     rdx, rdi
0x180006908  mov     cl, bpl
0x18000690b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006910  nop
0x180006911  add     rsp, 28h
0x180006915  pop     r15
0x180006917  pop     r14
0x180006919  pop     rdi
0x18000691a  pop     rsi
0x18000691b  pop     rbp
0x18000691c  pop     rbx
0x18000691d  retn
```
