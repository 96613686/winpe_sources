# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180009624`
- end: `0x1800096e0`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `188`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800096f0`

## callees

- `0x180009624`
- `0x180009b54`
- `0x180009e28`
- `0x180010010`

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
0x180009624  push    rbx
0x180009626  push    rbp
0x180009627  push    rsi
0x180009628  push    rdi
0x180009629  push    r14
0x18000962b  push    r15
0x18000962d  sub     rsp, 28h
0x180009631  mov     r15, r8
0x180009634  mov     rsi, rdx
0x180009637  mov     rdi, rcx
0x18000963a  mov     byte ptr [rdx], 0
0x18000963d  xor     r14b, r14b
0x180009640  mov     bpl, 1
0x180009643  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000964b  jz      short loc_1800096AE
0x18000964d  xor     edx, edx
0x18000964f  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180009654  mov     rbx, rax
0x180009657  test    rax, rax
0x18000965a  jz      short loc_1800096AE
0x18000965c  cmp     qword ptr [rax], 0
0x180009660  jz      short loc_1800096AE
0x180009662  mov     [rsi], r14b
0x180009665  mov     r9, r15; unsigned __int64
0x180009668  mov     r8, rsi; char *
0x18000966b  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x18000966e  mov     rcx, rdi; struct wil::FailureInfo *
0x180009671  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180009676  test    al, al
0x180009678  jz      short loc_18000967E
0x18000967a  mov     [rdi+48h], rsi
0x18000967e  mov     rbx, [rbx]
0x180009681  mov     al, [rbx+28h]
0x180009684  mov     [rbx+28h], bpl
0x180009688  test    al, al
0x18000968a  jnz     short loc_1800096A5
0x18000968c  mov     rcx, [rbx+8]
0x180009690  mov     rax, [rcx]
0x180009693  mov     rdx, rdi
0x180009696  mov     rax, [rax]
0x180009699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000969e  or      r14b, al
0x1800096a1  mov     byte ptr [rbx+28h], 0
0x1800096a5  mov     rbx, [rbx+10h]
0x1800096a9  test    rbx, rbx
0x1800096ac  jnz     short loc_180009681
0x1800096ae  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800096b5  test    rax, rax
0x1800096b8  jz      short loc_1800096D3
0x1800096ba  test    r14b, r14b
0x1800096bd  jnz     short loc_1800096C7
0x1800096bf  test    byte ptr [rdi+4], 2
0x1800096c3  jnz     short loc_1800096C7
0x1800096c5  xor     ebp, ebp
0x1800096c7  mov     rdx, rdi
0x1800096ca  mov     cl, bpl
0x1800096cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096d2  nop
0x1800096d3  add     rsp, 28h
0x1800096d7  pop     r15
0x1800096d9  pop     r14
0x1800096db  pop     rdi
0x1800096dc  pop     rsi
0x1800096dd  pop     rbp
0x1800096de  pop     rbx
0x1800096df  retn
```
