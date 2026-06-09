# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140004354`
- end: `0x14000440f`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `187`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140004420`

## callees

- `0x140004354`
- `0x140004854`
- `0x140005080`
- `0x14000b010`

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
0x140004354  push    rbx
0x140004356  push    rbp
0x140004357  push    rsi
0x140004358  push    rdi
0x140004359  push    r14
0x14000435b  push    r15
0x14000435d  sub     rsp, 28h
0x140004361  mov     r15, r8
0x140004364  mov     rsi, rdx
0x140004367  mov     rdi, rcx
0x14000436a  mov     byte ptr [rdx], 0
0x14000436d  xor     r14b, r14b
0x140004370  mov     bpl, 1
0x140004373  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14000437b  jz      short loc_1400043DC
0x14000437d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x140004382  mov     rbx, rax
0x140004385  test    rax, rax
0x140004388  jz      short loc_1400043DC
0x14000438a  cmp     qword ptr [rax], 0
0x14000438e  jz      short loc_1400043DC
0x140004390  mov     [rsi], r14b
0x140004393  mov     r9, r15; unsigned __int64
0x140004396  mov     r8, rsi; char *
0x140004399  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x14000439c  mov     rcx, rdi; struct wil::FailureInfo *
0x14000439f  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1400043a4  test    al, al
0x1400043a6  jz      short loc_1400043AC
0x1400043a8  mov     [rdi+48h], rsi
0x1400043ac  mov     rbx, [rbx]
0x1400043af  mov     al, [rbx+28h]
0x1400043b2  mov     [rbx+28h], bpl
0x1400043b6  test    al, al
0x1400043b8  jnz     short loc_1400043D3
0x1400043ba  mov     rcx, [rbx+8]
0x1400043be  mov     rax, [rcx]
0x1400043c1  mov     rdx, rdi
0x1400043c4  mov     rax, [rax]
0x1400043c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400043cc  or      r14b, al
0x1400043cf  mov     byte ptr [rbx+28h], 0
0x1400043d3  mov     rbx, [rbx+10h]
0x1400043d7  test    rbx, rbx
0x1400043da  jnz     short loc_1400043AF
0x1400043dc  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1400043e3  test    rax, rax
0x1400043e6  jz      short loc_140004401
0x1400043e8  test    r14b, r14b
0x1400043eb  jnz     short loc_1400043F5
0x1400043ed  test    byte ptr [rdi+4], 2
0x1400043f1  jnz     short loc_1400043F5
0x1400043f3  xor     ebp, ebp
0x1400043f5  mov     rdx, rdi
0x1400043f8  mov     cl, bpl
0x1400043fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004400  nop
0x140004401  add     rsp, 28h
0x140004405  pop     r15
0x140004407  pop     r14
0x140004409  pop     rdi
0x14000440a  pop     rsi
0x14000440b  pop     rbp
0x14000440c  pop     rbx
0x14000440d  retn
```
