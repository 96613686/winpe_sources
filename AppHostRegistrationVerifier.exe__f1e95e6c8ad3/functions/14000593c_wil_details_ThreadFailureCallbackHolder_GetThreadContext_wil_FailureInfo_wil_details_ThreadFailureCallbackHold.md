# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x14000593c`
- end: `0x140005a18`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140005234`
- `0x14000593c`

## callees

- `0x14000593c`
- `0x1400080c0`

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
0x14000593c  push    rbx
0x14000593e  push    rbp
0x14000593f  push    rsi
0x140005940  push    rdi
0x140005941  sub     rsp, 28h
0x140005945  xor     al, al
0x140005947  mov     byte ptr [r8], 0
0x14000594b  mov     rbp, r9
0x14000594e  mov     rdi, r8
0x140005951  mov     rsi, rdx
0x140005954  mov     rbx, rcx
0x140005957  test    rdx, rdx
0x14000595a  jz      loc_140005A0F
0x140005960  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140005964  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140005969  mov     rdx, [rsi+20h]
0x14000596d  test    rdx, rdx
0x140005970  jz      loc_140005A0F
0x140005976  cmp     dword ptr [rdx], 0
0x140005979  jnz     short loc_14000598C
0x14000597b  mov     eax, 1
0x140005980  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140005988  inc     eax
0x14000598a  mov     [rdx], eax
0x14000598c  cmp     dword ptr [rbx+50h], 0
0x140005990  jnz     short loc_1400059A3
0x140005992  movups  xmm0, xmmword ptr [rdx]
0x140005995  movups  xmmword ptr [rbx+50h], xmm0
0x140005999  movsd   xmm1, qword ptr [rdx+10h]
0x14000599e  movsd   qword ptr [rbx+60h], xmm1
0x1400059a3  movups  xmm0, xmmword ptr [rdx]
0x1400059a6  lea     r10, [rdi+rbp]
0x1400059aa  movups  xmmword ptr [rbx+68h], xmm0
0x1400059ae  movsd   xmm1, qword ptr [rdx+10h]
0x1400059b3  movsd   qword ptr [rbx+78h], xmm1
0x1400059b8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400059bc  mov     rax, rbx
0x1400059bf  inc     rax
0x1400059c2  cmp     byte ptr [rdi+rax], 0
0x1400059c6  jnz     short loc_1400059BF
0x1400059c8  lea     rcx, [rax+rdi]
0x1400059cc  mov     rax, r10
0x1400059cf  sub     rax, rcx
0x1400059d2  cmp     rax, 2
0x1400059d6  jle     short loc_140005A0D
0x1400059d8  mov     byte ptr [rcx], 5Ch ; '\'
0x1400059db  lea     rdi, [rcx+1]
0x1400059df  mov     r8, [rdx+8]; Source
0x1400059e3  inc     rbx
0x1400059e6  cmp     byte ptr [r8+rbx], 0
0x1400059eb  jnz     short loc_1400059E3
0x1400059ed  sub     r10, rdi
0x1400059f0  inc     rbx
0x1400059f3  cmp     rbx, r10
0x1400059f6  mov     rdx, r10; DestinationSize
0x1400059f9  mov     rcx, rdi; Destination
0x1400059fc  cmovnb  rbx, r10
0x140005a00  mov     r9, rbx; SourceSize
0x140005a03  call    memcpy_s
0x140005a08  mov     byte ptr [rbx+rdi-1], 0
0x140005a0d  mov     al, 1
0x140005a0f  add     rsp, 28h
0x140005a13  pop     rdi
0x140005a14  pop     rsi
0x140005a15  pop     rbp
0x140005a16  pop     rbx
0x140005a17  retn
```
