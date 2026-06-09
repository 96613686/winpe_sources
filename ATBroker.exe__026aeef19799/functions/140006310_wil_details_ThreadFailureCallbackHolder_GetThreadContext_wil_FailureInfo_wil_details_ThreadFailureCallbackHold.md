# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140006310`
- end: `0x1400063ed`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400059f0`
- `0x140006310`

## callees

- `0x140006310`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1400063d7`
- `msvcrt!memcpy_s` at `0x1400063d7`

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
0x140006310  push    rbx
0x140006312  push    rbp
0x140006313  push    rsi
0x140006314  push    rdi
0x140006315  sub     rsp, 28h
0x140006319  xor     al, al
0x14000631b  mov     byte ptr [r8], 0
0x14000631f  mov     rbp, r9
0x140006322  mov     rdi, r8
0x140006325  mov     rsi, rdx
0x140006328  mov     rbx, rcx
0x14000632b  test    rdx, rdx
0x14000632e  jz      loc_1400063E4
0x140006334  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140006338  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x14000633d  mov     rdx, [rsi+20h]
0x140006341  test    rdx, rdx
0x140006344  jz      loc_1400063E4
0x14000634a  cmp     dword ptr [rdx], 0
0x14000634d  jnz     short loc_140006360
0x14000634f  mov     eax, 1
0x140006354  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x14000635c  inc     eax
0x14000635e  mov     [rdx], eax
0x140006360  cmp     dword ptr [rbx+50h], 0
0x140006364  jnz     short loc_140006377
0x140006366  movups  xmm0, xmmword ptr [rdx]
0x140006369  movups  xmmword ptr [rbx+50h], xmm0
0x14000636d  movsd   xmm1, qword ptr [rdx+10h]
0x140006372  movsd   qword ptr [rbx+60h], xmm1
0x140006377  movups  xmm0, xmmword ptr [rdx]
0x14000637a  lea     r10, [rdi+rbp]
0x14000637e  movups  xmmword ptr [rbx+68h], xmm0
0x140006382  movsd   xmm1, qword ptr [rdx+10h]
0x140006387  movsd   qword ptr [rbx+78h], xmm1
0x14000638c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140006390  mov     rax, rbx
0x140006393  inc     rax
0x140006396  cmp     byte ptr [rdi+rax], 0
0x14000639a  jnz     short loc_140006393
0x14000639c  lea     rcx, [rax+rdi]
0x1400063a0  mov     rax, r10
0x1400063a3  sub     rax, rcx
0x1400063a6  cmp     rax, 2
0x1400063aa  jle     short loc_1400063E2
0x1400063ac  mov     byte ptr [rcx], 5Ch ; '\'
0x1400063af  lea     rdi, [rcx+1]
0x1400063b3  mov     r8, [rdx+8]; Source
0x1400063b7  inc     rbx
0x1400063ba  cmp     byte ptr [r8+rbx], 0
0x1400063bf  jnz     short loc_1400063B7
0x1400063c1  sub     r10, rdi
0x1400063c4  inc     rbx
0x1400063c7  cmp     rbx, r10
0x1400063ca  mov     rdx, r10; DestinationSize
0x1400063cd  mov     rcx, rdi; Destination
0x1400063d0  cmovnb  rbx, r10
0x1400063d4  mov     r9, rbx; SourceSize
0x1400063d7  call    cs:__imp_memcpy_s
0x1400063dd  mov     byte ptr [rbx+rdi-1], 0
0x1400063e2  mov     al, 1
0x1400063e4  add     rsp, 28h
0x1400063e8  pop     rdi
0x1400063e9  pop     rsi
0x1400063ea  pop     rbp
0x1400063eb  pop     rbx
0x1400063ec  retn
```
