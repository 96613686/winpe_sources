# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x1800044cc`
- end: `0x1800045a9`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003df0`
- `0x1800044cc`

## callees

- `0x1800044cc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180004593`
- `msvcrt!memcpy_s` at `0x180004593`

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
0x1800044cc  push    rbx
0x1800044ce  push    rbp
0x1800044cf  push    rsi
0x1800044d0  push    rdi
0x1800044d1  sub     rsp, 28h
0x1800044d5  xor     al, al
0x1800044d7  mov     byte ptr [r8], 0
0x1800044db  mov     rbp, r9
0x1800044de  mov     rdi, r8
0x1800044e1  mov     rsi, rdx
0x1800044e4  mov     rbx, rcx
0x1800044e7  test    rdx, rdx
0x1800044ea  jz      loc_1800045A0
0x1800044f0  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x1800044f4  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800044f9  mov     rdx, [rsi+20h]
0x1800044fd  test    rdx, rdx
0x180004500  jz      loc_1800045A0
0x180004506  cmp     dword ptr [rdx], 0
0x180004509  jnz     short loc_18000451C
0x18000450b  mov     eax, 1
0x180004510  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180004518  inc     eax
0x18000451a  mov     [rdx], eax
0x18000451c  cmp     dword ptr [rbx+50h], 0
0x180004520  jnz     short loc_180004533
0x180004522  movups  xmm0, xmmword ptr [rdx]
0x180004525  movups  xmmword ptr [rbx+50h], xmm0
0x180004529  movsd   xmm1, qword ptr [rdx+10h]
0x18000452e  movsd   qword ptr [rbx+60h], xmm1
0x180004533  movups  xmm0, xmmword ptr [rdx]
0x180004536  lea     r10, [rdi+rbp]
0x18000453a  movups  xmmword ptr [rbx+68h], xmm0
0x18000453e  movsd   xmm1, qword ptr [rdx+10h]
0x180004543  movsd   qword ptr [rbx+78h], xmm1
0x180004548  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000454c  mov     rax, rbx
0x18000454f  inc     rax
0x180004552  cmp     byte ptr [rdi+rax], 0
0x180004556  jnz     short loc_18000454F
0x180004558  lea     rcx, [rax+rdi]
0x18000455c  mov     rax, r10
0x18000455f  sub     rax, rcx
0x180004562  cmp     rax, 2
0x180004566  jle     short loc_18000459E
0x180004568  mov     byte ptr [rcx], 5Ch ; '\'
0x18000456b  lea     rdi, [rcx+1]
0x18000456f  mov     r8, [rdx+8]; Source
0x180004573  inc     rbx
0x180004576  cmp     byte ptr [r8+rbx], 0
0x18000457b  jnz     short loc_180004573
0x18000457d  sub     r10, rdi
0x180004580  inc     rbx
0x180004583  cmp     rbx, r10
0x180004586  mov     rdx, r10; DestinationSize
0x180004589  mov     rcx, rdi; Destination
0x18000458c  cmovnb  rbx, r10
0x180004590  mov     r9, rbx; SourceSize
0x180004593  call    cs:__imp_memcpy_s
0x180004599  mov     byte ptr [rbx+rdi-1], 0
0x18000459e  mov     al, 1
0x1800045a0  add     rsp, 28h
0x1800045a4  pop     rdi
0x1800045a5  pop     rsi
0x1800045a6  pop     rbp
0x1800045a7  pop     rbx
0x1800045a8  retn
```
