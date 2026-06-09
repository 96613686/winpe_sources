# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140008cf0`
- end: `0x140008dcc`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400088b0`
- `0x140008cf0`

## callees

- `0x140008cf0`
- `0x14000bfd0`

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
0x140008cf0  push    rbx
0x140008cf2  push    rbp
0x140008cf3  push    rsi
0x140008cf4  push    rdi
0x140008cf5  sub     rsp, 28h
0x140008cf9  xor     al, al
0x140008cfb  mov     byte ptr [r8], 0
0x140008cff  mov     rbp, r9
0x140008d02  mov     rdi, r8
0x140008d05  mov     rsi, rdx
0x140008d08  mov     rbx, rcx
0x140008d0b  test    rdx, rdx
0x140008d0e  jz      loc_140008DC3
0x140008d14  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140008d18  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140008d1d  mov     rdx, [rsi+20h]
0x140008d21  test    rdx, rdx
0x140008d24  jz      loc_140008DC3
0x140008d2a  cmp     dword ptr [rdx], 0
0x140008d2d  jnz     short loc_140008D40
0x140008d2f  mov     eax, 1
0x140008d34  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140008d3c  inc     eax
0x140008d3e  mov     [rdx], eax
0x140008d40  cmp     dword ptr [rbx+50h], 0
0x140008d44  jnz     short loc_140008D57
0x140008d46  movups  xmm0, xmmword ptr [rdx]
0x140008d49  movups  xmmword ptr [rbx+50h], xmm0
0x140008d4d  movsd   xmm1, qword ptr [rdx+10h]
0x140008d52  movsd   qword ptr [rbx+60h], xmm1
0x140008d57  movups  xmm0, xmmword ptr [rdx]
0x140008d5a  lea     r10, [rdi+rbp]
0x140008d5e  movups  xmmword ptr [rbx+68h], xmm0
0x140008d62  movsd   xmm1, qword ptr [rdx+10h]
0x140008d67  movsd   qword ptr [rbx+78h], xmm1
0x140008d6c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140008d70  mov     rax, rbx
0x140008d73  inc     rax
0x140008d76  cmp     byte ptr [rdi+rax], 0
0x140008d7a  jnz     short loc_140008D73
0x140008d7c  lea     rcx, [rax+rdi]
0x140008d80  mov     rax, r10
0x140008d83  sub     rax, rcx
0x140008d86  cmp     rax, 2
0x140008d8a  jle     short loc_140008DC1
0x140008d8c  mov     byte ptr [rcx], 5Ch ; '\'
0x140008d8f  lea     rdi, [rcx+1]
0x140008d93  mov     r8, [rdx+8]; Source
0x140008d97  inc     rbx
0x140008d9a  cmp     byte ptr [r8+rbx], 0
0x140008d9f  jnz     short loc_140008D97
0x140008da1  sub     r10, rdi
0x140008da4  inc     rbx
0x140008da7  cmp     rbx, r10
0x140008daa  mov     rdx, r10; DestinationSize
0x140008dad  mov     rcx, rdi; Destination
0x140008db0  cmovnb  rbx, r10
0x140008db4  mov     r9, rbx; SourceSize
0x140008db7  call    memcpy_s
0x140008dbc  mov     byte ptr [rbx+rdi-1], 0
0x140008dc1  mov     al, 1
0x140008dc3  add     rsp, 28h
0x140008dc7  pop     rdi
0x140008dc8  pop     rsi
0x140008dc9  pop     rbp
0x140008dca  pop     rbx
0x140008dcb  retn
```
