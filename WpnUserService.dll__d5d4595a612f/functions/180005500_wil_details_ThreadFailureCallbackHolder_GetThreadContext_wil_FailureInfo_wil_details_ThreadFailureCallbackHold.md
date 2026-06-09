# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180005500`
- end: `0x1800055dc`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004d60`
- `0x180005500`

## callees

- `0x180005500`
- `0x1800073b8`

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
0x180005500  push    rbx
0x180005502  push    rbp
0x180005503  push    rsi
0x180005504  push    rdi
0x180005505  sub     rsp, 28h
0x180005509  xor     al, al
0x18000550b  mov     byte ptr [r8], 0
0x18000550f  mov     rbp, r9
0x180005512  mov     rdi, r8
0x180005515  mov     rsi, rdx
0x180005518  mov     rbx, rcx
0x18000551b  test    rdx, rdx
0x18000551e  jz      loc_1800055D3
0x180005524  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180005528  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000552d  mov     rdx, [rsi+20h]
0x180005531  test    rdx, rdx
0x180005534  jz      loc_1800055D3
0x18000553a  cmp     dword ptr [rdx], 0
0x18000553d  jnz     short loc_180005550
0x18000553f  mov     eax, 1
0x180005544  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000554c  inc     eax
0x18000554e  mov     [rdx], eax
0x180005550  cmp     dword ptr [rbx+50h], 0
0x180005554  jnz     short loc_180005567
0x180005556  movups  xmm0, xmmword ptr [rdx]
0x180005559  movups  xmmword ptr [rbx+50h], xmm0
0x18000555d  movsd   xmm1, qword ptr [rdx+10h]
0x180005562  movsd   qword ptr [rbx+60h], xmm1
0x180005567  movups  xmm0, xmmword ptr [rdx]
0x18000556a  lea     r10, [rdi+rbp]
0x18000556e  movups  xmmword ptr [rbx+68h], xmm0
0x180005572  movsd   xmm1, qword ptr [rdx+10h]
0x180005577  movsd   qword ptr [rbx+78h], xmm1
0x18000557c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005580  mov     rax, rbx
0x180005583  inc     rax
0x180005586  cmp     byte ptr [rdi+rax], 0
0x18000558a  jnz     short loc_180005583
0x18000558c  lea     rcx, [rax+rdi]
0x180005590  mov     rax, r10
0x180005593  sub     rax, rcx
0x180005596  cmp     rax, 2
0x18000559a  jle     short loc_1800055D1
0x18000559c  mov     byte ptr [rcx], 5Ch ; '\'
0x18000559f  lea     rdi, [rcx+1]
0x1800055a3  mov     r8, [rdx+8]; Source
0x1800055a7  inc     rbx
0x1800055aa  cmp     byte ptr [r8+rbx], 0
0x1800055af  jnz     short loc_1800055A7
0x1800055b1  sub     r10, rdi
0x1800055b4  inc     rbx
0x1800055b7  cmp     rbx, r10
0x1800055ba  mov     rdx, r10; DestinationSize
0x1800055bd  mov     rcx, rdi; Destination
0x1800055c0  cmovnb  rbx, r10
0x1800055c4  mov     r9, rbx; SourceSize
0x1800055c7  call    memcpy_s
0x1800055cc  mov     byte ptr [rbx+rdi-1], 0
0x1800055d1  mov     al, 1
0x1800055d3  add     rsp, 28h
0x1800055d7  pop     rdi
0x1800055d8  pop     rsi
0x1800055d9  pop     rbp
0x1800055da  pop     rbx
0x1800055db  retn
```
