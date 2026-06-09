# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180008bb0`
- end: `0x180008c8c`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800081c0`
- `0x180008bb0`

## callees

- `0x180008bb0`
- `0x18000fbf8`

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
0x180008bb0  push    rbx
0x180008bb2  push    rbp
0x180008bb3  push    rsi
0x180008bb4  push    rdi
0x180008bb5  sub     rsp, 28h
0x180008bb9  xor     al, al
0x180008bbb  mov     byte ptr [r8], 0
0x180008bbf  mov     rbp, r9
0x180008bc2  mov     rdi, r8
0x180008bc5  mov     rsi, rdx
0x180008bc8  mov     rbx, rcx
0x180008bcb  test    rdx, rdx
0x180008bce  jz      loc_180008C83
0x180008bd4  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180008bd8  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180008bdd  mov     rdx, [rsi+20h]
0x180008be1  test    rdx, rdx
0x180008be4  jz      loc_180008C83
0x180008bea  cmp     dword ptr [rdx], 0
0x180008bed  jnz     short loc_180008C00
0x180008bef  mov     eax, 1
0x180008bf4  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180008bfc  inc     eax
0x180008bfe  mov     [rdx], eax
0x180008c00  cmp     dword ptr [rbx+50h], 0
0x180008c04  jnz     short loc_180008C17
0x180008c06  movups  xmm0, xmmword ptr [rdx]
0x180008c09  movups  xmmword ptr [rbx+50h], xmm0
0x180008c0d  movsd   xmm1, qword ptr [rdx+10h]
0x180008c12  movsd   qword ptr [rbx+60h], xmm1
0x180008c17  movups  xmm0, xmmword ptr [rdx]
0x180008c1a  lea     r10, [rdi+rbp]
0x180008c1e  movups  xmmword ptr [rbx+68h], xmm0
0x180008c22  movsd   xmm1, qword ptr [rdx+10h]
0x180008c27  movsd   qword ptr [rbx+78h], xmm1
0x180008c2c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180008c30  mov     rax, rbx
0x180008c33  inc     rax
0x180008c36  cmp     byte ptr [rdi+rax], 0
0x180008c3a  jnz     short loc_180008C33
0x180008c3c  lea     rcx, [rax+rdi]
0x180008c40  mov     rax, r10
0x180008c43  sub     rax, rcx
0x180008c46  cmp     rax, 2
0x180008c4a  jle     short loc_180008C81
0x180008c4c  mov     byte ptr [rcx], 5Ch ; '\'
0x180008c4f  lea     rdi, [rcx+1]
0x180008c53  mov     r8, [rdx+8]; Source
0x180008c57  inc     rbx
0x180008c5a  cmp     byte ptr [r8+rbx], 0
0x180008c5f  jnz     short loc_180008C57
0x180008c61  sub     r10, rdi
0x180008c64  inc     rbx
0x180008c67  cmp     rbx, r10
0x180008c6a  mov     rdx, r10; DestinationSize
0x180008c6d  mov     rcx, rdi; Destination
0x180008c70  cmovnb  rbx, r10
0x180008c74  mov     r9, rbx; SourceSize
0x180008c77  call    memcpy_s
0x180008c7c  mov     byte ptr [rbx+rdi-1], 0
0x180008c81  mov     al, 1
0x180008c83  add     rsp, 28h
0x180008c87  pop     rdi
0x180008c88  pop     rsi
0x180008c89  pop     rbp
0x180008c8a  pop     rbx
0x180008c8b  retn
```
