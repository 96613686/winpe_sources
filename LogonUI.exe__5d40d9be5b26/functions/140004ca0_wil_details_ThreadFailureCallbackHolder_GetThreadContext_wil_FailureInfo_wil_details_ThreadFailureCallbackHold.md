# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140004ca0`
- end: `0x140004d7c`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400046c8`
- `0x140004ca0`

## callees

- `0x140001cdc`
- `0x140004ca0`

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
0x140004ca0  push    rbx
0x140004ca2  push    rbp
0x140004ca3  push    rsi
0x140004ca4  push    rdi
0x140004ca5  sub     rsp, 28h
0x140004ca9  xor     al, al
0x140004cab  mov     byte ptr [r8], 0
0x140004caf  mov     rbp, r9
0x140004cb2  mov     rdi, r8
0x140004cb5  mov     rsi, rdx
0x140004cb8  mov     rbx, rcx
0x140004cbb  test    rdx, rdx
0x140004cbe  jz      loc_140004D73
0x140004cc4  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140004cc8  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140004ccd  mov     rdx, [rsi+20h]
0x140004cd1  test    rdx, rdx
0x140004cd4  jz      loc_140004D73
0x140004cda  cmp     dword ptr [rdx], 0
0x140004cdd  jnz     short loc_140004CF0
0x140004cdf  mov     eax, 1
0x140004ce4  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140004cec  inc     eax
0x140004cee  mov     [rdx], eax
0x140004cf0  cmp     dword ptr [rbx+50h], 0
0x140004cf4  jnz     short loc_140004D07
0x140004cf6  movups  xmm0, xmmword ptr [rdx]
0x140004cf9  movups  xmmword ptr [rbx+50h], xmm0
0x140004cfd  movsd   xmm1, qword ptr [rdx+10h]
0x140004d02  movsd   qword ptr [rbx+60h], xmm1
0x140004d07  movups  xmm0, xmmword ptr [rdx]
0x140004d0a  lea     r10, [rdi+rbp]
0x140004d0e  movups  xmmword ptr [rbx+68h], xmm0
0x140004d12  movsd   xmm1, qword ptr [rdx+10h]
0x140004d17  movsd   qword ptr [rbx+78h], xmm1
0x140004d1c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140004d20  mov     rax, rbx
0x140004d23  inc     rax
0x140004d26  cmp     byte ptr [rdi+rax], 0
0x140004d2a  jnz     short loc_140004D23
0x140004d2c  lea     rcx, [rax+rdi]
0x140004d30  mov     rax, r10
0x140004d33  sub     rax, rcx
0x140004d36  cmp     rax, 2
0x140004d3a  jle     short loc_140004D71
0x140004d3c  mov     byte ptr [rcx], 5Ch ; '\'
0x140004d3f  lea     rdi, [rcx+1]
0x140004d43  mov     r8, [rdx+8]; Source
0x140004d47  inc     rbx
0x140004d4a  cmp     byte ptr [r8+rbx], 0
0x140004d4f  jnz     short loc_140004D47
0x140004d51  sub     r10, rdi
0x140004d54  inc     rbx
0x140004d57  cmp     rbx, r10
0x140004d5a  mov     rdx, r10; DestinationSize
0x140004d5d  mov     rcx, rdi; Destination
0x140004d60  cmovnb  rbx, r10
0x140004d64  mov     r9, rbx; SourceSize
0x140004d67  call    memcpy_s
0x140004d6c  mov     byte ptr [rbx+rdi-1], 0
0x140004d71  mov     al, 1
0x140004d73  add     rsp, 28h
0x140004d77  pop     rdi
0x140004d78  pop     rsi
0x140004d79  pop     rbp
0x140004d7a  pop     rbx
0x140004d7b  retn
```
