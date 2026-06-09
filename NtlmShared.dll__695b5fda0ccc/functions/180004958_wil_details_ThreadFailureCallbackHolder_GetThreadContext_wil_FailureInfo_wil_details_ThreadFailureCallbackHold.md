# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180004958`
- end: `0x180004a35`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004260`
- `0x180004958`

## callees

- `0x180004958`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x180004a1f`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x180004a1f`

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
0x180004958  push    rbx
0x18000495a  push    rbp
0x18000495b  push    rsi
0x18000495c  push    rdi
0x18000495d  sub     rsp, 28h
0x180004961  xor     al, al
0x180004963  mov     byte ptr [r8], 0
0x180004967  mov     rbp, r9
0x18000496a  mov     rdi, r8
0x18000496d  mov     rsi, rdx
0x180004970  mov     rbx, rcx
0x180004973  test    rdx, rdx
0x180004976  jz      loc_180004A2C
0x18000497c  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180004980  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004985  mov     rdx, [rsi+20h]
0x180004989  test    rdx, rdx
0x18000498c  jz      loc_180004A2C
0x180004992  cmp     dword ptr [rdx], 0
0x180004995  jnz     short loc_1800049A8
0x180004997  mov     eax, 1
0x18000499c  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x1800049a4  inc     eax
0x1800049a6  mov     [rdx], eax
0x1800049a8  cmp     dword ptr [rbx+50h], 0
0x1800049ac  jnz     short loc_1800049BF
0x1800049ae  movups  xmm0, xmmword ptr [rdx]
0x1800049b1  movups  xmmword ptr [rbx+50h], xmm0
0x1800049b5  movsd   xmm1, qword ptr [rdx+10h]
0x1800049ba  movsd   qword ptr [rbx+60h], xmm1
0x1800049bf  movups  xmm0, xmmword ptr [rdx]
0x1800049c2  lea     r10, [rdi+rbp]
0x1800049c6  movups  xmmword ptr [rbx+68h], xmm0
0x1800049ca  movsd   xmm1, qword ptr [rdx+10h]
0x1800049cf  movsd   qword ptr [rbx+78h], xmm1
0x1800049d4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800049d8  mov     rax, rbx
0x1800049db  inc     rax
0x1800049de  cmp     byte ptr [rdi+rax], 0
0x1800049e2  jnz     short loc_1800049DB
0x1800049e4  lea     rcx, [rax+rdi]
0x1800049e8  mov     rax, r10
0x1800049eb  sub     rax, rcx
0x1800049ee  cmp     rax, 2
0x1800049f2  jle     short loc_180004A2A
0x1800049f4  mov     byte ptr [rcx], 5Ch ; '\'
0x1800049f7  lea     rdi, [rcx+1]
0x1800049fb  mov     r8, [rdx+8]; Source
0x1800049ff  inc     rbx
0x180004a02  cmp     byte ptr [r8+rbx], 0
0x180004a07  jnz     short loc_1800049FF
0x180004a09  sub     r10, rdi
0x180004a0c  inc     rbx
0x180004a0f  cmp     rbx, r10
0x180004a12  mov     rdx, r10; DestinationSize
0x180004a15  mov     rcx, rdi; Destination
0x180004a18  cmovnb  rbx, r10
0x180004a1c  mov     r9, rbx; SourceSize
0x180004a1f  call    cs:__imp_memcpy_s
0x180004a25  mov     byte ptr [rbx+rdi-1], 0
0x180004a2a  mov     al, 1
0x180004a2c  add     rsp, 28h
0x180004a30  pop     rdi
0x180004a31  pop     rsi
0x180004a32  pop     rbp
0x180004a33  pop     rbx
0x180004a34  retn
```
