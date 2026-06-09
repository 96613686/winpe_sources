# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x1800049bc`
- end: `0x180004a98`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800042c0`
- `0x1800049bc`

## callees

- `0x1800049bc`
- `0x180006798`

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
0x1800049bc  push    rbx
0x1800049be  push    rbp
0x1800049bf  push    rsi
0x1800049c0  push    rdi
0x1800049c1  sub     rsp, 28h
0x1800049c5  xor     al, al
0x1800049c7  mov     byte ptr [r8], 0
0x1800049cb  mov     rbp, r9
0x1800049ce  mov     rdi, r8
0x1800049d1  mov     rsi, rdx
0x1800049d4  mov     rbx, rcx
0x1800049d7  test    rdx, rdx
0x1800049da  jz      loc_180004A8F
0x1800049e0  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x1800049e4  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800049e9  mov     rdx, [rsi+20h]
0x1800049ed  test    rdx, rdx
0x1800049f0  jz      loc_180004A8F
0x1800049f6  cmp     dword ptr [rdx], 0
0x1800049f9  jnz     short loc_180004A0C
0x1800049fb  mov     eax, 1
0x180004a00  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180004a08  inc     eax
0x180004a0a  mov     [rdx], eax
0x180004a0c  cmp     dword ptr [rbx+50h], 0
0x180004a10  jnz     short loc_180004A23
0x180004a12  movups  xmm0, xmmword ptr [rdx]
0x180004a15  movups  xmmword ptr [rbx+50h], xmm0
0x180004a19  movsd   xmm1, qword ptr [rdx+10h]
0x180004a1e  movsd   qword ptr [rbx+60h], xmm1
0x180004a23  movups  xmm0, xmmword ptr [rdx]
0x180004a26  lea     r10, [rdi+rbp]
0x180004a2a  movups  xmmword ptr [rbx+68h], xmm0
0x180004a2e  movsd   xmm1, qword ptr [rdx+10h]
0x180004a33  movsd   qword ptr [rbx+78h], xmm1
0x180004a38  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004a3c  mov     rax, rbx
0x180004a3f  inc     rax
0x180004a42  cmp     byte ptr [rdi+rax], 0
0x180004a46  jnz     short loc_180004A3F
0x180004a48  lea     rcx, [rax+rdi]
0x180004a4c  mov     rax, r10
0x180004a4f  sub     rax, rcx
0x180004a52  cmp     rax, 2
0x180004a56  jle     short loc_180004A8D
0x180004a58  mov     byte ptr [rcx], 5Ch ; '\'
0x180004a5b  lea     rdi, [rcx+1]
0x180004a5f  mov     r8, [rdx+8]; Source
0x180004a63  inc     rbx
0x180004a66  cmp     byte ptr [r8+rbx], 0
0x180004a6b  jnz     short loc_180004A63
0x180004a6d  sub     r10, rdi
0x180004a70  inc     rbx
0x180004a73  cmp     rbx, r10
0x180004a76  mov     rdx, r10; DestinationSize
0x180004a79  mov     rcx, rdi; Destination
0x180004a7c  cmovnb  rbx, r10
0x180004a80  mov     r9, rbx; SourceSize
0x180004a83  call    memcpy_s
0x180004a88  mov     byte ptr [rbx+rdi-1], 0
0x180004a8d  mov     al, 1
0x180004a8f  add     rsp, 28h
0x180004a93  pop     rdi
0x180004a94  pop     rsi
0x180004a95  pop     rbp
0x180004a96  pop     rbx
0x180004a97  retn
```
