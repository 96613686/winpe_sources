# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180010ff4`
- end: `0x1800110ad`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `185`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800110c0`

## callees

- `0x180010ff4`
- `0x1800114cc`
- `0x180011688`
- `0x180029010`

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
0x180010ff4  push    rbx
0x180010ff6  push    rbp
0x180010ff7  push    rsi
0x180010ff8  push    rdi
0x180010ff9  push    r14
0x180010ffb  push    r15
0x180010ffd  sub     rsp, 28h
0x180011001  xor     r14b, r14b
0x180011004  mov     byte ptr [rdx], 0
0x180011007  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001100f  mov     r15, r8
0x180011012  mov     rsi, rdx
0x180011015  mov     rdi, rcx
0x180011018  mov     bpl, 1
0x18001101b  jz      short loc_18001107C
0x18001101d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180011022  mov     rbx, rax
0x180011025  test    rax, rax
0x180011028  jz      short loc_18001107C
0x18001102a  cmp     qword ptr [rax], 0
0x18001102e  jz      short loc_18001107C
0x180011030  mov     [rsi], r14b
0x180011033  mov     r9, r15; unsigned __int64
0x180011036  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x180011039  mov     r8, rsi; char *
0x18001103c  mov     rcx, rdi; struct wil::FailureInfo *
0x18001103f  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180011044  test    al, al
0x180011046  jz      short loc_18001104C
0x180011048  mov     [rdi+48h], rsi
0x18001104c  mov     rbx, [rbx]
0x18001104f  mov     al, [rbx+28h]
0x180011052  mov     [rbx+28h], bpl
0x180011056  test    al, al
0x180011058  jnz     short loc_180011073
0x18001105a  mov     rcx, [rbx+8]
0x18001105e  mov     rdx, rdi
0x180011061  mov     rax, [rcx]
0x180011064  mov     rax, [rax]
0x180011067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001106c  or      r14b, al
0x18001106f  mov     byte ptr [rbx+28h], 0
0x180011073  mov     rbx, [rbx+10h]
0x180011077  test    rbx, rbx
0x18001107a  jnz     short loc_18001104F
0x18001107c  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180011083  test    rax, rax
0x180011086  jz      short loc_1800110A0
0x180011088  test    r14b, r14b
0x18001108b  jnz     short loc_180011095
0x18001108d  test    byte ptr [rdi+4], 2
0x180011091  jnz     short loc_180011095
0x180011093  xor     ebp, ebp
0x180011095  mov     rdx, rdi
0x180011098  mov     cl, bpl
0x18001109b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110a0  add     rsp, 28h
0x1800110a4  pop     r15
0x1800110a6  pop     r14
0x1800110a8  pop     rdi
0x1800110a9  pop     rsi
0x1800110aa  pop     rbp
0x1800110ab  pop     rbx
0x1800110ac  retn
```
