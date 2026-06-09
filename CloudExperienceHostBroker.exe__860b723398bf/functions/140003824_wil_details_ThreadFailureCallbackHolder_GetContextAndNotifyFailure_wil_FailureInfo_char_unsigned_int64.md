# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140003824`
- end: `0x1400038de`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400038f0`

## callees

- `0x140003824`
- `0x140003cfc`
- `0x140003e84`
- `0x14000a010`

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
0x140003824  push    rbx
0x140003826  push    rbp
0x140003827  push    rsi
0x140003828  push    rdi
0x140003829  push    r14
0x14000382b  push    r15
0x14000382d  sub     rsp, 28h
0x140003831  mov     r15, r8
0x140003834  mov     rsi, rdx
0x140003837  mov     rdi, rcx
0x14000383a  mov     byte ptr [rdx], 0
0x14000383d  xor     r14b, r14b
0x140003840  mov     bpl, 1
0x140003843  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14000384b  jz      short loc_1400038AC
0x14000384d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x140003852  mov     rbx, rax
0x140003855  test    rax, rax
0x140003858  jz      short loc_1400038AC
0x14000385a  cmp     qword ptr [rax], 0
0x14000385e  jz      short loc_1400038AC
0x140003860  mov     [rsi], r14b
0x140003863  mov     r9, r15; unsigned __int64
0x140003866  mov     r8, rsi; char *
0x140003869  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x14000386c  mov     rcx, rdi; struct wil::FailureInfo *
0x14000386f  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140003874  test    al, al
0x140003876  jz      short loc_14000387C
0x140003878  mov     [rdi+48h], rsi
0x14000387c  mov     rbx, [rbx]
0x14000387f  mov     al, [rbx+28h]
0x140003882  mov     [rbx+28h], bpl
0x140003886  test    al, al
0x140003888  jnz     short loc_1400038A3
0x14000388a  mov     rcx, [rbx+8]
0x14000388e  mov     rax, [rcx]
0x140003891  mov     rdx, rdi
0x140003894  mov     rax, [rax]
0x140003897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000389c  or      r14b, al
0x14000389f  mov     byte ptr [rbx+28h], 0
0x1400038a3  mov     rbx, [rbx+10h]
0x1400038a7  test    rbx, rbx
0x1400038aa  jnz     short loc_14000387F
0x1400038ac  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1400038b3  test    rax, rax
0x1400038b6  jz      short loc_1400038D1
0x1400038b8  test    r14b, r14b
0x1400038bb  jnz     short loc_1400038C5
0x1400038bd  test    byte ptr [rdi+4], 2
0x1400038c1  jnz     short loc_1400038C5
0x1400038c3  xor     ebp, ebp
0x1400038c5  mov     rdx, rdi
0x1400038c8  mov     cl, bpl
0x1400038cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400038d0  nop
0x1400038d1  add     rsp, 28h
0x1400038d5  pop     r15
0x1400038d7  pop     r14
0x1400038d9  pop     rdi
0x1400038da  pop     rsi
0x1400038db  pop     rbp
0x1400038dc  pop     rbx
0x1400038dd  retn
```
