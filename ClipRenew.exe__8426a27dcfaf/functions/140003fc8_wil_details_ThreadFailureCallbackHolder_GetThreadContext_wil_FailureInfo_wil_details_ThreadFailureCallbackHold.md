# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140003fc8`
- end: `0x1400040a5`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400038d0`
- `0x140003fc8`

## callees

- `0x140003fc8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000408f`
- `msvcrt!memcpy_s` at `0x14000408f`

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
0x140003fc8  push    rbx
0x140003fca  push    rbp
0x140003fcb  push    rsi
0x140003fcc  push    rdi
0x140003fcd  sub     rsp, 28h
0x140003fd1  xor     al, al
0x140003fd3  mov     byte ptr [r8], 0
0x140003fd7  mov     rbp, r9
0x140003fda  mov     rdi, r8
0x140003fdd  mov     rsi, rdx
0x140003fe0  mov     rbx, rcx
0x140003fe3  test    rdx, rdx
0x140003fe6  jz      loc_14000409C
0x140003fec  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140003ff0  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140003ff5  mov     rdx, [rsi+20h]
0x140003ff9  test    rdx, rdx
0x140003ffc  jz      loc_14000409C
0x140004002  cmp     dword ptr [rdx], 0
0x140004005  jnz     short loc_140004018
0x140004007  mov     eax, 1
0x14000400c  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140004014  inc     eax
0x140004016  mov     [rdx], eax
0x140004018  cmp     dword ptr [rbx+50h], 0
0x14000401c  jnz     short loc_14000402F
0x14000401e  movups  xmm0, xmmword ptr [rdx]
0x140004021  movups  xmmword ptr [rbx+50h], xmm0
0x140004025  movsd   xmm1, qword ptr [rdx+10h]
0x14000402a  movsd   qword ptr [rbx+60h], xmm1
0x14000402f  movups  xmm0, xmmword ptr [rdx]
0x140004032  lea     r10, [rdi+rbp]
0x140004036  movups  xmmword ptr [rbx+68h], xmm0
0x14000403a  movsd   xmm1, qword ptr [rdx+10h]
0x14000403f  movsd   qword ptr [rbx+78h], xmm1
0x140004044  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140004048  mov     rax, rbx
0x14000404b  inc     rax
0x14000404e  cmp     byte ptr [rdi+rax], 0
0x140004052  jnz     short loc_14000404B
0x140004054  lea     rcx, [rax+rdi]
0x140004058  mov     rax, r10
0x14000405b  sub     rax, rcx
0x14000405e  cmp     rax, 2
0x140004062  jle     short loc_14000409A
0x140004064  mov     byte ptr [rcx], 5Ch ; '\'
0x140004067  lea     rdi, [rcx+1]
0x14000406b  mov     r8, [rdx+8]; Source
0x14000406f  inc     rbx
0x140004072  cmp     byte ptr [r8+rbx], 0
0x140004077  jnz     short loc_14000406F
0x140004079  sub     r10, rdi
0x14000407c  inc     rbx
0x14000407f  cmp     rbx, r10
0x140004082  mov     rdx, r10; DestinationSize
0x140004085  mov     rcx, rdi; Destination
0x140004088  cmovnb  rbx, r10
0x14000408c  mov     r9, rbx; SourceSize
0x14000408f  call    cs:__imp_memcpy_s
0x140004095  mov     byte ptr [rbx+rdi-1], 0
0x14000409a  mov     al, 1
0x14000409c  add     rsp, 28h
0x1400040a0  pop     rdi
0x1400040a1  pop     rsi
0x1400040a2  pop     rbp
0x1400040a3  pop     rbx
0x1400040a4  retn
```
