# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180003d14`
- end: `0x180003df5`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `225`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003d14`
- `0x180003e00`

## callees

- `0x180001224`
- `0x180003d14`

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
  __int64 v10; // rcx
  char *v11; // r10
  __int64 v12; // rax
  char *v13; // r8
  _BYTE *v14; // rdi
  _BYTE *v15; // r8
  rsize_t v16; // r10
  rsize_t v17; // rbx

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
      v10 = -1;
      v11 = &a3[a4];
      v12 = -1;
      *(_OWORD *)((char *)a1 + 104) = *(_OWORD *)v9;
      *((_QWORD *)a1 + 15) = *((_QWORD *)v9 + 2);
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
          ++v10;
        while ( v15[v10] );
        v16 = v11 - v14;
        v17 = v16;
        if ( v10 + 1 < v16 )
          v17 = v10 + 1;
        memcpy_s(v14, v16, v15, v17);
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
0x180003d14  push    rbx
0x180003d16  push    rbp
0x180003d17  push    rsi
0x180003d18  push    rdi
0x180003d19  sub     rsp, 28h
0x180003d1d  xor     al, al
0x180003d1f  mov     byte ptr [r8], 0
0x180003d23  mov     rbp, r9
0x180003d26  mov     rdi, r8
0x180003d29  mov     rsi, rdx
0x180003d2c  mov     rbx, rcx
0x180003d2f  test    rdx, rdx
0x180003d32  jz      loc_180003DEC
0x180003d38  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180003d3c  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180003d41  mov     rdx, [rsi+20h]
0x180003d45  test    rdx, rdx
0x180003d48  jz      loc_180003DEC
0x180003d4e  cmp     dword ptr [rdx], 0
0x180003d51  jnz     short loc_180003D64
0x180003d53  mov     eax, 1
0x180003d58  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180003d60  inc     eax
0x180003d62  mov     [rdx], eax
0x180003d64  cmp     dword ptr [rbx+50h], 0
0x180003d68  jnz     short loc_180003D7B
0x180003d6a  movups  xmm0, xmmword ptr [rdx]
0x180003d6d  movups  xmmword ptr [rbx+50h], xmm0
0x180003d71  movsd   xmm1, qword ptr [rdx+10h]
0x180003d76  movsd   qword ptr [rbx+60h], xmm1
0x180003d7b  movups  xmm0, xmmword ptr [rdx]
0x180003d7e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180003d82  lea     r10, [rdi+rbp]
0x180003d86  mov     rax, rcx
0x180003d89  movups  xmmword ptr [rbx+68h], xmm0
0x180003d8d  movsd   xmm1, qword ptr [rdx+10h]
0x180003d92  movsd   qword ptr [rbx+78h], xmm1
0x180003d97  inc     rax
0x180003d9a  cmp     byte ptr [rdi+rax], 0
0x180003d9e  jnz     short loc_180003D97
0x180003da0  lea     r8, [rax+rdi]
0x180003da4  mov     rax, r10
0x180003da7  sub     rax, r8
0x180003daa  cmp     rax, 2
0x180003dae  jle     short loc_180003DEA
0x180003db0  mov     byte ptr [r8], 5Ch ; '\'
0x180003db4  lea     rdi, [r8+1]
0x180003db8  mov     r8, [rdx+8]; Source
0x180003dbc  inc     rcx
0x180003dbf  cmp     byte ptr [r8+rcx], 0
0x180003dc4  jnz     short loc_180003DBC
0x180003dc6  lea     rax, [rcx+1]
0x180003dca  sub     r10, rdi
0x180003dcd  cmp     rax, r10
0x180003dd0  mov     rbx, r10
0x180003dd3  mov     rdx, r10; DestinationSize
0x180003dd6  mov     rcx, rdi; Destination
0x180003dd9  cmovb   rbx, rax
0x180003ddd  mov     r9, rbx; SourceSize
0x180003de0  call    memcpy_s
0x180003de5  mov     byte ptr [rbx+rdi-1], 0
0x180003dea  mov     al, 1
0x180003dec  add     rsp, 28h
0x180003df0  pop     rdi
0x180003df1  pop     rsi
0x180003df2  pop     rbp
0x180003df3  pop     rbx
0x180003df4  retn
```
