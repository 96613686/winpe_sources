# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000a9e8`
- end: `0x18000aac5`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800089f0`
- `0x18000a9e8`

## callees

- `0x18000a9e8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000aaaf`
- `msvcrt!memcpy_s` at `0x18000aaaf`

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
0x18000a9e8  push    rbx
0x18000a9ea  push    rbp
0x18000a9eb  push    rsi
0x18000a9ec  push    rdi
0x18000a9ed  sub     rsp, 28h
0x18000a9f1  xor     al, al
0x18000a9f3  mov     byte ptr [r8], 0
0x18000a9f7  mov     rbp, r9
0x18000a9fa  mov     rdi, r8
0x18000a9fd  mov     rsi, rdx
0x18000aa00  mov     rbx, rcx
0x18000aa03  test    rdx, rdx
0x18000aa06  jz      loc_18000AABC
0x18000aa0c  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18000aa10  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000aa15  mov     rdx, [rsi+20h]
0x18000aa19  test    rdx, rdx
0x18000aa1c  jz      loc_18000AABC
0x18000aa22  cmp     dword ptr [rdx], 0
0x18000aa25  jnz     short loc_18000AA38
0x18000aa27  mov     eax, 1
0x18000aa2c  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000aa34  inc     eax
0x18000aa36  mov     [rdx], eax
0x18000aa38  cmp     dword ptr [rbx+50h], 0
0x18000aa3c  jnz     short loc_18000AA4F
0x18000aa3e  movups  xmm0, xmmword ptr [rdx]
0x18000aa41  movups  xmmword ptr [rbx+50h], xmm0
0x18000aa45  movsd   xmm1, qword ptr [rdx+10h]
0x18000aa4a  movsd   qword ptr [rbx+60h], xmm1
0x18000aa4f  movups  xmm0, xmmword ptr [rdx]
0x18000aa52  lea     r10, [rdi+rbp]
0x18000aa56  movups  xmmword ptr [rbx+68h], xmm0
0x18000aa5a  movsd   xmm1, qword ptr [rdx+10h]
0x18000aa5f  movsd   qword ptr [rbx+78h], xmm1
0x18000aa64  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000aa68  mov     rax, rbx
0x18000aa6b  inc     rax
0x18000aa6e  cmp     byte ptr [rdi+rax], 0
0x18000aa72  jnz     short loc_18000AA6B
0x18000aa74  lea     rcx, [rax+rdi]
0x18000aa78  mov     rax, r10
0x18000aa7b  sub     rax, rcx
0x18000aa7e  cmp     rax, 2
0x18000aa82  jle     short loc_18000AABA
0x18000aa84  mov     byte ptr [rcx], 5Ch ; '\'
0x18000aa87  lea     rdi, [rcx+1]
0x18000aa8b  mov     r8, [rdx+8]; Source
0x18000aa8f  inc     rbx
0x18000aa92  cmp     byte ptr [r8+rbx], 0
0x18000aa97  jnz     short loc_18000AA8F
0x18000aa99  sub     r10, rdi
0x18000aa9c  inc     rbx
0x18000aa9f  cmp     rbx, r10
0x18000aaa2  mov     rdx, r10; DestinationSize
0x18000aaa5  mov     rcx, rdi; Destination
0x18000aaa8  cmovnb  rbx, r10
0x18000aaac  mov     r9, rbx; SourceSize
0x18000aaaf  call    cs:__imp_memcpy_s
0x18000aab5  mov     byte ptr [rbx+rdi-1], 0
0x18000aaba  mov     al, 1
0x18000aabc  add     rsp, 28h
0x18000aac0  pop     rdi
0x18000aac1  pop     rsi
0x18000aac2  pop     rbp
0x18000aac3  pop     rbx
0x18000aac4  retn
```
