# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180008148`
- end: `0x180008224`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007b48`
- `0x180008148`

## callees

- `0x180008148`
- `0x18000af04`

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
0x180008148  push    rbx
0x18000814a  push    rbp
0x18000814b  push    rsi
0x18000814c  push    rdi
0x18000814d  sub     rsp, 28h
0x180008151  xor     al, al
0x180008153  mov     byte ptr [r8], 0
0x180008157  mov     rbp, r9
0x18000815a  mov     rdi, r8
0x18000815d  mov     rsi, rdx
0x180008160  mov     rbx, rcx
0x180008163  test    rdx, rdx
0x180008166  jz      loc_18000821B
0x18000816c  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180008170  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180008175  mov     rdx, [rsi+20h]
0x180008179  test    rdx, rdx
0x18000817c  jz      loc_18000821B
0x180008182  cmp     dword ptr [rdx], 0
0x180008185  jnz     short loc_180008198
0x180008187  mov     eax, 1
0x18000818c  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180008194  inc     eax
0x180008196  mov     [rdx], eax
0x180008198  cmp     dword ptr [rbx+50h], 0
0x18000819c  jnz     short loc_1800081AF
0x18000819e  movups  xmm0, xmmword ptr [rdx]
0x1800081a1  movups  xmmword ptr [rbx+50h], xmm0
0x1800081a5  movsd   xmm1, qword ptr [rdx+10h]
0x1800081aa  movsd   qword ptr [rbx+60h], xmm1
0x1800081af  movups  xmm0, xmmword ptr [rdx]
0x1800081b2  lea     r10, [rdi+rbp]
0x1800081b6  movups  xmmword ptr [rbx+68h], xmm0
0x1800081ba  movsd   xmm1, qword ptr [rdx+10h]
0x1800081bf  movsd   qword ptr [rbx+78h], xmm1
0x1800081c4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800081c8  mov     rax, rbx
0x1800081cb  inc     rax
0x1800081ce  cmp     byte ptr [rdi+rax], 0
0x1800081d2  jnz     short loc_1800081CB
0x1800081d4  lea     rcx, [rax+rdi]
0x1800081d8  mov     rax, r10
0x1800081db  sub     rax, rcx
0x1800081de  cmp     rax, 2
0x1800081e2  jle     short loc_180008219
0x1800081e4  mov     byte ptr [rcx], 5Ch ; '\'
0x1800081e7  lea     rdi, [rcx+1]
0x1800081eb  mov     r8, [rdx+8]; Source
0x1800081ef  inc     rbx
0x1800081f2  cmp     byte ptr [r8+rbx], 0
0x1800081f7  jnz     short loc_1800081EF
0x1800081f9  sub     r10, rdi
0x1800081fc  inc     rbx
0x1800081ff  cmp     rbx, r10
0x180008202  mov     rdx, r10; DestinationSize
0x180008205  mov     rcx, rdi; Destination
0x180008208  cmovnb  rbx, r10
0x18000820c  mov     r9, rbx; SourceSize
0x18000820f  call    memcpy_s
0x180008214  mov     byte ptr [rbx+rdi-1], 0
0x180008219  mov     al, 1
0x18000821b  add     rsp, 28h
0x18000821f  pop     rdi
0x180008220  pop     rsi
0x180008221  pop     rbp
0x180008222  pop     rbx
0x180008223  retn
```
