# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180004510`
- end: `0x1800045ec`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003e20`
- `0x180004510`

## callees

- `0x180004510`
- `0x1800062e8`

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
0x180004510  push    rbx
0x180004512  push    rbp
0x180004513  push    rsi
0x180004514  push    rdi
0x180004515  sub     rsp, 28h
0x180004519  xor     al, al
0x18000451b  mov     byte ptr [r8], 0
0x18000451f  mov     rbp, r9
0x180004522  mov     rdi, r8
0x180004525  mov     rsi, rdx
0x180004528  mov     rbx, rcx
0x18000452b  test    rdx, rdx
0x18000452e  jz      loc_1800045E3
0x180004534  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180004538  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000453d  mov     rdx, [rsi+20h]
0x180004541  test    rdx, rdx
0x180004544  jz      loc_1800045E3
0x18000454a  cmp     dword ptr [rdx], 0
0x18000454d  jnz     short loc_180004560
0x18000454f  mov     eax, 1
0x180004554  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000455c  inc     eax
0x18000455e  mov     [rdx], eax
0x180004560  cmp     dword ptr [rbx+50h], 0
0x180004564  jnz     short loc_180004577
0x180004566  movups  xmm0, xmmword ptr [rdx]
0x180004569  movups  xmmword ptr [rbx+50h], xmm0
0x18000456d  movsd   xmm1, qword ptr [rdx+10h]
0x180004572  movsd   qword ptr [rbx+60h], xmm1
0x180004577  movups  xmm0, xmmword ptr [rdx]
0x18000457a  lea     r10, [rdi+rbp]
0x18000457e  movups  xmmword ptr [rbx+68h], xmm0
0x180004582  movsd   xmm1, qword ptr [rdx+10h]
0x180004587  movsd   qword ptr [rbx+78h], xmm1
0x18000458c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004590  mov     rax, rbx
0x180004593  inc     rax
0x180004596  cmp     byte ptr [rdi+rax], 0
0x18000459a  jnz     short loc_180004593
0x18000459c  lea     rcx, [rax+rdi]
0x1800045a0  mov     rax, r10
0x1800045a3  sub     rax, rcx
0x1800045a6  cmp     rax, 2
0x1800045aa  jle     short loc_1800045E1
0x1800045ac  mov     byte ptr [rcx], 5Ch ; '\'
0x1800045af  lea     rdi, [rcx+1]
0x1800045b3  mov     r8, [rdx+8]; Source
0x1800045b7  inc     rbx
0x1800045ba  cmp     byte ptr [r8+rbx], 0
0x1800045bf  jnz     short loc_1800045B7
0x1800045c1  sub     r10, rdi
0x1800045c4  inc     rbx
0x1800045c7  cmp     rbx, r10
0x1800045ca  mov     rdx, r10; DestinationSize
0x1800045cd  mov     rcx, rdi; Destination
0x1800045d0  cmovnb  rbx, r10
0x1800045d4  mov     r9, rbx; SourceSize
0x1800045d7  call    memcpy_s
0x1800045dc  mov     byte ptr [rbx+rdi-1], 0
0x1800045e1  mov     al, 1
0x1800045e3  add     rsp, 28h
0x1800045e7  pop     rdi
0x1800045e8  pop     rsi
0x1800045e9  pop     rbp
0x1800045ea  pop     rbx
0x1800045eb  retn
```
