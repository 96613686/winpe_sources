# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180005190`
- end: `0x18000526c`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800049f0`
- `0x180005190`

## callees

- `0x180005190`
- `0x1800073cc`

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
0x180005190  push    rbx
0x180005192  push    rbp
0x180005193  push    rsi
0x180005194  push    rdi
0x180005195  sub     rsp, 28h
0x180005199  xor     al, al
0x18000519b  mov     byte ptr [r8], 0
0x18000519f  mov     rbp, r9
0x1800051a2  mov     rdi, r8
0x1800051a5  mov     rsi, rdx
0x1800051a8  mov     rbx, rcx
0x1800051ab  test    rdx, rdx
0x1800051ae  jz      loc_180005263
0x1800051b4  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x1800051b8  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800051bd  mov     rdx, [rsi+20h]
0x1800051c1  test    rdx, rdx
0x1800051c4  jz      loc_180005263
0x1800051ca  cmp     dword ptr [rdx], 0
0x1800051cd  jnz     short loc_1800051E0
0x1800051cf  mov     eax, 1
0x1800051d4  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x1800051dc  inc     eax
0x1800051de  mov     [rdx], eax
0x1800051e0  cmp     dword ptr [rbx+50h], 0
0x1800051e4  jnz     short loc_1800051F7
0x1800051e6  movups  xmm0, xmmword ptr [rdx]
0x1800051e9  movups  xmmword ptr [rbx+50h], xmm0
0x1800051ed  movsd   xmm1, qword ptr [rdx+10h]
0x1800051f2  movsd   qword ptr [rbx+60h], xmm1
0x1800051f7  movups  xmm0, xmmword ptr [rdx]
0x1800051fa  lea     r10, [rdi+rbp]
0x1800051fe  movups  xmmword ptr [rbx+68h], xmm0
0x180005202  movsd   xmm1, qword ptr [rdx+10h]
0x180005207  movsd   qword ptr [rbx+78h], xmm1
0x18000520c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005210  mov     rax, rbx
0x180005213  inc     rax
0x180005216  cmp     byte ptr [rdi+rax], 0
0x18000521a  jnz     short loc_180005213
0x18000521c  lea     rcx, [rax+rdi]
0x180005220  mov     rax, r10
0x180005223  sub     rax, rcx
0x180005226  cmp     rax, 2
0x18000522a  jle     short loc_180005261
0x18000522c  mov     byte ptr [rcx], 5Ch ; '\'
0x18000522f  lea     rdi, [rcx+1]
0x180005233  mov     r8, [rdx+8]; Source
0x180005237  inc     rbx
0x18000523a  cmp     byte ptr [r8+rbx], 0
0x18000523f  jnz     short loc_180005237
0x180005241  sub     r10, rdi
0x180005244  inc     rbx
0x180005247  cmp     rbx, r10
0x18000524a  mov     rdx, r10; DestinationSize
0x18000524d  mov     rcx, rdi; Destination
0x180005250  cmovnb  rbx, r10
0x180005254  mov     r9, rbx; SourceSize
0x180005257  call    memcpy_s
0x18000525c  mov     byte ptr [rbx+rdi-1], 0
0x180005261  mov     al, 1
0x180005263  add     rsp, 28h
0x180005267  pop     rdi
0x180005268  pop     rsi
0x180005269  pop     rbp
0x18000526a  pop     rbx
0x18000526b  retn
```
