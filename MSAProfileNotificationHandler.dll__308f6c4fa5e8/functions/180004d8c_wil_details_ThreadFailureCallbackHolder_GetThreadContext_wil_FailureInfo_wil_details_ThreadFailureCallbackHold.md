# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180004d8c`
- end: `0x180004e68`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004690`
- `0x180004d8c`

## callees

- `0x1800028cc`
- `0x180004d8c`

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
0x180004d8c  push    rbx
0x180004d8e  push    rbp
0x180004d8f  push    rsi
0x180004d90  push    rdi
0x180004d91  sub     rsp, 28h
0x180004d95  xor     al, al
0x180004d97  mov     byte ptr [r8], 0
0x180004d9b  mov     rbp, r9
0x180004d9e  mov     rdi, r8
0x180004da1  mov     rsi, rdx
0x180004da4  mov     rbx, rcx
0x180004da7  test    rdx, rdx
0x180004daa  jz      loc_180004E5F
0x180004db0  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180004db4  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004db9  mov     rdx, [rsi+20h]
0x180004dbd  test    rdx, rdx
0x180004dc0  jz      loc_180004E5F
0x180004dc6  cmp     dword ptr [rdx], 0
0x180004dc9  jnz     short loc_180004DDC
0x180004dcb  mov     eax, 1
0x180004dd0  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180004dd8  inc     eax
0x180004dda  mov     [rdx], eax
0x180004ddc  cmp     dword ptr [rbx+50h], 0
0x180004de0  jnz     short loc_180004DF3
0x180004de2  movups  xmm0, xmmword ptr [rdx]
0x180004de5  movups  xmmword ptr [rbx+50h], xmm0
0x180004de9  movsd   xmm1, qword ptr [rdx+10h]
0x180004dee  movsd   qword ptr [rbx+60h], xmm1
0x180004df3  movups  xmm0, xmmword ptr [rdx]
0x180004df6  lea     r10, [rdi+rbp]
0x180004dfa  movups  xmmword ptr [rbx+68h], xmm0
0x180004dfe  movsd   xmm1, qword ptr [rdx+10h]
0x180004e03  movsd   qword ptr [rbx+78h], xmm1
0x180004e08  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004e0c  mov     rax, rbx
0x180004e0f  inc     rax
0x180004e12  cmp     byte ptr [rdi+rax], 0
0x180004e16  jnz     short loc_180004E0F
0x180004e18  lea     rcx, [rax+rdi]
0x180004e1c  mov     rax, r10
0x180004e1f  sub     rax, rcx
0x180004e22  cmp     rax, 2
0x180004e26  jle     short loc_180004E5D
0x180004e28  mov     byte ptr [rcx], 5Ch ; '\'
0x180004e2b  lea     rdi, [rcx+1]
0x180004e2f  mov     r8, [rdx+8]; Source
0x180004e33  inc     rbx
0x180004e36  cmp     byte ptr [r8+rbx], 0
0x180004e3b  jnz     short loc_180004E33
0x180004e3d  sub     r10, rdi
0x180004e40  inc     rbx
0x180004e43  cmp     rbx, r10
0x180004e46  mov     rdx, r10; DestinationSize
0x180004e49  mov     rcx, rdi; Destination
0x180004e4c  cmovnb  rbx, r10
0x180004e50  mov     r9, rbx; SourceSize
0x180004e53  call    memcpy_s
0x180004e58  mov     byte ptr [rbx+rdi-1], 0
0x180004e5d  mov     al, 1
0x180004e5f  add     rsp, 28h
0x180004e63  pop     rdi
0x180004e64  pop     rsi
0x180004e65  pop     rbp
0x180004e66  pop     rbx
0x180004e67  retn
```
