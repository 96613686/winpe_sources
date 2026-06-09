# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1400058f4`
- end: `0x1400059b0`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `188`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400059c0`

## callees

- `0x1400058f4`
- `0x140005dcc`
- `0x140005e70`
- `0x14000f010`

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
0x1400058f4  push    rbx
0x1400058f6  push    rbp
0x1400058f7  push    rsi
0x1400058f8  push    rdi
0x1400058f9  push    r14
0x1400058fb  push    r15
0x1400058fd  sub     rsp, 28h
0x140005901  mov     r15, r8
0x140005904  mov     rsi, rdx
0x140005907  mov     rdi, rcx
0x14000590a  mov     byte ptr [rdx], 0
0x14000590d  xor     r14b, r14b
0x140005910  mov     bpl, 1
0x140005913  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14000591b  jz      short loc_14000597E
0x14000591d  xor     edx, edx
0x14000591f  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x140005924  mov     rbx, rax
0x140005927  test    rax, rax
0x14000592a  jz      short loc_14000597E
0x14000592c  cmp     qword ptr [rax], 0
0x140005930  jz      short loc_14000597E
0x140005932  mov     [rsi], r14b
0x140005935  mov     r9, r15; unsigned __int64
0x140005938  mov     r8, rsi; char *
0x14000593b  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x14000593e  mov     rcx, rdi; struct wil::FailureInfo *
0x140005941  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140005946  test    al, al
0x140005948  jz      short loc_14000594E
0x14000594a  mov     [rdi+48h], rsi
0x14000594e  mov     rbx, [rbx]
0x140005951  mov     al, [rbx+28h]
0x140005954  mov     [rbx+28h], bpl
0x140005958  test    al, al
0x14000595a  jnz     short loc_140005975
0x14000595c  mov     rcx, [rbx+8]
0x140005960  mov     rax, [rcx]
0x140005963  mov     rdx, rdi
0x140005966  mov     rax, [rax]
0x140005969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000596e  or      r14b, al
0x140005971  mov     byte ptr [rbx+28h], 0
0x140005975  mov     rbx, [rbx+10h]
0x140005979  test    rbx, rbx
0x14000597c  jnz     short loc_140005951
0x14000597e  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140005985  test    rax, rax
0x140005988  jz      short loc_1400059A3
0x14000598a  test    r14b, r14b
0x14000598d  jnz     short loc_140005997
0x14000598f  test    byte ptr [rdi+4], 2
0x140005993  jnz     short loc_140005997
0x140005995  xor     ebp, ebp
0x140005997  mov     rdx, rdi
0x14000599a  mov     cl, bpl
0x14000599d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400059a2  nop
0x1400059a3  add     rsp, 28h
0x1400059a7  pop     r15
0x1400059a9  pop     r14
0x1400059ab  pop     rdi
0x1400059ac  pop     rsi
0x1400059ad  pop     rbp
0x1400059ae  pop     rbx
0x1400059af  retn
```
