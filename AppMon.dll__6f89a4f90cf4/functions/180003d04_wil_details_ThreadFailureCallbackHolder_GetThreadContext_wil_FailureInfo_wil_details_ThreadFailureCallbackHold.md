# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180003d04`
- end: `0x180003de0`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800036a8`
- `0x180003d04`

## callees

- `0x180003d04`
- `0x180005990`

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
0x180003d04  push    rbx
0x180003d06  push    rbp
0x180003d07  push    rsi
0x180003d08  push    rdi
0x180003d09  sub     rsp, 28h
0x180003d0d  xor     al, al
0x180003d0f  mov     byte ptr [r8], 0
0x180003d13  mov     rbp, r9
0x180003d16  mov     rdi, r8
0x180003d19  mov     rsi, rdx
0x180003d1c  mov     rbx, rcx
0x180003d1f  test    rdx, rdx
0x180003d22  jz      loc_180003DD7
0x180003d28  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180003d2c  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180003d31  mov     rdx, [rsi+20h]
0x180003d35  test    rdx, rdx
0x180003d38  jz      loc_180003DD7
0x180003d3e  cmp     dword ptr [rdx], 0
0x180003d41  jnz     short loc_180003D54
0x180003d43  mov     eax, 1
0x180003d48  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180003d50  inc     eax
0x180003d52  mov     [rdx], eax
0x180003d54  cmp     dword ptr [rbx+50h], 0
0x180003d58  jnz     short loc_180003D6B
0x180003d5a  movups  xmm0, xmmword ptr [rdx]
0x180003d5d  movups  xmmword ptr [rbx+50h], xmm0
0x180003d61  movsd   xmm1, qword ptr [rdx+10h]
0x180003d66  movsd   qword ptr [rbx+60h], xmm1
0x180003d6b  movups  xmm0, xmmword ptr [rdx]
0x180003d6e  lea     r10, [rdi+rbp]
0x180003d72  movups  xmmword ptr [rbx+68h], xmm0
0x180003d76  movsd   xmm1, qword ptr [rdx+10h]
0x180003d7b  movsd   qword ptr [rbx+78h], xmm1
0x180003d80  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180003d84  mov     rax, rbx
0x180003d87  inc     rax
0x180003d8a  cmp     byte ptr [rdi+rax], 0
0x180003d8e  jnz     short loc_180003D87
0x180003d90  lea     rcx, [rax+rdi]
0x180003d94  mov     rax, r10
0x180003d97  sub     rax, rcx
0x180003d9a  cmp     rax, 2
0x180003d9e  jle     short loc_180003DD5
0x180003da0  mov     byte ptr [rcx], 5Ch ; '\'
0x180003da3  lea     rdi, [rcx+1]
0x180003da7  mov     r8, [rdx+8]; Source
0x180003dab  inc     rbx
0x180003dae  cmp     byte ptr [r8+rbx], 0
0x180003db3  jnz     short loc_180003DAB
0x180003db5  sub     r10, rdi
0x180003db8  inc     rbx
0x180003dbb  cmp     rbx, r10
0x180003dbe  mov     rdx, r10; DestinationSize
0x180003dc1  mov     rcx, rdi; Destination
0x180003dc4  cmovnb  rbx, r10
0x180003dc8  mov     r9, rbx; SourceSize
0x180003dcb  call    memcpy_s
0x180003dd0  mov     byte ptr [rbx+rdi-1], 0
0x180003dd5  mov     al, 1
0x180003dd7  add     rsp, 28h
0x180003ddb  pop     rdi
0x180003ddc  pop     rsi
0x180003ddd  pop     rbp
0x180003dde  pop     rbx
0x180003ddf  retn
```
