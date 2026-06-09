# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180004ffc`
- end: `0x1800050d8`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004900`
- `0x180004ffc`

## callees

- `0x180004ffc`
- `0x180007308`

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
0x180004ffc  push    rbx
0x180004ffe  push    rbp
0x180004fff  push    rsi
0x180005000  push    rdi
0x180005001  sub     rsp, 28h
0x180005005  xor     al, al
0x180005007  mov     byte ptr [r8], 0
0x18000500b  mov     rbp, r9
0x18000500e  mov     rdi, r8
0x180005011  mov     rsi, rdx
0x180005014  mov     rbx, rcx
0x180005017  test    rdx, rdx
0x18000501a  jz      loc_1800050CF
0x180005020  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180005024  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005029  mov     rdx, [rsi+20h]
0x18000502d  test    rdx, rdx
0x180005030  jz      loc_1800050CF
0x180005036  cmp     dword ptr [rdx], 0
0x180005039  jnz     short loc_18000504C
0x18000503b  mov     eax, 1
0x180005040  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180005048  inc     eax
0x18000504a  mov     [rdx], eax
0x18000504c  cmp     dword ptr [rbx+50h], 0
0x180005050  jnz     short loc_180005063
0x180005052  movups  xmm0, xmmword ptr [rdx]
0x180005055  movups  xmmword ptr [rbx+50h], xmm0
0x180005059  movsd   xmm1, qword ptr [rdx+10h]
0x18000505e  movsd   qword ptr [rbx+60h], xmm1
0x180005063  movups  xmm0, xmmword ptr [rdx]
0x180005066  lea     r10, [rdi+rbp]
0x18000506a  movups  xmmword ptr [rbx+68h], xmm0
0x18000506e  movsd   xmm1, qword ptr [rdx+10h]
0x180005073  movsd   qword ptr [rbx+78h], xmm1
0x180005078  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000507c  mov     rax, rbx
0x18000507f  inc     rax
0x180005082  cmp     byte ptr [rdi+rax], 0
0x180005086  jnz     short loc_18000507F
0x180005088  lea     rcx, [rax+rdi]
0x18000508c  mov     rax, r10
0x18000508f  sub     rax, rcx
0x180005092  cmp     rax, 2
0x180005096  jle     short loc_1800050CD
0x180005098  mov     byte ptr [rcx], 5Ch ; '\'
0x18000509b  lea     rdi, [rcx+1]
0x18000509f  mov     r8, [rdx+8]; Source
0x1800050a3  inc     rbx
0x1800050a6  cmp     byte ptr [r8+rbx], 0
0x1800050ab  jnz     short loc_1800050A3
0x1800050ad  sub     r10, rdi
0x1800050b0  inc     rbx
0x1800050b3  cmp     rbx, r10
0x1800050b6  mov     rdx, r10; DestinationSize
0x1800050b9  mov     rcx, rdi; Destination
0x1800050bc  cmovnb  rbx, r10
0x1800050c0  mov     r9, rbx; SourceSize
0x1800050c3  call    memcpy_s
0x1800050c8  mov     byte ptr [rbx+rdi-1], 0
0x1800050cd  mov     al, 1
0x1800050cf  add     rsp, 28h
0x1800050d3  pop     rdi
0x1800050d4  pop     rsi
0x1800050d5  pop     rbp
0x1800050d6  pop     rbx
0x1800050d7  retn
```
