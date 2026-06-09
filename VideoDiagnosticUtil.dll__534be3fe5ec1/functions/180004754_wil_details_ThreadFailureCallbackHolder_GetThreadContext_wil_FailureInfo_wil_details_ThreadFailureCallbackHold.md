# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180004754`
- end: `0x180004838`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `228`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800041a0`
- `0x180004754`

## callees

- `0x180004754`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000481b`
- `msvcrt!memcpy_s` at `0x18000481b`

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
0x180004754  push    rbx
0x180004756  push    rbp
0x180004757  push    rsi
0x180004758  push    rdi
0x180004759  sub     rsp, 28h
0x18000475d  xor     al, al
0x18000475f  mov     byte ptr [r8], 0
0x180004763  mov     rbp, r9
0x180004766  mov     rdi, r8
0x180004769  mov     rsi, rdx
0x18000476c  mov     rbx, rcx
0x18000476f  test    rdx, rdx
0x180004772  jz      loc_18000482E
0x180004778  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18000477c  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004781  mov     rdx, [rsi+20h]
0x180004785  test    rdx, rdx
0x180004788  jz      loc_18000482E
0x18000478e  cmp     dword ptr [rdx], 0
0x180004791  jnz     short loc_1800047A4
0x180004793  mov     eax, 1
0x180004798  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x1800047a0  inc     eax
0x1800047a2  mov     [rdx], eax
0x1800047a4  cmp     dword ptr [rbx+50h], 0
0x1800047a8  jnz     short loc_1800047BB
0x1800047aa  movups  xmm0, xmmword ptr [rdx]
0x1800047ad  movups  xmmword ptr [rbx+50h], xmm0
0x1800047b1  movsd   xmm1, qword ptr [rdx+10h]
0x1800047b6  movsd   qword ptr [rbx+60h], xmm1
0x1800047bb  movups  xmm0, xmmword ptr [rdx]
0x1800047be  lea     r10, [rdi+rbp]
0x1800047c2  movups  xmmword ptr [rbx+68h], xmm0
0x1800047c6  movsd   xmm1, qword ptr [rdx+10h]
0x1800047cb  movsd   qword ptr [rbx+78h], xmm1
0x1800047d0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800047d4  mov     rax, rbx
0x1800047d7  inc     rax
0x1800047da  cmp     byte ptr [rdi+rax], 0
0x1800047de  jnz     short loc_1800047D7
0x1800047e0  lea     rcx, [rax+rdi]
0x1800047e4  mov     rax, r10
0x1800047e7  sub     rax, rcx
0x1800047ea  cmp     rax, 2
0x1800047ee  jle     short loc_18000482C
0x1800047f0  mov     byte ptr [rcx], 5Ch ; '\'
0x1800047f3  lea     rdi, [rcx+1]
0x1800047f7  mov     r8, [rdx+8]; Source
0x1800047fb  inc     rbx
0x1800047fe  cmp     byte ptr [r8+rbx], 0
0x180004803  jnz     short loc_1800047FB
0x180004805  sub     r10, rdi
0x180004808  inc     rbx
0x18000480b  cmp     rbx, r10
0x18000480e  mov     rdx, r10; DestinationSize
0x180004811  mov     rcx, rdi; Destination
0x180004814  cmovnb  rbx, r10
0x180004818  mov     r9, rbx; SourceSize
0x18000481b  call    cs:__imp_memcpy_s
0x180004822  nop     dword ptr [rax+rax+00h]
0x180004827  mov     byte ptr [rbx+rdi-1], 0
0x18000482c  mov     al, 1
0x18000482e  add     rsp, 28h
0x180004832  pop     rdi
0x180004833  pop     rsi
0x180004834  pop     rbp
0x180004835  pop     rbx
0x180004836  retn
```
