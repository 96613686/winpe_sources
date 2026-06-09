# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180005800`
- end: `0x1800058dc`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800050a0`
- `0x180005800`

## callees

- `0x180005800`
- `0x1800080e0`

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
        memcpy_s_0(v18, v16, v15, v17);
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
0x180005800  push    rbx
0x180005802  push    rbp
0x180005803  push    rsi
0x180005804  push    rdi
0x180005805  sub     rsp, 28h
0x180005809  xor     al, al
0x18000580b  mov     byte ptr [r8], 0
0x18000580f  mov     rbp, r9
0x180005812  mov     rdi, r8
0x180005815  mov     rsi, rdx
0x180005818  mov     rbx, rcx
0x18000581b  test    rdx, rdx
0x18000581e  jz      loc_1800058D3
0x180005824  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180005828  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000582d  mov     rdx, [rsi+20h]
0x180005831  test    rdx, rdx
0x180005834  jz      loc_1800058D3
0x18000583a  cmp     dword ptr [rdx], 0
0x18000583d  jnz     short loc_180005850
0x18000583f  mov     eax, 1
0x180005844  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000584c  inc     eax
0x18000584e  mov     [rdx], eax
0x180005850  cmp     dword ptr [rbx+50h], 0
0x180005854  jnz     short loc_180005867
0x180005856  movups  xmm0, xmmword ptr [rdx]
0x180005859  movups  xmmword ptr [rbx+50h], xmm0
0x18000585d  movsd   xmm1, qword ptr [rdx+10h]
0x180005862  movsd   qword ptr [rbx+60h], xmm1
0x180005867  movups  xmm0, xmmword ptr [rdx]
0x18000586a  lea     r10, [rdi+rbp]
0x18000586e  movups  xmmword ptr [rbx+68h], xmm0
0x180005872  movsd   xmm1, qword ptr [rdx+10h]
0x180005877  movsd   qword ptr [rbx+78h], xmm1
0x18000587c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005880  mov     rax, rbx
0x180005883  inc     rax
0x180005886  cmp     byte ptr [rdi+rax], 0
0x18000588a  jnz     short loc_180005883
0x18000588c  lea     rcx, [rax+rdi]
0x180005890  mov     rax, r10
0x180005893  sub     rax, rcx
0x180005896  cmp     rax, 2
0x18000589a  jle     short loc_1800058D1
0x18000589c  mov     byte ptr [rcx], 5Ch ; '\'
0x18000589f  lea     rdi, [rcx+1]
0x1800058a3  mov     r8, [rdx+8]; Source
0x1800058a7  inc     rbx
0x1800058aa  cmp     byte ptr [r8+rbx], 0
0x1800058af  jnz     short loc_1800058A7
0x1800058b1  sub     r10, rdi
0x1800058b4  inc     rbx
0x1800058b7  cmp     rbx, r10
0x1800058ba  mov     rdx, r10; DestinationSize
0x1800058bd  mov     rcx, rdi; Destination
0x1800058c0  cmovnb  rbx, r10
0x1800058c4  mov     r9, rbx; SourceSize
0x1800058c7  call    memcpy_s_0
0x1800058cc  mov     byte ptr [rbx+rdi-1], 0
0x1800058d1  mov     al, 1
0x1800058d3  add     rsp, 28h
0x1800058d7  pop     rdi
0x1800058d8  pop     rsi
0x1800058d9  pop     rbp
0x1800058da  pop     rbx
0x1800058db  retn
```
