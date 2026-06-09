# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180005b54`
- end: `0x180005c0e`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005c20`

## callees

- `0x180005b54`
- `0x18000680c`
- `0x180006a20`
- `0x180011010`

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
0x180005b54  push    rbx
0x180005b56  push    rbp
0x180005b57  push    rsi
0x180005b58  push    rdi
0x180005b59  push    r14
0x180005b5b  push    r15
0x180005b5d  sub     rsp, 28h
0x180005b61  mov     r15, r8
0x180005b64  mov     rsi, rdx
0x180005b67  mov     rdi, rcx
0x180005b6a  mov     byte ptr [rdx], 0
0x180005b6d  xor     r14b, r14b
0x180005b70  mov     bpl, 1
0x180005b73  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005b7b  jz      short loc_180005BDC
0x180005b7d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180005b82  mov     rbx, rax
0x180005b85  test    rax, rax
0x180005b88  jz      short loc_180005BDC
0x180005b8a  cmp     qword ptr [rax], 0
0x180005b8e  jz      short loc_180005BDC
0x180005b90  mov     [rsi], r14b
0x180005b93  mov     r9, r15; unsigned __int64
0x180005b96  mov     r8, rsi; char *
0x180005b99  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x180005b9c  mov     rcx, rdi; struct wil::FailureInfo *
0x180005b9f  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005ba4  test    al, al
0x180005ba6  jz      short loc_180005BAC
0x180005ba8  mov     [rdi+48h], rsi
0x180005bac  mov     rbx, [rbx]
0x180005baf  mov     al, [rbx+28h]
0x180005bb2  mov     [rbx+28h], bpl
0x180005bb6  test    al, al
0x180005bb8  jnz     short loc_180005BD3
0x180005bba  mov     rcx, [rbx+8]
0x180005bbe  mov     rax, [rcx]
0x180005bc1  mov     rdx, rdi
0x180005bc4  mov     rax, [rax]
0x180005bc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bcc  or      r14b, al
0x180005bcf  mov     byte ptr [rbx+28h], 0
0x180005bd3  mov     rbx, [rbx+10h]
0x180005bd7  test    rbx, rbx
0x180005bda  jnz     short loc_180005BAF
0x180005bdc  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180005be3  test    rax, rax
0x180005be6  jz      short loc_180005C01
0x180005be8  test    r14b, r14b
0x180005beb  jnz     short loc_180005BF5
0x180005bed  test    byte ptr [rdi+4], 2
0x180005bf1  jnz     short loc_180005BF5
0x180005bf3  xor     ebp, ebp
0x180005bf5  mov     rdx, rdi
0x180005bf8  mov     cl, bpl
0x180005bfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c00  nop
0x180005c01  add     rsp, 28h
0x180005c05  pop     r15
0x180005c07  pop     r14
0x180005c09  pop     rdi
0x180005c0a  pop     rsi
0x180005c0b  pop     rbp
0x180005c0c  pop     rbx
0x180005c0d  retn
```
