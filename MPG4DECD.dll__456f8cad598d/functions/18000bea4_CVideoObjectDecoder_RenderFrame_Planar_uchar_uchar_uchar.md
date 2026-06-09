# CVideoObjectDecoder::RenderFrame_Planar(uchar *,uchar *,uchar *)

- ea: `0x18000bea4`
- end: `0x18000c15d`
- name: `?RenderFrame_Planar@CVideoObjectDecoder@@AEAAXPEAE00@Z`
- size: `697`
- prototype: `void __fastcall(CVideoObjectDecoder *__hidden this, unsigned __int8 *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f500`
- `0x18000fa90`
- `0x1800106c0`
- `0x180011040`

## callees

- `0x18000bea4`
- `0x180022010`

## pseudocode

```c
void __fastcall CVideoObjectDecoder::RenderFrame_Planar(
        CVideoObjectDecoder *this,
        unsigned __int8 *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  __int64 v4; // rax
  unsigned int v6; // r15d
  unsigned __int8 *v7; // rdi
  __int64 v8; // rsi
  unsigned __int8 *v9; // rcx
  unsigned __int8 *v10; // rdx
  __int64 v11; // rbp
  _DWORD *v12; // r8
  __int64 v13; // r14
  unsigned int v14; // eax
  unsigned __int8 *v15; // r13
  unsigned int v16; // ecx
  unsigned __int8 *v17; // r12
  __int64 v18; // rsi
  __int64 v19; // rdi
  unsigned __int8 *v20; // rbp
  __int64 v21; // r14
  int v22; // ecx
  int v23; // eax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  unsigned __int8 *v27; // [rsp+70h] [rbp-78h]
  __int64 v28; // [rsp+78h] [rbp-70h]
  __int64 v29; // [rsp+80h] [rbp-68h]
  __int64 v30; // [rsp+88h] [rbp-60h]
  __int64 v31; // [rsp+98h] [rbp-50h]
  unsigned int v32; // [rsp+F0h] [rbp+8h]
  _DWORD *v33; // [rsp+F8h] [rbp+10h]
  unsigned __int8 *v34; // [rsp+100h] [rbp+18h]
  unsigned __int8 *v35; // [rsp+108h] [rbp+20h]

  v4 = *((int *)this + 89);
  v6 = 0;
  v7 = &a2[*((int *)this + 88)];
  v34 = v7;
  v8 = *((_QWORD *)this + 469);
  v9 = &a3[v4];
  v10 = &a4[v4];
  v11 = v8 + *((int *)this + 360);
  v12 = (_DWORD *)*((_QWORD *)this + 24);
  v13 = v8 + *((int *)this + 356);
  v35 = v9;
  v27 = &a4[v4];
  v28 = v8;
  v29 = v11;
  v30 = v13;
  v33 = v12;
  if ( !*((_DWORD *)this + 29) )
    return;
  do
  {
    v14 = *((_DWORD *)this + 28);
    if ( !v14 )
      goto LABEL_19;
    v31 = v8;
    v15 = v9;
    v16 = 0;
    v17 = v7;
    v18 = v11;
    v32 = 0;
    v19 = v13;
    v20 = v10;
    v21 = v31;
    do
    {
      if ( !*v12 || *((_DWORD *)this + 341) )
      {
        if ( *((_DWORD *)this + 72) )
        {
LABEL_7:
          (*((void (__fastcall **)(__int64, __int64, __int64, unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, _DWORD, _DWORD, _DWORD, _DWORD))this
           + 191))(
            v21,
            v18,
            v19,
            v17,
            v15,
            v20,
            *((_DWORD *)this + 84),
            *((_DWORD *)this + 85),
            *((_DWORD *)this + 342),
            *((_DWORD *)this + 364));
LABEL_16:
          v16 = v32;
          goto LABEL_17;
        }
        if ( v16 == v14 - 1 )
        {
          v22 = *((_DWORD *)this + 66) - *((_DWORD *)this + 73) + 16;
        }
        else
        {
          if ( v6 != *((_DWORD *)this + 29) - 1 )
            goto LABEL_7;
          v22 = 16;
        }
        if ( v6 == *((_DWORD *)this + 29) - 1 )
          v23 = *((_DWORD *)this + 67) - *((_DWORD *)this + 75) + 16;
        else
          v23 = 16;
        (*((void (__fastcall **)(__int64, __int64, __int64, unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, _DWORD, _DWORD, _DWORD, _DWORD, int, int))this
         + 192))(
          v21,
          v18,
          v19,
          v17,
          v15,
          v20,
          *((_DWORD *)this + 84),
          *((_DWORD *)this + 85),
          *((_DWORD *)this + 342),
          *((_DWORD *)this + 364),
          v22,
          v23);
        goto LABEL_16;
      }
LABEL_17:
      ++v16;
      v33 += 18;
      v21 += *((int *)this + 345);
      v24 = *((int *)this + 366);
      v17 += 16;
      v12 = v33;
      v18 += v24;
      v19 += v24;
      v32 = v16;
      v14 = *((_DWORD *)this + 28);
      v15 += 8;
      v20 += 8;
    }
    while ( v16 < v14 );
    v7 = v34;
    v8 = v28;
    v11 = v29;
    v13 = v30;
    v9 = v35;
    v10 = v27;
LABEL_19:
    ++v6;
    v7 += *((int *)this + 922);
    v25 = *((int *)this + 923);
    v9 += v25;
    v34 = v7;
    v10 += v25;
    v35 = v9;
    v8 += *((int *)this + 347);
    v27 = v10;
    v26 = *((int *)this + 367);
    v11 += v26;
    v28 = v8;
    v13 += v26;
    v29 = v11;
    v30 = v13;
  }
  while ( v6 < *((_DWORD *)this + 29) );
}

```

## disassembly

```asm
0x18000bea4  push    rbx
0x18000bea6  push    rbp
0x18000bea7  push    rsi
0x18000bea8  push    rdi
0x18000bea9  push    r12
0x18000beab  push    r13
0x18000bead  push    r14
0x18000beaf  push    r15
0x18000beb1  sub     rsp, 0A8h
0x18000beb8  movsxd  rax, dword ptr [rcx+164h]
0x18000bebf  mov     rbx, rcx
0x18000bec2  movsxd  rdi, dword ptr [rcx+160h]
0x18000bec9  xor     r15d, r15d
0x18000becc  add     rdi, rdx
0x18000becf  mov     [rsp+0E8h+arg_10], rdi
0x18000bed7  mov     rsi, [rbx+0EA8h]
0x18000bede  lea     rcx, [rax+r8]
0x18000bee2  movsxd  rbp, dword ptr [rbx+5A0h]
0x18000bee9  lea     rdx, [rax+r9]
0x18000beed  movsxd  r14, dword ptr [rbx+590h]
0x18000bef4  add     rbp, rsi
0x18000bef7  mov     r8, [rbx+0C0h]
0x18000befe  add     r14, rsi
0x18000bf01  mov     [rsp+0E8h+arg_18], rcx
0x18000bf09  mov     [rsp+0E8h+var_78], rdx
0x18000bf0e  mov     [rsp+0E8h+var_70], rsi
0x18000bf13  mov     [rsp+0E8h+var_68], rbp
0x18000bf1b  mov     [rsp+0E8h+var_60], r14
0x18000bf23  mov     [rsp+0E8h+arg_8], r8
0x18000bf2b  cmp     [rbx+74h], r15d
0x18000bf2f  jbe     loc_18000C149
0x18000bf35  mov     eax, [rbx+70h]
0x18000bf38  test    eax, eax
0x18000bf3a  jz      loc_18000C0E4
0x18000bf40  mov     [rsp+0E8h+var_50], rsi
0x18000bf48  mov     r13, rcx
0x18000bf4b  xor     ecx, ecx
0x18000bf4d  mov     r12, rdi
0x18000bf50  mov     rsi, rbp
0x18000bf53  mov     [rsp+0E8h+arg_0], ecx
0x18000bf5a  mov     rdi, r14
0x18000bf5d  mov     rbp, rdx
0x18000bf60  mov     r14, [rsp+0E8h+var_50]
0x18000bf68  cmp     dword ptr [r8], 0
0x18000bf6c  jz      short loc_18000BF7B
0x18000bf6e  cmp     dword ptr [rbx+554h], 0
0x18000bf75  jz      loc_18000C072
0x18000bf7b  cmp     dword ptr [rbx+120h], 0
0x18000bf82  jz      short loc_18000BFD3
0x18000bf84  mov     ecx, [rbx+5B0h]
0x18000bf8a  mov     r9, r12
0x18000bf8d  mov     rax, [rbx+5F8h]
0x18000bf94  mov     r8, rdi
0x18000bf97  mov     [rsp+0E8h+var_A0], ecx
0x18000bf9b  mov     rdx, rsi
0x18000bf9e  mov     ecx, [rbx+558h]
0x18000bfa4  mov     [rsp+0E8h+var_A8], ecx
0x18000bfa8  mov     ecx, [rbx+154h]
0x18000bfae  mov     [rsp+0E8h+var_B0], ecx
0x18000bfb2  mov     ecx, [rbx+150h]
0x18000bfb8  mov     [rsp+0E8h+var_B8], ecx
0x18000bfbc  mov     rcx, r14
0x18000bfbf  mov     [rsp+0E8h+var_C0], rbp
0x18000bfc4  mov     [rsp+0E8h+var_C8], r13
0x18000bfc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfce  jmp     loc_18000C06B
0x18000bfd3  dec     eax
0x18000bfd5  cmp     ecx, eax
0x18000bfd7  jz      short loc_18000BFEA
0x18000bfd9  mov     eax, [rbx+74h]
0x18000bfdc  dec     eax
0x18000bfde  cmp     r15d, eax
0x18000bfe1  jnz     short loc_18000BF84
0x18000bfe3  mov     ecx, 10h
0x18000bfe8  jmp     short loc_18000BFF9
0x18000bfea  mov     ecx, [rbx+108h]
0x18000bff0  sub     ecx, [rbx+124h]
0x18000bff6  add     ecx, 10h
0x18000bff9  mov     eax, [rbx+74h]
0x18000bffc  dec     eax
0x18000bffe  cmp     r15d, eax
0x18000c001  jz      short loc_18000C00A
0x18000c003  mov     eax, 10h
0x18000c008  jmp     short loc_18000C019
0x18000c00a  mov     eax, [rbx+10Ch]
0x18000c010  sub     eax, [rbx+12Ch]
0x18000c016  add     eax, 10h
0x18000c019  mov     [rsp+0E8h+var_90], eax
0x18000c01d  mov     r9, r12
0x18000c020  mov     rax, [rbx+600h]
0x18000c027  mov     r8, rdi
0x18000c02a  mov     [rsp+0E8h+var_98], ecx
0x18000c02e  mov     rdx, rsi
0x18000c031  mov     ecx, [rbx+5B0h]
0x18000c037  mov     [rsp+0E8h+var_A0], ecx
0x18000c03b  mov     ecx, [rbx+558h]
0x18000c041  mov     [rsp+0E8h+var_A8], ecx
0x18000c045  mov     ecx, [rbx+154h]
0x18000c04b  mov     [rsp+0E8h+var_B0], ecx
0x18000c04f  mov     ecx, [rbx+150h]
0x18000c055  mov     [rsp+0E8h+var_B8], ecx
0x18000c059  mov     rcx, r14
0x18000c05c  mov     [rsp+0E8h+var_C0], rbp
0x18000c061  mov     [rsp+0E8h+var_C8], r13
0x18000c066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c06b  mov     ecx, [rsp+0E8h+arg_0]
0x18000c072  movsxd  rax, dword ptr [rbx+564h]
0x18000c079  inc     ecx
0x18000c07b  add     [rsp+0E8h+arg_8], 48h ; 'H'
0x18000c084  add     r14, rax
0x18000c087  movsxd  rax, dword ptr [rbx+5B8h]
0x18000c08e  add     r12, 10h
0x18000c092  mov     r8, [rsp+0E8h+arg_8]
0x18000c09a  add     rsi, rax
0x18000c09d  add     rdi, rax
0x18000c0a0  mov     [rsp+0E8h+arg_0], ecx
0x18000c0a7  mov     eax, [rbx+70h]
0x18000c0aa  add     r13, 8
0x18000c0ae  add     rbp, 8
0x18000c0b2  cmp     ecx, eax
0x18000c0b4  jb      loc_18000BF68
0x18000c0ba  mov     rdi, [rsp+0E8h+arg_10]
0x18000c0c2  mov     rsi, [rsp+0E8h+var_70]
0x18000c0c7  mov     rbp, [rsp+0E8h+var_68]
0x18000c0cf  mov     r14, [rsp+0E8h+var_60]
0x18000c0d7  mov     rcx, [rsp+0E8h+arg_18]
0x18000c0df  mov     rdx, [rsp+0E8h+var_78]
0x18000c0e4  movsxd  rax, dword ptr [rbx+0E68h]
0x18000c0eb  inc     r15d
0x18000c0ee  add     rdi, rax
0x18000c0f1  movsxd  rax, dword ptr [rbx+0E6Ch]
0x18000c0f8  add     rcx, rax
0x18000c0fb  mov     [rsp+0E8h+arg_10], rdi
0x18000c103  add     rdx, rax
0x18000c106  mov     [rsp+0E8h+arg_18], rcx
0x18000c10e  movsxd  rax, dword ptr [rbx+56Ch]
0x18000c115  add     rsi, rax
0x18000c118  mov     [rsp+0E8h+var_78], rdx
0x18000c11d  movsxd  rax, dword ptr [rbx+5BCh]
0x18000c124  add     rbp, rax
0x18000c127  mov     [rsp+0E8h+var_70], rsi
0x18000c12c  add     r14, rax
0x18000c12f  mov     [rsp+0E8h+var_68], rbp
0x18000c137  mov     [rsp+0E8h+var_60], r14
0x18000c13f  cmp     r15d, [rbx+74h]
0x18000c143  jb      loc_18000BF35
0x18000c149  add     rsp, 0A8h
0x18000c150  pop     r15
0x18000c152  pop     r14
0x18000c154  pop     r13
0x18000c156  pop     r12
0x18000c158  pop     rdi
0x18000c159  pop     rsi
0x18000c15a  pop     rbp
0x18000c15b  pop     rbx
0x18000c15c  retn
```
