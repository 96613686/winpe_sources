# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x14000b9c8`
- end: `0x14000baa4`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140007184`
- `0x14000b9c8`

## callees

- `0x140006030`
- `0x14000b9c8`

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
0x14000b9c8  push    rbx
0x14000b9ca  push    rbp
0x14000b9cb  push    rsi
0x14000b9cc  push    rdi
0x14000b9cd  sub     rsp, 28h
0x14000b9d1  xor     al, al
0x14000b9d3  mov     byte ptr [r8], 0
0x14000b9d7  mov     rbp, r9
0x14000b9da  mov     rdi, r8
0x14000b9dd  mov     rsi, rdx
0x14000b9e0  mov     rbx, rcx
0x14000b9e3  test    rdx, rdx
0x14000b9e6  jz      loc_14000BA9B
0x14000b9ec  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x14000b9f0  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x14000b9f5  mov     rdx, [rsi+20h]
0x14000b9f9  test    rdx, rdx
0x14000b9fc  jz      loc_14000BA9B
0x14000ba02  cmp     dword ptr [rdx], 0
0x14000ba05  jnz     short loc_14000BA18
0x14000ba07  mov     eax, 1
0x14000ba0c  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x14000ba14  inc     eax
0x14000ba16  mov     [rdx], eax
0x14000ba18  cmp     dword ptr [rbx+50h], 0
0x14000ba1c  jnz     short loc_14000BA2F
0x14000ba1e  movups  xmm0, xmmword ptr [rdx]
0x14000ba21  movups  xmmword ptr [rbx+50h], xmm0
0x14000ba25  movsd   xmm1, qword ptr [rdx+10h]
0x14000ba2a  movsd   qword ptr [rbx+60h], xmm1
0x14000ba2f  movups  xmm0, xmmword ptr [rdx]
0x14000ba32  lea     r10, [rdi+rbp]
0x14000ba36  movups  xmmword ptr [rbx+68h], xmm0
0x14000ba3a  movsd   xmm1, qword ptr [rdx+10h]
0x14000ba3f  movsd   qword ptr [rbx+78h], xmm1
0x14000ba44  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000ba48  mov     rax, rbx
0x14000ba4b  inc     rax
0x14000ba4e  cmp     byte ptr [rdi+rax], 0
0x14000ba52  jnz     short loc_14000BA4B
0x14000ba54  lea     rcx, [rax+rdi]
0x14000ba58  mov     rax, r10
0x14000ba5b  sub     rax, rcx
0x14000ba5e  cmp     rax, 2
0x14000ba62  jle     short loc_14000BA99
0x14000ba64  mov     byte ptr [rcx], 5Ch ; '\'
0x14000ba67  lea     rdi, [rcx+1]
0x14000ba6b  mov     r8, [rdx+8]; Source
0x14000ba6f  inc     rbx
0x14000ba72  cmp     byte ptr [r8+rbx], 0
0x14000ba77  jnz     short loc_14000BA6F
0x14000ba79  sub     r10, rdi
0x14000ba7c  inc     rbx
0x14000ba7f  cmp     rbx, r10
0x14000ba82  mov     rdx, r10; DestinationSize
0x14000ba85  mov     rcx, rdi; Destination
0x14000ba88  cmovnb  rbx, r10
0x14000ba8c  mov     r9, rbx; SourceSize
0x14000ba8f  call    memcpy_s
0x14000ba94  mov     byte ptr [rbx+rdi-1], 0
0x14000ba99  mov     al, 1
0x14000ba9b  add     rsp, 28h
0x14000ba9f  pop     rdi
0x14000baa0  pop     rsi
0x14000baa1  pop     rbp
0x14000baa2  pop     rbx
0x14000baa3  retn
```
