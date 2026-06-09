# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180004d1c`
- end: `0x180004df8`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004620`
- `0x180004d1c`

## callees

- `0x180004d1c`
- `0x180006fa4`

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
0x180004d1c  push    rbx
0x180004d1e  push    rbp
0x180004d1f  push    rsi
0x180004d20  push    rdi
0x180004d21  sub     rsp, 28h
0x180004d25  xor     al, al
0x180004d27  mov     byte ptr [r8], 0
0x180004d2b  mov     rbp, r9
0x180004d2e  mov     rdi, r8
0x180004d31  mov     rsi, rdx
0x180004d34  mov     rbx, rcx
0x180004d37  test    rdx, rdx
0x180004d3a  jz      loc_180004DEF
0x180004d40  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180004d44  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004d49  mov     rdx, [rsi+20h]
0x180004d4d  test    rdx, rdx
0x180004d50  jz      loc_180004DEF
0x180004d56  cmp     dword ptr [rdx], 0
0x180004d59  jnz     short loc_180004D6C
0x180004d5b  mov     eax, 1
0x180004d60  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180004d68  inc     eax
0x180004d6a  mov     [rdx], eax
0x180004d6c  cmp     dword ptr [rbx+50h], 0
0x180004d70  jnz     short loc_180004D83
0x180004d72  movups  xmm0, xmmword ptr [rdx]
0x180004d75  movups  xmmword ptr [rbx+50h], xmm0
0x180004d79  movsd   xmm1, qword ptr [rdx+10h]
0x180004d7e  movsd   qword ptr [rbx+60h], xmm1
0x180004d83  movups  xmm0, xmmword ptr [rdx]
0x180004d86  lea     r10, [rdi+rbp]
0x180004d8a  movups  xmmword ptr [rbx+68h], xmm0
0x180004d8e  movsd   xmm1, qword ptr [rdx+10h]
0x180004d93  movsd   qword ptr [rbx+78h], xmm1
0x180004d98  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004d9c  mov     rax, rbx
0x180004d9f  inc     rax
0x180004da2  cmp     byte ptr [rdi+rax], 0
0x180004da6  jnz     short loc_180004D9F
0x180004da8  lea     rcx, [rax+rdi]
0x180004dac  mov     rax, r10
0x180004daf  sub     rax, rcx
0x180004db2  cmp     rax, 2
0x180004db6  jle     short loc_180004DED
0x180004db8  mov     byte ptr [rcx], 5Ch ; '\'
0x180004dbb  lea     rdi, [rcx+1]
0x180004dbf  mov     r8, [rdx+8]; Source
0x180004dc3  inc     rbx
0x180004dc6  cmp     byte ptr [r8+rbx], 0
0x180004dcb  jnz     short loc_180004DC3
0x180004dcd  sub     r10, rdi
0x180004dd0  inc     rbx
0x180004dd3  cmp     rbx, r10
0x180004dd6  mov     rdx, r10; DestinationSize
0x180004dd9  mov     rcx, rdi; Destination
0x180004ddc  cmovnb  rbx, r10
0x180004de0  mov     r9, rbx; SourceSize
0x180004de3  call    memcpy_s
0x180004de8  mov     byte ptr [rbx+rdi-1], 0
0x180004ded  mov     al, 1
0x180004def  add     rsp, 28h
0x180004df3  pop     rdi
0x180004df4  pop     rsi
0x180004df5  pop     rbp
0x180004df6  pop     rbx
0x180004df7  retn
```
