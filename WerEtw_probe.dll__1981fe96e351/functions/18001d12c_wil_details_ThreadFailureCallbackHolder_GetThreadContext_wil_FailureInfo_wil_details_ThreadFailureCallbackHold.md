# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18001d12c`
- end: `0x18001d208`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001ca30`
- `0x18001d12c`

## callees

- `0x18001d12c`
- `0x180020210`

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
0x18001d12c  push    rbx
0x18001d12e  push    rbp
0x18001d12f  push    rsi
0x18001d130  push    rdi
0x18001d131  sub     rsp, 28h
0x18001d135  xor     al, al
0x18001d137  mov     byte ptr [r8], 0
0x18001d13b  mov     rbp, r9
0x18001d13e  mov     rdi, r8
0x18001d141  mov     rsi, rdx
0x18001d144  mov     rbx, rcx
0x18001d147  test    rdx, rdx
0x18001d14a  jz      loc_18001D1FF
0x18001d150  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18001d154  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18001d159  mov     rdx, [rsi+20h]
0x18001d15d  test    rdx, rdx
0x18001d160  jz      loc_18001D1FF
0x18001d166  cmp     dword ptr [rdx], 0
0x18001d169  jnz     short loc_18001D17C
0x18001d16b  mov     eax, 1
0x18001d170  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18001d178  inc     eax
0x18001d17a  mov     [rdx], eax
0x18001d17c  cmp     dword ptr [rbx+50h], 0
0x18001d180  jnz     short loc_18001D193
0x18001d182  movups  xmm0, xmmword ptr [rdx]
0x18001d185  movups  xmmword ptr [rbx+50h], xmm0
0x18001d189  movsd   xmm1, qword ptr [rdx+10h]
0x18001d18e  movsd   qword ptr [rbx+60h], xmm1
0x18001d193  movups  xmm0, xmmword ptr [rdx]
0x18001d196  lea     r10, [rdi+rbp]
0x18001d19a  movups  xmmword ptr [rbx+68h], xmm0
0x18001d19e  movsd   xmm1, qword ptr [rdx+10h]
0x18001d1a3  movsd   qword ptr [rbx+78h], xmm1
0x18001d1a8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001d1ac  mov     rax, rbx
0x18001d1af  inc     rax
0x18001d1b2  cmp     byte ptr [rdi+rax], 0
0x18001d1b6  jnz     short loc_18001D1AF
0x18001d1b8  lea     rcx, [rax+rdi]
0x18001d1bc  mov     rax, r10
0x18001d1bf  sub     rax, rcx
0x18001d1c2  cmp     rax, 2
0x18001d1c6  jle     short loc_18001D1FD
0x18001d1c8  mov     byte ptr [rcx], 5Ch ; '\'
0x18001d1cb  lea     rdi, [rcx+1]
0x18001d1cf  mov     r8, [rdx+8]; Source
0x18001d1d3  inc     rbx
0x18001d1d6  cmp     byte ptr [r8+rbx], 0
0x18001d1db  jnz     short loc_18001D1D3
0x18001d1dd  sub     r10, rdi
0x18001d1e0  inc     rbx
0x18001d1e3  cmp     rbx, r10
0x18001d1e6  mov     rdx, r10; DestinationSize
0x18001d1e9  mov     rcx, rdi; Destination
0x18001d1ec  cmovnb  rbx, r10
0x18001d1f0  mov     r9, rbx; SourceSize
0x18001d1f3  call    memcpy_s
0x18001d1f8  mov     byte ptr [rbx+rdi-1], 0
0x18001d1fd  mov     al, 1
0x18001d1ff  add     rsp, 28h
0x18001d203  pop     rdi
0x18001d204  pop     rsi
0x18001d205  pop     rbp
0x18001d206  pop     rbx
0x18001d207  retn
```
