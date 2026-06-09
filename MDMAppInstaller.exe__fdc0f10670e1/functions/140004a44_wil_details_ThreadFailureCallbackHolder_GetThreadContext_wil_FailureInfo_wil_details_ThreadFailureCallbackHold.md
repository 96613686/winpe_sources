# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140004a44`
- end: `0x140004b21`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400043e4`
- `0x140004a44`

## callees

- `0x140004a44`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140004b0b`
- `msvcrt!memcpy_s` at `0x140004b0b`

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
0x140004a44  push    rbx
0x140004a46  push    rbp
0x140004a47  push    rsi
0x140004a48  push    rdi
0x140004a49  sub     rsp, 28h
0x140004a4d  xor     al, al
0x140004a4f  mov     byte ptr [r8], 0
0x140004a53  mov     rbp, r9
0x140004a56  mov     rdi, r8
0x140004a59  mov     rsi, rdx
0x140004a5c  mov     rbx, rcx
0x140004a5f  test    rdx, rdx
0x140004a62  jz      loc_140004B18
0x140004a68  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140004a6c  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140004a71  mov     rdx, [rsi+20h]
0x140004a75  test    rdx, rdx
0x140004a78  jz      loc_140004B18
0x140004a7e  cmp     dword ptr [rdx], 0
0x140004a81  jnz     short loc_140004A94
0x140004a83  mov     eax, 1
0x140004a88  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140004a90  inc     eax
0x140004a92  mov     [rdx], eax
0x140004a94  cmp     dword ptr [rbx+50h], 0
0x140004a98  jnz     short loc_140004AAB
0x140004a9a  movups  xmm0, xmmword ptr [rdx]
0x140004a9d  movups  xmmword ptr [rbx+50h], xmm0
0x140004aa1  movsd   xmm1, qword ptr [rdx+10h]
0x140004aa6  movsd   qword ptr [rbx+60h], xmm1
0x140004aab  movups  xmm0, xmmword ptr [rdx]
0x140004aae  lea     r10, [rdi+rbp]
0x140004ab2  movups  xmmword ptr [rbx+68h], xmm0
0x140004ab6  movsd   xmm1, qword ptr [rdx+10h]
0x140004abb  movsd   qword ptr [rbx+78h], xmm1
0x140004ac0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140004ac4  mov     rax, rbx
0x140004ac7  inc     rax
0x140004aca  cmp     byte ptr [rdi+rax], 0
0x140004ace  jnz     short loc_140004AC7
0x140004ad0  lea     rcx, [rax+rdi]
0x140004ad4  mov     rax, r10
0x140004ad7  sub     rax, rcx
0x140004ada  cmp     rax, 2
0x140004ade  jle     short loc_140004B16
0x140004ae0  mov     byte ptr [rcx], 5Ch ; '\'
0x140004ae3  lea     rdi, [rcx+1]
0x140004ae7  mov     r8, [rdx+8]; Source
0x140004aeb  inc     rbx
0x140004aee  cmp     byte ptr [r8+rbx], 0
0x140004af3  jnz     short loc_140004AEB
0x140004af5  sub     r10, rdi
0x140004af8  inc     rbx
0x140004afb  cmp     rbx, r10
0x140004afe  mov     rdx, r10; DestinationSize
0x140004b01  mov     rcx, rdi; Destination
0x140004b04  cmovnb  rbx, r10
0x140004b08  mov     r9, rbx; SourceSize
0x140004b0b  call    cs:__imp_memcpy_s
0x140004b11  mov     byte ptr [rbx+rdi-1], 0
0x140004b16  mov     al, 1
0x140004b18  add     rsp, 28h
0x140004b1c  pop     rdi
0x140004b1d  pop     rsi
0x140004b1e  pop     rbp
0x140004b1f  pop     rbx
0x140004b20  retn
```
