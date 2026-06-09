# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800370a4`
- end: `0x18003719e`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `250`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800371b0`

## callees

- `0x1800370a4`
- `0x18003800c`
- `0x180040010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800370d3`
- `KERNEL32!GetCurrentThreadId` at `0x1800370d3`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(
        unsigned __int64 a1,
        char *a2,
        unsigned __int64 a3)
{
  char v3; // r14
  __int64 v4; // rbx
  struct wil::FailureInfo *v7; // rdi
  char v8; // bp
  unsigned __int64 CurrentThreadId; // r9
  __int64 i; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v11; // rbx
  char v12; // al

  *a2 = 0;
  v3 = 0;
  v4 = wil::details::g_pThreadFailureCallbacks;
  v7 = (struct wil::FailureInfo *)a1;
  v8 = 1;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    a1 = 10 * ((CurrentThreadId >> 2) / 0xA);
    for ( i = *(_QWORD *)(v4 + 8 * ((CurrentThreadId >> 2) % 0xA)); i; i = *(_QWORD *)(i + 8) )
    {
      if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
      {
        i += 16;
        break;
      }
    }
    if ( i && *(_QWORD *)i )
    {
      *a2 = 0;
      if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(
             v7,
             *(struct wil::details::ThreadFailureCallbackHolder **)i,
             a2,
             a3) )
      {
        *((_QWORD *)v7 + 9) = a2;
      }
      v11 = *(struct wil::details::ThreadFailureCallbackHolder **)i;
      do
      {
        v12 = *((_BYTE *)v11 + 40);
        *((_BYTE *)v11 + 40) = 1;
        if ( !v12 )
        {
          v3 |= (***((__int64 (__fastcall ****)(_QWORD, struct wil::FailureInfo *))v11 + 1))(*((_QWORD *)v11 + 1), v7);
          *((_BYTE *)v11 + 40) = 0;
        }
        v11 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v11 + 2);
      }
      while ( v11 );
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( !v3 && (*((_BYTE *)v7 + 4) & 2) == 0 )
      v8 = 0;
    LOBYTE(a1) = v8;
    wil::details::g_pfnTelemetryCallback(a1, v7);
  }
}

```

## disassembly

```asm
0x1800370a4  push    rbx
0x1800370a6  push    rbp
0x1800370a7  push    rsi
0x1800370a8  push    rdi
0x1800370a9  push    r14
0x1800370ab  push    r15
0x1800370ad  sub     rsp, 28h
0x1800370b1  mov     byte ptr [rdx], 0
0x1800370b4  xor     r14b, r14b
0x1800370b7  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800370be  mov     r15, r8
0x1800370c1  mov     rsi, rdx
0x1800370c4  mov     rdi, rcx
0x1800370c7  mov     bpl, 1
0x1800370ca  test    rbx, rbx
0x1800370cd  jz      loc_18003716D
0x1800370d3  call    cs:__imp_GetCurrentThreadId
0x1800370d9  mov     r8d, eax
0x1800370dc  mov     r9d, eax
0x1800370df  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800370e9  shr     r8, 2
0x1800370ed  mul     r8
0x1800370f0  shr     rdx, 3
0x1800370f4  lea     rcx, [rdx+rdx*4]
0x1800370f8  add     rcx, rcx
0x1800370fb  sub     r8, rcx
0x1800370fe  mov     rbx, [rbx+r8*8]
0x180037102  test    rbx, rbx
0x180037105  jz      short loc_180037116
0x180037107  cmp     [rbx], r9d
0x18003710a  jz      short loc_180037112
0x18003710c  mov     rbx, [rbx+8]
0x180037110  jmp     short loc_180037102
0x180037112  add     rbx, 10h
0x180037116  test    rbx, rbx
0x180037119  jz      short loc_18003716D
0x18003711b  cmp     qword ptr [rbx], 0
0x18003711f  jz      short loc_18003716D
0x180037121  mov     [rsi], r14b
0x180037124  mov     r9, r15; unsigned __int64
0x180037127  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18003712a  mov     r8, rsi; char *
0x18003712d  mov     rcx, rdi; struct wil::FailureInfo *
0x180037130  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180037135  test    al, al
0x180037137  jz      short loc_18003713D
0x180037139  mov     [rdi+48h], rsi
0x18003713d  mov     rbx, [rbx]
0x180037140  mov     al, [rbx+28h]
0x180037143  mov     [rbx+28h], bpl
0x180037147  test    al, al
0x180037149  jnz     short loc_180037164
0x18003714b  mov     rcx, [rbx+8]
0x18003714f  mov     rdx, rdi
0x180037152  mov     rax, [rcx]
0x180037155  mov     rax, [rax]
0x180037158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003715d  or      r14b, al
0x180037160  mov     byte ptr [rbx+28h], 0
0x180037164  mov     rbx, [rbx+10h]
0x180037168  test    rbx, rbx
0x18003716b  jnz     short loc_180037140
0x18003716d  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180037174  test    rax, rax
0x180037177  jz      short loc_180037191
0x180037179  test    r14b, r14b
0x18003717c  jnz     short loc_180037186
0x18003717e  test    byte ptr [rdi+4], 2
0x180037182  jnz     short loc_180037186
0x180037184  xor     ebp, ebp
0x180037186  mov     rdx, rdi
0x180037189  mov     cl, bpl
0x18003718c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037191  add     rsp, 28h
0x180037195  pop     r15
0x180037197  pop     r14
0x180037199  pop     rdi
0x18003719a  pop     rsi
0x18003719b  pop     rbp
0x18003719c  pop     rbx
0x18003719d  retn
```
