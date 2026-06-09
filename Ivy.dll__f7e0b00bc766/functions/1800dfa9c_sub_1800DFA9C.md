# sub_1800DFA9C

- ea: `0x1800dfa9c`
- end: `0x1800dff65`
- name: `sub_1800DFA9C`
- size: `1225`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x1800ec158`

## callees

- `0x180008f04`
- `0x180011ac4`
- `0x180011ae8`
- `0x180023aa8`
- `0x18003fb30`
- `0x180046090`
- `0x1800dfa9c`
- `0x1800e03b4`
- `0x1800e05e0`
- `0x1800e089c`
- `0x1800e0b48`
- `0x1800e0e18`
- `0x1800e10ac`
- `0x18016eaf0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800dfe73`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800dfe89`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800dfe9f`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800dfe73`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800dfe89`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800dfe9f`

## string_xrefs

- `0x1800dff56`: `No datapoint to cache.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall sub_1800DFA9C(__int64 a1, __int64 a2, unsigned int **a3)
{
  _QWORD *v4; // rdi
  _DWORD *v5; // r14
  _DWORD *v6; // rsi
  __int64 v7; // rbx
  __int64 v8; // rdx
  __int64 v9; // r15
  unsigned int *v10; // r12
  unsigned int *j; // rsi
  _QWORD *v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // r15
  unsigned int *v15; // r12
  unsigned int *i; // rsi
  _QWORD *v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // r15
  unsigned int *v20; // r12
  unsigned int *v21; // rdi
  int v22; // r8d
  int v23; // r9d
  __int64 v24; // rsi
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  int v28; // esi
  int *v29; // r14
  int *k; // rbx
  int v31; // r8d
  _DWORD *v32; // rdx
  int v33; // eax
  __int64 v35; // [rsp+30h] [rbp-50h] BYREF
  __int64 v36; // [rsp+38h] [rbp-48h] BYREF
  __int64 v37; // [rsp+40h] [rbp-40h] BYREF
  int *v38; // [rsp+48h] [rbp-38h] BYREF
  int *v39; // [rsp+50h] [rbp-30h] BYREF
  _QWORD *v40; // [rsp+58h] [rbp-28h]
  __int64 v41; // [rsp+60h] [rbp-20h]
  int v42; // [rsp+D0h] [rbp+50h] BYREF
  _DWORD *v43; // [rsp+D8h] [rbp+58h]

  v4 = (_QWORD *)a1;
  v40 = (_QWORD *)a1;
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  *(_QWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  *(_DWORD *)(a1 + 120) = 0;
  if ( *a3 == a3[1] )
  {
    sub_180011AE8(508646114, &qword_1801AB2B8);
    sub_180011AC4(508646114, "No datapoint to cache.");
  }
  v5 = *(_DWORD **)a2;
  v6 = *(_DWORD **)(a2 + 8);
  v43 = v6;
  if ( v5 != v6 )
  {
    while ( 1 )
    {
      v7 = *(_QWORD *)(*(_QWORD *)v5 + 48LL);
      v41 = v7;
      if ( v7 )
      {
        (**(void (__fastcall ***)(__int64))v7)(v7);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      }
      if ( *(_DWORD *)(*(_QWORD *)v5 + 56LL) != 17 )
      {
        if ( *(_DWORD *)(*(_QWORD *)v5 + 56LL) == 18 )
        {
          v13 = v4[4];
          if ( v13 == v4[5] )
          {
            ((void (*)(void))sub_1800E05E0)();
          }
          else
          {
            *(_QWORD *)v13 = 0;
            *(_QWORD *)(v13 + 8) = 0;
            *(_QWORD *)(v13 + 16) = 0;
            *(_DWORD *)(v13 + 24) = 0;
            v4[4] += 32LL;
          }
          v14 = v4[4];
          if ( v4[3] == v14 )
            invoke_watson(0, 0, 0, 0, 0);
          *(_DWORD *)(v14 - 8) = v5[2];
          v36 = 0;
          v15 = a3[1];
          for ( i = *a3; i != v15; ++i )
          {
            (*(void (__fastcall **)(__int64, _QWORD, __int64 *, __int64))(*(_QWORD *)v7 + 48LL))(v7, *i, &v36, 1);
            v17 = *(_QWORD **)(v14 - 24);
            if ( v17 == *(_QWORD **)(v14 - 16) )
            {
              sub_180023AA8(v14 - 32, v17, &v36);
            }
            else
            {
              *v17 = v36;
              *(_QWORD *)(v14 - 24) = v17 + 1;
            }
          }
        }
        else
        {
          if ( *(_DWORD *)(*(_QWORD *)v5 + 56LL) != 19 )
          {
            sub_180011AE8(508646113, &qword_1801AB2B8);
            sub_180011AC4(508646113, "Unknown rendering data dimension.");
          }
          v8 = v4[1];
          if ( v8 == v4[2] )
          {
            sub_1800E05E0(v4);
          }
          else
          {
            *(_QWORD *)v8 = 0;
            *(_QWORD *)(v8 + 8) = 0;
            *(_QWORD *)(v8 + 16) = 0;
            *(_DWORD *)(v8 + 24) = 0;
            v4[1] += 32LL;
          }
          v9 = v4[1];
          if ( *v4 == v9 )
            invoke_watson(0, 0, 0, 0, 0);
          *(_DWORD *)(v9 - 8) = v5[2];
          v35 = 0;
          v10 = a3[1];
          for ( j = *a3; j != v10; ++j )
          {
            (*(void (__fastcall **)(__int64, _QWORD, __int64 *, __int64))(*(_QWORD *)v7 + 48LL))(v7, *j, &v35, 1);
            v12 = *(_QWORD **)(v9 - 24);
            if ( v12 == *(_QWORD **)(v9 - 16) )
            {
              sub_180023AA8(v9 - 32, v12, &v35);
            }
            else
            {
              *v12 = v35;
              *(_QWORD *)(v9 - 24) = v12 + 1;
            }
          }
        }
LABEL_48:
        v6 = v43;
        goto LABEL_49;
      }
      v18 = v4[7];
      if ( v18 == v4[8] )
      {
        sub_1800E089C();
      }
      else
      {
        *(_QWORD *)v18 = 0;
        *(_QWORD *)(v18 + 8) = 0;
        *(_QWORD *)(v18 + 16) = 0;
        *(_DWORD *)(v18 + 24) = 0;
        v4[7] += 32LL;
      }
      v19 = v4[7];
      if ( v4[6] == v19 )
        invoke_watson(0, 0, 0, 0, 0);
      *(_DWORD *)(v19 - 8) = v5[2];
      v37 = 0;
      v20 = *a3;
      if ( *a3 != a3[1] )
        break;
LABEL_49:
      if ( v7 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 24LL))(v7);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
      }
      v5 += 4;
      if ( v5 == v6 )
        goto LABEL_52;
    }
    v21 = a3[1];
    while ( 1 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, __int64 *, __int64))(*(_QWORD *)v7 + 56LL))(v7, *v20, &v37, 1);
      v24 = *(_QWORD *)(v19 - 24);
      v25 = v37;
      if ( !v37 )
        break;
      LOBYTE(v42) = 0;
      v38 = &v42;
      v39 = (int *)&v37;
      if ( v24 != *(_QWORD *)(v19 - 16) )
      {
        v39 = (int *)v24;
        *(_OWORD *)v24 = 0;
        *(_QWORD *)(v24 + 16) = 0;
        *(_QWORD *)(v24 + 24) = 0;
        v26 = -1;
        do
          ++v26;
        while ( *(_WORD *)(v25 + 2 * v26) );
        sub_180008F04(v24);
LABEL_44:
        *(_BYTE *)(v24 + 32) = v42;
        *(_QWORD *)(v19 - 24) += 40LL;
        goto LABEL_46;
      }
      sub_1800E0B48(v19 - 32, v24, v22, (unsigned int)&v39, (__int64)&v38);
LABEL_46:
      if ( ++v20 == v21 )
      {
        v4 = v40;
        goto LABEL_48;
      }
    }
    LOBYTE(v42) = 1;
    v39 = &v42;
    if ( v24 == *(_QWORD *)(v19 - 16) )
    {
      sub_1800E0E18(v19 - 32, v24, v22, v23, (__int64)&v39);
      goto LABEL_46;
    }
    *(_OWORD *)v24 = 0;
    *(_QWORD *)(v24 + 16) = 0;
    *(_QWORD *)(v24 + 24) = 7;
    *(_WORD *)v24 = 0;
    goto LABEL_44;
  }
LABEL_52:
  sub_180046090(v4 + 9, a3);
  sub_18003FB30(v4 + 12, (__int64)(v4[10] - v4[9]) >> 2);
  v28 = 0;
  v29 = (int *)v4[10];
  for ( k = (int *)v4[9]; k != v29; ++k )
  {
    v31 = v28;
    v42 = v28++;
    v32 = (_DWORD *)v4[13];
    if ( v32 == (_DWORD *)v4[14] )
    {
      sub_1800E10AC(v4 + 12, v32, k, &v42);
    }
    else
    {
      v33 = *k;
      v32[1] = v31;
      *v32 = v33;
      v4[13] += 8LL;
    }
  }
  LOBYTE(v27) = 0;
  sub_1800E03B4(v4[12], v4[13], (__int64)(v4[13] - v4[12]) >> 3, v27);
  return v4;
}

```

## disassembly

```asm
0x1800dfa9c  mov     [rsp-38h+arg_8], rbx
0x1800dfaa1  mov     [rsp-38h+arg_0], rcx
0x1800dfaa6  push    rbp
0x1800dfaa7  push    rsi
0x1800dfaa8  push    rdi
0x1800dfaa9  push    r12
0x1800dfaab  push    r13
0x1800dfaad  push    r14
0x1800dfaaf  push    r15
0x1800dfab1  mov     rbp, rsp
0x1800dfab4  sub     rsp, 80h
0x1800dfabb  movaps  [rsp+80h+var_10], xmm6
0x1800dfac0  mov     r13, r8
0x1800dfac3  mov     rdi, rcx
0x1800dfac6  mov     [rbp+var_28], rcx
0x1800dfaca  xor     r12d, r12d
0x1800dfacd  mov     [rcx], r12
0x1800dfad0  mov     [rcx+8], r12
0x1800dfad4  mov     [rcx+10h], r12
0x1800dfad8  mov     [rcx+18h], r12
0x1800dfadc  mov     [rcx+20h], r12
0x1800dfae0  mov     [rcx+28h], r12
0x1800dfae4  mov     [rcx+30h], r12
0x1800dfae8  mov     [rcx+38h], r12
0x1800dfaec  mov     [rcx+40h], r12
0x1800dfaf0  mov     [rcx+48h], r12
0x1800dfaf4  mov     [rcx+50h], r12
0x1800dfaf8  mov     [rcx+58h], r12
0x1800dfafc  mov     [rcx+60h], r12
0x1800dfb00  mov     [rcx+68h], r12
0x1800dfb04  mov     [rcx+70h], r12
0x1800dfb08  mov     [rcx+78h], r12d
0x1800dfb0c  mov     rax, [r8+8]
0x1800dfb10  cmp     [r8], rax
0x1800dfb13  jz      loc_1800DFF43
0x1800dfb19  mov     r14, [rdx]
0x1800dfb1c  mov     rsi, [rdx+8]
0x1800dfb20  mov     [rbp+arg_18], rsi
0x1800dfb24  cmp     r14, rsi
0x1800dfb27  jz      loc_1800DFE35
0x1800dfb2d  xorps   xmm6, xmm6
0x1800dfb30  mov     rbx, [r14]
0x1800dfb33  mov     rbx, [rbx+30h]
0x1800dfb37  mov     [rbp+var_20], rbx
0x1800dfb3b  test    rbx, rbx
0x1800dfb3e  jz      short loc_1800DFB60
0x1800dfb40  mov     rax, [rbx]
0x1800dfb43  mov     rcx, rbx
0x1800dfb46  mov     rax, [rax]
0x1800dfb49  call    cs:__guard_dispatch_icall_fptr
0x1800dfb4f  mov     rax, [rbx]
0x1800dfb52  mov     rcx, rbx
0x1800dfb55  mov     rax, [rax+10h]
0x1800dfb59  call    cs:__guard_dispatch_icall_fptr
0x1800dfb5f  nop
0x1800dfb60  mov     rcx, [r14]
0x1800dfb63  mov     edx, [rcx+38h]
0x1800dfb66  sub     edx, 11h
0x1800dfb69  jz      loc_1800DFCC3
0x1800dfb6f  sub     edx, 1
0x1800dfb72  jz      loc_1800DFC21
0x1800dfb78  cmp     edx, 1
0x1800dfb7b  jnz     loc_1800DFF1E
0x1800dfb81  mov     rdx, [rdi+8]
0x1800dfb85  cmp     rdx, [rdi+10h]
0x1800dfb89  jz      short loc_1800DFBA1
0x1800dfb8b  mov     [rdx], r12
0x1800dfb8e  mov     [rdx+8], r12
0x1800dfb92  mov     [rdx+10h], r12
0x1800dfb96  mov     [rdx+18h], r12d
0x1800dfb9a  add     qword ptr [rdi+8], 20h ; ' '
0x1800dfb9f  jmp     short loc_1800DFBA9
0x1800dfba1  mov     rcx, rdi
0x1800dfba4  call    sub_1800E05E0
0x1800dfba9  mov     r15, [rdi+8]
0x1800dfbad  cmp     [rdi], r15
0x1800dfbb0  jz      loc_1800DFE64
0x1800dfbb6  mov     eax, [r14+8]
0x1800dfbba  mov     [r15-8], eax
0x1800dfbbe  movsd   [rbp+var_50], xmm6
0x1800dfbc3  mov     r12, [r13+8]
0x1800dfbc7  mov     rsi, [r13+0]
0x1800dfbcb  jmp     short loc_1800DFC17
0x1800dfbcd  mov     rax, [rbx]
0x1800dfbd0  mov     r9d, 1
0x1800dfbd6  lea     r8, [rbp+var_50]
0x1800dfbda  mov     edx, [rsi]
0x1800dfbdc  mov     rcx, rbx
0x1800dfbdf  mov     rax, [rax+30h]
0x1800dfbe3  call    cs:__guard_dispatch_icall_fptr
0x1800dfbe9  mov     rdx, [r15-18h]
0x1800dfbed  cmp     rdx, [r15-10h]
0x1800dfbf1  jz      short loc_1800DFC06
0x1800dfbf3  movsd   xmm0, [rbp+var_50]
0x1800dfbf8  movsd   qword ptr [rdx], xmm0
0x1800dfbfc  lea     rax, [rdx+8]
0x1800dfc00  mov     [r15-18h], rax
0x1800dfc04  jmp     short loc_1800DFC13
0x1800dfc06  lea     r8, [rbp+var_50]
0x1800dfc0a  lea     rcx, [r15-20h]
0x1800dfc0e  call    sub_180023AA8
0x1800dfc13  add     rsi, 4
0x1800dfc17  cmp     rsi, r12
0x1800dfc1a  jnz     short loc_1800DFBCD
0x1800dfc1c  jmp     loc_1800DFDFC
0x1800dfc21  lea     rcx, [rdi+18h]
0x1800dfc25  mov     rdx, [rcx+8]
0x1800dfc29  cmp     rdx, [rcx+10h]
0x1800dfc2d  jz      short loc_1800DFC45
0x1800dfc2f  mov     [rdx], r12
0x1800dfc32  mov     [rdx+8], r12
0x1800dfc36  mov     [rdx+10h], r12
0x1800dfc3a  mov     [rdx+18h], r12d
0x1800dfc3e  add     qword ptr [rcx+8], 20h ; ' '
0x1800dfc43  jmp     short loc_1800DFC4A
0x1800dfc45  call    sub_1800E05E0
0x1800dfc4a  mov     r15, [rdi+20h]
0x1800dfc4e  cmp     [rdi+18h], r15
0x1800dfc52  jz      loc_1800DFE7A
0x1800dfc58  mov     eax, [r14+8]
0x1800dfc5c  mov     [r15-8], eax
0x1800dfc60  movsd   [rbp+var_48], xmm6
0x1800dfc65  mov     r12, [r13+8]
0x1800dfc69  mov     rsi, [r13+0]
0x1800dfc6d  jmp     short loc_1800DFCB9
0x1800dfc6f  mov     rax, [rbx]
0x1800dfc72  mov     r9d, 1
0x1800dfc78  lea     r8, [rbp+var_48]
0x1800dfc7c  mov     edx, [rsi]
0x1800dfc7e  mov     rcx, rbx
0x1800dfc81  mov     rax, [rax+30h]
0x1800dfc85  call    cs:__guard_dispatch_icall_fptr
0x1800dfc8b  mov     rdx, [r15-18h]
0x1800dfc8f  cmp     rdx, [r15-10h]
0x1800dfc93  jz      short loc_1800DFCA8
0x1800dfc95  movsd   xmm0, [rbp+var_48]
0x1800dfc9a  movsd   qword ptr [rdx], xmm0
0x1800dfc9e  lea     rax, [rdx+8]
0x1800dfca2  mov     [r15-18h], rax
0x1800dfca6  jmp     short loc_1800DFCB5
0x1800dfca8  lea     r8, [rbp+var_48]
0x1800dfcac  lea     rcx, [r15-20h]
0x1800dfcb0  call    sub_180023AA8
0x1800dfcb5  add     rsi, 4
0x1800dfcb9  cmp     rsi, r12
0x1800dfcbc  jnz     short loc_1800DFC6F
0x1800dfcbe  jmp     loc_1800DFDFC
0x1800dfcc3  lea     rcx, [rdi+30h]
0x1800dfcc7  mov     rdx, [rcx+8]
0x1800dfccb  cmp     rdx, [rcx+10h]
0x1800dfccf  jz      short loc_1800DFCE7
0x1800dfcd1  mov     [rdx], r12
0x1800dfcd4  mov     [rdx+8], r12
0x1800dfcd8  mov     [rdx+10h], r12
0x1800dfcdc  mov     [rdx+18h], r12d
0x1800dfce0  add     qword ptr [rcx+8], 20h ; ' '
0x1800dfce5  jmp     short loc_1800DFCEC
0x1800dfce7  call    sub_1800E089C
0x1800dfcec  mov     r15, [rdi+38h]
0x1800dfcf0  cmp     [rdi+30h], r15
0x1800dfcf4  jz      loc_1800DFE90
0x1800dfcfa  mov     eax, [r14+8]
0x1800dfcfe  mov     [r15-8], eax
0x1800dfd02  mov     [rbp+var_40], r12
0x1800dfd06  mov     r12, [r13+0]
0x1800dfd0a  mov     rax, [r13+8]
0x1800dfd0e  cmp     r12, rax
0x1800dfd11  jz      loc_1800DFE00
0x1800dfd17  mov     rdi, rax
0x1800dfd1a  mov     rax, [rbx]
0x1800dfd1d  mov     r9d, 1
0x1800dfd23  lea     r8, [rbp+var_40]
0x1800dfd27  mov     edx, [r12]
0x1800dfd2b  mov     rcx, rbx
0x1800dfd2e  mov     rax, [rax+38h]
0x1800dfd32  call    cs:__guard_dispatch_icall_fptr
0x1800dfd38  mov     rsi, [r15-18h]
0x1800dfd3c  mov     rdx, [rbp+var_40]
0x1800dfd40  xor     ecx, ecx
0x1800dfd42  lea     rax, [rbp+arg_10]
0x1800dfd46  test    rdx, rdx
0x1800dfd49  jz      short loc_1800DFDA6
0x1800dfd4b  mov     byte ptr [rbp+arg_10], cl
0x1800dfd4e  mov     [rbp+var_38], rax
0x1800dfd52  lea     rax, [rbp+var_40]
0x1800dfd56  mov     [rbp+var_30], rax
0x1800dfd5a  cmp     rsi, [r15-10h]
0x1800dfd5e  jz      short loc_1800DFD8B
0x1800dfd60  mov     [rbp+var_30], rsi
0x1800dfd64  xorps   xmm0, xmm0
0x1800dfd67  movups  xmmword ptr [rsi], xmm0
0x1800dfd6a  mov     [rsi+10h], rcx
0x1800dfd6e  mov     [rsi+18h], rcx
0x1800dfd72  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800dfd76  inc     r8
0x1800dfd79  cmp     [rdx+r8*2], cx
0x1800dfd7e  jnz     short loc_1800DFD76
0x1800dfd80  mov     rcx, rsi
0x1800dfd83  call    sub_180008F04
0x1800dfd88  nop
0x1800dfd89  jmp     short loc_1800DFDC9
0x1800dfd8b  lea     rax, [rbp+var_38]
0x1800dfd8f  mov     [rsp+80h+Reserved], rax
0x1800dfd94  lea     r9, [rbp+var_30]
0x1800dfd98  mov     rdx, rsi
0x1800dfd9b  lea     rcx, [r15-20h]
0x1800dfd9f  call    sub_1800E0B48
0x1800dfda4  jmp     short loc_1800DFDEB
0x1800dfda6  mov     byte ptr [rbp+arg_10], 1
0x1800dfdaa  mov     [rbp+var_30], rax
0x1800dfdae  cmp     rsi, [r15-10h]
0x1800dfdb2  jz      short loc_1800DFDD6
0x1800dfdb4  xorps   xmm0, xmm0
0x1800dfdb7  movups  xmmword ptr [rsi], xmm0
0x1800dfdba  mov     [rsi+10h], rcx
0x1800dfdbe  mov     qword ptr [rsi+18h], 7
0x1800dfdc6  mov     [rsi], cx
0x1800dfdc9  mov     al, byte ptr [rbp+arg_10]
0x1800dfdcc  mov     [rsi+20h], al
0x1800dfdcf  add     qword ptr [r15-18h], 28h ; '('
0x1800dfdd4  jmp     short loc_1800DFDEB
0x1800dfdd6  lea     rax, [rbp+var_30]
0x1800dfdda  mov     [rsp+80h+Reserved], rax
0x1800dfddf  mov     rdx, rsi
0x1800dfde2  lea     rcx, [r15-20h]
0x1800dfde6  call    sub_1800E0E18
0x1800dfdeb  add     r12, 4
0x1800dfdef  cmp     r12, rdi
0x1800dfdf2  jnz     loc_1800DFD1A
0x1800dfdf8  mov     rdi, [rbp+var_28]
0x1800dfdfc  mov     rsi, [rbp+arg_18]
0x1800dfe00  xor     r12d, r12d
0x1800dfe03  test    rbx, rbx
0x1800dfe06  jz      short loc_1800DFE28
0x1800dfe08  mov     rax, [rbx]
0x1800dfe0b  mov     rcx, rbx
0x1800dfe0e  mov     rax, [rax+18h]
0x1800dfe12  call    cs:__guard_dispatch_icall_fptr
0x1800dfe18  mov     rax, [rbx]
0x1800dfe1b  mov     rcx, rbx
0x1800dfe1e  mov     rax, [rax+8]
0x1800dfe22  call    cs:__guard_dispatch_icall_fptr
0x1800dfe28  add     r14, 10h
0x1800dfe2c  cmp     r14, rsi
0x1800dfe2f  jnz     loc_1800DFB30
0x1800dfe35  lea     rbx, [rdi+48h]
0x1800dfe39  mov     rdx, r13
0x1800dfe3c  mov     rcx, rbx
0x1800dfe3f  call    sub_180046090
0x1800dfe44  mov     rdx, [rbx+8]
0x1800dfe48  sub     rdx, [rbx]
0x1800dfe4b  sar     rdx, 2
0x1800dfe4f  lea     rcx, [rdi+60h]
0x1800dfe53  call    sub_18003FB30
0x1800dfe58  mov     esi, r12d
0x1800dfe5b  mov     r14, [rbx+8]
0x1800dfe5f  mov     rbx, [rbx]
0x1800dfe62  jmp     short loc_1800DFEDB
0x1800dfe64  mov     [rsp+80h+Reserved], r12; Reserved
0x1800dfe69  xor     r9d, r9d; LineNo
0x1800dfe6c  xor     r8d, r8d; FileName
0x1800dfe6f  xor     edx, edx; FunctionName
0x1800dfe71  xor     ecx, ecx; Expression
0x1800dfe73  call    cs:_invoke_watson
0x1800dfe7a  mov     [rsp+80h+Reserved], r12; Reserved
0x1800dfe7f  xor     r9d, r9d; LineNo
0x1800dfe82  xor     r8d, r8d; FileName
0x1800dfe85  xor     edx, edx; FunctionName
0x1800dfe87  xor     ecx, ecx; Expression
0x1800dfe89  call    cs:_invoke_watson
0x1800dfe90  mov     [rsp+80h+Reserved], r12; Reserved
0x1800dfe95  xor     r9d, r9d; LineNo
0x1800dfe98  xor     r8d, r8d; FileName
0x1800dfe9b  xor     edx, edx; FunctionName
0x1800dfe9d  xor     ecx, ecx; Expression
0x1800dfe9f  call    cs:_invoke_watson
0x1800dfea6  lea     rcx, [rdi+60h]
0x1800dfeaa  mov     r8d, esi
0x1800dfead  mov     [rbp+arg_10], esi
0x1800dfeb0  inc     esi
0x1800dfeb2  mov     rdx, [rcx+8]
0x1800dfeb6  cmp     rdx, [rcx+10h]
0x1800dfeba  jz      short loc_1800DFECB
0x1800dfebc  mov     eax, [rbx]
0x1800dfebe  mov     [rdx+4], r8d
0x1800dfec2  mov     [rdx], eax
0x1800dfec4  add     qword ptr [rcx+8], 8
0x1800dfec9  jmp     short loc_1800DFED7
0x1800dfecb  lea     r9, [rbp+arg_10]
0x1800dfecf  mov     r8, rbx
0x1800dfed2  call    sub_1800E10AC
0x1800dfed7  add     rbx, 4
0x1800dfedb  cmp     rbx, r14
0x1800dfede  jnz     short loc_1800DFEA6
0x1800dfee0  mov     rdx, [rdi+68h]
0x1800dfee4  mov     rcx, [rdi+60h]
0x1800dfee8  mov     r8, rdx
0x1800dfeeb  sub     r8, rcx
0x1800dfeee  sar     r8, 3
0x1800dfef2  mov     r9b, r12b
  ... truncated ...
```
