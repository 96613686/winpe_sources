# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180012cb8`
- end: `0x180012d9c`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `228`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180012640`
- `0x180012cb8`

## callees

- `0x180012cb8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180012d7f`
- `msvcrt!memcpy_s` at `0x180012d7f`

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
0x180012cb8  push    rbx
0x180012cba  push    rbp
0x180012cbb  push    rsi
0x180012cbc  push    rdi
0x180012cbd  sub     rsp, 28h
0x180012cc1  xor     al, al
0x180012cc3  mov     byte ptr [r8], 0
0x180012cc7  mov     rbp, r9
0x180012cca  mov     rdi, r8
0x180012ccd  mov     rsi, rdx
0x180012cd0  mov     rbx, rcx
0x180012cd3  test    rdx, rdx
0x180012cd6  jz      loc_180012D92
0x180012cdc  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180012ce0  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180012ce5  mov     rdx, [rsi+20h]
0x180012ce9  test    rdx, rdx
0x180012cec  jz      loc_180012D92
0x180012cf2  cmp     dword ptr [rdx], 0
0x180012cf5  jnz     short loc_180012D08
0x180012cf7  mov     eax, 1
0x180012cfc  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180012d04  inc     eax
0x180012d06  mov     [rdx], eax
0x180012d08  cmp     dword ptr [rbx+50h], 0
0x180012d0c  jnz     short loc_180012D1F
0x180012d0e  movups  xmm0, xmmword ptr [rdx]
0x180012d11  movups  xmmword ptr [rbx+50h], xmm0
0x180012d15  movsd   xmm1, qword ptr [rdx+10h]
0x180012d1a  movsd   qword ptr [rbx+60h], xmm1
0x180012d1f  movups  xmm0, xmmword ptr [rdx]
0x180012d22  lea     r10, [rdi+rbp]
0x180012d26  movups  xmmword ptr [rbx+68h], xmm0
0x180012d2a  movsd   xmm1, qword ptr [rdx+10h]
0x180012d2f  movsd   qword ptr [rbx+78h], xmm1
0x180012d34  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180012d38  mov     rax, rbx
0x180012d3b  inc     rax
0x180012d3e  cmp     byte ptr [rdi+rax], 0
0x180012d42  jnz     short loc_180012D3B
0x180012d44  lea     rcx, [rax+rdi]
0x180012d48  mov     rax, r10
0x180012d4b  sub     rax, rcx
0x180012d4e  cmp     rax, 2
0x180012d52  jle     short loc_180012D90
0x180012d54  mov     byte ptr [rcx], 5Ch ; '\'
0x180012d57  lea     rdi, [rcx+1]
0x180012d5b  mov     r8, [rdx+8]; Source
0x180012d5f  inc     rbx
0x180012d62  cmp     byte ptr [r8+rbx], 0
0x180012d67  jnz     short loc_180012D5F
0x180012d69  sub     r10, rdi
0x180012d6c  inc     rbx
0x180012d6f  cmp     rbx, r10
0x180012d72  mov     rdx, r10; DestinationSize
0x180012d75  mov     rcx, rdi; Destination
0x180012d78  cmovnb  rbx, r10
0x180012d7c  mov     r9, rbx; SourceSize
0x180012d7f  call    cs:__imp_memcpy_s
0x180012d86  nop     dword ptr [rax+rax+00h]
0x180012d8b  mov     byte ptr [rbx+rdi-1], 0
0x180012d90  mov     al, 1
0x180012d92  add     rsp, 28h
0x180012d96  pop     rdi
0x180012d97  pop     rsi
0x180012d98  pop     rbp
0x180012d99  pop     rbx
0x180012d9a  retn
```
