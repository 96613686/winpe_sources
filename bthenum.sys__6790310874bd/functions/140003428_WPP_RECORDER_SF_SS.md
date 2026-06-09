# WPP_RECORDER_SF_SS

- ea: `0x140003428`
- end: `0x140003596`
- name: `WPP_RECORDER_SF_SS`
- size: `366`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001e1e0`
- `0x14001ec38`

## callees

- `0x140003428`
- `0x140007d40`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140003578`
- `WppRecorder!WppAutoLogTrace` at `0x140003578`

## pseudocode

```c
__int64 __fastcall WPP_RECORDER_SF_SS(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 a4,
        int a5,
        const char *a6,
        const char *a7)
{
  const char *v7; // rbx
  __int64 v8; // rsi
  const char *v9; // rdi
  __int64 v12; // rbp
  __int64 v13; // rax
  const char *v14; // rdx
  __int64 v15; // rax
  __int64 v16; // r8
  const char *v17; // rcx
  __int64 v18; // rax
  bool v19; // zf
  int v21; // [rsp+20h] [rbp-78h]

  v7 = a7;
  v8 = -1;
  v9 = a6;
  v12 = 10;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
  {
    if ( a7 )
    {
      v13 = -1;
      do
        ++v13;
      while ( *(_WORD *)&a7[2 * v13] );
    }
    v14 = a7;
    if ( !a7 )
      v14 = L"NULL";
    if ( a6 )
    {
      v15 = -1;
      do
        ++v15;
      while ( *(_WORD *)&a6[2 * v15] );
      v16 = 2 * v15 + 2;
    }
    else
    {
      v16 = 10;
    }
    v17 = a6;
    if ( !a6 )
      v17 = L"NULL";
    pfnWppTraceMessage(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids,
      a4,
      v17,
      v16,
      v14);
  }
  if ( a7 )
  {
    v18 = -1;
    do
      ++v18;
    while ( *(_WORD *)&a7[2 * v18] );
  }
  if ( !a7 )
    v7 = L"NULL";
  v19 = a6 == 0;
  if ( a6 )
  {
    do
      ++v8;
    while ( *(_WORD *)&a6[2 * v8] );
    v12 = 2 * v8 + 2;
    v19 = a6 == 0;
  }
  if ( v19 )
    v9 = L"NULL";
  LOWORD(v21) = a4;
  return WppAutoLogTrace(a1, 0, 4, WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids, v21, v9, v12, v7);
}

```

## disassembly

```asm
0x140003428  push    rbx
0x14000342a  push    rbp
0x14000342b  push    rsi
0x14000342c  push    rdi
0x14000342d  push    r12
0x14000342f  push    r13
0x140003431  push    r14
0x140003433  push    r15
0x140003435  sub     rsp, 58h
0x140003439  mov     rax, cs:WPP_GLOBAL_Control
0x140003440  lea     r13, aNull_0; "NULL"
0x140003447  mov     rbx, [rsp+98h+arg_30]
0x14000344f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140003453  mov     rdi, [rsp+98h+arg_28]
0x14000345b  xor     r12d, r12d
0x14000345e  movzx   r14d, r9w
0x140003462  mov     r15, rcx
0x140003465  mov     edx, [rax+2Ch]
0x140003468  lea     ebp, [rsi+0Bh]
0x14000346b  test    dl, 8
0x14000346e  jz      loc_140003505
0x140003474  test    rbx, rbx
0x140003477  jz      short loc_140003490
0x140003479  mov     rax, rsi
0x14000347c  inc     rax
0x14000347f  cmp     [rbx+rax*2], r12w
0x140003484  jnz     short loc_14000347C
0x140003486  lea     r9, ds:2[rax*2]
0x14000348e  jmp     short loc_140003493
0x140003490  mov     r9, rbp
0x140003493  test    rbx, rbx
0x140003496  mov     rdx, rbx
0x140003499  cmovz   rdx, r13
0x14000349d  test    rdi, rdi
0x1400034a0  jz      short loc_1400034B9
0x1400034a2  mov     rax, rsi
0x1400034a5  inc     rax
0x1400034a8  cmp     [rdi+rax*2], r12w
0x1400034ad  jnz     short loc_1400034A5
0x1400034af  lea     r8, ds:2[rax*2]
0x1400034b7  jmp     short loc_1400034BC
0x1400034b9  mov     r8, rbp
0x1400034bc  mov     rax, cs:pfnWppTraceMessage
0x1400034c3  test    rdi, rdi
0x1400034c6  mov     [rsp+98h+var_58], r12
0x1400034cb  mov     rcx, rdi
0x1400034ce  mov     [rsp+98h+var_60], r9
0x1400034d3  cmovz   rcx, r13
0x1400034d7  mov     [rsp+98h+var_68], rdx
0x1400034dc  mov     r9d, r14d
0x1400034df  mov     [rsp+98h+var_70], r8
0x1400034e4  mov     edx, 2Bh ; '+'
0x1400034e9  mov     [rsp+98h+var_78], rcx
0x1400034ee  lea     r8, WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids
0x1400034f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400034fc  mov     rcx, [rcx+18h]
0x140003500  call    _guard_dispatch_icall
0x140003505  test    rbx, rbx
0x140003508  jz      short loc_140003521
0x14000350a  mov     rax, rsi
0x14000350d  inc     rax
0x140003510  cmp     [rbx+rax*2], r12w
0x140003515  jnz     short loc_14000350D
0x140003517  lea     rax, ds:2[rax*2]
0x14000351f  jmp     short loc_140003524
0x140003521  mov     rax, rbp
0x140003524  test    rbx, rbx
0x140003527  cmovz   rbx, r13
0x14000352b  test    rdi, rdi
0x14000352e  jz      short loc_140003545
0x140003530  inc     rsi
0x140003533  cmp     [rdi+rsi*2], r12w
0x140003538  jnz     short loc_140003530
0x14000353a  lea     rbp, ds:2[rsi*2]
0x140003542  test    rdi, rdi
0x140003545  mov     [rsp+98h+var_50], r12
0x14000354a  lea     r9, WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids
0x140003551  mov     [rsp+98h+var_58], rax
0x140003556  cmovz   rdi, r13
0x14000355a  mov     [rsp+98h+var_60], rbx
0x14000355f  xor     edx, edx
0x140003561  mov     [rsp+98h+var_68], rbp
0x140003566  mov     rcx, r15
0x140003569  mov     [rsp+98h+var_70], rdi
0x14000356e  mov     word ptr [rsp+98h+var_78], r14w
0x140003574  lea     r8d, [rdx+4]
0x140003578  call    cs:__imp_WppAutoLogTrace
0x14000357f  nop     dword ptr [rax+rax+00h]
0x140003584  add     rsp, 58h
0x140003588  pop     r15
0x14000358a  pop     r14
0x14000358c  pop     r13
0x14000358e  pop     r12
0x140003590  pop     rdi
0x140003591  pop     rsi
0x140003592  pop     rbp
0x140003593  pop     rbx
0x140003594  retn
```
