# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180014a50`
- end: `0x180014b2c`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800142ec`
- `0x180014a50`

## callees

- `0x180014a50`
- `0x180016a74`

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
0x180014a50  push    rbx
0x180014a52  push    rbp
0x180014a53  push    rsi
0x180014a54  push    rdi
0x180014a55  sub     rsp, 28h
0x180014a59  xor     al, al
0x180014a5b  mov     byte ptr [r8], 0
0x180014a5f  mov     rbp, r9
0x180014a62  mov     rdi, r8
0x180014a65  mov     rsi, rdx
0x180014a68  mov     rbx, rcx
0x180014a6b  test    rdx, rdx
0x180014a6e  jz      loc_180014B23
0x180014a74  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180014a78  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180014a7d  mov     rdx, [rsi+20h]
0x180014a81  test    rdx, rdx
0x180014a84  jz      loc_180014B23
0x180014a8a  cmp     dword ptr [rdx], 0
0x180014a8d  jnz     short loc_180014AA0
0x180014a8f  mov     eax, 1
0x180014a94  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180014a9c  inc     eax
0x180014a9e  mov     [rdx], eax
0x180014aa0  cmp     dword ptr [rbx+50h], 0
0x180014aa4  jnz     short loc_180014AB7
0x180014aa6  movups  xmm0, xmmword ptr [rdx]
0x180014aa9  movups  xmmword ptr [rbx+50h], xmm0
0x180014aad  movsd   xmm1, qword ptr [rdx+10h]
0x180014ab2  movsd   qword ptr [rbx+60h], xmm1
0x180014ab7  movups  xmm0, xmmword ptr [rdx]
0x180014aba  lea     r10, [rdi+rbp]
0x180014abe  movups  xmmword ptr [rbx+68h], xmm0
0x180014ac2  movsd   xmm1, qword ptr [rdx+10h]
0x180014ac7  movsd   qword ptr [rbx+78h], xmm1
0x180014acc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180014ad0  mov     rax, rbx
0x180014ad3  inc     rax
0x180014ad6  cmp     byte ptr [rdi+rax], 0
0x180014ada  jnz     short loc_180014AD3
0x180014adc  lea     rcx, [rax+rdi]
0x180014ae0  mov     rax, r10
0x180014ae3  sub     rax, rcx
0x180014ae6  cmp     rax, 2
0x180014aea  jle     short loc_180014B21
0x180014aec  mov     byte ptr [rcx], 5Ch ; '\'
0x180014aef  lea     rdi, [rcx+1]
0x180014af3  mov     r8, [rdx+8]; Source
0x180014af7  inc     rbx
0x180014afa  cmp     byte ptr [r8+rbx], 0
0x180014aff  jnz     short loc_180014AF7
0x180014b01  sub     r10, rdi
0x180014b04  inc     rbx
0x180014b07  cmp     rbx, r10
0x180014b0a  mov     rdx, r10; DestinationSize
0x180014b0d  mov     rcx, rdi; Destination
0x180014b10  cmovnb  rbx, r10
0x180014b14  mov     r9, rbx; SourceSize
0x180014b17  call    memcpy_s
0x180014b1c  mov     byte ptr [rbx+rdi-1], 0
0x180014b21  mov     al, 1
0x180014b23  add     rsp, 28h
0x180014b27  pop     rdi
0x180014b28  pop     rsi
0x180014b29  pop     rbp
0x180014b2a  pop     rbx
0x180014b2b  retn
```
