# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18002f2d0`
- end: `0x18002f426`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `342`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18002f2d0`
- `0x18002f430`

## callees

- `0x18002f2d0`
- `0x18003c020`
- `0x18003c6e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18002f3b6`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18002f3f8`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18002f3b6`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18002f3f8`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18002f404`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18002f404`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall wil::details::ThreadFailureCallbackHolder::GetThreadContext(
        struct wil::FailureInfo *a1,
        struct wil::details::ThreadFailureCallbackHolder **a2,
        char *a3,
        unsigned __int64 a4)
{
  bool result; // al
  struct wil::details::ThreadFailureCallbackHolder *v9; // rdi
  __int64 v10; // rcx
  char *v11; // rbp
  __int64 v12; // rax
  char *v13; // rbx
  _BYTE *v14; // rbx
  _BYTE *v15; // rdi
  size_t v17; // rbp
  size_t v18; // rsi

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
      v10 = -1;
      v11 = &a3[a4];
      v12 = -1;
      *(_OWORD *)((char *)a1 + 104) = *(_OWORD *)v9;
      *((_QWORD *)a1 + 15) = *((_QWORD *)v9 + 2);
      do
        ++v12;
      while ( a3[v12] );
      v13 = &a3[v12];
      if ( v11 - v13 <= 2 )
        return 1;
      *v13 = 92;
      v14 = v13 + 1;
      v15 = (_BYTE *)*((_QWORD *)v9 + 1);
      while ( v15[++v10] != 0 )
        ;
      v17 = v11 - v14;
      v18 = v17;
      if ( v10 + 1 < v17 )
        v18 = v10 + 1;
      if ( v18 )
      {
        if ( !v14 )
        {
LABEL_16:
          *_errno() = 22;
LABEL_23:
          _invalid_parameter_noinfo();
          goto LABEL_24;
        }
        if ( v15 && v17 >= v18 )
        {
          _mm_lfence();
          memmove(v14, v15, v18);
        }
        else
        {
          memset(v14, 0, v17);
          if ( !v15 )
            goto LABEL_16;
          if ( v17 < v18 )
          {
            *_errno() = 34;
            goto LABEL_23;
          }
        }
      }
LABEL_24:
      v14[v18 - 1] = 0;
      return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002f2d0  mov     [rsp+arg_0], rbx
0x18002f2d5  mov     [rsp+arg_8], rbp
0x18002f2da  mov     [rsp+arg_10], rsi
0x18002f2df  push    rdi
0x18002f2e0  sub     rsp, 20h
0x18002f2e4  xor     al, al
0x18002f2e6  mov     byte ptr [r8], 0
0x18002f2ea  mov     rbp, r9
0x18002f2ed  mov     rbx, r8
0x18002f2f0  mov     rdi, rdx
0x18002f2f3  mov     rsi, rcx
0x18002f2f6  test    rdx, rdx
0x18002f2f9  jz      loc_18002F411
0x18002f2ff  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18002f303  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18002f308  mov     rdi, [rdi+20h]
0x18002f30c  test    rdi, rdi
0x18002f30f  jz      loc_18002F411
0x18002f315  cmp     dword ptr [rdi], 0
0x18002f318  jnz     short loc_18002F32B
0x18002f31a  mov     eax, 1
0x18002f31f  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18002f327  inc     eax
0x18002f329  mov     [rdi], eax
0x18002f32b  cmp     dword ptr [rsi+50h], 0
0x18002f32f  jnz     short loc_18002F342
0x18002f331  movups  xmm0, xmmword ptr [rdi]
0x18002f334  movups  xmmword ptr [rsi+50h], xmm0
0x18002f338  movsd   xmm1, qword ptr [rdi+10h]
0x18002f33d  movsd   qword ptr [rsi+60h], xmm1
0x18002f342  movups  xmm0, xmmword ptr [rdi]
0x18002f345  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002f34c  add     rbp, rbx
0x18002f34f  mov     rax, rcx
0x18002f352  movups  xmmword ptr [rsi+68h], xmm0
0x18002f356  movsd   xmm1, qword ptr [rdi+10h]
0x18002f35b  movsd   qword ptr [rsi+78h], xmm1
0x18002f360  inc     rax
0x18002f363  cmp     byte ptr [rbx+rax], 0
0x18002f367  jnz     short loc_18002F360
0x18002f369  add     rbx, rax
0x18002f36c  mov     rax, rbp
0x18002f36f  sub     rax, rbx
0x18002f372  cmp     rax, 2
0x18002f376  jle     loc_18002F40F
0x18002f37c  mov     byte ptr [rbx], 5Ch ; '\'
0x18002f37f  inc     rbx
0x18002f382  mov     rdi, [rdi+8]
0x18002f386  nop     word ptr [rax+rax+00000000h]
0x18002f390  cmp     byte ptr [rdi+rcx+1], 0
0x18002f395  lea     rcx, [rcx+1]
0x18002f399  jnz     short loc_18002F390
0x18002f39b  sub     rbp, rbx
0x18002f39e  lea     rax, [rcx+1]
0x18002f3a2  cmp     rax, rbp
0x18002f3a5  mov     rsi, rbp
0x18002f3a8  cmovb   rsi, rax
0x18002f3ac  test    rsi, rsi
0x18002f3af  jz      short loc_18002F40A
0x18002f3b1  test    rbx, rbx
0x18002f3b4  jnz     short loc_18002F3C4
0x18002f3b6  call    cs:__imp__errno
0x18002f3bc  mov     dword ptr [rax], 16h
0x18002f3c2  jmp     short loc_18002F404
0x18002f3c4  test    rdi, rdi
0x18002f3c7  jz      short loc_18002F3E1
0x18002f3c9  cmp     rbp, rsi
0x18002f3cc  jb      short loc_18002F3E1
0x18002f3ce  lfence
0x18002f3d1  mov     r8, rsi; Size
0x18002f3d4  mov     rdx, rdi; Src
0x18002f3d7  mov     rcx, rbx; void *
0x18002f3da  call    memmove
0x18002f3df  jmp     short loc_18002F40A
0x18002f3e1  mov     r8, rbp; Size
0x18002f3e4  xor     edx, edx; Val
0x18002f3e6  mov     rcx, rbx; void *
0x18002f3e9  call    memset
0x18002f3ee  test    rdi, rdi
0x18002f3f1  jz      short loc_18002F3B6
0x18002f3f3  cmp     rbp, rsi
0x18002f3f6  jnb     short loc_18002F40A
0x18002f3f8  call    cs:__imp__errno
0x18002f3fe  mov     dword ptr [rax], 22h ; '"'
0x18002f404  call    cs:__imp__invalid_parameter_noinfo
0x18002f40a  mov     byte ptr [rsi+rbx-1], 0
0x18002f40f  mov     al, 1
0x18002f411  mov     rbx, [rsp+28h+arg_0]
0x18002f416  mov     rbp, [rsp+28h+arg_8]
0x18002f41b  mov     rsi, [rsp+28h+arg_10]
0x18002f420  add     rsp, 20h
0x18002f424  pop     rdi
0x18002f425  retn
```
