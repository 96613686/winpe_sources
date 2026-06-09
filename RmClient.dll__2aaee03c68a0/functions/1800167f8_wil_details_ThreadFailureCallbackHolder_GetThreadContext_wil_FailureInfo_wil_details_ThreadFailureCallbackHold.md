# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x1800167f8`
- end: `0x1800168d5`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001623c`
- `0x1800167f8`

## callees

- `0x1800167f8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800168bf`
- `msvcrt!memcpy_s` at `0x1800168bf`

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
0x1800167f8  push    rbx
0x1800167fa  push    rbp
0x1800167fb  push    rsi
0x1800167fc  push    rdi
0x1800167fd  sub     rsp, 28h
0x180016801  xor     al, al
0x180016803  mov     byte ptr [r8], 0
0x180016807  mov     rbp, r9
0x18001680a  mov     rdi, r8
0x18001680d  mov     rsi, rdx
0x180016810  mov     rbx, rcx
0x180016813  test    rdx, rdx
0x180016816  jz      loc_1800168CC
0x18001681c  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180016820  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180016825  mov     rdx, [rsi+20h]
0x180016829  test    rdx, rdx
0x18001682c  jz      loc_1800168CC
0x180016832  cmp     dword ptr [rdx], 0
0x180016835  jnz     short loc_180016848
0x180016837  mov     eax, 1
0x18001683c  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180016844  inc     eax
0x180016846  mov     [rdx], eax
0x180016848  cmp     dword ptr [rbx+50h], 0
0x18001684c  jnz     short loc_18001685F
0x18001684e  movups  xmm0, xmmword ptr [rdx]
0x180016851  movups  xmmword ptr [rbx+50h], xmm0
0x180016855  movsd   xmm1, qword ptr [rdx+10h]
0x18001685a  movsd   qword ptr [rbx+60h], xmm1
0x18001685f  movups  xmm0, xmmword ptr [rdx]
0x180016862  lea     r10, [rdi+rbp]
0x180016866  movups  xmmword ptr [rbx+68h], xmm0
0x18001686a  movsd   xmm1, qword ptr [rdx+10h]
0x18001686f  movsd   qword ptr [rbx+78h], xmm1
0x180016874  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180016878  mov     rax, rbx
0x18001687b  inc     rax
0x18001687e  cmp     byte ptr [rdi+rax], 0
0x180016882  jnz     short loc_18001687B
0x180016884  lea     rcx, [rax+rdi]
0x180016888  mov     rax, r10
0x18001688b  sub     rax, rcx
0x18001688e  cmp     rax, 2
0x180016892  jle     short loc_1800168CA
0x180016894  mov     byte ptr [rcx], 5Ch ; '\'
0x180016897  lea     rdi, [rcx+1]
0x18001689b  mov     r8, [rdx+8]; Source
0x18001689f  inc     rbx
0x1800168a2  cmp     byte ptr [r8+rbx], 0
0x1800168a7  jnz     short loc_18001689F
0x1800168a9  sub     r10, rdi
0x1800168ac  inc     rbx
0x1800168af  cmp     rbx, r10
0x1800168b2  mov     rdx, r10; DestinationSize
0x1800168b5  mov     rcx, rdi; Destination
0x1800168b8  cmovnb  rbx, r10
0x1800168bc  mov     r9, rbx; SourceSize
0x1800168bf  call    cs:__imp_memcpy_s
0x1800168c5  mov     byte ptr [rbx+rdi-1], 0
0x1800168ca  mov     al, 1
0x1800168cc  add     rsp, 28h
0x1800168d0  pop     rdi
0x1800168d1  pop     rsi
0x1800168d2  pop     rbp
0x1800168d3  pop     rbx
0x1800168d4  retn
```
