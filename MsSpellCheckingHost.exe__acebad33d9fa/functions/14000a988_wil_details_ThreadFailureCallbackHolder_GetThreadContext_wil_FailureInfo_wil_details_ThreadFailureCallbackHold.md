# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x14000a988`
- end: `0x14000aa65`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000a310`
- `0x14000a988`

## callees

- `0x14000a988`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000aa4f`
- `msvcrt!memcpy_s` at `0x14000aa4f`

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
0x14000a988  push    rbx
0x14000a98a  push    rbp
0x14000a98b  push    rsi
0x14000a98c  push    rdi
0x14000a98d  sub     rsp, 28h
0x14000a991  xor     al, al
0x14000a993  mov     byte ptr [r8], 0
0x14000a997  mov     rbp, r9
0x14000a99a  mov     rdi, r8
0x14000a99d  mov     rsi, rdx
0x14000a9a0  mov     rbx, rcx
0x14000a9a3  test    rdx, rdx
0x14000a9a6  jz      loc_14000AA5C
0x14000a9ac  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x14000a9b0  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x14000a9b5  mov     rdx, [rsi+20h]
0x14000a9b9  test    rdx, rdx
0x14000a9bc  jz      loc_14000AA5C
0x14000a9c2  cmp     dword ptr [rdx], 0
0x14000a9c5  jnz     short loc_14000A9D8
0x14000a9c7  mov     eax, 1
0x14000a9cc  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x14000a9d4  inc     eax
0x14000a9d6  mov     [rdx], eax
0x14000a9d8  cmp     dword ptr [rbx+50h], 0
0x14000a9dc  jnz     short loc_14000A9EF
0x14000a9de  movups  xmm0, xmmword ptr [rdx]
0x14000a9e1  movups  xmmword ptr [rbx+50h], xmm0
0x14000a9e5  movsd   xmm1, qword ptr [rdx+10h]
0x14000a9ea  movsd   qword ptr [rbx+60h], xmm1
0x14000a9ef  movups  xmm0, xmmword ptr [rdx]
0x14000a9f2  lea     r10, [rdi+rbp]
0x14000a9f6  movups  xmmword ptr [rbx+68h], xmm0
0x14000a9fa  movsd   xmm1, qword ptr [rdx+10h]
0x14000a9ff  movsd   qword ptr [rbx+78h], xmm1
0x14000aa04  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000aa08  mov     rax, rbx
0x14000aa0b  inc     rax
0x14000aa0e  cmp     byte ptr [rdi+rax], 0
0x14000aa12  jnz     short loc_14000AA0B
0x14000aa14  lea     rcx, [rax+rdi]
0x14000aa18  mov     rax, r10
0x14000aa1b  sub     rax, rcx
0x14000aa1e  cmp     rax, 2
0x14000aa22  jle     short loc_14000AA5A
0x14000aa24  mov     byte ptr [rcx], 5Ch ; '\'
0x14000aa27  lea     rdi, [rcx+1]
0x14000aa2b  mov     r8, [rdx+8]; Source
0x14000aa2f  inc     rbx
0x14000aa32  cmp     byte ptr [r8+rbx], 0
0x14000aa37  jnz     short loc_14000AA2F
0x14000aa39  sub     r10, rdi
0x14000aa3c  inc     rbx
0x14000aa3f  cmp     rbx, r10
0x14000aa42  mov     rdx, r10; DestinationSize
0x14000aa45  mov     rcx, rdi; Destination
0x14000aa48  cmovnb  rbx, r10
0x14000aa4c  mov     r9, rbx; SourceSize
0x14000aa4f  call    cs:__imp_memcpy_s
0x14000aa55  mov     byte ptr [rbx+rdi-1], 0
0x14000aa5a  mov     al, 1
0x14000aa5c  add     rsp, 28h
0x14000aa60  pop     rdi
0x14000aa61  pop     rsi
0x14000aa62  pop     rbp
0x14000aa63  pop     rbx
0x14000aa64  retn
```
