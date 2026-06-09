# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x1800185c0`
- end: `0x18001869c`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180018180`
- `0x1800185c0`

## callees

- `0x180006620`
- `0x1800185c0`

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
0x1800185c0  push    rbx
0x1800185c2  push    rbp
0x1800185c3  push    rsi
0x1800185c4  push    rdi
0x1800185c5  sub     rsp, 28h
0x1800185c9  xor     al, al
0x1800185cb  mov     byte ptr [r8], 0
0x1800185cf  mov     rbp, r9
0x1800185d2  mov     rdi, r8
0x1800185d5  mov     rsi, rdx
0x1800185d8  mov     rbx, rcx
0x1800185db  test    rdx, rdx
0x1800185de  jz      loc_180018693
0x1800185e4  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x1800185e8  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800185ed  mov     rdx, [rsi+20h]
0x1800185f1  test    rdx, rdx
0x1800185f4  jz      loc_180018693
0x1800185fa  cmp     dword ptr [rdx], 0
0x1800185fd  jnz     short loc_180018610
0x1800185ff  mov     eax, 1
0x180018604  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18001860c  inc     eax
0x18001860e  mov     [rdx], eax
0x180018610  cmp     dword ptr [rbx+50h], 0
0x180018614  jnz     short loc_180018627
0x180018616  movups  xmm0, xmmword ptr [rdx]
0x180018619  movups  xmmword ptr [rbx+50h], xmm0
0x18001861d  movsd   xmm1, qword ptr [rdx+10h]
0x180018622  movsd   qword ptr [rbx+60h], xmm1
0x180018627  movups  xmm0, xmmword ptr [rdx]
0x18001862a  lea     r10, [rdi+rbp]
0x18001862e  movups  xmmword ptr [rbx+68h], xmm0
0x180018632  movsd   xmm1, qword ptr [rdx+10h]
0x180018637  movsd   qword ptr [rbx+78h], xmm1
0x18001863c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180018640  mov     rax, rbx
0x180018643  inc     rax
0x180018646  cmp     byte ptr [rdi+rax], 0
0x18001864a  jnz     short loc_180018643
0x18001864c  lea     rcx, [rax+rdi]
0x180018650  mov     rax, r10
0x180018653  sub     rax, rcx
0x180018656  cmp     rax, 2
0x18001865a  jle     short loc_180018691
0x18001865c  mov     byte ptr [rcx], 5Ch ; '\'
0x18001865f  lea     rdi, [rcx+1]
0x180018663  mov     r8, [rdx+8]; Source
0x180018667  inc     rbx
0x18001866a  cmp     byte ptr [r8+rbx], 0
0x18001866f  jnz     short loc_180018667
0x180018671  sub     r10, rdi
0x180018674  inc     rbx
0x180018677  cmp     rbx, r10
0x18001867a  mov     rdx, r10; DestinationSize
0x18001867d  mov     rcx, rdi; Destination
0x180018680  cmovnb  rbx, r10
0x180018684  mov     r9, rbx; SourceSize
0x180018687  call    memcpy_s
0x18001868c  mov     byte ptr [rbx+rdi-1], 0
0x180018691  mov     al, 1
0x180018693  add     rsp, 28h
0x180018697  pop     rdi
0x180018698  pop     rsi
0x180018699  pop     rbp
0x18001869a  pop     rbx
0x18001869b  retn
```
