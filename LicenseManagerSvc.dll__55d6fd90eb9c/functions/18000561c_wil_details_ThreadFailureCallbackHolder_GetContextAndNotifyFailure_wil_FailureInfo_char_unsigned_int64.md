# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000561c`
- end: `0x1800056d6`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800056e0`

## callees

- `0x18000561c`
- `0x180005a50`
- `0x180005bd8`
- `0x180018010`

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
0x18000561c  push    rbx
0x18000561e  push    rbp
0x18000561f  push    rsi
0x180005620  push    rdi
0x180005621  push    r14
0x180005623  push    r15
0x180005625  sub     rsp, 28h
0x180005629  mov     r15, r8
0x18000562c  mov     rsi, rdx
0x18000562f  mov     rdi, rcx
0x180005632  mov     byte ptr [rdx], 0
0x180005635  xor     r14b, r14b
0x180005638  mov     bpl, 1
0x18000563b  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005643  jz      short loc_1800056A4
0x180005645  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000564a  mov     rbx, rax
0x18000564d  test    rax, rax
0x180005650  jz      short loc_1800056A4
0x180005652  cmp     qword ptr [rax], 0
0x180005656  jz      short loc_1800056A4
0x180005658  mov     [rsi], r14b
0x18000565b  mov     r9, r15; unsigned __int64
0x18000565e  mov     r8, rsi; char *
0x180005661  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x180005664  mov     rcx, rdi; struct wil::FailureInfo *
0x180005667  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000566c  test    al, al
0x18000566e  jz      short loc_180005674
0x180005670  mov     [rdi+48h], rsi
0x180005674  mov     rbx, [rbx]
0x180005677  mov     al, [rbx+28h]
0x18000567a  mov     [rbx+28h], bpl
0x18000567e  test    al, al
0x180005680  jnz     short loc_18000569B
0x180005682  mov     rcx, [rbx+8]
0x180005686  mov     rax, [rcx]
0x180005689  mov     rdx, rdi
0x18000568c  mov     rax, [rax]
0x18000568f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005694  or      r14b, al
0x180005697  mov     byte ptr [rbx+28h], 0
0x18000569b  mov     rbx, [rbx+10h]
0x18000569f  test    rbx, rbx
0x1800056a2  jnz     short loc_180005677
0x1800056a4  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800056ab  test    rax, rax
0x1800056ae  jz      short loc_1800056C9
0x1800056b0  test    r14b, r14b
0x1800056b3  jnz     short loc_1800056BD
0x1800056b5  test    byte ptr [rdi+4], 2
0x1800056b9  jnz     short loc_1800056BD
0x1800056bb  xor     ebp, ebp
0x1800056bd  mov     rdx, rdi
0x1800056c0  mov     cl, bpl
0x1800056c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056c8  nop
0x1800056c9  add     rsp, 28h
0x1800056cd  pop     r15
0x1800056cf  pop     r14
0x1800056d1  pop     rdi
0x1800056d2  pop     rsi
0x1800056d3  pop     rbp
0x1800056d4  pop     rbx
0x1800056d5  retn
```
