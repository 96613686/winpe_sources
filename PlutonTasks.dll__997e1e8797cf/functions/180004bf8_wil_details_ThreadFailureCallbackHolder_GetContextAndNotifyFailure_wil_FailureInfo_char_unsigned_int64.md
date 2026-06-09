# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004bf8`
- end: `0x180004cb4`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `188`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004cc0`

## callees

- `0x180004bf8`
- `0x1800050cc`
- `0x1800052d0`
- `0x18000a010`

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
0x180004bf8  push    rbx
0x180004bfa  push    rbp
0x180004bfb  push    rsi
0x180004bfc  push    rdi
0x180004bfd  push    r14
0x180004bff  push    r15
0x180004c01  sub     rsp, 28h
0x180004c05  mov     r15, r8
0x180004c08  mov     rsi, rdx
0x180004c0b  mov     rdi, rcx
0x180004c0e  mov     byte ptr [rdx], 0
0x180004c11  xor     r14b, r14b
0x180004c14  mov     bpl, 1
0x180004c17  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004c1f  jz      short loc_180004C82
0x180004c21  xor     edx, edx
0x180004c23  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180004c28  mov     rbx, rax
0x180004c2b  test    rax, rax
0x180004c2e  jz      short loc_180004C82
0x180004c30  cmp     qword ptr [rax], 0
0x180004c34  jz      short loc_180004C82
0x180004c36  mov     [rsi], r14b
0x180004c39  mov     r9, r15; unsigned __int64
0x180004c3c  mov     r8, rsi; char *
0x180004c3f  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x180004c42  mov     rcx, rdi; struct wil::FailureInfo *
0x180004c45  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004c4a  test    al, al
0x180004c4c  jz      short loc_180004C52
0x180004c4e  mov     [rdi+48h], rsi
0x180004c52  mov     rbx, [rbx]
0x180004c55  mov     al, [rbx+28h]
0x180004c58  mov     [rbx+28h], bpl
0x180004c5c  test    al, al
0x180004c5e  jnz     short loc_180004C79
0x180004c60  mov     rcx, [rbx+8]
0x180004c64  mov     rax, [rcx]
0x180004c67  mov     rdx, rdi
0x180004c6a  mov     rax, [rax]
0x180004c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c72  or      r14b, al
0x180004c75  mov     byte ptr [rbx+28h], 0
0x180004c79  mov     rbx, [rbx+10h]
0x180004c7d  test    rbx, rbx
0x180004c80  jnz     short loc_180004C55
0x180004c82  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004c89  test    rax, rax
0x180004c8c  jz      short loc_180004CA7
0x180004c8e  test    r14b, r14b
0x180004c91  jnz     short loc_180004C9B
0x180004c93  test    byte ptr [rdi+4], 2
0x180004c97  jnz     short loc_180004C9B
0x180004c99  xor     ebp, ebp
0x180004c9b  mov     rdx, rdi
0x180004c9e  mov     cl, bpl
0x180004ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ca6  nop
0x180004ca7  add     rsp, 28h
0x180004cab  pop     r15
0x180004cad  pop     r14
0x180004caf  pop     rdi
0x180004cb0  pop     rsi
0x180004cb1  pop     rbp
0x180004cb2  pop     rbx
0x180004cb3  retn
```
