# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140005c48`
- end: `0x140005d25`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400055b4`
- `0x140005c48`

## callees

- `0x140005c48`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140005d0f`
- `msvcrt!memcpy_s` at `0x140005d0f`

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
0x140005c48  push    rbx
0x140005c4a  push    rbp
0x140005c4b  push    rsi
0x140005c4c  push    rdi
0x140005c4d  sub     rsp, 28h
0x140005c51  xor     al, al
0x140005c53  mov     byte ptr [r8], 0
0x140005c57  mov     rbp, r9
0x140005c5a  mov     rdi, r8
0x140005c5d  mov     rsi, rdx
0x140005c60  mov     rbx, rcx
0x140005c63  test    rdx, rdx
0x140005c66  jz      loc_140005D1C
0x140005c6c  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140005c70  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140005c75  mov     rdx, [rsi+20h]
0x140005c79  test    rdx, rdx
0x140005c7c  jz      loc_140005D1C
0x140005c82  cmp     dword ptr [rdx], 0
0x140005c85  jnz     short loc_140005C98
0x140005c87  mov     eax, 1
0x140005c8c  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140005c94  inc     eax
0x140005c96  mov     [rdx], eax
0x140005c98  cmp     dword ptr [rbx+50h], 0
0x140005c9c  jnz     short loc_140005CAF
0x140005c9e  movups  xmm0, xmmword ptr [rdx]
0x140005ca1  movups  xmmword ptr [rbx+50h], xmm0
0x140005ca5  movsd   xmm1, qword ptr [rdx+10h]
0x140005caa  movsd   qword ptr [rbx+60h], xmm1
0x140005caf  movups  xmm0, xmmword ptr [rdx]
0x140005cb2  lea     r10, [rdi+rbp]
0x140005cb6  movups  xmmword ptr [rbx+68h], xmm0
0x140005cba  movsd   xmm1, qword ptr [rdx+10h]
0x140005cbf  movsd   qword ptr [rbx+78h], xmm1
0x140005cc4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140005cc8  mov     rax, rbx
0x140005ccb  inc     rax
0x140005cce  cmp     byte ptr [rdi+rax], 0
0x140005cd2  jnz     short loc_140005CCB
0x140005cd4  lea     rcx, [rax+rdi]
0x140005cd8  mov     rax, r10
0x140005cdb  sub     rax, rcx
0x140005cde  cmp     rax, 2
0x140005ce2  jle     short loc_140005D1A
0x140005ce4  mov     byte ptr [rcx], 5Ch ; '\'
0x140005ce7  lea     rdi, [rcx+1]
0x140005ceb  mov     r8, [rdx+8]; Source
0x140005cef  inc     rbx
0x140005cf2  cmp     byte ptr [r8+rbx], 0
0x140005cf7  jnz     short loc_140005CEF
0x140005cf9  sub     r10, rdi
0x140005cfc  inc     rbx
0x140005cff  cmp     rbx, r10
0x140005d02  mov     rdx, r10; DestinationSize
0x140005d05  mov     rcx, rdi; Destination
0x140005d08  cmovnb  rbx, r10
0x140005d0c  mov     r9, rbx; SourceSize
0x140005d0f  call    cs:__imp_memcpy_s
0x140005d15  mov     byte ptr [rbx+rdi-1], 0
0x140005d1a  mov     al, 1
0x140005d1c  add     rsp, 28h
0x140005d20  pop     rdi
0x140005d21  pop     rsi
0x140005d22  pop     rbp
0x140005d23  pop     rbx
0x140005d24  retn
```
