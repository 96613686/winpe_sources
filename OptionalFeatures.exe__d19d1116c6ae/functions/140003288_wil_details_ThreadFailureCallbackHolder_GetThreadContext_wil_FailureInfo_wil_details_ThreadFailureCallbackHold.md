# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140003288`
- end: `0x140003365`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140002b90`
- `0x140003288`

## callees

- `0x140003288`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000334f`
- `msvcrt!memcpy_s` at `0x14000334f`

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
0x140003288  push    rbx
0x14000328a  push    rbp
0x14000328b  push    rsi
0x14000328c  push    rdi
0x14000328d  sub     rsp, 28h
0x140003291  xor     al, al
0x140003293  mov     byte ptr [r8], 0
0x140003297  mov     rbp, r9
0x14000329a  mov     rdi, r8
0x14000329d  mov     rsi, rdx
0x1400032a0  mov     rbx, rcx
0x1400032a3  test    rdx, rdx
0x1400032a6  jz      loc_14000335C
0x1400032ac  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x1400032b0  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1400032b5  mov     rdx, [rsi+20h]
0x1400032b9  test    rdx, rdx
0x1400032bc  jz      loc_14000335C
0x1400032c2  cmp     dword ptr [rdx], 0
0x1400032c5  jnz     short loc_1400032D8
0x1400032c7  mov     eax, 1
0x1400032cc  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x1400032d4  inc     eax
0x1400032d6  mov     [rdx], eax
0x1400032d8  cmp     dword ptr [rbx+50h], 0
0x1400032dc  jnz     short loc_1400032EF
0x1400032de  movups  xmm0, xmmword ptr [rdx]
0x1400032e1  movups  xmmword ptr [rbx+50h], xmm0
0x1400032e5  movsd   xmm1, qword ptr [rdx+10h]
0x1400032ea  movsd   qword ptr [rbx+60h], xmm1
0x1400032ef  movups  xmm0, xmmword ptr [rdx]
0x1400032f2  lea     r10, [rdi+rbp]
0x1400032f6  movups  xmmword ptr [rbx+68h], xmm0
0x1400032fa  movsd   xmm1, qword ptr [rdx+10h]
0x1400032ff  movsd   qword ptr [rbx+78h], xmm1
0x140003304  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140003308  mov     rax, rbx
0x14000330b  inc     rax
0x14000330e  cmp     byte ptr [rdi+rax], 0
0x140003312  jnz     short loc_14000330B
0x140003314  lea     rcx, [rax+rdi]
0x140003318  mov     rax, r10
0x14000331b  sub     rax, rcx
0x14000331e  cmp     rax, 2
0x140003322  jle     short loc_14000335A
0x140003324  mov     byte ptr [rcx], 5Ch ; '\'
0x140003327  lea     rdi, [rcx+1]
0x14000332b  mov     r8, [rdx+8]; Source
0x14000332f  inc     rbx
0x140003332  cmp     byte ptr [r8+rbx], 0
0x140003337  jnz     short loc_14000332F
0x140003339  sub     r10, rdi
0x14000333c  inc     rbx
0x14000333f  cmp     rbx, r10
0x140003342  mov     rdx, r10; DestinationSize
0x140003345  mov     rcx, rdi; Destination
0x140003348  cmovnb  rbx, r10
0x14000334c  mov     r9, rbx; SourceSize
0x14000334f  call    cs:__imp_memcpy_s
0x140003355  mov     byte ptr [rbx+rdi-1], 0
0x14000335a  mov     al, 1
0x14000335c  add     rsp, 28h
0x140003360  pop     rdi
0x140003361  pop     rsi
0x140003362  pop     rbp
0x140003363  pop     rbx
0x140003364  retn
```
