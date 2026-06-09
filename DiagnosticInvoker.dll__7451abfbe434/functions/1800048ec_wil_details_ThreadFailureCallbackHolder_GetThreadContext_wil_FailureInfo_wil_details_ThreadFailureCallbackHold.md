# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x1800048ec`
- end: `0x1800049c8`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800041f0`
- `0x1800048ec`

## callees

- `0x1800048ec`
- `0x1800065b8`

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
0x1800048ec  push    rbx
0x1800048ee  push    rbp
0x1800048ef  push    rsi
0x1800048f0  push    rdi
0x1800048f1  sub     rsp, 28h
0x1800048f5  xor     al, al
0x1800048f7  mov     byte ptr [r8], 0
0x1800048fb  mov     rbp, r9
0x1800048fe  mov     rdi, r8
0x180004901  mov     rsi, rdx
0x180004904  mov     rbx, rcx
0x180004907  test    rdx, rdx
0x18000490a  jz      loc_1800049BF
0x180004910  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180004914  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004919  mov     rdx, [rsi+20h]
0x18000491d  test    rdx, rdx
0x180004920  jz      loc_1800049BF
0x180004926  cmp     dword ptr [rdx], 0
0x180004929  jnz     short loc_18000493C
0x18000492b  mov     eax, 1
0x180004930  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180004938  inc     eax
0x18000493a  mov     [rdx], eax
0x18000493c  cmp     dword ptr [rbx+50h], 0
0x180004940  jnz     short loc_180004953
0x180004942  movups  xmm0, xmmword ptr [rdx]
0x180004945  movups  xmmword ptr [rbx+50h], xmm0
0x180004949  movsd   xmm1, qword ptr [rdx+10h]
0x18000494e  movsd   qword ptr [rbx+60h], xmm1
0x180004953  movups  xmm0, xmmword ptr [rdx]
0x180004956  lea     r10, [rdi+rbp]
0x18000495a  movups  xmmword ptr [rbx+68h], xmm0
0x18000495e  movsd   xmm1, qword ptr [rdx+10h]
0x180004963  movsd   qword ptr [rbx+78h], xmm1
0x180004968  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000496c  mov     rax, rbx
0x18000496f  inc     rax
0x180004972  cmp     byte ptr [rdi+rax], 0
0x180004976  jnz     short loc_18000496F
0x180004978  lea     rcx, [rax+rdi]
0x18000497c  mov     rax, r10
0x18000497f  sub     rax, rcx
0x180004982  cmp     rax, 2
0x180004986  jle     short loc_1800049BD
0x180004988  mov     byte ptr [rcx], 5Ch ; '\'
0x18000498b  lea     rdi, [rcx+1]
0x18000498f  mov     r8, [rdx+8]; Source
0x180004993  inc     rbx
0x180004996  cmp     byte ptr [r8+rbx], 0
0x18000499b  jnz     short loc_180004993
0x18000499d  sub     r10, rdi
0x1800049a0  inc     rbx
0x1800049a3  cmp     rbx, r10
0x1800049a6  mov     rdx, r10; DestinationSize
0x1800049a9  mov     rcx, rdi; Destination
0x1800049ac  cmovnb  rbx, r10
0x1800049b0  mov     r9, rbx; SourceSize
0x1800049b3  call    memcpy_s
0x1800049b8  mov     byte ptr [rbx+rdi-1], 0
0x1800049bd  mov     al, 1
0x1800049bf  add     rsp, 28h
0x1800049c3  pop     rdi
0x1800049c4  pop     rsi
0x1800049c5  pop     rbp
0x1800049c6  pop     rbx
0x1800049c7  retn
```
