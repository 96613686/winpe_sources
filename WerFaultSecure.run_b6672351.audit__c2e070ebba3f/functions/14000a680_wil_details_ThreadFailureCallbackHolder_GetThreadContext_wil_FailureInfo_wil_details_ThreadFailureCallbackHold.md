# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x14000a680`
- end: `0x14000a75c`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000a3b0`
- `0x14000a680`

## callees

- `0x140004978`
- `0x14000a680`

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
0x14000a680  push    rbx
0x14000a682  push    rbp
0x14000a683  push    rsi
0x14000a684  push    rdi
0x14000a685  sub     rsp, 28h
0x14000a689  xor     al, al
0x14000a68b  mov     byte ptr [r8], 0
0x14000a68f  mov     rbp, r9
0x14000a692  mov     rdi, r8
0x14000a695  mov     rsi, rdx
0x14000a698  mov     rbx, rcx
0x14000a69b  test    rdx, rdx
0x14000a69e  jz      loc_14000A753
0x14000a6a4  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x14000a6a8  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x14000a6ad  mov     rdx, [rsi+20h]
0x14000a6b1  test    rdx, rdx
0x14000a6b4  jz      loc_14000A753
0x14000a6ba  cmp     dword ptr [rdx], 0
0x14000a6bd  jnz     short loc_14000A6D0
0x14000a6bf  mov     eax, 1
0x14000a6c4  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x14000a6cc  inc     eax
0x14000a6ce  mov     [rdx], eax
0x14000a6d0  cmp     dword ptr [rbx+50h], 0
0x14000a6d4  jnz     short loc_14000A6E7
0x14000a6d6  movups  xmm0, xmmword ptr [rdx]
0x14000a6d9  movups  xmmword ptr [rbx+50h], xmm0
0x14000a6dd  movsd   xmm1, qword ptr [rdx+10h]
0x14000a6e2  movsd   qword ptr [rbx+60h], xmm1
0x14000a6e7  movups  xmm0, xmmword ptr [rdx]
0x14000a6ea  lea     r10, [rdi+rbp]
0x14000a6ee  movups  xmmword ptr [rbx+68h], xmm0
0x14000a6f2  movsd   xmm1, qword ptr [rdx+10h]
0x14000a6f7  movsd   qword ptr [rbx+78h], xmm1
0x14000a6fc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000a700  mov     rax, rbx
0x14000a703  inc     rax
0x14000a706  cmp     byte ptr [rdi+rax], 0
0x14000a70a  jnz     short loc_14000A703
0x14000a70c  lea     rcx, [rax+rdi]
0x14000a710  mov     rax, r10
0x14000a713  sub     rax, rcx
0x14000a716  cmp     rax, 2
0x14000a71a  jle     short loc_14000A751
0x14000a71c  mov     byte ptr [rcx], 5Ch ; '\'
0x14000a71f  lea     rdi, [rcx+1]
0x14000a723  mov     r8, [rdx+8]; Source
0x14000a727  inc     rbx
0x14000a72a  cmp     byte ptr [r8+rbx], 0
0x14000a72f  jnz     short loc_14000A727
0x14000a731  sub     r10, rdi
0x14000a734  inc     rbx
0x14000a737  cmp     rbx, r10
0x14000a73a  mov     rdx, r10; DestinationSize
0x14000a73d  mov     rcx, rdi; Destination
0x14000a740  cmovnb  rbx, r10
0x14000a744  mov     r9, rbx; SourceSize
0x14000a747  call    memcpy_s
0x14000a74c  mov     byte ptr [rbx+rdi-1], 0
0x14000a751  mov     al, 1
0x14000a753  add     rsp, 28h
0x14000a757  pop     rdi
0x14000a758  pop     rsi
0x14000a759  pop     rbp
0x14000a75a  pop     rbx
0x14000a75b  retn
```
