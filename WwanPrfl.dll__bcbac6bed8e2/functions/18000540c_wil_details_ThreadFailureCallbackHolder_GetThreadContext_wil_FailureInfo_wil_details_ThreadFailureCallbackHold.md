# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000540c`
- end: `0x1800054e8`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004d10`
- `0x18000540c`

## callees

- `0x18000540c`
- `0x18000e674`

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
        memcpy_s_0(v18, v16, v15, v17);
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
0x18000540c  push    rbx
0x18000540e  push    rbp
0x18000540f  push    rsi
0x180005410  push    rdi
0x180005411  sub     rsp, 28h
0x180005415  xor     al, al
0x180005417  mov     byte ptr [r8], 0
0x18000541b  mov     rbp, r9
0x18000541e  mov     rdi, r8
0x180005421  mov     rsi, rdx
0x180005424  mov     rbx, rcx
0x180005427  test    rdx, rdx
0x18000542a  jz      loc_1800054DF
0x180005430  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180005434  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005439  mov     rdx, [rsi+20h]
0x18000543d  test    rdx, rdx
0x180005440  jz      loc_1800054DF
0x180005446  cmp     dword ptr [rdx], 0
0x180005449  jnz     short loc_18000545C
0x18000544b  mov     eax, 1
0x180005450  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180005458  inc     eax
0x18000545a  mov     [rdx], eax
0x18000545c  cmp     dword ptr [rbx+50h], 0
0x180005460  jnz     short loc_180005473
0x180005462  movups  xmm0, xmmword ptr [rdx]
0x180005465  movups  xmmword ptr [rbx+50h], xmm0
0x180005469  movsd   xmm1, qword ptr [rdx+10h]
0x18000546e  movsd   qword ptr [rbx+60h], xmm1
0x180005473  movups  xmm0, xmmword ptr [rdx]
0x180005476  lea     r10, [rdi+rbp]
0x18000547a  movups  xmmword ptr [rbx+68h], xmm0
0x18000547e  movsd   xmm1, qword ptr [rdx+10h]
0x180005483  movsd   qword ptr [rbx+78h], xmm1
0x180005488  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000548c  mov     rax, rbx
0x18000548f  inc     rax
0x180005492  cmp     byte ptr [rdi+rax], 0
0x180005496  jnz     short loc_18000548F
0x180005498  lea     rcx, [rax+rdi]
0x18000549c  mov     rax, r10
0x18000549f  sub     rax, rcx
0x1800054a2  cmp     rax, 2
0x1800054a6  jle     short loc_1800054DD
0x1800054a8  mov     byte ptr [rcx], 5Ch ; '\'
0x1800054ab  lea     rdi, [rcx+1]
0x1800054af  mov     r8, [rdx+8]; Source
0x1800054b3  inc     rbx
0x1800054b6  cmp     byte ptr [r8+rbx], 0
0x1800054bb  jnz     short loc_1800054B3
0x1800054bd  sub     r10, rdi
0x1800054c0  inc     rbx
0x1800054c3  cmp     rbx, r10
0x1800054c6  mov     rdx, r10; DestinationSize
0x1800054c9  mov     rcx, rdi; Destination
0x1800054cc  cmovnb  rbx, r10
0x1800054d0  mov     r9, rbx; SourceSize
0x1800054d3  call    memcpy_s_0
0x1800054d8  mov     byte ptr [rbx+rdi-1], 0
0x1800054dd  mov     al, 1
0x1800054df  add     rsp, 28h
0x1800054e3  pop     rdi
0x1800054e4  pop     rsi
0x1800054e5  pop     rbp
0x1800054e6  pop     rbx
0x1800054e7  retn
```
