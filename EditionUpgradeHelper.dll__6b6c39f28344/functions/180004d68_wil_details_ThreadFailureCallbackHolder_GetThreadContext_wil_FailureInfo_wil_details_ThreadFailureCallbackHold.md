# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180004d68`
- end: `0x180004e44`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004670`
- `0x180004d68`

## callees

- `0x180004d68`
- `0x180007ed4`

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
0x180004d68  push    rbx
0x180004d6a  push    rbp
0x180004d6b  push    rsi
0x180004d6c  push    rdi
0x180004d6d  sub     rsp, 28h
0x180004d71  xor     al, al
0x180004d73  mov     byte ptr [r8], 0
0x180004d77  mov     rbp, r9
0x180004d7a  mov     rdi, r8
0x180004d7d  mov     rsi, rdx
0x180004d80  mov     rbx, rcx
0x180004d83  test    rdx, rdx
0x180004d86  jz      loc_180004E3B
0x180004d8c  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180004d90  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004d95  mov     rdx, [rsi+20h]
0x180004d99  test    rdx, rdx
0x180004d9c  jz      loc_180004E3B
0x180004da2  cmp     dword ptr [rdx], 0
0x180004da5  jnz     short loc_180004DB8
0x180004da7  mov     eax, 1
0x180004dac  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180004db4  inc     eax
0x180004db6  mov     [rdx], eax
0x180004db8  cmp     dword ptr [rbx+50h], 0
0x180004dbc  jnz     short loc_180004DCF
0x180004dbe  movups  xmm0, xmmword ptr [rdx]
0x180004dc1  movups  xmmword ptr [rbx+50h], xmm0
0x180004dc5  movsd   xmm1, qword ptr [rdx+10h]
0x180004dca  movsd   qword ptr [rbx+60h], xmm1
0x180004dcf  movups  xmm0, xmmword ptr [rdx]
0x180004dd2  lea     r10, [rdi+rbp]
0x180004dd6  movups  xmmword ptr [rbx+68h], xmm0
0x180004dda  movsd   xmm1, qword ptr [rdx+10h]
0x180004ddf  movsd   qword ptr [rbx+78h], xmm1
0x180004de4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004de8  mov     rax, rbx
0x180004deb  inc     rax
0x180004dee  cmp     byte ptr [rdi+rax], 0
0x180004df2  jnz     short loc_180004DEB
0x180004df4  lea     rcx, [rax+rdi]
0x180004df8  mov     rax, r10
0x180004dfb  sub     rax, rcx
0x180004dfe  cmp     rax, 2
0x180004e02  jle     short loc_180004E39
0x180004e04  mov     byte ptr [rcx], 5Ch ; '\'
0x180004e07  lea     rdi, [rcx+1]
0x180004e0b  mov     r8, [rdx+8]; Source
0x180004e0f  inc     rbx
0x180004e12  cmp     byte ptr [r8+rbx], 0
0x180004e17  jnz     short loc_180004E0F
0x180004e19  sub     r10, rdi
0x180004e1c  inc     rbx
0x180004e1f  cmp     rbx, r10
0x180004e22  mov     rdx, r10; DestinationSize
0x180004e25  mov     rcx, rdi; Destination
0x180004e28  cmovnb  rbx, r10
0x180004e2c  mov     r9, rbx; SourceSize
0x180004e2f  call    memcpy_s
0x180004e34  mov     byte ptr [rbx+rdi-1], 0
0x180004e39  mov     al, 1
0x180004e3b  add     rsp, 28h
0x180004e3f  pop     rdi
0x180004e40  pop     rsi
0x180004e41  pop     rbp
0x180004e42  pop     rbx
0x180004e43  retn
```
