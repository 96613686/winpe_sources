# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000fcfc`
- end: `0x18000fdd9`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000eba0`
- `0x18000fcfc`

## callees

- `0x18000fcfc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000fdc3`
- `msvcrt!memcpy_s` at `0x18000fdc3`

## pseudocode

```c
bool __fastcall wil::details::ThreadFailureCallbackHolder::GetThreadContext(
        struct wil::FailureInfo *a1,
        struct wil::details::ThreadFailureCallbackHolder **a2,
        char *a3,
        unsigned __int64 a4)
{
  bool result; // al
  struct wil::details::ThreadFailureCallbackHolder *v9; // rdx
  char *v10; // r10
  __int64 v11; // rbx
  __int64 v12; // rax
  char *v13; // rcx
  char *v14; // rdi
  _BYTE *v15; // r8
  rsize_t v16; // r10
  rsize_t v17; // rbx
  void *v18; // rcx

  result = 0;
  *a3 = 0;
  if ( a2 )
  {
    result = wil::details::ThreadFailureCallbackHolder::GetThreadContext(a1, a2[2], a3, a4);
    v9 = a2[4];
    if ( v9 )
    {
      if ( !*(_DWORD *)v9 )
        *(_DWORD *)v9 = _InterlockedIncrement(&wil::details::ThreadFailureCallbackHolder::s_telemetryId);
      if ( !*((_DWORD *)a1 + 20) )
      {
        *((_OWORD *)a1 + 5) = *(_OWORD *)v9;
        *((_QWORD *)a1 + 12) = *((_QWORD *)v9 + 2);
      }
      v10 = &a3[a4];
      *(_OWORD *)((char *)a1 + 104) = *(_OWORD *)v9;
      *((_QWORD *)a1 + 15) = *((_QWORD *)v9 + 2);
      v11 = -1;
      v12 = -1;
      do
        ++v12;
      while ( a3[v12] );
      v13 = &a3[v12];
      if ( (__int64)(a4 - v12) > 2 )
      {
        *v13 = 92;
        v14 = v13 + 1;
        v15 = (_BYTE *)*((_QWORD *)v9 + 1);
        do
          ++v11;
        while ( v15[v11] );
        v16 = v10 - v14;
        v17 = v11 + 1;
        v18 = v13 + 1;
        if ( v17 >= v16 )
          v17 = v16;
        memcpy_s(v18, v16, v15, v17);
        v14[v17 - 1] = 0;
      }
      return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000fcfc  push    rbx
0x18000fcfe  push    rbp
0x18000fcff  push    rsi
0x18000fd00  push    rdi
0x18000fd01  sub     rsp, 28h
0x18000fd05  xor     al, al
0x18000fd07  mov     byte ptr [r8], 0
0x18000fd0b  mov     rbp, r9
0x18000fd0e  mov     rdi, r8
0x18000fd11  mov     rsi, rdx
0x18000fd14  mov     rbx, rcx
0x18000fd17  test    rdx, rdx
0x18000fd1a  jz      loc_18000FDD0
0x18000fd20  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18000fd24  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000fd29  mov     rdx, [rsi+20h]
0x18000fd2d  test    rdx, rdx
0x18000fd30  jz      loc_18000FDD0
0x18000fd36  cmp     dword ptr [rdx], 0
0x18000fd39  jnz     short loc_18000FD4C
0x18000fd3b  mov     eax, 1
0x18000fd40  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000fd48  inc     eax
0x18000fd4a  mov     [rdx], eax
0x18000fd4c  cmp     dword ptr [rbx+50h], 0
0x18000fd50  jnz     short loc_18000FD63
0x18000fd52  movups  xmm0, xmmword ptr [rdx]
0x18000fd55  movups  xmmword ptr [rbx+50h], xmm0
0x18000fd59  movsd   xmm1, qword ptr [rdx+10h]
0x18000fd5e  movsd   qword ptr [rbx+60h], xmm1
0x18000fd63  movups  xmm0, xmmword ptr [rdx]
0x18000fd66  lea     r10, [rdi+rbp]
0x18000fd6a  movups  xmmword ptr [rbx+68h], xmm0
0x18000fd6e  movsd   xmm1, qword ptr [rdx+10h]
0x18000fd73  movsd   qword ptr [rbx+78h], xmm1
0x18000fd78  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000fd7c  mov     rax, rbx
0x18000fd7f  inc     rax
0x18000fd82  cmp     byte ptr [rdi+rax], 0
0x18000fd86  jnz     short loc_18000FD7F
0x18000fd88  lea     rcx, [rax+rdi]
0x18000fd8c  mov     rax, r10
0x18000fd8f  sub     rax, rcx
0x18000fd92  cmp     rax, 2
0x18000fd96  jle     short loc_18000FDCE
0x18000fd98  mov     byte ptr [rcx], 5Ch ; '\'
0x18000fd9b  lea     rdi, [rcx+1]
0x18000fd9f  mov     r8, [rdx+8]; Source
0x18000fda3  inc     rbx
0x18000fda6  cmp     byte ptr [r8+rbx], 0
0x18000fdab  jnz     short loc_18000FDA3
0x18000fdad  sub     r10, rdi
0x18000fdb0  inc     rbx
0x18000fdb3  cmp     rbx, r10
0x18000fdb6  mov     rdx, r10; DestinationSize
0x18000fdb9  mov     rcx, rdi; Destination
0x18000fdbc  cmovnb  rbx, r10
0x18000fdc0  mov     r9, rbx; SourceSize
0x18000fdc3  call    cs:__imp_memcpy_s
0x18000fdc9  mov     byte ptr [rbx+rdi-1], 0
0x18000fdce  mov     al, 1
0x18000fdd0  add     rsp, 28h
0x18000fdd4  pop     rdi
0x18000fdd5  pop     rsi
0x18000fdd6  pop     rbp
0x18000fdd7  pop     rbx
0x18000fdd8  retn
```
