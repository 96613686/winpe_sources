# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x1800058a4`
- end: `0x180005981`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005280`
- `0x1800058a4`

## callees

- `0x1800058a4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000596b`
- `msvcrt!memcpy_s` at `0x18000596b`

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
0x1800058a4  push    rbx
0x1800058a6  push    rbp
0x1800058a7  push    rsi
0x1800058a8  push    rdi
0x1800058a9  sub     rsp, 28h
0x1800058ad  xor     al, al
0x1800058af  mov     byte ptr [r8], 0
0x1800058b3  mov     rbp, r9
0x1800058b6  mov     rdi, r8
0x1800058b9  mov     rsi, rdx
0x1800058bc  mov     rbx, rcx
0x1800058bf  test    rdx, rdx
0x1800058c2  jz      loc_180005978
0x1800058c8  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x1800058cc  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800058d1  mov     rdx, [rsi+20h]
0x1800058d5  test    rdx, rdx
0x1800058d8  jz      loc_180005978
0x1800058de  cmp     dword ptr [rdx], 0
0x1800058e1  jnz     short loc_1800058F4
0x1800058e3  mov     eax, 1
0x1800058e8  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x1800058f0  inc     eax
0x1800058f2  mov     [rdx], eax
0x1800058f4  cmp     dword ptr [rbx+50h], 0
0x1800058f8  jnz     short loc_18000590B
0x1800058fa  movups  xmm0, xmmword ptr [rdx]
0x1800058fd  movups  xmmword ptr [rbx+50h], xmm0
0x180005901  movsd   xmm1, qword ptr [rdx+10h]
0x180005906  movsd   qword ptr [rbx+60h], xmm1
0x18000590b  movups  xmm0, xmmword ptr [rdx]
0x18000590e  lea     r10, [rdi+rbp]
0x180005912  movups  xmmword ptr [rbx+68h], xmm0
0x180005916  movsd   xmm1, qword ptr [rdx+10h]
0x18000591b  movsd   qword ptr [rbx+78h], xmm1
0x180005920  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005924  mov     rax, rbx
0x180005927  inc     rax
0x18000592a  cmp     byte ptr [rdi+rax], 0
0x18000592e  jnz     short loc_180005927
0x180005930  lea     rcx, [rax+rdi]
0x180005934  mov     rax, r10
0x180005937  sub     rax, rcx
0x18000593a  cmp     rax, 2
0x18000593e  jle     short loc_180005976
0x180005940  mov     byte ptr [rcx], 5Ch ; '\'
0x180005943  lea     rdi, [rcx+1]
0x180005947  mov     r8, [rdx+8]; Source
0x18000594b  inc     rbx
0x18000594e  cmp     byte ptr [r8+rbx], 0
0x180005953  jnz     short loc_18000594B
0x180005955  sub     r10, rdi
0x180005958  inc     rbx
0x18000595b  cmp     rbx, r10
0x18000595e  mov     rdx, r10; DestinationSize
0x180005961  mov     rcx, rdi; Destination
0x180005964  cmovnb  rbx, r10
0x180005968  mov     r9, rbx; SourceSize
0x18000596b  call    cs:__imp_memcpy_s
0x180005971  mov     byte ptr [rbx+rdi-1], 0
0x180005976  mov     al, 1
0x180005978  add     rsp, 28h
0x18000597c  pop     rdi
0x18000597d  pop     rsi
0x18000597e  pop     rbp
0x18000597f  pop     rbx
0x180005980  retn
```
