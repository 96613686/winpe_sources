# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140002dd4`
- end: `0x140002e8d`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `185`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140002ea0`

## callees

- `0x140002dd4`
- `0x1400032ac`
- `0x140003434`
- `0x140006010`

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
0x140002dd4  push    rbx
0x140002dd6  push    rbp
0x140002dd7  push    rsi
0x140002dd8  push    rdi
0x140002dd9  push    r14
0x140002ddb  push    r15
0x140002ddd  sub     rsp, 28h
0x140002de1  xor     r14b, r14b
0x140002de4  mov     byte ptr [rdx], 0
0x140002de7  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140002def  mov     r15, r8
0x140002df2  mov     rsi, rdx
0x140002df5  mov     rdi, rcx
0x140002df8  mov     bpl, 1
0x140002dfb  jz      short loc_140002E5C
0x140002dfd  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x140002e02  mov     rbx, rax
0x140002e05  test    rax, rax
0x140002e08  jz      short loc_140002E5C
0x140002e0a  cmp     qword ptr [rax], 0
0x140002e0e  jz      short loc_140002E5C
0x140002e10  mov     [rsi], r14b
0x140002e13  mov     r9, r15; unsigned __int64
0x140002e16  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x140002e19  mov     r8, rsi; char *
0x140002e1c  mov     rcx, rdi; struct wil::FailureInfo *
0x140002e1f  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140002e24  test    al, al
0x140002e26  jz      short loc_140002E2C
0x140002e28  mov     [rdi+48h], rsi
0x140002e2c  mov     rbx, [rbx]
0x140002e2f  mov     al, [rbx+28h]
0x140002e32  mov     [rbx+28h], bpl
0x140002e36  test    al, al
0x140002e38  jnz     short loc_140002E53
0x140002e3a  mov     rcx, [rbx+8]
0x140002e3e  mov     rdx, rdi
0x140002e41  mov     rax, [rcx]
0x140002e44  mov     rax, [rax]
0x140002e47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002e4c  or      r14b, al
0x140002e4f  mov     byte ptr [rbx+28h], 0
0x140002e53  mov     rbx, [rbx+10h]
0x140002e57  test    rbx, rbx
0x140002e5a  jnz     short loc_140002E2F
0x140002e5c  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140002e63  test    rax, rax
0x140002e66  jz      short loc_140002E80
0x140002e68  test    r14b, r14b
0x140002e6b  jnz     short loc_140002E75
0x140002e6d  test    byte ptr [rdi+4], 2
0x140002e71  jnz     short loc_140002E75
0x140002e73  xor     ebp, ebp
0x140002e75  mov     rdx, rdi
0x140002e78  mov     cl, bpl
0x140002e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002e80  add     rsp, 28h
0x140002e84  pop     r15
0x140002e86  pop     r14
0x140002e88  pop     rdi
0x140002e89  pop     rsi
0x140002e8a  pop     rbp
0x140002e8b  pop     rbx
0x140002e8c  retn
```
