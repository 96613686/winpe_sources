# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x1400059d0`
- end: `0x140005aac`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140005224`
- `0x1400059d0`

## callees

- `0x1400059d0`
- `0x140007ea4`

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
0x1400059d0  push    rbx
0x1400059d2  push    rbp
0x1400059d3  push    rsi
0x1400059d4  push    rdi
0x1400059d5  sub     rsp, 28h
0x1400059d9  xor     al, al
0x1400059db  mov     byte ptr [r8], 0
0x1400059df  mov     rbp, r9
0x1400059e2  mov     rdi, r8
0x1400059e5  mov     rsi, rdx
0x1400059e8  mov     rbx, rcx
0x1400059eb  test    rdx, rdx
0x1400059ee  jz      loc_140005AA3
0x1400059f4  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x1400059f8  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1400059fd  mov     rdx, [rsi+20h]
0x140005a01  test    rdx, rdx
0x140005a04  jz      loc_140005AA3
0x140005a0a  cmp     dword ptr [rdx], 0
0x140005a0d  jnz     short loc_140005A20
0x140005a0f  mov     eax, 1
0x140005a14  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140005a1c  inc     eax
0x140005a1e  mov     [rdx], eax
0x140005a20  cmp     dword ptr [rbx+50h], 0
0x140005a24  jnz     short loc_140005A37
0x140005a26  movups  xmm0, xmmword ptr [rdx]
0x140005a29  movups  xmmword ptr [rbx+50h], xmm0
0x140005a2d  movsd   xmm1, qword ptr [rdx+10h]
0x140005a32  movsd   qword ptr [rbx+60h], xmm1
0x140005a37  movups  xmm0, xmmword ptr [rdx]
0x140005a3a  lea     r10, [rdi+rbp]
0x140005a3e  movups  xmmword ptr [rbx+68h], xmm0
0x140005a42  movsd   xmm1, qword ptr [rdx+10h]
0x140005a47  movsd   qword ptr [rbx+78h], xmm1
0x140005a4c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140005a50  mov     rax, rbx
0x140005a53  inc     rax
0x140005a56  cmp     byte ptr [rdi+rax], 0
0x140005a5a  jnz     short loc_140005A53
0x140005a5c  lea     rcx, [rax+rdi]
0x140005a60  mov     rax, r10
0x140005a63  sub     rax, rcx
0x140005a66  cmp     rax, 2
0x140005a6a  jle     short loc_140005AA1
0x140005a6c  mov     byte ptr [rcx], 5Ch ; '\'
0x140005a6f  lea     rdi, [rcx+1]
0x140005a73  mov     r8, [rdx+8]; Source
0x140005a77  inc     rbx
0x140005a7a  cmp     byte ptr [r8+rbx], 0
0x140005a7f  jnz     short loc_140005A77
0x140005a81  sub     r10, rdi
0x140005a84  inc     rbx
0x140005a87  cmp     rbx, r10
0x140005a8a  mov     rdx, r10; DestinationSize
0x140005a8d  mov     rcx, rdi; Destination
0x140005a90  cmovnb  rbx, r10
0x140005a94  mov     r9, rbx; SourceSize
0x140005a97  call    memcpy_s
0x140005a9c  mov     byte ptr [rbx+rdi-1], 0
0x140005aa1  mov     al, 1
0x140005aa3  add     rsp, 28h
0x140005aa7  pop     rdi
0x140005aa8  pop     rsi
0x140005aa9  pop     rbp
0x140005aaa  pop     rbx
0x140005aab  retn
```
