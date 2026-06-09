# VsmmHvpControlGpaAccessTrackingQueryHv

- ea: `0x1400d43c4`
- end: `0x1400d4600`
- name: `VsmmHvpControlGpaAccessTrackingQueryHv`
- size: `572`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400d3d48`

## callees

- `0x140021c60`
- `0x140021e00`
- `0x14002f724`
- `0x140079dfc`
- `0x1400d43c4`

## import_xrefs

- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400d4551`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400d4551`
- `winhvr!WinHvGetGpaRangesAccessState` at `0x1400d44af`
- `winhvr!WinHvGetGpaRangesAccessState` at `0x1400d44af`

## string_xrefs

- `0x1400d44d1`: `VsmmHvpControlGpaAccessTrackingQueryHv`
- `0x1400d458d`: `VsmmHvpControlGpaAccessTrackingQueryHv`

## pseudocode

```c
__int64 __fastcall VsmmHvpControlGpaAccessTrackingQueryHv(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned __int64 a4,
        __int64 a5,
        _QWORD *a6,
        unsigned int a7)
{
  __int64 v8; // r10
  _QWORD *v9; // r15
  char *v10; // r12
  unsigned __int8 v11; // di
  unsigned __int64 v12; // rbx
  unsigned __int64 v13; // r14
  int GpaRangesAccessState; // eax
  unsigned int v15; // esi
  __int64 v16; // rcx
  __int64 v17; // r15
  unsigned __int64 v18; // rsi
  unsigned int v20; // [rsp+44h] [rbp-2C4h]
  __int64 v21; // [rsp+48h] [rbp-2C0h]
  __int64 v22; // [rsp+50h] [rbp-2B8h]
  __int64 v23; // [rsp+58h] [rbp-2B0h] BYREF
  __int64 v24; // [rsp+60h] [rbp-2A8h]
  __int64 v25; // [rsp+68h] [rbp-2A0h]
  char *v26; // [rsp+70h] [rbp-298h]
  signed __int64 Src[8]; // [rsp+80h] [rbp-288h] BYREF
  _BYTE v28[512]; // [rsp+C0h] [rbp-248h] BYREF

  v20 = a3;
  v22 = a2;
  v8 = a1;
  v25 = a1;
  v9 = a6;
  v24 = (__int64)a6;
  v23 = 0;
  v10 = *(char **)(a5 + 8);
  v21 = 0;
  v11 = 0;
  if ( (a7 & 2) != 0 )
    v11 = ((a7 & 1) != 0) + 1;
  if ( a3 )
  {
    v12 = 0;
    if ( (a7 & 4) != 0 )
      v12 = 5;
  }
  else if ( (a7 & 1) != 0 )
  {
    v12 = a7 & 0xC;
  }
  else
  {
    v12 = ((unsigned __int64)a7 >> 2) & 3;
  }
  while ( a4 )
  {
    v13 = a4;
    if ( a4 > 0x200 )
      v13 = 512;
    GpaRangesAccessState = WinHvGetGpaRangesAccessState(*(_QWORD *)(v8 + 648), v12, a2, a3, v13, v28, &v23);
    v15 = GpaRangesAccessState;
    if ( GpaRangesAccessState < 0 )
    {
      VidTraceErrorStatusInternal0(
        "VsmmHvpControlGpaAccessTrackingQueryHv",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmhv.c",
        2345,
        (unsigned int)GpaRangesAccessState);
      return v15;
    }
    if ( (a7 & 2) != 0 )
    {
      memset(Src, 0, sizeof(Src));
      v16 = 0;
      v17 = v21;
      do
      {
        if ( (v11 & v28[v16]) != 0 )
        {
          _bittestandset64(Src, (unsigned int)v16);
          ++v17;
        }
        v16 = (unsigned int)(v16 + 1);
      }
      while ( (unsigned int)v16 < v13 );
      v21 = v17;
      v9 = (_QWORD *)v24;
      v18 = 8 * ((v13 + 63) >> 6);
      if ( v18 && ((unsigned __int8)v10 & 7) != 0 )
        ExRaiseDatatypeMisalignment();
      RtlCopyToUser(v10, Src, 8 * ((v13 + 63) >> 6));
      v10 += v18;
      v26 = v10;
    }
    a3 = v20;
    a2 = (v13 << (9 * (unsigned __int8)v20)) + v22;
    v22 = a2;
    a4 -= v13;
    v8 = v25;
  }
  if ( (a7 & 2) != 0 && v9 )
    *v9 += v21;
  return 0;
}

```

## disassembly

```asm
0x1400d43c4  push    rbx
0x1400d43c6  push    rsi
0x1400d43c7  push    rdi
0x1400d43c8  push    r12
0x1400d43ca  push    r13
0x1400d43cc  push    r14
0x1400d43ce  push    r15
0x1400d43d0  sub     rsp, 2D0h
0x1400d43d7  mov     rax, cs:__security_cookie
0x1400d43de  xor     rax, rsp
0x1400d43e1  mov     [rsp+308h+var_48], rax
0x1400d43e9  mov     r13, r9
0x1400d43ec  mov     [rsp+308h+var_2C4], r8d
0x1400d43f1  mov     [rsp+308h+var_2B8], rdx
0x1400d43f6  mov     r10, rcx
0x1400d43f9  mov     [rsp+308h+var_2A0], rcx
0x1400d43fe  mov     rax, [rsp+308h+arg_20]
0x1400d4406  mov     r15, [rsp+308h+arg_28]
0x1400d440e  mov     [rsp+308h+var_2A8], r15
0x1400d4413  mov     [rsp+308h+var_2B0], 0
0x1400d441c  mov     r12, [rax+8]
0x1400d4420  mov     [rsp+308h+var_2C0], 0
0x1400d4429  xor     dil, dil
0x1400d442c  mov     eax, [rsp+308h+arg_30]
0x1400d4433  mov     ecx, eax
0x1400d4435  and     ecx, 2
0x1400d4438  mov     [rsp+308h+var_2C8], ecx
0x1400d443c  jz      short loc_1400D4447
0x1400d443e  test    al, 1
0x1400d4440  setnz   dil
0x1400d4444  inc     dil
0x1400d4447  test    r8d, r8d
0x1400d444a  jnz     short loc_1400D4461
0x1400d444c  mov     rbx, rax
0x1400d444f  test    al, 1
0x1400d4451  jnz     short loc_1400D445C
0x1400d4453  shr     rbx, 2
0x1400d4457  and     ebx, 3
0x1400d445a  jmp     short loc_1400D446B
0x1400d445c  and     ebx, 0Ch
0x1400d445f  jmp     short loc_1400D446B
0x1400d4461  xor     ebx, ebx
0x1400d4463  test    al, 4
0x1400d4465  lea     eax, [rbx+5]
0x1400d4468  cmovnz  ebx, eax
0x1400d446b  mov     eax, 200h
0x1400d4470  test    r13, r13
0x1400d4473  jz      loc_1400D45C4
0x1400d4479  mov     r14, r13
0x1400d447c  cmp     r13, rax
0x1400d447f  cmova   r14, rax
0x1400d4483  lea     rax, [rsp+308h+var_2B0]
0x1400d4488  mov     [rsp+308h+var_2D8], rax
0x1400d448d  lea     rax, [rsp+308h+var_248]
0x1400d4495  mov     [rsp+308h+var_2E0], rax
0x1400d449a  mov     [rsp+308h+var_2E8], r14
0x1400d449f  mov     r9d, r8d
0x1400d44a2  mov     r8, rdx
0x1400d44a5  mov     rdx, rbx
0x1400d44a8  mov     rcx, [r10+288h]
0x1400d44af  call    cs:__imp_WinHvGetGpaRangesAccessState
0x1400d44b6  nop     dword ptr [rax+rax+00h]
0x1400d44bb  mov     esi, eax
0x1400d44bd  test    eax, eax
0x1400d44bf  jns     short loc_1400D44E2
0x1400d44c1  mov     r9d, eax
0x1400d44c4  mov     r8d, 929h
0x1400d44ca  lea     rdx, aOnecoreVmVidSy_37; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhv.c"
0x1400d44d1  lea     rcx, aVsmmhvpcontrol; "VsmmHvpControlGpaAccessTrackingQueryHv"
0x1400d44d8  call    VidTraceErrorStatusInternal0
0x1400d44dd  jmp     loc_1400D45DA
0x1400d44e2  cmp     [rsp+308h+var_2C8], 0
0x1400d44e7  jz      loc_1400D459B
0x1400d44ed  xor     edx, edx; Val
0x1400d44ef  lea     r8d, [rdx+40h]; Size
0x1400d44f3  lea     rcx, [rsp+308h+Src]; void *
0x1400d44fb  call    memset
0x1400d4500  xor     ecx, ecx
0x1400d4502  test    r14, r14
0x1400d4505  jz      short loc_1400D453A
0x1400d4507  mov     r15, [rsp+308h+var_2C0]
0x1400d450c  mov     edx, ecx
0x1400d450e  test    [rsp+rcx+308h+var_248], dil
0x1400d4516  jz      short loc_1400D4527
0x1400d4518  lea     rax, [rsp+308h+Src]
0x1400d4520  bts     [rax], rdx
0x1400d4524  inc     r15
0x1400d4527  inc     ecx
0x1400d4529  mov     eax, ecx
0x1400d452b  cmp     rax, r14
0x1400d452e  jb      short loc_1400D450C
0x1400d4530  mov     [rsp+308h+var_2C0], r15
0x1400d4535  mov     r15, [rsp+308h+var_2A8]
0x1400d453a  lea     rsi, [r14+3Fh]
0x1400d453e  shr     rsi, 6
0x1400d4542  shl     rsi, 3
0x1400d4546  test    rsi, rsi
0x1400d4549  jz      short loc_1400D455E
0x1400d454b  test    r12b, 7
0x1400d454f  jz      short loc_1400D455E
0x1400d4551  call    cs:__imp_ExRaiseDatatypeMisalignment
0x1400d4558  nop     dword ptr [rax+rax+00h]
0x1400d455d  int     3; Trap to Debugger
0x1400d455e  mov     r8, rsi; Size
0x1400d4561  lea     rdx, [rsp+308h+Src]; Src
0x1400d4569  mov     rcx, r12; void *
0x1400d456c  call    RtlCopyToUser
0x1400d4571  add     r12, rsi
0x1400d4574  mov     [rsp+308h+var_298], r12
0x1400d4579  jmp     short loc_1400D459B
0x1400d457b  mov     esi, eax
0x1400d457d  mov     r9d, eax
0x1400d4580  mov     r8d, 94Bh
0x1400d4586  lea     rdx, aOnecoreVmVidSy_37; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhv.c"
0x1400d458d  lea     rcx, aVsmmhvpcontrol; "VsmmHvpControlGpaAccessTrackingQueryHv"
0x1400d4594  call    VidTraceErrorStatusInternal0
0x1400d4599  jmp     short loc_1400D45DA
0x1400d459b  mov     r8d, [rsp+308h+var_2C4]
0x1400d45a0  lea     ecx, [r8+r8*8]
0x1400d45a4  mov     rax, r14
0x1400d45a7  shl     rax, cl
0x1400d45aa  mov     rdx, [rsp+308h+var_2B8]
0x1400d45af  add     rdx, rax
0x1400d45b2  mov     [rsp+308h+var_2B8], rdx
0x1400d45b7  sub     r13, r14
0x1400d45ba  mov     r10, [rsp+308h+var_2A0]
0x1400d45bf  jmp     loc_1400D446B
0x1400d45c4  cmp     [rsp+308h+var_2C8], 0
0x1400d45c9  jz      short loc_1400D45D8
0x1400d45cb  test    r15, r15
0x1400d45ce  jz      short loc_1400D45D8
0x1400d45d0  mov     rax, [rsp+308h+var_2C0]
0x1400d45d5  add     [r15], rax
0x1400d45d8  xor     esi, esi
0x1400d45da  mov     eax, esi
0x1400d45dc  mov     rcx, [rsp+308h+var_48]
0x1400d45e4  xor     rcx, rsp; StackCookie
0x1400d45e7  call    __security_check_cookie
0x1400d45ec  add     rsp, 2D0h
0x1400d45f3  pop     r15
0x1400d45f5  pop     r14
0x1400d45f7  pop     r13
0x1400d45f9  pop     r12
0x1400d45fb  pop     rdi
0x1400d45fc  pop     rsi
0x1400d45fd  pop     rbx
0x1400d45fe  retn
```
