# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180009e28`
- end: `0x180009f05`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180009624`
- `0x180009e28`

## callees

- `0x180009e28`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180009eef`
- `msvcrt!memcpy_s` at `0x180009eef`

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
0x180009e28  push    rbx
0x180009e2a  push    rbp
0x180009e2b  push    rsi
0x180009e2c  push    rdi
0x180009e2d  sub     rsp, 28h
0x180009e31  xor     al, al
0x180009e33  mov     byte ptr [r8], 0
0x180009e37  mov     rbp, r9
0x180009e3a  mov     rdi, r8
0x180009e3d  mov     rsi, rdx
0x180009e40  mov     rbx, rcx
0x180009e43  test    rdx, rdx
0x180009e46  jz      loc_180009EFC
0x180009e4c  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180009e50  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180009e55  mov     rdx, [rsi+20h]
0x180009e59  test    rdx, rdx
0x180009e5c  jz      loc_180009EFC
0x180009e62  cmp     dword ptr [rdx], 0
0x180009e65  jnz     short loc_180009E78
0x180009e67  mov     eax, 1
0x180009e6c  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180009e74  inc     eax
0x180009e76  mov     [rdx], eax
0x180009e78  cmp     dword ptr [rbx+50h], 0
0x180009e7c  jnz     short loc_180009E8F
0x180009e7e  movups  xmm0, xmmword ptr [rdx]
0x180009e81  movups  xmmword ptr [rbx+50h], xmm0
0x180009e85  movsd   xmm1, qword ptr [rdx+10h]
0x180009e8a  movsd   qword ptr [rbx+60h], xmm1
0x180009e8f  movups  xmm0, xmmword ptr [rdx]
0x180009e92  lea     r10, [rdi+rbp]
0x180009e96  movups  xmmword ptr [rbx+68h], xmm0
0x180009e9a  movsd   xmm1, qword ptr [rdx+10h]
0x180009e9f  movsd   qword ptr [rbx+78h], xmm1
0x180009ea4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180009ea8  mov     rax, rbx
0x180009eab  inc     rax
0x180009eae  cmp     byte ptr [rdi+rax], 0
0x180009eb2  jnz     short loc_180009EAB
0x180009eb4  lea     rcx, [rax+rdi]
0x180009eb8  mov     rax, r10
0x180009ebb  sub     rax, rcx
0x180009ebe  cmp     rax, 2
0x180009ec2  jle     short loc_180009EFA
0x180009ec4  mov     byte ptr [rcx], 5Ch ; '\'
0x180009ec7  lea     rdi, [rcx+1]
0x180009ecb  mov     r8, [rdx+8]; Source
0x180009ecf  inc     rbx
0x180009ed2  cmp     byte ptr [r8+rbx], 0
0x180009ed7  jnz     short loc_180009ECF
0x180009ed9  sub     r10, rdi
0x180009edc  inc     rbx
0x180009edf  cmp     rbx, r10
0x180009ee2  mov     rdx, r10; DestinationSize
0x180009ee5  mov     rcx, rdi; Destination
0x180009ee8  cmovnb  rbx, r10
0x180009eec  mov     r9, rbx; SourceSize
0x180009eef  call    cs:__imp_memcpy_s
0x180009ef5  mov     byte ptr [rbx+rdi-1], 0
0x180009efa  mov     al, 1
0x180009efc  add     rsp, 28h
0x180009f00  pop     rdi
0x180009f01  pop     rsi
0x180009f02  pop     rbp
0x180009f03  pop     rbx
0x180009f04  retn
```
