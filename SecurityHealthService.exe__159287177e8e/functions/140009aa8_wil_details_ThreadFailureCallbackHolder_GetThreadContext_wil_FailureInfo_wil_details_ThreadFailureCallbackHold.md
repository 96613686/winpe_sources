# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140009aa8`
- end: `0x140009b84`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400096d0`
- `0x140009aa8`

## callees

- `0x140009aa8`
- `0x14000cad8`

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
0x140009aa8  push    rbx
0x140009aaa  push    rbp
0x140009aab  push    rsi
0x140009aac  push    rdi
0x140009aad  sub     rsp, 28h
0x140009ab1  xor     al, al
0x140009ab3  mov     byte ptr [r8], 0
0x140009ab7  mov     rbp, r9
0x140009aba  mov     rdi, r8
0x140009abd  mov     rsi, rdx
0x140009ac0  mov     rbx, rcx
0x140009ac3  test    rdx, rdx
0x140009ac6  jz      loc_140009B7B
0x140009acc  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140009ad0  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140009ad5  mov     rdx, [rsi+20h]
0x140009ad9  test    rdx, rdx
0x140009adc  jz      loc_140009B7B
0x140009ae2  cmp     dword ptr [rdx], 0
0x140009ae5  jnz     short loc_140009AF8
0x140009ae7  mov     eax, 1
0x140009aec  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140009af4  inc     eax
0x140009af6  mov     [rdx], eax
0x140009af8  cmp     dword ptr [rbx+50h], 0
0x140009afc  jnz     short loc_140009B0F
0x140009afe  movups  xmm0, xmmword ptr [rdx]
0x140009b01  movups  xmmword ptr [rbx+50h], xmm0
0x140009b05  movsd   xmm1, qword ptr [rdx+10h]
0x140009b0a  movsd   qword ptr [rbx+60h], xmm1
0x140009b0f  movups  xmm0, xmmword ptr [rdx]
0x140009b12  lea     r10, [rdi+rbp]
0x140009b16  movups  xmmword ptr [rbx+68h], xmm0
0x140009b1a  movsd   xmm1, qword ptr [rdx+10h]
0x140009b1f  movsd   qword ptr [rbx+78h], xmm1
0x140009b24  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140009b28  mov     rax, rbx
0x140009b2b  inc     rax
0x140009b2e  cmp     byte ptr [rdi+rax], 0
0x140009b32  jnz     short loc_140009B2B
0x140009b34  lea     rcx, [rax+rdi]
0x140009b38  mov     rax, r10
0x140009b3b  sub     rax, rcx
0x140009b3e  cmp     rax, 2
0x140009b42  jle     short loc_140009B79
0x140009b44  mov     byte ptr [rcx], 5Ch ; '\'
0x140009b47  lea     rdi, [rcx+1]
0x140009b4b  mov     r8, [rdx+8]; Source
0x140009b4f  inc     rbx
0x140009b52  cmp     byte ptr [r8+rbx], 0
0x140009b57  jnz     short loc_140009B4F
0x140009b59  sub     r10, rdi
0x140009b5c  inc     rbx
0x140009b5f  cmp     rbx, r10
0x140009b62  mov     rdx, r10; DestinationSize
0x140009b65  mov     rcx, rdi; Destination
0x140009b68  cmovnb  rbx, r10
0x140009b6c  mov     r9, rbx; SourceSize
0x140009b6f  call    memcpy_s
0x140009b74  mov     byte ptr [rbx+rdi-1], 0
0x140009b79  mov     al, 1
0x140009b7b  add     rsp, 28h
0x140009b7f  pop     rdi
0x140009b80  pop     rsi
0x140009b81  pop     rbp
0x140009b82  pop     rbx
0x140009b83  retn
```
