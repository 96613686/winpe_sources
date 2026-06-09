# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x1800052d0`
- end: `0x1800053ac`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004bf8`
- `0x1800052d0`

## callees

- `0x1800052d0`
- `0x18000934c`

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
0x1800052d0  push    rbx
0x1800052d2  push    rbp
0x1800052d3  push    rsi
0x1800052d4  push    rdi
0x1800052d5  sub     rsp, 28h
0x1800052d9  xor     al, al
0x1800052db  mov     byte ptr [r8], 0
0x1800052df  mov     rbp, r9
0x1800052e2  mov     rdi, r8
0x1800052e5  mov     rsi, rdx
0x1800052e8  mov     rbx, rcx
0x1800052eb  test    rdx, rdx
0x1800052ee  jz      loc_1800053A3
0x1800052f4  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x1800052f8  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800052fd  mov     rdx, [rsi+20h]
0x180005301  test    rdx, rdx
0x180005304  jz      loc_1800053A3
0x18000530a  cmp     dword ptr [rdx], 0
0x18000530d  jnz     short loc_180005320
0x18000530f  mov     eax, 1
0x180005314  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000531c  inc     eax
0x18000531e  mov     [rdx], eax
0x180005320  cmp     dword ptr [rbx+50h], 0
0x180005324  jnz     short loc_180005337
0x180005326  movups  xmm0, xmmword ptr [rdx]
0x180005329  movups  xmmword ptr [rbx+50h], xmm0
0x18000532d  movsd   xmm1, qword ptr [rdx+10h]
0x180005332  movsd   qword ptr [rbx+60h], xmm1
0x180005337  movups  xmm0, xmmword ptr [rdx]
0x18000533a  lea     r10, [rdi+rbp]
0x18000533e  movups  xmmword ptr [rbx+68h], xmm0
0x180005342  movsd   xmm1, qword ptr [rdx+10h]
0x180005347  movsd   qword ptr [rbx+78h], xmm1
0x18000534c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005350  mov     rax, rbx
0x180005353  inc     rax
0x180005356  cmp     byte ptr [rdi+rax], 0
0x18000535a  jnz     short loc_180005353
0x18000535c  lea     rcx, [rax+rdi]
0x180005360  mov     rax, r10
0x180005363  sub     rax, rcx
0x180005366  cmp     rax, 2
0x18000536a  jle     short loc_1800053A1
0x18000536c  mov     byte ptr [rcx], 5Ch ; '\'
0x18000536f  lea     rdi, [rcx+1]
0x180005373  mov     r8, [rdx+8]; Source
0x180005377  inc     rbx
0x18000537a  cmp     byte ptr [r8+rbx], 0
0x18000537f  jnz     short loc_180005377
0x180005381  sub     r10, rdi
0x180005384  inc     rbx
0x180005387  cmp     rbx, r10
0x18000538a  mov     rdx, r10; DestinationSize
0x18000538d  mov     rcx, rdi; Destination
0x180005390  cmovnb  rbx, r10
0x180005394  mov     r9, rbx; SourceSize
0x180005397  call    memcpy_s
0x18000539c  mov     byte ptr [rbx+rdi-1], 0
0x1800053a1  mov     al, 1
0x1800053a3  add     rsp, 28h
0x1800053a7  pop     rdi
0x1800053a8  pop     rsi
0x1800053a9  pop     rbp
0x1800053aa  pop     rbx
0x1800053ab  retn
```
