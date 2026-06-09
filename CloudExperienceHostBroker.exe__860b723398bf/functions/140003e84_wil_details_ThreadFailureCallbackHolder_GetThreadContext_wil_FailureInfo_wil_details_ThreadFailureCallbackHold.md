# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140003e84`
- end: `0x140003f61`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140003824`
- `0x140003e84`

## callees

- `0x140003e84`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140003f4b`
- `msvcrt!memcpy_s` at `0x140003f4b`

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
0x140003e84  push    rbx
0x140003e86  push    rbp
0x140003e87  push    rsi
0x140003e88  push    rdi
0x140003e89  sub     rsp, 28h
0x140003e8d  xor     al, al
0x140003e8f  mov     byte ptr [r8], 0
0x140003e93  mov     rbp, r9
0x140003e96  mov     rdi, r8
0x140003e99  mov     rsi, rdx
0x140003e9c  mov     rbx, rcx
0x140003e9f  test    rdx, rdx
0x140003ea2  jz      loc_140003F58
0x140003ea8  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140003eac  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140003eb1  mov     rdx, [rsi+20h]
0x140003eb5  test    rdx, rdx
0x140003eb8  jz      loc_140003F58
0x140003ebe  cmp     dword ptr [rdx], 0
0x140003ec1  jnz     short loc_140003ED4
0x140003ec3  mov     eax, 1
0x140003ec8  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140003ed0  inc     eax
0x140003ed2  mov     [rdx], eax
0x140003ed4  cmp     dword ptr [rbx+50h], 0
0x140003ed8  jnz     short loc_140003EEB
0x140003eda  movups  xmm0, xmmword ptr [rdx]
0x140003edd  movups  xmmword ptr [rbx+50h], xmm0
0x140003ee1  movsd   xmm1, qword ptr [rdx+10h]
0x140003ee6  movsd   qword ptr [rbx+60h], xmm1
0x140003eeb  movups  xmm0, xmmword ptr [rdx]
0x140003eee  lea     r10, [rdi+rbp]
0x140003ef2  movups  xmmword ptr [rbx+68h], xmm0
0x140003ef6  movsd   xmm1, qword ptr [rdx+10h]
0x140003efb  movsd   qword ptr [rbx+78h], xmm1
0x140003f00  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140003f04  mov     rax, rbx
0x140003f07  inc     rax
0x140003f0a  cmp     byte ptr [rdi+rax], 0
0x140003f0e  jnz     short loc_140003F07
0x140003f10  lea     rcx, [rax+rdi]
0x140003f14  mov     rax, r10
0x140003f17  sub     rax, rcx
0x140003f1a  cmp     rax, 2
0x140003f1e  jle     short loc_140003F56
0x140003f20  mov     byte ptr [rcx], 5Ch ; '\'
0x140003f23  lea     rdi, [rcx+1]
0x140003f27  mov     r8, [rdx+8]; Source
0x140003f2b  inc     rbx
0x140003f2e  cmp     byte ptr [r8+rbx], 0
0x140003f33  jnz     short loc_140003F2B
0x140003f35  sub     r10, rdi
0x140003f38  inc     rbx
0x140003f3b  cmp     rbx, r10
0x140003f3e  mov     rdx, r10; DestinationSize
0x140003f41  mov     rcx, rdi; Destination
0x140003f44  cmovnb  rbx, r10
0x140003f48  mov     r9, rbx; SourceSize
0x140003f4b  call    cs:__imp_memcpy_s
0x140003f51  mov     byte ptr [rbx+rdi-1], 0
0x140003f56  mov     al, 1
0x140003f58  add     rsp, 28h
0x140003f5c  pop     rdi
0x140003f5d  pop     rsi
0x140003f5e  pop     rbp
0x140003f5f  pop     rbx
0x140003f60  retn
```
