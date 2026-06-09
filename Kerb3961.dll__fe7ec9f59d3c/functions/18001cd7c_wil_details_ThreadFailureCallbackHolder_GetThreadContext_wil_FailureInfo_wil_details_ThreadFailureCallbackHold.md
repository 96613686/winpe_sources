# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18001cd7c`
- end: `0x18001ce58`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001cb70`
- `0x18001cd7c`

## callees

- `0x1800185ac`
- `0x18001cd7c`

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
0x18001cd7c  push    rbx
0x18001cd7e  push    rbp
0x18001cd7f  push    rsi
0x18001cd80  push    rdi
0x18001cd81  sub     rsp, 28h
0x18001cd85  xor     al, al
0x18001cd87  mov     byte ptr [r8], 0
0x18001cd8b  mov     rbp, r9
0x18001cd8e  mov     rdi, r8
0x18001cd91  mov     rsi, rdx
0x18001cd94  mov     rbx, rcx
0x18001cd97  test    rdx, rdx
0x18001cd9a  jz      loc_18001CE4F
0x18001cda0  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18001cda4  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18001cda9  mov     rdx, [rsi+20h]
0x18001cdad  test    rdx, rdx
0x18001cdb0  jz      loc_18001CE4F
0x18001cdb6  cmp     dword ptr [rdx], 0
0x18001cdb9  jnz     short loc_18001CDCC
0x18001cdbb  mov     eax, 1
0x18001cdc0  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18001cdc8  inc     eax
0x18001cdca  mov     [rdx], eax
0x18001cdcc  cmp     dword ptr [rbx+50h], 0
0x18001cdd0  jnz     short loc_18001CDE3
0x18001cdd2  movups  xmm0, xmmword ptr [rdx]
0x18001cdd5  movups  xmmword ptr [rbx+50h], xmm0
0x18001cdd9  movsd   xmm1, qword ptr [rdx+10h]
0x18001cdde  movsd   qword ptr [rbx+60h], xmm1
0x18001cde3  movups  xmm0, xmmword ptr [rdx]
0x18001cde6  lea     r10, [rdi+rbp]
0x18001cdea  movups  xmmword ptr [rbx+68h], xmm0
0x18001cdee  movsd   xmm1, qword ptr [rdx+10h]
0x18001cdf3  movsd   qword ptr [rbx+78h], xmm1
0x18001cdf8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001cdfc  mov     rax, rbx
0x18001cdff  inc     rax
0x18001ce02  cmp     byte ptr [rdi+rax], 0
0x18001ce06  jnz     short loc_18001CDFF
0x18001ce08  lea     rcx, [rax+rdi]
0x18001ce0c  mov     rax, r10
0x18001ce0f  sub     rax, rcx
0x18001ce12  cmp     rax, 2
0x18001ce16  jle     short loc_18001CE4D
0x18001ce18  mov     byte ptr [rcx], 5Ch ; '\'
0x18001ce1b  lea     rdi, [rcx+1]
0x18001ce1f  mov     r8, [rdx+8]; Source
0x18001ce23  inc     rbx
0x18001ce26  cmp     byte ptr [r8+rbx], 0
0x18001ce2b  jnz     short loc_18001CE23
0x18001ce2d  sub     r10, rdi
0x18001ce30  inc     rbx
0x18001ce33  cmp     rbx, r10
0x18001ce36  mov     rdx, r10; DestinationSize
0x18001ce39  mov     rcx, rdi; Destination
0x18001ce3c  cmovnb  rbx, r10
0x18001ce40  mov     r9, rbx; SourceSize
0x18001ce43  call    memcpy_s
0x18001ce48  mov     byte ptr [rbx+rdi-1], 0
0x18001ce4d  mov     al, 1
0x18001ce4f  add     rsp, 28h
0x18001ce53  pop     rdi
0x18001ce54  pop     rsi
0x18001ce55  pop     rbp
0x18001ce56  pop     rbx
0x18001ce57  retn
```
