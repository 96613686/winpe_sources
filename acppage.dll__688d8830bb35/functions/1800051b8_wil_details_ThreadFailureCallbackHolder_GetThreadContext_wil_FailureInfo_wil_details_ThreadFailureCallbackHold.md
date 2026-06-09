# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x1800051b8`
- end: `0x180005295`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004a30`
- `0x1800051b8`

## callees

- `0x1800051b8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000527f`
- `msvcrt!memcpy_s` at `0x18000527f`

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
0x1800051b8  push    rbx
0x1800051ba  push    rbp
0x1800051bb  push    rsi
0x1800051bc  push    rdi
0x1800051bd  sub     rsp, 28h
0x1800051c1  xor     al, al
0x1800051c3  mov     byte ptr [r8], 0
0x1800051c7  mov     rbp, r9
0x1800051ca  mov     rdi, r8
0x1800051cd  mov     rsi, rdx
0x1800051d0  mov     rbx, rcx
0x1800051d3  test    rdx, rdx
0x1800051d6  jz      loc_18000528C
0x1800051dc  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x1800051e0  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800051e5  mov     rdx, [rsi+20h]
0x1800051e9  test    rdx, rdx
0x1800051ec  jz      loc_18000528C
0x1800051f2  cmp     dword ptr [rdx], 0
0x1800051f5  jnz     short loc_180005208
0x1800051f7  mov     eax, 1
0x1800051fc  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180005204  inc     eax
0x180005206  mov     [rdx], eax
0x180005208  cmp     dword ptr [rbx+50h], 0
0x18000520c  jnz     short loc_18000521F
0x18000520e  movups  xmm0, xmmword ptr [rdx]
0x180005211  movups  xmmword ptr [rbx+50h], xmm0
0x180005215  movsd   xmm1, qword ptr [rdx+10h]
0x18000521a  movsd   qword ptr [rbx+60h], xmm1
0x18000521f  movups  xmm0, xmmword ptr [rdx]
0x180005222  lea     r10, [rdi+rbp]
0x180005226  movups  xmmword ptr [rbx+68h], xmm0
0x18000522a  movsd   xmm1, qword ptr [rdx+10h]
0x18000522f  movsd   qword ptr [rbx+78h], xmm1
0x180005234  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005238  mov     rax, rbx
0x18000523b  inc     rax
0x18000523e  cmp     byte ptr [rdi+rax], 0
0x180005242  jnz     short loc_18000523B
0x180005244  lea     rcx, [rax+rdi]
0x180005248  mov     rax, r10
0x18000524b  sub     rax, rcx
0x18000524e  cmp     rax, 2
0x180005252  jle     short loc_18000528A
0x180005254  mov     byte ptr [rcx], 5Ch ; '\'
0x180005257  lea     rdi, [rcx+1]
0x18000525b  mov     r8, [rdx+8]; Source
0x18000525f  inc     rbx
0x180005262  cmp     byte ptr [r8+rbx], 0
0x180005267  jnz     short loc_18000525F
0x180005269  sub     r10, rdi
0x18000526c  inc     rbx
0x18000526f  cmp     rbx, r10
0x180005272  mov     rdx, r10; DestinationSize
0x180005275  mov     rcx, rdi; Destination
0x180005278  cmovnb  rbx, r10
0x18000527c  mov     r9, rbx; SourceSize
0x18000527f  call    cs:__imp_memcpy_s
0x180005285  mov     byte ptr [rbx+rdi-1], 0
0x18000528a  mov     al, 1
0x18000528c  add     rsp, 28h
0x180005290  pop     rdi
0x180005291  pop     rsi
0x180005292  pop     rbp
0x180005293  pop     rbx
0x180005294  retn
```
