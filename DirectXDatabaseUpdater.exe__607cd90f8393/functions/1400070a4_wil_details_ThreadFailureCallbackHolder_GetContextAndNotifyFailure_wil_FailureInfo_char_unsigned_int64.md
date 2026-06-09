# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1400070a4`
- end: `0x140007160`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `188`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140007170`

## callees

- `0x1400070a4`
- `0x14000757c`
- `0x1400077d8`
- `0x14001a010`

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
                                                                   (__int64)a1,
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
0x1400070a4  push    rbx
0x1400070a6  push    rbp
0x1400070a7  push    rsi
0x1400070a8  push    rdi
0x1400070a9  push    r14
0x1400070ab  push    r15
0x1400070ad  sub     rsp, 28h
0x1400070b1  mov     r15, r8
0x1400070b4  mov     rsi, rdx
0x1400070b7  mov     rdi, rcx
0x1400070ba  mov     byte ptr [rdx], 0
0x1400070bd  xor     r14b, r14b
0x1400070c0  mov     bpl, 1
0x1400070c3  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1400070cb  jz      short loc_14000712E
0x1400070cd  xor     edx, edx
0x1400070cf  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1400070d4  mov     rbx, rax
0x1400070d7  test    rax, rax
0x1400070da  jz      short loc_14000712E
0x1400070dc  cmp     qword ptr [rax], 0
0x1400070e0  jz      short loc_14000712E
0x1400070e2  mov     [rsi], r14b
0x1400070e5  mov     r9, r15; unsigned __int64
0x1400070e8  mov     r8, rsi; char *
0x1400070eb  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x1400070ee  mov     rcx, rdi; struct wil::FailureInfo *
0x1400070f1  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1400070f6  test    al, al
0x1400070f8  jz      short loc_1400070FE
0x1400070fa  mov     [rdi+48h], rsi
0x1400070fe  mov     rbx, [rbx]
0x140007101  mov     al, [rbx+28h]
0x140007104  mov     [rbx+28h], bpl
0x140007108  test    al, al
0x14000710a  jnz     short loc_140007125
0x14000710c  mov     rcx, [rbx+8]
0x140007110  mov     rax, [rcx]
0x140007113  mov     rdx, rdi
0x140007116  mov     rax, [rax]
0x140007119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000711e  or      r14b, al
0x140007121  mov     byte ptr [rbx+28h], 0
0x140007125  mov     rbx, [rbx+10h]
0x140007129  test    rbx, rbx
0x14000712c  jnz     short loc_140007101
0x14000712e  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140007135  test    rax, rax
0x140007138  jz      short loc_140007153
0x14000713a  test    r14b, r14b
0x14000713d  jnz     short loc_140007147
0x14000713f  test    byte ptr [rdi+4], 2
0x140007143  jnz     short loc_140007147
0x140007145  xor     ebp, ebp
0x140007147  mov     rdx, rdi
0x14000714a  mov     cl, bpl
0x14000714d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007152  nop
0x140007153  add     rsp, 28h
0x140007157  pop     r15
0x140007159  pop     r14
0x14000715b  pop     rdi
0x14000715c  pop     rsi
0x14000715d  pop     rbp
0x14000715e  pop     rbx
0x14000715f  retn
```
