# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000eba0`
- end: `0x18000ec9b`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `251`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ecb0`

## callees

- `0x18000eba0`
- `0x18000fcfc`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ebcf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ebcf`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(
        unsigned __int64 a1,
        char *a2,
        unsigned __int64 a3)
{
  struct wil::FailureInfo *v5; // rdi
  char v6; // r14
  char v7; // bp
  __int64 v8; // rbx
  unsigned __int64 CurrentThreadId; // r9
  __int64 i; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v11; // rbx
  char v12; // al

  v5 = (struct wil::FailureInfo *)a1;
  *a2 = 0;
  v6 = 0;
  v7 = 1;
  v8 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    a1 = 10 * ((CurrentThreadId >> 2) / 0xA);
    for ( i = *(_QWORD *)(v8 + 8 * ((CurrentThreadId >> 2) % 0xA)); i; i = *(_QWORD *)(i + 8) )
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
             v5,
             *(struct wil::details::ThreadFailureCallbackHolder **)i,
             a2,
             a3) )
      {
        *((_QWORD *)v5 + 9) = a2;
      }
      v11 = *(struct wil::details::ThreadFailureCallbackHolder **)i;
      do
      {
        v12 = *((_BYTE *)v11 + 40);
        *((_BYTE *)v11 + 40) = 1;
        if ( !v12 )
        {
          v6 |= (***((__int64 (__fastcall ****)(_QWORD, struct wil::FailureInfo *))v11 + 1))(*((_QWORD *)v11 + 1), v5);
          *((_BYTE *)v11 + 40) = 0;
        }
        v11 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v11 + 2);
      }
      while ( v11 );
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
0x18000eba0  push    rbx
0x18000eba2  push    rbp
0x18000eba3  push    rsi
0x18000eba4  push    rdi
0x18000eba5  push    r14
0x18000eba7  push    r15
0x18000eba9  sub     rsp, 28h
0x18000ebad  mov     r15, r8
0x18000ebb0  mov     rsi, rdx
0x18000ebb3  mov     rdi, rcx
0x18000ebb6  mov     byte ptr [rdx], 0
0x18000ebb9  xor     r14b, r14b
0x18000ebbc  mov     bpl, 1
0x18000ebbf  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000ebc6  test    rbx, rbx
0x18000ebc9  jz      loc_18000EC69
0x18000ebcf  call    cs:__imp_GetCurrentThreadId
0x18000ebd5  mov     r9d, eax
0x18000ebd8  mov     r8d, eax
0x18000ebdb  shr     r8, 2
0x18000ebdf  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000ebe9  mul     r8
0x18000ebec  shr     rdx, 3
0x18000ebf0  lea     rcx, [rdx+rdx*4]
0x18000ebf4  add     rcx, rcx
0x18000ebf7  sub     r8, rcx
0x18000ebfa  mov     rbx, [rbx+r8*8]
0x18000ebfe  test    rbx, rbx
0x18000ec01  jz      short loc_18000EC12
0x18000ec03  cmp     [rbx], r9d
0x18000ec06  jz      short loc_18000EC0E
0x18000ec08  mov     rbx, [rbx+8]
0x18000ec0c  jmp     short loc_18000EBFE
0x18000ec0e  add     rbx, 10h
0x18000ec12  test    rbx, rbx
0x18000ec15  jz      short loc_18000EC69
0x18000ec17  cmp     qword ptr [rbx], 0
0x18000ec1b  jz      short loc_18000EC69
0x18000ec1d  mov     [rsi], r14b
0x18000ec20  mov     r9, r15; unsigned __int64
0x18000ec23  mov     r8, rsi; char *
0x18000ec26  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000ec29  mov     rcx, rdi; struct wil::FailureInfo *
0x18000ec2c  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000ec31  test    al, al
0x18000ec33  jz      short loc_18000EC39
0x18000ec35  mov     [rdi+48h], rsi
0x18000ec39  mov     rbx, [rbx]
0x18000ec3c  mov     al, [rbx+28h]
0x18000ec3f  mov     [rbx+28h], bpl
0x18000ec43  test    al, al
0x18000ec45  jnz     short loc_18000EC60
0x18000ec47  mov     rcx, [rbx+8]
0x18000ec4b  mov     rax, [rcx]
0x18000ec4e  mov     rdx, rdi
0x18000ec51  mov     rax, [rax]
0x18000ec54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec59  or      r14b, al
0x18000ec5c  mov     byte ptr [rbx+28h], 0
0x18000ec60  mov     rbx, [rbx+10h]
0x18000ec64  test    rbx, rbx
0x18000ec67  jnz     short loc_18000EC3C
0x18000ec69  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000ec70  test    rax, rax
0x18000ec73  jz      short loc_18000EC8E
0x18000ec75  test    r14b, r14b
0x18000ec78  jnz     short loc_18000EC82
0x18000ec7a  test    byte ptr [rdi+4], 2
0x18000ec7e  jnz     short loc_18000EC82
0x18000ec80  xor     ebp, ebp
0x18000ec82  mov     rdx, rdi
0x18000ec85  mov     cl, bpl
0x18000ec88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec8d  nop
0x18000ec8e  add     rsp, 28h
0x18000ec92  pop     r15
0x18000ec94  pop     r14
0x18000ec96  pop     rdi
0x18000ec97  pop     rsi
0x18000ec98  pop     rbp
0x18000ec99  pop     rbx
0x18000ec9a  retn
```
