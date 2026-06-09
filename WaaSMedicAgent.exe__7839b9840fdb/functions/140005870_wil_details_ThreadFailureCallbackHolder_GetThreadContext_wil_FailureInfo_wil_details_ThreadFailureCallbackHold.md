# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140005870`
- end: `0x14000594c`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400050a0`
- `0x140005870`

## callees

- `0x140005870`
- `0x140007618`

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
0x140005870  push    rbx
0x140005872  push    rbp
0x140005873  push    rsi
0x140005874  push    rdi
0x140005875  sub     rsp, 28h
0x140005879  xor     al, al
0x14000587b  mov     byte ptr [r8], 0
0x14000587f  mov     rbp, r9
0x140005882  mov     rdi, r8
0x140005885  mov     rsi, rdx
0x140005888  mov     rbx, rcx
0x14000588b  test    rdx, rdx
0x14000588e  jz      loc_140005943
0x140005894  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140005898  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x14000589d  mov     rdx, [rsi+20h]
0x1400058a1  test    rdx, rdx
0x1400058a4  jz      loc_140005943
0x1400058aa  cmp     dword ptr [rdx], 0
0x1400058ad  jnz     short loc_1400058C0
0x1400058af  mov     eax, 1
0x1400058b4  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x1400058bc  inc     eax
0x1400058be  mov     [rdx], eax
0x1400058c0  cmp     dword ptr [rbx+50h], 0
0x1400058c4  jnz     short loc_1400058D7
0x1400058c6  movups  xmm0, xmmword ptr [rdx]
0x1400058c9  movups  xmmword ptr [rbx+50h], xmm0
0x1400058cd  movsd   xmm1, qword ptr [rdx+10h]
0x1400058d2  movsd   qword ptr [rbx+60h], xmm1
0x1400058d7  movups  xmm0, xmmword ptr [rdx]
0x1400058da  lea     r10, [rdi+rbp]
0x1400058de  movups  xmmword ptr [rbx+68h], xmm0
0x1400058e2  movsd   xmm1, qword ptr [rdx+10h]
0x1400058e7  movsd   qword ptr [rbx+78h], xmm1
0x1400058ec  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400058f0  mov     rax, rbx
0x1400058f3  inc     rax
0x1400058f6  cmp     byte ptr [rdi+rax], 0
0x1400058fa  jnz     short loc_1400058F3
0x1400058fc  lea     rcx, [rax+rdi]
0x140005900  mov     rax, r10
0x140005903  sub     rax, rcx
0x140005906  cmp     rax, 2
0x14000590a  jle     short loc_140005941
0x14000590c  mov     byte ptr [rcx], 5Ch ; '\'
0x14000590f  lea     rdi, [rcx+1]
0x140005913  mov     r8, [rdx+8]; Source
0x140005917  inc     rbx
0x14000591a  cmp     byte ptr [r8+rbx], 0
0x14000591f  jnz     short loc_140005917
0x140005921  sub     r10, rdi
0x140005924  inc     rbx
0x140005927  cmp     rbx, r10
0x14000592a  mov     rdx, r10; DestinationSize
0x14000592d  mov     rcx, rdi; Destination
0x140005930  cmovnb  rbx, r10
0x140005934  mov     r9, rbx; SourceSize
0x140005937  call    memcpy_s
0x14000593c  mov     byte ptr [rbx+rdi-1], 0
0x140005941  mov     al, 1
0x140005943  add     rsp, 28h
0x140005947  pop     rdi
0x140005948  pop     rsi
0x140005949  pop     rbp
0x14000594a  pop     rbx
0x14000594b  retn
```
