# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18001261c`
- end: `0x1800126f9`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180011fe0`
- `0x18001261c`

## callees

- `0x18001261c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800126e3`
- `msvcrt!memcpy_s` at `0x1800126e3`

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
0x18001261c  push    rbx
0x18001261e  push    rbp
0x18001261f  push    rsi
0x180012620  push    rdi
0x180012621  sub     rsp, 28h
0x180012625  xor     al, al
0x180012627  mov     byte ptr [r8], 0
0x18001262b  mov     rbp, r9
0x18001262e  mov     rdi, r8
0x180012631  mov     rsi, rdx
0x180012634  mov     rbx, rcx
0x180012637  test    rdx, rdx
0x18001263a  jz      loc_1800126F0
0x180012640  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180012644  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180012649  mov     rdx, [rsi+20h]
0x18001264d  test    rdx, rdx
0x180012650  jz      loc_1800126F0
0x180012656  cmp     dword ptr [rdx], 0
0x180012659  jnz     short loc_18001266C
0x18001265b  mov     eax, 1
0x180012660  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180012668  inc     eax
0x18001266a  mov     [rdx], eax
0x18001266c  cmp     dword ptr [rbx+50h], 0
0x180012670  jnz     short loc_180012683
0x180012672  movups  xmm0, xmmword ptr [rdx]
0x180012675  movups  xmmword ptr [rbx+50h], xmm0
0x180012679  movsd   xmm1, qword ptr [rdx+10h]
0x18001267e  movsd   qword ptr [rbx+60h], xmm1
0x180012683  movups  xmm0, xmmword ptr [rdx]
0x180012686  lea     r10, [rdi+rbp]
0x18001268a  movups  xmmword ptr [rbx+68h], xmm0
0x18001268e  movsd   xmm1, qword ptr [rdx+10h]
0x180012693  movsd   qword ptr [rbx+78h], xmm1
0x180012698  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001269c  mov     rax, rbx
0x18001269f  inc     rax
0x1800126a2  cmp     byte ptr [rdi+rax], 0
0x1800126a6  jnz     short loc_18001269F
0x1800126a8  lea     rcx, [rax+rdi]
0x1800126ac  mov     rax, r10
0x1800126af  sub     rax, rcx
0x1800126b2  cmp     rax, 2
0x1800126b6  jle     short loc_1800126EE
0x1800126b8  mov     byte ptr [rcx], 5Ch ; '\'
0x1800126bb  lea     rdi, [rcx+1]
0x1800126bf  mov     r8, [rdx+8]; Source
0x1800126c3  inc     rbx
0x1800126c6  cmp     byte ptr [r8+rbx], 0
0x1800126cb  jnz     short loc_1800126C3
0x1800126cd  sub     r10, rdi
0x1800126d0  inc     rbx
0x1800126d3  cmp     rbx, r10
0x1800126d6  mov     rdx, r10; DestinationSize
0x1800126d9  mov     rcx, rdi; Destination
0x1800126dc  cmovnb  rbx, r10
0x1800126e0  mov     r9, rbx; SourceSize
0x1800126e3  call    cs:__imp_memcpy_s
0x1800126e9  mov     byte ptr [rbx+rdi-1], 0
0x1800126ee  mov     al, 1
0x1800126f0  add     rsp, 28h
0x1800126f4  pop     rdi
0x1800126f5  pop     rsi
0x1800126f6  pop     rbp
0x1800126f7  pop     rbx
0x1800126f8  retn
```
