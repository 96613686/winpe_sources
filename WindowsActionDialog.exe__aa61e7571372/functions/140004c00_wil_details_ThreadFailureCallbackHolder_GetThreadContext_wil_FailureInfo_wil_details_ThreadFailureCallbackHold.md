# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140004c00`
- end: `0x140004cdc`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140004450`
- `0x140004c00`

## callees

- `0x140004c00`
- `0x1400079e8`

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
0x140004c00  push    rbx
0x140004c02  push    rbp
0x140004c03  push    rsi
0x140004c04  push    rdi
0x140004c05  sub     rsp, 28h
0x140004c09  xor     al, al
0x140004c0b  mov     byte ptr [r8], 0
0x140004c0f  mov     rbp, r9
0x140004c12  mov     rdi, r8
0x140004c15  mov     rsi, rdx
0x140004c18  mov     rbx, rcx
0x140004c1b  test    rdx, rdx
0x140004c1e  jz      loc_140004CD3
0x140004c24  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140004c28  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140004c2d  mov     rdx, [rsi+20h]
0x140004c31  test    rdx, rdx
0x140004c34  jz      loc_140004CD3
0x140004c3a  cmp     dword ptr [rdx], 0
0x140004c3d  jnz     short loc_140004C50
0x140004c3f  mov     eax, 1
0x140004c44  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140004c4c  inc     eax
0x140004c4e  mov     [rdx], eax
0x140004c50  cmp     dword ptr [rbx+50h], 0
0x140004c54  jnz     short loc_140004C67
0x140004c56  movups  xmm0, xmmword ptr [rdx]
0x140004c59  movups  xmmword ptr [rbx+50h], xmm0
0x140004c5d  movsd   xmm1, qword ptr [rdx+10h]
0x140004c62  movsd   qword ptr [rbx+60h], xmm1
0x140004c67  movups  xmm0, xmmword ptr [rdx]
0x140004c6a  lea     r10, [rdi+rbp]
0x140004c6e  movups  xmmword ptr [rbx+68h], xmm0
0x140004c72  movsd   xmm1, qword ptr [rdx+10h]
0x140004c77  movsd   qword ptr [rbx+78h], xmm1
0x140004c7c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140004c80  mov     rax, rbx
0x140004c83  inc     rax
0x140004c86  cmp     byte ptr [rdi+rax], 0
0x140004c8a  jnz     short loc_140004C83
0x140004c8c  lea     rcx, [rax+rdi]
0x140004c90  mov     rax, r10
0x140004c93  sub     rax, rcx
0x140004c96  cmp     rax, 2
0x140004c9a  jle     short loc_140004CD1
0x140004c9c  mov     byte ptr [rcx], 5Ch ; '\'
0x140004c9f  lea     rdi, [rcx+1]
0x140004ca3  mov     r8, [rdx+8]; Source
0x140004ca7  inc     rbx
0x140004caa  cmp     byte ptr [r8+rbx], 0
0x140004caf  jnz     short loc_140004CA7
0x140004cb1  sub     r10, rdi
0x140004cb4  inc     rbx
0x140004cb7  cmp     rbx, r10
0x140004cba  mov     rdx, r10; DestinationSize
0x140004cbd  mov     rcx, rdi; Destination
0x140004cc0  cmovnb  rbx, r10
0x140004cc4  mov     r9, rbx; SourceSize
0x140004cc7  call    memcpy_s
0x140004ccc  mov     byte ptr [rbx+rdi-1], 0
0x140004cd1  mov     al, 1
0x140004cd3  add     rsp, 28h
0x140004cd7  pop     rdi
0x140004cd8  pop     rsi
0x140004cd9  pop     rbp
0x140004cda  pop     rbx
0x140004cdb  retn
```
