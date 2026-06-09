# McTemplateU0zzzzd_EventWriteTransfer

- ea: `0x14001326c`
- end: `0x1400133ab`
- name: `McTemplateU0zzzzd_EventWriteTransfer`
- size: `319`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a5e0`
- `0x14000d134`

## callees

- `0x140006d70`
- `0x14001326c`
- `0x14001a8d0`

## pseudocode

```c
ULONG __fastcall McTemplateU0zzzzd_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5,
        const wchar_t *a6,
        char a7)
{
  __int64 v7; // rax
  int v9; // r10d
  __int64 v10; // rcx
  int v11; // ecx
  __int64 v12; // rcx
  int v13; // ecx
  const wchar_t *v14; // rcx
  __int64 v15; // rdx
  int v16; // edx
  const wchar_t *v17; // rcx
  bool v18; // zf
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+30h] [rbp-31h] BYREF
  const wchar_t *v21; // [rsp+40h] [rbp-21h]
  int v22; // [rsp+48h] [rbp-19h]
  int v23; // [rsp+4Ch] [rbp-15h]
  const wchar_t *v24; // [rsp+50h] [rbp-11h]
  int v25; // [rsp+58h] [rbp-9h]
  int v26; // [rsp+5Ch] [rbp-5h]
  const wchar_t *v27; // [rsp+60h] [rbp-1h]
  int v28; // [rsp+68h] [rbp+7h]
  int v29; // [rsp+6Ch] [rbp+Bh]
  const wchar_t *v30; // [rsp+70h] [rbp+Fh]
  int v31; // [rsp+78h] [rbp+17h]
  int v32; // [rsp+7Ch] [rbp+1Bh]
  char *v33; // [rsp+80h] [rbp+1Fh]
  __int64 v34; // [rsp+88h] [rbp+27h]

  v7 = -1;
  v9 = 10;
  if ( a3 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a3[v10] );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v11 = 10;
  }
  v22 = v11;
  v23 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v21 = a3;
  if ( a4 )
  {
    v12 = -1;
    do
      ++v12;
    while ( a4[v12] );
    v13 = 2 * v12 + 2;
  }
  else
  {
    v13 = 10;
  }
  v25 = v13;
  v14 = a5;
  if ( !a4 )
    a4 = L"NULL";
  v26 = 0;
  v24 = a4;
  if ( a5 )
  {
    v15 = -1;
    do
      ++v15;
    while ( a5[v15] );
    v16 = 2 * v15 + 2;
  }
  else
  {
    v16 = 10;
  }
  v28 = v16;
  v29 = 0;
  if ( !a5 )
    v14 = L"NULL";
  v27 = v14;
  v17 = a6;
  v18 = a6 == 0;
  if ( a6 )
  {
    do
      ++v7;
    while ( a6[v7] );
    v9 = 2 * v7 + 2;
    v18 = a6 == 0;
  }
  v31 = v9;
  v33 = &a7;
  if ( v18 )
    v17 = L"NULL";
  v30 = v17;
  v32 = 0;
  v34 = 4;
  return McGenEventWrite_EventWriteTransfer((__int64)v17, a2, (__int64)a3, 6u, &v20);
}

```

## disassembly

```asm
0x14001326c  mov     [rsp-8+arg_0], rbx
0x140013271  mov     [rsp-8+arg_10], rdi
0x140013276  push    rbp
0x140013277  lea     rbp, [rsp-3Fh]
0x14001327c  sub     rsp, 0A0h
0x140013283  mov     rax, cs:__security_cookie
0x14001328a  xor     rax, rsp
0x14001328d  mov     [rbp+3Fh+var_10], rax
0x140013291  or      rax, 0FFFFFFFFFFFFFFFFh
0x140013295  xor     ebx, ebx
0x140013297  mov     r11, rdx
0x14001329a  mov     r10d, 0Ah
0x1400132a0  test    r8, r8
0x1400132a3  jz      short loc_1400132BB
0x1400132a5  mov     rcx, rax
0x1400132a8  inc     rcx
0x1400132ab  cmp     [r8+rcx*2], bx
0x1400132b0  jnz     short loc_1400132A8
0x1400132b2  lea     ecx, ds:2[rcx*2]
0x1400132b9  jmp     short loc_1400132BE
0x1400132bb  mov     ecx, r10d
0x1400132be  test    r8, r8
0x1400132c1  mov     [rbp+3Fh+var_58], ecx
0x1400132c4  lea     rdi, aNull; "NULL"
0x1400132cb  mov     [rbp+3Fh+var_54], ebx
0x1400132ce  cmovz   r8, rdi
0x1400132d2  mov     [rbp+3Fh+var_60], r8
0x1400132d6  test    r9, r9
0x1400132d9  jz      short loc_1400132F1
0x1400132db  mov     rcx, rax
0x1400132de  inc     rcx
0x1400132e1  cmp     [r9+rcx*2], bx
0x1400132e6  jnz     short loc_1400132DE
0x1400132e8  lea     ecx, ds:2[rcx*2]
0x1400132ef  jmp     short loc_1400132F4
0x1400132f1  mov     ecx, r10d
0x1400132f4  test    r9, r9
0x1400132f7  mov     [rbp+3Fh+var_48], ecx
0x1400132fa  mov     rcx, [rbp+3Fh+arg_20]
0x1400132fe  cmovz   r9, rdi
0x140013302  mov     [rbp+3Fh+var_44], ebx
0x140013305  mov     [rbp+3Fh+var_50], r9
0x140013309  test    rcx, rcx
0x14001330c  jz      short loc_140013323
0x14001330e  mov     rdx, rax
0x140013311  inc     rdx
0x140013314  cmp     [rcx+rdx*2], bx
0x140013318  jnz     short loc_140013311
0x14001331a  lea     edx, ds:2[rdx*2]
0x140013321  jmp     short loc_140013326
0x140013323  mov     edx, r10d
0x140013326  test    rcx, rcx
0x140013329  mov     [rbp+3Fh+var_38], edx
0x14001332c  mov     [rbp+3Fh+var_34], ebx
0x14001332f  cmovz   rcx, rdi
0x140013333  mov     [rbp+3Fh+var_40], rcx
0x140013337  mov     rcx, [rbp+3Fh+arg_28]
0x14001333b  test    rcx, rcx
0x14001333e  jz      short loc_140013354
0x140013340  inc     rax
0x140013343  cmp     [rcx+rax*2], bx
0x140013347  jnz     short loc_140013340
0x140013349  lea     r10d, ds:2[rax*2]
0x140013351  test    rcx, rcx
0x140013354  lea     rax, [rbp+3Fh+arg_30]
0x140013358  mov     [rbp+3Fh+var_28], r10d
0x14001335c  mov     [rbp+3Fh+var_20], rax
0x140013360  cmovz   rcx, rdi
0x140013364  lea     rax, [rbp+3Fh+var_70]
0x140013368  mov     [rbp+3Fh+var_30], rcx
0x14001336c  mov     r9d, 6
0x140013372  mov     [rsp+0A0h+var_80], rax
0x140013377  mov     rdx, r11
0x14001337a  mov     [rbp+3Fh+var_24], ebx
0x14001337d  mov     [rbp+3Fh+var_18], 4
0x140013385  call    McGenEventWrite_EventWriteTransfer
0x14001338a  mov     rcx, [rbp+3Fh+var_10]
0x14001338e  xor     rcx, rsp; StackCookie
0x140013391  call    __security_check_cookie
0x140013396  lea     r11, [rsp+0A0h+var_s0]
0x14001339e  mov     rbx, [r11+10h]
0x1400133a2  mov     rdi, [r11+20h]
0x1400133a6  mov     rsp, r11
0x1400133a9  pop     rbp
0x1400133aa  retn
```
