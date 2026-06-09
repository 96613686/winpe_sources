# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x1400051bc`
- end: `0x140005298`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140004ac0`
- `0x1400051bc`

## callees

- `0x1400051bc`
- `0x140009088`

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
0x1400051bc  push    rbx
0x1400051be  push    rbp
0x1400051bf  push    rsi
0x1400051c0  push    rdi
0x1400051c1  sub     rsp, 28h
0x1400051c5  xor     al, al
0x1400051c7  mov     byte ptr [r8], 0
0x1400051cb  mov     rbp, r9
0x1400051ce  mov     rdi, r8
0x1400051d1  mov     rsi, rdx
0x1400051d4  mov     rbx, rcx
0x1400051d7  test    rdx, rdx
0x1400051da  jz      loc_14000528F
0x1400051e0  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x1400051e4  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1400051e9  mov     rdx, [rsi+20h]
0x1400051ed  test    rdx, rdx
0x1400051f0  jz      loc_14000528F
0x1400051f6  cmp     dword ptr [rdx], 0
0x1400051f9  jnz     short loc_14000520C
0x1400051fb  mov     eax, 1
0x140005200  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140005208  inc     eax
0x14000520a  mov     [rdx], eax
0x14000520c  cmp     dword ptr [rbx+50h], 0
0x140005210  jnz     short loc_140005223
0x140005212  movups  xmm0, xmmword ptr [rdx]
0x140005215  movups  xmmword ptr [rbx+50h], xmm0
0x140005219  movsd   xmm1, qword ptr [rdx+10h]
0x14000521e  movsd   qword ptr [rbx+60h], xmm1
0x140005223  movups  xmm0, xmmword ptr [rdx]
0x140005226  lea     r10, [rdi+rbp]
0x14000522a  movups  xmmword ptr [rbx+68h], xmm0
0x14000522e  movsd   xmm1, qword ptr [rdx+10h]
0x140005233  movsd   qword ptr [rbx+78h], xmm1
0x140005238  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000523c  mov     rax, rbx
0x14000523f  inc     rax
0x140005242  cmp     byte ptr [rdi+rax], 0
0x140005246  jnz     short loc_14000523F
0x140005248  lea     rcx, [rax+rdi]
0x14000524c  mov     rax, r10
0x14000524f  sub     rax, rcx
0x140005252  cmp     rax, 2
0x140005256  jle     short loc_14000528D
0x140005258  mov     byte ptr [rcx], 5Ch ; '\'
0x14000525b  lea     rdi, [rcx+1]
0x14000525f  mov     r8, [rdx+8]; Source
0x140005263  inc     rbx
0x140005266  cmp     byte ptr [r8+rbx], 0
0x14000526b  jnz     short loc_140005263
0x14000526d  sub     r10, rdi
0x140005270  inc     rbx
0x140005273  cmp     rbx, r10
0x140005276  mov     rdx, r10; DestinationSize
0x140005279  mov     rcx, rdi; Destination
0x14000527c  cmovnb  rbx, r10
0x140005280  mov     r9, rbx; SourceSize
0x140005283  call    memcpy_s
0x140005288  mov     byte ptr [rbx+rdi-1], 0
0x14000528d  mov     al, 1
0x14000528f  add     rsp, 28h
0x140005293  pop     rdi
0x140005294  pop     rsi
0x140005295  pop     rbp
0x140005296  pop     rbx
0x140005297  retn
```
