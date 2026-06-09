# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000a328`
- end: `0x18000a3e2`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a3f0`

## callees

- `0x18000a328`
- `0x18000a6b4`
- `0x18000aa3c`
- `0x18001e010`

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
0x18000a328  push    rbx
0x18000a32a  push    rbp
0x18000a32b  push    rsi
0x18000a32c  push    rdi
0x18000a32d  push    r14
0x18000a32f  push    r15
0x18000a331  sub     rsp, 28h
0x18000a335  xor     r14b, r14b
0x18000a338  mov     byte ptr [rdx], 0
0x18000a33b  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000a343  mov     r15, r8
0x18000a346  mov     rsi, rdx
0x18000a349  mov     rdi, rcx
0x18000a34c  mov     bpl, 1
0x18000a34f  jz      short loc_18000A3B0
0x18000a351  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000a356  mov     rbx, rax
0x18000a359  test    rax, rax
0x18000a35c  jz      short loc_18000A3B0
0x18000a35e  cmp     qword ptr [rax], 0
0x18000a362  jz      short loc_18000A3B0
0x18000a364  mov     [rsi], r14b
0x18000a367  mov     r9, r15; unsigned __int64
0x18000a36a  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x18000a36d  mov     r8, rsi; char *
0x18000a370  mov     rcx, rdi; struct wil::FailureInfo *
0x18000a373  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000a378  test    al, al
0x18000a37a  jz      short loc_18000A380
0x18000a37c  mov     [rdi+48h], rsi
0x18000a380  mov     rbx, [rbx]
0x18000a383  mov     al, [rbx+28h]
0x18000a386  mov     [rbx+28h], bpl
0x18000a38a  test    al, al
0x18000a38c  jnz     short loc_18000A3A7
0x18000a38e  mov     rcx, [rbx+8]
0x18000a392  mov     rdx, rdi
0x18000a395  mov     rax, [rcx]
0x18000a398  mov     rax, [rax]
0x18000a39b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3a0  or      r14b, al
0x18000a3a3  mov     byte ptr [rbx+28h], 0
0x18000a3a7  mov     rbx, [rbx+10h]
0x18000a3ab  test    rbx, rbx
0x18000a3ae  jnz     short loc_18000A383
0x18000a3b0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000a3b7  test    rax, rax
0x18000a3ba  jz      short loc_18000A3D4
0x18000a3bc  test    r14b, r14b
0x18000a3bf  jnz     short loc_18000A3C9
0x18000a3c1  test    byte ptr [rdi+4], 2
0x18000a3c5  jnz     short loc_18000A3C9
0x18000a3c7  xor     ebp, ebp
0x18000a3c9  mov     rdx, rdi
0x18000a3cc  mov     cl, bpl
0x18000a3cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3d4  add     rsp, 28h
0x18000a3d8  pop     r15
0x18000a3da  pop     r14
0x18000a3dc  pop     rdi
0x18000a3dd  pop     rsi
0x18000a3de  pop     rbp
0x18000a3df  pop     rbx
0x18000a3e0  retn
```
