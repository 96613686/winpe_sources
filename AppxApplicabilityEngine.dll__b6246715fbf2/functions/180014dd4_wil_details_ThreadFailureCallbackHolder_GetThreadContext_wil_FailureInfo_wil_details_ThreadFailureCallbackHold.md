# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180014dd4`
- end: `0x180014eb1`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800147f8`
- `0x180014dd4`

## callees

- `0x180014dd4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180014e9b`
- `msvcrt!memcpy_s` at `0x180014e9b`

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
0x180014dd4  push    rbx
0x180014dd6  push    rbp
0x180014dd7  push    rsi
0x180014dd8  push    rdi
0x180014dd9  sub     rsp, 28h
0x180014ddd  xor     al, al
0x180014ddf  mov     byte ptr [r8], 0
0x180014de3  mov     rbp, r9
0x180014de6  mov     rdi, r8
0x180014de9  mov     rsi, rdx
0x180014dec  mov     rbx, rcx
0x180014def  test    rdx, rdx
0x180014df2  jz      loc_180014EA8
0x180014df8  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180014dfc  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180014e01  mov     rdx, [rsi+20h]
0x180014e05  test    rdx, rdx
0x180014e08  jz      loc_180014EA8
0x180014e0e  cmp     dword ptr [rdx], 0
0x180014e11  jnz     short loc_180014E24
0x180014e13  mov     eax, 1
0x180014e18  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180014e20  inc     eax
0x180014e22  mov     [rdx], eax
0x180014e24  cmp     dword ptr [rbx+50h], 0
0x180014e28  jnz     short loc_180014E3B
0x180014e2a  movups  xmm0, xmmword ptr [rdx]
0x180014e2d  movups  xmmword ptr [rbx+50h], xmm0
0x180014e31  movsd   xmm1, qword ptr [rdx+10h]
0x180014e36  movsd   qword ptr [rbx+60h], xmm1
0x180014e3b  movups  xmm0, xmmword ptr [rdx]
0x180014e3e  lea     r10, [rdi+rbp]
0x180014e42  movups  xmmword ptr [rbx+68h], xmm0
0x180014e46  movsd   xmm1, qword ptr [rdx+10h]
0x180014e4b  movsd   qword ptr [rbx+78h], xmm1
0x180014e50  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180014e54  mov     rax, rbx
0x180014e57  inc     rax
0x180014e5a  cmp     byte ptr [rdi+rax], 0
0x180014e5e  jnz     short loc_180014E57
0x180014e60  lea     rcx, [rax+rdi]
0x180014e64  mov     rax, r10
0x180014e67  sub     rax, rcx
0x180014e6a  cmp     rax, 2
0x180014e6e  jle     short loc_180014EA6
0x180014e70  mov     byte ptr [rcx], 5Ch ; '\'
0x180014e73  lea     rdi, [rcx+1]
0x180014e77  mov     r8, [rdx+8]; Source
0x180014e7b  inc     rbx
0x180014e7e  cmp     byte ptr [r8+rbx], 0
0x180014e83  jnz     short loc_180014E7B
0x180014e85  sub     r10, rdi
0x180014e88  inc     rbx
0x180014e8b  cmp     rbx, r10
0x180014e8e  mov     rdx, r10; DestinationSize
0x180014e91  mov     rcx, rdi; Destination
0x180014e94  cmovnb  rbx, r10
0x180014e98  mov     r9, rbx; SourceSize
0x180014e9b  call    cs:__imp_memcpy_s
0x180014ea1  mov     byte ptr [rbx+rdi-1], 0
0x180014ea6  mov     al, 1
0x180014ea8  add     rsp, 28h
0x180014eac  pop     rdi
0x180014ead  pop     rsi
0x180014eae  pop     rbp
0x180014eaf  pop     rbx
0x180014eb0  retn
```
