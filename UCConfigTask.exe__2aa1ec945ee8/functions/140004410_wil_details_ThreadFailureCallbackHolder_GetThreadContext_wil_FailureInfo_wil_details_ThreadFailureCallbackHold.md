# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140004410`
- end: `0x1400044ec`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140003d24`
- `0x140004410`

## callees

- `0x140004410`
- `0x140007a00`

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
0x140004410  push    rbx
0x140004412  push    rbp
0x140004413  push    rsi
0x140004414  push    rdi
0x140004415  sub     rsp, 28h
0x140004419  xor     al, al
0x14000441b  mov     byte ptr [r8], 0
0x14000441f  mov     rbp, r9
0x140004422  mov     rdi, r8
0x140004425  mov     rsi, rdx
0x140004428  mov     rbx, rcx
0x14000442b  test    rdx, rdx
0x14000442e  jz      loc_1400044E3
0x140004434  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140004438  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x14000443d  mov     rdx, [rsi+20h]
0x140004441  test    rdx, rdx
0x140004444  jz      loc_1400044E3
0x14000444a  cmp     dword ptr [rdx], 0
0x14000444d  jnz     short loc_140004460
0x14000444f  mov     eax, 1
0x140004454  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x14000445c  inc     eax
0x14000445e  mov     [rdx], eax
0x140004460  cmp     dword ptr [rbx+50h], 0
0x140004464  jnz     short loc_140004477
0x140004466  movups  xmm0, xmmword ptr [rdx]
0x140004469  movups  xmmword ptr [rbx+50h], xmm0
0x14000446d  movsd   xmm1, qword ptr [rdx+10h]
0x140004472  movsd   qword ptr [rbx+60h], xmm1
0x140004477  movups  xmm0, xmmword ptr [rdx]
0x14000447a  lea     r10, [rdi+rbp]
0x14000447e  movups  xmmword ptr [rbx+68h], xmm0
0x140004482  movsd   xmm1, qword ptr [rdx+10h]
0x140004487  movsd   qword ptr [rbx+78h], xmm1
0x14000448c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140004490  mov     rax, rbx
0x140004493  inc     rax
0x140004496  cmp     byte ptr [rdi+rax], 0
0x14000449a  jnz     short loc_140004493
0x14000449c  lea     rcx, [rax+rdi]
0x1400044a0  mov     rax, r10
0x1400044a3  sub     rax, rcx
0x1400044a6  cmp     rax, 2
0x1400044aa  jle     short loc_1400044E1
0x1400044ac  mov     byte ptr [rcx], 5Ch ; '\'
0x1400044af  lea     rdi, [rcx+1]
0x1400044b3  mov     r8, [rdx+8]; Source
0x1400044b7  inc     rbx
0x1400044ba  cmp     byte ptr [r8+rbx], 0
0x1400044bf  jnz     short loc_1400044B7
0x1400044c1  sub     r10, rdi
0x1400044c4  inc     rbx
0x1400044c7  cmp     rbx, r10
0x1400044ca  mov     rdx, r10; DestinationSize
0x1400044cd  mov     rcx, rdi; Destination
0x1400044d0  cmovnb  rbx, r10
0x1400044d4  mov     r9, rbx; SourceSize
0x1400044d7  call    memcpy_s
0x1400044dc  mov     byte ptr [rbx+rdi-1], 0
0x1400044e1  mov     al, 1
0x1400044e3  add     rsp, 28h
0x1400044e7  pop     rdi
0x1400044e8  pop     rsi
0x1400044e9  pop     rbp
0x1400044ea  pop     rbx
0x1400044eb  retn
```
