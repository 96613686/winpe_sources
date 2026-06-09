# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000e758`
- end: `0x18000e835`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d890`
- `0x18000e758`

## callees

- `0x18000e758`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000e81f`
- `msvcrt!memcpy_s` at `0x18000e81f`

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
0x18000e758  push    rbx
0x18000e75a  push    rbp
0x18000e75b  push    rsi
0x18000e75c  push    rdi
0x18000e75d  sub     rsp, 28h
0x18000e761  xor     al, al
0x18000e763  mov     byte ptr [r8], 0
0x18000e767  mov     rbp, r9
0x18000e76a  mov     rdi, r8
0x18000e76d  mov     rsi, rdx
0x18000e770  mov     rbx, rcx
0x18000e773  test    rdx, rdx
0x18000e776  jz      loc_18000E82C
0x18000e77c  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18000e780  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000e785  mov     rdx, [rsi+20h]
0x18000e789  test    rdx, rdx
0x18000e78c  jz      loc_18000E82C
0x18000e792  cmp     dword ptr [rdx], 0
0x18000e795  jnz     short loc_18000E7A8
0x18000e797  mov     eax, 1
0x18000e79c  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000e7a4  inc     eax
0x18000e7a6  mov     [rdx], eax
0x18000e7a8  cmp     dword ptr [rbx+50h], 0
0x18000e7ac  jnz     short loc_18000E7BF
0x18000e7ae  movups  xmm0, xmmword ptr [rdx]
0x18000e7b1  movups  xmmword ptr [rbx+50h], xmm0
0x18000e7b5  movsd   xmm1, qword ptr [rdx+10h]
0x18000e7ba  movsd   qword ptr [rbx+60h], xmm1
0x18000e7bf  movups  xmm0, xmmword ptr [rdx]
0x18000e7c2  lea     r10, [rdi+rbp]
0x18000e7c6  movups  xmmword ptr [rbx+68h], xmm0
0x18000e7ca  movsd   xmm1, qword ptr [rdx+10h]
0x18000e7cf  movsd   qword ptr [rbx+78h], xmm1
0x18000e7d4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000e7d8  mov     rax, rbx
0x18000e7db  inc     rax
0x18000e7de  cmp     byte ptr [rdi+rax], 0
0x18000e7e2  jnz     short loc_18000E7DB
0x18000e7e4  lea     rcx, [rax+rdi]
0x18000e7e8  mov     rax, r10
0x18000e7eb  sub     rax, rcx
0x18000e7ee  cmp     rax, 2
0x18000e7f2  jle     short loc_18000E82A
0x18000e7f4  mov     byte ptr [rcx], 5Ch ; '\'
0x18000e7f7  lea     rdi, [rcx+1]
0x18000e7fb  mov     r8, [rdx+8]; Source
0x18000e7ff  inc     rbx
0x18000e802  cmp     byte ptr [r8+rbx], 0
0x18000e807  jnz     short loc_18000E7FF
0x18000e809  sub     r10, rdi
0x18000e80c  inc     rbx
0x18000e80f  cmp     rbx, r10
0x18000e812  mov     rdx, r10; DestinationSize
0x18000e815  mov     rcx, rdi; Destination
0x18000e818  cmovnb  rbx, r10
0x18000e81c  mov     r9, rbx; SourceSize
0x18000e81f  call    cs:__imp_memcpy_s
0x18000e825  mov     byte ptr [rbx+rdi-1], 0
0x18000e82a  mov     al, 1
0x18000e82c  add     rsp, 28h
0x18000e830  pop     rdi
0x18000e831  pop     rsi
0x18000e832  pop     rbp
0x18000e833  pop     rbx
0x18000e834  retn
```
