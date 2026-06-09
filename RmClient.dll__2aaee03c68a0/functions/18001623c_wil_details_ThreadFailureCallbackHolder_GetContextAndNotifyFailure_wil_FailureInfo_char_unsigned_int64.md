# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18001623c`
- end: `0x1800162f5`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `185`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180016300`

## callees

- `0x18001623c`
- `0x180016670`
- `0x1800167f8`
- `0x18001c010`

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
0x18001623c  push    rbx
0x18001623e  push    rbp
0x18001623f  push    rsi
0x180016240  push    rdi
0x180016241  push    r14
0x180016243  push    r15
0x180016245  sub     rsp, 28h
0x180016249  xor     r14b, r14b
0x18001624c  mov     byte ptr [rdx], 0
0x18001624f  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180016257  mov     r15, r8
0x18001625a  mov     rsi, rdx
0x18001625d  mov     rdi, rcx
0x180016260  mov     bpl, 1
0x180016263  jz      short loc_1800162C4
0x180016265  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18001626a  mov     rbx, rax
0x18001626d  test    rax, rax
0x180016270  jz      short loc_1800162C4
0x180016272  cmp     qword ptr [rax], 0
0x180016276  jz      short loc_1800162C4
0x180016278  mov     [rsi], r14b
0x18001627b  mov     r9, r15; unsigned __int64
0x18001627e  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x180016281  mov     r8, rsi; char *
0x180016284  mov     rcx, rdi; struct wil::FailureInfo *
0x180016287  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18001628c  test    al, al
0x18001628e  jz      short loc_180016294
0x180016290  mov     [rdi+48h], rsi
0x180016294  mov     rbx, [rbx]
0x180016297  mov     al, [rbx+28h]
0x18001629a  mov     [rbx+28h], bpl
0x18001629e  test    al, al
0x1800162a0  jnz     short loc_1800162BB
0x1800162a2  mov     rcx, [rbx+8]
0x1800162a6  mov     rdx, rdi
0x1800162a9  mov     rax, [rcx]
0x1800162ac  mov     rax, [rax]
0x1800162af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162b4  or      r14b, al
0x1800162b7  mov     byte ptr [rbx+28h], 0
0x1800162bb  mov     rbx, [rbx+10h]
0x1800162bf  test    rbx, rbx
0x1800162c2  jnz     short loc_180016297
0x1800162c4  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800162cb  test    rax, rax
0x1800162ce  jz      short loc_1800162E8
0x1800162d0  test    r14b, r14b
0x1800162d3  jnz     short loc_1800162DD
0x1800162d5  test    byte ptr [rdi+4], 2
0x1800162d9  jnz     short loc_1800162DD
0x1800162db  xor     ebp, ebp
0x1800162dd  mov     rdx, rdi
0x1800162e0  mov     cl, bpl
0x1800162e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162e8  add     rsp, 28h
0x1800162ec  pop     r15
0x1800162ee  pop     r14
0x1800162f0  pop     rdi
0x1800162f1  pop     rsi
0x1800162f2  pop     rbp
0x1800162f3  pop     rbx
0x1800162f4  retn
```
