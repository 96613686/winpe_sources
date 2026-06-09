# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004cf0`
- end: `0x180004df5`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `261`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004c80`

## callees

- `0x180004cf0`
- `0x18000fba0`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d1a`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(
        struct wil::FailureInfo *a1,
        char *a2,
        unsigned __int64 a3)
{
  struct wil::FailureInfo *v5; // rdi
  char v6; // si
  __int64 v7; // rbx
  unsigned __int64 CurrentThreadId; // r10
  struct wil::details::ThreadFailureCallbackHolder **v9; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v10; // rbx
  char v11; // al

  v5 = a1;
  *a2 = 0;
  v6 = 0;
  v7 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    a1 = *(struct wil::FailureInfo **)(v7 + 8 * ((CurrentThreadId >> 2) % 0xA));
    if ( a1 )
    {
      while ( *(_DWORD *)a1 != (_DWORD)CurrentThreadId )
      {
        a1 = (struct wil::FailureInfo *)*((_QWORD *)a1 + 1);
        if ( !a1 )
          goto LABEL_5;
      }
      v9 = (struct wil::details::ThreadFailureCallbackHolder **)((char *)a1 + 16);
    }
    else
    {
LABEL_5:
      v9 = 0;
    }
    if ( v9 && *v9 )
    {
      *a2 = 0;
      if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(v5, *v9, a2, a3) )
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
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( v6 || (*((_BYTE *)v5 + 4) & 2) != 0 )
      LOBYTE(a1) = 1;
    else
      a1 = 0;
    wil::details::g_pfnTelemetryCallback(a1, v5);
  }
}

```

## disassembly

```asm
0x180004cf0  push    rbx
0x180004cf2  push    rbp
0x180004cf3  push    rsi
0x180004cf4  push    rdi
0x180004cf5  push    r14
0x180004cf7  sub     rsp, 20h
0x180004cfb  mov     rbp, r8
0x180004cfe  mov     r14, rdx
0x180004d01  mov     rdi, rcx
0x180004d04  mov     byte ptr [rdx], 0
0x180004d07  xor     sil, sil
0x180004d0a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004d11  test    rbx, rbx
0x180004d14  jz      loc_180004DBE
0x180004d1a  call    cs:__imp_GetCurrentThreadId
0x180004d20  mov     r10d, eax
0x180004d23  mov     r9d, eax
0x180004d26  shr     r9, 2
0x180004d2a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004d34  mul     r9
0x180004d37  shr     rdx, 3
0x180004d3b  lea     rcx, [rdx+rdx*4]
0x180004d3f  add     rcx, rcx
0x180004d42  sub     r9, rcx
0x180004d45  mov     rcx, [rbx+r9*8]
0x180004d49  test    rcx, rcx
0x180004d4c  jz      short loc_180004D62
0x180004d4e  xchg    ax, ax
0x180004d50  cmp     [rcx], r10d
0x180004d53  jz      loc_180004DD9
0x180004d59  mov     rcx, [rcx+8]
0x180004d5d  test    rcx, rcx
0x180004d60  jnz     short loc_180004D50
0x180004d62  xor     ebx, ebx
0x180004d64  test    rbx, rbx
0x180004d67  jz      short loc_180004DBE
0x180004d69  cmp     qword ptr [rbx], 0
0x180004d6d  jz      short loc_180004DBE
0x180004d6f  mov     [r14], sil
0x180004d72  mov     r9, rbp; unsigned __int64
0x180004d75  mov     r8, r14; char *
0x180004d78  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004d7b  mov     rcx, rdi; struct wil::FailureInfo *
0x180004d7e  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004d83  test    al, al
0x180004d85  jz      short loc_180004D8B
0x180004d87  mov     [rdi+48h], r14
0x180004d8b  mov     rbx, [rbx]
0x180004d8e  xchg    ax, ax
0x180004d90  movzx   eax, byte ptr [rbx+28h]
0x180004d94  mov     byte ptr [rbx+28h], 1
0x180004d98  test    al, al
0x180004d9a  jnz     short loc_180004DB5
0x180004d9c  mov     rcx, [rbx+8]
0x180004da0  mov     rax, [rcx]
0x180004da3  mov     rdx, rdi
0x180004da6  mov     rax, [rax]
0x180004da9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dae  or      sil, al
0x180004db1  mov     byte ptr [rbx+28h], 0
0x180004db5  mov     rbx, [rbx+10h]
0x180004db9  test    rbx, rbx
0x180004dbc  jnz     short loc_180004D90
0x180004dbe  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004dc5  test    rax, rax
0x180004dc8  jz      short loc_180004DEA
0x180004dca  test    sil, sil
0x180004dcd  jnz     short loc_180004DDF
0x180004dcf  test    byte ptr [rdi+4], 2
0x180004dd3  jnz     short loc_180004DDF
0x180004dd5  xor     ecx, ecx
0x180004dd7  jmp     short loc_180004DE1
0x180004dd9  lea     rbx, [rcx+10h]
0x180004ddd  jmp     short loc_180004D64
0x180004ddf  mov     cl, 1
0x180004de1  mov     rdx, rdi
0x180004de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004de9  nop
0x180004dea  add     rsp, 20h
0x180004dee  pop     r14
0x180004df0  pop     rdi
0x180004df1  pop     rsi
0x180004df2  pop     rbp
0x180004df3  pop     rbx
0x180004df4  retn
```
