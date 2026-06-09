# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1400098f0`
- end: `0x1400099aa`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400099b0`

## callees

- `0x1400098f0`
- `0x140009dbc`
- `0x140009f78`
- `0x14003a010`

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
0x1400098f0  push    rbx
0x1400098f2  push    rbp
0x1400098f3  push    rsi
0x1400098f4  push    rdi
0x1400098f5  push    r14
0x1400098f7  push    r15
0x1400098f9  sub     rsp, 28h
0x1400098fd  mov     r15, r8
0x140009900  mov     rsi, rdx
0x140009903  mov     rdi, rcx
0x140009906  mov     byte ptr [rdx], 0
0x140009909  xor     r14b, r14b
0x14000990c  mov     bpl, 1
0x14000990f  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140009917  jz      short loc_140009978
0x140009919  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x14000991e  mov     rbx, rax
0x140009921  test    rax, rax
0x140009924  jz      short loc_140009978
0x140009926  cmp     qword ptr [rax], 0
0x14000992a  jz      short loc_140009978
0x14000992c  mov     [rsi], r14b
0x14000992f  mov     r9, r15; unsigned __int64
0x140009932  mov     r8, rsi; char *
0x140009935  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x140009938  mov     rcx, rdi; struct wil::FailureInfo *
0x14000993b  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140009940  test    al, al
0x140009942  jz      short loc_140009948
0x140009944  mov     [rdi+48h], rsi
0x140009948  mov     rbx, [rbx]
0x14000994b  mov     al, [rbx+28h]
0x14000994e  mov     [rbx+28h], bpl
0x140009952  test    al, al
0x140009954  jnz     short loc_14000996F
0x140009956  mov     rcx, [rbx+8]
0x14000995a  mov     rax, [rcx]
0x14000995d  mov     rdx, rdi
0x140009960  mov     rax, [rax]
0x140009963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009968  or      r14b, al
0x14000996b  mov     byte ptr [rbx+28h], 0
0x14000996f  mov     rbx, [rbx+10h]
0x140009973  test    rbx, rbx
0x140009976  jnz     short loc_14000994B
0x140009978  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x14000997f  test    rax, rax
0x140009982  jz      short loc_14000999D
0x140009984  test    r14b, r14b
0x140009987  jnz     short loc_140009991
0x140009989  test    byte ptr [rdi+4], 2
0x14000998d  jnz     short loc_140009991
0x14000998f  xor     ebp, ebp
0x140009991  mov     rdx, rdi
0x140009994  mov     cl, bpl
0x140009997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000999c  nop
0x14000999d  add     rsp, 28h
0x1400099a1  pop     r15
0x1400099a3  pop     r14
0x1400099a5  pop     rdi
0x1400099a6  pop     rsi
0x1400099a7  pop     rbp
0x1400099a8  pop     rbx
0x1400099a9  retn
```
