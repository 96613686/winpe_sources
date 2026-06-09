# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180004ef0`
- end: `0x180004fcd`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004810`
- `0x180004ef0`

## callees

- `0x180004ef0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180004fb7`
- `msvcrt!memcpy_s` at `0x180004fb7`

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
0x180004ef0  push    rbx
0x180004ef2  push    rbp
0x180004ef3  push    rsi
0x180004ef4  push    rdi
0x180004ef5  sub     rsp, 28h
0x180004ef9  xor     al, al
0x180004efb  mov     byte ptr [r8], 0
0x180004eff  mov     rbp, r9
0x180004f02  mov     rdi, r8
0x180004f05  mov     rsi, rdx
0x180004f08  mov     rbx, rcx
0x180004f0b  test    rdx, rdx
0x180004f0e  jz      loc_180004FC4
0x180004f14  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180004f18  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004f1d  mov     rdx, [rsi+20h]
0x180004f21  test    rdx, rdx
0x180004f24  jz      loc_180004FC4
0x180004f2a  cmp     dword ptr [rdx], 0
0x180004f2d  jnz     short loc_180004F40
0x180004f2f  mov     eax, 1
0x180004f34  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180004f3c  inc     eax
0x180004f3e  mov     [rdx], eax
0x180004f40  cmp     dword ptr [rbx+50h], 0
0x180004f44  jnz     short loc_180004F57
0x180004f46  movups  xmm0, xmmword ptr [rdx]
0x180004f49  movups  xmmword ptr [rbx+50h], xmm0
0x180004f4d  movsd   xmm1, qword ptr [rdx+10h]
0x180004f52  movsd   qword ptr [rbx+60h], xmm1
0x180004f57  movups  xmm0, xmmword ptr [rdx]
0x180004f5a  lea     r10, [rdi+rbp]
0x180004f5e  movups  xmmword ptr [rbx+68h], xmm0
0x180004f62  movsd   xmm1, qword ptr [rdx+10h]
0x180004f67  movsd   qword ptr [rbx+78h], xmm1
0x180004f6c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004f70  mov     rax, rbx
0x180004f73  inc     rax
0x180004f76  cmp     byte ptr [rdi+rax], 0
0x180004f7a  jnz     short loc_180004F73
0x180004f7c  lea     rcx, [rax+rdi]
0x180004f80  mov     rax, r10
0x180004f83  sub     rax, rcx
0x180004f86  cmp     rax, 2
0x180004f8a  jle     short loc_180004FC2
0x180004f8c  mov     byte ptr [rcx], 5Ch ; '\'
0x180004f8f  lea     rdi, [rcx+1]
0x180004f93  mov     r8, [rdx+8]; Source
0x180004f97  inc     rbx
0x180004f9a  cmp     byte ptr [r8+rbx], 0
0x180004f9f  jnz     short loc_180004F97
0x180004fa1  sub     r10, rdi
0x180004fa4  inc     rbx
0x180004fa7  cmp     rbx, r10
0x180004faa  mov     rdx, r10; DestinationSize
0x180004fad  mov     rcx, rdi; Destination
0x180004fb0  cmovnb  rbx, r10
0x180004fb4  mov     r9, rbx; SourceSize
0x180004fb7  call    cs:__imp_memcpy_s
0x180004fbd  mov     byte ptr [rbx+rdi-1], 0
0x180004fc2  mov     al, 1
0x180004fc4  add     rsp, 28h
0x180004fc8  pop     rdi
0x180004fc9  pop     rsi
0x180004fca  pop     rbp
0x180004fcb  pop     rbx
0x180004fcc  retn
```
