# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180005378`
- end: `0x180005454`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004c80`
- `0x180005378`

## callees

- `0x180005378`
- `0x180008a94`

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
0x180005378  push    rbx
0x18000537a  push    rbp
0x18000537b  push    rsi
0x18000537c  push    rdi
0x18000537d  sub     rsp, 28h
0x180005381  xor     al, al
0x180005383  mov     byte ptr [r8], 0
0x180005387  mov     rbp, r9
0x18000538a  mov     rdi, r8
0x18000538d  mov     rsi, rdx
0x180005390  mov     rbx, rcx
0x180005393  test    rdx, rdx
0x180005396  jz      loc_18000544B
0x18000539c  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x1800053a0  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800053a5  mov     rdx, [rsi+20h]
0x1800053a9  test    rdx, rdx
0x1800053ac  jz      loc_18000544B
0x1800053b2  cmp     dword ptr [rdx], 0
0x1800053b5  jnz     short loc_1800053C8
0x1800053b7  mov     eax, 1
0x1800053bc  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x1800053c4  inc     eax
0x1800053c6  mov     [rdx], eax
0x1800053c8  cmp     dword ptr [rbx+50h], 0
0x1800053cc  jnz     short loc_1800053DF
0x1800053ce  movups  xmm0, xmmword ptr [rdx]
0x1800053d1  movups  xmmword ptr [rbx+50h], xmm0
0x1800053d5  movsd   xmm1, qword ptr [rdx+10h]
0x1800053da  movsd   qword ptr [rbx+60h], xmm1
0x1800053df  movups  xmm0, xmmword ptr [rdx]
0x1800053e2  lea     r10, [rdi+rbp]
0x1800053e6  movups  xmmword ptr [rbx+68h], xmm0
0x1800053ea  movsd   xmm1, qword ptr [rdx+10h]
0x1800053ef  movsd   qword ptr [rbx+78h], xmm1
0x1800053f4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800053f8  mov     rax, rbx
0x1800053fb  inc     rax
0x1800053fe  cmp     byte ptr [rdi+rax], 0
0x180005402  jnz     short loc_1800053FB
0x180005404  lea     rcx, [rax+rdi]
0x180005408  mov     rax, r10
0x18000540b  sub     rax, rcx
0x18000540e  cmp     rax, 2
0x180005412  jle     short loc_180005449
0x180005414  mov     byte ptr [rcx], 5Ch ; '\'
0x180005417  lea     rdi, [rcx+1]
0x18000541b  mov     r8, [rdx+8]; Source
0x18000541f  inc     rbx
0x180005422  cmp     byte ptr [r8+rbx], 0
0x180005427  jnz     short loc_18000541F
0x180005429  sub     r10, rdi
0x18000542c  inc     rbx
0x18000542f  cmp     rbx, r10
0x180005432  mov     rdx, r10; DestinationSize
0x180005435  mov     rcx, rdi; Destination
0x180005438  cmovnb  rbx, r10
0x18000543c  mov     r9, rbx; SourceSize
0x18000543f  call    memcpy_s
0x180005444  mov     byte ptr [rbx+rdi-1], 0
0x180005449  mov     al, 1
0x18000544b  add     rsp, 28h
0x18000544f  pop     rdi
0x180005450  pop     rsi
0x180005451  pop     rbp
0x180005452  pop     rbx
0x180005453  retn
```
