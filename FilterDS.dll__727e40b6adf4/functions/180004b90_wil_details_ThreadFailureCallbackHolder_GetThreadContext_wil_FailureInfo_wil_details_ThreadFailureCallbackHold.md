# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180004b90`
- end: `0x180004c6d`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004500`
- `0x180004b90`

## callees

- `0x180004b90`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180004c57`
- `msvcrt!memcpy_s` at `0x180004c57`

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
0x180004b90  push    rbx
0x180004b92  push    rbp
0x180004b93  push    rsi
0x180004b94  push    rdi
0x180004b95  sub     rsp, 28h
0x180004b99  xor     al, al
0x180004b9b  mov     byte ptr [r8], 0
0x180004b9f  mov     rbp, r9
0x180004ba2  mov     rdi, r8
0x180004ba5  mov     rsi, rdx
0x180004ba8  mov     rbx, rcx
0x180004bab  test    rdx, rdx
0x180004bae  jz      loc_180004C64
0x180004bb4  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180004bb8  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004bbd  mov     rdx, [rsi+20h]
0x180004bc1  test    rdx, rdx
0x180004bc4  jz      loc_180004C64
0x180004bca  cmp     dword ptr [rdx], 0
0x180004bcd  jnz     short loc_180004BE0
0x180004bcf  mov     eax, 1
0x180004bd4  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180004bdc  inc     eax
0x180004bde  mov     [rdx], eax
0x180004be0  cmp     dword ptr [rbx+50h], 0
0x180004be4  jnz     short loc_180004BF7
0x180004be6  movups  xmm0, xmmword ptr [rdx]
0x180004be9  movups  xmmword ptr [rbx+50h], xmm0
0x180004bed  movsd   xmm1, qword ptr [rdx+10h]
0x180004bf2  movsd   qword ptr [rbx+60h], xmm1
0x180004bf7  movups  xmm0, xmmword ptr [rdx]
0x180004bfa  lea     r10, [rdi+rbp]
0x180004bfe  movups  xmmword ptr [rbx+68h], xmm0
0x180004c02  movsd   xmm1, qword ptr [rdx+10h]
0x180004c07  movsd   qword ptr [rbx+78h], xmm1
0x180004c0c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004c10  mov     rax, rbx
0x180004c13  inc     rax
0x180004c16  cmp     byte ptr [rdi+rax], 0
0x180004c1a  jnz     short loc_180004C13
0x180004c1c  lea     rcx, [rax+rdi]
0x180004c20  mov     rax, r10
0x180004c23  sub     rax, rcx
0x180004c26  cmp     rax, 2
0x180004c2a  jle     short loc_180004C62
0x180004c2c  mov     byte ptr [rcx], 5Ch ; '\'
0x180004c2f  lea     rdi, [rcx+1]
0x180004c33  mov     r8, [rdx+8]; Source
0x180004c37  inc     rbx
0x180004c3a  cmp     byte ptr [r8+rbx], 0
0x180004c3f  jnz     short loc_180004C37
0x180004c41  sub     r10, rdi
0x180004c44  inc     rbx
0x180004c47  cmp     rbx, r10
0x180004c4a  mov     rdx, r10; DestinationSize
0x180004c4d  mov     rcx, rdi; Destination
0x180004c50  cmovnb  rbx, r10
0x180004c54  mov     r9, rbx; SourceSize
0x180004c57  call    cs:__imp_memcpy_s
0x180004c5d  mov     byte ptr [rbx+rdi-1], 0
0x180004c62  mov     al, 1
0x180004c64  add     rsp, 28h
0x180004c68  pop     rdi
0x180004c69  pop     rsi
0x180004c6a  pop     rbp
0x180004c6b  pop     rbx
0x180004c6c  retn
```
