# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140007184`
- end: `0x14000723d`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `185`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140007160`

## callees

- `0x140007184`
- `0x1400073c0`
- `0x14000b9c8`
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
0x140007184  push    rbx
0x140007186  push    rbp
0x140007187  push    rsi
0x140007188  push    rdi
0x140007189  push    r14
0x14000718b  push    r15
0x14000718d  sub     rsp, 28h
0x140007191  xor     r14b, r14b
0x140007194  mov     byte ptr [rdx], 0
0x140007197  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14000719f  mov     r15, r8
0x1400071a2  mov     rsi, rdx
0x1400071a5  mov     rdi, rcx
0x1400071a8  mov     bpl, 1
0x1400071ab  jz      short loc_14000720C
0x1400071ad  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1400071b2  mov     rbx, rax
0x1400071b5  test    rax, rax
0x1400071b8  jz      short loc_14000720C
0x1400071ba  cmp     qword ptr [rax], 0
0x1400071be  jz      short loc_14000720C
0x1400071c0  mov     [rsi], r14b
0x1400071c3  mov     r9, r15; unsigned __int64
0x1400071c6  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x1400071c9  mov     r8, rsi; char *
0x1400071cc  mov     rcx, rdi; struct wil::FailureInfo *
0x1400071cf  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1400071d4  test    al, al
0x1400071d6  jz      short loc_1400071DC
0x1400071d8  mov     [rdi+48h], rsi
0x1400071dc  mov     rbx, [rbx]
0x1400071df  mov     al, [rbx+28h]
0x1400071e2  mov     [rbx+28h], bpl
0x1400071e6  test    al, al
0x1400071e8  jnz     short loc_140007203
0x1400071ea  mov     rcx, [rbx+8]
0x1400071ee  mov     rdx, rdi
0x1400071f1  mov     rax, [rcx]
0x1400071f4  mov     rax, [rax]
0x1400071f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400071fc  or      r14b, al
0x1400071ff  mov     byte ptr [rbx+28h], 0
0x140007203  mov     rbx, [rbx+10h]
0x140007207  test    rbx, rbx
0x14000720a  jnz     short loc_1400071DF
0x14000720c  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140007213  test    rax, rax
0x140007216  jz      short loc_140007230
0x140007218  test    r14b, r14b
0x14000721b  jnz     short loc_140007225
0x14000721d  test    byte ptr [rdi+4], 2
0x140007221  jnz     short loc_140007225
0x140007223  xor     ebp, ebp
0x140007225  mov     rdx, rdi
0x140007228  mov     cl, bpl
0x14000722b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007230  add     rsp, 28h
0x140007234  pop     r15
0x140007236  pop     r14
0x140007238  pop     rdi
0x140007239  pop     rsi
0x14000723a  pop     rbp
0x14000723b  pop     rbx
0x14000723c  retn
```
