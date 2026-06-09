# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140003aec`
- end: `0x140003bc8`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400033f0`
- `0x140003aec`

## callees

- `0x140003aec`
- `0x140005768`

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
0x140003aec  push    rbx
0x140003aee  push    rbp
0x140003aef  push    rsi
0x140003af0  push    rdi
0x140003af1  sub     rsp, 28h
0x140003af5  xor     al, al
0x140003af7  mov     byte ptr [r8], 0
0x140003afb  mov     rbp, r9
0x140003afe  mov     rdi, r8
0x140003b01  mov     rsi, rdx
0x140003b04  mov     rbx, rcx
0x140003b07  test    rdx, rdx
0x140003b0a  jz      loc_140003BBF
0x140003b10  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140003b14  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140003b19  mov     rdx, [rsi+20h]
0x140003b1d  test    rdx, rdx
0x140003b20  jz      loc_140003BBF
0x140003b26  cmp     dword ptr [rdx], 0
0x140003b29  jnz     short loc_140003B3C
0x140003b2b  mov     eax, 1
0x140003b30  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140003b38  inc     eax
0x140003b3a  mov     [rdx], eax
0x140003b3c  cmp     dword ptr [rbx+50h], 0
0x140003b40  jnz     short loc_140003B53
0x140003b42  movups  xmm0, xmmword ptr [rdx]
0x140003b45  movups  xmmword ptr [rbx+50h], xmm0
0x140003b49  movsd   xmm1, qword ptr [rdx+10h]
0x140003b4e  movsd   qword ptr [rbx+60h], xmm1
0x140003b53  movups  xmm0, xmmword ptr [rdx]
0x140003b56  lea     r10, [rdi+rbp]
0x140003b5a  movups  xmmword ptr [rbx+68h], xmm0
0x140003b5e  movsd   xmm1, qword ptr [rdx+10h]
0x140003b63  movsd   qword ptr [rbx+78h], xmm1
0x140003b68  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140003b6c  mov     rax, rbx
0x140003b6f  inc     rax
0x140003b72  cmp     byte ptr [rdi+rax], 0
0x140003b76  jnz     short loc_140003B6F
0x140003b78  lea     rcx, [rax+rdi]
0x140003b7c  mov     rax, r10
0x140003b7f  sub     rax, rcx
0x140003b82  cmp     rax, 2
0x140003b86  jle     short loc_140003BBD
0x140003b88  mov     byte ptr [rcx], 5Ch ; '\'
0x140003b8b  lea     rdi, [rcx+1]
0x140003b8f  mov     r8, [rdx+8]; Source
0x140003b93  inc     rbx
0x140003b96  cmp     byte ptr [r8+rbx], 0
0x140003b9b  jnz     short loc_140003B93
0x140003b9d  sub     r10, rdi
0x140003ba0  inc     rbx
0x140003ba3  cmp     rbx, r10
0x140003ba6  mov     rdx, r10; DestinationSize
0x140003ba9  mov     rcx, rdi; Destination
0x140003bac  cmovnb  rbx, r10
0x140003bb0  mov     r9, rbx; SourceSize
0x140003bb3  call    memcpy_s
0x140003bb8  mov     byte ptr [rbx+rdi-1], 0
0x140003bbd  mov     al, 1
0x140003bbf  add     rsp, 28h
0x140003bc3  pop     rdi
0x140003bc4  pop     rsi
0x140003bc5  pop     rbp
0x140003bc6  pop     rbx
0x140003bc7  retn
```
