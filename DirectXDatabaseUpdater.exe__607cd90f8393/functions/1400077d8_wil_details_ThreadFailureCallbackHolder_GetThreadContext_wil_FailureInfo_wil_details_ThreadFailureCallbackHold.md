# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x1400077d8`
- end: `0x1400078b4`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400070a4`
- `0x1400077d8`

## callees

- `0x1400077d8`
- `0x14000eff0`

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
0x1400077d8  push    rbx
0x1400077da  push    rbp
0x1400077db  push    rsi
0x1400077dc  push    rdi
0x1400077dd  sub     rsp, 28h
0x1400077e1  xor     al, al
0x1400077e3  mov     byte ptr [r8], 0
0x1400077e7  mov     rbp, r9
0x1400077ea  mov     rdi, r8
0x1400077ed  mov     rsi, rdx
0x1400077f0  mov     rbx, rcx
0x1400077f3  test    rdx, rdx
0x1400077f6  jz      loc_1400078AB
0x1400077fc  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140007800  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140007805  mov     rdx, [rsi+20h]
0x140007809  test    rdx, rdx
0x14000780c  jz      loc_1400078AB
0x140007812  cmp     dword ptr [rdx], 0
0x140007815  jnz     short loc_140007828
0x140007817  mov     eax, 1
0x14000781c  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140007824  inc     eax
0x140007826  mov     [rdx], eax
0x140007828  cmp     dword ptr [rbx+50h], 0
0x14000782c  jnz     short loc_14000783F
0x14000782e  movups  xmm0, xmmword ptr [rdx]
0x140007831  movups  xmmword ptr [rbx+50h], xmm0
0x140007835  movsd   xmm1, qword ptr [rdx+10h]
0x14000783a  movsd   qword ptr [rbx+60h], xmm1
0x14000783f  movups  xmm0, xmmword ptr [rdx]
0x140007842  lea     r10, [rdi+rbp]
0x140007846  movups  xmmword ptr [rbx+68h], xmm0
0x14000784a  movsd   xmm1, qword ptr [rdx+10h]
0x14000784f  movsd   qword ptr [rbx+78h], xmm1
0x140007854  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140007858  mov     rax, rbx
0x14000785b  inc     rax
0x14000785e  cmp     byte ptr [rdi+rax], 0
0x140007862  jnz     short loc_14000785B
0x140007864  lea     rcx, [rax+rdi]
0x140007868  mov     rax, r10
0x14000786b  sub     rax, rcx
0x14000786e  cmp     rax, 2
0x140007872  jle     short loc_1400078A9
0x140007874  mov     byte ptr [rcx], 5Ch ; '\'
0x140007877  lea     rdi, [rcx+1]
0x14000787b  mov     r8, [rdx+8]; Source
0x14000787f  inc     rbx
0x140007882  cmp     byte ptr [r8+rbx], 0
0x140007887  jnz     short loc_14000787F
0x140007889  sub     r10, rdi
0x14000788c  inc     rbx
0x14000788f  cmp     rbx, r10
0x140007892  mov     rdx, r10; DestinationSize
0x140007895  mov     rcx, rdi; Destination
0x140007898  cmovnb  rbx, r10
0x14000789c  mov     r9, rbx; SourceSize
0x14000789f  call    memcpy_s
0x1400078a4  mov     byte ptr [rbx+rdi-1], 0
0x1400078a9  mov     al, 1
0x1400078ab  add     rsp, 28h
0x1400078af  pop     rdi
0x1400078b0  pop     rsi
0x1400078b1  pop     rbp
0x1400078b2  pop     rbx
0x1400078b3  retn
```
