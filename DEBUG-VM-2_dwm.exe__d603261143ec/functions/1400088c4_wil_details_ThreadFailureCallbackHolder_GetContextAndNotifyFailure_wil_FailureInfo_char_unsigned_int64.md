# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1400088c4`
- end: `0x14000897d`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `185`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140008990`

## callees

- `0x1400088c4`
- `0x140008d00`
- `0x140008f14`
- `0x140010010`

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
0x1400088c4  push    rbx
0x1400088c6  push    rbp
0x1400088c7  push    rsi
0x1400088c8  push    rdi
0x1400088c9  push    r14
0x1400088cb  push    r15
0x1400088cd  sub     rsp, 28h
0x1400088d1  xor     r14b, r14b
0x1400088d4  mov     byte ptr [rdx], 0
0x1400088d7  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1400088df  mov     r15, r8
0x1400088e2  mov     rsi, rdx
0x1400088e5  mov     rdi, rcx
0x1400088e8  mov     bpl, 1
0x1400088eb  jz      short loc_14000894C
0x1400088ed  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1400088f2  mov     rbx, rax
0x1400088f5  test    rax, rax
0x1400088f8  jz      short loc_14000894C
0x1400088fa  cmp     qword ptr [rax], 0
0x1400088fe  jz      short loc_14000894C
0x140008900  mov     [rsi], r14b
0x140008903  mov     r9, r15; unsigned __int64
0x140008906  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x140008909  mov     r8, rsi; char *
0x14000890c  mov     rcx, rdi; struct wil::FailureInfo *
0x14000890f  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140008914  test    al, al
0x140008916  jz      short loc_14000891C
0x140008918  mov     [rdi+48h], rsi
0x14000891c  mov     rbx, [rbx]
0x14000891f  mov     al, [rbx+28h]
0x140008922  mov     [rbx+28h], bpl
0x140008926  test    al, al
0x140008928  jnz     short loc_140008943
0x14000892a  mov     rcx, [rbx+8]
0x14000892e  mov     rdx, rdi
0x140008931  mov     rax, [rcx]
0x140008934  mov     rax, [rax]
0x140008937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000893c  or      r14b, al
0x14000893f  mov     byte ptr [rbx+28h], 0
0x140008943  mov     rbx, [rbx+10h]
0x140008947  test    rbx, rbx
0x14000894a  jnz     short loc_14000891F
0x14000894c  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140008953  test    rax, rax
0x140008956  jz      short loc_140008970
0x140008958  test    r14b, r14b
0x14000895b  jnz     short loc_140008965
0x14000895d  test    byte ptr [rdi+4], 2
0x140008961  jnz     short loc_140008965
0x140008963  xor     ebp, ebp
0x140008965  mov     rdx, rdi
0x140008968  mov     cl, bpl
0x14000896b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008970  add     rsp, 28h
0x140008974  pop     r15
0x140008976  pop     r14
0x140008978  pop     rdi
0x140008979  pop     rsi
0x14000897a  pop     rbp
0x14000897b  pop     rbx
0x14000897c  retn
```
