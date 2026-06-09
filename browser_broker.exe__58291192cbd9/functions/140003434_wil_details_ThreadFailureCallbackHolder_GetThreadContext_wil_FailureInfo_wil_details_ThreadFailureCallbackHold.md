# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140003434`
- end: `0x140003510`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140002dd4`
- `0x140003434`

## callees

- `0x140003434`
- `0x140004bb8`

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
0x140003434  push    rbx
0x140003436  push    rbp
0x140003437  push    rsi
0x140003438  push    rdi
0x140003439  sub     rsp, 28h
0x14000343d  xor     al, al
0x14000343f  mov     byte ptr [r8], 0
0x140003443  mov     rbp, r9
0x140003446  mov     rdi, r8
0x140003449  mov     rsi, rdx
0x14000344c  mov     rbx, rcx
0x14000344f  test    rdx, rdx
0x140003452  jz      loc_140003507
0x140003458  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x14000345c  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140003461  mov     rdx, [rsi+20h]
0x140003465  test    rdx, rdx
0x140003468  jz      loc_140003507
0x14000346e  cmp     dword ptr [rdx], 0
0x140003471  jnz     short loc_140003484
0x140003473  mov     eax, 1
0x140003478  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140003480  inc     eax
0x140003482  mov     [rdx], eax
0x140003484  cmp     dword ptr [rbx+50h], 0
0x140003488  jnz     short loc_14000349B
0x14000348a  movups  xmm0, xmmword ptr [rdx]
0x14000348d  movups  xmmword ptr [rbx+50h], xmm0
0x140003491  movsd   xmm1, qword ptr [rdx+10h]
0x140003496  movsd   qword ptr [rbx+60h], xmm1
0x14000349b  movups  xmm0, xmmword ptr [rdx]
0x14000349e  lea     r10, [rdi+rbp]
0x1400034a2  movups  xmmword ptr [rbx+68h], xmm0
0x1400034a6  movsd   xmm1, qword ptr [rdx+10h]
0x1400034ab  movsd   qword ptr [rbx+78h], xmm1
0x1400034b0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400034b4  mov     rax, rbx
0x1400034b7  inc     rax
0x1400034ba  cmp     byte ptr [rdi+rax], 0
0x1400034be  jnz     short loc_1400034B7
0x1400034c0  lea     rcx, [rax+rdi]
0x1400034c4  mov     rax, r10
0x1400034c7  sub     rax, rcx
0x1400034ca  cmp     rax, 2
0x1400034ce  jle     short loc_140003505
0x1400034d0  mov     byte ptr [rcx], 5Ch ; '\'
0x1400034d3  lea     rdi, [rcx+1]
0x1400034d7  mov     r8, [rdx+8]; Source
0x1400034db  inc     rbx
0x1400034de  cmp     byte ptr [r8+rbx], 0
0x1400034e3  jnz     short loc_1400034DB
0x1400034e5  sub     r10, rdi
0x1400034e8  inc     rbx
0x1400034eb  cmp     rbx, r10
0x1400034ee  mov     rdx, r10; DestinationSize
0x1400034f1  mov     rcx, rdi; Destination
0x1400034f4  cmovnb  rbx, r10
0x1400034f8  mov     r9, rbx; SourceSize
0x1400034fb  call    memcpy_s
0x140003500  mov     byte ptr [rbx+rdi-1], 0
0x140003505  mov     al, 1
0x140003507  add     rsp, 28h
0x14000350b  pop     rdi
0x14000350c  pop     rsi
0x14000350d  pop     rbp
0x14000350e  pop     rbx
0x14000350f  retn
```
