# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180005dfc`
- end: `0x180005ed8`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005700`
- `0x180005dfc`

## callees

- `0x180005dfc`
- `0x180009228`

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
0x180005dfc  push    rbx
0x180005dfe  push    rbp
0x180005dff  push    rsi
0x180005e00  push    rdi
0x180005e01  sub     rsp, 28h
0x180005e05  xor     al, al
0x180005e07  mov     byte ptr [r8], 0
0x180005e0b  mov     rbp, r9
0x180005e0e  mov     rdi, r8
0x180005e11  mov     rsi, rdx
0x180005e14  mov     rbx, rcx
0x180005e17  test    rdx, rdx
0x180005e1a  jz      loc_180005ECF
0x180005e20  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180005e24  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005e29  mov     rdx, [rsi+20h]
0x180005e2d  test    rdx, rdx
0x180005e30  jz      loc_180005ECF
0x180005e36  cmp     dword ptr [rdx], 0
0x180005e39  jnz     short loc_180005E4C
0x180005e3b  mov     eax, 1
0x180005e40  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180005e48  inc     eax
0x180005e4a  mov     [rdx], eax
0x180005e4c  cmp     dword ptr [rbx+50h], 0
0x180005e50  jnz     short loc_180005E63
0x180005e52  movups  xmm0, xmmword ptr [rdx]
0x180005e55  movups  xmmword ptr [rbx+50h], xmm0
0x180005e59  movsd   xmm1, qword ptr [rdx+10h]
0x180005e5e  movsd   qword ptr [rbx+60h], xmm1
0x180005e63  movups  xmm0, xmmword ptr [rdx]
0x180005e66  lea     r10, [rdi+rbp]
0x180005e6a  movups  xmmword ptr [rbx+68h], xmm0
0x180005e6e  movsd   xmm1, qword ptr [rdx+10h]
0x180005e73  movsd   qword ptr [rbx+78h], xmm1
0x180005e78  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005e7c  mov     rax, rbx
0x180005e7f  inc     rax
0x180005e82  cmp     byte ptr [rdi+rax], 0
0x180005e86  jnz     short loc_180005E7F
0x180005e88  lea     rcx, [rax+rdi]
0x180005e8c  mov     rax, r10
0x180005e8f  sub     rax, rcx
0x180005e92  cmp     rax, 2
0x180005e96  jle     short loc_180005ECD
0x180005e98  mov     byte ptr [rcx], 5Ch ; '\'
0x180005e9b  lea     rdi, [rcx+1]
0x180005e9f  mov     r8, [rdx+8]; Source
0x180005ea3  inc     rbx
0x180005ea6  cmp     byte ptr [r8+rbx], 0
0x180005eab  jnz     short loc_180005EA3
0x180005ead  sub     r10, rdi
0x180005eb0  inc     rbx
0x180005eb3  cmp     rbx, r10
0x180005eb6  mov     rdx, r10; DestinationSize
0x180005eb9  mov     rcx, rdi; Destination
0x180005ebc  cmovnb  rbx, r10
0x180005ec0  mov     r9, rbx; SourceSize
0x180005ec3  call    memcpy_s
0x180005ec8  mov     byte ptr [rbx+rdi-1], 0
0x180005ecd  mov     al, 1
0x180005ecf  add     rsp, 28h
0x180005ed3  pop     rdi
0x180005ed4  pop     rsi
0x180005ed5  pop     rbp
0x180005ed6  pop     rbx
0x180005ed7  retn
```
