# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180012c28`
- end: `0x180012d05`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800124c4`
- `0x180012c28`

## callees

- `0x180012c28`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180012cef`
- `msvcrt!memcpy_s` at `0x180012cef`

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
0x180012c28  push    rbx
0x180012c2a  push    rbp
0x180012c2b  push    rsi
0x180012c2c  push    rdi
0x180012c2d  sub     rsp, 28h
0x180012c31  xor     al, al
0x180012c33  mov     byte ptr [r8], 0
0x180012c37  mov     rbp, r9
0x180012c3a  mov     rdi, r8
0x180012c3d  mov     rsi, rdx
0x180012c40  mov     rbx, rcx
0x180012c43  test    rdx, rdx
0x180012c46  jz      loc_180012CFC
0x180012c4c  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180012c50  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180012c55  mov     rdx, [rsi+20h]
0x180012c59  test    rdx, rdx
0x180012c5c  jz      loc_180012CFC
0x180012c62  cmp     dword ptr [rdx], 0
0x180012c65  jnz     short loc_180012C78
0x180012c67  mov     eax, 1
0x180012c6c  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180012c74  inc     eax
0x180012c76  mov     [rdx], eax
0x180012c78  cmp     dword ptr [rbx+50h], 0
0x180012c7c  jnz     short loc_180012C8F
0x180012c7e  movups  xmm0, xmmword ptr [rdx]
0x180012c81  movups  xmmword ptr [rbx+50h], xmm0
0x180012c85  movsd   xmm1, qword ptr [rdx+10h]
0x180012c8a  movsd   qword ptr [rbx+60h], xmm1
0x180012c8f  movups  xmm0, xmmword ptr [rdx]
0x180012c92  lea     r10, [rdi+rbp]
0x180012c96  movups  xmmword ptr [rbx+68h], xmm0
0x180012c9a  movsd   xmm1, qword ptr [rdx+10h]
0x180012c9f  movsd   qword ptr [rbx+78h], xmm1
0x180012ca4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180012ca8  mov     rax, rbx
0x180012cab  inc     rax
0x180012cae  cmp     byte ptr [rdi+rax], 0
0x180012cb2  jnz     short loc_180012CAB
0x180012cb4  lea     rcx, [rax+rdi]
0x180012cb8  mov     rax, r10
0x180012cbb  sub     rax, rcx
0x180012cbe  cmp     rax, 2
0x180012cc2  jle     short loc_180012CFA
0x180012cc4  mov     byte ptr [rcx], 5Ch ; '\'
0x180012cc7  lea     rdi, [rcx+1]
0x180012ccb  mov     r8, [rdx+8]; Source
0x180012ccf  inc     rbx
0x180012cd2  cmp     byte ptr [r8+rbx], 0
0x180012cd7  jnz     short loc_180012CCF
0x180012cd9  sub     r10, rdi
0x180012cdc  inc     rbx
0x180012cdf  cmp     rbx, r10
0x180012ce2  mov     rdx, r10; DestinationSize
0x180012ce5  mov     rcx, rdi; Destination
0x180012ce8  cmovnb  rbx, r10
0x180012cec  mov     r9, rbx; SourceSize
0x180012cef  call    cs:__imp_memcpy_s
0x180012cf5  mov     byte ptr [rbx+rdi-1], 0
0x180012cfa  mov     al, 1
0x180012cfc  add     rsp, 28h
0x180012d00  pop     rdi
0x180012d01  pop     rsi
0x180012d02  pop     rbp
0x180012d03  pop     rbx
0x180012d04  retn
```
