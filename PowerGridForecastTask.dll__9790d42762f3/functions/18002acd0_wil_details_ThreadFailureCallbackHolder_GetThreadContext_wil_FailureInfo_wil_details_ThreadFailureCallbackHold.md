# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18002acd0`
- end: `0x18002adad`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002a5f0`
- `0x18002acd0`

## callees

- `0x18002acd0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18002ad97`
- `msvcrt!memcpy_s` at `0x18002ad97`

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
0x18002acd0  push    rbx
0x18002acd2  push    rbp
0x18002acd3  push    rsi
0x18002acd4  push    rdi
0x18002acd5  sub     rsp, 28h
0x18002acd9  xor     al, al
0x18002acdb  mov     byte ptr [r8], 0
0x18002acdf  mov     rbp, r9
0x18002ace2  mov     rdi, r8
0x18002ace5  mov     rsi, rdx
0x18002ace8  mov     rbx, rcx
0x18002aceb  test    rdx, rdx
0x18002acee  jz      loc_18002ADA4
0x18002acf4  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18002acf8  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18002acfd  mov     rdx, [rsi+20h]
0x18002ad01  test    rdx, rdx
0x18002ad04  jz      loc_18002ADA4
0x18002ad0a  cmp     dword ptr [rdx], 0
0x18002ad0d  jnz     short loc_18002AD20
0x18002ad0f  mov     eax, 1
0x18002ad14  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18002ad1c  inc     eax
0x18002ad1e  mov     [rdx], eax
0x18002ad20  cmp     dword ptr [rbx+50h], 0
0x18002ad24  jnz     short loc_18002AD37
0x18002ad26  movups  xmm0, xmmword ptr [rdx]
0x18002ad29  movups  xmmword ptr [rbx+50h], xmm0
0x18002ad2d  movsd   xmm1, qword ptr [rdx+10h]
0x18002ad32  movsd   qword ptr [rbx+60h], xmm1
0x18002ad37  movups  xmm0, xmmword ptr [rdx]
0x18002ad3a  lea     r10, [rdi+rbp]
0x18002ad3e  movups  xmmword ptr [rbx+68h], xmm0
0x18002ad42  movsd   xmm1, qword ptr [rdx+10h]
0x18002ad47  movsd   qword ptr [rbx+78h], xmm1
0x18002ad4c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002ad50  mov     rax, rbx
0x18002ad53  inc     rax
0x18002ad56  cmp     byte ptr [rdi+rax], 0
0x18002ad5a  jnz     short loc_18002AD53
0x18002ad5c  lea     rcx, [rax+rdi]
0x18002ad60  mov     rax, r10
0x18002ad63  sub     rax, rcx
0x18002ad66  cmp     rax, 2
0x18002ad6a  jle     short loc_18002ADA2
0x18002ad6c  mov     byte ptr [rcx], 5Ch ; '\'
0x18002ad6f  lea     rdi, [rcx+1]
0x18002ad73  mov     r8, [rdx+8]; Source
0x18002ad77  inc     rbx
0x18002ad7a  cmp     byte ptr [r8+rbx], 0
0x18002ad7f  jnz     short loc_18002AD77
0x18002ad81  sub     r10, rdi
0x18002ad84  inc     rbx
0x18002ad87  cmp     rbx, r10
0x18002ad8a  mov     rdx, r10; DestinationSize
0x18002ad8d  mov     rcx, rdi; Destination
0x18002ad90  cmovnb  rbx, r10
0x18002ad94  mov     r9, rbx; SourceSize
0x18002ad97  call    cs:__imp_memcpy_s
0x18002ad9d  mov     byte ptr [rbx+rdi-1], 0
0x18002ada2  mov     al, 1
0x18002ada4  add     rsp, 28h
0x18002ada8  pop     rdi
0x18002ada9  pop     rsi
0x18002adaa  pop     rbp
0x18002adab  pop     rbx
0x18002adac  retn
```
