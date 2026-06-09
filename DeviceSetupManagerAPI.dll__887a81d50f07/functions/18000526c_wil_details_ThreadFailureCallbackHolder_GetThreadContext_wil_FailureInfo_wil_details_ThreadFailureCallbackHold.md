# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000526c`
- end: `0x180005348`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004b70`
- `0x18000526c`

## callees

- `0x18000526c`
- `0x180008bc8`

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
0x18000526c  push    rbx
0x18000526e  push    rbp
0x18000526f  push    rsi
0x180005270  push    rdi
0x180005271  sub     rsp, 28h
0x180005275  xor     al, al
0x180005277  mov     byte ptr [r8], 0
0x18000527b  mov     rbp, r9
0x18000527e  mov     rdi, r8
0x180005281  mov     rsi, rdx
0x180005284  mov     rbx, rcx
0x180005287  test    rdx, rdx
0x18000528a  jz      loc_18000533F
0x180005290  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180005294  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005299  mov     rdx, [rsi+20h]
0x18000529d  test    rdx, rdx
0x1800052a0  jz      loc_18000533F
0x1800052a6  cmp     dword ptr [rdx], 0
0x1800052a9  jnz     short loc_1800052BC
0x1800052ab  mov     eax, 1
0x1800052b0  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x1800052b8  inc     eax
0x1800052ba  mov     [rdx], eax
0x1800052bc  cmp     dword ptr [rbx+50h], 0
0x1800052c0  jnz     short loc_1800052D3
0x1800052c2  movups  xmm0, xmmword ptr [rdx]
0x1800052c5  movups  xmmword ptr [rbx+50h], xmm0
0x1800052c9  movsd   xmm1, qword ptr [rdx+10h]
0x1800052ce  movsd   qword ptr [rbx+60h], xmm1
0x1800052d3  movups  xmm0, xmmword ptr [rdx]
0x1800052d6  lea     r10, [rdi+rbp]
0x1800052da  movups  xmmword ptr [rbx+68h], xmm0
0x1800052de  movsd   xmm1, qword ptr [rdx+10h]
0x1800052e3  movsd   qword ptr [rbx+78h], xmm1
0x1800052e8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800052ec  mov     rax, rbx
0x1800052ef  inc     rax
0x1800052f2  cmp     byte ptr [rdi+rax], 0
0x1800052f6  jnz     short loc_1800052EF
0x1800052f8  lea     rcx, [rax+rdi]
0x1800052fc  mov     rax, r10
0x1800052ff  sub     rax, rcx
0x180005302  cmp     rax, 2
0x180005306  jle     short loc_18000533D
0x180005308  mov     byte ptr [rcx], 5Ch ; '\'
0x18000530b  lea     rdi, [rcx+1]
0x18000530f  mov     r8, [rdx+8]; Source
0x180005313  inc     rbx
0x180005316  cmp     byte ptr [r8+rbx], 0
0x18000531b  jnz     short loc_180005313
0x18000531d  sub     r10, rdi
0x180005320  inc     rbx
0x180005323  cmp     rbx, r10
0x180005326  mov     rdx, r10; DestinationSize
0x180005329  mov     rcx, rdi; Destination
0x18000532c  cmovnb  rbx, r10
0x180005330  mov     r9, rbx; SourceSize
0x180005333  call    memcpy_s
0x180005338  mov     byte ptr [rbx+rdi-1], 0
0x18000533d  mov     al, 1
0x18000533f  add     rsp, 28h
0x180005343  pop     rdi
0x180005344  pop     rsi
0x180005345  pop     rbp
0x180005346  pop     rbx
0x180005347  retn
```
