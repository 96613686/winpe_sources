# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180003d80`
- end: `0x180003e64`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `228`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800036e4`
- `0x180003d80`

## callees

- `0x180003d80`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180003e47`
- `msvcrt!memcpy_s` at `0x180003e47`

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
0x180003d80  push    rbx
0x180003d82  push    rbp
0x180003d83  push    rsi
0x180003d84  push    rdi
0x180003d85  sub     rsp, 28h
0x180003d89  xor     al, al
0x180003d8b  mov     byte ptr [r8], 0
0x180003d8f  mov     rbp, r9
0x180003d92  mov     rdi, r8
0x180003d95  mov     rsi, rdx
0x180003d98  mov     rbx, rcx
0x180003d9b  test    rdx, rdx
0x180003d9e  jz      loc_180003E5A
0x180003da4  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180003da8  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180003dad  mov     rdx, [rsi+20h]
0x180003db1  test    rdx, rdx
0x180003db4  jz      loc_180003E5A
0x180003dba  cmp     dword ptr [rdx], 0
0x180003dbd  jnz     short loc_180003DD0
0x180003dbf  mov     eax, 1
0x180003dc4  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180003dcc  inc     eax
0x180003dce  mov     [rdx], eax
0x180003dd0  cmp     dword ptr [rbx+50h], 0
0x180003dd4  jnz     short loc_180003DE7
0x180003dd6  movups  xmm0, xmmword ptr [rdx]
0x180003dd9  movups  xmmword ptr [rbx+50h], xmm0
0x180003ddd  movsd   xmm1, qword ptr [rdx+10h]
0x180003de2  movsd   qword ptr [rbx+60h], xmm1
0x180003de7  movups  xmm0, xmmword ptr [rdx]
0x180003dea  lea     r10, [rdi+rbp]
0x180003dee  movups  xmmword ptr [rbx+68h], xmm0
0x180003df2  movsd   xmm1, qword ptr [rdx+10h]
0x180003df7  movsd   qword ptr [rbx+78h], xmm1
0x180003dfc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180003e00  mov     rax, rbx
0x180003e03  inc     rax
0x180003e06  cmp     byte ptr [rdi+rax], 0
0x180003e0a  jnz     short loc_180003E03
0x180003e0c  lea     rcx, [rax+rdi]
0x180003e10  mov     rax, r10
0x180003e13  sub     rax, rcx
0x180003e16  cmp     rax, 2
0x180003e1a  jle     short loc_180003E58
0x180003e1c  mov     byte ptr [rcx], 5Ch ; '\'
0x180003e1f  lea     rdi, [rcx+1]
0x180003e23  mov     r8, [rdx+8]; Source
0x180003e27  inc     rbx
0x180003e2a  cmp     byte ptr [r8+rbx], 0
0x180003e2f  jnz     short loc_180003E27
0x180003e31  sub     r10, rdi
0x180003e34  inc     rbx
0x180003e37  cmp     rbx, r10
0x180003e3a  mov     rdx, r10; DestinationSize
0x180003e3d  mov     rcx, rdi; Destination
0x180003e40  cmovnb  rbx, r10
0x180003e44  mov     r9, rbx; SourceSize
0x180003e47  call    cs:__imp_memcpy_s
0x180003e4e  nop     dword ptr [rax+rax+00h]
0x180003e53  mov     byte ptr [rbx+rdi-1], 0
0x180003e58  mov     al, 1
0x180003e5a  add     rsp, 28h
0x180003e5e  pop     rdi
0x180003e5f  pop     rsi
0x180003e60  pop     rbp
0x180003e61  pop     rbx
0x180003e62  retn
```
