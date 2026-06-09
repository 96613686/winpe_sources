# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180077f80`
- end: `0x18007805c`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180014ae8`
- `0x180077f80`

## callees

- `0x180015e48`
- `0x180077f80`

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
0x180077f80  push    rbx
0x180077f82  push    rbp
0x180077f83  push    rsi
0x180077f84  push    rdi
0x180077f85  sub     rsp, 28h
0x180077f89  xor     al, al
0x180077f8b  mov     byte ptr [r8], 0
0x180077f8f  mov     rbp, r9
0x180077f92  mov     rdi, r8
0x180077f95  mov     rsi, rdx
0x180077f98  mov     rbx, rcx
0x180077f9b  test    rdx, rdx
0x180077f9e  jz      loc_180078053
0x180077fa4  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180077fa8  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180077fad  mov     rdx, [rsi+20h]
0x180077fb1  test    rdx, rdx
0x180077fb4  jz      loc_180078053
0x180077fba  cmp     dword ptr [rdx], 0
0x180077fbd  jnz     short loc_180077FD0
0x180077fbf  mov     eax, 1
0x180077fc4  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180077fcc  inc     eax
0x180077fce  mov     [rdx], eax
0x180077fd0  cmp     dword ptr [rbx+50h], 0
0x180077fd4  jnz     short loc_180077FE7
0x180077fd6  movups  xmm0, xmmword ptr [rdx]
0x180077fd9  movups  xmmword ptr [rbx+50h], xmm0
0x180077fdd  movsd   xmm1, qword ptr [rdx+10h]
0x180077fe2  movsd   qword ptr [rbx+60h], xmm1
0x180077fe7  movups  xmm0, xmmword ptr [rdx]
0x180077fea  lea     r10, [rdi+rbp]
0x180077fee  movups  xmmword ptr [rbx+68h], xmm0
0x180077ff2  movsd   xmm1, qword ptr [rdx+10h]
0x180077ff7  movsd   qword ptr [rbx+78h], xmm1
0x180077ffc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180078000  mov     rax, rbx
0x180078003  inc     rax
0x180078006  cmp     byte ptr [rdi+rax], 0
0x18007800a  jnz     short loc_180078003
0x18007800c  lea     rcx, [rax+rdi]
0x180078010  mov     rax, r10
0x180078013  sub     rax, rcx
0x180078016  cmp     rax, 2
0x18007801a  jle     short loc_180078051
0x18007801c  mov     byte ptr [rcx], 5Ch ; '\'
0x18007801f  lea     rdi, [rcx+1]
0x180078023  mov     r8, [rdx+8]; Source
0x180078027  inc     rbx
0x18007802a  cmp     byte ptr [r8+rbx], 0
0x18007802f  jnz     short loc_180078027
0x180078031  sub     r10, rdi
0x180078034  inc     rbx
0x180078037  cmp     rbx, r10
0x18007803a  mov     rdx, r10; DestinationSize
0x18007803d  mov     rcx, rdi; Destination
0x180078040  cmovnb  rbx, r10
0x180078044  mov     r9, rbx; SourceSize
0x180078047  call    memcpy_s
0x18007804c  mov     byte ptr [rbx+rdi-1], 0
0x180078051  mov     al, 1
0x180078053  add     rsp, 28h
0x180078057  pop     rdi
0x180078058  pop     rsi
0x180078059  pop     rbp
0x18007805a  pop     rbx
0x18007805b  retn
```
