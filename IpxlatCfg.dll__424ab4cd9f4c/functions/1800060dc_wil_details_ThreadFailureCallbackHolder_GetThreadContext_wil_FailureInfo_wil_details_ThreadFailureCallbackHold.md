# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x1800060dc`
- end: `0x1800061b8`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800059e0`
- `0x1800060dc`

## callees

- `0x1800060dc`
- `0x18000a168`

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
0x1800060dc  push    rbx
0x1800060de  push    rbp
0x1800060df  push    rsi
0x1800060e0  push    rdi
0x1800060e1  sub     rsp, 28h
0x1800060e5  xor     al, al
0x1800060e7  mov     byte ptr [r8], 0
0x1800060eb  mov     rbp, r9
0x1800060ee  mov     rdi, r8
0x1800060f1  mov     rsi, rdx
0x1800060f4  mov     rbx, rcx
0x1800060f7  test    rdx, rdx
0x1800060fa  jz      loc_1800061AF
0x180006100  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180006104  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180006109  mov     rdx, [rsi+20h]
0x18000610d  test    rdx, rdx
0x180006110  jz      loc_1800061AF
0x180006116  cmp     dword ptr [rdx], 0
0x180006119  jnz     short loc_18000612C
0x18000611b  mov     eax, 1
0x180006120  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180006128  inc     eax
0x18000612a  mov     [rdx], eax
0x18000612c  cmp     dword ptr [rbx+50h], 0
0x180006130  jnz     short loc_180006143
0x180006132  movups  xmm0, xmmword ptr [rdx]
0x180006135  movups  xmmword ptr [rbx+50h], xmm0
0x180006139  movsd   xmm1, qword ptr [rdx+10h]
0x18000613e  movsd   qword ptr [rbx+60h], xmm1
0x180006143  movups  xmm0, xmmword ptr [rdx]
0x180006146  lea     r10, [rdi+rbp]
0x18000614a  movups  xmmword ptr [rbx+68h], xmm0
0x18000614e  movsd   xmm1, qword ptr [rdx+10h]
0x180006153  movsd   qword ptr [rbx+78h], xmm1
0x180006158  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000615c  mov     rax, rbx
0x18000615f  inc     rax
0x180006162  cmp     byte ptr [rdi+rax], 0
0x180006166  jnz     short loc_18000615F
0x180006168  lea     rcx, [rax+rdi]
0x18000616c  mov     rax, r10
0x18000616f  sub     rax, rcx
0x180006172  cmp     rax, 2
0x180006176  jle     short loc_1800061AD
0x180006178  mov     byte ptr [rcx], 5Ch ; '\'
0x18000617b  lea     rdi, [rcx+1]
0x18000617f  mov     r8, [rdx+8]; Source
0x180006183  inc     rbx
0x180006186  cmp     byte ptr [r8+rbx], 0
0x18000618b  jnz     short loc_180006183
0x18000618d  sub     r10, rdi
0x180006190  inc     rbx
0x180006193  cmp     rbx, r10
0x180006196  mov     rdx, r10; DestinationSize
0x180006199  mov     rcx, rdi; Destination
0x18000619c  cmovnb  rbx, r10
0x1800061a0  mov     r9, rbx; SourceSize
0x1800061a3  call    memcpy_s
0x1800061a8  mov     byte ptr [rbx+rdi-1], 0
0x1800061ad  mov     al, 1
0x1800061af  add     rsp, 28h
0x1800061b3  pop     rdi
0x1800061b4  pop     rsi
0x1800061b5  pop     rbp
0x1800061b6  pop     rbx
0x1800061b7  retn
```
