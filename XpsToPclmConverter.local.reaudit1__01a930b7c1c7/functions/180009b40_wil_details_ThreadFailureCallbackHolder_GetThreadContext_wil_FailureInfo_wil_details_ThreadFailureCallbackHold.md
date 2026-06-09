# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180009b40`
- end: `0x180009c1c`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009454`
- `0x180009b40`

## callees

- `0x180009b40`
- `0x18000d374`

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
0x180009b40  push    rbx
0x180009b42  push    rbp
0x180009b43  push    rsi
0x180009b44  push    rdi
0x180009b45  sub     rsp, 28h
0x180009b49  xor     al, al
0x180009b4b  mov     byte ptr [r8], 0
0x180009b4f  mov     rbp, r9
0x180009b52  mov     rdi, r8
0x180009b55  mov     rsi, rdx
0x180009b58  mov     rbx, rcx
0x180009b5b  test    rdx, rdx
0x180009b5e  jz      loc_180009C13
0x180009b64  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180009b68  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180009b6d  mov     rdx, [rsi+20h]
0x180009b71  test    rdx, rdx
0x180009b74  jz      loc_180009C13
0x180009b7a  cmp     dword ptr [rdx], 0
0x180009b7d  jnz     short loc_180009B90
0x180009b7f  mov     eax, 1
0x180009b84  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180009b8c  inc     eax
0x180009b8e  mov     [rdx], eax
0x180009b90  cmp     dword ptr [rbx+50h], 0
0x180009b94  jnz     short loc_180009BA7
0x180009b96  movups  xmm0, xmmword ptr [rdx]
0x180009b99  movups  xmmword ptr [rbx+50h], xmm0
0x180009b9d  movsd   xmm1, qword ptr [rdx+10h]
0x180009ba2  movsd   qword ptr [rbx+60h], xmm1
0x180009ba7  movups  xmm0, xmmword ptr [rdx]
0x180009baa  lea     r10, [rdi+rbp]
0x180009bae  movups  xmmword ptr [rbx+68h], xmm0
0x180009bb2  movsd   xmm1, qword ptr [rdx+10h]
0x180009bb7  movsd   qword ptr [rbx+78h], xmm1
0x180009bbc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180009bc0  mov     rax, rbx
0x180009bc3  inc     rax
0x180009bc6  cmp     byte ptr [rdi+rax], 0
0x180009bca  jnz     short loc_180009BC3
0x180009bcc  lea     rcx, [rax+rdi]
0x180009bd0  mov     rax, r10
0x180009bd3  sub     rax, rcx
0x180009bd6  cmp     rax, 2
0x180009bda  jle     short loc_180009C11
0x180009bdc  mov     byte ptr [rcx], 5Ch ; '\'
0x180009bdf  lea     rdi, [rcx+1]
0x180009be3  mov     r8, [rdx+8]; Source
0x180009be7  inc     rbx
0x180009bea  cmp     byte ptr [r8+rbx], 0
0x180009bef  jnz     short loc_180009BE7
0x180009bf1  sub     r10, rdi
0x180009bf4  inc     rbx
0x180009bf7  cmp     rbx, r10
0x180009bfa  mov     rdx, r10; DestinationSize
0x180009bfd  mov     rcx, rdi; Destination
0x180009c00  cmovnb  rbx, r10
0x180009c04  mov     r9, rbx; SourceSize
0x180009c07  call    memcpy_s
0x180009c0c  mov     byte ptr [rbx+rdi-1], 0
0x180009c11  mov     al, 1
0x180009c13  add     rsp, 28h
0x180009c17  pop     rdi
0x180009c18  pop     rsi
0x180009c19  pop     rbp
0x180009c1a  pop     rbx
0x180009c1b  retn
```
