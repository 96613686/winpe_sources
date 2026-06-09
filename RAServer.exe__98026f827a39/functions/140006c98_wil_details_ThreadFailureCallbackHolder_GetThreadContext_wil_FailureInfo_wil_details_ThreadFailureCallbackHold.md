# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140006c98`
- end: `0x140006d75`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000625c`
- `0x140006c98`

## callees

- `0x140006c98`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140006d5f`
- `msvcrt!memcpy_s` at `0x140006d5f`

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
0x140006c98  push    rbx
0x140006c9a  push    rbp
0x140006c9b  push    rsi
0x140006c9c  push    rdi
0x140006c9d  sub     rsp, 28h
0x140006ca1  xor     al, al
0x140006ca3  mov     byte ptr [r8], 0
0x140006ca7  mov     rbp, r9
0x140006caa  mov     rdi, r8
0x140006cad  mov     rsi, rdx
0x140006cb0  mov     rbx, rcx
0x140006cb3  test    rdx, rdx
0x140006cb6  jz      loc_140006D6C
0x140006cbc  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140006cc0  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140006cc5  mov     rdx, [rsi+20h]
0x140006cc9  test    rdx, rdx
0x140006ccc  jz      loc_140006D6C
0x140006cd2  cmp     dword ptr [rdx], 0
0x140006cd5  jnz     short loc_140006CE8
0x140006cd7  mov     eax, 1
0x140006cdc  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140006ce4  inc     eax
0x140006ce6  mov     [rdx], eax
0x140006ce8  cmp     dword ptr [rbx+50h], 0
0x140006cec  jnz     short loc_140006CFF
0x140006cee  movups  xmm0, xmmword ptr [rdx]
0x140006cf1  movups  xmmword ptr [rbx+50h], xmm0
0x140006cf5  movsd   xmm1, qword ptr [rdx+10h]
0x140006cfa  movsd   qword ptr [rbx+60h], xmm1
0x140006cff  movups  xmm0, xmmword ptr [rdx]
0x140006d02  lea     r10, [rdi+rbp]
0x140006d06  movups  xmmword ptr [rbx+68h], xmm0
0x140006d0a  movsd   xmm1, qword ptr [rdx+10h]
0x140006d0f  movsd   qword ptr [rbx+78h], xmm1
0x140006d14  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140006d18  mov     rax, rbx
0x140006d1b  inc     rax
0x140006d1e  cmp     byte ptr [rdi+rax], 0
0x140006d22  jnz     short loc_140006D1B
0x140006d24  lea     rcx, [rax+rdi]
0x140006d28  mov     rax, r10
0x140006d2b  sub     rax, rcx
0x140006d2e  cmp     rax, 2
0x140006d32  jle     short loc_140006D6A
0x140006d34  mov     byte ptr [rcx], 5Ch ; '\'
0x140006d37  lea     rdi, [rcx+1]
0x140006d3b  mov     r8, [rdx+8]; Source
0x140006d3f  inc     rbx
0x140006d42  cmp     byte ptr [r8+rbx], 0
0x140006d47  jnz     short loc_140006D3F
0x140006d49  sub     r10, rdi
0x140006d4c  inc     rbx
0x140006d4f  cmp     rbx, r10
0x140006d52  mov     rdx, r10; DestinationSize
0x140006d55  mov     rcx, rdi; Destination
0x140006d58  cmovnb  rbx, r10
0x140006d5c  mov     r9, rbx; SourceSize
0x140006d5f  call    cs:__imp_memcpy_s
0x140006d65  mov     byte ptr [rbx+rdi-1], 0
0x140006d6a  mov     al, 1
0x140006d6c  add     rsp, 28h
0x140006d70  pop     rdi
0x140006d71  pop     rsi
0x140006d72  pop     rbp
0x140006d73  pop     rbx
0x140006d74  retn
```
