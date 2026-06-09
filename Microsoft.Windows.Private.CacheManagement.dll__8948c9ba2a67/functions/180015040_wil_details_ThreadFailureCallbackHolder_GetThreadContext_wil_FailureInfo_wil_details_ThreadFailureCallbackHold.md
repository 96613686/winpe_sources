# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180015040`
- end: `0x180015196`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `342`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180015040`
- `0x1800151a0`

## callees

- `0x180015040`
- `0x18001cf40`
- `0x18001d600`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180015174`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180015174`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180015126`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180015168`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180015126`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180015168`

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
0x180015040  mov     [rsp+arg_0], rbx
0x180015045  mov     [rsp+arg_8], rbp
0x18001504a  mov     [rsp+arg_10], rsi
0x18001504f  push    rdi
0x180015050  sub     rsp, 20h
0x180015054  xor     al, al
0x180015056  mov     byte ptr [r8], 0
0x18001505a  mov     rbp, r9
0x18001505d  mov     rbx, r8
0x180015060  mov     rdi, rdx
0x180015063  mov     rsi, rcx
0x180015066  test    rdx, rdx
0x180015069  jz      loc_180015181
0x18001506f  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180015073  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180015078  mov     rdi, [rdi+20h]
0x18001507c  test    rdi, rdi
0x18001507f  jz      loc_180015181
0x180015085  cmp     dword ptr [rdi], 0
0x180015088  jnz     short loc_18001509B
0x18001508a  mov     eax, 1
0x18001508f  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180015097  inc     eax
0x180015099  mov     [rdi], eax
0x18001509b  cmp     dword ptr [rsi+50h], 0
0x18001509f  jnz     short loc_1800150B2
0x1800150a1  movups  xmm0, xmmword ptr [rdi]
0x1800150a4  movups  xmmword ptr [rsi+50h], xmm0
0x1800150a8  movsd   xmm1, qword ptr [rdi+10h]
0x1800150ad  movsd   qword ptr [rsi+60h], xmm1
0x1800150b2  movups  xmm0, xmmword ptr [rdi]
0x1800150b5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800150bc  add     rbp, rbx
0x1800150bf  mov     rax, rcx
0x1800150c2  movups  xmmword ptr [rsi+68h], xmm0
0x1800150c6  movsd   xmm1, qword ptr [rdi+10h]
0x1800150cb  movsd   qword ptr [rsi+78h], xmm1
0x1800150d0  inc     rax
0x1800150d3  cmp     byte ptr [rbx+rax], 0
0x1800150d7  jnz     short loc_1800150D0
0x1800150d9  add     rbx, rax
0x1800150dc  mov     rax, rbp
0x1800150df  sub     rax, rbx
0x1800150e2  cmp     rax, 2
0x1800150e6  jle     loc_18001517F
0x1800150ec  mov     byte ptr [rbx], 5Ch ; '\'
0x1800150ef  inc     rbx
0x1800150f2  mov     rdi, [rdi+8]
0x1800150f6  nop     word ptr [rax+rax+00000000h]
0x180015100  cmp     byte ptr [rdi+rcx+1], 0
0x180015105  lea     rcx, [rcx+1]
0x180015109  jnz     short loc_180015100
0x18001510b  sub     rbp, rbx
0x18001510e  lea     rax, [rcx+1]
0x180015112  cmp     rax, rbp
0x180015115  mov     rsi, rbp
0x180015118  cmovb   rsi, rax
0x18001511c  test    rsi, rsi
0x18001511f  jz      short loc_18001517A
0x180015121  test    rbx, rbx
0x180015124  jnz     short loc_180015134
0x180015126  call    cs:__imp__errno
0x18001512c  mov     dword ptr [rax], 16h
0x180015132  jmp     short loc_180015174
0x180015134  test    rdi, rdi
0x180015137  jz      short loc_180015151
0x180015139  cmp     rbp, rsi
0x18001513c  jb      short loc_180015151
0x18001513e  lfence
0x180015141  mov     r8, rsi; Size
0x180015144  mov     rdx, rdi; Src
0x180015147  mov     rcx, rbx; void *
0x18001514a  call    memmove
0x18001514f  jmp     short loc_18001517A
0x180015151  mov     r8, rbp; Size
0x180015154  xor     edx, edx; Val
0x180015156  mov     rcx, rbx; void *
0x180015159  call    memset
0x18001515e  test    rdi, rdi
0x180015161  jz      short loc_180015126
0x180015163  cmp     rbp, rsi
0x180015166  jnb     short loc_18001517A
0x180015168  call    cs:__imp__errno
0x18001516e  mov     dword ptr [rax], 22h ; '"'
0x180015174  call    cs:__imp__invalid_parameter_noinfo
0x18001517a  mov     byte ptr [rsi+rbx-1], 0
0x18001517f  mov     al, 1
0x180015181  mov     rbx, [rsp+28h+arg_0]
0x180015186  mov     rbp, [rsp+28h+arg_8]
0x18001518b  mov     rsi, [rsp+28h+arg_10]
0x180015190  add     rsp, 20h
0x180015194  pop     rdi
0x180015195  retn
```
