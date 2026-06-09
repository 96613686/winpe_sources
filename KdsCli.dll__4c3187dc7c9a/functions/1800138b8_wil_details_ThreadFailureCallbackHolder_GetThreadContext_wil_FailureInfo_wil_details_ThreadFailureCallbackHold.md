# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x1800138b8`
- end: `0x180013994`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800131c0`
- `0x1800138b8`

## callees

- `0x180001f4c`
- `0x1800138b8`

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
0x1800138b8  push    rbx
0x1800138ba  push    rbp
0x1800138bb  push    rsi
0x1800138bc  push    rdi
0x1800138bd  sub     rsp, 28h
0x1800138c1  xor     al, al
0x1800138c3  mov     byte ptr [r8], 0
0x1800138c7  mov     rbp, r9
0x1800138ca  mov     rdi, r8
0x1800138cd  mov     rsi, rdx
0x1800138d0  mov     rbx, rcx
0x1800138d3  test    rdx, rdx
0x1800138d6  jz      loc_18001398B
0x1800138dc  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x1800138e0  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800138e5  mov     rdx, [rsi+20h]
0x1800138e9  test    rdx, rdx
0x1800138ec  jz      loc_18001398B
0x1800138f2  cmp     dword ptr [rdx], 0
0x1800138f5  jnz     short loc_180013908
0x1800138f7  mov     eax, 1
0x1800138fc  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180013904  inc     eax
0x180013906  mov     [rdx], eax
0x180013908  cmp     dword ptr [rbx+50h], 0
0x18001390c  jnz     short loc_18001391F
0x18001390e  movups  xmm0, xmmword ptr [rdx]
0x180013911  movups  xmmword ptr [rbx+50h], xmm0
0x180013915  movsd   xmm1, qword ptr [rdx+10h]
0x18001391a  movsd   qword ptr [rbx+60h], xmm1
0x18001391f  movups  xmm0, xmmword ptr [rdx]
0x180013922  lea     r10, [rdi+rbp]
0x180013926  movups  xmmword ptr [rbx+68h], xmm0
0x18001392a  movsd   xmm1, qword ptr [rdx+10h]
0x18001392f  movsd   qword ptr [rbx+78h], xmm1
0x180013934  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180013938  mov     rax, rbx
0x18001393b  inc     rax
0x18001393e  cmp     byte ptr [rdi+rax], 0
0x180013942  jnz     short loc_18001393B
0x180013944  lea     rcx, [rax+rdi]
0x180013948  mov     rax, r10
0x18001394b  sub     rax, rcx
0x18001394e  cmp     rax, 2
0x180013952  jle     short loc_180013989
0x180013954  mov     byte ptr [rcx], 5Ch ; '\'
0x180013957  lea     rdi, [rcx+1]
0x18001395b  mov     r8, [rdx+8]; Source
0x18001395f  inc     rbx
0x180013962  cmp     byte ptr [r8+rbx], 0
0x180013967  jnz     short loc_18001395F
0x180013969  sub     r10, rdi
0x18001396c  inc     rbx
0x18001396f  cmp     rbx, r10
0x180013972  mov     rdx, r10; DestinationSize
0x180013975  mov     rcx, rdi; Destination
0x180013978  cmovnb  rbx, r10
0x18001397c  mov     r9, rbx; SourceSize
0x18001397f  call    memcpy_s
0x180013984  mov     byte ptr [rbx+rdi-1], 0
0x180013989  mov     al, 1
0x18001398b  add     rsp, 28h
0x18001398f  pop     rdi
0x180013990  pop     rsi
0x180013991  pop     rbp
0x180013992  pop     rbx
0x180013993  retn
```
