# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000691c`
- end: `0x1800069f8`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006220`
- `0x18000691c`

## callees

- `0x18000691c`
- `0x180009ce8`

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
0x18000691c  push    rbx
0x18000691e  push    rbp
0x18000691f  push    rsi
0x180006920  push    rdi
0x180006921  sub     rsp, 28h
0x180006925  xor     al, al
0x180006927  mov     byte ptr [r8], 0
0x18000692b  mov     rbp, r9
0x18000692e  mov     rdi, r8
0x180006931  mov     rsi, rdx
0x180006934  mov     rbx, rcx
0x180006937  test    rdx, rdx
0x18000693a  jz      loc_1800069EF
0x180006940  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180006944  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180006949  mov     rdx, [rsi+20h]
0x18000694d  test    rdx, rdx
0x180006950  jz      loc_1800069EF
0x180006956  cmp     dword ptr [rdx], 0
0x180006959  jnz     short loc_18000696C
0x18000695b  mov     eax, 1
0x180006960  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180006968  inc     eax
0x18000696a  mov     [rdx], eax
0x18000696c  cmp     dword ptr [rbx+50h], 0
0x180006970  jnz     short loc_180006983
0x180006972  movups  xmm0, xmmword ptr [rdx]
0x180006975  movups  xmmword ptr [rbx+50h], xmm0
0x180006979  movsd   xmm1, qword ptr [rdx+10h]
0x18000697e  movsd   qword ptr [rbx+60h], xmm1
0x180006983  movups  xmm0, xmmword ptr [rdx]
0x180006986  lea     r10, [rdi+rbp]
0x18000698a  movups  xmmword ptr [rbx+68h], xmm0
0x18000698e  movsd   xmm1, qword ptr [rdx+10h]
0x180006993  movsd   qword ptr [rbx+78h], xmm1
0x180006998  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000699c  mov     rax, rbx
0x18000699f  inc     rax
0x1800069a2  cmp     byte ptr [rdi+rax], 0
0x1800069a6  jnz     short loc_18000699F
0x1800069a8  lea     rcx, [rax+rdi]
0x1800069ac  mov     rax, r10
0x1800069af  sub     rax, rcx
0x1800069b2  cmp     rax, 2
0x1800069b6  jle     short loc_1800069ED
0x1800069b8  mov     byte ptr [rcx], 5Ch ; '\'
0x1800069bb  lea     rdi, [rcx+1]
0x1800069bf  mov     r8, [rdx+8]; Source
0x1800069c3  inc     rbx
0x1800069c6  cmp     byte ptr [r8+rbx], 0
0x1800069cb  jnz     short loc_1800069C3
0x1800069cd  sub     r10, rdi
0x1800069d0  inc     rbx
0x1800069d3  cmp     rbx, r10
0x1800069d6  mov     rdx, r10; DestinationSize
0x1800069d9  mov     rcx, rdi; Destination
0x1800069dc  cmovnb  rbx, r10
0x1800069e0  mov     r9, rbx; SourceSize
0x1800069e3  call    memcpy_s
0x1800069e8  mov     byte ptr [rbx+rdi-1], 0
0x1800069ed  mov     al, 1
0x1800069ef  add     rsp, 28h
0x1800069f3  pop     rdi
0x1800069f4  pop     rsi
0x1800069f5  pop     rbp
0x1800069f6  pop     rbx
0x1800069f7  retn
```
