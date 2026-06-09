# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000573c`
- end: `0x180005818`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005040`
- `0x18000573c`

## callees

- `0x18000573c`
- `0x180008b08`

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
0x18000573c  push    rbx
0x18000573e  push    rbp
0x18000573f  push    rsi
0x180005740  push    rdi
0x180005741  sub     rsp, 28h
0x180005745  xor     al, al
0x180005747  mov     byte ptr [r8], 0
0x18000574b  mov     rbp, r9
0x18000574e  mov     rdi, r8
0x180005751  mov     rsi, rdx
0x180005754  mov     rbx, rcx
0x180005757  test    rdx, rdx
0x18000575a  jz      loc_18000580F
0x180005760  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180005764  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005769  mov     rdx, [rsi+20h]
0x18000576d  test    rdx, rdx
0x180005770  jz      loc_18000580F
0x180005776  cmp     dword ptr [rdx], 0
0x180005779  jnz     short loc_18000578C
0x18000577b  mov     eax, 1
0x180005780  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180005788  inc     eax
0x18000578a  mov     [rdx], eax
0x18000578c  cmp     dword ptr [rbx+50h], 0
0x180005790  jnz     short loc_1800057A3
0x180005792  movups  xmm0, xmmword ptr [rdx]
0x180005795  movups  xmmword ptr [rbx+50h], xmm0
0x180005799  movsd   xmm1, qword ptr [rdx+10h]
0x18000579e  movsd   qword ptr [rbx+60h], xmm1
0x1800057a3  movups  xmm0, xmmword ptr [rdx]
0x1800057a6  lea     r10, [rdi+rbp]
0x1800057aa  movups  xmmword ptr [rbx+68h], xmm0
0x1800057ae  movsd   xmm1, qword ptr [rdx+10h]
0x1800057b3  movsd   qword ptr [rbx+78h], xmm1
0x1800057b8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800057bc  mov     rax, rbx
0x1800057bf  inc     rax
0x1800057c2  cmp     byte ptr [rdi+rax], 0
0x1800057c6  jnz     short loc_1800057BF
0x1800057c8  lea     rcx, [rax+rdi]
0x1800057cc  mov     rax, r10
0x1800057cf  sub     rax, rcx
0x1800057d2  cmp     rax, 2
0x1800057d6  jle     short loc_18000580D
0x1800057d8  mov     byte ptr [rcx], 5Ch ; '\'
0x1800057db  lea     rdi, [rcx+1]
0x1800057df  mov     r8, [rdx+8]; Source
0x1800057e3  inc     rbx
0x1800057e6  cmp     byte ptr [r8+rbx], 0
0x1800057eb  jnz     short loc_1800057E3
0x1800057ed  sub     r10, rdi
0x1800057f0  inc     rbx
0x1800057f3  cmp     rbx, r10
0x1800057f6  mov     rdx, r10; DestinationSize
0x1800057f9  mov     rcx, rdi; Destination
0x1800057fc  cmovnb  rbx, r10
0x180005800  mov     r9, rbx; SourceSize
0x180005803  call    memcpy_s
0x180005808  mov     byte ptr [rbx+rdi-1], 0
0x18000580d  mov     al, 1
0x18000580f  add     rsp, 28h
0x180005813  pop     rdi
0x180005814  pop     rsi
0x180005815  pop     rbp
0x180005816  pop     rbx
0x180005817  retn
```
