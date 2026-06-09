# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x1800104dc`
- end: `0x1800105b8`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ffc8`
- `0x1800104dc`

## callees

- `0x18000a182`
- `0x1800104dc`

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
0x1800104dc  push    rbx
0x1800104de  push    rbp
0x1800104df  push    rsi
0x1800104e0  push    rdi
0x1800104e1  sub     rsp, 28h
0x1800104e5  xor     al, al
0x1800104e7  mov     byte ptr [r8], 0
0x1800104eb  mov     rbp, r9
0x1800104ee  mov     rdi, r8
0x1800104f1  mov     rsi, rdx
0x1800104f4  mov     rbx, rcx
0x1800104f7  test    rdx, rdx
0x1800104fa  jz      loc_1800105AF
0x180010500  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180010504  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180010509  mov     rdx, [rsi+20h]
0x18001050d  test    rdx, rdx
0x180010510  jz      loc_1800105AF
0x180010516  cmp     dword ptr [rdx], 0
0x180010519  jnz     short loc_18001052C
0x18001051b  mov     eax, 1
0x180010520  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180010528  inc     eax
0x18001052a  mov     [rdx], eax
0x18001052c  cmp     dword ptr [rbx+50h], 0
0x180010530  jnz     short loc_180010543
0x180010532  movups  xmm0, xmmword ptr [rdx]
0x180010535  movups  xmmword ptr [rbx+50h], xmm0
0x180010539  movsd   xmm1, qword ptr [rdx+10h]
0x18001053e  movsd   qword ptr [rbx+60h], xmm1
0x180010543  movups  xmm0, xmmword ptr [rdx]
0x180010546  lea     r10, [rdi+rbp]
0x18001054a  movups  xmmword ptr [rbx+68h], xmm0
0x18001054e  movsd   xmm1, qword ptr [rdx+10h]
0x180010553  movsd   qword ptr [rbx+78h], xmm1
0x180010558  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001055c  mov     rax, rbx
0x18001055f  inc     rax
0x180010562  cmp     byte ptr [rdi+rax], 0
0x180010566  jnz     short loc_18001055F
0x180010568  lea     rcx, [rax+rdi]
0x18001056c  mov     rax, r10
0x18001056f  sub     rax, rcx
0x180010572  cmp     rax, 2
0x180010576  jle     short loc_1800105AD
0x180010578  mov     byte ptr [rcx], 5Ch ; '\'
0x18001057b  lea     rdi, [rcx+1]
0x18001057f  mov     r8, [rdx+8]; Source
0x180010583  inc     rbx
0x180010586  cmp     byte ptr [r8+rbx], 0
0x18001058b  jnz     short loc_180010583
0x18001058d  sub     r10, rdi
0x180010590  inc     rbx
0x180010593  cmp     rbx, r10
0x180010596  mov     rdx, r10; DestinationSize
0x180010599  mov     rcx, rdi; Destination
0x18001059c  cmovnb  rbx, r10
0x1800105a0  mov     r9, rbx; SourceSize
0x1800105a3  call    memcpy_s
0x1800105a8  mov     byte ptr [rbx+rdi-1], 0
0x1800105ad  mov     al, 1
0x1800105af  add     rsp, 28h
0x1800105b3  pop     rdi
0x1800105b4  pop     rsi
0x1800105b5  pop     rbp
0x1800105b6  pop     rbx
0x1800105b7  retn
```
