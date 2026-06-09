# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180006a20`
- end: `0x180006afc`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005b54`
- `0x180006a20`

## callees

- `0x180006a20`
- `0x18000b43c`

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
0x180006a20  push    rbx
0x180006a22  push    rbp
0x180006a23  push    rsi
0x180006a24  push    rdi
0x180006a25  sub     rsp, 28h
0x180006a29  xor     al, al
0x180006a2b  mov     byte ptr [r8], 0
0x180006a2f  mov     rbp, r9
0x180006a32  mov     rdi, r8
0x180006a35  mov     rsi, rdx
0x180006a38  mov     rbx, rcx
0x180006a3b  test    rdx, rdx
0x180006a3e  jz      loc_180006AF3
0x180006a44  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180006a48  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180006a4d  mov     rdx, [rsi+20h]
0x180006a51  test    rdx, rdx
0x180006a54  jz      loc_180006AF3
0x180006a5a  cmp     dword ptr [rdx], 0
0x180006a5d  jnz     short loc_180006A70
0x180006a5f  mov     eax, 1
0x180006a64  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180006a6c  inc     eax
0x180006a6e  mov     [rdx], eax
0x180006a70  cmp     dword ptr [rbx+50h], 0
0x180006a74  jnz     short loc_180006A87
0x180006a76  movups  xmm0, xmmword ptr [rdx]
0x180006a79  movups  xmmword ptr [rbx+50h], xmm0
0x180006a7d  movsd   xmm1, qword ptr [rdx+10h]
0x180006a82  movsd   qword ptr [rbx+60h], xmm1
0x180006a87  movups  xmm0, xmmword ptr [rdx]
0x180006a8a  lea     r10, [rdi+rbp]
0x180006a8e  movups  xmmword ptr [rbx+68h], xmm0
0x180006a92  movsd   xmm1, qword ptr [rdx+10h]
0x180006a97  movsd   qword ptr [rbx+78h], xmm1
0x180006a9c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180006aa0  mov     rax, rbx
0x180006aa3  inc     rax
0x180006aa6  cmp     byte ptr [rdi+rax], 0
0x180006aaa  jnz     short loc_180006AA3
0x180006aac  lea     rcx, [rax+rdi]
0x180006ab0  mov     rax, r10
0x180006ab3  sub     rax, rcx
0x180006ab6  cmp     rax, 2
0x180006aba  jle     short loc_180006AF1
0x180006abc  mov     byte ptr [rcx], 5Ch ; '\'
0x180006abf  lea     rdi, [rcx+1]
0x180006ac3  mov     r8, [rdx+8]; Source
0x180006ac7  inc     rbx
0x180006aca  cmp     byte ptr [r8+rbx], 0
0x180006acf  jnz     short loc_180006AC7
0x180006ad1  sub     r10, rdi
0x180006ad4  inc     rbx
0x180006ad7  cmp     rbx, r10
0x180006ada  mov     rdx, r10; DestinationSize
0x180006add  mov     rcx, rdi; Destination
0x180006ae0  cmovnb  rbx, r10
0x180006ae4  mov     r9, rbx; SourceSize
0x180006ae7  call    memcpy_s
0x180006aec  mov     byte ptr [rbx+rdi-1], 0
0x180006af1  mov     al, 1
0x180006af3  add     rsp, 28h
0x180006af7  pop     rdi
0x180006af8  pop     rsi
0x180006af9  pop     rbp
0x180006afa  pop     rbx
0x180006afb  retn
```
