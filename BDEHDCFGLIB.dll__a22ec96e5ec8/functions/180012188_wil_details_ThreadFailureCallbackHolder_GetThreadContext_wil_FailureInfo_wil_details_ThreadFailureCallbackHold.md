# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180012188`
- end: `0x180012265`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180011a90`
- `0x180012188`

## callees

- `0x180012188`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001224f`
- `msvcrt!memcpy_s` at `0x18001224f`

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
0x180012188  push    rbx
0x18001218a  push    rbp
0x18001218b  push    rsi
0x18001218c  push    rdi
0x18001218d  sub     rsp, 28h
0x180012191  xor     al, al
0x180012193  mov     byte ptr [r8], 0
0x180012197  mov     rbp, r9
0x18001219a  mov     rdi, r8
0x18001219d  mov     rsi, rdx
0x1800121a0  mov     rbx, rcx
0x1800121a3  test    rdx, rdx
0x1800121a6  jz      loc_18001225C
0x1800121ac  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x1800121b0  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800121b5  mov     rdx, [rsi+20h]
0x1800121b9  test    rdx, rdx
0x1800121bc  jz      loc_18001225C
0x1800121c2  cmp     dword ptr [rdx], 0
0x1800121c5  jnz     short loc_1800121D8
0x1800121c7  mov     eax, 1
0x1800121cc  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x1800121d4  inc     eax
0x1800121d6  mov     [rdx], eax
0x1800121d8  cmp     dword ptr [rbx+50h], 0
0x1800121dc  jnz     short loc_1800121EF
0x1800121de  movups  xmm0, xmmword ptr [rdx]
0x1800121e1  movups  xmmword ptr [rbx+50h], xmm0
0x1800121e5  movsd   xmm1, qword ptr [rdx+10h]
0x1800121ea  movsd   qword ptr [rbx+60h], xmm1
0x1800121ef  movups  xmm0, xmmword ptr [rdx]
0x1800121f2  lea     r10, [rdi+rbp]
0x1800121f6  movups  xmmword ptr [rbx+68h], xmm0
0x1800121fa  movsd   xmm1, qword ptr [rdx+10h]
0x1800121ff  movsd   qword ptr [rbx+78h], xmm1
0x180012204  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180012208  mov     rax, rbx
0x18001220b  inc     rax
0x18001220e  cmp     byte ptr [rdi+rax], 0
0x180012212  jnz     short loc_18001220B
0x180012214  lea     rcx, [rax+rdi]
0x180012218  mov     rax, r10
0x18001221b  sub     rax, rcx
0x18001221e  cmp     rax, 2
0x180012222  jle     short loc_18001225A
0x180012224  mov     byte ptr [rcx], 5Ch ; '\'
0x180012227  lea     rdi, [rcx+1]
0x18001222b  mov     r8, [rdx+8]; Source
0x18001222f  inc     rbx
0x180012232  cmp     byte ptr [r8+rbx], 0
0x180012237  jnz     short loc_18001222F
0x180012239  sub     r10, rdi
0x18001223c  inc     rbx
0x18001223f  cmp     rbx, r10
0x180012242  mov     rdx, r10; DestinationSize
0x180012245  mov     rcx, rdi; Destination
0x180012248  cmovnb  rbx, r10
0x18001224c  mov     r9, rbx; SourceSize
0x18001224f  call    cs:__imp_memcpy_s
0x180012255  mov     byte ptr [rbx+rdi-1], 0
0x18001225a  mov     al, 1
0x18001225c  add     rsp, 28h
0x180012260  pop     rdi
0x180012261  pop     rsi
0x180012262  pop     rbp
0x180012263  pop     rbx
0x180012264  retn
```
