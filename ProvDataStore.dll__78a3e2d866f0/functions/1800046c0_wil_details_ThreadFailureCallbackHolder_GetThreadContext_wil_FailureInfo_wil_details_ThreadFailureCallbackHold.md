# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x1800046c0`
- end: `0x18000479d`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004030`
- `0x1800046c0`

## callees

- `0x1800046c0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180004787`
- `msvcrt!memcpy_s` at `0x180004787`

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
0x1800046c0  push    rbx
0x1800046c2  push    rbp
0x1800046c3  push    rsi
0x1800046c4  push    rdi
0x1800046c5  sub     rsp, 28h
0x1800046c9  xor     al, al
0x1800046cb  mov     byte ptr [r8], 0
0x1800046cf  mov     rbp, r9
0x1800046d2  mov     rdi, r8
0x1800046d5  mov     rsi, rdx
0x1800046d8  mov     rbx, rcx
0x1800046db  test    rdx, rdx
0x1800046de  jz      loc_180004794
0x1800046e4  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x1800046e8  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800046ed  mov     rdx, [rsi+20h]
0x1800046f1  test    rdx, rdx
0x1800046f4  jz      loc_180004794
0x1800046fa  cmp     dword ptr [rdx], 0
0x1800046fd  jnz     short loc_180004710
0x1800046ff  mov     eax, 1
0x180004704  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000470c  inc     eax
0x18000470e  mov     [rdx], eax
0x180004710  cmp     dword ptr [rbx+50h], 0
0x180004714  jnz     short loc_180004727
0x180004716  movups  xmm0, xmmword ptr [rdx]
0x180004719  movups  xmmword ptr [rbx+50h], xmm0
0x18000471d  movsd   xmm1, qword ptr [rdx+10h]
0x180004722  movsd   qword ptr [rbx+60h], xmm1
0x180004727  movups  xmm0, xmmword ptr [rdx]
0x18000472a  lea     r10, [rdi+rbp]
0x18000472e  movups  xmmword ptr [rbx+68h], xmm0
0x180004732  movsd   xmm1, qword ptr [rdx+10h]
0x180004737  movsd   qword ptr [rbx+78h], xmm1
0x18000473c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004740  mov     rax, rbx
0x180004743  inc     rax
0x180004746  cmp     byte ptr [rdi+rax], 0
0x18000474a  jnz     short loc_180004743
0x18000474c  lea     rcx, [rax+rdi]
0x180004750  mov     rax, r10
0x180004753  sub     rax, rcx
0x180004756  cmp     rax, 2
0x18000475a  jle     short loc_180004792
0x18000475c  mov     byte ptr [rcx], 5Ch ; '\'
0x18000475f  lea     rdi, [rcx+1]
0x180004763  mov     r8, [rdx+8]; Source
0x180004767  inc     rbx
0x18000476a  cmp     byte ptr [r8+rbx], 0
0x18000476f  jnz     short loc_180004767
0x180004771  sub     r10, rdi
0x180004774  inc     rbx
0x180004777  cmp     rbx, r10
0x18000477a  mov     rdx, r10; DestinationSize
0x18000477d  mov     rcx, rdi; Destination
0x180004780  cmovnb  rbx, r10
0x180004784  mov     r9, rbx; SourceSize
0x180004787  call    cs:__imp_memcpy_s
0x18000478d  mov     byte ptr [rbx+rdi-1], 0
0x180004792  mov     al, 1
0x180004794  add     rsp, 28h
0x180004798  pop     rdi
0x180004799  pop     rsi
0x18000479a  pop     rbp
0x18000479b  pop     rbx
0x18000479c  retn
```
