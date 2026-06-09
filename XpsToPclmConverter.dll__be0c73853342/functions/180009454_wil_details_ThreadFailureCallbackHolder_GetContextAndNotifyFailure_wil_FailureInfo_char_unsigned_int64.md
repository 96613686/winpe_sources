# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180009454`
- end: `0x18000950e`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180009520`

## callees

- `0x180009454`
- `0x18000992c`
- `0x180009b40`
- `0x18001f010`

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
0x180009454  push    rbx
0x180009456  push    rbp
0x180009457  push    rsi
0x180009458  push    rdi
0x180009459  push    r14
0x18000945b  push    r15
0x18000945d  sub     rsp, 28h
0x180009461  mov     r15, r8
0x180009464  mov     rsi, rdx
0x180009467  mov     rdi, rcx
0x18000946a  mov     byte ptr [rdx], 0
0x18000946d  xor     r14b, r14b
0x180009470  mov     bpl, 1
0x180009473  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000947b  jz      short loc_1800094DC
0x18000947d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180009482  mov     rbx, rax
0x180009485  test    rax, rax
0x180009488  jz      short loc_1800094DC
0x18000948a  cmp     qword ptr [rax], 0
0x18000948e  jz      short loc_1800094DC
0x180009490  mov     [rsi], r14b
0x180009493  mov     r9, r15; unsigned __int64
0x180009496  mov     r8, rsi; char *
0x180009499  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x18000949c  mov     rcx, rdi; struct wil::FailureInfo *
0x18000949f  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800094a4  test    al, al
0x1800094a6  jz      short loc_1800094AC
0x1800094a8  mov     [rdi+48h], rsi
0x1800094ac  mov     rbx, [rbx]
0x1800094af  mov     al, [rbx+28h]
0x1800094b2  mov     [rbx+28h], bpl
0x1800094b6  test    al, al
0x1800094b8  jnz     short loc_1800094D3
0x1800094ba  mov     rcx, [rbx+8]
0x1800094be  mov     rax, [rcx]
0x1800094c1  mov     rdx, rdi
0x1800094c4  mov     rax, [rax]
0x1800094c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094cc  or      r14b, al
0x1800094cf  mov     byte ptr [rbx+28h], 0
0x1800094d3  mov     rbx, [rbx+10h]
0x1800094d7  test    rbx, rbx
0x1800094da  jnz     short loc_1800094AF
0x1800094dc  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800094e3  test    rax, rax
0x1800094e6  jz      short loc_180009501
0x1800094e8  test    r14b, r14b
0x1800094eb  jnz     short loc_1800094F5
0x1800094ed  test    byte ptr [rdi+4], 2
0x1800094f1  jnz     short loc_1800094F5
0x1800094f3  xor     ebp, ebp
0x1800094f5  mov     rdx, rdi
0x1800094f8  mov     cl, bpl
0x1800094fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009500  nop
0x180009501  add     rsp, 28h
0x180009505  pop     r15
0x180009507  pop     r14
0x180009509  pop     rdi
0x18000950a  pop     rsi
0x18000950b  pop     rbp
0x18000950c  pop     rbx
0x18000950d  retn
```
