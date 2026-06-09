# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140003bac`
- end: `0x140003c88`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400034b0`
- `0x140003bac`

## callees

- `0x140003bac`
- `0x140005808`

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
0x140003bac  push    rbx
0x140003bae  push    rbp
0x140003baf  push    rsi
0x140003bb0  push    rdi
0x140003bb1  sub     rsp, 28h
0x140003bb5  xor     al, al
0x140003bb7  mov     byte ptr [r8], 0
0x140003bbb  mov     rbp, r9
0x140003bbe  mov     rdi, r8
0x140003bc1  mov     rsi, rdx
0x140003bc4  mov     rbx, rcx
0x140003bc7  test    rdx, rdx
0x140003bca  jz      loc_140003C7F
0x140003bd0  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140003bd4  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140003bd9  mov     rdx, [rsi+20h]
0x140003bdd  test    rdx, rdx
0x140003be0  jz      loc_140003C7F
0x140003be6  cmp     dword ptr [rdx], 0
0x140003be9  jnz     short loc_140003BFC
0x140003beb  mov     eax, 1
0x140003bf0  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140003bf8  inc     eax
0x140003bfa  mov     [rdx], eax
0x140003bfc  cmp     dword ptr [rbx+50h], 0
0x140003c00  jnz     short loc_140003C13
0x140003c02  movups  xmm0, xmmword ptr [rdx]
0x140003c05  movups  xmmword ptr [rbx+50h], xmm0
0x140003c09  movsd   xmm1, qword ptr [rdx+10h]
0x140003c0e  movsd   qword ptr [rbx+60h], xmm1
0x140003c13  movups  xmm0, xmmword ptr [rdx]
0x140003c16  lea     r10, [rdi+rbp]
0x140003c1a  movups  xmmword ptr [rbx+68h], xmm0
0x140003c1e  movsd   xmm1, qword ptr [rdx+10h]
0x140003c23  movsd   qword ptr [rbx+78h], xmm1
0x140003c28  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140003c2c  mov     rax, rbx
0x140003c2f  inc     rax
0x140003c32  cmp     byte ptr [rdi+rax], 0
0x140003c36  jnz     short loc_140003C2F
0x140003c38  lea     rcx, [rax+rdi]
0x140003c3c  mov     rax, r10
0x140003c3f  sub     rax, rcx
0x140003c42  cmp     rax, 2
0x140003c46  jle     short loc_140003C7D
0x140003c48  mov     byte ptr [rcx], 5Ch ; '\'
0x140003c4b  lea     rdi, [rcx+1]
0x140003c4f  mov     r8, [rdx+8]; Source
0x140003c53  inc     rbx
0x140003c56  cmp     byte ptr [r8+rbx], 0
0x140003c5b  jnz     short loc_140003C53
0x140003c5d  sub     r10, rdi
0x140003c60  inc     rbx
0x140003c63  cmp     rbx, r10
0x140003c66  mov     rdx, r10; DestinationSize
0x140003c69  mov     rcx, rdi; Destination
0x140003c6c  cmovnb  rbx, r10
0x140003c70  mov     r9, rbx; SourceSize
0x140003c73  call    memcpy_s
0x140003c78  mov     byte ptr [rbx+rdi-1], 0
0x140003c7d  mov     al, 1
0x140003c7f  add     rsp, 28h
0x140003c83  pop     rdi
0x140003c84  pop     rsi
0x140003c85  pop     rbp
0x140003c86  pop     rbx
0x140003c87  retn
```
