# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180005e60`
- end: `0x180005f3c`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005788`
- `0x180005e60`

## callees

- `0x180005e60`
- `0x18000a0b8`

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
0x180005e60  push    rbx
0x180005e62  push    rbp
0x180005e63  push    rsi
0x180005e64  push    rdi
0x180005e65  sub     rsp, 28h
0x180005e69  xor     al, al
0x180005e6b  mov     byte ptr [r8], 0
0x180005e6f  mov     rbp, r9
0x180005e72  mov     rdi, r8
0x180005e75  mov     rsi, rdx
0x180005e78  mov     rbx, rcx
0x180005e7b  test    rdx, rdx
0x180005e7e  jz      loc_180005F33
0x180005e84  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180005e88  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005e8d  mov     rdx, [rsi+20h]
0x180005e91  test    rdx, rdx
0x180005e94  jz      loc_180005F33
0x180005e9a  cmp     dword ptr [rdx], 0
0x180005e9d  jnz     short loc_180005EB0
0x180005e9f  mov     eax, 1
0x180005ea4  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180005eac  inc     eax
0x180005eae  mov     [rdx], eax
0x180005eb0  cmp     dword ptr [rbx+50h], 0
0x180005eb4  jnz     short loc_180005EC7
0x180005eb6  movups  xmm0, xmmword ptr [rdx]
0x180005eb9  movups  xmmword ptr [rbx+50h], xmm0
0x180005ebd  movsd   xmm1, qword ptr [rdx+10h]
0x180005ec2  movsd   qword ptr [rbx+60h], xmm1
0x180005ec7  movups  xmm0, xmmword ptr [rdx]
0x180005eca  lea     r10, [rdi+rbp]
0x180005ece  movups  xmmword ptr [rbx+68h], xmm0
0x180005ed2  movsd   xmm1, qword ptr [rdx+10h]
0x180005ed7  movsd   qword ptr [rbx+78h], xmm1
0x180005edc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005ee0  mov     rax, rbx
0x180005ee3  inc     rax
0x180005ee6  cmp     byte ptr [rdi+rax], 0
0x180005eea  jnz     short loc_180005EE3
0x180005eec  lea     rcx, [rax+rdi]
0x180005ef0  mov     rax, r10
0x180005ef3  sub     rax, rcx
0x180005ef6  cmp     rax, 2
0x180005efa  jle     short loc_180005F31
0x180005efc  mov     byte ptr [rcx], 5Ch ; '\'
0x180005eff  lea     rdi, [rcx+1]
0x180005f03  mov     r8, [rdx+8]; Source
0x180005f07  inc     rbx
0x180005f0a  cmp     byte ptr [r8+rbx], 0
0x180005f0f  jnz     short loc_180005F07
0x180005f11  sub     r10, rdi
0x180005f14  inc     rbx
0x180005f17  cmp     rbx, r10
0x180005f1a  mov     rdx, r10; DestinationSize
0x180005f1d  mov     rcx, rdi; Destination
0x180005f20  cmovnb  rbx, r10
0x180005f24  mov     r9, rbx; SourceSize
0x180005f27  call    memcpy_s
0x180005f2c  mov     byte ptr [rbx+rdi-1], 0
0x180005f31  mov     al, 1
0x180005f33  add     rsp, 28h
0x180005f37  pop     rdi
0x180005f38  pop     rsi
0x180005f39  pop     rbp
0x180005f3a  pop     rbx
0x180005f3b  retn
```
