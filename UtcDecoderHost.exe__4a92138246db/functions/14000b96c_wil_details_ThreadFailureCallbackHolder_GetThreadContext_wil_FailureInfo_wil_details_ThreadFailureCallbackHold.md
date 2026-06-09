# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x14000b96c`
- end: `0x14000ba48`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b270`
- `0x14000b96c`

## callees

- `0x14000b96c`
- `0x14000d608`

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
0x14000b96c  push    rbx
0x14000b96e  push    rbp
0x14000b96f  push    rsi
0x14000b970  push    rdi
0x14000b971  sub     rsp, 28h
0x14000b975  xor     al, al
0x14000b977  mov     byte ptr [r8], 0
0x14000b97b  mov     rbp, r9
0x14000b97e  mov     rdi, r8
0x14000b981  mov     rsi, rdx
0x14000b984  mov     rbx, rcx
0x14000b987  test    rdx, rdx
0x14000b98a  jz      loc_14000BA3F
0x14000b990  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x14000b994  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x14000b999  mov     rdx, [rsi+20h]
0x14000b99d  test    rdx, rdx
0x14000b9a0  jz      loc_14000BA3F
0x14000b9a6  cmp     dword ptr [rdx], 0
0x14000b9a9  jnz     short loc_14000B9BC
0x14000b9ab  mov     eax, 1
0x14000b9b0  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x14000b9b8  inc     eax
0x14000b9ba  mov     [rdx], eax
0x14000b9bc  cmp     dword ptr [rbx+50h], 0
0x14000b9c0  jnz     short loc_14000B9D3
0x14000b9c2  movups  xmm0, xmmword ptr [rdx]
0x14000b9c5  movups  xmmword ptr [rbx+50h], xmm0
0x14000b9c9  movsd   xmm1, qword ptr [rdx+10h]
0x14000b9ce  movsd   qword ptr [rbx+60h], xmm1
0x14000b9d3  movups  xmm0, xmmword ptr [rdx]
0x14000b9d6  lea     r10, [rdi+rbp]
0x14000b9da  movups  xmmword ptr [rbx+68h], xmm0
0x14000b9de  movsd   xmm1, qword ptr [rdx+10h]
0x14000b9e3  movsd   qword ptr [rbx+78h], xmm1
0x14000b9e8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000b9ec  mov     rax, rbx
0x14000b9ef  inc     rax
0x14000b9f2  cmp     byte ptr [rdi+rax], 0
0x14000b9f6  jnz     short loc_14000B9EF
0x14000b9f8  lea     rcx, [rax+rdi]
0x14000b9fc  mov     rax, r10
0x14000b9ff  sub     rax, rcx
0x14000ba02  cmp     rax, 2
0x14000ba06  jle     short loc_14000BA3D
0x14000ba08  mov     byte ptr [rcx], 5Ch ; '\'
0x14000ba0b  lea     rdi, [rcx+1]
0x14000ba0f  mov     r8, [rdx+8]; Source
0x14000ba13  inc     rbx
0x14000ba16  cmp     byte ptr [r8+rbx], 0
0x14000ba1b  jnz     short loc_14000BA13
0x14000ba1d  sub     r10, rdi
0x14000ba20  inc     rbx
0x14000ba23  cmp     rbx, r10
0x14000ba26  mov     rdx, r10; DestinationSize
0x14000ba29  mov     rcx, rdi; Destination
0x14000ba2c  cmovnb  rbx, r10
0x14000ba30  mov     r9, rbx; SourceSize
0x14000ba33  call    memcpy_s
0x14000ba38  mov     byte ptr [rbx+rdi-1], 0
0x14000ba3d  mov     al, 1
0x14000ba3f  add     rsp, 28h
0x14000ba43  pop     rdi
0x14000ba44  pop     rsi
0x14000ba45  pop     rbp
0x14000ba46  pop     rbx
0x14000ba47  retn
```
