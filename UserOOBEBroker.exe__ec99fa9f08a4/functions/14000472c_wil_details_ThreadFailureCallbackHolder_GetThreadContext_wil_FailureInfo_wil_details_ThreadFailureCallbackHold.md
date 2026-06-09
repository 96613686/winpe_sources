# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x14000472c`
- end: `0x140004809`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400040f0`
- `0x14000472c`

## callees

- `0x14000472c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1400047f3`
- `msvcrt!memcpy_s` at `0x1400047f3`

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
0x14000472c  push    rbx
0x14000472e  push    rbp
0x14000472f  push    rsi
0x140004730  push    rdi
0x140004731  sub     rsp, 28h
0x140004735  xor     al, al
0x140004737  mov     byte ptr [r8], 0
0x14000473b  mov     rbp, r9
0x14000473e  mov     rdi, r8
0x140004741  mov     rsi, rdx
0x140004744  mov     rbx, rcx
0x140004747  test    rdx, rdx
0x14000474a  jz      loc_140004800
0x140004750  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140004754  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140004759  mov     rdx, [rsi+20h]
0x14000475d  test    rdx, rdx
0x140004760  jz      loc_140004800
0x140004766  cmp     dword ptr [rdx], 0
0x140004769  jnz     short loc_14000477C
0x14000476b  mov     eax, 1
0x140004770  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140004778  inc     eax
0x14000477a  mov     [rdx], eax
0x14000477c  cmp     dword ptr [rbx+50h], 0
0x140004780  jnz     short loc_140004793
0x140004782  movups  xmm0, xmmword ptr [rdx]
0x140004785  movups  xmmword ptr [rbx+50h], xmm0
0x140004789  movsd   xmm1, qword ptr [rdx+10h]
0x14000478e  movsd   qword ptr [rbx+60h], xmm1
0x140004793  movups  xmm0, xmmword ptr [rdx]
0x140004796  lea     r10, [rdi+rbp]
0x14000479a  movups  xmmword ptr [rbx+68h], xmm0
0x14000479e  movsd   xmm1, qword ptr [rdx+10h]
0x1400047a3  movsd   qword ptr [rbx+78h], xmm1
0x1400047a8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400047ac  mov     rax, rbx
0x1400047af  inc     rax
0x1400047b2  cmp     byte ptr [rdi+rax], 0
0x1400047b6  jnz     short loc_1400047AF
0x1400047b8  lea     rcx, [rax+rdi]
0x1400047bc  mov     rax, r10
0x1400047bf  sub     rax, rcx
0x1400047c2  cmp     rax, 2
0x1400047c6  jle     short loc_1400047FE
0x1400047c8  mov     byte ptr [rcx], 5Ch ; '\'
0x1400047cb  lea     rdi, [rcx+1]
0x1400047cf  mov     r8, [rdx+8]; Source
0x1400047d3  inc     rbx
0x1400047d6  cmp     byte ptr [r8+rbx], 0
0x1400047db  jnz     short loc_1400047D3
0x1400047dd  sub     r10, rdi
0x1400047e0  inc     rbx
0x1400047e3  cmp     rbx, r10
0x1400047e6  mov     rdx, r10; DestinationSize
0x1400047e9  mov     rcx, rdi; Destination
0x1400047ec  cmovnb  rbx, r10
0x1400047f0  mov     r9, rbx; SourceSize
0x1400047f3  call    cs:__imp_memcpy_s
0x1400047f9  mov     byte ptr [rbx+rdi-1], 0
0x1400047fe  mov     al, 1
0x140004800  add     rsp, 28h
0x140004804  pop     rdi
0x140004805  pop     rsi
0x140004806  pop     rbp
0x140004807  pop     rbx
0x140004808  retn
```
