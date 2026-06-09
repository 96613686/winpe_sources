# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000b53c`
- end: `0x18000b619`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180009474`
- `0x18000b53c`

## callees

- `0x18000b53c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000b603`
- `msvcrt!memcpy_s` at `0x18000b603`

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
0x18000b53c  push    rbx
0x18000b53e  push    rbp
0x18000b53f  push    rsi
0x18000b540  push    rdi
0x18000b541  sub     rsp, 28h
0x18000b545  xor     al, al
0x18000b547  mov     byte ptr [r8], 0
0x18000b54b  mov     rbp, r9
0x18000b54e  mov     rdi, r8
0x18000b551  mov     rsi, rdx
0x18000b554  mov     rbx, rcx
0x18000b557  test    rdx, rdx
0x18000b55a  jz      loc_18000B610
0x18000b560  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18000b564  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000b569  mov     rdx, [rsi+20h]
0x18000b56d  test    rdx, rdx
0x18000b570  jz      loc_18000B610
0x18000b576  cmp     dword ptr [rdx], 0
0x18000b579  jnz     short loc_18000B58C
0x18000b57b  mov     eax, 1
0x18000b580  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000b588  inc     eax
0x18000b58a  mov     [rdx], eax
0x18000b58c  cmp     dword ptr [rbx+50h], 0
0x18000b590  jnz     short loc_18000B5A3
0x18000b592  movups  xmm0, xmmword ptr [rdx]
0x18000b595  movups  xmmword ptr [rbx+50h], xmm0
0x18000b599  movsd   xmm1, qword ptr [rdx+10h]
0x18000b59e  movsd   qword ptr [rbx+60h], xmm1
0x18000b5a3  movups  xmm0, xmmword ptr [rdx]
0x18000b5a6  lea     r10, [rdi+rbp]
0x18000b5aa  movups  xmmword ptr [rbx+68h], xmm0
0x18000b5ae  movsd   xmm1, qword ptr [rdx+10h]
0x18000b5b3  movsd   qword ptr [rbx+78h], xmm1
0x18000b5b8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000b5bc  mov     rax, rbx
0x18000b5bf  inc     rax
0x18000b5c2  cmp     byte ptr [rdi+rax], 0
0x18000b5c6  jnz     short loc_18000B5BF
0x18000b5c8  lea     rcx, [rax+rdi]
0x18000b5cc  mov     rax, r10
0x18000b5cf  sub     rax, rcx
0x18000b5d2  cmp     rax, 2
0x18000b5d6  jle     short loc_18000B60E
0x18000b5d8  mov     byte ptr [rcx], 5Ch ; '\'
0x18000b5db  lea     rdi, [rcx+1]
0x18000b5df  mov     r8, [rdx+8]; Source
0x18000b5e3  inc     rbx
0x18000b5e6  cmp     byte ptr [r8+rbx], 0
0x18000b5eb  jnz     short loc_18000B5E3
0x18000b5ed  sub     r10, rdi
0x18000b5f0  inc     rbx
0x18000b5f3  cmp     rbx, r10
0x18000b5f6  mov     rdx, r10; DestinationSize
0x18000b5f9  mov     rcx, rdi; Destination
0x18000b5fc  cmovnb  rbx, r10
0x18000b600  mov     r9, rbx; SourceSize
0x18000b603  call    cs:__imp_memcpy_s
0x18000b609  mov     byte ptr [rbx+rdi-1], 0
0x18000b60e  mov     al, 1
0x18000b610  add     rsp, 28h
0x18000b614  pop     rdi
0x18000b615  pop     rsi
0x18000b616  pop     rbp
0x18000b617  pop     rbx
0x18000b618  retn
```
